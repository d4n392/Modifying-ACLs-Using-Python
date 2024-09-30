# Using Conditional Statements
## Introduction

In this lab I practiced writing conditional statements in Python.  
Conditional statements are a powerful structure that help in achieving automation when you need to make sure conditions are met before certain actions are executed. For example, security analysts can use conditional statements in Python to check if users are approved to access a device.

---

## Scenario

I’m working as a security analyst. First, I am responsible for checking whether a user's operating system requires an update. Then, I need to investigate login attempts to a specific device. I must determine if login attempts were made by users approved to access this device and if the login attempts occurred during organization hours.

---

### Task 1

I was asked to help automate the process of checking whether a user's operating system requires an update. Imagine that a user's device can be running one of the following operating systems: OS 1, OS 2, or OS 3. While OS 2 is up-to-date, OS 1 and OS 3 are not. My task was to check whether the user's system is up-to-date, and if it is, display a message accordingly. To do this, I completed the conditional statement using the keyword `if`.

```python
# Assign a variable named `system` to a specific operating system, represented as a string
system = "OS 2"

# If OS 2 is running, then display a "no update needed" message
if system == "OS 2":
   print("no update needed")

# If OS 2 is running, then display a "no update needed" message
if system == "OS 2":
   print("no update needed")
```
Output:
no update needed

### Task 2
I assigned the system variable to different values ("OS 1", "OS 2", and "OS 3"), ran the cell, and observed what happened.

```python
system = "OS 2"

# If OS 2 is running, then display a "no update needed" message
if system == "OS 2":
   print("no update needed")
```
Question: What happens when OS 2 is running? What happens when OS 1 is running?
Answer:

When OS 2 is running we get a "no update needed" message.
When OS 1 or OS 3 are running we get no message at all.
### Task 3
Nothing is displayed when the system is not equal to "OS 2". This is because the condition didn’t evaluate to True. It would be beneficial if an alternative message is provided when updates are needed.

```python
system = "OS 4"

if system == "OS 2":
   print("no update needed")
elif system == "OS 1":
   print("update needed")
elif system == "OS 3":
   print("update needed")
else:
   print("ALERT! UNKNOWN OS DETECTED, INITIATING SELF DESTRUCTION.")
```
Output:
ALERT! UNKNOWN OS DETECTED, INITIATING SELF DESTRUCTION.

### Task 4
I decided to improve the conditional by adding the elif keyword. In the following code, I added two elif statements to check for other operating systems and provide appropriate messages.
system = "OS 4"

```python
if system == "OS 2":
   print("no update needed")
elif system == "OS 1":
   print("update needed")
elif system == "OS 3":
   print("update needed")
else:
   print("ALERT! UNKNOWN OS DETECTED, INITIATING SELF DESTRUCTION.")
```
Output:
ALERT! UNKNOWN OS DETECTED, INITIATING SELF DESTRUCTION.

Question:
What happens when OS 2 is running? What happens when OS 1 or OS 3 is running?
Answer:

If the system is OS 2 we get a "no update needed" message.
If the system is either OS 1 or OS 3 we get an "update needed" message.
Any other OS will trigger a custom alert.

### Task 5
I combined conditions using the or operator to simplify the code for multiple operating systems.

```python
system = "OS 4"

if system == "OS 2":
   print("no update needed")
elif system == "OS 1" or "OS 3":
   print("update needed.")
```
Observation:
Even for unrecognized OS like "OS 4", the condition evaluates to True because of the or operator, leading to an "update needed" message. Adding an else block would make this more accurate.

### Task 6
I was tasked with investigating login attempts to a specific device. Only approved users should log on to this device. I wrote a conditional statement that compares variables representing approved users to the username attempting to log in.

```python
approved_user1 = "elarson"
approved_user2 = "bmoreno"
username = "bmoreno"

if username == approved_user1 or username == approved_user2:
   print("This user has access to this device.")
else:
   print("This user does not have access to this device.")
```
Output:
This user has access to this device.

### Task 7
I expanded the list of approved users and used the in operator to check login attempts.

```python
approved_list = ["elarson", "bmoreno", "tshah", "sgilmore", "eraab"]
username = "elarson"

if username in approved_list:
   print("This user has access to this device.")
else:
   print("This user does not have access to this device.")
```
Question: What happens when an approved user tries to log in? What happens when an unapproved user tries to log in?
Answer:

Approved users are granted access with a message.
Unapproved users are denied access with an appropriate message.

## Conclusion
In this lab, I worked with Python's conditional statements (if, elif, else) to control program flow. The lab reinforced key concepts like system state checks, user access validation, and logical operations, which are crucial for security automation.


