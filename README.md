# GTM Traffic Quality & Browser Audit Tag 🕵️‍♂️📊

This project provides a Custom HTML tag for **Google Tag Manager** designed to audit the quality of incoming web traffic. It identifies non-human traffic, privacy-focused sessions, and technical barriers that often skew marketing data.

## 🚀 Key Features

The script pushes a `browser_audit_complete` event to the `dataLayer` with the following parameters:

* **`is_bot`**: Detects search engines, scrapers, social media preview bots (Slack, WhatsApp, LinkedIn), and headless browsers.
* **`is_ad_blocker`**: Detects if the user has an active ad-blocker by testing a connection to common ad-serving scripts.
* **`is_incognito`**: Identifies if the user is in Private/Incognito mode (supporting Chrome, Firefox, Safari(default), and Brave).
* **`browser_name`**: Accurately identifies the browser engine (Chromium, Firefox, Safari, etc.).

## 💡 Why this is useful

1.  **Data Hygiene**: Filter out sophisticated bots that standard GA4 filters might miss to reveal your true conversion rate.
2.  **Attribution Accuracy**: Incognito users don't retain cookies. Knowing this helps set realistic expectations for retargeting and multi-touch attribution.
3.  **Technical Insights**: Understanding the percentage of users with ad-blockers helps explain discrepancies between media platform clicks and analytics sessions.

## 🛠️ Implementation

1.  **Download** the `traffic_quality_checker.json` file from this repository.
2.  **Import** the file into your GTM container (Admin -> Import Container).
3.  **Variables**: Ensure you create Data Layer Variables for `traffic_quality.is_bot`, `traffic_quality.is_ad_blocker`, and `traffic_quality.is_incognito`.
4.  **GA4**: Attach these variables as event parameters to your GA4 configuration or event tags.

## 📜 Credits & References

The core logic for cross-browser incognito detection is powered by the excellent work of **Joe12387**.
* **Original Library**: [detectIncognito](https://github.com/Joe12387/detectIncognito)
