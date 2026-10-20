# Challenge 01 — Nothing to See Here

**Category:** Web Source Basics

## Objective
Inspect a webpage's source code to find a flag that is not visible in the rendered page.

## Investigation
1. Open the challenge webpage.
2. Press `Ctrl + U` in the browser to view its HTML source.
3. Search the source for `COEP{` or inspect HTML comments.
4. The source contains this comment:

```html
<!--
SECRET FLAG CONCEALED BELOW:
Good job checking the raw HTML source code!
COEP{view_source_is_your_friend}
-->
```

## Flag
`COEP{view_source_is_your_friend}`

## What I Learned
- The visible page and its HTML source are not the same thing.
- HTML comments are not displayed as ordinary page content, but remain readable in the source.
- Never store passwords, private API keys, or other secrets in frontend HTML or JavaScript.

## Tools
- Web browser
- View Source (`Ctrl + U`)
- Optional: Developer Tools
