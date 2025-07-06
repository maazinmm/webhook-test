# GitHub Webhook Receiver with Flask

This is a simple Flask web application that listens for GitHub webhooks and prints the payload to your terminal or console. It's great for learning how webhooks work and how GitHub can communicate with your own apps.

---

## What This Project Does

This app:
- Starts a local Flask server.
- Listens for a `POST` request at a `/webhook` endpoint.
- Prints the GitHub event data it receives.
- Uses [ngrok](https://ngrok.com/) to make your local server accessible over the internet.
- Is useful for testing GitHub webhooks on your machine before deploying to a real server.

---

## Tools Used

- [Python 3](https://www.python.org/)
- [Flask](https://flask.palletsprojects.com/)
- [ngrok](https://ngrok.com/) – exposes your local server to the internet
- [GitHub Webhooks](https://docs.github.com/en/webhooks)

---

## How to Set It Up

### 1. **Clone this repository**

git clone https://github.com/maazinmm/webhook-test.git
cd webhook-test

## Create and activate a virtual environment

python -m venv venv
venv\Scripts\activate


## Run the Flask app

python github-webhook.py

The app will start running on http://127.0.0.1:5000


## Expose Flask to the Internet with ngrok

GitHub needs to reach your local server to send webhook data.

### Step 1: Start ngrok
In a new terminal (don't close your Flask app), run:

ngrok http 5000

ngrok will give you a public URL like:
https://random-id.ngrok.app

## Connect GitHub Webhook
1. Go to your GitHub repository.
2. Click Settings > Webhooks > Add webhook.
3. Paste your ngrok URL + /github, for example:

https://random-id.ngrok.io/webhook

4. Choose application/json as the content type.
5. Choose the events you want (or select "Just the push event").
6. Click Add webhook.

```bash