# 🎬 CreatorFlow — TikTok Creator Publishing Tool

CreatorFlow is a creator publishing tool designed to help TikTok creators prepare and share their original video content.

The application allows users to preview their content, configure privacy settings, control interaction permissions, and manually confirm posts before sharing them to their TikTok profile.

> ⚠️ **CreatorFlow does not automate posting without user interaction.**
> Users must manually review and confirm each post before publishing.

---

## 🚀 Quick Start

### First time (installation)
```
Double-click: setup.bat
```

### Every other time
```
Double-click: creatorflow.bat
```

Opens automatically at: **http://localhost:8501**

---

## 📁 Structure

```
CreatorFlow/
├── app.py              ← Streamlit interface
├── queue.json          ← Pending posts
├── config.json         ← Credentials and config
├── videos/             ← Videos folder
├── creatorflow.bat     ← Launch app
├── setup.bat           ← Initial setup
└── requirements.txt    ← Python dependencies
```

---

## ⚙️ Configure TikTok API

1. Go to [developers.tiktok.com](https://developers.tiktok.com)
2. Create an app → Product → **Content Posting API**
3. Go to Settings and fill in:
   - **Client Key**
   - **Client Secret**
   - **Access Token** (with scope `video.upload`)
   - **Open ID**

> **Without credentials**, the app runs in **simulation mode** — great for testing the flow.

---

## 📖 How to use

1. Open `creatorflow.bat`
2. Go to **➕ New Post**
3. Upload your video (MP4, MOV, etc.)
4. Write your caption and hashtags
5. Edit the title and configure privacy settings
6. Set interaction controls (comments, duet, stitch)
7. **Review everything** in the preview panel
8. Click **✅ Confirm & Publish** to post

> Every post requires explicit user confirmation before anything is sent to TikTok.

---

## 🔑 queue.json — Post structure

```json
{
  "id": "abc12345",
  "video_path": "C:\\...\\videos\\my_video.mp4",
  "caption": "Post caption",
  "hashtags": "#fyp #viral",
  "privacy": "PUBLIC_TO_EVERYONE",
  "comments_enabled": true,
  "duet_enabled": false,
  "stitch_enabled": false,
  "status": "pending_confirmation",
  "created_at": "2025-01-14T10:30:00",
  "posted_at": null,
  "error": null
}
```

**Possible statuses:** `draft` → `pending_confirmation` → `posted` / `failed`

---

## 🛠️ Requirements

- Python 3.10+
- Windows 10/11
- Internet connection (for TikTok API)

---

## 🔒 Privacy & Compliance

CreatorFlow is designed for **manual, user-initiated publishing only**.

- No content is posted without the creator's explicit confirmation
- No background processes publish on the user's behalf
- All posts are reviewed by the user before submission to TikTok
- CreatorFlow acts as a configuration and preview interface, not an automation bot
- CreatorFlow does not add watermarks, logos, promotional overlays, or modify the creator's content in any way before publishing to TikTok
- The application retrieves creator information from the TikTok API and displays the creator's nickname so users clearly know which TikTok account the content will be published to
