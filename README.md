# Game2

A cross-platform game project targeting Android and Windows with an Expo client, a browser preview, account services, and a separately hosted game backend.

## Current architecture

- `client/`: Expo application (Android and Windows build target).
- `server/`: Classic-Brawl backend integration notes and server deployment work.
- `web/`: browser preview and HTTP API (planned).
- MongoDB: account and profile persistence (planned).

## Backend foundation

The selected upstream project is [Classic-Brawl](https://github.com/presidentofgoblin/Classic-brawl), a community server emulator for the v26 client protocol. It is **not** the official Brawl Stars source code and does not provide an Expo client.

Upstream revision selected for evaluation: `9e1f76e4fa071adf68427f2baee2ec27f586384b` (2021-02-20).

The upstream server listens for raw TCP connections on port `9339`. It is not an HTTP server. Keep it separate from the HTTP API/preview service and deploy it only on hosting that explicitly supports public inbound TCP connections.

## Licensing and assets

Classic-Brawl declares GNU GPL-3.0. If we modify and distribute its server code, we must comply with GPL-3.0, including providing the corresponding source and preserving required notices. See [server/UPSTREAM.md](server/UPSTREAM.md).

Do not assume that the GPL license on the repository automatically grants rights to Supercell trademarks, game artwork, audio, maps, or other proprietary assets. This project will not download or redistribute unofficial modified client APKs.

## Development status

This repository is being initialized. No working game client, account API, MongoDB connection, or deployed game server is claimed yet.