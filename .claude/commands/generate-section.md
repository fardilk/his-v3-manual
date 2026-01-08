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
   - Identify UI state and action in each image
   - Map to flow defined in context

3. **Generate LaTeX**
   - Follow standard format in CLAUDE.md
   - **Write ALL content in BAHASA INDONESIA**
   - Output to `sections/[module-name].md` (LaTeX code in markdown file)

4. **Update Todo**
   - Mark as generated in `sections/todos.md`

## Output
File: `sections/[module-name].md` (contains LaTeX code ready for copy-paste)