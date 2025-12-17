# Kerberos and Certs

## General Information
Author: Nathan Ord
Date: 12/16/2025
Description: Getting onto a network is the first hurdle, but where do you go once you have taken the first step? Traditional persistence is boring, so let’s be a little sneaker with Kerberos and certificates in a Windows network! You can create and store certs like a password to use forever without having to worry about passwords changing.

## Video
https://youtu.be/mD00y8X3aJQ

## Why You Should Care

We’ve talked about C2s and how they may work, but those are only as good as their creator and how much better a Blue Team is in the network. You need other options that retain your access without the risk of burning your Red Team infrastructure. As such, leveraging Kerberos and certificates is a solid way of keeping a foot in the door of a Windows network before pulling back to the edge to maintain access into a network generally. This is a bit harder to catch for a Blue Team and is significantly more resilient than other options in a Windows network.

## Three Main Ideas

* Initial Access in a Windows environment w/ Kerberos
  * We can use Kerberos to get into a network using user credentials we have harvested in some way. This gives us a foothold.
* Lateral movement in a Windows environment w/ Kerberos
  * We can use other techniques of privilege escalation and continue to use Kerberos throughout a network. The hope would be to get the krbtgt hash and make Golden Tickets to pivot.
* Long term persistence w/o C2
  * Once we get to the Golden Tickets, we need to lay low as these may get caught. As such, we lay down as much non-beaconing access as possible.

## Future Directions

* Other Windows authentication methodologies that are not attached to passwords and hashes
* Network device/edge persistence
* General Red Team TTPs


## Resources:
### Understanding Kerberos
* https://web.mit.edu/Saltzer/www/publications/Kerberosorigin.pdf
* https://learn.microsoft.com/en-us/windows-server/security/kerberos/kerberos-authentication-overview
* https://www.geeksforgeeks.org/computer-networks/difference-between-kerberos-and-ntlm/
* https://web.mit.edu/Kerberos/#what_is
* https://www.freecodecamp.org/news/how-does-kerberos-work-authentication-protocol/

### Kerberos/Authentication Abuse

* https://github.com/ParrotSec/mimikatz
* https://github.com/GhostPack/Rubeus

### Certificate Abuse

* https://specterops.io/blog/2021/06/17/shadow-credentials-abusing-key-trust-account-mapping-for-account-takeover/
* https://www.ired.team/offensive-security-experiments/active-directory-kerberos-abuse/shadow-credentials
* https://github.com/ShutdownRepo/pywhisker
* https://github.com/eladshamir/Whisker

