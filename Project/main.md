# Criterion A: Planning
## Problem Definition

My client is **Mr. X**, the Director of IT Security at a large financial institution. The bank’s employees frequently handle sensitive information, and the client is concerned about secure password management. With many employees working remotely and in shared workspaces, traditional password managers could attract attention or be targeted by cyber threats. Mr. X is seeking a **secure, covert solution** for storing passwords that integrate seamlessly into the daily workflow of bank employees without raising suspicion.

(See the evidence of Consultation in the Appendix)

## Proposed Solution

I propose developing a **disguised password manager** in Python, which functions as a simple calendar application. This calendar will allow users to add and manage events while hiding its true purpose—**storing and retrieving passwords securely**—activated only by a secret code. A login and signup system will add an extra layer of security, ensuring only authorized users have access.

### Why Python?

I proposed Python as it is the ideal choice for this project for several reasons:

- **Cross-platform Compatibility**: Python can run on various operating systems used by employees (Windows, MacOS, Linux), ensuring the tool is widely accessible across different work environments.
- **Readability and Maintenance**: Python’s clean syntax makes the program easy to maintain and extend, which is essential for a growing financial institution where the system may need to be updated or modified in the future.
- **Security Libraries**: Python has strong support for cryptographic libraries such as `cryptography` or `hashlib`, allowing the tool to implement robust encryption for password storage, which is a core requirement of the project.
- **Rapid Prototyping**: Python allows for fast development cycles, meaning that we can iterate quickly on the design and incorporate feedback from the client to meet their exact needs in a shorter timeframe.

### Why Use a CSV File?

I proposed using a **CSV file** to store the calendar events and encrypted passwords for the following reasons:

- **Simplicity and Transparency**: CSV files are simple to manage, and they integrate well with Python’s native libraries. This makes the tool efficient to run without complex database setups that may be unnecessary for the client’s needs.
- **Low Resource Consumption**: For a financial institution, performance matters, and CSV files provide a lightweight, low-resource option.
- **Data Encryption**: Even though the data is stored in CSV, passwords will be encrypted using basic cryptographic techniques like character shifting or hashing. This ensures that sensitive information remains protected, even if the file is accessed without permission.

## Requirements

### Basic Calendar Functionality

- The application should operate as a basic calendar where users can **add, view, and edit events**.

### Hidden Functionality

- The program should include a hidden password manager mode that is only activated when a **secret code** (e.g., "open123") is entered.
- Once in password manager mode, users should be able to:
  - **Add a password** for specific purposes, such as logging into websites or accounts.
  - **View the stored passwords**, which are masked initially and revealed only if the user re-enters the secret code.
  - Optionally, the application can display passwords in a **partially masked form** (e.g., showing only the first and last characters for security).

### Basic Security Features

- Passwords should be stored in an **external text file**, allowing the program to persistently save user data.
- To ensure security, passwords should be stored using a basic **encryption or obfuscation technique**. This could include reversing the password string, character shifting, or more advanced methods like hashing or encryption algorithms.

### Login and Signup System

- The tool should include a **login and signup system** to restrict access to the password manager.
- Only registered users can access the application, ensuring protection and preventing unauthorized access to both calendar functions and the hidden password manager.
- The login system should prompt for a **username and password**, securing the application from the start.

### User Interaction

- The tool will be operated through a **simple terminal-based interface**, allowing users to interact with both the calendar and the password manager modes.


# Criterion  B: Design

## Flow diagrams for algorithms
img.
**fig. 1** this is the flow diagram for the algorithm used to search in the data file... 
## Data storage

## Sketches of the application (wireframe diagrams)

## Test plan
# Test Plan

| Description                                    | Test Type       | Input                                                                                                                                                      | Expected Outcome                                                                                                                                                                        |
|------------------------------------------------|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Test for Signup System**                     | Unit test       | 1. Run the script 2. Click the Signup button 3. Input the username and password 4. Click Signup                                                             | A popup should show if the username exists or passwords don’t match; otherwise, user should be redirected to login screen.                                                               |
| **Test for Login System**                      | Unit test       | 1. Run the script 2. Input correct username and password 3. Click Login                                                                                     | Successful login should take user to the User Menu. If credentials are incorrect or file is missing, an error message should appear.                                                     |
| **Test for Add Event System**                  | Unit test       | 1. Login 2. Select "Add Event" from the menu 3. Input event date and description 4. Press Add Event                                                         | If input is correct, a success message should appear. If the date format is wrong, or the event is empty, an error message should appear.                                                |
| **Test for View Events System**                | Unit test       | 1. Login 2. Select "View Events" from the menu                                                                                                              | The list of events should be displayed with date and description. If there are no events, a message indicating "No events found" should be shown.                                        |
| **Test for Edit Event System**                 | Unit test       | 1. Login 2. Select "Edit Event" 3. Input the number corresponding to the event to edit 4. Input new date and description                                    | The event should be updated successfully, and a confirmation message should be displayed. If the event number is invalid or date format is wrong, an error message should appear.        |
| **Test for Delete Event System**               | Unit test       | 1. Login 2. Select "Delete Event" 3. Input the number corresponding to the event to delete                                                                  | The event should be removed, and the list should be updated with a success message. If an invalid event number is entered, an error message should be shown.                             |
| **Test for Password Manager - Add Password**   | Integration test | 1. Login 2. Open Password Manager 3. Select "Add Password" 4. Enter website, account name, and password or leave blank to auto-generate                     | If inputs are valid, a success message should be shown, and the password should be saved. A generated password should appear if left blank.                                               |
| **Test for Password Manager - View Passwords** | Integration test | 1. Login 2. Open Password Manager 3. Select "View Passwords" 4. Select a website to view its stored password                                                | The list of saved passwords should be displayed. When selecting a website, the corresponding decrypted password should be shown.                                                         |
| **Test for Password Manager - Delete Password**| Integration test | 1. Login 2. Open Password Manager 3. Select "Delete Password" 4. Input the number corresponding to the password entry to delete                             | The password entry should be deleted, and a success message should be displayed. If an invalid number is selected, an error message should be shown.                                      |
| **Test for Logout System**                     | Unit test       | 1. Login 2. Perform any action 3. Select "Logout"                                                                                                           | Upon selecting logout, the user should be returned to the login screen, ending the session.                                                                                               |

## Record of tasks
| Task Number | Planned Action              | Planned Outcome                                                 | Time Estimate | Target Completion Date | Criterion |
|-------------|-----------------------------|-----------------------------------------------------------------|---------------|------------------------|-----------|
| 1           | 1st Meeting with the client | Obtained a problem definition, understand what the situation is | 10 min        | Sep 7                  | A         |
|             |                             |                                                                 |               |                        |           |
|             |                             |                                                                 |               |                        |           |
