Target: https://0aaa006a03fe708e803c67200063002f.web-security-academy.net/my-account?id=anaheim

Finding 1- Brute Force Vulnerability

Endpoint: POST /login 
Vulnerability: Username enumeration via different responses
What I changed: username parameter in Repeater 
Response diff: "Invalid username" → "Incorrect password"
Valid username found: anaheim
Valid password found: montana 
Impact: Attacker can enumerate valid usernames and passwords and target them. Attackers can also change the mail of the user that makes them loose access to thier own account.
Fix: Return identical error message for all failed logins evidence 
Proof : 
   

Finding 2 - Email Change Without Verification

Endpoint: POST /my-account/change-email
Vulnerability: Missing email change confirmation
What I changed: email parameter to adit@gmail.com from aditya@gmail.com 
Result: Email changed immediately with no verification required on old or new email address that shows the need of MFA there .
Impact: Attacker with valid session can change account email locking out the legitimate user permanently that can affect availability part of CIA triad 
Fix: Send confirmation link to old email before 
allowing email change
Proof :    
