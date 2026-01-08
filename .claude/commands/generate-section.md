# Generate Section Command

Generate LaTeX documentation for a specific module.

## Usage
```
/generate-section [module-name]
```

## Process

1. **Load Context**
   - Read `module/[module-name].md`
   - Validate screenshots exist in `screenshots/[module-name]/`

2. **Analyze Screenshots**
   - Open each image sequentially (1.jpg, 2.jpg, ...)
   - **Check the marking at TOP of each image:**
     - **"FIGURE"** → Full width screenshot, use `\begin{figure}[H]...\end{figure}`
     - **"INLINE-IMAGE"** → Button/icon, use `$\vcenter{\hbox{\includegraphics[height=.6cm, page=XX]{images/pdf/his-v3-baru-2025.pdf}}}$`
   - For INLINE-IMAGE: note the PDF page number from the marking
   - Identify UI state and action in each image
   - Map to flow defined in context

3. **Generate LaTeX**
   - Follow standard format in CLAUDE.md
   - **Write ALL content in BAHASA INDONESIA**
   - For FIGURE images: use path `images/[module-name]/[number].jpg`
   - For INLINE-IMAGE: use PDF path with correct page number
   - Output to `sections/[module-name].md` (LaTeX code in markdown file)

4. **Update Todo**
   - Mark as generated in `sections/todos.md`

## Output
File: `sections/[module-name].md` (contains LaTeX code ready for copy-paste)