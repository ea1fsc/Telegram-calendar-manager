# Calendar Bot for Telegram

A Telegram bot to manage calendars hosted on a self-hosted NextCloud instance. This bot allows you to create, update, delete, and list events, send event invitations via email, and receive notifications in Telegram based on event schedules.

## Features

- Connects to your NextCloud calendars via **CalDAV**.
- Add, delete, and update events from Telegram commands.
- List upcoming events.
- Send email invitations with `.ics` files to participants.
- Notifications in Telegram when events occur or according to configurable reminders.
- Docker-ready for easy deployment.

## Commands (Telegram)
  - /start – Start the bot
  - /help – Show available commands
  - /add_event – Add a new event to your calendar
  - /delete_event – Delete an existing event
  - /list_events – List upcoming events

**There will be more commands as the project grows.**

## Requirements

- Python 3.12+
- NextCloud instance with CalDAV enabled
- Telegram bot token
- SMTP email account for sending invitations

## Installation

1. Clone the repository:
  ```bash
  git clone https://github.com/ea1fsc/Telegram-calendar-manager.git
  cd Telegram-calendar-manager
  ```

2. Create a .env or config.env file with your credentials:
  - `TELEGRAM_BOT_TOKEN`= YOUR_TELEGRAM_BOT_TOKEN
  - `NEXTCLOUD_URL`= https://NEXTCLOUD_URL
  - `NEXTCLOUD_USER`= YOUR_NEXTCLOUD_USERNAME
  - `NEXTCLOUD_PASSWORD`= YOUR_NEXTCLOUD_PASSWORD
  - `SMTP_EMAIL`= YOUR_EMAIL
  - `SMTP_PASSWORD`= YOUR_EMAIL_PASSWORD

3. Install dependencies:
  ```bash
  pip install -r requirements.txt
  ```
4. Run the bot
  ```bash
  python bot/main.py
  ```
## Docker
1. Build the Docker image:
   ```bash
   docker build -t calendar_bot .
   ```
2. Run the Docker container:
   ```bash
   docker run -d --name calendar_bot --env-file config.env calendar_bot
   ```
