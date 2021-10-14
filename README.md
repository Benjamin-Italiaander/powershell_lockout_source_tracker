
# Track down the source that is locking you out on a Domain controller


# What is locking me out?
This is a simple script to find the lockout source. You can run it on your domain controller from the powershell. Just copy this file to your AD-desktop and right click "Run with PowerShell" enter the username and it shows you the lockout source. 


Locking out an account after several failed authentication attempts is a common policy in a Microsoft Windows environment. Lockouts happen for a variety of reasons: a user enters the wrong password, the cached credentials used by a service are expired, Active Directory account replication errors, incorrect shared drive mappings, disconnected terminal sessions on a Windows server or mobile device accessing Exchange Server, and more.

Before you unlock the account, you need to find out why the lockout happened, so you can mitigate security risks and possibly prevent the same issue from happening again. PowerShell can be a good tool for determining why an account was locked out and the source — the script provided above lets you search for lockouts related to a single user account by examining all events with ID 4740 in the security log. The output contains the details needed for further investigation: the computer where the account lockout occurred and the time when it happened.

# Run Script
Open the Powershell ISE → Run the following script, entering the name of the locked-out user


# Hint
If you like to have a list of all locked-out users, run this command in the PowerShell


Search-ADAccount –LockedOut 
