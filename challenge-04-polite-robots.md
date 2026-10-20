# Challenge 04 — Polite Robots

**Category:** Web Reconnaissance

## Objective
Use a website's `robots.txt` crawler directives as clues during an authorized CTF investigation.

## Observed Content
The challenge's `robots.txt` displayed:

```text
User-agent: *
Disallow: /s3cr3t-vault-7f3a/
Disallow: /mini-ctf/s3cr3t-vault-7f3a/
Disallow: ./s3cr3t-vault-7f3a/
```

## Investigation
1. Read the `robots.txt` file.
2. Note the unusual path: `s3cr3t-vault-7f3a`.
3. Within the authorized CTF site, inspect the path that matches the site's URL structure, including the listed `/mini-ctf/` path if applicable.
4. Record the response and inspect any accessible page or resource for additional clues.
5. Confirm the flag from the actual challenge response before documenting it.

## Result / Flag
**Pending verification.** The path in `robots.txt` is a clue, not itself a confirmed flag. Add the resource found and the exact flag after verifying the challenge.

## What I Learned
- `robots.txt` gives crawler instructions; it is not an access-control mechanism.
- A `Disallow` entry does not guarantee a path is private or accessible.
- Reconnaissance clues need to be verified through observed responses.

## Security Note
Sensitive resources must use proper authentication and authorization, not rely on `robots.txt` to hide them.
