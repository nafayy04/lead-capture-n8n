Lead Capture Automation with n8n
An automated lead capture pipeline that collects form submissions, logs them to Google Sheets, and sends instant Gmail notifications. Built entirely with n8n — no backend code required.

Demo

User fills the form → data saved to Google Sheets → email notification fired instantly

Features

HTML lead capture form with validation and success state
Webhook trigger that receives form submissions instantly
Data cleaning and field mapping via n8n Edit Fields node
Automatic row append to Google Sheets on every submission
Gmail notification email sent to your inbox with full lead details
Production ready and always on once activated in n8n


Tech Stack

n8n — workflow automation
Google Sheets API — lead storage
Gmail API — email notifications
HTML / CSS / JavaScript — frontend form


How It Works

User submits the HTML form with their name, email, and message
The form sends a POST request to the n8n Webhook node
The Edit Fields node cleans and maps the incoming data
The Google Sheets node appends a new row with the lead details
The Gmail node sends a formatted notification email to your inbox


Setup Instructions
Prerequisites

n8n installed locally or on a server
A Google account with Google Sheets and Gmail access
A Google Cloud project with Gmail API and Google Sheets API enabled

Steps
1. Clone the repo
bashgit clone https://github.com/nafayy04/lead-capture-n8n.git
cd lead-capture-n8n
2. Import the workflow into n8n

Open n8n and go to Workflows
Click the three dots menu and select Import from File
Select workflow.json from this repo

3. Set up credentials

In n8n go to Credentials and add a new Google Sheets OAuth2 credential
Add a new Gmail OAuth2 credential
Connect both to your Google account

4. Configure the workflow

Open the Google Sheets node and select your spreadsheet
Make sure your sheet has these columns in Row 1: Name, Email, Message, Time
Open the Gmail node and set your email address in the To field

5. Configure the HTML form

Open index.html
Replace YOUR_PRODUCTION_WEBHOOK_URL with your n8n Production Webhook URL

jsconst WEBHOOK_URL = 'YOUR_PRODUCTION_WEBHOOK_URL';
6. Activate the workflow

In n8n hit the Active toggle in the top right
Open index.html in your browser and submit a test entry
Check your Google Sheet and Gmail inbox


Project Structure
lead-capture-n8n/
├── index.html        # Lead capture form (frontend)
├── workflow.json     # n8n workflow export
└── README.md         # Project documentation

Google Sheet Setup
Create a Google Sheet with these exact column headers in Row 1:
Name Email Message Time
n8n will append a new row automatically on every form submission.

Author
Nafay — github.com/nafayy04
Open to freelance automation and AI workflow projects. Feel free to reach out.

License
MIT — free to use and modify.
