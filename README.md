# EasyPeasy
A tool that helps domain administrators secure passwords in a domain by reciving a text file with all the details - usernames with duplicted passwords and usernames with weak passwords.

# Overview
EasyPeasy is a tool that helps its users discover if there are weak passwords in a domain and if there are users with the same passwords.
All the hashes will be deleted.

The tool runs on PowerShell version 4 or 5.
The tool uses Invoke-DCSync to PowerShell, which extarcts hashes from a domain. 
The script is written in PowerShell, it is also contains C Sharp code. 
The tool uses a database of common NTLM hashes.

# Usage:
The tool runs on PowerShell version 4 or 5, and only domain administrator can execute it.

option 1 - from command line:
- Open Windows PowerShell (PowerShell - with ExecutionPolicy ByPass), and change directory to the one where the files are downloaded (for example: cd C:\Users\administrator\Downloads).
- Type ".\ep.ps1" and press Enter.

option 2 - from the directory:
- (sure that all the files are downloaded and loacted in the same folder) Right click on ep.ps1, and click on 'Run with PowerShell' (PowerShell - with ExecutionPolicy ByPass).

# Results on the command line:
 After running the program, an output will be showed on PowerShell command line that will help the user understand what the program does:
 
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
 Check the output on the screen and go to the file by its path.
 If the there are no weak passwords or password duplicates in the domain the file (EPoutput.txt) will be empty.
 
 A demo for a file with the results (EPoutput.txt):

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
