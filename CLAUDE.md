 
# HIS v3 User Manual Generator

## Project Overview
Workspace for generating HIS v3 user manual documentation in LaTeX format.

## Language
- **ALL output MUST be written in BAHASA INDONESIA**
- Captions, descriptions, steps, and explanations must use Indonesian language
- Technical terms (menu names, button labels) may remain in English if that's how they appear in the UI

## Output Format
- Output files are `.md` files containing LaTeX code (for easy copy-paste into main LaTeX document)
- Files saved to: `sections/[module-name].md`

## Directory Structure
```
HISv3/
├── AGENTS.md          # Agent behaviors & roles
├── CLAUDE.md          # This file - project instructions
├── exports/           # Final compiled LaTeX files
├── module/            # Module definitions & context
│   └── README.md      # Module registry
├── screenshots/       # Source images (1.jpg, 2.jpg, etc)
└── sections/          # Generated LaTeX sections (.md files)
    └── todos.md       # Task queue
```

## LaTeX Formatting Standards

### Paragraph
- ALWAYS use `\par` to start a new paragraph
- Example: `\par Radiology is a service...`

### Image Types
Screenshots are marked with a label at the TOP of the image:

#### 1. FIGURE (Full Width Screenshot)
- Marked with **"FIGURE"** at top of image
- Used for full UI screenshots
- Format:
```latex
\begin{figure}[H]
\centering
    \includegraphics[width=\textwidth]{images/[module-name]/[number].jpg}
\caption{Deskripsi gambar dalam Bahasa Indonesia}
\label{fig:[module-name]-[number]}
\end{figure}
```

#### 2. INLINE-IMAGE (Button/Icon)
- Marked with **"INLINE-IMAGE"** at top of image
- Used for small buttons, icons, or UI elements
- **IMPORTANT**: Uses PDF page reference, NOT individual image file
- Format:
```latex
$\vcenter{\hbox{\includegraphics[height=.6cm, page=XX]{images/pdf/his-v3-baru-2025.pdf}}}$
```
- Replace `XX` with the actual page number from the PDF
- The page number will be noted in the screenshot or context file

### Section Structure
```latex
\section{Main Title}
\par Explanatory paragraph...

\subsection{Sub Section}
\par Sub section explanation...
```

### Itemize (Steps)
```latex
\begin{itemize}
    \item Langkah pertama
    \item Klik tombol $\vcenter{\hbox{\includegraphics[height=.6cm, page=44]{images/pdf/his-v3-baru-2025.pdf}}}$ untuk menyimpan
        \begin{figure}[H]
        \centering
            \includegraphics[width=\textwidth]{images/module-name/1.jpg}
        \caption{Deskripsi dalam Bahasa Indonesia}
        \label{fig:module-name-1}
        \end{figure}
    \item Langkah selanjutnya
\end{itemize}
```

### Notes/Warning Box (mdframed)
```latex
\begin{mdframed}[backgroundcolor=yellow!20]
\textbf{Note:} Important information here
\end{mdframed}
```

### Bold Text
- Use `\textbf{text}` for menus, buttons, or important terms
- Example: `\textbf{Patient Visit}`, `\textbf{Save}`

## Workflow

1. **Seeding**: User uploads screenshots to `screenshots/[module-name]/` with sequential names (1.jpg, 2.jpg, etc)
   - Mark each image at TOP with either **"FIGURE"** or **"INLINE-IMAGE"**
   - For INLINE-IMAGE: include the PDF page number in the marking
2. **Context**: User creates context file in `module/[module-name].md`
3. **Generate**: Run `/generate-section [module-name]`
4. **Review**: Run `/review [module-name]`
5. **Export**: Final LaTeX code (in .md files) ready in `sections/`

## Image Path Convention

### FIGURE Images
- Screenshots stored in: `screenshots/[module-name]/`
- In LaTeX, path becomes: `images/[module-name]/[number].jpg`

### INLINE-IMAGE (Buttons/Icons)
- Referenced from PDF: `images/pdf/his-v3-baru-2025.pdf`
- Use `page=XX` parameter to specify the page number
- Example: `\includegraphics[height=.6cm, page=44]{images/pdf/his-v3-baru-2025.pdf}`

## Naming Convention
- Module name: kebab-case (example: `radiology-visit`)
- Label: `fig:[module-name]-[number]`