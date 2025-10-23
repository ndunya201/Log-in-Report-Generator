# Log-in-Report-Generator
A Python script that tracks and reports user login activity across machines. It defines an Event class to capture system events, sorts and processes login/logout data, and generates a clear report showing which users are currently active on each machine. Useful for monitoring system usage and detecting inconsistencies in login sessions.

---

## Overview
This project simulates and analyzes user login and logout events. It helps identify which users are currently logged in, on which machines, and detects inconsistencies (e.g., logging out of a machine without a prior login).

---

## How It Works
1. **Event Class** – Represents an event with attributes such as date, type, machine, and user.
2. **Functions:**
   - get_event_date(event): Returns the event date to help sort events chronologically
   - current_users(events): Processes all events to determine currently logged-in users.
   - generate_report(machines): Prints a clean summary showing users active on each machine. 

---

## Example Usage

```python
# Define event class and functions (see script)
# Create event instances
events = [
    Event('2020-01-21 12:45:56', 'login', 'myworkstation.local', 'jordan'),
    Event('2020-01-22 15:53:42', 'logout', 'webserver.local', 'jordan'),
    Event('2020-01-21 18:53:21', 'login', 'webserver.local', 'lane'),
    Event('2020-01-22 10:25:34', 'logout', 'myworkstation.local', 'jordan'),
    Event('2020-01-21 08:20:01', 'login', 'webserver.local', 'jordan'),
    Event('2020-01-23 11:24:35', 'logout', 'mailserver.local', 'chris'),
]

# Process and generate report
users = current_users(events)
generate_report(users)
```

---

## Sample Output
webserver.local: lane, jordan

---

## Key Learnings

- Sorting objects using custom functions
- Managing nested data structures (dictionary of sets)
- Handling inconsistent data (logout without login)
- Generating summary reports programmatically
