# Release 0.2.2-rc.3

Adaptation for DeepSeek Harness desktop **0.2.2-rc.3**.

- Align the plugin manifest, DSH host peers, UI-primitives development package, runtime checks and bundle metadata with rc.3.
- No provider, settings or transport code change was needed: the rc.1 surfaces this plugin uses (`web` service, `configForms`, credentials, official client slots) remain compatible in rc.3.
- Revalidated registration, volatile settings, compatibility admission, settings form saves and Responses transport against the rc.3 packages. **43 automated tests pass**.
- `engines.dsh` intentionally admits only `0.2.2-rc.3`; earlier releases stay on their own plugin builds.

# Release 0.2.2-rc.1

Adaptation for DeepSeek Harness desktop **0.2.2-rc.1**.

- Rename the package from `dsh-web-search-codex-020` to `dsh-web-search-codex`. The npm package of that name (0.1.2) belongs to the upstream project; this plugin is distributed through GitHub Releases, not npm.
- Align the plugin manifest, DSH host peers, UI-primitives development package, runtime checks and bundle metadata with rc.1: Cordis 4.1.0, Schemastery 3.19.0, cordis-plugin-loader 1.1.0.
- Keep the `web-search-codex` configuration namespace, `codex-local` provider ID and `CODEX_SEARCH_API_KEY` default credential reference unchanged.
- Revalidate provider registration, dynamic settings, compatibility admission, settings form saves and Responses transport against the rc.1 packages. **43 automated tests pass**.

# Release 0.2.1-rc.5

Adaptation for DeepSeek Harness desktop **0.2.1-rc.5**.

- Align the plugin manifest, DSH host peers, UI-primitives development package, runtime checks and bundle metadata with rc.5.
- Revalidate provider registration, dynamic settings, compatibility admission, settings form saves and Responses transport against the rc.5 packages.
- Preserve the existing configuration namespace, provider ID and credential reference for in-place upgrades.

# Release 0.2.1-rc.3

Adaptation for DeepSeek Harness desktop **0.2.1-rc.3**.

- Declare the tested runtime in `engines.dsh` and align DSH host peer dependencies, passing the new compatibility gate without an exemption.
- Keep the existing package name, `web-search-codex` configuration namespace, `codex-local` provider and credential reference so existing settings can be reused.
- Follow the rc.3 browser shell contract: develop against UI primitives at rc.3 while using the shell's provided runtime instance, without installing primitives as a host peer.
- Normalize Windows CRLF source before building the classic client; add an LF/CRLF build regression.
- Validate the generated client with the actual rc.3 SettingsFormModel implementation: typed saves, revision conflicts, simultaneous reference/key changes, rejected writes, retries and blank secrets.
- Update Loader/WebRuntime integration coverage for rc.3, including source limits, caller cancellation and volatile provider selection.
- Refresh transport user-agent, documentation and validation evidence. The automated suite now contains **43 passing tests**.

See VALIDATION.md for scope and limits. Installation assets are distributed through GitHub Releases.

# Release 0.2.0-rc.2

Initial independent adaptation for DeepSeek Harness desktop 0.2.0-rc.2.

- Pin DSH peer packages to the tested 0.2.0-rc.2 runtime.
- Use volatile Config fields and per-operation DSH credential resolution.
- Add an installable DSH bundle selecting `codex-local`.
- Add a Chinese desktop settings card with staged configuration and credential-only API Key storage.
- Build the client into the classic ModuleLoader format required by this DSH version.
- Send the gateway-tested Responses request form: array input, forced native search, complete source inclusion, no storage, and SSE by default.
- Merge native search sources and answer URL citations.
- Reject incomplete streams, ordinary answers without native search, and failed responses.
- Add timeouts and cancellation; stop after response.completed without waiting for the upstream connection to close.
- Include 33 passing automated tests and a successful real Responses gateway search.

See VALIDATION.md for evidence and limits. No npm registry publication is implied by this GitHub release.
