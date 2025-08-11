# Stream Alerts Bot – User Guide

## 📌 What the Bot Does
- Monitors Discord users’ **streaming status** (Twitch, YouTube, Kick).
- Auto-creates a **#live-alerts** channel and two roles:
  - **Live Streamer** – given to members while they are streaming.
  - **Stream Alerts** – mentioned when someone goes live.
- Posts a rich embed with stream title, start time, and a “Watch Live” button.
- Optionally requires a **keyword** in the stream title to trigger alerts.

---

## ⚡ Getting Started
1. **Invite the Bot** to your server (ask the owner for the invite link).
2. Make sure the bot has:
   - **Manage Channels** – so it can create `#live-alerts`.
   - **Manage Roles** – so it can create/assign roles.
   - **Send Messages**, **Embed Links**.
   - **View Channel** permissions in any alert channel.
3. The bot will auto-create:
   - `#live-alerts` channel
   - **Live Streamer** and **Stream Alerts** roles

---

## 💬 Commands

**Set a keyword** (optional):
```
!setkeyword yourword
```
- Streams must include this word in their title to be announced.
- Clear it with:
```
!setkeyword
```

**Manually trigger alerts** for all currently live members:
```
!blastlive
```
- Will only send alerts for streams matching the keyword (if set).
- To bypass the keyword filter:
```
!blastlive true
```

---

## 🔔 How Alerts Work
- When a member starts streaming:
  - Bot sends an embed in `#live-alerts`
  - Assigns **Live Streamer** role
  - Mentions **Stream Alerts** role
- When they stop streaming:
  - Sends an “ended stream” message
  - Removes the **Live Streamer** role

---

## 📌 Notes for Server Owners
- Rename `#live-alerts` if you want, but keep it text-based and visible to members.
- Adjust **Stream Alerts** role permissions if you want only certain people to be notified.
- Members can join/leave the **Stream Alerts** role if you make it self-assignable.

---

[Bot Link](https://discord.com/oauth2/authorize?client_id=1337191599477755935)
