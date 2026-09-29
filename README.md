# Dynamic Bot List Manager

A small React and Bun application for managing a list of automation bots in the browser. The interface keeps bot state in React and provides controls to add, edit, filter, trigger, stop, and delete bots.

## Features

- View the number of bots currently marked as **Running**.
- Add new bots with a name, status, and task.
- Edit an existing bot from its row.
- Trigger a bot to simulate a five-second job, or stop it immediately.
- Filter the list by an exact status value.
- Run the UI and API routes from a single Bun server.

## Tech stack

- [Bun](https://bun.com/) for dependency management, development, bundling, and serving.
- [React](https://react.dev/) 19 with TypeScript.
- Tailwind CSS browser build for utility classes used by the UI.

## Getting started

### Prerequisites

Install [Bun](https://bun.com/docs/installation) (the project uses Bun's package manager and server runtime).

### Install

From the repository root:

```bash
bun install
```

### Run in development

```bash
bun dev
```

Open the URL printed by Bun, normally `http://localhost:3000`. Development mode enables hot module reloading.

### Run in production mode

```bash
bun start
```

To create an optimized browser bundle:

```bash
bun run build
```

The generated files are written to `dist/`.

## Using the app

1. Enter a bot name, status, and task in the form, then select **Add Bot**.
2. Use **Trigger** to mark a bot as running. After five seconds it is marked completed.
3. Use **Stop**, **Delete**, or **Edit** for the corresponding action.
4. Enter a status such as `Running`, `Completed`, or `Stopped` in the filter field to show matching bots.

The initial list contains:

| Bot | Status | Task |
| --- | --- | --- |
| Email Extractor | Running | Extracting emails |
| Notification Sender | Completed | Sending notifications |
| Data Analyser | Stopped | Analysing data |

## API routes

The Bun server also exposes a small example API:

```bash
curl http://localhost:3000/api/hello
curl http://localhost:3000/api/hello/Ada
curl -X PUT http://localhost:3000/api/hello
```

These routes return JSON responses and are defined in [`src/index.ts`](src/index.ts).

## Project structure

```text
src/
├── App.tsx            # Root React component
├── BotListManager.tsx # Bot state and management UI
├── frontend.tsx       # React DOM entry point
├── index.html         # HTML shell and browser entry point
├── index.ts           # Bun server and API routes
└── index.css          # Application styles
```

## Contributing

Contributions are welcome. To propose a change:

1. Create a focused branch from the default branch.
2. Make the smallest change that addresses the issue or feature.
3. Run `bun run build` and manually verify the affected UI or API route.
4. Open a pull request describing the behavior changed and how it was checked.

Please keep React components and Bun server behavior in their existing locations where possible, and avoid committing generated `dist/` files or local environment files.

## Support

For project-specific questions, open a GitHub issue with reproduction steps and the command you ran. For runtime and framework documentation, see the [Bun documentation](https://bun.com/docs) and [React documentation](https://react.dev/learn).

## Maintainers

This project is maintained by the repository owners and its contributors. Pull requests and focused bug reports are the preferred ways to improve it.

## License

No license file is currently included in this repository. Add or review a license before redistributing the project.
