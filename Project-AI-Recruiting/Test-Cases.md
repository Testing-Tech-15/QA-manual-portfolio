# TC-001:Dashboard Data Isolation Between Different User Accounts

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


# TC-002: Confirmation Code Validation Missing During Sign Up

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
Sign Up confirmation code validation.

- The system must require users to enter the confirmation code before completing registration.  
- Users cannot bypass the confirmation code step.  
- Error message should be displayed if the code is missing.  

---

## Scenario
User completes Sign Up without entering the confirmation code.

---

## Description
(This scenario tests whether the Sign Up process enforces confirmation code validation.)

1. Open the Getbot.ai website  
2. Navigate to the **Sign Up** page  
3. Enter a mixed-language first name `"Testiინგ"` or normal first name `"testing"`  
4. Enter a mixed-language last name `"Testiინგ"` or normal last name `"testing"`  
5. Enter a valid email `"zenaishvilianzhela@gmail.com"`  
6. Enter a valid password (if required by the form)  
7. Click the **Sign Up** button  
8. Do **not** enter the confirmation code  
9. Click **Login / Sign In**  

### Actual Result
- System allows user to attempt login without entering confirmation code  
- No proper validation error or prompt displayed (system may proceed incorrectly)  

### Expected Result
- The system should display an error message: `"Please enter the confirmation code"`  
- Account should **not** be created  
- User remains on the confirmation page  

---

## Test Data (Anonymized)
- **Email:** zenaishvilianzhela@gmail.com  
- **First Name:** Testiინგ / testing  
- **Last Name:** Testiინგ / testing  
- **Password:** Valid (according to system requirements)  

---

## Given / When / Then

**Given**  
- I open the Getbot.ai website  
- I navigate to the Sign Up page  
- I enter first name, last name, email, and password  

**When**  
- I click the Sign Up button  
- I do **not** enter the confirmation code  
- I click Login / Sign In  

**Then**  
- The system should display an error: `"Please enter the confirmation code"`  
- The account should **not** be created  
- I remain on the confirmation page  

---

## Related Bug
- Sign Up process allows submission without confirmation code

