# Validation record - 0.2.2-rc.1

## Runtime under test

- Installed DeepSeek Harness desktop package manifest: **0.2.2-rc.1**.
- Host OS: Windows.
- Node.js used for this run: **24.21.0**.
- @deepseek-ai/cordis: 4.1.0; @deepseek-ai/schemastery: 3.19.0; cordis-plugin-loader: 1.1.0.
- @deepseek-ai/dsh-web, dsh-app-boot, dsh-client-ui-primitives, dsh-credentials, dsh-launch-environment and dsh-llm: **0.2.2-rc.1**.

## Completed checks

- `npm run build` and `npm run check` passed.
- Automated suite: **43 passed, 0 failed, 0 skipped**.
- The runtime suite loads actual rc.1 Cordis, Loader, Schema, WebRuntime and AppBoot packages with fixture credentials and HTTP. It covers compatibility admission, provider registration/disposal, volatile updates, bundle composition, source limits and caller cancellation.
- The generated-client suite executes the published rc.1 SettingsFormModel implementation with React. It covers typed batched saves, revision conflicts, credential-reference changes, rejected writes, retry behavior and blank-secret preservation. In Node, the browser package root cannot load because it imports CSS; tests execute its published settings regions verbatim and do not claim DOM or slot-rendering coverage.
- `npm pack` produced `dsh-web-search-codex-0.2.2-rc.1.tgz` (14 files). The tarball was unpacked and installed into the local DSH desktop profile through `dsh plugin add`; the host entry imported, the classic client factory and bundle metadata loaded, and the resolved packages were rc.1. This is not a full Electron UI click-through.

## Limits and notes

- Tests use fixture credentials and intercepted HTTP; no real API key, paid upstream search request or manual Electron UI acceptance was used.
- `npm install` reported dependency advisories. `npm audit` could not provide details because this project does not maintain a lockfile (`ENOLOCK`); the advisories were not independently attributed or changed in this plugin update.
- GitHub Actions results are not implied by local checks and should be confirmed after the push.
- Only DSH **0.2.2-rc.1** is declared supported. The package `engines.dsh` intentionally admits only that runtime.
- The npm name `dsh-web-search-codex` is already used by the upstream 0.1.2 package, so this plugin is distributed as a GitHub Release tarball rather than an npm package.
