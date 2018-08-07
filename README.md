# EasyPeasy
Weak and duplicated passwords scanner.

# Overview
EasyPeasy is a tool that scans for weak passwords by comparing the domain accounts' passwords to a database of common passwords.
The tool also scans for accounts with identical passwords.
All the passwords hashes will be deleted.

The tool runs on PowerShell version 4 or 5.
The tool uses Invoke-DCSync to PowerShell, which extarcts passwords hashes from Active Directory. 

# Usage:
The tool runs on PowerShell version 4 or 5 and must be executed with domain administrator's privileges.

Option 1 - from the command line:
- Open Windows PowerShell (PowerShell - with ExecutionPolicy ByPass), and change directory to the one where the files are downloaded (for example: cd C:\Users\administrator\Downloads).
- Type ".\ep.ps1" and press Enter.

Option 2 - from the directory:
- Right click on ep.ps1, and click on 'Run with PowerShell' (PowerShell - with ExecutionPolicy ByPass).

# Sample output:

 Getting Hashes from Active Directory...
 
Comparing hashes...

Checking if the hashes are 'strong'...

We found 17 Users with the SAME password

We found 0 Users with WEAK password

=============================================================

Writing the results to file...

done! check out the results in the path: C:\Users\ADMINI~1\AppData\Local\Temp\easypeasy\EPoutput.txt

Press Enter to exit...
# Results in a file:
 If the there are no weak passwords or password duplicates in the domain the file (EPoutput.txt) will be empty.
 
Sample scan result file:

=============================================================


 The users below have the SAME password:
 
SuperMario

Miki Mouse

=============================================================

The user below has a WEAK password:

cinderella

=============================================================

The users below have the SAME password and a WEAK one:

domainuser

cat

=============================================================

 # References:
 The tool uses Invoke-DCSync by @monoxgas (Nick Landers), with a little change.
