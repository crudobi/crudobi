# Crudobi

Local-first builder. My hardware, my builds, no hosted anything. I ship systems that survive being killed: crash-only services, mesh networks, and one universal engine underneath it all.

## What I'm building

- **wasm3d** — universal engine: pure-Rust compute core, typed 2D/3D render-command protocols, device interconnect traits (Wi-Fi / Bluetooth / LoRa / camera). Every project's logic ports here.
- **Mesh Sim** — high-fidelity mesh network simulator: PHY, MAC, L3/L4, Bluetooth, LoRa, dynamic topology editing.
- **Mesh Registry** — browser-only distributed registry over a WebSocket mesh, CRDT state sync.
- **NewsCruise** — tunable news and trading feed.
- **Local Events Map** — local-first events map, Rust/WASM clustering.
- **CrashDock / Fleet Controller** — crash-only fleet control plane and agents.

Live projects: [crashproof.press/projects](https://crashproof.press/projects/)

## How I build

- **Local only** — everything builds and runs on machines I own.
- **Crash-only design** — durable state lives outside the process; SIGKILL is a normal event, recovery is the only startup path.
- **Engine computes, hosts render** — heavy math and untrusted-data parsing go to the WASM engine layer, fail-closed; hosts own input and I/O.
- **No divergent implementations** — one engine, every project ports to it.
