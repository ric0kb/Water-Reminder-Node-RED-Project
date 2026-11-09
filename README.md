\# 🚰 Node-RED Hourly Hydration \& Air Quality Bot



An automated, local-first Node-RED flow that sends hourly hydration reminders with Singapore military-themed ("Encik/Recruit") nag messages and real-time Singapore Air Quality (PM2.5) advisories directly via Telegram.



\## 🌟 Features



\- \*\*Hourly Hydration Nagging:\*\* Sends randomized, contextual hydration reminders during operational hours (08:01 to 22:01 SGT).

\- \*\*Singapore Air Quality Updates:\*\* Fetches real-time 1-hour PM2.5 data directly from the official Data.gov.sg API and formats actionable outdoor activity recommendations across North, South, East, West, and Central regions.

\- \*\*Self-Service Telegram Subscriptions:\*\* Users can subscribe using `/fall\_in` and unsubscribe using `/fall\_out`.

\- \*\*State Persistence:\*\* Dynamically reads and updates subscriber preferences locally in a JSON file.



\---



\## 📁 Repository Structure



```text

.

├── flows.json               # Scrubbed Node-RED flow export ready for import

├── recipients.example.json   # Template file showing the subscriber JSON structure

├── .gitignore               # Prevents local runtime data and credentials from being tracked

└── README.md                # Project documentation

