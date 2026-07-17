# PPTX to Markdown Conversion — Knowledge Reference

## Purpose

This document captures the process and knowledge needed to convert PowerPoint (.pptx) content into Markdown format using the `python-pptx` library.

---

## 1. Tools and Library

### python-pptx

- **Install:** `pip install python-pptx`
- **Role:** Read .pptx file structure (slides, shapes, text frames, tables, notes).
- **No dependency on:** Microsoft Office or LibreOffice.

---

## 2. PPTX File Structure

```
Presentation
├── Slides[]
│   ├── slide_layout (source layout name)
│   ├── shapes[] (each shape is an object on the slide)
│   │   ├── has_text_frame → text_frame.paragraphs[]
│   │   │   ├── paragraph.text
│   │   │   └── paragraph.level (indent level: 0, 1, 2...)
│   │   ├── has_table → table.rows[] → row.cells[]
│   │   ├── is_placeholder → placeholder_format.idx
│   │   └── shape_id (compare with title shape)
│   └── has_notes_slide → notes_slide.notes_text_frame.text
```

### Key Shape Types

| Type | Detection | Content |
| --- | --- | --- |
| Title | `slide.shapes.title` | Slide title |
| Text Box | `shape.has_text_frame` | Multi-paragraph text |
| Table | `shape.has_table` | Tabular data |
| Placeholder | `shape.is_placeholder` | Shape inherited from layout |
| Image | `shape.shape_type == MSO_SHAPE_TYPE.PICTURE` | Image (no text extraction) |

---

## 3. Python Script

```python
from pptx import Presentation

def pptx_to_markdown(pptx_path):
    prs = Presentation(pptx_path)
    output = []

    for i, slide in enumerate(prs.slides, 1):
        output.append(f'# Slide {i}')
        output.append('')

        # Layout name
        layout_name = slide.slide_layout.name if slide.slide_layout else 'Unknown'
        output.append(f'**Layout:** {layout_name}')
        output.append('')

        # Title
        if slide.shapes.title:
            title_text = slide.shapes.title.text.strip()
            if title_text:
                output.append(f'## {title_text}')
                output.append('')

        # All shapes
        for shape in slide.shapes:
            # Skip title (already handled)
            if slide.shapes.title and shape.shape_id == slide.shapes.title.shape_id:
                continue

            if shape.has_text_frame:
                text = shape.text_frame.text.strip()
                if not text:
                    continue

                # Placeholder info
                ph_info = ''
                if shape.is_placeholder:
                    ph_info = f' (placeholder idx={shape.placeholder_format.idx})'

                output.append(f'**Shape{ph_info}:**')
                for para in shape.text_frame.paragraphs:
                    para_text = para.text.strip()
                    if para_text:
                        level = para.level if para.level else 0
                        indent = '  ' * level
                        output.append(f'{indent}- {para_text}')
                output.append('')

            elif shape.has_table:
                table = shape.table
                output.append('**Table:**')
                output.append('')
                # Header row
                header = '| ' + ' | '.join(
                    cell.text.strip() for cell in table.rows[0].cells
                ) + ' |'
                separator = '| ' + ' | '.join(
                    '---' for _ in table.rows[0].cells
                ) + ' |'
                output.append(header)
                output.append(separator)
                # Data rows
                for row in table.rows[1:]:
                    row_text = '| ' + ' | '.join(
                        cell.text.strip() for cell in row.cells
                    ) + ' |'
                    output.append(row_text)
                output.append('')

        # Speaker notes
        if slide.has_notes_slide:
            notes_text = slide.notes_slide.notes_text_frame.text.strip()
            if notes_text:
                output.append('**Speaker Notes:**')
                output.append(f'{notes_text}')
                output.append('')

        output.append('---')
        output.append('')

    return '\n'.join(output)


# Usage
if __name__ == '__main__':
    md_content = pptx_to_markdown('path/to/file.pptx')
    with open('output.md', 'w', encoding='utf-8') as f:
        f.write(md_content)
```

---

## 4. Conversion Rules

### 4.1 Heading Mapping

| PPTX Element | Markdown |
| --- | --- |
| Slide number | `# Slide N` |
| Slide title | `## Title text` |
| Sub-section (post-processing) | `### Subtitle` |

### 4.2 Text and Bullets

- Each paragraph in a text frame maps to a bullet `-`.
- `paragraph.level` determines indentation:
  - Level 0 → `- text`
  - Level 1 → `  - text`
  - Level 2 → `    - text`

### 4.3 Tables

- First row → header row.
- Separator `| --- | --- |` immediately after header.
- Remaining rows → data rows.

### 4.4 Speaker Notes

- Placed under `**Speaker Notes:**` at the end of each slide section.
- Content preserved as-is without additional formatting.

### 4.5 Images and Media

- `python-pptx` cannot extract text from images.
- Note their existence: `[Image: filename or description]` if needed.
- To extract image files: use `shape.image.blob` to save bytes.

---

## 5. Post-Processing: Raw → Readable Markdown

After raw extraction, post-process to create a human-friendly file:

| Step | Description |
| --- | --- |
| Group related shapes | Multiple shapes on the same slide may form one concept → combine into a table or list |
| Identify flow/sequence | If the slide describes a process → use numbered list `1. 2. 3.` |
| Create tables | When there are multiple label-description pairs → consolidate into a table |
| Blockquotes | Use `>` for footnotes, disclaimers, or caveats |
| Remove noise | Slide number placeholders, empty shapes, leftover template text |
| Preserve language | Do not translate content — keep English/Vietnamese as-is from the slide |

---

## 6. Important Notes

1. **Encoding:** Always use `encoding='utf-8'` when writing files — required for non-ASCII content (e.g., Vietnamese).
2. **Shape order:** The order of shapes in `slide.shapes` is z-order (back→front), not reading order (left→right, top→bottom). Reorder based on content for readable output.
3. **Grouped shapes:** Shapes inside a group (`GroupShape`) require recursing into `shape.shapes` to access inner content.
4. **Placeholder idx values:**
   - `idx=0` → Title
   - `idx=1` → Body/Content
   - `idx=12` → Slide number
   - Other idx values depend on the layout
5. **Layout name:** Useful for understanding slide purpose (Section Header, Blank, Title Only, Two Content, etc.).
6. **Template file:** Never overwrite the original template — read only.

---

## 7. Limitations

- Cannot extract text from SmartArt (SmartArt consists of complex grouped shapes).
- Cannot extract text from embedded charts.
- Does not preserve font formatting (bold, italic, color) in plain markdown — requires processing `run.font` for that.
- Animations and transitions are not represented in output.
- Hyperlinks: must be read separately from `run.hyperlink`.

---

## 8. Extensions (Optional)

### Extract Bold/Italic

```python
for para in shape.text_frame.paragraphs:
    for run in para.runs:
        text = run.text
        if run.font.bold:
            text = f'**{text}**'
        if run.font.italic:
            text = f'*{text}*'
```

### Extract Images

```python
from pptx.enum.shapes import MSO_SHAPE_TYPE

for shape in slide.shapes:
    if shape.shape_type == MSO_SHAPE_TYPE.PICTURE:
        image = shape.image
        image_bytes = image.blob
        ext = image.content_type.split('/')[-1]
        filename = f'slide{i}_image.{ext}'
        with open(filename, 'wb') as f:
            f.write(image_bytes)
```

### Extract Hyperlinks

```python
for para in shape.text_frame.paragraphs:
    for run in para.runs:
        if run.hyperlink and run.hyperlink.address:
            text = f'[{run.text}]({run.hyperlink.address})'
```
