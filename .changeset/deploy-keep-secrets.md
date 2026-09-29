---
"cf": patch
---

Keep existing Worker secrets on `cf deploy`

`cf deploy` no longer removes secrets that are set on a deployed Worker but
not declared in its configuration. Deploys now always ask the API to inherit
existing secrets, matching `cf workers versions create`. Use
`cf workers secrets delete` to remove a secret.
