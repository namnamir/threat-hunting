
# RISK ASSESSMENT

## Introduction

An important tool that Information Technology (IT) managers use to evaluate the security of the IT systems that they manage and to determine the potential for loss or harm to organizational operations, mission, and stakeholders is a Risk Assessment. IT managers use this tool to evaluate the security of the IT systems that they manage. Management is given the capacity to do the following thanks to the risk assessment:

- Ensure that the information technology (IT) applications and systems have an acceptable degree of security protection.
- Ensure that your information and network security adhere to all applicable federal, state regulations.
- Appease the entities responsible for monitoring.
- Determine the maximum amount of danger that may be tolerated.

The presence of risk can never be completely removed, but it may be mitigated by the implementation of appropriate information technology security procedures. The decision as to what level of risk will be accepted will be based on management's review of the identified IT security controls needed to mitigate risk versus the potential impact of implementing those controls on available resources and system operations. This review will determine which level of risk will be acceptable. The Risk Assessment evaluates the current degree of risk associated with the application and gives suggestions for mitigating that risk for management to examine. The Risk Assessment is used as the principal access control function for a wide variety of mission-critical applications. If these applications were to become unavailable or lose their integrity, it would have a crippling effect on the organization's ability to carry out its goals. The importance of the system to the company is reflected both in the sensitivity level of the system itself and in the information that is either stored inside the system, processed by the system, or communicated by the system. The degree of sensitivity was utilized as the foundation for developing and implementing the essential information technology security measures for the system.

The executive, legislative, departmental, and technical requirements serve as the foundation for this risk assessment, which details the vulnerabilities of the organization and the related risks. The Security Program is responsible for establishing both the policy and the organizational and managerial responsibility to carry it out. This ensures that the appropriate controls are put into place. The approach for doing the security risk assessment is derived from the Risk Management Guide for Information Technology Systems, Special Publication 800-30 published by the National Institute of Standards and Technology (NIST).

## Purpose

An analysis of how well the management, operational, and technological security measures that are now in place to protect the organization have been included as one of the goals of this report, which is to offer the Operating Administration management with such an analysis. This report on the organization's risk assessment reveals many dangers and weak spots that might affect the company. In addition to this, it determines the overall risk level, analyzes the effect that is connected with the threats and vulnerabilities that have been identified, and evaluates the possibility that a vulnerability may be exploited. This report will assist the Operating Administration management in better understanding the threats that are posed to the organization's resources. It describes the risk assessment activities that were carried out by employees from the Risk Assessment Team between the Start Date and the End Date.

## Scope

This risk assessment will examine risks to the company in the areas of management, operational, and technological controls, as its scope of work. This risk assessment is only applicable to the System Boundary and consisted of site visits to conduct interviews at the Location of Interviews and physical security inspections of the Locations Where Reviews Took Place.

Exclusions from the Scope:
This evaluation does not cover the mainframe platform (which is the general support system on which the system resides), the General Support System (which is located in the lower level of the Headquarters building), or the backbone network. All of these components, however, will be described within their respective certifications.

## Testing Methods

Calculating vulnerabilities can be done with the help of a number of different tools or testing methods. Some of these tools and methods include the NIST _Recommended Security Controls for Federal Information Systems_, SP 800-53, vulnerability scans, results from the Security Testing and Evaluation Plan, and various checklists that are specific to the software, hardware, or operating system with which the organization is configured. The following instruments were used in the process of risk assessment for the organization:

Some examples of tools that can be used to determine the security requirements and controls for operating systems, software, and hardware include the following:

