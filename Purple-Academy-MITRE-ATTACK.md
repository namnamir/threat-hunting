# 0 - The Absolute Beginners Guide to MITRE ATT&CK
## Fundamentals of the MITRE ATT&CK® Framework
- An "Indicator of Compromise (IoC)" is the evidence that a cyberattack has taken place.
- Pyramid of Painby David Bianco shows how difficult it is to collect and apply the IOC to a cyber defense tool. For instance, Hash Valuesare easierto use than Tools. But theyare notvery effective.
  - At the apex of the pyramid, we have TTPs (Tactics Techniques and Procedures).
![Pyramid of Pain](img/pyramid-of-pain.jpeg)

- Defender's Dilemma:The adversaryonly needstobreachone of thevictims in orderto compromise theenterprise. So, only one of the victims is breached, the attacker can move laterally inside the enterprise.
- The Adversary's Dilemma: The defender only needs to detect one of the indicators of the adversary's presence to initiate incident response within the enterprise. So defenders only need to detect one indicator.
  - Also, we can detect one step in a TTP in the TTP chain; we can detect all other steps. And sometimes attackers use defense bypass techniques so we wouldn't be able to detect every step.
- Tactics, Techniques, Procedures (TTP)
    - **Tactics** are the adversary's technical goals.These are our 14 row headings.
    - **Techniques** are how those goals are achieved - methods used to accomplish a tactic. So, for initial access, you can either send a spearphishingattachment or exploita public-facing application like an Apache server.
    - **Procedures** are specific implementations of techniques.
    - At the moment, ATT&CK for Enterprise contains 14 tactics, 177 techniques, and 348 sub-techniques.
- For your defenses to be more robust, we should not aim to block malware hashes or IP addresses. Instead, we should try to block the set of techniques used by the malware.
- Each high-level component of ATT&CK is related to the other componentsin some way. "Adversary Group" is our starting point. They use "Techniques"to accomplish "Tactics". Adversaries also use (malicious) "Software" that implements these techniques. Each technique includes "Procedure" examples by APT groups and malwareand includes "Mitigation" suggestions and "Detection" suggestions. "Data sources" and metadatahelpdetection.
![Mitre Att&ck Modle Relationship](img/mitre-attack-model-relationships.png)
