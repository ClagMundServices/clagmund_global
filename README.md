# 📢 ClagMund Twitch Bot - Setup & Usage Guide

## 🚀 Installation & Setup

### **1️⃣ Invite the Bot to Your Server**
Use the bot's **invite link**:

```
https://discord.com/oauth2/authorize?client_id=1337191599477755935&permissions=268519424&integration_type=0&scope=bot+applications.commands
```

### **2️⃣ Ensure the Bot Has Correct Permissions**
Once added to your server:
- Go to **Server Settings → Roles** and **drag** the bot role **above** any role it needs to manage (e.g., the `Streaming Now!` role).

### **3️⃣ Give Access to the Notification Channel**
- Make sure the bot has **permission to send messages & embeds** in the designated Twitch notification channel.
- You can create a new **#twitch-notifications** channel and allow the bot to post.

---

## 🔧 Bot Commands & Usage

### **📜 General Commands**
| Command | Description | Example |
|---------|-------------|---------|
| `!liststreamers` | List all tracked Twitch streamers for the server | `!liststreamers` |
| `!addstreamer <TwitchUsername> <@DiscordUser> <ChannelID> <LiveRoleID> <NotificationRoleID> [Keyword]` | Register a new Twitch streamer for notifications | `!addstreamer iclagzi @ClagZ 1154294810451128410 1337349063858720813 167349474558720347 "GTA"` |
| `!removestreamer <TwitchUsername>` | Remove a Twitch streamer from tracking in this server | `!removestreamer iclagzi` |
| `!multistream` | Creates a link to multistream using all currently active streamers |  `!multistream`  |
| `!streamstats <TwitchUsername>` | Show the XP and total stream time of a specific streamer in the current server | `!streamstats iclagzi` |
| `!serverleaderboard` | Show the top 10 streamers based on XP and stream time for the current server | `!serverleaderboard` |
| `!globalleaderboard` | Show the top 10 streamers across all servers, using their highest recorded XP and stream time | `!globalleaderboard` |
| `!serverview` | Show the current server stats, combined XP and stream time along with total number of streamers | `!serverview` |

### 📲 **IDs & Placeholders**
- **ChannelID**: The numerical ID of the channel where notifications will be posted. *(Right-click the channel → Copy ID)*.
- **LiveRoleID**: The role assigned to the streamer when they go live. *(Right-click the role in Server Settings → Copy ID)*.
- **NotificationRoleID**: *(Optional)* The role that gets mentioned when a streamer goes live.
- **Keyword**: *(Optional)* If provided, notifications are only sent when the stream title contains this keyword.

#### **🚨 Using `none` as a Placeholder**
If you don’t want to assign a **Live Role** or **Notification Role**, use `none`:
- **No roles, no keyword**: `!addstreamer iclagzi @ClagZ 1154294810451128410 none none`
- **Only Notification Role**: `!addstreamer iclagzi @ClagZ 1154294810451128410 none 167349474558720347`
- **Only Live Role**: `!addstreamer iclagzi @ClagZ 1154294810451128410 1337349063858720813 none`
- **Both Roles + Keyword**: `!addstreamer iclagzi @ClagZ 1154294810451128410 1337349063858720813 167349474558720347 "GTA"`

---

## 📌 How Streamer Notifications Work

- The bot **checks every 30 seconds** if a streamer is live.
- If a **keyword** was set when adding the streamer, the bot **only** triggers if the Twitch stream **title contains** that keyword.
- When a streamer **goes live**:
  - The bot **posts an alert** in the assigned channel.
  - The bot **mentions the Notification Role** (if set).
  - The bot **assigns the Streamer Role** (if applicable).
  - The streamer's **XP increases by 10 points**.
  - The bot starts **tracking their stream duration**.
- When a streamer **goes offline**:
  - The bot **removes the Streamer Role**.
  - The bot **posts an offline message**.
  - The bot **adds their total stream duration to their stats**.

---

## 🏆 Leaderboards & Stream Stats

### **Checking a Streamer's Stats**
```
!streamstats <TwitchUsername>
```
🔹 Shows **XP** and **total stream time** for a specific streamer **in the current server**.

### **Server Leaderboard**
```
!serverleaderboard
```
🔹 Displays the **top 10 streamers** in your Discord server **ranked by XP and total stream time**.

### **Global Leaderboard**
```
!globalleaderboard
```
🔹 Displays the **top 10 streamers across ALL servers** using the bot.
🔹 If a streamer is in **multiple servers**, only their **highest** XP and stream time are considered.

### **Server Stats**
```
!serverview
```
🔹 Displays the **total streamers** using the bot, along with **total XP** and **streaming time**

---

## 🛠️ Troubleshooting

### **1️⃣ The bot is not responding**
- Ensure the bot is **online** in your server.
- Check if the bot has **correct permissions** to read and send messages in the channels.
- Ensure the bot **has access** to the roles it needs to assign.

### **2️⃣ The bot is not assigning/removing roles**
- **Make sure the bot's role is ABOVE** the role it is trying to assign in **Server Settings → Roles**.
- Check that the bot has **"Manage Roles"** permissions.

### **3️⃣ The bot is not sending notifications**
- Ensure the Twitch username is **correctly entered** when adding a streamer.
- If using a **keyword**, check if it **matches** the Twitch stream title exactly.

---

## 🎉 You're All Set!

If you have any issues, double-check the **permissions** and **role hierarchy**, or try removing and re-adding the bot. Happy streaming! 🚀

