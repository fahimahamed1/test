# Telegram Bot Admin Panel

A fully featured Telegram bot with a powerful admin panel — manage users, premium access, interface pages, approvals, suspensions, timers, and more, all from within Telegram.

---

## ✨ Features

- **Admin Panel** – Manage everything via Telegram:
  - Toggle **Premium Mode** to restrict access to approved users only.
  - View and approve **Pending Users**.
  - Suspend or delete users.
  - Manually add custom users.
  - Set **Timers** for temporary user access.
  - Broadcast messages to all users.
  - Add or delete `.ejs` **pages** used in the bot interface.

- **User Management**
  - View pending, approved, and suspended users.

- **Timers**
  - Grant or revoke temporary access automatically.

- **Page Management**
  - Dynamically manage interface pages like welcome or help messages.

---

## 📦 Requirements

- **Node.js** (v14.x or higher)
- **npm** (v6.x or higher)
- **Telegram Bot Token** (via [BotFather](https://core.telegram.org/bots#botfather))
- **Telegram Admin User ID(s)** — for admin access to the bot

---

## 🚀 Installation & Setup

### 1. Clone the repository

```bash
git clone https://github.com/fahimahamed1/Phishing-bot.git
cd Phishing-bot
```

### 2. Create a `.env` file

```bash
cp .env.example .env
```

Edit the `.env` file with your configuration:

```env
BOT_TOKEN=your_bot_token_here
HOST_URL=http://localhost
PORT=3000
ADMINS=123456789,987654321
```

### 3. Install dependencies

```bash
npm install
```

### 4. Start the bot

```bash
npm start
```

The bot should now be up and running! Admins can access the admin panel through Telegram.

---

## 🐳 Run with Docker

You can run this bot using **Docker** or **Docker Compose** for easier deployment and management.

### Option 1: Run with Docker CLI

```bash
docker run -d -p 3000:3000 --name phishing-bot-container \
  -e BOT_TOKEN=your_bot_token_here \
  -e HOST_URL=http://localhost \
  -e ADMINS=5630435349,1234567890 \
  fahimahamed/phishing-bot:latest
```

> ✅ Replace the environment values with your actual bot token, host URL, and admin Telegram user IDs.

### Option 2: Run with Docker Compose

1. Create a `.env` file:

```env
BOT_TOKEN=your_bot_token_here
HOST_URL=http://localhost
PORT=3000
ADMINS=5630435349,1234567890
```

2. Create a `docker-compose.yml` file:

```yaml
version: '3.8'

services:
  phishing-bot:
    image: fahimahamed/phishing-bot:latest
    container_name: phishing-bot-container
    ports:
      - "3000:3000"
    env_file:
      - .env
    restart: unless-stopped
```

3. Start the bot:

```bash
docker-compose up -d
```

---

## 🛠 Usage

- Only users listed as admins in `.env` under `ADMINS` can access the admin panel.
- Admins can approve or suspend users, toggle premium mode, manage timers, and more directly via Telegram.
- Premium mode restricts the bot’s usage to approved users only.
- Timers allow temporary access control for users.

---

## 💬 Example Admin Commands

- `/approve <user_id>` – Approve a user manually
- `/suspend <user_id>` – Suspend a user
- Admins can also use inline buttons within Telegram to manage users quickly.

---

## 🧩 Troubleshooting

- **Bot not responding?**
  - Make sure your `BOT_TOKEN` is correct and the bot is running (`npm start` or `docker ps`).

- **Admin commands not working?**
  - Ensure your Telegram user ID is included in the `ADMINS` environment variable.

- **Port conflicts?**
  - Change the `PORT` value in `.env` or Docker settings.

---

## 🤝 Contributing

Feel free to open issues or submit pull requests! Suggestions and improvements are welcome.

---

## 📄 License

This project is open source and free to use under the MIT License.

---
