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

Almena Network is a decentralized identity platform built on W3C standards (DIDs, Verifiable Credentials). People and organizations can create, issue, and verify digital identities without a single intermediary owning the directory.

The platform roadmap also includes decentralized applications, persistence, messaging, coordination, and ordering.

---

## How the work is organized

Day-to-day code and sites are split across **four projects**. Together they cover protocol and node software, product shells for issuers and holders, and public documentation and marketing.

| Project | Role | Stack (high level) |
|---------|------|---------------------|
| **[almena](https://github.com/almena-network/almena)** | Core platform: **daemon** (gRPC API and node logic), **Almena** desktop app (issuers and requesters), **CLI** (operator TUI), and **protobuf** definitions shared by clients. | Rust (tonic, daemon and tooling), Tauri v2 + React + Vite for the desktop shell |
| **[wallet](https://github.com/almena-network/wallet)** | **Holder** experience: DIDs, credentials, and keys on device; mobile-first UI. Integrates with the daemon over **HTTP REST** (`/api/v1/…`), not gRPC. | Tauri v2 + React + TypeScript |
| **docs** | Official documentation site: user guides, integrator-oriented material, and developer deep-dives. Bilingual **English** and **Spanish**. | Docusaurus, pnpm |
| **web** | Public marketing and landing experience aligned with [almena.network](https://almena.network). | Astro, pnpm |

In the **[almena-network](https://github.com/almena-network/almena-network)** umbrella repository, **almena** and **wallet** are linked as **Git submodules** so the hub stays in sync with their upstream repos; **docs** and **web** live in the same tree (clone once, work everywhere).

---

## Integration at a glance

- **Almena** (desktop) and the **CLI** talk to **almenad** over **gRPC** using the canonical protos in the **almena** repo.
- The **wallet** uses the daemon’s **REST** surface for the flows that require a signed, HTTP-friendly contract.
- **Docs** and **web** ship as static sites; they describe and promote the same components above.

---

## Quick links

- [Umbrella repository](https://github.com/almena-network/almena-network) (submodules + docs + web)
- [almena](https://github.com/almena-network/almena) (daemon, desktop, CLI, proto)
- [wallet](https://github.com/almena-network/wallet)
- [Website](https://almena.network)
- [Documentation](https://docs.almena.network)
