# Prototype Instructions

Run the local server yourself and open the preview in the browser available to this environment. Do not give the user server-start instructions when you can run it.

Before making substantial visual changes, use the Product Design plugin's `get-context` skill when the visual source is unclear or no longer matches the current goal. When the user gives durable prototype-specific design feedback, preferences, or decisions, record them in `AGENTS.md`.

When implementing from a selected generated mock, treat that image as the source of truth for layout, component anatomy, density, spacing, color, typography, visible content, and hierarchy.

Build app UI in `src/`. Keep `.openai/hosting.json`, `worker/index.js`, `scripts/prepare-sites-build.mjs`, and `tests/sites-worker.test.mjs` intact so the same local prototype can be handed to Sites. Before a Sites handoff, run `npm run build` and `npm run test:sites`; the build must leave `dist/client/index.html`, `dist/server/index.js`, and `dist/.openai/hosting.json`.

## Product Decisions

- Currency display uses a space between the Ghana cedi mark and the amount; the GH₵ mark is rendered 3px smaller than its numeric value across quotation and history views.

- XLSX calculations are formula-driven: editable quantity and unit-price cells feed each line amount; subtotal, percentage-formatted discount and tax inputs, and total recalculate automatically on open.

- Service-item selection is a true toggle across web and APK: tapping plus adds one quantity and changes the control to a checkmark; tapping the checkmark removes that item and its amount, returning the control to plus. Quantity changes remain in quotation detail controls.
