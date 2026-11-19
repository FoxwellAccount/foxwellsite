# Team Commit Convention (TCC)

Foxwell Collective Interactive (Foxwell Games)

This document defines how commits are written and how source files are structured in this repository. Every contributor must follow it before pushing code.

## Official Repository Timestamp

The repository was officially created on November 17, 2026.

## 1. Commit Messages

Commit messages are written in English, in plain text, and follow the Conventional Commits 1.0.0 specification.

```
type(scope): subject

body

footer
```

### Header

* type: required. One of the approved types in section 2.
* scope: optional. The file, page, or system affected, in lowercase (for example: lightbox, contact-form, window).
* subject: required. Imperative mood, lowercase, no trailing period. File names, identifiers, acronyms, and proper nouns keep their original case (for example: TCC.md, CC-BY, November).
* The header must not exceed 72 characters.
* A "!" before the colon marks a breaking change: a change that removes or renames something that visitors or other files depend on (for example: feat(workspace)!: replace accordions with windows).

### Body

Optional. Separated from the header by a blank line. Explains what changed and why, not how. Lines wrap at 72 characters.

### Footer

Optional. Separated from the body by a blank line. Used for issue references and breaking changes:

```
Refs: #12
BREAKING CHANGE: description of what breaks and how to migrate
```

## 2. Commit Types

| Type | Use for |
| --- | --- |
| feat | A new feature or system |
| fix | A bug fix |
| docs | Documentation files only, such as this document |
| content | Text, dates, legal terms, credits, or image files shown on the site. No code change |
| style | Formatting and visual styling: whitespace, CSS, layout, animations. No logic change |
| refactor | A code change that neither fixes a bug nor adds a feature |
| perf | A change that improves performance |
| test | Adding or correcting tests |
| build | Build system, dependencies, or package manager changes |
| ci | Continuous integration and deployment configuration |
| chore | Maintenance that does not touch source code or tests |
| revert | Reverts a previous commit |

When a change fits more than one type, choose the one that describes its main effect on the visitor: a new capability is feat, a visual-only change is style, and an internal restructure with no visible effect is refactor.

## 3. Commit Rules

* Write the subject in the imperative present tense: "add", not "added" or "adds".
* One logical change per commit.
* Plain text only: no Markdown, no emojis, no HTML.
* A revert commit uses the revert type, repeats the subject of the reverted commit, and lists the reverted hash in the body.

## 4. Examples

```
feat(contact-form): add subject routing and message encoding

fix(lightbox): close viewer when the escape key is pressed

style(window): add glow effect to expanded panels

feat(workspace)!: replace accordions with draggable windows

content(terms): set effective date to November 18, 2026

docs(tcc): rewrite convention to match industry standard
```

## 5. Source File Rules

These rules apply to every source code file (HTML, CSS, JS), including inline style and script blocks. Files in other formats, such as Markdown, JSON, plain text, and images, are exempt from rules 2 and 3. These rules are permanent and cannot be removed or relaxed.

1. All code is written in English: file names, identifiers, and text.
2. Code contains no comments. The mandatory header and footer are the only comment blocks allowed.
3. Every file starts with the header and ends with the footer, exactly as written below. Only the File Name and Purpose values change from file to file.

### Mandatory Header

Placed at the absolute top of the file as a comment block. The header has exactly these four lines and no other fields:

```
File Name: [filename]
Purpose: [brief description]
Owner: Foxwell Collective Interactive (Foxwell Games)
Copyright: All rights reserved. Codes, IPs, contents, and studio materials are strictly protected under international copyright and intellectual property laws.
```

### Mandatory Footer

Placed at the absolute bottom of the file as a comment block:

```
Terms of Use: The codes provided herein may be modified strictly for personal use. They cannot be shared, distributed, or presented illegally as if they were the property of someone else, in accordance with the accepted terms of Foxwell Collective Interactive.
```

Comment syntax: HTML uses `<!-- -->`, CSS and JS use `/* */`. In HTML, the header goes before the doctype and the footer after the closing html tag.
