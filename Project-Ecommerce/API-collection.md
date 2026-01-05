"""
Automated Registration Test – Selenium
Confidential – NDA Protected

This script performs an automated end-to-end test of a user registration flow
on a generic e-commerce website. All URLs, emails, and credentials are anonymized
for portfolio purposes.
"""

from selenium import webdriver
from selenium.webdriver.common.by import By
from selenium.webdriver.support.ui import WebDriverWait
from selenium.webdriver.support import expected_conditions as EC
import time

# Initialize WebDriver
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
