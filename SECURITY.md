# Security

The projects published in Github based on `VOTING Ausmittlung` are made available as part of a public bug bounty program.

## Code of Conduct

This project uses the [Code of Conduct](./CODE_OF_CONDUCT.md) to define expected conduct in our community.

Instances of abusive, harassing, or otherwise unacceptable behavior may be reported by contacting a project maintainer at psirt-voting@abraxas.ch

## Bug Bounty Policy

### Overview

The Bug Bounty Program is part of the Program as defined in the [Code of Conduct](./CODE_OF_CONDUCT.md) available on GitHub.
This Bug Bounty Policy (also called Security Policy) complements the [Code of Conduct](./CODE_OF_CONDUCT.md) with Bug Bounty specific rules and regulations.
The System subject to the Program including this Bug Bounty Program has the Abraxas product name `VOTING Ausmittlung`. The product `VOTING Ausmittlung` and its infrastructure include for example:

- `VOTING Ausmittlung` (Backend)
- `VOTING Ausmittlung Erfassung` (Frontend)
- `VOTING Ausmittlung Monitoring` (Frontend)
- `VOTING Basis` (Backend & Frontend)
- `VOTING IAM` (Identity and Access Management)

We will from time to time as considered necessary issue an updated version of this Bug Bounty Policy.

### Program Rules

The rules and regulations established in the [Code of Conduct](./CODE_OF_CONDUCT.md) and this Bug Bounty Policy are binding for this Bug Bounty Program.

#### Legal Safe Harbor

