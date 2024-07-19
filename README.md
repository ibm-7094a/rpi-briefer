# **Rpi-Briefer**

###### A Simple, Scheduled Briefing Application for Your Raspberry Pi!

## Overview

**Rpi-Briefer** is a lightweight Python application designed to provide you with a daily briefing. This tool gathers **weather forecasts** and **news headlines** to keep you informed without the hassle of searching for information yourself. 

## **Purpose**

Rpi-Briefer was created with one goal in mind: to send *you* a summary of important information about your day so that *you* don't have to bother looking it up! The application uses **free APIs** to fetch relevant data, which are included in the code.

## **How It Works**

The application performs the following steps to generate and send your daily briefing:

1. **Fetch Weather Forecast:**
   - The `get_weather` function retrieves the weather forecast for the next 3 days.
   - It uses the [WeatherAPI](https://www.weatherapi.com/) to get the weather data.
   - The forecast includes:
     - **Date**
     - **Maximum Temperature (°F)**
     - **Minimum Temperature (°F)**
     - **Condition** (e.g., Sunny, Rainy)

2. **Fetch News Headlines:**
   - The `get_news` function retrieves the top 3 news headlines.
   - It uses the [NewsAPI](https://newsapi.org/) to get the latest headlines.
   - The headlines include:
     - **Title of the Article**

3. **Send Daily Briefing via Email:**
   - The `send_email` function sends an email with the weather forecast and news headlines.
   - It uses **Gmail's SMTP server** for sending the email.

   **Security Tip:** Instead of using your regular Gmail password, consider setting up an [App Password](https://support.google.com/accounts/answer/185833?hl=en) for enhanced security. App passwords are a one-time passcode that can be used for this specific application, reducing the risk of your main password being compromised.

## **Installation and Usage**

To set up and use Rpi-Briefer, follow these steps:

1. **Clone the Repository:**
   ```bash
   git clone https://github.com/ibm-7094a/rpi-briefer
   cd rpi-briefer
   ```

2. **Install Dependencies:**
   Ensure you have the required Python packages installed:
   ```bash
   pip install requests
   ```

3. **Update the Code:**
   - Replace the placeholders for `weather_api_key`, `news_api_key`, `sender_email`, and `sender_password` with your actual API keys and email credentials.
   - Set the `receiver_email` to the email address where you want to receive the daily briefing.

4. **Run the Application:**
   Execute the script to send your daily briefing:
   ```bash
   python rpi-briefer.py
   ```

## **Configuration**

- **API Keys:**
  - Obtain your API keys from [WeatherAPI](https://www.weatherapi.com/) and [NewsAPI](https://newsapi.org/).

- **Email Credentials:**
  - Use your Gmail credentials to send the email. For security, use an [App Password](https://support.google.com/accounts/answer/185833?hl=en) instead of your regular Gmail password.
 
- **Schedule Command Execution:**
  - On UNIX-based systems (what else do you run on your pi?) use the built-in CRON command for scheduling. Learn about it [here](https://linuxconfig.org/using-cron-scheduler-on-linux-systems), it's useful!

