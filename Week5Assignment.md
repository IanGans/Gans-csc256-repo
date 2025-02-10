# Assignment: Creating Acceptance Test Criteria, Test Scenarios, and Test Cases Using Testing Techniques

## Part 1: Review and Enhance the User Stories

### User Story 1: Borrowing Books
**As a registered library member, I want to borrow up to 5 books at a time so that I can read them at home.**

#### Acceptance Criteria:
1. Members must be logged into their accounts to borrow books.
2. Members can borrow a maximum of 5 books at a time.
3. Borrowing is restricted to available books in the library’s inventory.
4. System should prevent borrowing of more than 5 books.
5. Members can borrow books only if their membership is active.

---

### User Story 2: Returning Books
**As a library member, I want to return borrowed books before the due date so that I can avoid fines.**

#### Acceptance Criteria:
1. Members must log in to return books.
2. Books can only be returned if they are currently borrowed.
3. The system must update the due date status upon return.
4. If the book is returned after the due date, a fine must be calculated based on the overdue period.
5. The system should confirm the successful return of each book.

---

### User Story 3: Overdue Notifications
**As a library admin, I want to automatically notify members of overdue books by email, so they can return books promptly.**

#### Acceptance Criteria:
1. Notifications must be sent automatically if the due date is exceeded.
2. Notifications should include member details, book details, and overdue days.
3. Notifications should be sent only to members with valid email addresses.
4. Notifications must be sent daily until the book is returned or renewed.
5. Admins can view a list of overdue notifications sent.

---

### User Story 4: Membership Registration
**As a new user, I want to register for a library membership by providing my name, age (should be 12 or above), and address so I can borrow books.**

#### Acceptance Criteria:
1. The registration form must require the user’s name, age, and address.
2. The system should validate that the user’s age is 12 or above.
3. An error message must be displayed if the age is invalid.
4. Successful registration should provide the user with a unique membership ID.
5. Membership registration must include email confirmation.

---

## Part 2: Analyze and Apply Techniques

### 1. Equivalence Partitioning (User Story 4: Membership Registration)
#### Test Scenario:
Validate that the registration system accepts users aged 12 or above and rejects users below 12.

#### Test Case:
- **Test Case ID:** TC_EP_001
- **Test Case Title:** Validate age input for library registration.
- **Preconditions:** Access to the library registration form.
- **Steps to Execute:**
  1. Open the library registration form.
  2. Enter valid name and address.
  3. Enter age values (e.g., 11, 12, 25).
  4. Submit the form.
- **Expected Results:**
  - Age < 12: Registration is rejected with an error message.
  - Age ≥ 12: Registration is successful, and a membership ID is generated.

---

### 2. Decision Table Testing (User Story 2: Returning Books)
#### Test Scenario:
Validate the outcomes of book returns based on due date and return status.

#### Decision Table:
| Due Date Passed | Book Returned | Expected Outcome      |
|-----------------|---------------|-----------------------|
| Yes             | Yes           | Fine calculated       |
| Yes             | No            | Fine continues        |
| No              | Yes           | Return successful     |
| No              | No            | No change             |

#### Test Case:
- **Test Case ID:** TC_DT_002
- **Test Case Title:** Validate book return outcomes.
- **Preconditions:** Member account is active with borrowed books.
- **Steps to Execute:**
  1. Attempt to return a book that is overdue.
  2. Attempt to return a book that is not overdue.
  3. Do not return a book that is overdue.
  4. Do not return a book that is not overdue.
- **Expected Results:**
  - Fine is calculated for overdue books upon return.
  - No action for unreturned books.
  - Successful return confirmation for books returned on time.

---

### 3. Transition Testing (User Story 3: Overdue Notifications)
#### Test Scenario:
Validate state transitions from borrowed to returned, triggering overdue notifications when applicable.

#### Test Case:
- **Test Case ID:** TC_TT_003
- **Test Case Title:** Validate state transitions for overdue notifications.
- **Preconditions:** A book is borrowed and the member’s email is valid.
- **Steps to Execute:**
  1. Borrow a book and note the due date.
  2. Allow the due date to pass without returning the book.
  3. Confirm overdue notification is sent.
  4. Return the book and confirm notification stops.
- **Expected Results:**
  - Notification is triggered once the due date is exceeded.
  - Notification stops after the book is returned.

---

### 4. Boundary Value Analysis (User Story 1: Borrowing Books)
#### Test Scenario:
Validate borrowing limits using boundary values (0, 1, and 5 books).

#### Test Case:
- **Test Case ID:** TC_BVA_004
- **Test Case Title:** Validate borrowing limits for books.
- **Preconditions:** Member account is active.
- **Steps to Execute:**
  1. Attempt to borrow 0 books.
  2. Attempt to borrow 1 book.
  3. Attempt to borrow 5 books.
  4. Attempt to borrow 6 books.
- **Expected Results:**
  - Borrowing 0 books: No action.
  - Borrowing 1-5 books: Success.
  - Borrowing 6 books: Error message displayed.



