# Blue Team Foundations — My Learning Notes

**Learning Area:** SOC Level 1  
**Topic:** Blue Team Introduction  
**Learning Source:** TryHackMe — SOC Level 1 Learning Path

These notes document my understanding of defensive cybersecurity through independent study.

This is my personal learning summary, not an official TryHackMe guide or a reproduction of its lab questions, answers or walkthroughs.

---

## 1. Understanding the Blue Team

The Blue Team represents the defensive side of cybersecurity.

Its primary responsibility is to protect an organization's systems, networks, users and information from potential security threats.

Common responsibilities include:

- Monitoring systems and networks.
- Identifying suspicious activities.
- Investigating security alerts.
- Responding to security incidents.
- Improving security controls.
- Reducing organizational risks.

### What is a SOC?

A Security Operations Center (SOC) is a team or function responsible for coordinating security monitoring and operational response.

A SOC collects and analyzes information from:

- Endpoints and workstations.
- Servers.
- Network devices.
- Identity systems.
- Firewalls.
- Security monitoring platforms.

The objective is to identify suspicious activity and investigate potential threats.

A SOC analyst should not assume every alert represents an actual attack. Investigation and evidence are essential.

## 2. Understanding SOC Analyst Responsibilities

One fundamental SOC activity is alert triage.

Alert triage means reviewing an alert, gathering relevant information, evaluating its importance and deciding what action should happen next.

A typical investigation includes:

1. Alert review.
2. Context gathering.
3. Risk assessment.
4. Documentation.
5. Escalation when necessary.

### Example: Repeated Failed Login Attempts

Imagine a monitoring platform generates an alert because an employee account experiences multiple failed login attempts.

An analyst might investigate:

- Source IP address.
- Failed login timestamps.
- Whether a successful login followed.
- Whether the device or location is unusual.
- Whether other suspicious activities occurred.

Multiple failed attempts alone do not prove an account compromise. The analyst must investigate the surrounding evidence.

---

## 3. SOC Roles and Team Structure

Organizations may divide SOC responsibilities into different levels depending on their size, security requirements and operating model.

A commonly used structure includes Tier 1, Tier 2 and Tier 3.

| SOC Level | Primary Focus | Responsibilities |
|---|---|---|
| Tier 1 | Initial alert triage | Reviews alerts, gathers information and escalates suspicious activities. |
| Tier 2 | Investigation | Performs deeper analysis and supports incident handling. |
| Tier 3 | Advanced analysis | May focus on threat hunting, malware analysis and complex investigations. |

These responsibilities can vary between organizations. Some companies combine multiple roles within the same team.

### Other Cybersecurity Teams

**Incident Response / CIRT**

Coordinates activities when a security incident occurs, including investigation, containment and recovery.

**Security Engineering**

Builds and maintains security technologies, integrations and monitoring capabilities.

**Threat Intelligence**

Studies threat actors, attack campaigns and indicators to help defenders understand potential threats.

**Digital Forensics**

Examines digital evidence to understand what happened during a security incident.

**GRC (Governance, Risk and Compliance)**

Focuses on security policies, risk management and regulatory requirements.

**Red Team**

Performs authorized security simulations to evaluate an organization's defensive capabilities.

### SOC vs Incident Response

A SOC is an operational function responsible for security monitoring and coordination.

Incident Response describes the activities and capabilities used to manage security incidents.

They work closely together, but they are not identical.

---

## 4. Security Must Support the Business

Cybersecurity is not only about technical tools. Security teams must also understand the organization they protect.

Different organizations have different priorities.

For example:

- A hospital must protect patient information and healthcare services.
- A bank must protect customer accounts and financial transactions.
- A manufacturing company must protect production systems and operational continuity.

This is why understanding business impact is important when evaluating security incidents.

### The CIA Triad

The CIA Triad represents three fundamental principles of information security.

**Confidentiality**

Information should only be accessible to authorized individuals.

**Integrity**

Information should remain accurate and protected from unauthorized modification.

**Availability**

Systems and information should be accessible whenever authorized users need them.

A security incident can affect one or more of these principles.

### My Key Understanding

Security decisions should consider both technical risk and business impact. An incident affecting a critical production system may require a different response priority from an incident involving a low-impact test system.

---

## 5. People as a Target

Technology is not the only target in cybersecurity. Attackers also target people because employees have access to emails, applications, internal systems and sensitive information.

This is where **social engineering** becomes important.

Social engineering involves manipulating or deceiving individuals into performing actions that benefit an attacker.

### Common Social Engineering Techniques

**Phishing**

Fraudulent emails or messages designed to trick users into clicking malicious links, opening attachments or sharing sensitive information.

**Impersonation**

Pretending to be a trusted individual or organization to gain someone's confidence.

**Vishing**

Using voice calls to manipulate individuals into revealing information or performing an action.

**Smishing**

Using deceptive SMS messages to deliver malicious links or fraudulent requests.

**Malicious Downloads**

Convincing users to download or execute harmful software.

**Physical Social Engineering**

Attempting to gain unauthorized physical access through deception, such as following an authorized employee into a restricted area.

### How Can Organizations Reduce These Risks?

- Security awareness training.
- Email security and phishing protection.
- Multi-factor authentication.
- Strong identity verification procedures.
- Endpoint protection.
- Suspicious email reporting mechanisms.
- Clear procedures for sensitive requests.

### What Can a SOC Detect?

A SOC may correlate email activity, identity events and endpoint logs.

