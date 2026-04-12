<h1 align="center">Almena Network</h1>

<p align="center">
  <strong>Decentralized identity. Owned by you. Trusted by everyone.</strong>
</p>

<p align="center">
  <a href="https://almena.network">Website</a> &middot;
  <a href="https://docs.almena.network">Documentation</a>
</p>

---

## What is Almena Network?

Almena Network is a decentralized identity platform built on W3C standards (DIDs, Verifiable Credentials). It enables people and organizations to create, issue, and verify digital identities without intermediaries or centralized databases.

The platform also grows toward decentralized applications, persistence, messaging, coordination, and ordering over time.

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
| **web** | Public site built with Astro. Marketing and web presence aligned with [almena.network](https://almena.network). |
| **homebrew-almena** | Homebrew tap for installing the **Almena CLI** (`almena`) on macOS Apple Silicon from GitHub Releases. |

---

- **Desktop** and **CLI** connect to the daemon as gRPC clients.
- **Wallet** is a standalone app for holders; it does not depend on the daemon.
- **Docs** is a static site (Docusaurus). **Web** is a static Astro site.
- **Homebrew-almena** packages the CLI for macOS; it does not ship the daemon or desktop app.

---

## Quick Links

- [Main repository](https://github.com/almena-network/almena-network) (monorepo)
- [Website](https://almena.network)
- [Documentation](https://docs.almena.network)
