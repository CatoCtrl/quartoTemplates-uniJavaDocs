# uniJavaDocs (Quarto PDF Template)

A professional Quarto template for PDF generation with custom formatting.

## Features

- **Title Page**: Centered title on a dedicated first page
- **Page Layout**: 
  - Left margin: 3cm
  - Right blank space: ~1/3 of page (A4: set right=7cm)
  - Top/bottom margins: 2.5cm
- **Page Numbers**: Centered at the bottom of each page
- **Table of Contents**: Includes only level 1 headings
- **Line Spacing**: 2-point line spacing throughout the document
- **Code Blocks**: 
  - Monospace font with proper formatting
  - Respects margins and spacing constraints
  - Intelligent line breaking with hook arrow indicators (↪)
  - Auto-indents broken lines for readability

## Template Structure

```
uniJavaDocs/
├── _quarto.yml       # Quarto project configuration
├── template.yml      # Template metadata (copied into new project)
├── header.tex        # LaTeX formatting definitions
├── template.qmd      # Clean template document to edit
└── README.md         # This file
```

## Quick Start

### Option 1: Direct Use

1. Copy the template directory:
   ```bash
   cp -r uniJavaDocs my-project
   cd my-project
   ```

2. Edit `template.qmd` and change the title:
   ```yaml
   ---
   title: "Your Title Here"
   ---
   ```

3. Write your content using standard Markdown syntax

4. Render to PDF:
   ```bash
   quarto render template.qmd
   ```

### Option 2: Use with `quarto use template`

- **Local path**:
  ```bash
  quarto use template /absolute/path/to/uniJavaDocs
  ```

- **GitHub** (after pushing to a repository):
  ```bash
  quarto use template <your-github-username>/uniJavaDocs
  ```

**To publish on GitHub**:
```bash
cd /path/to/uniJavaDocs
# Create an empty repo named uniJavaDocs on GitHub, then:
git remote add origin git@github.com:<your-github-username>/uniJavaDocs.git
git branch -M main
git push -u origin main
```

## Usage Guide

### Document Structure

Edit `template.qmd` with your content:

```markdown
---
title: "Your Document Title"
---

# Level 1 Heading

Your content here with automatic 2-point line spacing.

## Level 2 Heading

This does NOT appear in the table of contents.

### Level 3 Heading

This also does NOT appear in the table of contents.

## Code Example

\```python
# Code with proper margins and line breaking
def example():
    return "Hello World"
\```
```

### Customization

Edit `_quarto.yml` to customize:

- **Margins**: Change `geometry` settings
- **Line spacing**: Adjust `linestretch` value
- **TOC depth**: Modify `toc-depth`
- **Sections**: Toggle `number-sections`
- **Paper size**: Uses A4 by default via `geometry: [a4paper]`; adjust `right` accordingly for other sizes (e.g., Letter ≈ 7.2cm)

Edit `header.tex` for advanced LaTeX customization.

## Testing

Test the template by rendering the example:
```bash
quarto render template.qmd
```

Verify the PDF output includes:
- Separate title page
- Table of contents with Level 1 headings only
- Correct margins (3cm left, ~1/3 page blank on right; A4: 7cm right margin)
- Page numbers at bottom center
- Proper line spacing and code block formatting

## Requirements

- Quarto (tested with recent versions)
- LaTeX distribution with:
  - xelatex
  - fancyhdr package
  - titling package
  - fvextra package
  - listings package

Most standard LaTeX installations include these packages.

## Notes

- No additional installations required beyond standard Quarto/LaTeX setup
- All formatting is applied automatically via configuration
- Clean separation of content (`template.qmd`) and styling (`_quarto.yml`, `header.tex`)
- Template is self-contained and portable
