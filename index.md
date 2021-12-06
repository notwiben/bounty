## Welcome to SIRCLO Bounty Page

# Rules
The following requirements must be adhered to in order to participate in SIRCLO’s bounty program :
- We investigate and respond to all valid reports. Due to the volume of reports we receive, though, we prioritise evaluations based on risk and other factors, and it may take some time before you receive a reply.
- We determine bounty amounts based on a variety of factors, including (but not limited to) impact, ease of exploitation, and quality of the report. Note that extremely low-risk issues may not qualify for a bounty at all.
- We seek to pay similar amounts for similar issues, but bounty amounts and qualifying issues may change with time. Past rewards do not necessarily guarantee similar results in the future.
- In the event of duplicate reports, we award a bounty to the first person to submit an issue. (Capacity determines duplicates and may not share details on the other reports.) A given bounty is only paid to one individual.
- Your participation in this program must not disrupt or compromise any data that does not belong to you. Any attacks against other users or company data without provable express consent are prohibited and will automatically disqualify you from participating in the program.
- You must not disclose the issue to the public or a third-party before it has been fixed and prior written consent from SIRCLO.
- You must comply with any applicable laws and regulations in connection with your participation in this program. 
- SIRCLO’s development team, employees and all other affiliates are not eligible for rewards.

SIRCLO’s bug bounty program is not a contest or competition. It is an experimental and discretionary rewards program. We may modify the terms of this program or terminate this program at any time without notice. All decisions as to the amount and type of rewards that may be issued, the method of payment (for monetary rewards), and whether or not any reported issue constitutes a significant risk or is eligible for a reward, will be determined at SIRCLO’s complete discretion in each case.

# Scope

We are interested in any vulnerability that could negatively affect the security of our users.

## In-Scope Vulnerability Classes
- Cross-site Scripting (XSS)
- Cross-site Request Forgery
- Server-Side Request Forgery (SSRF)
- SQL Injection
- Server-side Remote Code Execution (RCE)
- XML External Entity Attacks (XXE)
- Access Control Issues (Insecure Direct Object Reference issues, etc)
- Exposed Administrative Panels that don't require login credentials
- Directory Traversal Issues
- Local File Disclosure (LFD)

## In-Scope Properties
- *.mysirclo.com
- *.mysirclo.id
- *.sirclo.me
- *.sirclo-integrations.com
- *.sirclo.com

