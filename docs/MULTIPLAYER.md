# Multiplayer

Transport abstraction: collaboration protocol → merge/sync layer → Trystero/WebRTC or BroadcastChannel.

Remote mode uses Trystero 0.25.3 modern action objects. Nostr is default; MQTT, BitTorrent and IPFS are selectable. A room password is a shared secret for stronger SDP encryption during discovery, not identity verification.

Snapshot join flow: peer detected → presence exchange → snapshot request → existing peer sends projects/tasks/decisions/comments → receiver validates/merges/persists.

Direct WebRTC cannot traverse every network. Configure TURN through Trystero `turnConfig` in a private deployment when required. Do not publish reusable TURN credentials in this static bundle.
