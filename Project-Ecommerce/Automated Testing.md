# Portfolio – Automated Testing (NDA Protected)

> **Confidential – NDA Protected**  
> All sensitive URLs, credentials, and emails are anonymized for portfolio purposes.

---

## 1. Selenium – Automated Registration Test

**Overview:**  
Automated end-to-end test of user registration flow on a generic e-commerce website using **Python + Selenium WebDriver**.  

**Short Review:**  
- Opens sign-in modal  
- Fills in test credentials  
- Navigates registration form  
- Submits registration with dynamic email  
- Confirms registration success  
- Logs progress and handles errors  

### Test Steps
1. Open website and click **Sign In**.  
2. Fill in email/password fields for test account.  
3. Wait for modal and click **Sign Up here** link.  
4. Fill registration form:
   - First Name / Last Name  
   - Dynamic email (`user+timestamp@test.com`)  
   - Password / Confirm Password  
5. Submit form.  
6. Validate registration success via message or page redirection.  

### Test Case Table

| ID | Description | Expected Result | Status |
|----|-------------|----------------|--------|
| TC-REG-001 | Complete registration flow | Registration completes successfully, success message displayed | Pending |

### Checklist
- [ ] Open sign-in modal  
- [ ] Fill test credentials  
- [ ] Navigate to registration form  
- [ ] Fill all required fields  
- [ ] Submit form  
- [ ] Verify success  

### Code

```python
"""
Automated Registration Test – Selenium
Confidential – NDA Protected
"""

from selenium import webdriver
from selenium.webdriver.common.by import By
from selenium.webdriver.support.ui import WebDriverWait
from selenium.webdriver.support import expected_conditions as EC
import time

driver = webdriver.Chrome()
driver.maximize_window()
driver.get("https://example-anonymous-site.com")
wait = WebDriverWait(driver, 15)

try:
    print("Step 1: Open Sign In modal...")
    sign_in_btn = wait.until(
        EC.element_to_be_clickable(
            (By.XPATH, "//*[self::button or self::a or self::div or self::span][contains(text(),'Sign In')]")
        )
    )
    sign_in_btn.click()

    print("Step 2: Fill in email/password for test account...")
    email_input = wait.until(EC.presence_of_element_located((By.XPATH, "//input[@type='email']")))
    email_input.clear()
    email_input.send_keys("test.user@anonymous.com")

    password_input = driver.find_element(By.XPATH, "//input[@type='password']")
    password_input.clear()
    password_input.send_keys("Test@1234")

    print("Step 3: Navigate to registration form...")
    modal = wait.until(
        EC.visibility_of_element_located(
            (By.XPATH, "//*[contains(text(),'Welcome Back')]/ancestor::div[contains(@class,'modal')]")
        )
    )
    sign_up_link = modal.find_element(
        By.XPATH,
        ".//*[contains(translate(text(), 'ABCDEFGHIJKLMNOPQRSTUVWXYZ', 'abcdefghijklmnopqrstuvwxyz'), 'sign up here')]"
    )
    sign_up_link.click()

    print("Step 4: Fill registration fields...")
    first_name = wait.until(EC.presence_of_element_located((By.XPATH, "//input[@name='firstName']")))
    first_name.send_keys("Test")
    last_name = driver.find_element(By.XPATH, "//input[@name='lastName']")
    last_name.send_keys("User")
    email = driver.find_element(By.XPATH, "//input[@type='email']")
    email.send_keys(f"test.user+{int(time.time())}@test.com")
    password = driver.find_element(By.XPATH, "//input[@type='password']")
    password.send_keys("Test@1234")
    try:
        confirm_password = driver.find_element(By.XPATH, "//input[@name='confirmPassword']")
        confirm_password.send_keys("Test@1234")
    except:
        print("No confirm password field found (skipped).")

    print("Step 5: Submit registration form...")
    sign_up_btn = driver.find_element(By.XPATH, "//button[contains(text(),'Sign Up')]")
    sign_up_btn.click()

    print("Step 6: Validate registration success...")
    success = wait.until(lambda d: "Registration successful" in d.page_source or "dashboard" in d.current_url)
    if success:
        print("✅ Registration completed successfully!")
    else:
        print("⚠️ Registration test failed – success message not found.")

except Exception as ex:
    print(f"❌ Test failed: {ex}")

finally:
    driver.quit()
    print("Browser closed.")
