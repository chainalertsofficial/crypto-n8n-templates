================================================================
  CHAIN ALERTS — Crypto Price Alert Bot
  n8n Workflow Template  |  chainalerts.sellup.io
================================================================

Thank you for purchasing. This workflow gives you a personal
crypto alert bot you control entirely through Telegram.
No coding required. Setup takes about 10 minutes.

----------------------------------------------------------------
  WHAT THIS DOES
----------------------------------------------------------------

- Monitors any coin's price every 5 minutes via CoinGecko
- You control everything by sending commands to your Telegram bot
- Set price alerts, percentage move alerts, check prices on demand
- Sends a morning summary every day at 8AM
- All alerts are stored and persist — nothing resets if n8n restarts

----------------------------------------------------------------
  WHAT YOU NEED BEFORE YOU START  (all free)
----------------------------------------------------------------

1. n8n installed on your computer
   Download: https://n8n.io/download

2. A Telegram account

3. A free CoinGecko API key
   Sign up at: https://www.coingecko.com/en/api
   Takes 2 minutes. Copy your API key.

4. A Telegram Bot token + your Chat ID
   Instructions for both are in STEP 2 and STEP 3 below.

----------------------------------------------------------------
  STEP 1 — IMPORT THE WORKFLOW INTO N8N
----------------------------------------------------------------

1. Open n8n on your computer
2. Click the menu in the top left > Import Workflow
3. Select the file:  crypto-price-alert-v1.json
4. The workflow will appear on your canvas
5. Do not run it yet — complete the steps below first

----------------------------------------------------------------
  STEP 2 — CREATE YOUR TELEGRAM BOT (2 minutes)
----------------------------------------------------------------

1. Open Telegram and search for:  @BotFather
2. Press Start
3. Send the message:  /newbot
4. BotFather will ask for a name — type anything, e.g.  MyAlertBot
5. It will then ask for a username — must end in 'bot', e.g.  myalerts_bot
6. BotFather will reply with your Bot Token
   It looks like:  7412563890:AAFxyz123abc...
7. Copy and save this token — you will need it in STEP 4

----------------------------------------------------------------
  STEP 3 — GET YOUR TELEGRAM CHAT ID (1 minute)
----------------------------------------------------------------

1. Open Telegram and search for:  @userinfobot
2. Press Start or send any message
3. It will immediately reply with your Chat ID
   It is a number like:  123456789
4. Copy and save this number — you will need it in STEP 4

----------------------------------------------------------------
  STEP 4 — ENTER YOUR CREDENTIALS INTO THE WORKFLOW
----------------------------------------------------------------

In n8n, you need to update 3 places:

  A. COINGECKO API KEY
     - Click the "Fetch Crypto Price" node
     - Find the URL field
     - Replace  YOUR_API_KEY  with your CoinGecko key

  B. TELEGRAM BOT TOKEN
     - Click any Telegram node in the workflow
     - Click "Create New Credential"
     - Paste your Bot Token from STEP 2
     - Save it — this applies to all Telegram nodes automatically

  C. YOUR CHAT ID
     - Click the "Send Telegram Alert" node
     - Find the Chat ID field
     - Replace  YOUR_CHAT_ID  with the number from STEP 3
     - Do the same for any other Telegram nodes that have a Chat ID field

----------------------------------------------------------------
  STEP 5 — ACTIVATE THE WORKFLOW
----------------------------------------------------------------

1. Click the toggle in the top right of n8n to set it to Active
2. Open Telegram and find the bot you created in STEP 2
3. Press Start
4. Send the command:  /help
5. The bot should reply with a list of available commands

If it replies, everything is working.

----------------------------------------------------------------
  HOW TO USE YOUR BOT — ALL COMMANDS
----------------------------------------------------------------

  /help
  Shows all available commands

  /price BTC
  Gets the current price of Bitcoin instantly
  Works with any coin ID (see Coin IDs section below)

  /add BTC 50000 above
  Sets an alert — triggers when BTC goes ABOVE $50,000

  /add ETH 3000 below
  Sets an alert — triggers when ETH goes BELOW $3,000

  /alert BTC 5%
  Sets a percentage alert — triggers if BTC moves 5% in
  either direction from its current price

  /list
  Shows all your active alerts

  /remove BTC
  Deletes your alert for Bitcoin

  /pause
  Pauses all alerts temporarily (they are not deleted)

  /resume
  Turns alerts back on after pausing

  /top5
  Shows the top 5 coins by 24-hour percentage gain

Every morning at 8:00 AM UTC the bot automatically sends you
a summary of all active alerts and the current price of each coin.

----------------------------------------------------------------
  COIN IDS — HOW TO FIND THE RIGHT ONE
----------------------------------------------------------------

CoinGecko uses specific IDs for each coin, not just the ticker.

Common ones:
  Bitcoin      = bitcoin
  Ethereum     = ethereum
  Solana       = solana
  BNB          = binancecoin
  XRP          = ripple
  Dogecoin     = dogecoin
  Avalanche    = avalanche-2
  Chainlink    = chainlink

To find any coin's ID:
1. Go to https://www.coingecko.com
2. Search for the coin
3. Look at the URL — the last part is the ID
   Example: coingecko.com/en/coins/bitcoin  →  ID is  bitcoin

----------------------------------------------------------------
  TROUBLESHOOTING
----------------------------------------------------------------

Bot does not reply to /help
  - Make sure you pressed Start in the bot chat first
  - Check that the Bot Token is entered correctly in n8n
  - Make sure the workflow is set to Active (toggle top right)

No alerts are firing
  - Check your Chat ID is correct
  - Make sure the workflow is Active
  - Test with /price BTC to confirm the bot is responding

CoinGecko returns an error
  - Free tier has a rate limit — the workflow handles this
    but if you are testing repeatedly, wait 1 minute and retry
  - Double check your API key has no extra spaces when pasted

Price is showing as 0 or null
  - The coin ID is likely wrong — check the exact ID on CoinGecko
  - Coin IDs are lowercase and sometimes have dashes (e.g. avalanche-2)

----------------------------------------------------------------
  SUPPORT
----------------------------------------------------------------

If you are stuck, visit the store and leave a message:
chainalerts.sellup.io

For n8n general help: https://community.n8n.io

----------------------------------------------------------------
  LEGAL
----------------------------------------------------------------

This template is for personal use only.
You may not resell or redistribute this workflow file.
Price data is provided by CoinGecko's free public API.
Chain Alerts is not responsible for trading decisions
made based on alerts from this tool.

================================================================
  Chain Alerts  |  n8n Crypto Automation Templates
  chainalerts.sellup.io
================================================================
