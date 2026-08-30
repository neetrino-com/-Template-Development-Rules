# Vercel Git deployments — only `main`

Optional. Use when the project should auto-deploy from `main` only.

Copy [`vercel.json.example`](./vercel.json.example) to the project root as `vercel.json`. Merge with an existing `vercel.json` if the project already has one.

```json
{
  "$schema": "https://openapi.vercel.sh/vercel.json",
  "git": {
    "deploymentEnabled": {
      "*": false,
      "main": true
    }
  }
}
```

`*` disables Git deployments for every branch. `main: true` keeps production deploys. Unspecified branches would default to enabled; here they are covered by `*`.

This turns off Vercel preview URLs for pull requests. The default quality checklist still expects PR previews unless the TECH_CARD opts out.

Official docs: [Git configuration](https://vercel.com/docs/project-configuration/git-configuration).
