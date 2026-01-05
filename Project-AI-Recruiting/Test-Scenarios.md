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

