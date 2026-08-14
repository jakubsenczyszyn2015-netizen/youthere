# Changelog

All notable changes to the YouThere? desktop client.

## Latest build — 2026-08-14

**Parties now live on a hosted server.** The client talks to the YouThere? server
online instead of running one on your machine, so a party is visible to everyone
wherever they are — not just to people on the same network.

### Added
- Server address is remembered in `~/.youthere.json`, so the launcher pre-fills it next time.
- The launcher checks the server is actually answering before opening the app, and tells
  you when a free host is still waking up (that can take ~30 seconds).
- Secure `wss://` connections for remote servers; plain `ws://` is kept for `localhost`
  and `127.*` so local testing still works.

### Changed
- The launcher is now a single "which server?" field instead of the host/join screen.
- Download is about 5 MB smaller — 22 MB → 16.8 MB.

### Removed
- The bundled server. You no longer host from your own PC, share your LAN IP, or open
  firewall ports to get friends in.

### Unchanged
- The click-through desktop overlay: always-on-top banners for shouts, pokes, voice
  prompts and people joining, drawn over whatever you're doing.

## Previous build

First public release. Bundled its own server so one person hosted the party on their
machine and everyone else joined over the local network with the host's IP address.

- Party browser, party codes, and password-protected parties
- Voice chat with mic/output pickers, level meter, mute and deafen
- Room chat, free "are you there?" pokes, full-screen Shouts, and recorded voice notes
- Points economy — chat is free, Shout costs 10, Record costs 100
- Reflex test, Reaction duel, and Tic-tac-toe to earn points
- Click-through desktop overlay
