```.py
import csv
import string
from datetime import datetime
import random
banner1 =    ("    ███████╗ ██████╗██╗  ██╗███████╗██████╗ ██╗   ██╗██╗     ██╗██╗  ██╗\n"
              "    ██╔════╝██╔════╝██║  ██║██╔════╝██╔══██╗██║   ██║██║     ██║╚██╗██╔╝\n"
              "    ███████╗██║     ███████║█████╗  ██║  ██║██║   ██║██║     ██║ ╚███╔╝\n"
              "    ╚════██║██║     ██╔══██║██╔══╝  ██║  ██║██║   ██║██║     ██║ ██╔██╗\n"
              "    ███████║╚██████╗██║  ██║███████╗██████╔╝╚██████╔╝███████╗██║██╔╝ ██╗\n"
              "    ╚══════╝ ╚═════╝╚═╝  ╚═╝╚══════╝╚═════╝  ╚═════╝ ╚══════╝╚═╝╚═╝  ╚═╝\n")
banner2 = ("██╗    ██╗███████╗██╗      ██████╗ ██████╗ ███╗   ███╗███████╗    ████████╗ ██████╗     ████████╗██╗  ██╗███████╗\n"
           "██║    ██║██╔════╝██║     ██╔════╝██╔═══██╗████╗ ████║██╔════╝    ╚══██╔══╝██╔═══██╗    ╚══██╔══╝██║  ██║██╔════╝\n"
           "██║ █╗ ██║█████╗  ██║     ██║     ██║   ██║██╔████╔██║█████╗         ██║   ██║   ██║       ██║   ███████║█████╗\n"
           "██║███╗██║██╔══╝  ██║     ██║     ██║   ██║██║╚██╔╝██║██╔══╝         ██║   ██║   ██║       ██║   ██╔══██║██╔══╝\n"
           "╚███╔███╔╝███████╗███████╗╚██████╗╚██████╔╝██║ ╚═╝ ██║███████╗       ██║   ╚██████╔╝       ██║   ██║  ██║███████╗\n"
           " ╚══╝╚══╝ ╚══════╝╚══════╝ ╚═════╝ ╚═════╝ ╚═╝     ╚═╝╚══════╝       ╚═╝    ╚═════╝        ╚═╝   ╚═╝  ╚═╝╚══════╝\n"
           "██████╗  █████╗ ███████╗███████╗██╗    ██╗ ██████╗ ██████╗ ██████╗     ███╗   ███╗ █████╗ ███╗   ██╗ █████╗  ██████╗ ███████╗██████╗ \n"
           "██╔══██╗██╔══██╗██╔════╝██╔════╝██║    ██║██╔═══██╗██╔══██╗██╔══██╗    ████╗ ████║██╔══██╗████╗  ██║██╔══██╗██╔════╝ ██╔════╝██╔══██╗\n"
           "██████╔╝███████║███████╗███████╗██║ █╗ ██║██║   ██║██████╔╝██║  ██║    ██╔████╔██║███████║██╔██╗ ██║███████║██║  ███╗█████╗  ██████╔╝\n"
           "██╔═══╝ ██╔══██║╚════██║╚════██║██║███╗██║██║   ██║██╔══██╗██║  ██║    ██║╚██╔╝██║██╔══██║██║╚██╗██║██╔══██║██║   ██║██╔══╝  ██╔══██╗\n"
           "██║     ██║  ██║███████║███████║╚███╔███╔╝╚██████╔╝██║  ██║██████╔╝    ██║ ╚═╝ ██║██║  ██║██║ ╚████║██║  ██║╚██████╔╝███████╗██║  ██║\n"
           "╚═╝     ╚═╝  ╚═╝╚══════╝╚══════╝ ╚══╝╚══╝  ╚═════╝ ╚═╝  ╚═╝╚═════╝     ╚═╝     ╚═╝╚═╝  ╚═╝╚═╝  ╚═══╝╚═╝  ╚═╝ ╚═════╝ ╚══════╝╚═╝  ╚═╝\n")


# Colors for terminal output (unchanged)
class Colors:
    HEADER = '\033[95m'
    OKBLUE = '\033[94m'
    OKCYAN = '\033[96m'
    OKGREEN = '\033[92m'
    WARNING = '\033[93m'
    FAIL = '\033[91m'
    ENDC = '\033[0m'
    BOLD = '\033[1m'
    UNDERLINE = '\033[4m'

from os import system, name
def clear_screen():
    #windows
    if name == 'nt':
        _ = system('cls')
    #mac
    else:
        _ = system('clear')
# Simple XOR encryption and decryption
def xor_encrypt_decrypt(data, key):
    return ''.join(chr(ord(c) ^ key) for c in data)


# Input validation for date
def validate_date(date_text):
    try:
        datetime.strptime(date_text, '%Y-%m-%d')
        return True
    except ValueError:
        return False


# Input validation for username and password
def validate_username_password(username, password):
    if not username or not password:
        return False
    return True

def is_unique_username(username):
    try:
        with open('user.csv', mode='r') as file:
            reader = csv.reader(file)
            for row in reader:
                if row[0] == username:
                    return False
    except FileNotFoundError:
        return True  # If no file, assume no users exist yet
    return True

# Standard password input
def standard_input(prompt="Password: "):
    return input(prompt).strip()


# Login and signup
def signup():
    print(f"{Colors.HEADER}--- Signup ---{Colors.ENDC}")
    while True:
        username = input("Enter username: ").strip()
        if not username:
            print(f"{Colors.FAIL}Username cannot be empty. Please try again.{Colors.ENDC}")
            continue
        if not is_unique_username(username):
            print(f"{Colors.FAIL}Username already exists. Please try a different one.{Colors.ENDC}")
            continue
        password = standard_input("Enter password: ")

        if validate_username_password(username, password):
            with open('user.csv', mode='a', newline='') as file:
                writer = csv.writer(file)
                writer.writerow([username, password])
            print(f"{Colors.OKGREEN}Signup successful!{Colors.ENDC}")
            break
        else:
            print(f"{Colors.FAIL}Invalid username or password. Try again.{Colors.ENDC}")


def login():
    print(f"{Colors.HEADER}--- Login ---{Colors.ENDC}")
    username = input("Enter username: ").strip()
    password = standard_input("Enter password: ")

    try:
        with open('user.csv', mode='r') as file:
            reader = csv.reader(file)
            for row in reader:
                if row[0] == username and row[1] == password:
                    print(f"{Colors.OKGREEN}Login successful!{Colors.ENDC}")
                    return True
    except FileNotFoundError:
        print(f"{Colors.FAIL}User file not found!{Colors.ENDC}")

    print(f"{Colors.FAIL}Login failed!{Colors.ENDC}")
    return False



# Post-login functionality
def user_menu(username):
    while True:
        print(f"\n{Colors.HEADER}--- User Menu ---{Colors.ENDC}")
        print(f"{Colors.OKBLUE}1. Add Event{Colors.ENDC}")
        print(f"{Colors.OKBLUE}2. View Events{Colors.ENDC}")
        print(f"{Colors.OKBLUE}3. Edit Event{Colors.ENDC}")
        print(f"{Colors.OKBLUE}4. Delete Event{Colors.ENDC}")
        print(f"{Colors.FAIL}5. Logout{Colors.ENDC}")

        choice = input("Enter choice: ").strip()

        if choice == "1":
            add_event(username)
        elif choice == "2":
            view_events(username)
        elif choice == "3":
            edit_event(username)  # You'll also need to modify this function similarly
        elif choice == "4":
            delete_event(username)  # And this one
        elif choice == "5":
            print(f"{Colors.OKGREEN}Logging out...{Colors.ENDC}")
            break
        else:
            print(f"{Colors.FAIL}Invalid choice. Try again.{Colors.ENDC}")


# Calendar event handling
def add_event(username):
    print(f"{Colors.HEADER}--- Add Event ---{Colors.ENDC}")
    while True:
        date = input("Enter the event date (YYYY-MM-DD): ").strip()
        event = input("Enter the event description: ").strip()

        if not validate_date(date):
            print(f"{Colors.FAIL}Invalid date format. Please enter a valid date in YYYY-MM-DD format.{Colors.ENDC}")
            continue

        if not event:
            print(f"{Colors.FAIL}Event description cannot be empty. Please try again.{Colors.ENDC}")
            continue

        current_time = datetime.now().strftime('%H:%M')
        current_date = datetime.now().strftime('%Y-%m-%d')

        if date == current_date and event == current_time:
            print(banner2)
            password_manager(username)
            break

        with open('cal.csv', mode='a', newline='') as file:
            writer = csv.writer(file)
            writer.writerow([username, date, event])  # Include username
        print(f"{Colors.OKGREEN}Event added successfully!{Colors.ENDC}")
        break



def view_events(username):
    print(f"{Colors.HEADER}--- View Events ---{Colors.ENDC}")
    try:
        with open('cal.csv', mode='r') as file:
            reader = csv.reader(file)
            events_found = False
            for i, row in enumerate(reader, start=1):
                if row[0] == username:  # Check if the event belongs to the logged-in user
                    print(f"{Colors.OKCYAN}{i}. Date: {row[1]}, Event: {row[2]}{Colors.ENDC}")
                    events_found = True
            if not events_found:
                print(f"{Colors.WARNING}No events found.{Colors.ENDC}")
    except FileNotFoundError:
        print(f"{Colors.FAIL}No events file found!{Colors.ENDC}")


def edit_event(username):
    print(f"{Colors.HEADER}--- Edit Event ---{Colors.ENDC}")
    view_events(username)
    try:
        event_number = int(input("Enter the event number to edit: ").strip())
        with open('cal.csv', mode='r') as file:
            events = list(csv.reader(file))

        # Filter events for the current user
        user_events = [event for event in events if event[0] == username]

        if 1 <= event_number <= len(user_events):
            new_date = input("Enter new date (YYYY-MM-DD): ").strip()
            new_event = input("Enter new event description: ").strip()
            user_events[event_number - 1][1] = new_date
            user_events[event_number - 1][2] = new_event

            # Update the original events list with modified user events
            for index, event in enumerate(events):
                if event[0] == username and index < len(user_events):
                    events[index] = user_events[index]

            with open('cal.csv', mode='w', newline='') as file:
                writer = csv.writer(file)
                writer.writerows(events)
            print(f"{Colors.OKGREEN}Event updated successfully!{Colors.ENDC}")
        else:
            print(f"{Colors.FAIL}Invalid event number!{Colors.ENDC}")
    except (ValueError, IndexError):
        print(f"{Colors.FAIL}Error updating event!{Colors.ENDC}")


def edit_event(username):
    print(f"{Colors.HEADER}--- Edit Event ---{Colors.ENDC}")
    view_events(username)
    try:
        event_number = int(input("Enter the event number to edit: ").strip())
        with open('cal.csv', mode='r') as file:
            events = list(csv.reader(file))

        # Filter events for the current user
        user_events = [event for event in events if event[0] == username]

        if 1 <= event_number <= len(user_events):
            new_date = input("Enter new date (YYYY-MM-DD): ").strip()
            new_event = input("Enter new event description: ").strip()
            user_events[event_number - 1][1] = new_date
            user_events[event_number - 1][2] = new_event

            # Update the original events list with modified user events
            for index, event in enumerate(events):
                if event[0] == username and index < len(user_events):
                    events[index] = user_events[index]

            with open('cal.csv', mode='w', newline='') as file:
                writer = csv.writer(file)
                writer.writerows(events)
            print(f"{Colors.OKGREEN}Event updated successfully!{Colors.ENDC}")
        else:
            print(f"{Colors.FAIL}Invalid event number!{Colors.ENDC}")
    except (ValueError, IndexError):
        print(f"{Colors.FAIL}Error updating event!{Colors.ENDC}")


def delete_event(username):
    print(f"{Colors.HEADER}--- Delete Event ---{Colors.ENDC}")
    view_events(username)
    try:
        event_number = int(input("Enter the event number to delete: ").strip())
        with open('cal.csv', mode='r') as file:
            events = list(csv.reader(file))

        # Filter events for the current user
        user_events = [event for event in events if event[0] == username]

        if 1 <= event_number <= len(user_events):
            del events[events.index(user_events[event_number - 1])]  # Remove the event from original list
            with open('cal.csv', mode='w', newline='') as file:
                writer = csv.writer(file)
                writer.writerows(events)
            print(f"{Colors.OKGREEN}Event deleted successfully!{Colors.ENDC}")
        else:
            print(f"{Colors.FAIL}Invalid event number!{Colors.ENDC}")
    except (ValueError, IndexError):
        print(f"{Colors.FAIL}Error deleting event!{Colors.ENDC}")


# Password Manager with XOR encryption
def generate_password():
    lower = 'abcdefghijklmnopqrstuvwxyz'
    upper = 'ABCDEFGHIJKLMNOPQRSTUVWXYZ'
    digits = '0123456789'
    symbols = '!@#$%^&*()-_=+[]{}|;:,.<>?/'

    all_chars = lower + upper + digits+symbols

    password_chars = [
        lower[random.randint(0, len(lower) - 1)],
        upper[random.randint(0, len(upper) - 1)],
        digits[random.randint(0, len(digits) - 1)],
        symbols[random.randint(0, len(digits) - 1)]
    ]

    # Fill the rest of the password with random characters
    for _ in range(len(password_chars), 12):
        password_chars.append(all_chars[random.randint(0, len(all_chars) - 1)])
    return ''.join(password_chars)

# Function to evaluate password strength
def evaluate_password_strength(password):
    length_criteria = len(password) >= 12
    digit_criteria = any(char.isdigit() for char in password)
    upper_criteria = any(char.isupper() for char in password)
    lower_criteria = any(char.islower() for char in password)
    symbol_criteria = any(char in string.punctuation for char in password)

    # Password score
    score = sum([length_criteria, digit_criteria, upper_criteria, lower_criteria, symbol_criteria])

    # Password strength evaluation
    if score == 5:
        return "Strong"
    elif score >= 3:
        return "Medium"
    else:
        return "Weak"


# Password Manager with XOR encryption and password strength evaluation
def password_manager(username):
    key = 123  # Simple XOR encryption key

    while True:
        print(f"{Colors.HEADER}--- Password Manager ---{Colors.ENDC}")
        print(f"{Colors.OKBLUE}1. Add Password{Colors.ENDC}")
        print(f"{Colors.OKBLUE}2. View Passwords{Colors.ENDC}")
        print(f"{Colors.OKBLUE}3. Delete Password{Colors.ENDC}")
        print(f"{Colors.FAIL}4. Exit Password Manager{Colors.ENDC}")

        choice = input("Enter choice: ").strip()

        if choice == "1":
            website = input("Enter website: ").strip()
            account = input("Enter account name: ").strip()
            password = input("Enter password (leave blank to generate a random one): ").strip()

            if not password:
                password = generate_password()
                print(f"{Colors.OKGREEN}Generated password: {password}{Colors.ENDC}")

            password_strength = evaluate_password_strength(password)
            print(f"{Colors.OKCYAN}Password strength: {password_strength}{Colors.ENDC}")

            encrypted_password = xor_encrypt_decrypt(password, key)
            with open('passwords.csv', mode='a', newline='') as file:
                writer = csv.writer(file)
                writer.writerow([username, website, account, encrypted_password])  # Include username
            print(f"{Colors.OKGREEN}Password added successfully!{Colors.ENDC}")

        elif choice == "2":
            try:
                with open('passwords.csv', mode='r') as file:
                    passwords = list(csv.reader(file))

                # Display only the passwords associated with the logged-in user
                for i, row in enumerate(passwords, start=1):
                    if row[0] == username:  # Check if the password belongs to the logged-in user
                        print(f"{Colors.OKCYAN}{i}. Website: {row[1]} | Account: {row[2]}{Colors.ENDC}")

                # Ask user to select a website to view its password
                website_number = int(input("Enter the number of the website to view password: ").strip())
                if 1 <= website_number <= len(passwords) and passwords[website_number - 1][0] == username:
                    encrypted_password = passwords[website_number - 1][3]
                    decrypted_password = xor_encrypt_decrypt(encrypted_password, key)
                    print(
                        f"{Colors.OKGREEN}Password for {passwords[website_number - 1][2]} on {passwords[website_number - 1][1]}: {decrypted_password}{Colors.ENDC}")
                else:
                    print(f"{Colors.FAIL}Invalid website number!{Colors.ENDC}")
            except FileNotFoundError:
                print(f"{Colors.FAIL}No passwords found!{Colors.ENDC}")

        elif choice == "3":
            # Similar to the view functionality but checks for username
            try:
                with open('passwords.csv', mode='r') as file:
                    passwords = list(csv.reader(file))

                # Display available passwords for the user
                for i, row in enumerate(passwords, start=1):
                    if row[0] == username:  # Show only the logged-in user's passwords
                        print(f"{Colors.OKCYAN}{i}. Website: {row[1]} | Account: {row[2]}{Colors.ENDC}")

                # Ask user to select a password to delete
                website_number = int(input("Enter the number of the website to delete: ").strip())

                if 1 <= website_number <= len(passwords) and passwords[website_number - 1][0] == username:
                    del passwords[website_number - 1]
                    with open('passwords.csv', mode='w', newline='') as file:
                        writer = csv.writer(file)
                        writer.writerows(passwords)
                    print(f"{Colors.OKGREEN}Password deleted successfully!{Colors.ENDC}")
                else:
                    print(f"{Colors.FAIL}Invalid website number!{Colors.ENDC}")
            except FileNotFoundError:
                print(f"{Colors.FAIL}No passwords found!{Colors.ENDC}")
        elif choice == "4":
            clear_screen()  # Clear screen before exiting
            break
        else:
            print(f"{Colors.FAIL}Invalid choice. Try again.{Colors.ENDC}")

# Main program flow
def main():
    while True:
        print(banner1)
        print(f"{Colors.OKBLUE}1. Login{Colors.ENDC}")
        print(f"{Colors.OKBLUE}2. Signup{Colors.ENDC}")
        print(f"{Colors.FAIL}3. Exit{Colors.ENDC}")

        choice = input("Enter choice: ").strip()

        if choice == "1":
            if login():
                username = input("Enter your username: ").strip()  # Get the username after login
                user_menu(username)  # Show the user menu with username
        elif choice == "2":
            signup()
        elif choice == "3":
            clear_screen()  # Clear screen before exiting
            print(f"{Colors.OKGREEN}Exiting the program.{Colors.ENDC}")
            break
        else:
            print(f"{Colors.FAIL}Invalid choice. Try again.{Colors.ENDC}")

if __name__ == "__main__":
    main()

```
