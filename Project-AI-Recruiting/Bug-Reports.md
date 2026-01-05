 BR-001: Newly Created Account Shows Chats from an Old Account Before Page Refresh

---

## General Information
- **Priority:** High  
- **Date:** 26 November 2025, 13:59  
- **User Type:** Student  
- **Reproducibility:** 50%  
- **Status:** Not Started  
- **Attachments:**  Jam recording (screen recording demonstrating the issue)
 

---

## Environment
- **Device:** Desktop  
- **Browser:** Opera 124.0.5705.42  

---

## Description
When a new account is created and the user logs in, chats from a previously used account temporarily appear on the dashboard of the new account.  
After refreshing the page, these chats disappear.

This behavior indicates a **session management / data isolation issue**, which may lead to **privacy and security concerns**.

---

## Test Data (Anonymized)
- **Old account email:** user_old_account@example.com (contains existing chats)  
- **New account email:** user_new_account@example.com (no chat history)  
- User is logged out before creating the new account  

---

## Steps to Reproduce
1. Log in with the existing account (`user_old_account@example.com`)
2. Ensure there is active chat history in this account
3. Log out from the account
4. Create a new account using `user_new_account@example.com`
5. Log in with the new account
6. Navigate to the **Dashboard / Chat page**

---

## Actual Result
- Chats from the old account are temporarily displayed in the new account
- After refreshing the page, the old chats disappear

---

## Expected Result
- The new account should display only its own chat history
- No chats from the old account should appear at any time




# BR-002: "Install Now" Button Redirects to Wrong Chrome Web Store Page

---

## General Information
- **Priority:** High  
- **Date:** 2 January 2026  
- **User Type:** Student  
- **Reproducibility:** 100%  
- **Status:** Not Started  
- **Attachments:** Screen recording demonstrating the issue  

---

## Environment
- **Device:** Desktop  
- **Browser:** Chrome 142.0.7444.177  

---

## Description
Clicking the **"Install Now"** button for the extension **GetBotAI: AI Plagiarism & GPT-4o & Gemini Pro 1.5 & Claude 3.5 Sonnet** redirects the user to a **different, unrelated Chrome Web Store page**:  
**GetbotAI: Chat with all AI: Gemini, GPT-5, Claude, Veo, DeepSeek & More**  

This behavior indicates a **misconfigured link**, which may lead to **user confusion and trust issues**.

---

## Test Data (Anonymized)
- User is on the **Getbot.ai homepage**  
- Extension section is fully loaded  
- Internet connection is stable  
- Chrome browser installed and functioning

---

## Steps to Reproduce
1. Open the **Getbot.ai homepage**  
2. Scroll to the **extensions section**  
3. Locate the **AI Detector / Plagiarism Check** extension  
4. Click **Install Now**  

---

## Actual Result
- User is redirected to an **unrelated Chrome Web Store page**:  
  *GetbotAI: Chat with all AI: Gemini, GPT-5, Claude, Veo, DeepSeek & More*  

---

## Expected Result
- User should be redirected to the **official Chrome Web Store page** for:  
  *GetBotAI: AI Plagiarism & GPT-4o & Gemini Pro 1.5 & Claude 3.5 Sonnet*



