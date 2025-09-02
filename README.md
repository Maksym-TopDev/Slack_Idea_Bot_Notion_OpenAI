# Slack Idea Submission Bot (Notion Integration)
## Overview
- This Slack bot summarizes and categorizes submitted ideas via the OpenAI API and organizes them in a Notion database.

## Example of Operation

https://github.com/user-attachments/assets/f61f9f13-5d09-4693-a22e-6bdba88d8614

## Installation Instructions
### 1. Create a Slack App.
---
- Configure your Slack app based on the [official documentation](https://tools.slack.dev/bolt-python/ja-jp/getting-started/).
- Select "From a manifest" and build the app based on the [manifest.yaml](manifest.yaml).

> *Please set the request_url in [manifest.yaml](manifest.yaml) to your own URL. If you're trying it locally, we recommend using a local hosting service such as [ngrok](https://ngrok.com/).

> *If you're having trouble setting the URL, try the final step and then set the URL again.

- Create a `.env` file using [.env.sample](env/.env.sample) as a reference.
- Obtain the Signing Secret from Basic Information in the Slack App admin panel and the Bot User OAuth Token from OAuth & Permissions, and insert these values ​​into the `SLACK_SIGNING_SECRET` and `SLACK_BOT_TOKEN` fields in the `.env` file.

### 2. Set up the Notion API.
---
- Obtain your Notion API integration key and the database ID where you want to store your idea data.
[Reference page here. ](https://qiita.com/ulxsth/items/3434471ac91f8fa311cf)
- Insert the values ​​for `NOTION_SECRET` and `NOTION_DATABASE_ID` in the `.env` file.

### 3. Prepare other environment variables
---
- Insert your OpenAI API key into `OPENAI_API_KEY` in the `.env` file.
- Insert the ID of the Slack channel where you want to share ideas into `TARGET_CHANNEL` in the `.env` file. ([How to obtain a Slack channel ID](https://qiita.com/YumaInaura/items/0c4f4adb33eb21032c08))

### 4. Environment Setup
---
- Create a virtual environment
```
python -m venv venv
```
- Activate the virtual environment
```
source venv/bin/activate
```
- Install required libraries
```
pip install -r requirements.txt
```
### 5. Execution
---
```
python app.py
```
- By default, it will be executed on localhost port 3000. Use this URL to publicly publish it using a local hosting service such as [ngrok](https://ngrok.com/).
