## How to Add New Module

1. Create folder `screenshots/[module-name]/`
2. Upload screenshots sequentially: 1.jpg, 2.jpg, etc
3. Create file `module/[module-name].md` with format above
4. Update the table above
5. Run `/generate-section [module-name]`
```

---

## Updated Directory Structure
```
HISv3/
├── AGENTS.md
├── CLAUDE.md
├── .claude/
│   └── commands/
│       ├── generate-section.md    # renamed from generate-page.md
│       ├── review.md
│       └── module/
│           └── list.md
├── exports/                        # Final compiled exports if needed
├── module/
│   └── README.md
├── screenshots/
│   └── [module-name]/             # 1.jpg, 2.jpg, etc
└── sections/
    ├── todos.md
    └── [module-name].tex          # Generated output