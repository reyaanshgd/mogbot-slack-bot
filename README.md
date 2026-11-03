# mogbot-slack-bot
A slack bot, that will make your message look cool compared to the average slack message (mog).
## Mogbot includes the following commands:
- /mogbot-ping - This command pings mogbot, to check mogbot's latency
- /mogbot-wordle - This command pulls out the answer to the daily wordle
- /mogbot-help - lists some of mogbot's commands
- /mogbot-joke - pulls out a simple joke
- /mogbot-catfact - pulls out a fact about cats!
## 🔗 Quick Links & Live Demo

* **Add to Slack (Install Link):** [https://slack.com/oauth/v2/authorize?client_id=2210535565.12347000660290&scope=commands](https://slack.com/oauth/v2/authorize?client_id=2210535565.12347000660290&scope=commands)
* **Watch Mogbot Live (Test Channel):** Join the test channel on the Slack workspace to see Mogbot run live:  
   **[#mogbot-testing](https://app.slack.com/client/E09V59WQY1E/C0CDKKKG4DV)** *(or join your workspace's `#mogbot-testing` channel)*

---

## How to Install Mogbot to Your Slack Workspace

If you just want to use Mogbot in your Slack workspace without hosting code:

1. Click the **[Add to Slack Link](https://slack.com/oauth/v2/authorize?client_id=2210535565.12347000660290&scope=commands)**.
2. Select the Slack workspace where you want to add Mogbot.
3. Review the requested permissions (`commands`) and click **Allow**.
4. Open your Slack app, go to any channel, and type `/invite @Mogbot` to add the bot.
5. Type `/mogbot-help` to start using commands!

---

## 🛠️ How to Self-Host / Run Mogbot Yourself

If you want to run your own instance of Mogbot from source code, follow these steps:

### 1. Prerequisites
Make sure you have installed:
* **Node.js** (v16.x or higher)
* **npm** (comes with Node.js)
* A **Slack Workspace** where you have permission to install apps

---

### 2. Create Your Own Slack App
1. Go to the **Slack API Dashboard: https://api.slack.com/apps** and click **Create New App** > **From an app manifest** (or **From scratch**).
2. **Enable Socket Mode:**
   * Go to **Settings** > **Socket Mode** in the left sidebar.
   * Toggle **Enable Socket Mode** to **ON**.
   * Generate an **App-Level Token** with the `connections:write` scope. Save this token (`xapp-...`).
3. **Configure Scopes:**
   * Go to **Features** > **OAuth & Permissions**.
   * Under **Bot Token Scopes**, add the `commands` scope.
4. **Add Slash Commands:**
   * Go to **Features** > **Slash Commands** and create:
     * `/mogbot-help`
     * `/mogbot-ping`
     * `/mogbot-catfact`
     * `/mogbot-joke`
     * `/mogbot-wordle`
5. **Install App to Workspace:**
   * Go to **Settings** > **Install App** and click **Install to Workspace**.
   * Copy the **Bot User OAuth Token** (`xoxb-...`).

---

### 3. Clone Repository & Install Dependencies

```bash
# Clone the repository
git clone https://github.com/reyaanshgd/mogbot-slack-bot.git
cd mogbot

# Install dependencies (@slack/bolt, axios, dotenv)
npm install
```
---

### Step 4: Set Up Environment Variables
Create a .env file in the root directory:
```bash
touch .env
```

Add your credentials inside .env:
```bash
SLACK_BOT_TOKEN=xoxb-your-bot-user-oauth-token
SLACK_APP_TOKEN=xapp-your-app-level-token
```
---

### 5. Start the Bot
Run Mogbot using Node.js:

```bash
node index.js
```

When connected, you'll see:

Bot is running!
