# GitHub Webhook Receiver with Flask

This is a simple Flask web application that listens for GitHub webhooks and prints the payload to your terminal or console. It's great for learning how webhooks work and how GitHub can communicate with your own apps.

![image](https://github.com/user-attachments/assets/c8591791-a355-496f-bd97-46678105e22d)

*Webhook works successfully!*
## What This Project Does

This app:
- Starts a local Flask server.
- Listens for a `POST` request at a `/webhook` endpoint.
- Prints the GitHub event data it receives.
- Uses [ngrok](https://ngrok.com/) to make your local server accessible over the internet.
- Is useful for testing GitHub webhooks on your machine before deploying to a real server.

## Tools Used

- [Python 3](https://www.python.org/)
- [Flask](https://flask.palletsprojects.com/)
- [ngrok](https://ngrok.com/) – exposes your local server to the internet
- [GitHub Webhooks](https://docs.github.com/en/webhooks)


## How to Set It Up

### 1. **Clone this repository**
```
git clone https://github.com/maazinmm/webhook-test.git
cd webhook-test
```
## Create and activate a virtual environment
```
python -m venv venv
venv\Scripts\activate
```

## Run the Flask app
```
python files/github-webhook.py
```
The app will start running on http://127.0.0.1:5000


## Expose Flask to the Internet with ngrok

GitHub needs to reach your local server to send webhook data.

### Step 1: Start ngrok
In a new terminal (don't close your Flask app), run:
```
ngrok http 5000
```
ngrok will give you a public URL like:
```
https://random-id.ngrok.app
```
## Connect GitHub Webhook
1. Go to your GitHub repository.
2. Click Settings > Webhooks > Add webhook.
3. Paste your ngrok URL + /github, for example:
```
https://random-id.ngrok.io/github
```
<sub>***/github is my app route as shown in the flask code***</sub>

4. Choose application/json as the content type.
5. Choose the events you want (or select "Just the push event").
6. Click Add webhook.

## Test
Make a push to your GitHub repo or trigger the event you selected.

You should see the payload printed in your Flask terminal window.

## Example of an output
![image](https://github.com/user-attachments/assets/af3656cf-c3d7-4923-b7f3-8cbac6640c45)

## Works Successfuly!
You should see a message like this in the webhook window in github
![image](https://github.com/user-attachments/assets/b90c5cf4-3371-4cdd-bca8-54082d89bc2d)

