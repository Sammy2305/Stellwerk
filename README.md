# Stellwerk

Stellwerk is an early-stage railway signalling simulation. The goal is to model interlockings, block logic, and timetable execution while providing a separate, modern UI for dispatchers to experiment with scenarios and training exercises.

## Vision and scope
- **Simulation-first:** focus on accurate interlocking behaviour, train movements, route reservation, and occupancy tracking.
- **Configurable scenarios:** load different track layouts, schedules, and signal rules to test operational strategies.
- **Safe experimentation:** sandboxed environment for training and validation without affecting real systems.

## Architecture
The project is planned with a clear separation between the core simulation engine and user-facing interfaces:
- **Simulation core:** pure domain logic that handles infrastructure topology, signalling rules, state transitions, and timetable execution. Designed to be headless and testable.
- **UI/clients:** web and/or desktop clients consuming the simulation via an API or messaging layer. The UI should not embed signalling rules; it only renders state and sends user actions.
- **Integration layer:** adapters or services that bridge the simulation to external data sources, persistence, or network protocols.

## Domain model highlights
While implementation is in progress, the core concepts include:
- **Infrastructure:** tracks, switches/points, signals, platforms, and block sections.
- **Operations:** trains, consists, timetables, and planned routes.
- **Interlocking:** route setting, locking/unlocking logic, flank protection, occupancy detection, and conflict resolution.
- **Control & monitoring:** dispatcher commands, indications, and event logs.

## Development setup
1. Ensure you have a recent **Node.js** (or your chosen runtime once finalized) and **pnpm/npm** available.
2. Clone the repository and install dependencies when they are added:
   ```bash
   pnpm install   # or npm install
   ```
3. Run type-checks/tests as they become available:
   ```bash
   pnpm test      # or npm test
   pnpm lint
   ```
4. Launch the app (once a UI exists):
   ```bash
   pnpm dev       # start development server
   pnpm build     # produce production assets
   ```

## Future documentation
- Architecture and protocol details will live under [`docs/`](docs/) as they are authored.
- API usage, data formats, and contribution guidelines will be added alongside initial code drops.

If you are exploring or contributing early, please open issues to propose requirements or share domain expertise.
