# Assignment: **Creating Test Scenarios and Test Cases Using Testing Techniques**

## Objective:
Develop test cases and scenarios using **Equivalence Partitioning**, **Decision Table Testing**, **Transition Testing**, and **Boundary Value Analysis** for newly created user stories, ensuring originality.

---

## **Part 1: User Stories and Acceptance Criteria**

### **User Story 1: Adding Items to a Shopping Cart**
- As a user, I want to add items to my shopping cart so that I can review them before purchasing.  
- **Acceptance Criteria:**
  - Users can add between 1 and 20 units of any item to the cart.  
  - If a user attempts to add more than 20 units of an item, an error message should display: “Cannot add more than 20 units.”  
  - The cart should update the item count in real-time after each addition.

---

### **User Story 2: Submitting Feedback on a Product**
- As a user, I want to leave feedback for a purchased product so that I can share my experience with others.  
- **Acceptance Criteria:**
  - Feedback must contain between 10 and 500 characters.  
  - Users must have purchased the product to leave feedback.  
  - Only one feedback submission per product is allowed per user.  

---

### **User Story 3: Viewing Order History**
- As a user, I want to view my previous orders so that I can track my purchases.  
- **Acceptance Criteria:**
  - Orders from the past 12 months should be displayed.  
  - If no orders exist, a message should display: “You have no orders in the last year.”  
  - Users must log in to view order history.  

---

### **User Story 4: Applying Discount Codes**
- As a user, I want to apply discount codes during checkout so that I can reduce the total cost of my purchase.  
- **Acceptance Criteria:**
  - Discount codes must be valid and not expired.  
  - Only one discount code can be applied per order.  
  - The system should reject invalid or expired codes with an error message: “Discount code is invalid or expired.”  

---

## **Part 2: Test Scenarios and Test Cases**

### **Equivalence Partitioning (User Story 1: Adding Items to a Shopping Cart)**

#### Test Scenario
Validate the number of units added to the shopping cart.

#### Test Case

**Test Case ID:** TC_EP_01  
**Test Case Title:** Validate the allowed quantity of items in the shopping cart.  
**Preconditions:** The user is logged in and viewing a product page.  

**Steps to Execute:**  
1. Add **5 units** of an item to the cart.  
2. Add **20 units** of an item to the cart.  
3. Add **25 units** of an item to the cart.  
4. Add **0 units** of an item to the cart.  

**Expected Results:**  
- Step 1: Items successfully added to the cart.  
- Step 2: Items successfully added to the cart.  
- Step 3: Addition fails with error: “Cannot add more than 20 units.”  
- Step 4: Addition fails with error: “Quantity must be at least 1.”  

---

### **Decision Table Testing (User Story 4: Applying Discount Codes)**

#### Test Scenario
Validate discount code application based on multiple input conditions.

#### Decision Table

| **Condition**                  | **Valid Code?** | **Code Expired?** | **Multiple Codes Applied?** | **Action**                          |  
|--------------------------------|-----------------|-------------------|-----------------------------|-------------------------------------|  
| Yes                            | No              | No                | Apply discount successfully. |  
| No                             | -               | No                | Reject with error: “Invalid code.” |  
| Yes                            | Yes             | No                | Reject with error: “Code expired.” |  
| Yes                            | No              | Yes               | Reject with error: “Only one code allowed.” |  

#### Test Case

**Test Case ID:** TC_DT_01  
**Test Case Title:** Validate discount code behavior under various conditions.  
**Preconditions:** User has items in their cart and is on the checkout page.  

**Steps to Execute:**  
1. Apply a valid, unexpired code.  
2. Apply an invalid code.  
3. Apply an expired code.  
4. Apply two codes at once.  

**Expected Results:**  
- Step 1: Discount is successfully applied.  
- Step 2: Error: “Invalid code.”  
- Step 3: Error: “Code expired.”  
- Step 4: Error: “Only one code allowed.”  

---

### **Transition Testing (User Story 3: Viewing Order History)**

#### Test Scenario
Validate transitions between login, viewing the order history, and navigating back to the dashboard.

#### Test Case

**Test Case ID:** TC_TT_01  
**Test Case Title:** Validate order history transitions.  
**Preconditions:** User account exists, and the user has past orders within 12 months.  

**Steps to Execute:**  
1. Log in with valid credentials.  
2. Navigate to the “Order History” page.  
3. View details of a specific order.  
4. Return to the main dashboard.  

**Expected Results:**  
- Step 1: Login is successful.  
- Step 2: Order history is displayed with orders from the past 12 months.  
- Step 3: Order details are displayed.  
- Step 4: User is navigated back to the dashboard successfully.  

---

### **Boundary Value Analysis (User Story 2: Submitting Feedback on a Product)**

#### Test Scenario
Validate the character count for feedback submission.

#### Test Case

**Test Case ID:** TC_BVA_01  
**Test Case Title:** Validate feedback character limits.  
**Preconditions:** User has purchased the product and is on the feedback submission page.  

**Steps to Execute:**  
1. Submit feedback with exactly **10 characters**.  
2. Submit feedback with exactly **500 characters**.  
3. Submit feedback with **9 characters**.  
4. Submit feedback with **501 characters**.  

**Expected Results:**  
- Step 1: Feedback submission succeeds.  
- Step 2: Feedback submission succeeds.  
- Step 3: Feedback submission fails with error: “Feedback must be at least 10 characters.”  
- Step 4: Feedback submission fails with error: “Feedback cannot exceed 500 characters.”  

---

## **Part 3: Deliverables**

1. **User Stories:**  
   Four user stories with unique acceptance criteria.  

2. **Test Scenarios and Test Cases:**  
   Newly created test cases for each user story, leveraging Equivalence Partitioning, Decision Table Testing, Transition Testing, and Boundary Value Analysis.  

3. **Submission Format:**  
   This document is formatted in markdown for clarity and professional presentation.
