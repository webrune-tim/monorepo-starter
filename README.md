# Simple Monorepo Starter

---

#### This is a simple monorepo starter for a project that has multiple packages. It uses [PnPm](https://pnpm.io/) for efficiency and speed

#### The code came mainly from Scott Tolinski's [Monorepos with Pnpm Course](https://leveluptutorials.com/tutorials/monorepos-with-pnpm) on monorepos

---

## How to use

```bash
  # Clone the repo

  gh repo clone timscodebase/monorepo-starter your-project-name
  cd your-project-name
  pnpm install
```

## Scripts

```json
  "scripts": {
    "start:main": "pnpm -F @project-name/main start",
    "start:second": "pnpm -F @project-name/second start",
    "start": "pnpm -r start",
    "update:all": "pnpm -r update -i -L",
    "clean": "find ./ -name node_modules -type d -exec rm -rf {} +"
  },
```

- `start:main` - starts the main package
- `start:second` - starts the second package
- `start` - starts both/all packages
- `update:all` - recursively updates all dependencies for all packages
- `clean` - removes all `node_modules` folders

## How to add a new package

```bash
  # Add a new package
  pnpm -F @timsmith/second add just-snake-case@3.0.0

  # Add a new dependency to the main package (the root package) - rarely needed
  pnpm add -w just-kebab-case
```