- National Institute of Standards and Technology ([NIST](https://www.nist.gov/)), Guidelines on Electronic Mail Security, [SP-800-45](https://csrc.nist.gov/publications/detail/sp/800-45/version-2/final), September 2007
- National Institute of Standards and Technology, Guidelines on Securing Public Web Servers, Special Publication [800-44](https://csrc.nist.gov/publications/detail/sp/800-44/version-2/final), September 2007
- The NIST Guidelines on Active Content and Mobile Code, Special Publication [800-28](https://csrc.nist.gov/publications/detail/sp/800-28/version-2/final), March 2008
- National Institute of Standards and Technology, Guidelines on Firewalls and Firewall Policy, Special Publication [800-41](https://csrc.nist.gov/publications/detail/sp/800-41/rev-1/final), September 2009

# Risk Assessment Methodology

The process of risk assessment is divided into four separate stages, which are as follows:

- An assessment of the risks posed by the resources, controls, threats, and vulnerabilities.
- Decisions made by management to either adopt security countermeasures or tolerate residual risk.
- The use of various preventative measures
- Ongoing inspection of the risk management program at regular intervals

The first phase, which lays the groundwork for the subsequent three stages, is what this paper covers. The following are included in the comprehensive threat, vulnerability, and risk analysis:

- Asset Identification: The process of determining which system resources within the system border need to be protected.

- Identification of Threat Sources and Vulnerability: Weaknesses in the system design, system security processes, implementation, and internal controls that may be exploited by authorized operators or by unauthorized intruders.

- Threat Identification: A listing of all known and anticipated dangers that are relevant to the system that is being evaluated.

The identification of security needs comes first, before moving on to risk assessment. In addition to the policies of individual departments, executive, legislative, and technological advice are also considered when determining security standards. In addition, the precise security requirements for the hardware, software, and operating system are outlined here. The risk assessment is carried out with the purpose of determining the managerial, operational, and technological controls, as well as any other suitable countermeasures, that are required for the protection of the system.

## Identifying System Assets

The determination of system threats, vulnerabilities, and dangers, as well as the appropriate degree of security to apply to the system and associated system components, requires the identification of system assets. The following items are included in system asset identification:

- The process of determining and documenting the system architecture.
- The process of determining the assets of the system and its subsystems, including all of the hardware, software, and associated equipment.
- Identifying system interfaces (external and internal).
- Determining where the system's limits lie.

When it comes to complex systems, a system description is often generated once the system assets have been identified. This description is then either included in the Security Plan or the Technical Architecture Document. After the assets have been identified, the next step is to assess the system's sensitivity requirements and severity (the effect of the system's loss) in relation to the system information's confidentiality, integrity, and availability. In order to ascertain the level of sensitivity of the information, the following three fundamental protection criteria are defined by the federal IT security standards:

1. Protection against disclosure that is not allowed, often known as confidentiality.
2. Integrity is the protection of anything against unauthorized, unplanned, or inadvertent change. In addition to this:

    - Verification of the sender or the recipient of a communication is an example of non-repudiation.
    - Authenticity is defined as the process of verifying that the content of a communication has not been altered while it was in route.

3. Availability: The capacity to make oneself immediately available in order to fulfill the needs of the task or to prevent significant losses.

The design of the system as well as the actual places where it is deployed together make up what is known as the system environment. Access to system assets or data, both physically and digitally, is a component of the system environment, which varies depending on the kind of site installation. The potential for loss of confidentiality, integrity, and/or system availability, all of which might have an effect on system assets or data, is a good indicator of the severity of the impact. This effect may be evaluated by the loss of system functioning, impedance, or failure to achieve an Agency mission. It can also be quantified by monetary losses, loss of life, loss of safety, loss of public trust, or unauthorized exposure of data. Evaluation of system assets, needs, and information that is kept, processed, or transferred by the system are used to arrive at a conclusion on the risk level. The amount of risk is calculated by assigning a qualitative score of high, moderate, or low to each of the system's three pillars: availability, secrecy, and integrity. 

## Analyzing System Threats

Threat sources are anything that may damage a system or use a vulnerability to attack an asset. It's anything that might compromise an asset's confidentiality, integrity, or availability. The system's capabilities, intents, and attack techniques must be examined. A danger source covers physical, natural, environmental, and human sources and affects most networks and computer systems when proper protections are not in place. Any scenario or occurrence that might impair an IT system or exploit a vulnerability to attack an asset is a threat source. It's anything that might compromise an asset's confidentiality, integrity, or availability. Natural, human, and environmental threats are widespread. It's necessary to evaluate all possible threat-sources that might impair an IT system and its processing environment when analyzing threat-sources. Environmental dangers such as a leaking pipe may swiftly flood a computer room and destroy an organization's IT assets and resources. Humans may be threat-sources via purposeful or unintended activities, such as hostile assaults or unhappy workers. A intentional attack may be a malevolent effort to obtain unauthorized access to an IT system (e.g., password guessing) to jeopardize system and data integrity, availability, or confidentiality or a benign, but purposeful, attempt to overcome system security. Trojan horse programs circumvent system security to boost productivity. Bypassing security for a good purpose weakens system security. Threat agents or behaviors employed in risk assessments are based on NIST SP 800-30. Threats to systems, leased telecommunications systems, and public telecommunications services fall into three basic categories.

- Natural Threats : Floods, earthquakes, tornadoes, landslides, avalanches, electrical storms, and other natural disasters are examples of natural threats.

- Human Threats: Occurrences that are either made possible by or caused by human beings, such as accidental acts (such as unintended data input) or purposeful activities (such as hacking) (network based attacks, malicious software upload, unauthorized access to confidential information).

- Environmental and Physical Threats : Long-term power outages, pollution, chemical spills, and leaking of liquids are examples of environmental and physical hazards.

The security of telecommunications systems, networks, network management systems, computers, and information systems is susceptible to a wide variety of attacks, any one of which might result in costly harm. It is helpful to think of the danger as the stimulus, the vulnerability as the weakness, and the impact as the overall effect that the threat has on the system or the information that is processed, stored, or sent by the system. A danger may present itself in a variety of ways, some of which may be known vulnerabilities while others may be undiscovered vulnerabilities. The final effect of a threat taking advantage of any vulnerability is that it generates the possibility for a breach of the protected assets and information of the agency. Threats may have any one of the following five broad repercussions: unauthorized exposure of information, data corruption or destruction, denial of service attacks, system failure, or loss of communications.

## Analyzing System Vulnerabilities

The environment, the architecture, the design, or the implementation of a system; the organizational rules, processes, or practices; the management or administration of hardware, software, data, facility, or staff resources are all examples of potential vulnerabilities. When a vulnerability is taken advantage of, it may result in damage to the system or to the information that is being processed, transferred, or stored by the system. The vulnerability assessment takes into account all three of the following security control categories in line with the NIST Standard Publication 800-53, "Recommended Security Controls for Federal Information Systems."

- Management Controls are protections connected to the management of the system's security and the management of the risk for a system. - Management Controls are also known as administrative controls. A lack of risk management, life cycle activities, system security plans, certification and accreditation activities, and security control reviews are all examples of management weaknesses.

- The operational processes that are carried out with regard to an information system are included as part of the operational controls. The majority of the time, these vulnerabilities are caused by a lack of (or an inadequacy in) the many practices and processes that are essential to the safe functioning of a system. However, there are other factors that may also play a role. Some examples of operational vulnerabilities include the lack of (adequate) security awareness and training, security monitoring and detection provisions, personnel and physical security controls, and security auditing, as well as the absence of some or all of the procedural documentation that is essential to effectively applying and managing a security program.

- Technical Controls are countermeasures relating to the protection of hardware, software, system architecture, and ways of communication. - Technical Controls are also known as technical safeguards. Inadequate security software controls and mechanisms, incorrect operating system code, a lack of virus controls and procedures, and a lack of authentication and access restrictions are some examples of technological vulnerabilities. In most cases, vulnerabilities are found during the risk assessment or during the testing and evaluation of the system's security. The following are some of the primary actions that are included in security certification in order to obtain an awareness of the system's vulnerabilities:

- Developing a robust data gathering questionnaire.
- Carrying out site assessments and going on site visits to several representative installation locations
- Conducting interviews with system users as well as system maintainers
- The process of documenting the results

System vulnerabilities are found after doing an analysis of the system's managerial, operational, and technological security measures when the system is operating in its fielded environment.

A risk rating was generated as a consequence of a review of the system vulnerabilities, the risks associated with those vulnerabilities, and the likely effect of the vulnerability being exploited. This value was assigned to each control that was either absent or only partly implemented. The extent of the danger was dependent on two variables, which are as follows:

1. Likelihood of Occurrence: This refers to the probability that a threat may exploit a vulnerability, taking into account the system environment and any other preventative measures that have already been implemented.

2. Effect - The impact of the threat exploiting the vulnerability in terms of the loss of actual assets or resources and the impact on the organization's purpose, reputation, or interest in the matter.

Before the analyst can determine the overall risk levels, they need to examine how important the system's availability, integrity, and confidentiality are in relation to the system's ability to perform its function, as well as the different types of damage that could be caused by the exercise of each threat-vulnerability pair. When a vulnerability is exploited, there is a possibility that one or more of the following sorts of harm may be caused to a system or its data:

- Loss of Availability / Denial of Service – This condition occurs when access to the system, a particular system capability, or data is denied (Asset is not destroyed).

- Loss of Integrity /Destruction and/or Modification refers to the total loss of the asset, which can be caused by the asset's destruction in its entirety or by damage that cannot be repaired, as well as by unauthorized change, damage that can be repaired to the asset, or a change in the functionality of the asset.

- Breach of Confidentiality or Disclosure: The disclosure of private information to persons or the general public who do not have a "need to know" about the information in question.

In the next section, which is titled "Risk Calculation," we will talk more about the study of the system's vulnerabilities as well as the estimation of the risk.

## Mission Criticality

Utilizing the IT System Certification and Accreditation guide, if one is available, is another method for determining the importance of the purpose to the firm. Any telecommunications or information system that is utilized or managed by an agency, a contractor of an agency, or another entity on behalf of an agency is referred to as a mission critical system. This phrase applies to any system that meets the following criteria:

- Meets the requirements for classification as a national security system outlined in subsection 5142 of the Clinger-Cohen Act of 1996 (40 U.S.C. 1452).
- is protected at all times by procedures established for information that has been specifically authorized to be classified in accordance with criteria established by an Executive order, an Act of Congress, State or organization policy, in order to protect the national defense or further the interests of the entity named in the policy.
- Handles any information, the loss of which, improper use of which, unauthorized disclosure of which, or unauthorized access to which, would have a detrimental effect on the purpose of an organization.

Non-mission critical applications are those automated information resources that do not fall under the definition of mission critical applications. Their failure would not prevent or a major subordinate organizational element from carrying out core business operations in the short to long term; however, it would have an impact on the effectiveness or efficiency of day-to-day operations.

# Risk Calculation

This section discusses vulnerabilities, the threats that can exploit those vulnerabilities, and the probable impact of that vulnerability exploited. System vulnerabilities are identified as required security controls that are not fully implemented. These are classified as vulnerabilities because the lack of required controls result in vulnerability that a threat can be exploited successfully.

The analysis of system vulnerabilities, the threats that can exploit those vulnerabilities, and the probable impact of that vulnerability exploitation resulted in a risk rating for each missing or partially implemented control. The risk level was determined based on the following two factors:

1. Impact of the threat exploiting the vulnerability in terms of loss of tangible assets or resources and impact on the organizations mission, reputation, or interest.

2. Likelihood to which the threat can exploit a vulnerability given the system environment, threat frequencies, and other mitigating controls in place.

The following sections discuss the areas of potential impact and how the values for the above two factors, magnitude of impact and likelihood of occurrence, and the level of risk were determined. The factors used in these sections are derived from NIST _Risk Management Guide for Information Technology Systems,_ SP 800-30.

# Risk Assessment Results

## Risk Summary

The results of the risk assessment of the organization indicated that the primary risks to system resources related to unlawful/unauthorized acts committed by hackers, computer criminals, and insiders related to system intrusion, fraud, and spoofing. Unintentional user errors and omissions is an additional critical risk to system data and operations.

The assessment found that identified risks could be fully mitigated through the implementation of security controls specified in the the organization Security Plan and in the accompanying Plan of Action and Milestones.

## Applicability of Minimum Security Baseline

The risk assessment of the the organization included an assessment of the applicability of Minimum Security Baseline to determine its adequacy in protecting system resources. 

## Additional Controls Required

In addition to controls identified in Minimum Security Baseline (NIST SP 800-53), the risk assessment identified several additional controls that should be implemented to mitigate risks to the organization resources. 

Example [report](img/Risk-Assessment-Report.doc)

## Refecenses
- ISO 27000 Series
- NIST SP 800-53
- NIST SP 800-171
- NIST CSF
- NIST SP 1800 Series
- COBIT
- CIS Controls
- HITRUST Common Security Framework
- GDPR
- COSO
