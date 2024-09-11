# Modifying-ACLs-Using-Python

## Using Conditional Statements

In this lab I practiced writing conditional statements in Python.
Conditional statements are a powerful structure that help in achieving automation when you need to make sure conditions are met before certain actions are executed. For example, security analysts can use conditional statements in Python to check if users are approved to access a device. 


## Scenario

You're working as a security analyst. First, you are responsible for checking whether a user's operating system requires an update. Then, you need to investigate login attempts to a specific device. You must determine if login attempts were made by users approved to access this device and if the login attempts occurred during organization hours.
You are asked to help automate the process of checking whether a user's operating system requires an update. 
Imagine that a user's device can be running one of the following operating systems: OS 1, OS 2, or OS 3. While OS 2 is up-to-date, OS 1 and OS 3 are not. 
Your task is to check whether the user's system is up-to-date, and if it is, display a message accordingly. To do this, complete the conditional statement using the keyword if. 

### Step 1

#Assign a variable named `system` to a specific operating system, represented as a string. This variable indicates which operating system is running
​
system = "OS 2"
​
#If OS 2 is running, then display a "no update needed" message
​
if system == "OS 2":

   print("no update needed")
  
no update needed

_Now try assigning the system variable to different values ("OS 1", "OS 2", and "OS 3"), run the cell, and observe what happens. Keep the conditional statement as is. _

#Assign `system` to a specific operating system. This variable represents which operating system is running

​
system = "OS 2"
​
#If OS 2 is running, then display a "no update needed" message
​
if system == "OS 2":

   print("no update needed")
  
**What happens when OS 2 is running? What happens when OS 1 is running?**

When OS 2 is running we get a "no update needed" message. When OS 1 or OS 3 are running we get no message at all.

_Nothing is displayed when the system is not equal to "OS 2". This is because the condition didn't evaluate to True. It would be beneficial if an alternative message is provided to them when updates are needed._

### Step 2

In the following cell, add the appropriate keyword after the first conditional so that it will display a message that conveys that an update is needed when the system is not running OS 2.

Then, set the value of the system variable to indicate that OS 2 is running and run the cell. After observing what happens, set the value of system to indicate either that OS 1 is running or that OS 3 is running and run the cell.

#Assign `system` to a specific operating system

#This variable represents which operating system is running
​
system = "OS 4"
​
#If OS 2 is running, then display a "no update needed" message

#Otherwise, display a "update needed" message
​
if system == "OS 2":

   print("no update needed")
   
elif system == "OS 1":

   print("update needed")
   
elif system == "OS 3":

   print("update needed")
   
else:

   print("ALERT UNKNOWN OS DETECTED, INITIATING SELF DESTRUCTION.")
   
ALERT UNKNOWN OS DETECTED, INITIATING SELF DESTRUCTION.

**In this setup what happens when OS 2 is running? And what happens when OS 2 is not running?**

When OS 2 is running we get a "no update needed" message displayed in the output. When OS 2 is not running we get an "update needed" message.

_This setup is still not ideal. If the variable system contains a random string or integer, the conditional above would still display update needed._

To improve the conditional, you will need to add the elif keyword. In the following cell, you will add two elif statements after the if statement, to create the final code. The first elif statement will display update needed if system is "OS 1". 

The second elif statement will display the same message, if system is "OS 3". Complete the second elif statement, and then run the cell with the variable system set to a different string each time. Observe what happens when each operating system is running. 

### Step 3

#Assign `system` to a specific operating system

#This variable represents which operating system is running


system = "OS 4"
​
#If OS 2 is running, then display a "no update needed" message

#Otherwise if OS 1 is running, display a "update needed" message

#Otherwise if OS 3 is running, display a "update needed" message
​
if system == "OS 2":

   print("no update needed")
   
elif system == "OS 1":

   print("update needed")
   
elif system == "OS 3":

   print("update needed")
   
else:

   print("ALERT! UNKNOWN OS DETECTED, INITIATING SELF DESTRUCTION.")
   
ALERT! UNKNOWN OS DETECTED, INITIATING SELF DESTRUCTION.

