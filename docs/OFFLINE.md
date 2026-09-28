# Offline behavior

Core app shell, bundled guides, calculators and local records are designed to remain usable after service-worker installation. BroadcastChannel same-device rooms need no network. Remote WebRTC peer discovery, new model downloads and current external datasets require connectivity. Service workers do not run under `file://`.
