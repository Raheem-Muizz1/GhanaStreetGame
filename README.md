# Spar

A browser version of **Spar**, the Ghanaian street card game. One HTML file, no build step, no install.

- 2 to 4 players, 32-card deck (no Aces), five cards each
- Play against the computer (Easy, Normal or Hard, which counts cards), or online with friends using a room code
- Standard mode (first to the target score) and Knockout mode (last player standing)
- Realistic table: opponents' cards face-down, played cards stay on the table until the round ends
- A virtual deck cut in round 1: the cutter gets the first card and leads
- Eight drawn avatars whose faces react to the game, a racetrack table with a leather rail, string lights and a kente rug, a game-speed setting (tap the table to skip pauses), and a lively classic look: drifting suits, shimmering title, tap-chip menus, pulsing turn glow, floating +points, a final-trick alert, felt table with a wooden rim, paper cards that fan in your hand, brass nameplates
- Background talking-drum music (the drum button turns it off), sounds, deal and sweep animations, emoji reactions, a win tally, and a How to play screen
- Rejoin a game if your connection drops or you reload the page
- Installable on a phone ("Add to Home Screen"); games against the computer work offline

## Play

Open the live page (after you enable GitHub Pages, see below):

`https://YOUR-USERNAME.github.io/YOUR-REPO/`

Or just open `index.html` in any browser.

### Play online with friends

1. Open the page, pick **Online friend** for one or more opponent seats, and tap **Create room**.
2. Send the 5-letter room code to your friends, along with the page link.
3. They open the page, type the code under **Join a friend's game**, and tap **Join room**.

Online play connects players directly through [PeerJS](https://peerjs.com), so it needs an internet connection but no server of your own. If a friend drops out mid-game, a computer takes over their seat.

### If online play will not connect

- Open the game from the GitHub Pages link in Chrome or Safari, not from inside a file previewer or another app.
- "Create room" or "Join room" shows what failed. If it says the connection server could not be reached, try another Wi-Fi or mobile data connection and turn off any VPN or data saver.
- The free PeerJS cloud server is community run and is sometimes busy. You can run your own PeerServer and set `peerServer` in `CONFIG`.
- Hosts can tap **Share invite** in the lobby to send friends a link that fills in the room code for them.
- Playing against the computer never needs the internet.
- **Your own server (optional):** run a free PeerServer (`npm i peer`, then `npx peerjs --port 9000 --path /`) on a host such as Render or Railway, then share the game link with `?peerhost=your-server.example.com` added to the end. Everyone using that link connects through your server.

## Rules in brief

- Each round has five tricks. The player who wins a trick leads the next one.
- You must follow the suit that was led if you can. Otherwise you may play any card.
- The highest card of the suit led wins the trick. King is highest, 6 is lowest.
- Only the **fifth trick** scores: 1 point, or 2 points if it is won with a 6.
- **Standard:** first player to the target score wins.
- **Knockout:** when a player reaches the target, the next active player clockwise is knocked out and everyone's score resets. The last player left wins.

## Publish with GitHub Pages

1. Push this repository to GitHub.
2. Open the repository, then **Settings, Pages**.
3. Under **Build and deployment**, set **Source** to **Deploy from a branch**, choose branch `main` and folder `/ (root)`, then **Save**.
4. After a minute or two the link above goes live.

## Customize

Everything you are likely to change is in the `CONFIG` block at the top of the script in `index.html`: ranks, suits, hand size, bonus rule, computer names, computer thinking time and how often the Normal computer makes a random move.

## Files

- `index.html`: the whole game
- `manifest.webmanifest`, `sw.js`, `icon-192.png`, `icon-512.png`: let people install it on a phone and use it offline. Keep them in the same folder as `index.html`.

## License

MIT, see `LICENSE`.
