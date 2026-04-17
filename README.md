Lead Capture Automation with n8n
I built this to demonstrate a complete lead capture pipeline using n8n. When someone fills out the form, their details are automatically saved to Google Sheets and an email notification is sent to your inbox instantly, no manual work needed.
Why I built this
Most businesses collect leads through forms but then have to manually check submissions and notify their team. I wanted to automate that entire flow so the moment someone submits a form, the data is logged and the right person is notified without touching anything.
How it works
You open the HTML form and fill in your name, email, and message. When you hit submit, the form sends a POST request to an n8n Webhook. The Edit Fields node cleans and maps the incoming data. The Google Sheets node appends a new row with the lead details. Finally the Gmail node fires a formatted notification email to your inbox with the full submission.
Tech Stack
n8n for workflow automation, Google Sheets API for lead storage, Gmail API for email notifications, and HTML, CSS, and JavaScript for the frontend form.
How to Run
Open index.html and replace YOUR_PRODUCTION_WEBHOOK_URL with your n8n webhook URL, then open the file in your browser and submit the form.
How to Import the Workflow
Open n8n, click Add Workflow, select Import from File, and choose the workflow.json file. Then go to Credentials in n8n and add a new Google Sheets OAuth2 credential and a Gmail OAuth2 credential. To set these up you will need a Google Cloud project with both the Google Sheets API and Gmail API enabled. Once your credentials are connected, assign them to the Google Sheets node and the Gmail node inside the workflow. Make sure your Google Sheet has these columns in Row 1: Name, Email, Message, Time.
