# Texas Water Sovereignty OS v2.0.0

A local-first Texas water planning and cross-domain collaboration suite.

## Deploy
1. Extract the ZIP.
2. Upload the whole folder to an HTTPS static host (GitHub Pages, Cloudflare Pages, Netlify, conventional HTTPS hosting, etc.).
3. Open `index.html`.
4. The service worker registers automatically on HTTPS or localhost. It deliberately does not register under `file://`.

## Multiplayer
The collaboration workspace provides a same-device BroadcastChannel mode that works without a network, plus optional Trystero 0.25.3 remote rooms. Nostr is the default discovery strategy; MQTT, BitTorrent and IPFS adapters are selectable. Remote Trystero modules are loaded from pinned jsDelivr URLs when a network room is explicitly joined. After discovery, room data uses WebRTC data channels. Some NAT/firewall combinations require TURN; no TURN credentials are bundled.

Peer identifiers and self-declared organizations/roles are NOT verified identities. Do not use an open peer room for confidential institutional data without appropriate controls.

## WebLLM
Local AI is optional. When enabled, the browser loads WebLLM and its current supported-model registry, then runs the selected model through a dedicated Web Worker using WebGPU. Model weights are not included in this ZIP and can be large. New model downloads require connectivity; the deterministic water tools never require WebLLM.

## Offline matrix
- Bundled content/calculators/projects/JSON tools: yes after install/cache
- Same-device BroadcastChannel rooms: yes
- Saved peer snapshots: yes
- Remote Trystero discovery: no
- Current live web data / uncached maps: no
- New WebLLM model download: no
- Previously browser-cached model: browser/WebLLM dependent

## Data sovereignty
Existing water projects remain in IndexedDB (`texasWaterOS`). Collaboration tasks, decisions, comments and snapshots use a separate IndexedDB database (`texasWaterOSCollab`) to avoid breaking the v1 core. JSON exports remain user-controlled. SHA-256 means integrity, not authorship.

## Current context
See `assets/data/current-context.json` and `docs/DATA-SOURCES.md`. Dated facts are snapshots, not permanent truth.

## Security
No secrets are embedded. Remote CDN loading is limited to explicit optional Trystero/WebLLM use; pinning is used for Trystero 0.25.3. Deployers needing strong institutional identity/authorization should add authenticated infrastructure rather than treating browser-side role labels as enforcement.
