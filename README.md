# Customer Feedback Analysis Automation

This project is an **automated workflow** built in **n8n** that processes customer feedback submitted via Google Forms, analyzes the sentiment using OpenAI, and routes the feedback to appropriate Slack channels based on urgency and sentiment.

---

## Workflow Overview

### 1. Google Sheets Trigger Node
- Connected to the **Google Forms Customer Feedback Form**.
- Triggers automatically when a customer/client submits a form.

### 2. Edit Fields Node
- Renames and organizes the form variables for **better readability**.

### 3. OpenAI Node
- Analyzes the feedback text submitted by the customer.
- Performs the following tasks:
  - Summarizes the **intent/sentiment** of the feedback: *Positive*, *Neutral*, or *Negative*.
  - Determines if the feedback is **urgent**.

### 4. Function Node
- Converts the OpenAI output into **structured JSON format** for further processing.

### 5. If Node
- Routes the feedback based on sentiment:
  - **Negative feedback:** sends a message to a designated Slack channel for immediate attention.
  - **Positive/Neutral feedback:** sends the feedback to a general Slack channel.

### 6. Slack Nodes
- Sends the processed feedback messages to the appropriate **Slack channels** for team communication and action.

---

## Features
- Automated sentiment analysis of customer feedback.
- Urgent negative feedback is highlighted for faster response.
- Seamless integration between Google Forms, OpenAI, and Slack.
- Fully customizable workflow for different feedback channels or priorities.

---

## How It Works
1. Customer submits a feedback form via Google Forms.
2. Google Sheets triggers the workflow.
3. Fields are edited for readability.
4. OpenAI analyzes the feedback and outputs sentiment and urgency.
5. Function Node converts the output to JSON.
6. If Node evaluates sentiment: negative feedback is sent to an urgent Slack channel; others are sent to a general channel.
7. Slack nodes post the messages to the team for action.

---

## Requirements
- n8n account (Cloud or self-hosted)
- Google Sheets & Google Forms integration
- OpenAI API key
- Slack workspace with channels configured for notifications

**Negative Feedback:**  
