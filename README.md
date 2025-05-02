#Leave Management System
This is a simple leave management system built using the FastMCP framework in Python. It allows employees to check their leave balance, apply for leaves on specific dates, view their leave history, and receive personalized greetings. The system uses an in-memory mock database to store employee leave data.
Features

Check Leave Balance: Retrieve the number of remaining leave days for an employee.
Apply for Leave: Request leave for specific dates, with balance validation.
View Leave History: See the dates an employee has previously taken leave.
Personalized Greeting: Get a custom greeting message for a user.

Prerequisites

Python 3.8 or higher
FastMCP library (ensure it is installed or available in your environment)

To install dependencies (if FastMCP is available via pip):
pip install fastmcp

Installation

Clone or download the project files to your local machine.
Ensure Python and the required dependencies are installed.
Place the main script (e.g., leave_manager.py) in your working directory.

Usage

Run the Server:Save the code in a file (e.g., leave_manager.py) and run it:
python leave_manager.py

This starts the FastMCP server named LeaveManager.

Interact with the Server:Use a client interface compatible with FastMCP (e.g., API calls, CLI, or UI) to send the following commands:

Check Leave Balance: get_leave_balance("E001")
Example Response: E001 has 18 leave days remaining.


Apply for Leave: apply_leave("E002", ["2025-04-17", "2025-04-18"])
Example Response: Leave applied for 2 day(s). Remaining balance: 18.


Get Leave History: get_leave_history("E001")
Example Response: Leave history for E001: 2024-12-25, 2025-01-01


Get Greeting: greeting://Alice
Example Response: Hello, Alice! How can I assist you with leave management today?





Mock Database
The system uses an in-memory dictionary (employee_leaves) as a mock database, initialized with:

Employee E001: 18 leave days, history: ["2024-12-25", "2025-01-01"]
Employee E002: 20 leave days, history: []

Note: Data persists only during the server's runtime. Restarting the server resets the data to the initial state.
Code Structure

FastMCP Server: The server is created with FastMCP("LeaveManager").
Tools:
get_leave_balance(employee_id: str): Returns the remaining leave days.
apply_leave(employee_id: str, leave_dates: List[str]): Applies leave for specified dates.
get_leave_history(employee_id: str): Retrieves leave history.


Resource:
get_greeting(name: str): Returns a personalized greeting via greeting://{name}.



Limitations

In-Memory Storage: Data is not persistent across server restarts.
Date Validation: The system does not validate date formats or check for duplicate leave dates.
Scalability: Designed for small-scale use with a mock database.
Error Handling: Basic checks for employee ID and leave balance; additional validation may be needed for production use.

Future Improvements

Add persistent storage (e.g., SQLite or MongoDB) for employee data.
Implement date format validation and prevent duplicate leave requests.
Add authentication to secure employee data access.
Support bulk leave applications or cancellation of leaves.
Integrate a user-friendly frontend for easier interaction.

Testing
To test the system, use the following example prompts:

Appy leave for {EID} for dates {}
Get leave history for {EID}
Get leave balance for (EID}

Ensure the server is running and use a compatible client to send these requests.
License
This project is for demonstration purposes and does not include a specific license. Modify and use it as needed for your use case.
Contact
For questions or contributions, please reach out to the project maintainer or open an issue in the repository (if applicable).
