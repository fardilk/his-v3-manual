 
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

### Images (Full Width)
```latex
\begin{figure}[H]
\centering
    \includegraphics[width=\textwidth]{images/module-name/1.jpg}
\caption{Image description}
\label{fig:module-name-1}
\end{figure}
```

### Inline Images (Button/Icon)
```latex
click the button $\vcenter{\hbox{\includegraphics[height=.6cm]{images/module-name/button.jpg}}}$
```

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
    \item First step
    \item Second step
        \begin{figure}[H]
        \centering
            \includegraphics[width=\textwidth]{images/module-name/1.jpg}
        \caption{Caption}
        \label{fig:label}
        \end{figure}
    \item Third step
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
2. **Context**: User creates context file in `module/[module-name].md`
3. **Generate**: Run `/generate-section [module-name]`
4. **Review**: Run `/review [module-name]`
5. **Export**: Final LaTeX code (in .md files) ready in `sections/`

## Image Path Convention
- Screenshots stored in: `screenshots/[module-name]/`
- In LaTeX, path becomes: `images/[module-name]/[number].jpg`

## Naming Convention
- Module name: kebab-case (example: `radiology-visit`)
- Label: `fig:[module-name]-[number]`