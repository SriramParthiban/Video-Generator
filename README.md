# 🎥 Automated Video Generation Workflow (n8n + OpenAI + Veo3)

This repository contains an **n8n workflow** that automatically generates **short-form video ideas and cinematic AI videos** for TikTok/Instagram-style content.  
It is designed to help international students (or similar niches) create **personal branding and career-growth content** effortlessly.

---

## 🚀 What It Does

1. **Scheduled Trigger**  
   - Runs daily (or at a set time) to start the workflow automatically.

2. **Generate Content Ideas**  
   - Uses OpenAI (GPT models) to brainstorm **relatable, viral short-form content ideas**.  
   - Output includes:  
     - `caption` (short, catchy text with hashtags)  
     - `idea` (summary of video action/story)  
     - `environment` (set/location for video)  
     - `status` (default: `to create`)

3. **Video Prompt Creation**  
   - Transforms the idea into a **cinematic Veo3 prompt**.  
   - Adds details such as:  
     - scene description  
     - lighting & mood  
     - camera movement  
     - realistic atmosphere

4. **Save to Google Sheets**  
   - Stores each generated idea (caption, idea, environment, status) in a Google Sheet for tracking.

5. **AI Video Generation (Veo3 via Fal AI)**  
   - Sends the cinematic prompt to Veo3 API.  
   - Waits for 10 minutes, then fetches the generated video.

6. **Update Google Sheets**  
   - Appends the generated video link to the same sheet, alongside its idea & caption.

---

## 🛠️ Tech Stack

- **n8n** (workflow automation)  
- **OpenAI GPT (gpt-4o-mini)** for idea generation & prompt building  
- **Fal AI (Veo3)** for cinematic video generation  
- **Google Sheets** for tracking content ideas, captions, and video URLs  

---

## 📂 Workflow Overview

- `Schedule Trigger` → `Generate a Idea/Content` → `Video prompt` → `Save to Sheets` → `Create Video` → `Wait` → `Get Video` → `Update Sheets`

---

## 🔑 Requirements

- OpenAI API Key  
- Fal AI API Key (for Veo3)  
- Google Sheets API credentials  
- n8n (self-hosted or cloud)  

---

## ⚡ How to Use

1. Import the JSON workflow (`Video Generation.json`) into your **n8n** instance.  
2. Configure credentials for:  
   - OpenAI  
   - Fal AI (HTTP Header Auth)  
   - Google Sheets  
3. Adjust the schedule time as needed.  
4. Run the workflow → Check your Google Sheet for generated ideas & video links.  

---

## 📌 Example Output in Google Sheets

| Ideas                           | Captions                                              | Environment              | Status     | URL       |
|---------------------------------|-------------------------------------------------------|--------------------------|------------|-----------|
| "Portfolio breakthrough moment" | "When your portfolio finally lands you an interview 😭🙌 #jobready" | Co-working space w/ laptop | to create  | [video]   |

---

## 🎯 Use Case

Perfect for:  
- Content creators targeting **international students**  
- Personal branding & career-focused TikToks/Instagram Reels  
- Automating **daily content ideation + video generation** pipeline

---

## 📜 License

This project is licensed under the MIT License. Feel free to modify and use for your own content workflows.

---
