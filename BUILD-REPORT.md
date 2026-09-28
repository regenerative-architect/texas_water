# Build report — Texas Water Sovereignty OS v2.0.0

Build date: 2026-09-28

## Performed successfully
- Node syntax check: original inline application script.
- Node syntax check: upgrade.js, multiplayer.mjs, webllm.mjs, webllm-worker.mjs, sw.js.
- JSON parse/validation: manifest.webmanifest and current-context.json.
- Local-reference check: every `./` src/href referenced by index.html exists in the bundle.
- Local HTTP smoke check: index, manifest, service worker, offline page, scripts, current-context data and icon returned HTTP 200.
- ZIP CRC/integrity check: no corrupt member.

## Environment limitation
A Chromium headless DOM smoke test was attempted, but this container's Chromium GPU/display initialization did not complete cleanly and the test timed out. Therefore this build does NOT claim a completed interactive browser audit, two-peer WebRTC test, TURN test, or WebGPU/WebLLM model-inference test.

## Runtime-dependent tests to perform after HTTPS deployment
1. Open two browsers/devices and join the same Nostr room.
2. Verify peer join/leave, project broadcast, task/comment/decision sync and snapshot recovery.
3. Repeat in same-device BroadcastChannel mode with two tabs.
4. If restrictive networks fail, configure private TURN credentials and confirm relay behavior.
5. On a WebGPU-capable browser, enable Local AI, download a model, generate and cancel a draft, then test cached reuse.
6. Install the PWA, go offline, and verify calculators, local projects, guides and same-device collaboration.
