
# NDA Bug Reports – Mobile App

> **Confidential – NDA Protected**

---

## **Bug 1: App crashes when resending registration code**

**Device:** Galaxy S21 Ultra 5G  
**OS:** Android 13  
**App Version:** One UI 5.1  

### **Precondition**
- User is not registered.  
- Registration form is accessible.  

### **Steps to Reproduce**
1. Open the registration form.  
2. Enter all required information correctly (first name, last name, email, password, etc.).  
3. Tap **“Confirm and Continue”**.  
4. On the verification screen, tap **“Didn’t receive the code? Resend”**.  

### **Actual Result**
- Screen goes blank, no code input field is visible.  
- Full screen loses color and shows a loading spinner. App becomes unresponsive.  
- Only device back button allows returning to the registration form, but the issue persists.  
- Registration button remains active and verification email is sent again.  

### **Expected Result**
- Code input field should remain visible.  
- App should not freeze; registration process should continue normally.  

### **Test Case Table**

| ID | Description | Steps | Expected Result | Status |
|----|-------------|-------|----------------|--------|
| TC-REG-001 | Resend verification code | Steps 1-4 above | Code input visible, app responsive | Pending |

### **Test Scenario**
- Verify app behavior when user resends verification code during registration.  
- Validate that screen remains interactive and user can continue registration.  

### **Checklist**
- [ ] Open registration form.  
- [ ] Enter valid data.  
- [ ] Tap **Confirm and Continue**.  
- [ ] Tap **Resend Code**.  
- [ ] Verify code input field is visible.  
- [ ] Verify app does not freeze.  
- [ ] Verify registration can continue.  

### **Attachments**
- Screenshots/video demonstrating crash.  

---

## **Bug 2: Back button on Login screen not functional**

**Device:** Galaxy S21 Ultra 5G  
**OS:** Android 13  
**App Version:** One UI 5.1  

### **Precondition**
- User is not registered.  
- Login form is accessible.  

### **Steps to Reproduce**
1. Open the app.  
2. Navigate to **Login** screen.  
3. Enter email and password used for registration.  
4. Tap in-app **Back button**.  

### **Actual Result**
- App back button does not respond.  
- Using device back button may close Login screen or entire app.  
- App is effectively inaccessible until phone restart or app reinstall.  

### **Expected Result**
- App back button should work correctly.  
- User should return to previous or main screen.  
- App should not close unexpectedly.  

### **Test Case Table**

| ID | Description | Steps | Expected Result | Status |
|----|-------------|-------|----------------|--------|
| TC-LOGIN-001 | Back button functionality on Login screen | Steps 1-4 above | User returns to previous screen, app remains functional | Pending |



### **Attachments**
- Screenshots/video showing back button failure.  
