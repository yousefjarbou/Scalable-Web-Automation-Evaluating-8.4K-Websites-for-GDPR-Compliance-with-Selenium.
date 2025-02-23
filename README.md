# Scalable-Web-Automation-Evaluating-8.4K-Websites-for-GDPR-Compliance-with-Selenium.
### **Automating GDPR Compliance Audits Using 2GDPR by Selenium**
### **A Research Project in Collaboration with Princess Sumaya University for Technology (PSUT-January 2025)**  

## **Project Overview**  
This project investigates GDPR compliance across **educational websites**, focusing on their cookie consent mechanisms. We aim to **analyze, detect, and evaluate** whether these websites adhere to the **General Data Protection Regulation (GDPR)** by properly handling **cookie consent** and ensuring user privacy.

Our dataset originates from [**The Majestic Million**](https://majestic.com/reports/majestic-million?domain=&majesticMillionType=2&tld=paris&oq=&canUseDefault=), a publicly available list of the most visited websites globally. We specifically targeted **8,483 educational sector websites**, applying two approaches to test their compliance.


### **Project Contributors**  
- **Yousef Jarbou** – Automation,implementation,research & dataset selection.
- **Dr. Mu'awya Al-Dala'ien** – Supervision.

---
### **The methodology involved:**

1. **Extracting websites from the dataset**:
   - We started with a dataset of 8,483 educational URLs derived from "The Majestic Million."
   - The URLs were extracted and fed into the automation script.

2. **Automating interactions with 2GDPR using Selenium**:
   - Navigating to the **2GDPR** site.
   - Entering each URL into the website’s input field.
   - Simulating button clicks to initiate the compliance check.

3. **Extracting results from HTML content**:
   - Results were extracted by parsing the HTML of the results page.
   - We analyzed **icons and colors** on the screen:
     - **Green icons** indicated GDPR compliance.
     - **Red icons** flagged non-compliance.
   - A binary output (e.g., `[1, 0, 1, 1, 1]`) was generated for each website, representing the outcomes of the compliance checks.

### **Challenges Encountered**:
**1.Rate Limits & Blocking**:
     - The 2GDPR website imposed rate limits, which triggered CAPTCHA challenges and sometimes blocked requests entirely.
**2.Dynamic Content Loading**:
     - Results were not static and required repeated checks to confirm when the data was fully loaded.
**3.Scalability Issues**:
     - Processing a large number of URLs proved to be unsustainable due to dependencies on the third-party website.

**How We Tried to Overcome These Challenges**:
   - **A.Mimicking Human Behavior**:
     - Introduced **randomized delays** between requests (e.g., 0.5 to 2 seconds).
     - Added **B.periodic longer pauses** after every 20 URLs to reduce detection.
   - **C.Improved XPath Selection**:
     - Used alternative XPath methods to locate elements more reliably.
   - **D.Retry Mechanisms**:
     - Implemented logic to retry failed requests due to timeouts or rate limits.
   - **E.Dynamic Page Detection**:
     - Added waiting mechanisms to detect when the dynamic content was fully loaded before extracting results.
   - **F.Splitting Data into Batches**:
     - To overcome rate limits and blocking, we **split the dataset into smaller batches** and distributed them across **multiple devices and networks**:
       - Batches were run on different IP ranges (e.g., **home Wi-Fi, university Wi-Fi, mobile hotspot**), minimizing detection by the website.
---

## **Final Results**
**Partial Success (1,200 Websites Completed)**:
   - Despite the challenges, we successfully processed **1,200 URLs out of the 8,483** in the dataset.
   - The results included:
     - **Acceptance Status**: Whether the website passed or failed compliance checks.
     - **Green Icon Count**: The number of compliance indicators passed.
     - **Binary Check Results**: A 5-element binary representation of the checks performed.

**Limitations**:
   - The reliance on **2GDPR** as a third-party tool limited scalability and introduced potential reliability risks.
   - The dynamic loading and frequent rate-limiting added significant delays to processing.

**solution**:
While this approach demonstrated that automation could extract GDPR compliance data, it became evident that relying on a third-party tool like 2GDPR wasn’t sustainable for a larger-scale dataset. This realization led us to develop our custom GDPR compliance checker tool (add link) which offered greater control, flexibility, and scalability.

---

