# USA Visa Slot Tracker

If you've ever tried to book a US visa appointment, you know the struggle — slots appear and disappear faster than you can refresh the page.

I wrote this for myself when I got tired of manually checking the site every hour. The script watches for open slots at the embassy in Astana and immediately sends a Telegram message the moment something shows up.

## What you need

- Python 3
- Chrome + ChromeDriver
- A Telegram bot (takes 2 minutes to set up via @BotFather)

## Setup

Install dependencies:

```bash
pip install -r requirements.txt
```

Create a `.env` file:

```
LOGIN=your email from ais.usvisa-info.com
PASSWORD=your password from ais.usvisa-info.com
CHECK_PAGE=https://ais.usvisa-info.com/ru-kz/niv/schedule/YOUR_ID/payment

BOT_TOKEN=your bot token
CHAT_ID=where to send slot alerts
CHAT_ID_SERVICE=where to send service messages and errors
```

`CHECK_PAGE` is the payment/schedule page from your account — the URL contains your application ID.

Run:

```bash
python USAvisa.py
```

The script runs in a loop and checks every 2 minutes. As soon as slots open up, you get a message and can go book right away.
