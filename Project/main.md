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

## Record of tasks
| Task Number | Planned Action              | Planned Outcome                                                 | Time Estimate | Target Completion Date | Criterion |
|-------------|-----------------------------|-----------------------------------------------------------------|---------------|------------------------|-----------|
| 1           | 1st Meeting with the client | Obtained a problem definition, understand what the situation is | 10 min        | Sep 7                  | A         |
|             |                             |                                                                 |               |                        |           |
|             |                             |                                                                 |               |                        |           |
