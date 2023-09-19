# Authentication and Access Control Vulnerability

Tags: Application Security Weakness, Web Vulnerability, Authentication and Access Control

## Authentication

### Improper Authentication
### Forceful Browsing
### Username Enumeration
### Password Enumeration
### Insufficiently Protected Credentials
### Insufficient Anti-Automation

Occurs when part of the application, such as login forms, polls, comment forms, etc., can be triggered using automated scripting techniques.

**How is this caused?**

Lack of checks to determine if the actions being executed are by a human user. Without certain checks, the app cannot make a decision between user-induced requests or scripted requests.

## Examples of Critical Security Vulnerabilities

### Example 1: Brute Force Attack on a Login System without Account Lockout Mechanism

- The web application has a login system without an account lockout mechanism.
- Attackers launch brute force attacks to discover valid username/password combinations.
- They use automated scripts or tools to systematically guess different combinations until successful.
- Since there is no account lockout mechanism, attackers can make unlimited login attempts.
- Eventually, they gain unauthorized access to user accounts.

### Example 2: Image Processing Bypassing CAPTCHA in a Forum Application

- The web application uses a CAPTCHA mechanism to prevent automated spamming.
- The CAPTCHA mechanism is flawed, allowing attackers to bypass it using image processing techniques.
- Attackers utilize image processing algorithms or tools to accurately interpret CAPTCHA images.
- They can automate the creation of multiple user accounts and post random messages in the forum.
- This bypasses the CAPTCHA, leading to spam flooding the forum.

## Criticality of the Attacks

- Unauthorized Access: Brute force attacks result in unauthorized access to user accounts, compromising sensitive information.
- System Disruption: Spamming attacks overload system resources, causing performance issues or system crashes.
- Reputation Damage: Such attacks can damage the system or organization's reputation, leading to a loss of trust.
- Misuse of Resources: Repetitive actions consume system resources, increasing operational costs and hindering efficiency.

## Glossary

- Lockout Mechanism: A security feature that temporarily disables an account after multiple failed login attempts, protecting against brute force attacks.

### Weak Password Policy
### Insecure Password Change Function
### Insecure Password Reset Function
### Use of Single Factor Authentication

# Session Handling
# Cross-Site Request Forgery

A CSRF occurs when a third party is able to trick a user's web browser into performing actions on the site the user is currently authenticated.

To prevent this, state-changing actions should be protected with a CSRF token.

# Access Control
# Server-Side Request Forgery
# Mass Management
