---
"cf": patch
---

Run Node dev-server delegates through Node on Windows

`cf dev`, `cf build`, and the build step of `cf deploy` no longer fail with
`spawn EFTYPE` on Windows when a project uses Wrangler or the Vite plugin.
Windows cannot start a Node script from its shebang line, so cf now runs these
delegates with its own Node executable. macOS and Linux are unchanged.
