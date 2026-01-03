# Repository Visibility

This repository is intentionally **public**.

It contains the public source for vercher.dev and is designed to be openly viewable.
The structure, documentation, and code reflect how the site is built and how decisions
are made, and are not intended to contain secrets, credentials, or private data.

If sensitive material is ever introduced in the future, it should live in a separate,
private repository.

vercher.dev/
├── index.html                # (later) root landing / redirect
│
├── civic/
│   └── index.html            # (later) civic landing
│
├── consulting/
│   └── index.html            # (later) consulting landing
│
├── personal/
│   └── index.html            # (later) personal landing
│
├── css/
│   ├── brand.css             # brand tokens & mode locking
│   └── base.css              # structural defaults (already created)
│
├── assets/
│   ├── icons/
│   │   ├── vercher-v.svg
│   │   ├── vercher-lockup.svg
│   │   └── favicon/
│   │       ├── favicon-civic.ico
│   │       ├── favicon-consulting.ico
│   │       └── favicon-personal.ico
│   │
│   └── images/               # future photos, diagrams, etc.
│
├── templates/
│   └── comment-block.html    # use in every html page
│
├── brand/
│   └── BRAND.md              # brand usage guide
│
└── README.md                 # repo-level notes (optional)