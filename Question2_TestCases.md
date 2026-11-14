# Question 2: Test Case Design – Login System

## 1. Objective

The objective is to design test cases for a login system to verify username validation, password validation, successful authentication, invalid credentials handling, and account locking after three consecutive failed login attempts.

## 2. Functional Requirements

1. Username must not be empty.
2. Password must contain at least 6 characters.
3. Valid username and password must allow successful login.
4. Invalid credentials must display an appropriate error message.
5. The account must be locked after 3 consecutive failed login attempts.

## 3. Test Case Table

| Test Case ID | Test Scenario | Input Data | Expected Output |
|---|---|---|---|
| TC_01 | Login with valid credentials | Username: user1, Password: abc123 | Login successful. User is redirected to the dashboard. |
| TC_02 | Login with empty username | Username: (empty), Password: abc123 | Display "Username is required." Login must not proceed. |
| TC_03 | Login with empty password | Username: user1, Password: (empty) | Display "Password is required." Login must not proceed. |
| TC_04 | Password shorter than 6 characters | Username: user1, Password: abc12 | Display "Password must be at least 6 characters long." Login must not proceed. |
| TC_05 | Password exactly 6 characters | Username: user1, Password: abc123 (correct password) | Login successful. User is redirected to the dashboard. |
| TC_06 | Login with incorrect username | Username: wronguser, Password: abc123 | Display "Invalid username or password." Login must fail. |
| TC_07 | Login with incorrect password | Username: user1, Password: wrong123 | Display "Invalid username or password." Login must fail. |
| TC_08 | Three consecutive failed login attempts | Username: user1, Password: wrong123 submitted three consecutive times | First two attempts display "Invalid username or password." Third attempt displays "Account locked due to 3 consecutive failed login attempts." |
| TC_09 | Login attempt after account lock | Username: user1, Password: abc123 after account is locked | Display "Your account is locked. Please contact support." Login must be denied even with correct credentials. |

## 4. Test Coverage

- TC_01 covers successful login with valid credentials.
- TC_02 covers empty username validation.
- TC_03 covers empty password validation.
- TC_04 covers password length below the minimum requirement.
- TC_05 covers the exact minimum password length boundary.
- TC_06 and TC_07 cover invalid username and password scenarios.
- TC_08 verifies account locking after three consecutive failed attempts.
- TC_09 verifies that a locked account cannot log in using correct credentials.

## 5. Assumptions

1. The registered username is user1.
2. The correct password for user1 is abc123.
3. The password pass123 is also treated as a valid password for user1 in TC_01. For consistency, the test data should instead use the registered password abc123; therefore, TC_01 should use abc123.
4. The failed attempt counter resets after a successful login.
5. Once an account is locked, further login attempts are denied until the account is unlocked by an authorized process.

**Note:** These test cases are designed based on the functional requirements provided in the assignment. The error messages are proposed expected outputs because exact message wording was not specified.
