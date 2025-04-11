# 📬 Smart Marketing & Sentiment Analysis Platform

A Django-based platform for automated email campaigns using Excel uploads and real-time sentiment analysis from social media platforms like Facebook, Twitter, YouTube, Instagram, Reddit, and TikTok.

## 🚀 Features

### ✅ User Authentication
- Secure login/logout functionality.
- JWT or session-based authentication.
- Profile management with OAuth token setup for social media.

### 📂 Excel Upload & Email Automation
- Upload `.xlsx` files containing:
  - `email`, `category`, `frequency`, and other custom fields.
- Email sending logic based on `frequency` and `category`.
- Emails are sent asynchronously using **Celery** and **Redis/Kafka**.

### ✉️ Dynamic Email Templates
- Upload multiple email templates based on **category**.
- Email templates can include custom variables such as `{{ name }}`, `{{ address }}`, etc.
- System automatically validates that all required variables in the template exist in the uploaded Excel sheet.
- Templates are stored per user, with live previews and edit options.

### ⚙️ Asynchronous Email Engine
- Background email processing using **Celery** and **Celery Beat**.
- Track:
  - Emails sent
  - Success/failure
  - Delivery timestamps
- Future support for open/click/bounce tracking (via SendGrid/Mailgun webhooks).

### 🔍 Hashtag-Based Social Media Sentiment Analysis
- Users can enter hashtags for analysis.
- Choose platforms:
  - **Facebook**
  - **Twitter**
  - **Instagram**
  - **Reddit**
  - **TikTok**
  - **YouTube**
- Fetch related posts/comments using OAuth2 APIs.
- Perform sentiment analysis using **HuggingFace Transformers** or **TextBlob**.
- NLP-based classification (Positive, Neutral, Negative + Emotions)

### 📊 Rich Reporting Dashboard
- Email campaign report (sent, success, failed, schedule tracking).
- Sentiment analysis reports:
  - Bar and line charts (trend over time)
  - Platform-wise comparison
  - Word clouds
  - Historical vs. current analysis
- Export reports as **PDF/CSV**.

### 🔌 Modular Plugin System for Social Media
- Enable/disable social platform integration per user.
- OAuth2-based platform modules.
- Extensible architecture for adding more platforms.

---

## 🏗️ Tech Stack

| Layer          | Technology                         |
|----------------|------------------------------------|
| Backend        | Django 5.x, Django REST Framework  |
| Task Queue     | Celery + Redis or Kafka            |
| Scheduler      | Celery Beat                        |
| Database       | PostgreSQL                         |
| Frontend       | Django Templates / Chart.js        |
| Containerization | Docker + Docker Compose           |
| NLP/ML         | TextBlob, NLTK, HuggingFace        |
| Email Services | SMTP, SendGrid, Mailgun            |
| Reporting      | Plotly, Chart.js, Matplotlib       |

---

## 📂 Project Structure (Simplified)
