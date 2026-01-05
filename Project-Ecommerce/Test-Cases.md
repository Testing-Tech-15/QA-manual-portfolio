# TC-001: Language Switch with Unsaved Changes

## Description
Verify language switching behavior when changes are made in a category form but are not saved.

---

## Pre-conditions
- User is logged in to the **Admin Panel**
- A category edit page is open (e.g. *Children's Clothing* category)
- One or more fields have been modified (e.g. **Name (Georgian)**)
- The **Save changes** button has NOT been clicked

---

## Post-conditions
- Changes are either saved or discarded based on the user's selection
- Database reflects the final user action accordingly

---

## Test Steps & Expected Results

| Step | Action | Expected Result |
|-----|--------|----------------|
| 1 | Modify the **Name (Georgian)** field | Field value is updated but not saved |
| 2 | Click on the **English** language tab | System detects unsaved changes |
| 3 | In the warning popup, select **Save** (if available) | Changes are saved and language is switched |
| 4 | In the warning popup, select **Discard / Cancel** | Changes are not saved and language is switched |
| 5 | In the warning popup, select **Cancel / Close** | User remains on the current language tab, no changes applied |

---

## Expected Behavior
- System must warn the user about **unsaved changes**
- User must be able to:
  - Save changes
  - Discard changes
  - Cancel the action and stay on the current page
- No data loss or unexpected behavior should occur

- ---
---

# TC-002: Required Field Validation – Empty Category Name on Save

## Description
Verify that the system displays a proper validation error when attempting to save changes with an empty required **Category Name** field.

---

## Pre-conditions
- User is logged in to the **Admin Panel**
- User is on **Catalog → Categories** page
- An existing category is selected
- **Edit Category** form is open
- **Category Name** field is initially filled

---

## Post-conditions
- Category changes are NOT saved
- **Category Name** field remains empty
- Appropriate validation error is displayed
- System remains in **Edit mode**

---

## Test Steps & Expected Results

| Step | Action | Expected Result |
|-----|--------|----------------|
| 1 | Clear the text from the **Category Name** field | Field becomes empty |
| 2 | Click **Save Changes** | Validation error is shown and changes are not saved |

---

## Expected Behavior
- Required field validation must be triggered
- User must be informed that **Category Name** is mandatory
- No data should be saved with empty required fields
