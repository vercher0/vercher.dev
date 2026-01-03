

# vercher.dev

This repository contains the public source for **vercher.dev**, my personal website.

The site serves as a single, coherent presence for:
- Civic and public service work
- Consulting and systems-focused professional work
- Personal writing and projects

It is intentionally simple, static, and system-oriented.

---

## Purpose

This project is designed to:
- Clearly separate civic, consulting, and personal contexts
- Encode design and branding decisions explicitly
- Favor clarity, structure, and long-term maintainability over polish

The site is built using plain HTML and CSS to keep the focus on content,
structure, and intent rather than frameworks or tooling.

---

## Structure Overview

The site is organized by context:

- `/`  
  Personal-first gateway that introduces who I am and routes visitors to
  the appropriate section.

- `/civic/`  
  Civic and public service work, written with an emphasis on trust,
  transparency, and accountability.

- `/consulting/`  
  Professional consulting and systems work, focused on healthcare, data,
  and operations.

- `/personal/`  
  Personal writing, experiments, and projects.

Shared assets, styles, and documentation live outside these sections to
enforce consistency and reduce drift.

---

## Design & Brand System

The site uses a small, explicit brand system based on **page-level mode
locking**:

- Each page declares a single brand mode (`civic`, `consulting`, or `personal`)
- Brand colors and behavior are enforced via CSS tokens
- Favicons are selected per mode to reinforce context
- SVGs and components remain mode-agnostic

Brand rules and usage guidelines are documented in:

```
/brand/BRAND.md
```

---

## Local Development

This site is intended to be served locally using a simple static server.

Recommended workflow:
- Open the project root in VS Code
- Use the **Live Server** extension
- Visit paths like `/`, `/consulting/`, and `/civic/`

Absolute paths (e.g. `/css/base.css`) are used intentionally and assume a
server context rather than `file://` URLs.

---

## Repository Visibility

This repository is intentionally **public**.

It does not contain secrets, credentials, client data, or private
configuration. If sensitive material is ever required in the future, it
should live in a separate, private repository.

---

## Status

This project is a living system and will evolve over time.
The current focus is on:
- Structure
- Governance
- Clarity of intent

Visual polish and deeper content will be added incrementally.