## Out-of-scope Vulnerability Classes
- Open redirects. 99% of open redirects have low security impact. For the rare cases where the impact is higher, e.g., stealing oauth tokens, we do still want to hear about them.
- Publicly accessible login panels - These generally have low security impact and are in software that SIRCLO runs but doesn’t control.
- Reports that state that software is out of date/vulnerable without a proof of concept.
- Host header issues without an accompanying proof-of-concept demonstrating vulnerability.
- XSS issues that affect only outdated browsers.
- Stack traces that disclose information.
- CSV injection. Please see [this article](https://sites.google.com/site/bughunteruniversity/nonvuln/csv-excel-formula-injection).
- Best practices concerns.
- Highly speculative reports about theoretical damage. Be concrete.
- Self-XSS that can not be used to exploit other users (this includes having a user paste JavaScript into the browser console).
- Vulnerabilities as reported by automated tools without additional analysis as to how they're an issue.
- Reports from automated web vulnerability scanners (Acunetix, Vega, etc.) that have not been validated.
- Denial of Service Attacks.
- Reflected File Download (RFD).
- `window.opener`-related issues.
- Physical or social engineering attempts (this includes phishing attacks against SIRCLO employees).
- Content injection issues.
- Cross-site Request Forgery (CSRF) with minimal security implications (Logout CSRF, etc.)
- Missing autocomplete attributes.
- Missing cookie flags on non-security-sensitive cookies.
- Issues that require physical access to a victim’s computer.
- Missing security headers that do not present an immediate security vulnerability.
- Fraud issues (please see the below section elaborating on this).
- SSL/TLS scan reports (this means output from sites such as SSL Labs).
- Banner grabbing issues (figuring out what web server we use, etc.).
- Open ports without an accompanying proof-of-concept demonstrating vulnerability.
- Recently disclosed 0day vulnerabilities. We need time to patch our systems just like everyone else - please give us two weeks before reporting these types of issues.
- Entering the Srclo offices, throwing crisps everywhere, unleashing a bunch of hungry racoons, and hijacking an abandoned terminal on an unlocked workstation while staff are distracted.

## Out-of-scope Properties
- internal site
- staging site

# Rewards

Our rewards are impact-based. This means, for example, that we will issue a relatively high reward for a vulnerability that has the potential to leak sensitive user data, but that we will issue little to no reward for a vulnerability that allows an attacker to deface a microsite. When we have our reward meetings, we always ask one question: If a malicious attacker abuses this, how bad off are we? We assume the worst and pay out the bug accordingly.

If we receive several reports for the same issue, we offer the bounty to the earliest report for which we had enough actionable information to identify the issue. We don't want to encourage people spamming us with vague issues in an attempt to be first.

If a single fix fixes multiple vulnerabilities, we treat this as a single vulnerability.  For example, if you find 3 vulnerabilities in a WordPress plugin we use, and our fix is to remove the plugin, this will receive a single bounty, determined, as always, by impact.

The bounty category on this page are guidelines to express roughly how we think about the severity of classes of issues. They are not exact rules. There can be attributes of bugs that make them more or less severe, which will affect the payout. For example, if a vulnerability affects only a small population of users, it will likely receive a lower reward than a similar vulnerability that affects a larger population of users. To date, we have most commonly rewarded on the top end of our published bounty category.

At the end of the day, all reward amounts are at our discretion, but we aim to be fair. Some researchers won't agree with some of our decisions, but we're paying out to the best of our ethical ability and trust that the majority of researchers will consider their rewards fair and in many cases generous. We will adapt as the program continues.

## Things you should expect to receive little to no bounty for
- Microsites with little to no user data
- Issues requiring user-interaction
- Outdated wordpress instances
- Most brute forcing issues

## Bounty Category
N.B: the amounts listed here are the maximum we can pay for these categories of issues. This is meant as rough guidance on how we think about rewarding issues, ultimately we will reward largely based on the impact of the issue but at our discretion. 

- **Critical issues** - Remote code execution on a production server. Exposure of information that identifies individuals (social security numbers, credit card numbers, bank account numbers, driver license images) Full account takeover of rider/partner account without interaction. Payment or partner invoice information exposure at scale. Potential access to source code. XSS in Toolshed (our internal account management system), or server-side request forgery (SSRF). Vulnerabilities leading to the compromise of an employee account (with a way to bypass two-factor).

- **Significant Issues** - Stored Cross-site Scripting which can cause significant brand damage (e.g. in a homepage), missing authorization checks leading to the exposure of email addresses, date of birth, names, phone numbers, etc.

- **Medium Issues** - Reflected Cross-site Scripting (XSS), most Cross-site Request Forgery (CSRF) issues, access control issues which do not exposed PII but affect other accounts, some account validation bypasses (being able to change driver picture, etc). Any vulnerability which allows the bulk lookup of user UUIDs (e.g. turn an auto-incrementing ID into a UUID, turn an email into a UUID).

- **Fraud Issues** - - Send these to `ext-fraud@sirclo.com`. We currently do not reward for fraud issues. 

## Submission
Though we welcome reporting of non-security issues, please note that only genuine security issues are eligible for rewards. If you have found a vulnerability, we would love to work with you to resolve it:
- Please email us at bugs[at]sirclo.com with the subject “[Bug Bounty SIRCLO] - Vulnerability Name”. Please do not contact employees directly or through other channels about a report.
- Within the body of the email, please describe the nature of the bug along with any steps required to replicate it, vulnerable component (API, FQDN, Deep URL), as well as pertinent applications, programs or tools used to discover the bug and the date and time testing took place.
- Include your legal name, phone number, and IP address at time of testing with your submission.
# Miscellany

## Reporting Guidelines
We need detailed written steps to reproduce. We do not accept reports that include only a video.

## Policy Changes
You can view the changes to this policy over time at [bounty.sirclo.com](https://bounty.sirclo.com).

## Fraud issues
If you’d like to report an issue related to fraud, please contact ext-fraud@sirclo.com. These type of issues are important but we unfortunately cannot reward issues if this type at this time. Specifically promo code fraud and give-get fraud is abuse of our promotional offers and referral codes in order to get free rides from SIRCLO are a common submission. We do not consider these in scope for our bug bounty program at this time unless they show an explicit technical vulnerability in our software.  Lack of verification for things such as phone numbers, credit cards, etc are all fraud related issues and are not in scope for this bug bounty program.

## Examples of good bugs
- https://fin1te.net/articles/uber-turning-self-xss-into-good-xss/
- http://blog.portswigger.net/2016/04/adapting-angularjs-payloads-to-exploit.html
- http://blog.orange.tw/2016/04/bug-bounty-uber-ubercom-remote-code_7.html
- https://labs.integrity.pt/articles/uber-hacking-how-we-found-out-who-you-are-where-you-are-and-where-you-went/

# Frequently Asked Questions

## Can I blog about my bug?
Yes, but we ask that you wait until the issue is both fixed and paid out before you publish the blog post. We also prefer that you request disclosure through HackerOne so that readers of your blog post can get the full background on the issue.

## What is your policy on chaining bugs and privilege escalation?
Chaining of bugs is not frowned upon in any way, we love to see clever exploit chains! However, if you have managed to compromise an SIRCLO-owned server we do not allow for escalations such as port scanning internal networks, privilege escalation attempts, attempting to pivot to other systems, etc. If you get access to an SIRCLO server please report it us and we will reward you with an appropriate bounty taking into full consideration the severity of what could be done. Chaining a CSRF vulnerability with a self XSS? Nice! Using AWS access key to dump user info? Not cool.

## Do you provide test accounts?
As of this time we do not have a good system for creating test accounts for our bug bounty submitters. Please create an account as you would normally and perform testing with that account or accounts.  Whenever possible only test against yourself, never other users. If there is ever a situation where you cannot test a bug while adhering to this please let us know and we will help figure out an appropriate solution.

## What about public disclosure?
Found a particularly interesting or clever bug in an SIRCLO service? We’re more than happy to publicly disclose your bug once it has been remediated by our developers. Please note that in certain situations we may request more time to investigate an issue internally to ensure that it is properly fixed across all SIRCLO services. Public disclosure before SIRCLO has had time to remediate an issue is grounds for immediate forfeiture of any reward as well as possible removal from the bug bounty program.

## What is an SIRCLO microsite?
An SIRCLO microsite is a website which is not explicitly listed in the scope above but is made by an SIRCLO employee and owned by SIRCLO. The most common examples of microsites include SIRCLO city sites, blogs, and partner incentive sites.

## Are SIRCLO microsites (for example, our blogs and city-specific SIRCLO sites) in scope?
Microsites are an important part of how SIRCLO reaches people in diverse local markets all around the world. Since they have smaller audiences, shouldn't contain much or any user data and aren’t part of the our core services, the impact of issues on these sites is significantly less severe. Since we are primary interested in vulnerabilities which could lead to the exfiltration of customer information, vulnerabilities in microsite services will not be rewarded for except in extraordinary circumstances. 

# Program terms
Your participation in the Bug Bounty Program is voluntary and subject to the [Bug Bounty Program Terms](https://bounty.sirclo.com/).
