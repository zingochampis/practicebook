# GitHub Repository to PDF Exporter - User Manual

## Table of Contents
1. [Overview](#overview)
2. [Getting Started](#getting-started)
3. [Using the Application](#using-the-application)
4. [Creating and Organizing Content on GitHub](#creating-and-organizing-content-on-github)
5. [Best Practices](#best-practices)
6. [Troubleshooting](#troubleshooting)

## Overview

The GitHub Repository to PDF Exporter is a web-based tool that allows you to:
- Browse any public GitHub repository
- Select specific files to include in your PDF
- Export selected files as a formatted PDF document with proper sections
- Preserve formatting for Markdown files and special characters (including Unicode)

### Key Features
- **Full UTF-8 Support**: Correctly displays special characters, accented letters, and non-Latin scripts
- **Markdown Rendering**: Automatically formats `.md` files with headers, lists, code blocks, etc.
- **Section Organization**: Files are grouped by their folder structure
- **Page Formats**: Choose between A4 or US Letter paper sizes
- **Pagination**: Automatic page breaks with alternating page numbers

## Getting Started

### Requirements
- A modern web browser (Chrome, Firefox, Safari, or Edge)
- Internet connection to access GitHub repositories
- The HTML file saved locally on your computer

### Installation
1. Save the HTML file to your computer
2. Open the file in your web browser by double-clicking it
3. No additional installation or dependencies required!

## Using the Application

### Step 1: Load a Repository
1. Enter a GitHub repository URL in one of these formats:
   - Full URL: `https://github.com/owner/repository`
   - Short format: `owner/repository`
2. Click "Load Repository" or press Enter
3. Wait for the repository structure to load in the left panel

### Step 2: Browse and Select Files
1. **Folders** appear with a folder icon - click to expand/collapse
2. **Files** appear with checkboxes - click the checkbox or anywhere on the file row to select
3. Selected files immediately appear in the right preview panel
4. Deselect files by unchecking them

### Step 3: Choose Page Format
- Use the toggle switch in the top-right to select:
  - **A4** (210×297mm) - Default, shown in blue
  - **Letter** (8.5×11 inches) - Toggle to green

### Step 4: Export to PDF
1. Click the "Export to PDF" button (enabled when files are selected)
2. Wait for the PDF generation (may take a few seconds for many files)
3. The PDF will automatically download with the filename:
   - `github-export-a4.pdf` or
   - `github-export-letter.pdf`

## Creating and Organizing Content on GitHub

### Understanding Sections
In the PDF exporter, **sections** are created from your repository's folder structure:
- Root-level files appear in the "Root" section
- Each folder becomes its own section
- Nested folders create sub-sections

### Creating a New Section
To create a new section in your PDF:

1. **On GitHub.com:**
   - Navigate to your repository
   - Click "Create new file"
   - Type `YourSectionName/README.md` (the `/` creates a folder)
   - Add content and commit

2. **Using Git locally:**
   ```bash
   mkdir YourSectionName
   cd YourSectionName
   echo "# Section Title" > README.md
   git add .
   git commit -m "Add new section"
   git push
   ```

### Creating Markdown Files

#### Basic Markdown Structure
Create a new `.md` file with this template:

```markdown
# Document Title

## Introduction
Your introduction text here.

## Main Content

### Subsection 1
Content with **bold** and *italic* text.

### Subsection 2
- Bullet point 1
- Bullet point 2
  - Nested point

## Code Examples

```python
def hello_world():
    print("Hello, World!")
```

## Conclusion
Your conclusion here.
```
```
#### Markdown Elements Supported
- **Headers**: `#` through `######` (H1-H6)
- **Bold**: `**text**` or `__text__`
- **Italic**: `*text*` or `_text_`
- **Code**: Inline `` `code` `` or code blocks
- **Lists**: Ordered (`1. `) and unordered (`- ` or `* `)
- **Blockquotes**: `> quoted text`
- **Links**: `[text](url)`
- **Images**: `![alt text](url)` (shows as alt text in PDF)

### Repository Structure Example

```
my-documentation/
├── README.md                    # Root section
├── introduction/               # "introduction" section
│   ├── getting-started.md
│   └── requirements.md
├── tutorials/                  # "tutorials" section
│   ├── basic-tutorial.md
│   ├── advanced-tutorial.md
│   └── examples/              # "examples" subsection
│       └── example1.md
└── reference/                  # "reference" section
    ├── api-reference.md
    └── configuration.md
```

This structure creates sections: Root, introduction, tutorials, examples, and reference.

## Best Practices

### For GitHub Organization
1. **Use descriptive folder names** - They become section titles
2. **Add README.md to each folder** - Provides section introduction
3. **Number files for ordering** - e.g., `01-introduction.md`, `02-setup.md`
4. **Keep file names concise** - They appear as titles in the PDF

### For Markdown Content
1. **Start with a clear H1 header** - Becomes the document title
2. **Use proper heading hierarchy** - Don't skip levels (H1 → H3)
3. **Add blank lines between sections** - Improves readability
4. **Use code blocks for examples** - Preserves formatting

### For PDF Generation
1. **Preview before exporting** - Check the right panel
2. **Select related files together** - Maintains context
3. **Consider file size** - Very large repositories may take time
4. **Check special characters** - Ensure they display correctly

## Troubleshooting

### Common Issues

**"Failed to fetch file content"**
- Check if the repository is public
- Verify your internet connection
- Try refreshing the page and reloading the repository

**Special characters not displaying**
- Ensure the source files are UTF-8 encoded
- Check that characters display correctly on GitHub first

**PDF generation takes too long**
- Reduce the number of selected files
- Select smaller files
- Close other browser tabs to free memory

**Toggle switch not working**
- Ensure JavaScript is enabled
- Try a different browser
- Check browser console for errors (F12)

### GitHub API Limits
- Unauthenticated requests: 60 per hour
- If you hit the limit, wait an hour or use a different IP

### File Size Limitations
- GitHub API limits file size to 1MB for content API
- Larger files won't load and will show an error

## Tips and Tricks

1. **Quick Selection**: Click anywhere on a file row to toggle selection
2. **Bulk Operations**: Open all folders first, then select multiple files quickly
3. **Format Testing**: Generate both A4 and Letter to see which works better
4. **Section Planning**: Organize your GitHub repo structure before creating content
5. **Multi-language Support**: Test with a few files first if using non-Latin scripts

---

*Note: This tool works with public repositories only. For private repositories, you would need to modify the code to include authentication tokens.*