**Under this setup what happens when OS 2 is running? What happens when OS 1 is running? What happens when OS 3 is running? What happens when neither of those three operating systems are running?**

If the system is OS 2 we get our "no update needed" message printed. If the system is either OS 1 or OS 3 we get an "update needed" message. Then I had fun with it and any other OS I had the code print a ALERT! UNKNOWN OS DETECTED, INITIATING SELF DESTRUCTION." message.

_Writing code that is readable and concise is a best practice in programming. The conditional above can be written more concisely._

### Step 4

In the following cell, use a logical operator to combine the two elif statements from the previous setup into one elif statement. Assign the system variable to a value and run the cell. Like you did in the previous task, use "OS 1", "OS 2", "OS 3", and other strings.

#Assign `system` to a specific operating system

#This variable represents which operating system is running
​
system = "OS 4"
​
#If OS 2 is running, then display a "no update needed" message

#Otherwise if either OS 1 or OS 3 is running, display a "update needed" message
​
if system == "OS 2":

   print("no update needed
   
elif (system == "OS 1" or "OS 3"):

   print("update needed.")
   
update needed.

**What do you observe about this conditional?**

If the OS was either 1 or 3 it would print "update needed". If the OS was 2 it would print the "no update needed". The only problem is there is no else conditional for if the OS was anything other than 1, 2, or 3. Even if beyond the parameters, say OS 4, it will print update needed; This may not be necessary.

### Step 5

Now you'll move on to the next part of your work. You've been asked to investigate login attempts to a specific device. Only approved users should log on to this device.

You'll start with two authorized users, stored in the variables approved_user1 and approved_user2. 

You'll need to write a conditional statement that compares those variables to a third variable, username. This will be the username of a specific user trying to log in. 

#Assign `approved_user1` and `approved_user2` to usernames of approved users
​
approved_user1 = "elarson"

approved_user2 = "bmoreno"
​
#Assign `username` to the username of a specific user trying to log in
​
username = "bmoreno"
​
#If the user trying to log in is among the approved users, then display a message that they are approved to access this device

#Otherwise, display a message that they do not have access to this device
​
if username == approved_user1 or username == approved_user2:

   print("This user has access to this device.")
   
else:

   print("This user does not have access to this device.")
  
This user does not have access to this device.

The number of approved users has now expanded to five. Rather than storing each of the approved users' usernames individually, it would be more concise to store them in an allow list called approved_list.

### Step 6

The in operator in Python can be used to determine whether a given value is an element of a sequence. Using the in operator in a condition can help you check whether a specific username is part of a list of approved usernames. For example, in the code below, username in approved_list evaluates to True if the value of the username variable is included in approved_list.

Complete the code in the following cell to display the same messages that you used in the previous step. When the condition evaluates to True, the following message will be displayed: "This user has access to this device." When it evaluates to False, the following message will be displayed: "This user does not have access to this device." Then, run the cell to observe its behavior.

Afterwards, reassign the username variable to a username that is not approved and run the cell to observe what happens.

#Assign `approved_list` to a list of approved usernames
​
approved_list = ["elarson", "bmoreno", "tshah", "sgilmore", "eraab"]
​
#Assign `username` to the username of a specific user trying to log in
​
username = "elarson"
​
#If the user trying to log in is among the approved users, then display a message that they are approved to access this device

#Otherwise, display a message that they do not have access to this device
​
if username in approved_list:

   print("This user has access to this device.")
   
else:

   print("This user does not have access to this device.")
  
This user has access to this device.

**What happens when an approved user tries to log in? What happens when an unapproved user tries to log in?**

When an approved user on the approved_list tries to log in, it displays "This user has access to this device" message. When an unapproved user tries to log in, "This user does not have access to this device" message is displayed.

### Step 7

Now you'll write another conditional statement. This one will use the organization_hours variable to check if the user logged in during specific organization hours. When that condition is met, the code should display the string "Login attempt made during organization hours.". When that condition isn't met, the code should display the string "Login attempt made outside of organization hours.".

The organization_hours variable will have a Boolean data type. If organization_hours has a Boolean value of True, that means the user is logged in during the specified organization hours. If organization_hours has a Boolean value of False, that means the user is not logged in during those hours.

#Assign `organization_hours` to a Boolean value that represents whether the user is trying to log in during organization hours
​
organization_hours = False
​
#If the entered `organization_hours` has a value of True, then display "Login attempt made during organization hours."

#Otherwise, display "Login attempt made outside of organization hours."
​
if organization_hours == True:

   print("Login attempt made during organization hours.")
   
else:

   print("Login attempt made outside of organization hours.")
  
Login attempt made outside of organization hours.

**What happens when the user logs in during organization hours? What happens when they log in outside of organization hours?**

When the user logs in during normal operating hours, they get a "Login attempt made during organization hours" message. When the user logs in outside of normal operating hours, they get a "Login attempt made outside of organization hours" message.

### Step 8

The following cell assembles the code from the previous tasks. It includes the conditional statement that checks if a user is on the allow list and the conditional statement that checks if the user logged in during organization hours.

#Assign `approved_list` to a list of approved usernames
​
approved_list = ["elarson", "bmoreno", "tshah", "sgilmore", "eraab"]
​
#Assign `username` to the username of a specific user trying to log in
​
username = "basd"
​
#If the user trying to log in is among the approved users, then display a message that they are approved to access this device

#Otherwise, display a message that they do not have access to this device
​
if username in approved_list:

   print("This user has access to this device.")
​
else:

   print("This user does not have access to this device.")
​
#Assign `organization_hours` to a Boolean value that represents whether the user is trying to log in during organization hours
​
organization_hours = False

#If the entered `organization_hours` has a value of True, then display "Login attempt made during organization hours."

#Otherwise, display "Login attempt made outside of organization hours."
​
if organization_hours == True:

   print("Login attempt made during organization hours.")
   
else:

   print("Login attempt made outside of organization hours.")
  
This user does not have access to this device.

Login attempt made outside of organization hours.

**What happens when the user trying to log in is not among the approved users? What happens when the user trying to log in is among the approved users? What happens when the user tries to log in outside of organization hours?**

When the user logging in is on the approved list, the message "This user has access to this device." is displayed. When the user trying to log in is not among the approved users it will print the "This user does not have access to this device." message. If we change the organization_hours to equal False, we get the "Login attempt made outside of organization hours." message. Together these last two conditions would be an unapproved user tried accessing the device outside of normal operating hours, which may be indicative of a potential attack.

### Step 9

You can also provide a single message about the login attempt. To do this, you can join both conditions into a single conditional statement using a logical operator. This will make the code more concise.

Examine the code in the following cell and add the missing operator that would allow for a single message. Then run the cell, entering different combinations of information, and observe what happens.

#Assign `approved_list` to a list of approved usernames
​
approved_list = ["elarson", "bmoreno", "tshah", "sgilmore", "eraab"]
​
#Assign `username` to the username of a specific user trying to log in
​
username = "bmoreno"
​
#Assign `organization_hours` to a Boolean value that represents whether the user is trying to log in during organization hours
​
organization_hours = True
​
#If the user is among the approved users and they are logging in during organization hours, then convey that the user is logged in

#Otherwise, convey that either the username is not approved or the login attempt was made outside of organization hours
​
if username in approved_list and organization_hours == True:

   print("Login attempt made by an approved user during organization hours.")
  
else:

   print("Username not approved or login attempt made outside of organization hours.")
​
**In this setup, what happens when the user trying to log in is an approved user and doing so during organization hours? What happens when the user either is not approved or attempts to log in outside of organization hours?**

If the user logging in is an approved user logging in during the organization's operational hours, the message "Login attempt made by an approved user during organization hours." will be displayed. On the other hand if either the user logging in is not on the approved_list or the login attempt is made outside of normal hours, then the message "Username not approved or login attempt made outside of organization hours." is displayed.

## Conclusion

In this lab, I worked with Python's conditional statements (if, elif, else) to control program flow, checking system OS updates, handling unrecognized inputs, and verifying user access with logical operators like or and in. I used Boolean variables to manage login attempts during organization hours and combined multiple conditions for efficient user access and time checks. The lab emphasized writing concise, readable code while reinforcing key programming concepts relevant to security automation, such as system state checks and access validation.

