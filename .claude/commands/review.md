# Review Command

Review generated LaTeX section for quality assurance.

## Usage
```
/review [module-name]
```

## Checklist

### Format
- [ ] Every paragraph starts with \par
- [ ] Figures use [H] placement
- [ ] Every figure has unique caption and label

### Image Types
- [ ] FIGURE images use PDF: `images/pdf/[module-name].pdf` with correct `page=X`
- [ ] INLINE-IMAGE uses PDF: `images/pdf/his-v3-baru-2025.pdf` with correct `page=X`
- [ ] Page number matches image filename (e.g., `005.png` → `page=5`)
- [ ] Image type matches the marking in source screenshot

### Content
- [ ] All screenshots are covered
- [ ] Step order is sequential and logical
- [ ] Menu/button names are bolded
- [ ] No ambiguous steps

### Language
- [ ] All content is written in BAHASA INDONESIA
- [ ] Captions and descriptions use Indonesian language

### Output
Report to console + suggested fixes if any