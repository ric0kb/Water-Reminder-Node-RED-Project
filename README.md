\# 🚰 Node-RED Hourly Hydration \& Air Quality Bot



An automated, local-first Node-RED flow that sends hourly hydration reminders with Singapore military-themed ("Encik/Recruit") nag messages and real-time Singapore Air Quality (PM2.5) advisories directly via Telegram.



\## 🌟 Features



\- \*\*Hourly Hydration Nagging:\*\* Sends randomized, contextual hydration reminders during operational hours (08:01 to 22:01 SGT).

\- \*\*Singapore Air Quality Updates:\*\* Fetches real-time 1-hour PM2.5 data directly from the official Data.gov.sg API and formats actionable outdoor activity recommendations across North, South, East, West, and Central regions.

\- \*\*Self-Service Telegram Subscriptions:\*\* Users can subscribe using `/fall_in` and unsubscribe using `/fall_out`.

\- \*\*State Persistence:\*\* Dynamically reads and updates subscriber preferences locally in a JSON file.



\---



\## 📁 Repository Structure



```text

.

├── flows.json               # Scrubbed Node-RED flow export ready for import

├── recipients.example.json   # Template file showing the subscriber JSON structure

├── .gitignore               # Prevents local runtime data and credentials from being tracked

└── README.md                # Project documentation




---

## 🛠️ Prerequisites

- **Node-RED** (Installed locally or via Docker on Raspberry Pi, Linux, Windows, or macOS)
- **Node-RED Palette:** `node-red-contrib-telegrambot` (v17.0.3 or higher)
- **Telegram Bot Token:** Created via [@BotFather](https://t.me/BotFather) on Telegram

---

## 🚀 Quick Start Guide

### 1. Set Up Subscriber Storage
Ensure your Node-RED runtime environment has access to your subscriber file path (default defined in flow nodes: `/data/recipients.json`).

Copy the example template file to create your local runtime state file:
bash
cp recipients.example.json /data/recipients.json

If you are running Node-RED natively without Docker, update the `file in` and `file` nodes in your flow to point to your preferred local directory (e.g., `/home/pi/.node-red/recipients.json`).

### 2. Import the Flow
1. Open your Node-RED Flow Editor.
2. Open the top-right menu ☰ $\rightarrow$ **Import**.
3. Select **select a file to import** and upload `Water Reminders.json`.
4. Click **Import**.

### 3. Configure Your Telegram Bot Node
1. Double-click any Telegram node in the imported flow (`Telegram Receiver` or `The Nag Master 3000`).
2. Click the pencil edit icon next to the **Bot** field.
3. Enter your **Bot Name** and your secret **Bot Token** provided by @BotFather.
4. Click **Update**, then hit **Deploy** in the top right.

---

## 🤖 Telegram Bot Commands

| Command | Action |
| :--- | :--- |
| `/fall_in` | Subscribe or re-subscribe to hourly hydration and AQ reminders. |
| `/fall_out` | Pause/unsubscribe from receiving reminders. |

---
