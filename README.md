# nx-tsc

Nx executor to check types of project source files using `tsc --noEmit`

## Installation

```bash
npm install -D @obergodmar/nx-tsc
```

## Configuration

Add a `types-check` target to each `project.json`:

```json
{
  "$schema": "../../node_modules/nx/schemas/project-schema.json",
  "sourceRoot": "libs/my-lib/src",
  "targets": {
    "types-check": {
      "executor": "@obergodmar/nx-tsc:types-check",
      "options": {
        "tsConfig": ["tsconfig.json"]
      }
    }
  }
}
```

## Run types-check

This enables the `tsc` target in the Nx workspace:

```bash
nx types-check my-lib
```

## Run types-check for every single app/lib

Add a `types-check` script to global `package.json`:

```json
{
  "scripts": {
    "types-check": "nx run-many --target=types-check --all=true --verbose"
  }
}
```

```bash
npm run types-check
```
