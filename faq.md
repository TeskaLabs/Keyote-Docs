---
layout: default
title: Keyote FAQ
sidebar: toc
---

# Frequently Asked Questions

<hr/>

## General


### What phones do you support?

Keyote is available for iOS.
We will release a Keyote for Android soon.


### What computer OS do you support?

Keyote is available for macOS.
We will release a Keyote for Windows and Linux soon.


### How Keyote on mobile phone and computer communicates? 

The Keyote consists of two apps:
one is Keyote running on your phone,
second is Keyote running on your computer.

Once paired, these two applications communicate over local networks such as Wi-Fi.
A communication is encrypted, so it could be used over public untrusted networks.

If you have a problem with a connectivity,
please use USB cable or a create a hot spot on the phone and connect your computer to it.


### My phone with Keytoe was stolen, what should I do?

That's unfortunate, but don't worry, keys in the phone are protected by a biometric authorization
(based on the phone type it is Touch ID, Face ID, ...).
The phone requires your approval to use keys.
It is extremely difficult and costly for an attacker to extract Keyote keys from a phone.
Their security is directly attached to a security of the phone
which is a feature that is continuously tested by a phone vendor and by third parties.

More reading: [How secure are Face ID and Touch ID](https://www.howtogeek.com/350676/how-secure-are-face-id-and-touch-id/)  
_Basically, what the attackers need is a complete high resolution, non-smudged copy of your finger print, as well as thousands of dollars worth of equipment._
	
**Practically**: Stop using your current Keyote public keys from the lost phone.
Install a Keyote app on your new phone,
generate a new set of keys
and replace the old ones.


## SSH

### I use password-based authentication to connect over SSH, why should I use Keyote?

It is well known that users reuse passwords or small variations on passwords for different services,
allowing a compromise of one to cause the compromise of many.
Requiring users to remember highly random passwords for every different service is unreasonable,
and many passwords are brute-forceable.
Finally, passwords are annoying to type every time code is pushed or you login to a server.


### I keep my private key in `~/.ssh`, why should I use Keyote?

Any application you run or install can silently read, use, and send off your private key without your knowledge.
Keyote stores keys on the mobile phone, out of the reach of any application.
Also, Keyote requires your explicit permission to use the private key.


### I passphrase encrypt my SSH private key, why should I use Keyote?

A passphrase-encrypted key is decrypted upon entry of the password and given to a running SSH agent.
A user-level process or malware can use a decrypted key stored in an agent without knowledge of the user.
Furthermore, the same malware can pose as an SSH agent and direct SSH to use it using the SSH_AUTH_SOCK environment variable, receiving the key in plaintext the first time it is used.


### I have two-factor authentication enabled on my servers, why should I use Keyote?

Adding two-factor authentication to either password or public key authentication requires changes to every SSH server.
Keyote works out of the box without any changes to a server. 
In some cases, such as third-party hosted services (GitHub, Bitbucket, etc.),
integrating third-party two-factor is impossible.
Many solutions require users to type a 6-digit passcode for every login,
and others rely on a centralized server to perform the two-factor verification.


### I have two-factor authentication enabled on my GitHub account. Why should I use Keyote?

GitHub does not enforce two-factor authentication when you push or pull code with SSH.
Using Keyote requires access to your phone to use the SSH key.


### I use a security token (NitroKey, YubiKey, etc) to store my private key securely. Why should I use Keyote?

With a security token you can generate and store SSH keys in a separate piece of hardware connected via USB.
While the private key might not be extractable from the device, users now have to purchase and carry around another piece of hardware that takes up a USB port.
The attacked can [look over your shoulder](https://en.wikipedia.org/wiki/Shoulder_surfing_(computer_security)) to steal your security token PIN and then steal the token itself.


### Does TeskaLabs, vendor of Keyote, have access to my SSH private key?

No, the SSH private key is generated on the mobile device and never leaves.


### If the SSH private key never leaves my phone, how does it work?

The role of a private key in an SSH login is to sign the SSH handshake.
When a signature is required, your computer calls out to Keyote running on the paired phone with the data that must be signed.
If authorized, Keyote performs the signature using the private key and returns only the signature to the computer.  
It follows [PKCS#11 Cryptography Standard](https://en.wikipedia.org/wiki/PKCS_11).


### How does Keyote affect my SSH client?

Upon install, Keyote adds a few lines to your SSH configuration at `~/.ssh/config` that cause SSH to offer your Keyote key.
Your other keys will still be presented and your Keyote key will only be used if it has access to the service you are connecting to.


### How does my phone communicate with my computer securely?

All communication is encrypted and authenticated using keys related to so-called identity of each device.
These keys are exchanged during a pairing process and pinned for a given communication session.
The communication is futher enhanced by a session-specific key, that prevents replay attacks.


### Can I backup my private key?

Backing up your private key reduces its security to the security of the backup.
We do not currently support backing up or extracting your private key.
In the future we may add key splitting among team members or transferring your private key directly to a new phone.


### Why you are using RSA key for SSH?

Unfortunately, OpenSSH PKCS#11 interface does not support EC keys yet. 


<hr />
Have more questions?  
Mail us at [product-keyote@teskalabs.com](mailto:product-keyote@teskalabs.com)

