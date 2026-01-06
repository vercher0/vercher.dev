# Repository Visibility

This repository is intentionally **public**.

It contains the public source for vercher.dev and is designed to be openly viewable.
The structure, documentation, and code reflect how the site is built and how decisions
are made, and are not intended to contain secrets, credentials, or private data.

If sensitive material is ever introduced in the future, it should live in a separate,
private repository.

vercher.dev/
├── index.html                # root landing / routing hub
│
├── about/
│   └── index.html            # about / orientation
│
├── civic/
│   └── index.html            # civic landing
│
├── consulting/
│   └── index.html            # consulting landing
│
├── writing/
│   ├── index.html            # writing landing
│   ├── _post-template.html   # writing post template
│   └── posts/
│       ├── machine-ethics-2011.html
│       └── why-i-care-about-systems-and-responsibility.html
│
├── cv/
│   └── index.html            # curriculum vitae
│
├── contact/
│   └── index.html            # contact page
│
├── css/
│   ├── brand.css             # brand tokens & mode locking
│   └── base.css              # structural defaults
│
├── assets/
│   ├── icons/
│   │   ├── vercher-v.svg
│   │   ├── vercher-lockup.svg
│   │   └── favicon/
│   │       ├── favicon-civic.svg
│   │       ├── favicon-consulting.svg
│   │       └── favicon-personal.svg
│   │
│   └── images/               # future photos, diagrams, etc.
│
├── templates/
│   └── comment-block.html    # use in every html page
│
├── brand/
│   └── BRAND.md              # brand usage guide
│
├── sitemap.xml               # search engine sitemap
│
└── README.md                 # repo-level notes