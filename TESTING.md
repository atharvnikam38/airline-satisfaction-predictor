# Testing and Quality Assurance Plan: Airline Passenger Satisfaction Predictor

## 1. Scope of Testing

This document outlines the testing strategy for the Airline Passenger Satisfaction Predictor application. The scope includes:
- **Frontend (UI/UX):** Testing the user interface for both Single and Batch Prediction tabs.
- **Backend (API):** Testing the Flask API endpoints (`/predict`, `/predict_batch`, `/download_results`).
- **Business Logic:** Validating the data preprocessing, prediction logic, and analytics generation.

---

## 2. Manual Test Scenarios & Cases

### Scenario 2.1: Single Prediction Form

| Test Case ID | Description | Steps | Expected Result |
| :--- | :--- | :--- | :--- |
| **TC-SP-01** | **Happy Path:** Submit with valid data | 1. Fill all fields with valid data. 2. Click "Predict Satisfaction". | User is redirected to the result page. A prediction ("Satisfied" or "Neutral or Dissatisfied") is displayed. |
| **TC-SP-02** | **Validation:** Submit with an empty required field | 1. Leave "Age" blank. 2. Click "Predict". | A browser alert "Please fill in all required fields" appears. The form is not submitted. |
| **TC-SP-03** | **Boundary Value:** Test minimum age | 1. Enter '1' for Age. 2. Fill other fields. 3. Click "Predict". | Form submits successfully. |
| **TC-SP-04** | **Boundary Value:** Test maximum age | 1. Enter '120' for Age. 2. Fill other fields. 3. Click "Predict". | Form submits successfully. |
| **TC-SP-05** | **Invalid Input:** Enter text in a number field | 1. Attempt to type 'abc' in "Flight Distance". | (Browser-dependent) The field should ideally not accept text. *Actual Result: [Document what happens]* |
| **TC-SP-06**| **UI:** Test tab switching | 1. Click "Batch Prediction" tab. 2. Click "Single Prediction" tab again. | The Batch tab content becomes visible, then the Single tab content becomes visible again. The 'active' class is correctly applied. |

### Scenario 2.2: Batch Prediction Feature

| Test Case ID | Description | Steps | Expected Result |
| :--- | :--- | :--- | :--- |
| **TC-BP-01** | **Happy Path:** Upload valid `.xlsx` file | 1. Go to Batch tab. 2. Upload a valid Excel file using the template. 3. Click "Process File". | User is redirected to the batch result page with summary stats and sample data. |
| **TC-BP-02** | **File Type Validation:** Upload a `.csv` file | 1. Go to Batch tab. 2. Attempt to upload a CSV file. | The file should be rejected by the file input filter (`accept=".xlsx,.xls"`). *Actual Result: [Document what happens]* |
| **TC-BP-03** | **Backend Validation:** Upload Excel with missing columns | 1. Remove the 'Age' column from the template. 2. Upload the file. | The application should return an error page stating "Missing required columns: Age". |
| **TC-BP-04** | **Backend Validation:** Upload Excel with invalid data | 1. Put 'abc' in an 'Age' cell. 2. Upload the file. | The application should gracefully handle the error and show a user-friendly error message. *Actual Result: [Document what happens, likely a server error]* |
| **TC-BP-05** | **UI:** Test drag-and-drop file upload | 1. Drag an Excel file onto the upload area. | The file name appears, and the "Process File" button is enabled. |
| **TC-BP-06** | **Functionality:** Test download results link | 1. After a successful batch prediction, click "Download Full Results". | A file named `passenger_satisfaction_predictions.xlsx` is downloaded. |

---

## 3. Sample Bug Report

**Bug ID:** BP-01
**Title:** Server crashes with 500 error when batch uploading Excel file with text in a numeric column.
**Steps to Reproduce:**
1. Navigate to the "Batch Prediction" tab.
2. Download the sample template.
3. In the `Age` column for the first record, enter "Fifty" instead of a number.
4. Save the file.
5. Upload this modified Excel file and click "Process File".
**Expected Result:** The application should display a user-friendly error message like "Invalid data found in the 'Age' column. Please ensure all data is numeric."
**Actual Result:** The server returns a generic "Internal Server Error" (500), which is not user-friendly.
**Severity:** High
