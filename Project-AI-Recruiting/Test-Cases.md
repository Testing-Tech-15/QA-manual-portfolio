Dashboard Data Isolation Between Different User Accounts

---

## General Information
- **Assigned To:** QA Engineer  
- **Date:** 26 November 2025  
- **Priority:** High  
- **Status:** Not Started  
- **Pass / Fail:** Fail  
- **Attachments:** None  

---

## Feature
Dashboard data isolation between different user accounts.

- Each user should see only their own data after logging in
- No data should be shared, leaked, or displayed between different accounts
- Only the user’s own chat history must be visible

---

## Scenario
Newly created account temporarily displays chat history belonging to another user.

---

## Description
(This scenario occurs when an existing account already has stored chat history.)

1. User is logged in with an **existing account**
2. This account already contains chat history
3. User logs out
4. User creates a **new account**
5. User logs in with the newly created account
6. User navigates to the **Dashboard / Chat page**

### Actual Result
- Chats belonging to the previous account are temporarily displayed
- After refreshing the page, chats from the old account disappear

### Expected Result
- Newly created account should display **empty chat history**
- No data from any other account should be visible at any time

---

## Test Data (Anonymized)
- **Old account email:** user_old_account@example.com  
- **New account email:** user_new_account@example.com  

---

## Given / When / Then

**Given**
- User is logged in with `user_old_account@example.com`
- Existing chat history is present

**When**
- User logs out
- User creates and logs in with `user_new_account@example.com`
- User opens Dashboard / Chat page

**Then**
- Chat history should be empty  
- Chats from the old account should NOT appear  

**But**
- Old chats appear temporarily  
- They disappear only after page refresh

---

## Related Bug
- Newly created account shows chats from an old account before refresh
