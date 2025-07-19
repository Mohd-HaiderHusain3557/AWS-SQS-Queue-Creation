# ✅ Creating an Amazon SQS Queue and Subscribing It to an SNS Topic

This guide explains how to create an Amazon SQS queue and subscribe it to an SNS topic using the **Amazon SQS protocol**.

---

## 🔹 Step 1: Sign in to AWS Console *(not in screenshot)*

- Go to [https://console.aws.amazon.com/](https://console.aws.amazon.com/)
- Login using your AWS credentials (or sign up if you don't have an account).

---

## 🔹 Step 2: Navigate to Amazon SQS

- From the AWS Console Home, either:
  - Click on **Simple Queue Service** under “Recently visited”
  - Or, search for **SQS** in the top search bar and select **Simple Queue Service**

---

## 🔹 Step 3: Create a New Queue

- Click **Create queue**
- Choose a queue type:
  - **Standard** – at-least-once delivery, unordered
  - **FIFO** – exactly-once, ordered delivery
- Enter a queue name (e.g., `Queue1`)
- Configure additional settings:
  - Retention: 1 minute  
  - Max message size: 256 KB  
  - (as shown in screenshot)
- Scroll down and click **Create queue**

---

## 🔹 Step 4: Confirm Queue Creation

- You’ll see the newly created queue listed (e.g., `Queue1`)
- Click on the queue to view its details or configure further actions

---

## 🔹 Step 5: Create an SNS Topic *(if not already created)*

- Go to **Simple Notification Service** in AWS Console
- Click **Create topic**
- Choose a type (Standard or FIFO)
- Enter a name and click **Create**
- Note down the **Topic ARN**

---

## 🔹 Step 6: Subscribe the SQS Queue to the SNS Topic

- Go to **SNS Dashboard** → **Subscriptions** → **Create subscription**
- Choose your Topic ARN
- Set **Protocol** to **Amazon SQS**
- For **Endpoint**, paste the **SQS Queue ARN** (from SQS queue details)
- Click **Create subscription**

---

## ✅ Done!

Now, any message published to the SNS topic will be automatically delivered to the subscribed SQS queue.
