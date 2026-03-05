<h1 align="center">Almena ID</h1>

<p align="center">
  <strong>Decentralized identity. Owned by you. Trusted by everyone.</strong>
</p>

<p align="center">
  <a href="https://almena.id">Website</a> &middot;
  <a href="https://docs.almena.id">Documentation</a>
</p>

---

## What is Almena ID?

Almena ID is a decentralized identity platform built on W3C standards (DIDs, Verifiable Credentials). It enables people and organizations to create, issue, and verify digital identities without intermediaries or centralized databases.

The main repository is a monorepo orchestrated via Taskfile. It comprises several subprojects:

---

## Subprojects

| Subproject | Description |
|------------|-------------|
| **daemon** | gRPC server (Rust). Source of truth for the proto definitions. Receives requests from desktop and CLI. Exposes health checks, version, system info, and geolocation. Uses libp2p for P2P networking. |
| **desktop** | Tauri + React desktop application for **Issuers** and **Requesters**. Enables issuing Verifiable Credentials, requesting presentations, and managing trust frameworks. Connects to the daemon via gRPC. |
| **wallet** | Mobile-first identity wallet for **Holders**. Manages DIDs, Verifiable Credentials, and key storage. Touch-friendly UI (390×844 px). Keys stored in the system keychain. |
| **cli** | Terminal UI (TUI) client built with Ratatui. Connects to the daemon via gRPC for operators who prefer the command line. |
| **docs** | Docusaurus documentation site. User guides, integrator guides, and API reference. English and Spanish. |

---

- **Desktop** and **CLI** connect to the daemon as gRPC clients.
- **Wallet** is a standalone app for holders; it does not depend on the daemon.
- **Docs** is a static site (Docusaurus).

---

## Quick Links

- [Main repository](https://github.com/almena-id/almena-id) (monorepo)
- [Website](https://almena.id)
- [Documentation](https://docs.almena.id)