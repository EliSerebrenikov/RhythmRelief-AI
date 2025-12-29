# 🎵 RhythmRelief AI: Advanced Technical Assistant

**An AI-powered technical support agent for a Spotify-clone app. Built with Dify (RAG) and Xano API to provide real-time account-based assistance and automated troubleshooting.**

---

## 🚀 Live Demo
**Experience the project here:** [SupportStream Live Demo](https://energetic-ocelot-trot.vercel.app/)

The bot is deployed as a persistent side-panel assistant within a high-fidelity Spotify-clone interface built with **DYAD**, allowing users to troubleshoot issues and manage their accounts without leaving the music player.

## 🧠 System Architecture
* **Orchestration:** [Dify.ai](https://dify.ai/)
* **Backend & API:** [Xano](https://www.xano.com/)
* **UI/UX:** Built with **DYAD** for a seamless, modern streaming interface.
* **Knowledge Base:** Multi-document RAG system utilizing proprietary app guides.

---

## 🛠 Features

### 1. Intelligent Knowledge Retrieval (RAG)
The agent leverages specialized documentation to resolve user queries:
* **Offline Listening:** Explains the 10,000-song limit per device and the "30-Day Rule" requiring users to go online once every month.
* **Audio Quality:** Guides users through setting levels from "Low" (24kbit/s) to "Very High" (320kbit/s for Premium).
* **New Features:** Supports users with the AI DJ, Smart Shuffle, and Jam real-time listening sessions.
* **Technical Troubleshooting:** Provides step-by-step guides for "Clean Reinstalls" on Android and iOS.

### 2. Personalized API Workflows (Xano)
The agent queries a **Xano Backend** to check the user's live account status:
* **Status Verification:** Checks if a user is `active`, `payment_failed`, or `suspended`.
* **Dynamic Logic:** If the Xano flow detects a `payment_failed` status, it triggers a recommendation variable to guide the user toward billing support.

---

## 🧪 Try It Out: Test Scenarios

To see the agent's integration with Xano and the Knowledge Base in action, you can use the following examples in the [Live Demo](https://energetic-ocelot-trot.vercel.app/):

### 1. Account Status Check (API Integration)
The agent can detect specific account issues by querying the Xano database.
* **Try this:** *"I'm having trouble with my account, can you check user2@test.com?"*
* **Expected Result:** The bot will identify that the subscription status is `payment_failed` due to a `card_declined` error and will recommend contacting customer support.

### 2. Technical Troubleshooting (RAG)
* **Try this:** *"How do I perform a clean reinstall on Android?"*
* **Expected Result:** The bot will provide the exact steps: Phone Settings > Apps > Spotify > Storage > Clear Data & Cache.

### 3. Feature Guidance
* **Try this:** *"What is the 30-day rule for downloads?"*
* **Expected Result:** It will clarify that you must go online at least once every 30 days to keep your downloads active.

---

## 📊 Technical Deep Dive: Xano Integration

**The Workflow Logic:**
1. **Input:** Agent sends user `email` to the Xano endpoint.
2. **Get Record:** Xano retrieves the specific row for that user.
3. **Conditional Check:** * If `subscription_status == payment_failed`, the flow updates the `recommendation` variable to "Contact customer support".
   * If user data is `null`, an error is thrown to prompt a login verification.
4. **Response:** Returns structured JSON to Dify to inform the agent's response.

---

## 📸 Project Gallery

### I. The Database (Xano)
![Xano Database](./xano_database.png)

### II. API Logic Stack
![Xano Flow](./xano_flow.png)

---

## ⚙️ Setup & Installation
1. **Dify:** Upload the documentation `.txt` files to the Knowledge section. Set RAG priority for Troubleshooting.
2. **Xano:** Import the schema and configure the API endpoint in Dify's "Tools".
3. **App Integration:** The interface is built using **DYAD** components and hosted on Vercel.

---

*This project was developed to demonstrate the power of combining No-code backends with LLM orchestration.*
