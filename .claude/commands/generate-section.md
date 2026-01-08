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
   - **Check for subsections**: If module file contains `## subsections` section, use `\subsection{}` commands in output

2. **Analyze Screenshots**
   - Open each image sequentially (1.jpg, 2.jpg, ...)
   - **Check the marking at TOP of each image:**
     - **"FIGURE"** → Full width screenshot, use `\begin{figure}[H]...\end{figure}`
     - **"INLINE-IMAGE"** → Button/icon, use `$\vcenter{\hbox{\includegraphics[height=.6cm, page=XX]{images/pdf/his-v3-baru-2025.pdf}}}$`
   - **For INLINE-IMAGE: page number = image number** (e.g., `009.png` → `page=9`)
   - Identify UI state and action in each image
   - Map to flow defined in context

3. **Generate LaTeX**
   - Follow standard format in CLAUDE.md
   - **Write ALL content in BAHASA INDONESIA**
   - **For FIGURE images**: use `images/pdf/[module-name].pdf` with `page=X` (X = image number)
   - **For INLINE-IMAGE**: use `images/pdf/his-v3-baru-2025.pdf` with `page=X` (X = image number)
   - **If module has subsections defined**: Output includes `\subsection{}` for each subsection
   - **If module has no subsections**: Use plain text without `\subsection{}`
   - Output to `sections/[module-name].md` (LaTeX code in markdown file)

4. **Update Todo**
   - Mark as generated in `sections/todos.md`

## Output
File: `sections/[module-name].md` (contains LaTeX code ready for copy-paste)