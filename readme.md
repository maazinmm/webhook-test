# Readme.md

![alt text](image9.png)
To activate Webhook, you go to Settings in your github repo

![alt text](image-1.png)
Find Webhooks in the left side pane

![alt text](image-2.png)
Add Webhook

![alt text](image3.png)
Run the web App

![alt text](image4.png)
Open a new terminal window to run ngrok
ngrok translates your localhost address to one that's open to the internet (useful for the webhook)
You have to download and install ngrok first (a simple google search should give you enough info)

![alt text](image.png)
Run: ngrok http [port number] 
```bash
ngrok http 5000
```
![alt text](image5.png)
Your "public" localhost address is live

![alt text](image6.png)
Paste the public URL in the Webhook payload, and make "content-type" here matches your code

![alt text](image7.png)
Scroll down and select the event you want to trigger the webhook

![alt text](image8.png)
I have selected "pushes", "labels", and "pull requests"

Scroll down and Add Webhook!