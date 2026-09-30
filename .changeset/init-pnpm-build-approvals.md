---
"cf": patch
---

Approve workerd build scripts in new pnpm projects

`cf init` no longer fails with `ERR_PNPM_IGNORED_BUILDS` when you choose pnpm.
pnpm 11 and later refuse to run dependency build scripts that a project has not
approved, and the new Worker depends on workerd, which needs its script. New
pnpm projects now include a `pnpm-workspace.yaml` that approves workerd and
esbuild. Projects created with npm, yarn, or bun are unchanged.
