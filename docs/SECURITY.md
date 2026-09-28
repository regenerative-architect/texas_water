# Security notes

- No embedded secrets.
- Peer IDs / self-declared roles are unverified.
- Use room passwords as shared secrets, not identity proof.
- Incoming shared records are treated as data, not executable HTML.
- Institutional deployments needing authorization should add authenticated identity and persistence.
- TURN may be required for restrictive networks; credentials must be configured privately.
