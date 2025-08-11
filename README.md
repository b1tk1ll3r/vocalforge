# 🎙️ VocalForge

![VocalForge Logo](https://github.com/b1tk1ll3r/vocalforge/blob/main/logo.png)  
[![Discord Bot](https://img.shields.io/badge/Discord-Invite-blue?logo=discord&logoColor=white)](https://discord.com/oauth2/authorize?client_id=1403851394452291584)
[![License](https://img.shields.io/github/license/b1tk1ll3r/vocalforge)](LICENSE)
[![Go Version](https://img.shields.io/github/go-mod/go-version/b1tk1ll3r/vocalforge)](go.mod)

> **VocalForge** is a Discord bot that creates **temporary private voice channels** on demand — with auto-cleanup, per-guild settings, and instant permissions.

---

## ✨ Features

- 🛠 **Per-Guild Configuration** – Each server can set its own lobby, category, and timeout.  
- 🚪 **Instant Private Rooms** – Join the lobby, get your own room.  
- ⏱ **Auto-Cleanup** – Empty channels are deleted after a set timeout.  
- 🔒 **Access Control** – Owners can `/adduser` to grant access instantly.  
- 🌍 **Multi-Language Ready** – Supports multiple languages (default: German).  

---

## 📜 Commands

| Command | Description |
| ------- | ----------- |
| `/makevc [name] [user_limit] [timeout_min]` | Create a private voice channel just for you. |
| `/setlobby <lobby_name>` | Set the voice channel name that triggers private room creation. *(Admin only)* |
| `/setcategory <category_name>` | Set or create the category for private rooms. *(Admin only)* |
| `/settimeout <minutes>` | Set inactivity timeout for private channels. *(Admin only)* |
| `/adduser <@member>` | Give a user access to your private voice channel. |

📖 **Full command documentation** is available in the [VocalForge Wiki](https://github.com/b1tk1ll3r/vocalforge/wiki).

---

## 🚀 Quickstart

1. **Invite the bot** to your server → [Click here](https://discord.com/oauth2/authorize?client_id=1403851394452291584)  
2. **Create a lobby voice channel** named `➕ Erstelle privaten Raum` *(or change via `/setlobby`)*  
3. **Join the lobby** – VocalForge will create a private voice channel for you automatically.  

---

## 🛠 Development

```bash
git clone https://github.com/b1tk1ll3r/vocalforge.git
cd vocalforge
go build
DISCORD_TOKEN=your_token_here ./vocalforge
