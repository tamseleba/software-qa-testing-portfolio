# Software Quality Assurance Portfolio

![QA Testing Banner](https://img.shields.io/badge/ISTQB-CTFL_Certified-blue?style=for-the-badge)
![Testing Type](https://img.shields.io/badge/Testing-Manual_%26_API-green?style=for-the-badge)
![Tools](https://img.shields.io/badge/Tools-Postman_%7C_Google_Sheets_%7C_Chrome_DevTools-orange?style=for-the-badge)

## Executive Summary
This portfolio demonstrates end-to-end Quality Assurance testing methodologies across web user interfaces and RESTful APIs. It contains a formal **Test Plan**, **Test Execution Matrix**, **Defect Log**, and an **Automated Postman API Test Suite**.

---

## 1. Manual Testing — SauceDemo E-Commerce App

* **Target Application:** [SauceDemo](https://www.saucedemo.com)
* **Testing Types:** Functional, Positive, Negative, Boundary, and Persona Verification (Edge Cases).
* **Documentation:** Located in `/manual-testing/SauceDemo_Test_Plan_and_Cases.xlsx`.

### Test Coverage Highlights
* **Authentication:** Standard login verification (`TC-001`), invalid credentials handling (`TC-006`), and empty field validation (`TC-007`).
* **E-Commerce Workflows:** Product sorting by price (`TC-004`), dynamic cart updating (`TC-002`, `TC-003`), and complete checkout sequence (`TC-005`).
* **Edge & Persona Verification:** Validated `problem_user` catalog behavior (`TC-010`) and `locked_out_user` blocking (`TC-009`).

### Key Bug Report Summary (`BUG-001`)
* **Title:** Product catalog images render broken link `/sl-404.jpg` under `problem_user` persona.
* **Severity:** Medium | **Priority:** P2
* **Environment:** Chrome Desktop (Latest) / Windows 11
* **Steps to Reproduce:**
  1. Navigate to `https://www.saucedemo.com`.
  2. Log in using `problem_user` / `secret_sauce`.
  3. Inspect inventory product card images on `/inventory.html`.
* **Expected Result:** High-resolution product images load for all items.
* **Actual Result:** All 6 inventory item cards display broken image placeholder (`/static/media/sl-404.a688280e.jpg`).

---

## 2. API Testing — Postman Verification Suite

* **Target Services:** JSONPlaceholder & DummyJSON REST APIs.
* **Test Collection File:** `/api-testing/ReqRes-API-Regression.postman_collection.json`.
* **Assertions:** HTTP Status Codes (200, 201, 400, 404), JSON Body Schema, and Error Messaging.

### API Test Matrix & Status Code Coverage

| ID | Endpoint | Method | Test Objective | Expected Status | Status |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **API-001** | `/users` | **GET** | Verify user list pagination & data array structure | `200 OK` | **PASS** |
| **API-002** | `/posts` | **POST** | Verify resource creation & auto-generated ID | `201 Created` | **PASS** |
| **API-003** | `/auth/login` | **POST** | Validate backend payload validation (missing password) | `400 Bad Request` | **PASS** |
| **API-004** | `/users/999` | **GET** | Verify system behavior for non-existent resource ID | `404 Not Found` | **PASS** |

### Execution Proof
![Postman Test Results](api-testing/postman-test-results.png)

---

## Tools & Skills Demonstrated

* **Test Management:** Test Plan formulation, Scope definition, Entry/Exit criteria, Test Matrix design.
* **Defect Reporting:** Structured bug logging (Steps to Reproduce, Severity, Expected vs. Actual results).
* **API Testing:** Postman Collection Runner, JavaScript `pm.test` assertions, HTTP Status Code validation, JSON parsing.
* **Version Control:** GitHub portfolio structuring and Markdown documentation.
