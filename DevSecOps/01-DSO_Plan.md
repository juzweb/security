# The planning phase
The planning stage is the first part of the continuous development section of the DevOps lifecycle, and is often the least automated phase. Here, the aim of a project is refined, the scope of change is defined, and the methods for implementing the change are designed.

As with any section of the DevOps cycle, security must be considered during the planning stage when implementing a DevSecOps approach. Snyk recommends that security engineers be involved in this phase, so they can identify insecure plans relating to infrastructure and offer alternative solutions.

![image](https://github.com/juzweb/security/assets/2524790/6ec1f1d6-a1d5-4767-8228-9bfde603709f)


# Security considerations
During the planning phase, change impact should be analyzed; the first step in outlining potential new security considerations is determining what the proposed project will change.

Risk assessments should be broken down into modular, rapid exercises, allowing businesses to address risks as they arise during planning for a sprint or new microservice. Having developers demonstrate the proposed architecture and discuss possible security concerns will help to develop proactive thought processes in non-security-focused individuals.

Threat modeling and attack mapping should be carried out to determine and evaluate the risk that these changes expose. This involves:

- Abuse cases – developers should consider not only how legitimate users may use the proposed changes or new systems, but also how they may be abused by malicious actors.
- Attacker personas – examining the skills and motivations of potential attackers helps to pinpoint vulnerabilities from the view of an attacker.
- Evil user stories – this models threats from a scenario perspective, rather than based on attackers. Identify resources of interest and then form a scenario to be prevented. For example: “an evil user cannot download sensitive data”.

# Tooling
A range of tools is available to help integrate security into the planning phase of the DevSecOps cycle.

Issue tracking and management tools such as Jira or Trello are useful for breaking down projects into bite-sized components. This makes it easier to add security requirements and promotes rapid risk assessments.

Useful tools for threat modeling include:

- IriusRisk, Microsoft Threat Modeling tool, or OWASP Threat Dragon for system diagramming. Visualizing system components makes it easier to identify types of threats and define the attack surface.
- Mozilla's Rapid Risk Assessment methodology can be used before a full threat modeling to summarize risks in your project.
- Standards such as OWASP's Application Security Verification Standard (ASVS) provide requirements that, when adhered to, can aid secure development. This can be used to pinpoint areas that require a particular focus on security.

# Planning for the future
The planning phase should also accommodate the later stages of the cycle. It should be determined how security testing will be incorporated into the delivery process, and where this can be automated. This includes identifying security issues to consider, and the tools and techniques that will be necessary to identify and remediate them.

DevOps teams should:

- Identify tools and integration software needed for the delivery (e.g., IDE security plugins for the code phase).
- Identify the areas most responsible for security breaches in each stage. Examples include:
  - Build phase – vulnerable code and third-party dependencies
  - Test phase – omitting to test for security issues
  - Deploy phase – lack of coordination and outdated software in the production environment
  - Monitor phase – insufficient logging and alerting
- Identify and establish checkpoints where security controls can be placed. Examples include:
  - Build – code scanners and software composition analysis
  - Test – dynamic application security testing
  - Deploy – automated patching and chaos engineering
  - Monitor – integrate SIEM tools for greater monitoring visibility
- Identify the security tools and controls that can be integrated into the pipeline and placed at checkpoints.
