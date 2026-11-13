# Validation record - 0.2.2-rc.3

## Runtime under test

- Installed DeepSeek Harness desktop package manifest: **0.2.2-rc.3**.
- Host OS: Windows.
- Node.js used for this run: **24.22.2**.
- @deepseek-ai/cordis: 4.1.0; @deepseek-ai/schemastery: 3.19.0; cordis-plugin-loader: 1.1.0.
- @deepseek-ai/dsh-web, dsh-app-boot, dsh-client-ui-primitives, dsh-credentials, dsh-launch-environment and dsh-llm: **0.2.2-rc.3**.

## Completed checks

- `npm install` resolved every DSH package to 0.2.2-rc.3.
- `npm run build` and `npm run check` passed.
- Automated suite: **43 passed, 0 failed, 0 skipped**.
- The runtime suite loads actual rc.3 Cordis, Loader, Schema, WebRuntime and AppBoot packages with fixture credentials and HTTP. It covers compatibility admission, provider registration/disposal, volatile updates, bundle composition, source limits and caller cancellation.
- The generated-client suite executes the published rc.3 SettingsFormModel implementation with React. It covers typed batched saves, revision conflicts, credential-reference changes, rejected writes, retry behavior and blank-secret preservation. In Node, the browser package root cannot load because it imports CSS; tests execute its published settings regions verbatim and do not claim DOM or slot-rendering coverage.
- No provider, settings or transport source change was required between rc.1 and rc.3; the plugin only needed manifest, check-target and documentation alignment.
- `npm pack` produced `dsh-web-search-codex-0.2.2-rc.3.tgz` (14 files). The archive contents were listed and its embedded manifest re-read: name, version, `engines.dsh` and all DSH peer/dev ranges are 0.2.2-rc.3.

## Limits and notes

- Tests use fixture credentials and intercepted HTTP; no real API key, paid upstream search request or manual Electron UI acceptance was used.
- The packaged tarball was **not** installed into the live desktop profile during this run, so no `dsh plugin add` activation result is claimed here. Install it and reload to confirm activation in the desktop UI.
- This project does not maintain a lockfile, so `npm audit` still cannot attribute advisories (`ENOLOCK`).
- GitHub Actions results are not implied by local checks and should be confirmed after the push.
- Only DSH **0.2.2-rc.3** is declared supported. The package `engines.dsh` intentionally admits only that runtime.
- The npm name `dsh-web-search-codex` is already used by the upstream 0.1.2 package, so this plugin is distributed as a GitHub Release tarball rather than an npm package.
