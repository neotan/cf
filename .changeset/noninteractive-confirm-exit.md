---
"cf": minor
---

Exit with an error when a destructive command is refused without `--force`

Destructive commands such as `cf workflows delete` still refuse to run
without `--force` in non-interactive contexts, but now exit with status 1
instead of 0. Scripts and CI jobs can therefore tell a refused operation from a
successful one. This also applies to `cf registrar registrations create`,
which uses the same confirmation, and generated commands no longer print
`Aborted.` when they refuse to run. Scripts that relied on the previous exit
status must pass `--force` to perform the operation. Declining the prompt in
an interactive terminal still exits successfully.
