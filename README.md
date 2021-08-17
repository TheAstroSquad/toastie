```
 ▄▄▄        ██████ ▄▄▄█████▓ ██▀███   ▒█████    ██████   █████   █    ██  ▄▄▄      ▓█████▄ 
▒████▄    ▒██    ▒ ▓  ██▒ ▓▒▓██ ▒ ██▒▒██▒  ██▒▒██    ▒ ▒██▓  ██▒ ██  ▓██▒▒████▄    ▒██▀ ██▌
▒██  ▀█▄  ░ ▓██▄   ▒ ▓██░ ▒░▓██ ░▄█ ▒▒██░  ██▒░ ▓██▄   ▒██▒  ██░▓██  ▒██░▒██  ▀█▄  ░██   █▌
░██▄▄▄▄██   ▒   ██▒░ ▓██▓ ░ ▒██▀▀█▄  ▒██   ██░  ▒   ██▒░██  █▀ ░▓▓█  ░██░░██▄▄▄▄██ ░▓█▄   ▌
 ▓█   ▓██▒▒██████▒▒  ▒██▒ ░ ░██▓ ▒██▒░ ████▓▒░▒██████▒▒░▒███▒█▄ ▒▒█████▓  ▓█   ▓██▒░▒████▓ 
 ▒▒   ▓▒█░▒ ▒▓▒ ▒ ░  ▒ ░░   ░ ▒▓ ░▒▓░░ ▒░▒░▒░ ▒ ▒▓▒ ▒ ░░░ ▒▒░ ▒ ░▒▓▒ ▒ ▒  ▒▒   ▓▒█░ ▒▒▓  ▒ 
  ▒   ▒▒ ░░ ░▒  ░ ░    ░      ░▒ ░ ▒░  ░ ▒ ▒░ ░ ░▒  ░ ░ ░ ▒░  ░ ░░▒░ ░ ░   ▒   ▒▒ ░ ░ ▒  ▒ 
  ░   ▒   ░  ░  ░    ░        ░░   ░ ░ ░ ░ ▒  ░  ░  ░     ░   ░  ░░░ ░ ░   ░   ▒    ░ ░  ░ 
      ░  ░      ░              ░         ░ ░        ░      ░       ░           ░  ░   ░    
                                                                                    ░      
```

## Animal Jam Account Takeover Vulnerability Security Advisory

README based on https://github.com/nerdsinspace/leaky-leaky

### Details
**Severity**: High

**Exploit Date**: August 16, 2021

**Public**: August 17, 2021

**Advisory**: August 17, 2021

**Finder**: [MoonMan of AstroSquad](https://www.youtube.com/channel/UCYOqm-bSKqmAnDdP-MYFgdA)

### Vulnerability Scope
This vulnerability affects all Animal Jam accounts.

### Description
A malicious attacker can takeover a Animal Jam account without any authentication for the takeover. This allows a attacker to gain full access to the account, a example for this is impersonation for a famous player.   

### Reproduction
This vulnerability seems to be caused by a failure to validate an account's email when a password reset happens. A attacker can imitate a password reset by sending a post request with certain post-datadata on the endpoint known as [https://api.animaljam.com/game_account/username/send_password_reset/desktop]. The endpoint will accept any email specified in the post-data.

To reproduce this issue an attacker needs to follow the following steps.

   1. Send a post request to the password_reset endpoint
   2. Specify the email address you want to use for the account

### Resolution
This vulnerability needs to be fixed on the server side level of Animal Jam api.

### Notes

Animal Jam is a poorly written game with poor optimization and a CEO that is money hungry, allowing child predators onto the platform because it brings him money. If Animal Jam staff members are reading this, I would advise you to get predators off your game and start reading those in-game reports. The funny part of all of this is possibly that this is the simplest 0day exploit we've seen and proves the lack of security Animal Jam stated. Futhurmore, if you still want to play Animal Jam after this, we are quite disappointed.

PoC was written by HellSec, you can find the original PoC [here](https://github.com/IRIS-Team/AnimalJam-0day)
