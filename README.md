Intelbras NVD 9032 R Ftd – Critical Password Reset Vulnerability

Discovered by: Theo Cia

CVE: Pending Assignment
Status: Reported to vendor
Date Discovered: November 2025
Impact: Full administrative access via MFA bypass
Firmware: V2.800.00IB00C.0.T
Build Date: 2022-08-17


🛡️ Summary

A critical vulnerability in the Intelbras NVD 9032 R Ftd IP CFTV device allows an attacker to bypass the multi-factor authentication during password recovery. This results in the ability to change the admin password and gain full access to the administrative panel.

⚠️ Vulnerability Details

Affected component: Password recovery endpoint

Vulnerability class: Improper Access Control (CWE-284)

Attack vector: Web-based response manipulation (interception/proxy)

Steps to reproduce:

Go to the login page and click on Forgot Password.

Submit any user email or phone number (targeting the admin account).

Intercept the HTTP POST response after submitting the MFA code.

Modify the server response from:

{"result":false,"error":"internal error","id":6}


to:

{"result":true,"id":6}


Submit the form. The password will be updated even without a valid code.

Use the new password to log in as admin.

🎯 Impact

This vulnerability allows unauthenticated attackers to:

Reset the admin password

Bypass multi-factor authentication

Gain full administrative access to the NVR panel

🔒 Mitigation

No official fix is available as of the publication date. Intelbras has been notified.

📩 Contact

For more information or coordination, please contact:
theo.cia@guardsi.com.br
