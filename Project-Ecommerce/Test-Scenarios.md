# TS-001: Language Switch with Unsaved Changes

## Feature
Ensure language switching handles unsaved changes correctly in Admin Panel.

## Scenario
User modifies category form but has not saved changes, then switches language.

## Precondition
- User is logged in to Admin Panel  
- Edit page for a category is open (e.g. "Children's Clothing")  
- One or more fields modified (e.g., Name in Georgian)  
- Save button NOT clicked  

## Steps
1. Modify the Name (Georgian) field  
2. Click on English language tab  
3. Observe warning popup for unsaved changes  
4. Select Save → changes should be saved and language switched  
5. Select Discard → changes not saved, language switched  
6. Select Cancel → user remains on current language tab, changes unchanged  

## Expected Result
- System warns about unsaved changes  
- User can Save, Discard, or Cancel  
- No data loss or unexpected behavior occurs  

## Post-condition
- Database reflects user’s choice accordingly



# TS-002: Required Field Validation – Empty Category Name on Save

## Feature
System must validate required fields when saving category changes.

## Scenario
User clears required Category Name field and attempts to save.

## Precondition
- User logged in to Admin Panel  
- Navigate to Catalog → Categories  
- Select existing category and open Edit Category form  
- Category Name initially filled  

## Steps
1. Clear the text from the Category Name field  
2. Click Save Changes  

## Expected Result
- Validation error is displayed  
- Changes are NOT saved  
- Field remains empty  
- System stays in Edit mode

## Post-condition
- Category remains unchanged


