# Overview

I assessed the input handling and backend command execution logic of a web application’s feedback functionality. During testing, I identified a blind OS command injection vulnerability caused by unsafe construction of shell commands using user-supplied input. By injecting a payload into the email parameter and leveraging out-of-band techniques via Burp Collaborator, I confirmed arbitrary command execution by exfiltrating the output of a whoami command. This project demonstrates how insufficient input validation can lead to full system compromise.

# Methodology

Step 1: Identified the email parameter in the feedback form as a potential command injection vector.

Step 2: Crafted a payload that executed an OS command and triggered a DNS request to an attacker-controlled Burp Collaborator domain.

Step 3: Monitored out-of-band DNS interactions to detect command execution in the absence of in-band output.

Step 4: Verified successful exploitation by extracting the operating system user from the DNS query.

# Conclusion

This assessment confirmed a critical blind OS command injection vulnerability that allowed remote command execution on the server. The findings highlight the risks of invoking shell commands with untrusted input and the importance of strong input validation and secure execution practices.