For example, a suspicious email followed by an unusual login attempt and unexpected device activity may indicate a potential security incident.

Looking at multiple events together provides a clearer picture than investigating each event separately.

---

## 6. Systems as a Target

Attackers may also target technology directly.

A system could be a:

- Laptop or workstation.
- Server.
- Network device.
- Web application.
- Virtual machine.
- Cloud service.

Once an attacker compromises one system, they may attempt to move to other systems, obtain additional privileges, access sensitive information or disrupt services.

### Common System Security Risks

**1. Software Vulnerabilities**

A weakness in software design or implementation that could potentially be exploited by an attacker.

Example: An unpatched vulnerability in a web server.

**2. Misconfigurations**

Incorrect or unsafe system settings, permissions or deployment configurations.

Example: A cloud storage resource configured to allow unauthorized public access.

**3. Supply Chain Attacks**

Attacks that target trusted vendors, software dependencies, update mechanisms or other components in the software supply chain.

### Vulnerability vs Misconfiguration

| Vulnerability | Misconfiguration |
|---|---|
| A weakness in software or hardware. | An unsafe setting or deployment choice. |
| May require a security patch or software upgrade. | Usually requires correcting settings or permissions. |
| Example: An unpatched software flaw. | Example: An unnecessarily exposed service. |

### Understanding CVE and Zero-Day

**CVE (Common Vulnerabilities and Exposures)**

A standardized identifier assigned to a publicly known cybersecurity vulnerability.

**Zero-Day Vulnerability**

A vulnerability that is exploited or known to attackers before a security fix is available to defenders.

### How Organizations Reduce System Risks

- Maintain an inventory of assets.
- Apply security patches regularly.
- Review configurations and permissions.
- Remove unnecessary services.
- Perform vulnerability assessments.
- Monitor endpoint, server and network activities.
- Conduct authorized security assessments.

### My Key Understanding

People and systems are connected in cybersecurity. A phishing attack can lead to stolen credentials, unauthorized access and potentially further compromise of organizational systems.

Defending an organization requires protecting both its people and its technology.

---

## 7. How These Security Areas Connect

One of my biggest takeaways from studying Blue Team fundamentals is that people, identities and technology are connected.

Consider this hypothetical scenario:

1. An employee receives a deceptive email.
2. The employee enters their credentials into a fraudulent website.
3. An attacker attempts to use the stolen credentials.
4. An identity monitoring system detects an unusual sign-in.
5. Endpoint and cloud logs provide additional context.
6. SOC analysts correlate the available evidence.
7. The security team determines whether escalation and incident response are required.

This scenario connects multiple areas of cybersecurity.

| Security Area | Role in the Scenario |
|---|---|
| IAM | Protects identities and controls access to resources. |
| SOC / TDR | Detects, investigates and responds to suspicious activity. |
| Vulnerability Management | Helps identify and reduce weaknesses in systems. |
| Security Awareness | Helps employees recognize and report deceptive activity. |
| Security Automation | Can help with repetitive investigation and evidence gathering. |

I want to explore these connections further as I continue learning cybersecurity.

---

## 8. My Learning Reflection

This section captures my personal understanding of the concepts I explored while studying Blue Team fundamentals.

Rather than simply collecting definitions, I want to understand how security concepts connect to real-world security operations.

### What I Learned

One important takeaway from this learning experience is that cybersecurity monitoring involves much more than identifying alerts.

A SOC analyst needs to understand the context behind an event, correlate information from different sources, evaluate potential risks and make evidence-based decisions.

I also learned how people, identities and systems can become connected parts of a security incident.

### Concepts I Want to Explore Further

| Concept | What I Want to Understand Better |
|---|---|
| Alert Triage | How analysts determine whether an alert requires investigation. |
| SIEM | How logs from different sources are collected and correlated. |
| Incident Response | How security teams investigate, contain and recover from incidents. |
| Identity Security | How suspicious authentication and access activities are detected. |
| Threat Detection | How detection rules identify suspicious behaviour. |

### Practical Learning Goals

My next learning objectives are:

- Understand Windows authentication and security event logs.
- Explore how SIEM platforms collect and correlate events.
- Practise analysing suspicious login activities.
- Understand the relationship between MITRE ATT&CK techniques and security detections.
- Learn how SOC analysts document and escalate security incidents.

### My Current Perspective

I see Blue Team operations as a combination of technology, investigation, analytical thinking and decision-making.

Tools can generate alerts and provide useful information, but understanding the evidence and determining the appropriate response require security knowledge and human judgment.

As I continue learning, I want to strengthen my practical investigation skills and understand how defensive security operations work in real environments.

---

## 9. Key Takeaways

- Blue Team activities focus on protecting an organization's systems, people and information.
- A SOC coordinates security monitoring and operational response.
- Alert triage requires investigation, context and evidence.
- SOC responsibilities vary across organizations.
- Incident response and SOC operations are connected but have different meanings.
- Social engineering targets people through deception and manipulation.
- Technical attacks can exploit vulnerabilities and misconfigurations.
- CVEs provide standardized identifiers for publicly known vulnerabilities.
- Effective cybersecurity requires prevention, monitoring, investigation, response and continuous improvement.

---

## Learning References

- [TryHackMe — SOC Level 1 Learning Path](https://tryhackme.com/path/outline/soclevel1)

*These notes are an independent learning summary written in my own words. They are not an official TryHackMe publication and do not reproduce room questions, answers, flags or walkthrough solutions.*
