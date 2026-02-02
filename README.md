# IP-Threat-Intelligence-Automation-System

An automated security workflow built with n8n that intercepts IP addresses via Telegram, checks their reputation using AbuseIPDB, and logs the results into Google Sheets for audit trailing.
🚀 Features
Real-time Monitoring: Intercepts IP queries via Webhooks.
Threat Intel Integration: Automatically fetches Abuse Confidence Scores.
Automated Logging: Saves timestamps, IP addresses, and safety status to Google Sheets.
Instant Alerts: Sends formatted reports back to Telegram.
🛠️ Technical Workflow
The system follows a linear automation logic:
Webhook: Receives the IP address from a Telegram bot.
HTTP Request: Queries the AbuseIPDB API for the IP's reputation.
Telegram Node: Sends a "Safe" or "Danger" alert to the user.
Google Sheets Node: Appends a new row with the threat data.
📸 Screenshots
Workflow Logic
The complete automation pipeline from Webhook to Google Sheets.
![](/assets/Workflow.png)
Data Mapping
Example of using JSON expressions like {{ $now }} and {{ $json.query.ip }} to dynamically map data.
![](/assets/DataMapping.png)
Database (Google Sheets)
The final output showing logged IP addresses and their respective abuse scores.
![](/assets/Sheet.png)
Telegram Node: Sends a "Safe" or "Danger" alert to the user.
![](/assets/Telegrambot.png)
🔧 Setup Instructions
Import the provided workflow.json into your n8n instance.
Replace the AbuseIPDB API Key in the HTTP Request node.
Connect your Google account and select your target spreadsheet.
Set the workflow to Active.
