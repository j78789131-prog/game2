# Classic-Brawl backend integration

## Upstream

- Repository: https://github.com/presidentofgoblin/Classic-brawl
- Selected revision: `9e1f76e4fa071adf68427f2baee2ec27f586384b`
- Upstream license: GNU General Public License v3.0 (GPL-3.0)
- Upstream protocol listener: TCP port `9339`
- Upstream documented Python dependency: `tinydb`
- Upstream entry point: `main.py`

This directory currently contains integration documentation only; the upstream server source has not been copied into this repository yet.

## Hosting requirements

Classic-Brawl uses Python sockets and accepts raw TCP clients. A normal Render Web Service is designed for HTTP/HTTPS traffic and is not a drop-in host for this game-protocol listener. Before deployment, choose a host that explicitly supports public inbound TCP on port 9339, or redesign the networking layer around a supported transport.

Use the HTTP service separately for:
- account registration and sign-in;
- MongoDB-backed user profiles;
- health/status endpoints;
- browser preview and client configuration.

Never expose MongoDB credentials or server secrets in the Expo application.

## Client compatibility

The upstream README refers to a third-party pre-modified client. We will not download, package, or redistribute that client. Our Android/Windows client will be developed separately and will need an authorized, compatible protocol implementation. An Expo app cannot simply load the original compiled Android APK as source code.

## GPL-3.0 compliance checklist before copying or modifying upstream code

- Include the complete upstream GPL-3.0 license text.
- Preserve upstream copyright and attribution notices.
- Mark modified files and the date of modifications.
- Distribute the corresponding source under GPL-3.0 when conveying a covered derivative work.
- Review every asset/data file separately; do not assume that code licensing clears third-party game assets or trademarks.

This is an engineering note, not legal advice.