Abraxas values a constructive and fair collaboration with the participants of the Program. Abraxas will not take legal actions against participants in this Bug Bounty Program, as long as participants act in good faith and in accordance with the [licence agreement](./CODE_OF_CONDUCT.md#license-source-code-permitted-use), this Bug Bounty Policy, the provisions of the [Code of Conduct](./CODE_OF_CONDUCT.md) and the applicable laws. Under these conditions:

- We interpret activities by participants within this Program as authorized access under the Swiss Penal Code. This includes Swiss Penal Code paragraphs 143, 143bis and 144bis.
- We will not file a complaint against participants within this Program for trying to circumvent the security measures deployed in order to protect the services in-scope for this Program.
- If legal action is initiated by a third party against a participant within this Program, we will take reasonable measures supporting the participant to defend the claim of the third party.

Any non-compliance with the licence agreement, [Code of Conduct](./CODE_OF_CONDUCT.md), this Bug Bounty Policy, and the applicable laws may result in exclusion from the Program and legal prosecution. For minor breaches, a warning may be issued. For severe breaches, Abraxas reserves all rights provided by applicable laws.

#### Basic Principles

All activities leading to the discovery of a vulnerability:

- are within the scope permitted by law (see section Legal Safe Harbor);
- are within the Program;
- may result in a bounty to be paid to you. The amount of compensation is based on the criticality of the vulnerability and the quality of the documentation submitted to Abraxas;
- shall not destroy, interrupt or lower the Services and Products used by Abraxas (and its customers and partners);
- shall respect the intellectual property rights and other rights of Abraxas, its customers and third-parties;
- shall not result in third-party data to be spied on or disclosed.

#### Eligibility Bug Bounty Program

- This is a public Program – everyone can participate
- We reserve the right to terminate the Program at any moment and not accept nor award any new vulnerability reports. This termination will be announced by Abraxas suitable means
- You must avoid tests that could cause degradation or interruption of our service (refrain from using automated tools and limit yourself about requests per second)
- You must not leak, manipulate, or destroy any user data
- Only test with user accounts that are under your control
- You must not be a former or current employee of Abraxas, the directly involved customers of the system, Bug Bounty Switzerland, one of its contractors or project participants within the last six months
- Strictly follow a “report first” approach (in contrast to “exploit first”). All activities that are not absolutely necessary to identify a vulnerability should be omitted and permission asked to further exploit
- Any vulnerability must be reported exclusively through the channel specified in the [Submission Guidelines (CoC)](./CODE_OF_CONDUCT.md#submission-guidelines)

#### Responsible Vulnerability Disclosure

Vulnerability disclosure is possible since the start of the public phase of the Program, respecting the “Responsible Vulnerability Disclosure” section in the [Code of Conduct](./CODE_OF_CONDUCT.md). Abraxas will communicate transparently about results and will credit researchers publicly, if agreed.

#### Reporting Requirements

Please ensure to report only findings with a real impact on security of the product `VOTING Ausmittlung` and report clear proof of concepts that demonstrate the scenario.

Please make sure to complete your report in accordance with the guidelines set forth in the [Submission Guidelines (CoC)](./CODE_OF_CONDUCT.md#submission-guidelines).

### Scope

|System|URL|Description|
|---|---|---|
|VOTING Basis|<https://bbt.vo.abraxas-apps.ch/basis/*>|UI|
|VOTING Ausmittlung Erfassung|<https://bbt.vo.abraxas-apps.ch/ausmittlung/erfassung/*>|UI|
|VOTING Ausmittlung Monitoring|<https://bbt.vo.abraxas-apps.ch/ausmittlung/monitoring/*>|UI|
|API|<https://bbt.vo.abraxas-apis.ch/*>|VOTING Services API|
|VOTING IAM IdP|<https://pre.abraxas-vo.sec.abraxas-apps.ch/authorize>|UI|
|VOTING IAM self services|<https://pre.abraxas-vo.sec.abraxas-apps.ch/myaccount>|UI|
|VOTING IAM API|<https://pre.abraxas-vo.sec.abraxas-apis.ch/>| IAM Services API|

Should you identify an interesting but out-of-scope target you can attribute to `VOTING Ausmittlung`, please report it and ask for permission to test it.

Vulnerabilities on the IdP system `VOTING IAM` are in scope if they affect the integration with the product `VOTING Ausmittlung` (e.g. vulnerabilities in the exchange of tokens, on the authentication flow, self services of the user).

The source code of `VOTING IAM` is not covered by the source code publication.

The source code included in the public Bug Bounty Program can be used for identification of exploitable/demonstrable vulnerabilities.

### Out-of-Scope and general information

`VOTING IAM` administrator use cases such as identity (lifecycle) management is not in-scope. The available accounts (see below) do not have according permissions for administration use cases.

The following statements refer to the `VOTING Basis` application.

- Master data must not be changed. These can be found in the navigation `Auszählungskreise` (Counting Circles) and `Wahlkreise` (Domain of influence).
- No contests, votes or elections may be deleted.
- New contests, votes and elections may be created, but not in the pre-defined contests.
- Test data will be reset every Wednesday morning 11 to 12 am (CEST). Initially just once a week to allow more time to manage the test data. The rhythm will eventually be adjusted. If necessary, we reserve the right of resetting the test data in between.

The self-registration website to create test users is not a productive component of the system. It is only a helping system for you in order that you can log in the application. This component is out of scope.

### Account Access

No user accounts are required for the pentests. However, test users can be generated by the "self-registration form" for a more substantial result. To do so, register yourself on the [Bug Bounty Platform](https://www.bugbounty.ch/abraxas/) and follow the instructions described there.

Afterwards, the following users and roles will be made available to you:

|User|Tenant|Application(s)|role(s)|
|---|---|---|---|
| Wahlverwalter<br />(election supervisor, in our setup authorized for the state chancellery) | Kanton XY<br />(canton XY) | VOTING Basis<br /><br />VOTING Ausmittlung Erfassung<br /><br />VOTING Ausmittlung Monitoring<br /><br />VOTING IAM | Wahlverwalter<br />(election supervisor) |
| Wahlverwalter<br />(election supervisor, in our setup authorized for the municipality) | Gemeinde XY<br />(municipality XY) | VOTING Basis<br /><br />VOTING Ausmittlung Erfassung<br /><br />VOTING Ausmittlung Monitoring<br /><br />VOTING IAM | Wahlverwalter<br />(election supervisor) |
| Erfasser<br />(editor, in our setup authorized for the municipality) | Gemeinde XY<br />(municipality XY) | VOTING Ausmittlung Erfassung<br /><br />VOTING IAM | Erfasser<br />(editor) |

### Qualifying Vulnerabilities

Everything with a real impact on security of `VOTING Ausmittlung` – e.g.:

- Remote code execution (RCE)
- Local files access and manipulation (LFI, RFI, XXE, SSRF, XSPA)
- Code injections (HTML, JS, SQL, PHP, ...)
- Cross-Site Scripting (XSS)
- Cross-Site Requests Forgery (CSRF) with real security impact
- Session Management
- Identitification and authentication failures
- Insecure direct object references (IDOR)
- CORS with real security impact
- Broken access control: Horizontal and vertical privilege escalation
- Source code findings with a measurable and provable impact on the System and its users

### Non-Qualifying Vulnerabilities

- All attacks which can be considered denial of service, resource starvation or brute force attacks
- Social engineering
- Physical attacks on people, buildings and devices
- Issues that require physical access to a victim’s computer/device
- For source code findings: Code smell or missing best practices
- For system or infrastructure: Missing best practices or other guidelines which do not indicate a security issue.
- Testing for weak credentials of prepared test users in the System
- Known issues listed on [Exclusions](./Exclusions.pdf)
- "Self" XSS
- Missing cookie flags on non-sensitive cookies
- Missing "HTTP Host Header" XSS
- Clickjacking/UI redressing
- Stack traces or path disclosure unless they leak sensitive information
- Software version disclosure
- Presence of autocomplete attribute on web forms
- Lack of HTTP Strict Transport Security Header
- Missing security-related HTTP headers which do not lead directly to a vulnerability
- SSL/TLS best practices
- Mixed content warnings
- Logout and other instances of low-severity Cross-Site Request Forgery
- Vulnerabilities related to E-Mail Server Configuration
- Vulnerabilities affecting outdated browsers or platforms
- Reports from automated web vulnerability scanners that have not been validated by hand
- Recently disclosed 0-day vulnerabilities
- Any hypothetical flaw or best practices without exploitable POC
- Bypassing rate-limits or the non-existence of rate-limits
- Username / email enumeration

### Reward Grid

The Abraxas Bug Bounty Grid defines in which framework and methodology bounties can be defined. It is based on the CVSS Scoring Model. Please note that in a normal, productive setting `VOTING Ausmittlung` is not exposed to the Internet. For the Public Bug Bounty, the following static grid is used.

#### Bounties

|Scope|Low|Medium|High|Critical|
|---|---|---|---|---|
|1.	VOTING Ausmittlung (Backend)<br />2.	VOTING Ausmittlung Erfassung (Frontend)<br />3.	VOTING Ausmittlung Monitoring (Frontend)<br />4.	VOTING Basis (Backend & Frontend)<br />5.	VOTING IAM|CHF 500|CHF 1'500|CHF 4'000|CHF 10'000|

#### Scenarios

Additionally, there are specific scenarios for which Abraxas is prepared to offer special bounties. These bounties apply to all scopes and will be paid instead of the above CVSS based bounties (and not additional to them), if applicable.

|No.|Scenario|Examples|Bounty Range|
|---|---|---|---|
|1|Tampering of the system so that election results can be changed without the possibility of detection on the part of the service provider.| - Tampering of counting results<br />- Tampering of used algorithms| CHF 15'000 - CHF 30'000|
|2|Detection of errors in the calculation basis of the vote count/result determination, which could lead to an incorrect election result| - Detection of logic errors, that results could not be considered<br />- Incorrect application of given calculation algorithms (e.g. Hagenbach-Bischoff method)| CHF 15'000 - CHF 30'000|
|3|Tampering in the generation & transmission of the election results in the system VOTING Ausmittlung to the publication systems of the cantons, so that results can be changed, without detection possibility on the part of the service provider| - Tampering during transmission to the publication systems <br /> - Tampering at the output document, which is transmitted| CHF 10'000 - CHF 25'000|
|4|The system can be tampered with in such a way that it is highly unlikely that the results will be delivered on time on election Sunday (excl. DoS/DDoS attacks)|-	Encryption of the required user data in the system <br /> - Corruption of data in the central storage system <br /> - Destruction of entire database systems (clusters) that a complete disaster recovery process must be initiated including control of the current data inventory.| CHF 10'000 - CHF 15'000|

Rewards are distributed at the discretion of Abraxas.

#### Eligibility Bounties

- You must be the first reporter of a vulnerability to be eligible for a bounty
- The vulnerability must be a qualifying vulnerability or enter in one of the categories of the specific scenarios to be eligible for a bounty
- In case of exploits on different endpoints, parameters or components caused by the same underlying weakness, we reserve the right to honor only the first report and reject the subsequent ones as 'Duplicate' or 'Informative' depending on the case.
- Claims related to the reporting of a vulnerability before, after or without actually reporting a vulnerability are not considered by Abraxas.
