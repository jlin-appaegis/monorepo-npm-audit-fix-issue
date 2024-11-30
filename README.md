## Steps to Reproduce

1. Install dependencies using `npm ci`.
2. Run `npm audit fix --force` to address all vulnerabilities.

## Current Behavior

The package `@swc/cli` is added as a dependency to the workspace `package-a`, even though it is not listed as a dependency of `package-a` in the `package.json`.

## Expected Behavior

`npm audit fix --force` should only upgrade existing vulnerable dependencies. It should NOT add new dependencies to workspaces unless explicitly defined in the `package.json`.
