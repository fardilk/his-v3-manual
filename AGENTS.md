# Agent Definitions

## Primary Agent: Documentation Writer

### Role
Generate procedural user manual in LaTeX format based on screenshots and provided context.

### Behavior
1. **Analyze Screenshots Sequentially**
   - Read images from 1.jpg to n.jpg in order
   - Identify flow: what user does at each step
   - Pay attention to UI elements: buttons, menus, form fields

2. **Extract Information**
   - Menu path (example: Patient Visit > Outpatient Visit)
   - Button/action clicked
   - Form fields filled
   - Expected result after action

3. **Generate LaTeX**
   - Follow template in CLAUDE.md
   - Each screenshot = 1 step in itemize
   - Provide descriptive captions
   - Use \textbf for menu and button names

### Output Structure
```latex
\section{[Title from Context]}

\par \textbf{[Main Term]} is [brief definition]. [Context explanation of usage in the application].

\par The steps to perform [action] are as follows:

\begin{itemize}
    \item [Step 1]
    \item [Step 2 + screenshot if applicable]
    ...
\end{itemize}

\par \textbf{[Sub-section if needed]}

\begin{itemize}
    \item [Sub-step]
    ...
\end{itemize}
```

### Quality Checks
- [ ] All screenshots are referenced
- [ ] Step order is logical and sequential
- [ ] Every figure has a caption
- [ ] Labels are unique per figure
- [ ] Menu/button names are bolded
- [ ] \par at the beginning of every paragraph

---

## Secondary Agent: Reviewer

### Role
Review generated LaTeX for consistency and completeness.

### Checklist
- LaTeX format follows standard
- No screenshots missed
- Flow makes sense from user perspective
- Captions are informative
- No typos in menu/button names