# 🛍️ Manual + API Testing Project: Packly Website
**Comprehensive Quality Assurance Documentation for a Bangladesh E-commerce Marketplace**

## 📜 Table of Contents
- [Test Documentation](#-test-documentation)
- [Project Overview](#-project-overview)
- [Test Scope & Exclusions](#-test-scope--exclusions)
- [Test Strategy & Approach](#-test-strategy--approach)
- [Test Execution Summary](#-test-execution-summary)
- [Key Defects Found](#-key-defects-found)
- [Project Context & Key Learnings](#-project-context)

---

## 📊 Test Documentation

**Packly Test Cases & Reports**

🔗 [View All Test Documentation](https://docs.google.com/spreadsheets/d/1czRy3Yo3OFlHqIEtiwWWckpszlU8SyrCj-WyRK2smWk/edit?usp=sharing)

**Contents:**
- 126 total test cases executed (109 manual UI + 17 API)
- Boundary value / best-case / worst-case test cases across 30 functional areas
- 40 high-level test scenarios across 10 modules
- Full mind map of test coverage across 17 site modules
- 15 confirmed defects identified across UI and API layers, with screenshots and reproduction steps

**Access Notes:**
- Requires a Google account (if hosted on Google Drive/Sheets)
- Set to "View Only" by default
- Request edit access if needed

---

## 🌐 Project Overview

**Application Under Test (AUT):** Packly (https://www.packly.com/)
**Test Plan ID:** TP-Packly-01
**Testing Phase:** Functional | API | Boundary Value | Basic Security | Basic Accessibility

### Objective
To ensure the Packly website delivers a seamless, bug-free shopping experience for customers by validating core functionalities, data accuracy, API reliability, and basic security/accessibility practices — through both UI-level and API-level manual testing.

### Key Features Validated
- User Management (Registration, Login, Forgot Password, Logout, Profile)
- Product Discovery (Search, Categories, Sort, Filters)
- Product Detail, Cart & Checkout
- My Account & Order Tracking
- Customer Support (Help Center)
- Shops Directory
- Core Backend API Endpoints

---

## 🎯 Test Scope & Exclusions

### In Scope

| Module | Test Coverage Details |
|---|---|
| User Authentication | Phone + OTP registration, login, forgot password, session/logout behavior |
| Product Discovery | Search, category navigation, sort, price/brand/rating/promotion filters |
| Cart & Checkout | Item selection, quantity, payment method, coupon codes, shipping fee logic |
| Customer Support | Help Center FAQ and search |
| API Layer | Login, OTP, product listing/filtering, search, cart, checkout, coupon, order tracking, profile update endpoints |
| UI Components | Responsiveness, image alt text, keyboard navigation |

### Out of Scope

| Item | Reason for Exclusion |
|---|---|
| Real Payment Processing | Financial risk — no real payments or completed orders were made |
| Seller Business Manager Portal | Separate sub-system, out of scope for this round |
| Load/Stress Testing | Outside manual testing scope; risk of disrupting a live production site |
| Deep Penetration Security Testing | Legal/ethical restrictions — only basic input-validation-level checks performed |
| Mobile App | Limited to the web application only |

---

## 🔬 Test Strategy & Approach

### 1. Test Types

| Type | Tools/Methods Used | Coverage |
|---|---|---|
| Functional Testing (UI) | Manual test cases (109) | Core user journeys |
| API Testing | Browser DevTools (Network tab) | 17 key backend endpoints |
| Boundary Value Analysis | Manual test cases (122) | Field limits across 30 functional areas |
| Basic Security Testing | Manual input testing (XSS/SQLi payloads) | Search, login, checkout forms |
| Basic Accessibility Testing | Manual keyboard nav + DevTools inspection | Key pages, images, forms |

### 2. Test Phases
1. **Exploration & Requirement Understanding** – Manual walkthrough of the live site to document all observable functionality (no formal FRS was available).
2. **Test Design** – Created 126 test cases across manual UI and API layers, plus 122 BVA-style cases.
3. **Execution** – Manual UI testing and API testing (via DevTools network inspection), with defect logging and screenshot evidence.
4. **Reporting** – Summary metrics and defect documentation (this report).

---

## 📊 Test Execution Summary

### Manual UI Testing

| Status | Count | Percentage |
|---|---|---|
| Passed | 93 | 85.3% |
| Failed | 14 | 12.8% |
| Not Executed | 2 | 1.8% |
| **Total** | **109** | **100%** |

### API Testing

| Status | Count | Percentage |
|---|---|---|
| Passed | 13 | 76.5% |
| Failed | 1 | 5.9% |
| Not Executed | 3 | 17.6% |
| **Total** | **17** | **100%** |

### Combined Overall Metrics

| Status | Count | Percentage |
|---|---|---|
| Passed | 106 | 84.1% |
| Failed | 15 | 11.9% |
| Not Executed | 5 | 4.0% |
| **Total** | **126** | **100%** |

---

## 🐞 Key Defects Found

A sample of confirmed, reproducible defects identified during this testing effort:

- **Price filter default value bug** — the "To" price field defaults to an unrealistic hardcoded value (378888858888), traced down to the raw HTML `max`/`value` attributes.
- **Brand + Price filter combination bug** — combining Brand and Price Range filters causes the Brand condition to be silently ignored.
- **Search "no match" bug (confirmed at API level)** — searching a nonsense keyword returns the full unfiltered catalog instead of an empty result; root cause traced to a malformed `search` query parameter in the API request.
- **Track Order API returns 500 Internal Server Error** for a nonexistent Order ID, instead of a proper 404 — a real backend defect masked by a friendly frontend message.
- **Wishlist/Favorites toggle inconsistency** — heart icon state doesn't persist correctly, and remove/add confirmation messages are reversed.
- **Checkout Address field missing validation** — Name and Phone Number fields validate correctly when empty, but Address (also marked required) does not.
- **Flash Sale messaging bug** — section displays "Flash sale has ended" while 102 actively discounted products remain listed and purchasable.
- **Accessibility gap** — Categories dropdown does not respond to the Space key (falls through to default page-scroll behavior instead).
- **Generic/missing image alt text** — product images use a non-descriptive placeholder alt text ("Main Product Image"), and some UI icons (e.g. Google Play badge) have no alt text at all.

Full details, screenshots, and reproduction steps for each defect are documented in the test execution spreadsheets and `bug-reports/` folder.

---

## 📚 Project Context

This is a personal testing project developed as part of self-directed QA learning, designed to:
- Practice manual and API testing methodologies in a real-world scenario
- Build expertise in creating test plans, test cases, and summary reports
- Demonstrate QA skills for professional development and CV/portfolio purposes

## 🎓 Key Learnings

Through testing Packly.com, I've:

**1. Technical Skills**
- ✔️ Designed 126+ test cases covering functional, API, boundary-value, security, and accessibility testing
- ✔️ Used browser DevTools to inspect and verify real API requests, responses, and status codes
- ✔️ Documented defects with clear reproduction steps, screenshots, and network evidence
- ✔️ Traced UI-level bugs down to their root cause at the API/HTML level (e.g. price filter, search query bug)

**2. Domain Knowledge**
- ✔️ Understood e-commerce platform workflows (registration, product discovery, cart, checkout, order tracking)
- ✔️ Learned basic accessibility standards (keyboard navigation, alt text, focus handling)
- ✔️ Learned basic API status code conventions (401 vs 422, 404 vs 500) and how to evaluate deviations fairly

**3. Professional Growth**
- ✔️ Gained experience structuring test documentation (test plan, test scenarios, test cases, BVA, API tests)
- ✔️ Improved analytical skills for identifying edge cases and cross-referencing related bugs across modules
- ✔️ Developed habits for organized test tracking (spreadsheets, mind maps, GitHub repo structure)

**4. Ethical Testing Practices**
- ✔️ Conducted all testing manually and non-disruptively on a live public website, with no real payments, no automated scripts, and no unauthorized data access
- ✔️ Applied judgment to distinguish confirmed defects from subjective assumptions when writing bug reports
