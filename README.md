# nx-tsc

Nx executor to check types of project source files using `tsc --noEmit`

## Installation

```bash
npm install -D @obergodmar/nx-tsc
```

## Configuration

Add a `typecheck` target to each `project.json`:

```json
{
  "$schema": "../../node_modules/nx/schemas/project-schema.json",
  "sourceRoot": "libs/my-lib/src",
  "targets": {
    "typecheck": {
      "executor": "@obergodmar/nx-tsc:typecheck",
      "options": {
        "tsConfig": ["tsconfig.json"]
      }
    }
  }
}
```

## Run typecheck

This enables the `tsc` target in the Nx workspace:

```bash
nx typecheck my-lib
```

## Run typecheck for every single app/lib

Add a `typecheck` script to global `package.json`:

```json
{
  "scripts": {
    "typecheck": "nx run-many -t=typecheck --verbose"
  }
}
```

```bash
npm run typecheck
```
