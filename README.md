# Scalable-Web-Automation-Evaluating-8.4K-Websites-for-GDPR-Compliance-with-Selenium.
# **Automating GDPR Compliance Audits Using 2GDPR by Selenium**
### **A Research Project in Collaboration with Princess Sumaya University for Technology (PSUT-January 2025)**  

## **Project Overview**  
This project investigates GDPR compliance across **educational websites**, focusing on their cookie consent mechanisms. We aim to **analyze, detect, and evaluate** whether these websites adhere to the **General Data Protection Regulation (GDPR)** by properly handling **cookie consent** and ensuring user privacy.

Our dataset originates from [**The Majestic Million**](https://majestic.com/reports/majestic-million?domain=&majesticMillionType=2&tld=paris&oq=&canUseDefault=), a publicly available list of the most visited websites globally. We specifically targeted **8,483 educational sector websites**, applying two approaches to test their compliance.


### **Project Contributors**  
- **Sana Mourad & Aya Aljabali** – Research & dataset selection.
- **Yousef Jarbou** – Automation & implementation.
- **Dr. Mu'awya Al-Dala'ien** – Supervision.

---

## **How 2GDPR Scraper Works**
1. **Extracts educational URLs from the dataset**.
2. **Uses Selenium to automate interactions with 2GDPR**.
3. **Analyzes the results by extracting HTML elements and color-coded indicators**.
4. **Stores results in a structured CSV format**.

---

## **Challenges & How We Overcame Them**
### **1. Website Blocking & Rate Limits**
- The **2GDPR website detected and blocked automated requests** after multiple queries.
- **Solution:** 
  - Introduced **randomized delays** between requests (0.5 to 2 seconds).
  - Implemented **longer pauses every 20 queries** to mimic human behavior.
  - Ran **multiple devices on separate networks** (e.g., **home Wi-Fi, university Wi-Fi, mobile hotspot**) to distribute the workload and reduce detection.

### **2. Dynamic Content Loading**
- The compliance check results took time to load dynamically.
- **Solution:**  
  - Used **explicit wait conditions** to ensure the page fully loaded before extracting data.

### **3. Partial Success & Scalability Issues**
- Despite optimizations, we **only processed 1,200 out of 8,483 websites** due to rate limits.
- **This limitation led us to develop a second approach**, removing dependence on external tools.

---

## **Final Results**
- **1,200 educational websites analyzed.**
- **Extracted GDPR compliance indicators using visual analysis of 2GDPR results.**
- **Partial success due to rate limits and automation detection.**
- **Led to the development of Approach 2 for a more scalable solution.**

---

## **How to Run**
```bash
pip install selenium pandas webdriver-manager beautifulsoup4
python 2gdpr_scraper.py
