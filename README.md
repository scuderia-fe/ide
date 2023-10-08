# Scuderia FE - IDE

IDE is a project made for learning

## Commands

| Name  | Command       | Equivalent      |
| ----- | ------------- | --------------- |
| dev   | bun run dev   | turbo run dev   |
| build | bun run build | turbo run build |
| start | bun run start | turbo run start |

## What's inside

### Root

- Deps and package manager [Bun](https://bun.sh)
- Monorepo and tools [Turborepo](https://turbo.build)
- Ensuring conventional changelog with [Commitlint](https://commitlint.js.org)

### Docs

- Made with [Starlight](https://starlight.astro.build/it/)

### Ide

- Made with [Tauri](https://tauri.app)
- Frontend with [sveltekit](https://kit.svelte.dev/)

### Troubleshooting

Adding a shared package into the `packages` folder after the first run of a `bun install` **_could_** cause troubles while installing the dependencies again.

An error similar to the following could appear: `workspace dependency "{package name}" not found`

When this appears, make sure you have correctly referenced the package name in every `apps/**/package.json` that needs it.

If that's the case, then the only workaround to that is to remove `bun.lockb` file, remove the global cache and then install dependencies again.

Remove Bun lockfile:

```zsh
rm -f bun.lockb
```

Clear Bun's global cache:

```zsh
bun pm cache rm
```

Install dependencies again:

```zsh
bun install
```

Contact one of the maintainers in case the issue persists.
