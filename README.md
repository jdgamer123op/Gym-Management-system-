# Gym-Management-system-
Gym Management System

A terminal-based Python program to manage a gym. It manages members, trainers, membership plans, daily attendance, expiry alerts, and revenue statistics.

Requirements

- Python 3.8 or newer
- No external packages required
- Uses Python standard library only

How to Run

Open the project folder in the terminal and run:

python3 main.py

For Windows:

python main.py

Always run "main.py". The other Python files are supporting modules.

The data file "data/gym.json" will be created automatically.

Run the Tests

python3 test_gym.py

Features

1. Add Member
   
   - Registers a new gym member.
   - Phone number must contain 10 digits.

2. View Members
   
   - Displays all members.
   - Shows their current membership status.

3. Search Members
   
   - Searches members by name or phone number.
   - Search is partial and case-insensitive.

4. Update Member
   
   - Allows editing member details.
   - Blank input keeps the existing value.

5. Delete Member
   
   - Deletes a member.
   - Also removes their membership and attendance history.

6. Add Trainer
   
   - Registers a trainer.
   - Stores the trainer's specialization.

7. View Trainers
   
   - Displays all trainers.
   - Shows the number of members assigned to each trainer.

8. Assign / Change Trainer
   
   - Assigns a trainer to a member.
   - Allows changing or removing the assigned trainer.

9. Assign or Renew Membership
   
   - Assigns a new membership plan.
   - Allows existing memberships to be renewed.

10. View Memberships
    
    - Displays the latest membership record of every member.

11. Membership Expiry Alerts
    
    - Shows expired memberships.
    - Shows memberships that are expiring soon.

12. Mark Attendance
    
    - Records daily member check-ins.
    - Prevents duplicate check-ins on the same day.

13. View Today's Attendance
    
    - Displays members who checked in today.

14. View Statistics
    
    - Shows total members.
    - Shows revenue.
    - Shows pending fees.
    - Shows the most popular membership plan.

15. Exit
    
    - Saves the data.
    - Exits the program.

Membership Plans

Plan| Duration| Fee
Monthly| 30 days| Rs 1500
Quarterly| 90 days| Rs 4000
Annual| 365 days| Rs 15000

Renewal Rule

If a member's current membership is still active, renewing the membership extends it from the existing end date instead of today's date.

This ensures that already-paid membership time is not lost.

If the membership has already expired, the new membership starts from today's date.

Project Structure

gym-management-system/
│
├── main.py
├── gym.py
├── storage.py
├── utils.py
├── test_gym.py
│
├── data/
│   └── gym.json
│
├── README.md
└── requirements.txt

File Description

- "main.py" - Contains the main menu and program entry point.
- "gym.py" - Handles members, trainers, memberships, attendance, and statistics.
- "storage.py" - Handles JSON data loading and saving.
- "utils.py" - Contains input validation and display helper functions.
- "test_gym.py" - Contains runnable tests.
- "data/gym.json" - Stores the gym data and is created automatically.
- "README.md" - Project documentation.
- "requirements.txt" - Lists project requirements.

Data Storage

The program stores data in a JSON file.

The JSON file contains four main lists:

- Members
- Trainers
- Memberships
- Attendance

Each membership record stores:

- Start date
- End date
- Payment status

The complete membership history is preserved even after a membership is renewed.

Data is saved after every action.

If the JSON file becomes corrupted, the program replaces it with empty data instead of crashing.

Input Validation

The program validates user input.

The following invalid inputs are rejected:

- Empty names
- Invalid phone numbers
- Non-numeric IDs
- Invalid menu choices
- Duplicate same-day attendance
- Non-existent member or trainer IDs

When invalid input is entered, the program displays an error message and asks the user to enter the information again.

Limitations

- Supports only a single gym location.
- Uses a single staff login.
- Authentication is not implemented.
- Fees are tracked as Paid or Pending.
- Partial payments are not supported.
- Attendance records only check-in time.
- Check-out time and session duration are not recorded.
- Dates use the computer's current date.

Future Improvements

- Add partial payment tracking.
- Add complete payment history.
- Add check-out time and session duration.
- Add diet plans for members.
- Add workout plans for members.
- Add CSV report export.
- Add SMS expiry reminders.
- Add email expiry reminders.