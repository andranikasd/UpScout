# UpScout

**UpScout** is a Telegram bot that periodically checks for new jobs posted on Upwork in a specific category (or multiple categories) and sends relevant notifications to a Telegram channel. The idea is to simplify the process of staying up-to-date on new freelance gigs.

## Workflow Description

1. **Schedule API Calls**  
   - Every `n` minutes, the bot uses the Upwork API to look for new job postings in the selected category (or categories).
2. **Compare Job Postings**  
   - The bot compares the newly fetched job postings with previously retrieved ones to identify new or unseen listings.
3. **Notify via Telegram**  
   - If new jobs are found, the bot sends notifications to the designated Telegram channel with:
     - Job Title  
     - Brief Description  
     - Direct Link to Apply (on Upwork)

## How It Works

1. **Bot Initialization**  
   - Configure environment variables and API tokens (Upwork and Telegram).
   - Run the bot (e.g., `python src/main.py`).
2. **Upwork Job Retrieval**  
   - The bot periodically calls the Upwork API using the credentials you provided.
3. **Data Handling**  
   - Compare newly fetched job data with a local or remote store (e.g., a database or file) to see if it’s a duplicate.
4. **Telegram Notification**  
   - If new jobs are detected, the bot sends messages to the specified Telegram channel or group.

## Getting Started

1. **Clone the repository**  
   ```bash
   git clone https://github.com/andranikasd/UpScout.git
   cd UpScout
   ```

2. **Install dependencies**  
   ```bash
   pip install -r requirements.txt
   ```

3. **Set Up Environment Variables**  
   Create a `.env` file in the project root or set these variables in your deployment environment:
   - `UPWORK_API_KEY`  
   - `UPWORK_SECRET_KEY`  
   - `TELEGRAM_BOT_TOKEN`  
   - `TELEGRAM_CHAT_ID`  
   - `PREFERRED_JOB_CATEGORY` (optional if you have multiple categories)
   - `CRON_SCHEDULE`

4. **Run the Bot Locally**  
   ```bash
   python3 src/main.py
   ```

5. **Deploy to Kubernetes**  
   - Build a Docker image for the bot and push it to your registry.
   - Expose or schedule the bot as needed.

## TODO List

- [ ] **Bot Basic Setup**  
  - Initialize the bot’s structure (code layout, main logic).  
  - Manage API keys, credentials, and environment variables.

- [ ] **Cron Basic Setup**  
  - Configure periodic or scheduled tasks (e.g., 5-minute intervals).  
  - Decide on and implement a scheduling mechanism (e.g., Python scheduling, CronJobs, etc.).

- [ ] **Upwork Integration**  
  - Establish secure communication with Upwork’s API.  
  - Handle fetching, filtering, and parsing job data.

- [ ] **CI/CD**  
  - Automate testing, linting, and deployment steps.  
  - Integrate with a service (e.g., GitHub Actions, Jenkins, etc.) for continuous integration.

- [ ] **Dockerization**  
  - Build a Docker image for the bot.  
  - Ensure best practices (small base image, multi-stage builds if needed).

- [ ] **Kubernetes Deployment Configuration**  
  - Create Deployment and/or CronJob manifests for the bot.  
  - Use ConfigMaps/Secrets for storing environment variables.

- [ ] **ECS Deployment Configuration**  
  - Adapt container settings for AWS ECS (e.g., Fargate, EC2).  
  - Manage scaling, logging, and environment variables in ECS.
## Contributing

1. Fork this repository.
2. Create a feature branch: `git checkout -b feature/new-awesome-feature`.
3. Commit your changes: `git commit -m 'Add a new awesome feature'`.
4. Push to the branch: `git push origin feature/new-awesome-feature`.
5. Create a Pull Request.

---

Feel free to modify this `README.md` to suit the specific details of your project!