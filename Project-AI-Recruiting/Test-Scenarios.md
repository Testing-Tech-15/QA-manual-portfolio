# TS-001: Dashboard Data Isolation

## Feature
Ensure data isolation between different user accounts.

## Scenario
Newly created account temporarily displays content from another user.

## Precondition
- Existing account with data is available  
- Test user can create a new account  

## Steps
1. Log in with an existing account  
2. Verify active content is present  
3. Log out  
4. Create and log in with a new account  
5. Open the Dashboard page  

## Expected Result
- Only the new account’s content is visible  
- No data from other users appears  

## Test Data (Anonymized)
- Old account: user_old_account@example.com  
- New account: user_new_account@example.com



# TS-002: Extension Install Redirect

## Feature
Ensure the "Install Now" button redirects to the correct Chrome Web Store page.

## Scenario
Clicking the extension install button leads to a wrong page.

## Precondition
- User on portal homepage  
- Extension section fully loaded  

## Steps
1. Click "AI Detector / Plagiarism Check"  
2. Click "Install Now"  

## Expected Result
- Redirect goes to official Chrome Web Store page for the intended extension  

## Test Data (Anonymized)
- Extension: AI Detector / Plagiarism Check  
- User: Authorized test user

