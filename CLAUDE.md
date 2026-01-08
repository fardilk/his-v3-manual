 
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
- **Uses PDF with page reference**: `images/pdf/[module-name].pdf`
- **Page number = Image number** (e.g., `001.png` → `page=1`, `012.png` → `page=12`)
- Format:
```latex
\begin{figure}[H]
\centering
    \includegraphics[width=\textwidth,page=1]{images/pdf/[module-name].pdf}
\caption{Deskripsi gambar dalam Bahasa Indonesia}
\label{fig:[module-name]-[number]}
\end{figure}
```

#### 2. INLINE-IMAGE (Button/Icon)
- Marked with **"INLINE-IMAGE"** at top of image
- Used for small buttons, icons, or UI elements
- **Uses PDF with page reference**: `images/pdf/his-v3-baru-2025.pdf`
- **Page number = Image number** (e.g., `009.png` → `page=9`, `044.png` → `page=44`)
- Format:
```latex
$\vcenter{\hbox{\includegraphics[height=.6cm, page=9]{images/pdf/his-v3-baru-2025.pdf}}}$
```

### Section Structure
```latex
\section{Main Title}

\par Penjelasan modul dalam Bahasa Indonesia...

Langkah-langkah melakukan [nama proses]:

\begin{itemize}
    \item Langkah pertama...
\end{itemize}
```
- **NO `\subsection`** - use plain text as list introduction instead

### Itemize (Steps)
```latex
\begin{itemize}
    \item Langkah pertama
    \item Klik tombol $\vcenter{\hbox{\includegraphics[height=.6cm, page=9]{images/pdf/his-v3-baru-2025.pdf}}}$ untuk menyimpan
        \begin{figure}[H]
        \centering
            \includegraphics[width=\textwidth,page=1]{images/pdf/module-name.pdf}
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
- In LaTeX, uses module PDF: `images/pdf/[module-name].pdf`
- **Page number = Image filename number** (e.g., `005.png` → `page=5`)
- Example: `\includegraphics[width=\textwidth,page=5]{images/pdf/pendaftaran-kunjungan-laboratorium.pdf}`

### INLINE-IMAGE (Buttons/Icons)
- Referenced from PDF: `images/pdf/his-v3-baru-2025.pdf`
- **Page number = Image filename number** (e.g., `009.png` → `page=9`)
- Example: `\includegraphics[height=.6cm, page=9]{images/pdf/his-v3-baru-2025.pdf}`

## Naming Convention
- Module name: kebab-case (example: `radiology-visit`)
- Label: `fig:[module-name]-[number]`