# 📖 Pika Stats Overlay (Minecraft 1.8.9)

A stats overlay for **Pika Network** (Minecraft 1.8.9). While you play it shows who you're up against —
**FKDR, wins, level, their client and more** — in a separate window **and** inside the in-game TAB.
Works on **Lunar, Badlion, CM, Vanilla and cracked**.

> ⚠️ It only reads what's already on your screen + public Pika stats. It doesn't change the game, help
> you in combat, or touch other accounts.

> 📖 Full step-by-step guide lives in the **[Wiki](../../wiki)**.
> 💬 Help, updates & bug reports: **[Discord](https://discord.gg/SkpdG67kxF)**.

---

## ⬇️ Install & first run

1. Download the latest release and unzip it to a folder — **keep all files together**.
2. Start **Minecraft 1.8.9** first.
3. Run **`Pika_stats_overlay.exe`**. The first time, Windows may show a blue *Unknown publisher* popup →
   **More info → Run anyway** (normal for a small tool).
4. Pick the Minecraft process (**`javaw.exe`**) and the DLL **`minecraft_1.8.9.dll`**.
5. Click **Inject + Open Overlay**, join a game — done 🎉

Closed it? Type **`/pika-overlay`** in chat to bring it back.

---

## ⌨️ Chat commands

Caught by the overlay — never sent to the server, no one else sees them.

* **`/pika-overlay`** — open the stats window (type `/pika` + **TAB** to auto-complete)
* **`/pika-hide`** — hide it (keeps running in the background)
* **`/pika-toggle`** — show if hidden, hide if visible
* **`/pika-lookup <name>;`** — look up any player and print their stats in your chat

> `/pika-lookup` **must end with a semicolon `;`** — that's how it knows you're done.
> Example: `/pika-lookup Notch;`
> It prints: level · rank · name · guild · **friend? (yes/no)** · FKDR · WLR · Wins · WS · Client.

---

## ✨ Features

### 👥 Stats

Per player: **Level · Rank · Wins · WLR · FKDR · Win Streak (WS) · Guild · UUID (copy)**.
Rank is shown in the server's colour; players with no Pika profile are marked **NICKED**; right-click a
player to copy their UUID / name or send a **hacker / sniper report**. Pick your game **mode**, the
**sort** order, and which **columns** show in the window (drag to reorder).

### 🎮 In-game TAB

Adds up to **3 stat columns** next to each name in the real in-game TAB, plus player **health** and
**client logos**. Name colours follow the **server** (ranks / team colours) and update live on a lobby
switch.

### 🛰️ Client detection

Shows which client each player runs, with a logo — in the overlay **and** the TAB. **Lunar** and **CM**
are detected live in-game; other clients need a **Seraph key** (Settings → API). Detections are
crowd-shared and **self-correct** once a player is no longer on that client.

### 🛡️ Anti-cheat hints  *(Lunar & Badlion only)*

Optional chat warnings when a player shows cheat-like patterns — **Auto Clicker, Auto Block, Scaffold,
Speed Bridge, Fast Break** *(experimental)*.

> ⚠️ A **hint, not proof** — it can be wrong. "Worth a look", not an accusation.

### 🎯 Extras

* World **markers** above teammates (optionally only during a real round, not the lobby).
* **Offline / cracked support**, including a cosmetic fix that restores skins & cosmetics on offline-mode
  servers *(Lunar)*.
* Always-on-top, adjustable **opacity**, auto-reload, and settings that save automatically.

---

## ⚡ Under the hood

**Cache-first**: stats appear instantly from a local flat-file cache (`stats_cache.txt`), then refresh
asynchronously via the Pika API on a **rate-limit-safe** queue (the players you can see are fetched
first). Client detections are shared through a bundled local resolver database. A guard system prevents
duplicate entries, world-switch races and stale updates.

---

## 🆘 Troubleshooting

* **"Unknown publisher"** → *More info → Run anyway* (normal).
* **Blocked as a virus** → false positive from Windows Defender's AI (the file is clean) → add the folder
  as an **Exclusion** in Windows Security.
* **Stats show `-`** → check that **Game mode / Mode** match what you actually play, then **Reset**.
* **Commands do nothing** → `/pika-lookup` needs the trailing `;`.
* **Reporting a bug** → turn on **Enable debug logging** (Settings → Advanced), reproduce, share the log —
  leave it **off** while playing normally.

Still stuck? Join the **[Discord](https://discord.gg/SkpdG67kxF)** and tell us which client you're on +
what happened 🙌
