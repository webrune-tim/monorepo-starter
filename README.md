# Simple Monorepo Starter

This is a simple monorepo starter for a project that has multiple packages. It uses [PnPm](https://pnpm.io/) for efficiency and speed

The code came mainly from Scott Tolinski's [Monorepos with Pnpm](https://leveluptutorials.com/tutorials/monorepos-with-pnpm) tutorial.

---

## How to use

1) Click the green "Use this template" button above to create a new repo from this template
2) Name your new monorepo
3) Enjoy!

The `packages` folder is where you'll put your packages, duh. A package can be anything from a frontend framework to a backend framework to a library to a CLI tool. It's up to you!

### Scripts

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

### How to add new dependencies

```bash
  # Add a new package
  pnpm -F @project-name/second add just-snake-case@3.0.0

  # Add a new dependency to the main package (the root package) - rarely needed
  pnpm add -w just-kebab-case
```

### How to add a new package

Simply create a new folder in the `packages` folder and add run `pnpm init` in that folder.

1) Create a new folder in the `packages` folder
2) Run `pnpm init` in that folder
3) Optionally, duplicate `start:second` in the root `package.json` and change the name to the new package
