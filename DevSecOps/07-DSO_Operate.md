# The operation phase
The operation phase is the seventh stage of the DevOps lifecycle. Development teams will have previously planned a change and deployed it on the platform. In this phase, the change must be checked to ensure it works as intended in the live environment.

Ongoing configuration and maintenance tasks must also be performed, such as regular data and system backups, infrastructure scale management with appropriate load balancing to ensure optimum resource utilization, and proactive hunts for vulnerabilities in systems. These are prime candidates for automation to minimize both the scope for human error and time spent by the team on repetitive tasks.

This phase also ensures that users interact with the service as expected and have an appropriate experience. This links with the monitoring phase, but user feedback should be prioritized, which can be as simple as a questionnaire form based on how they use the platform.

![image](https://github.com/juzweb/security/assets/2524790/544f741a-7ebd-4269-8e99-5e3d8fa1f6bb)

# Security considerations
The operation phase is all about looking after your live environment. Therefore, security should be a primary consideration; it's during this phase that an attacker is most likely to target your platform. All the work completed in previous stages will ensure you’re in a good place, but it's still important to remain proactive.

It can be challenging to know what should be backed up in a DevOps environment. Creating backups of individual machines may not be required if you have a pipeline that can seamlessly rebuild your entire system. Persistent databases are the obvious candidates for regular backups. You should consider where you’re holding these backups and who will have access to them.

Encryption is a must and will add another layer of protection against potential data leaks. The location of backups should be separate from where you hold live information. If you operate in the cloud, then you could host your backups on a different cloud provider (Azure/AWS/GCP).

If you're automatically scaling and load balancing your environment, you should ensure the new infrastructure that you spin up and down gets configured correctly. They should be up-to-date with any security infrastructure changes. You should evaluate all infrastructure in the live environment and ensure infrastructure meets your specific baseline or benchmark requirements.

User behavior should also be monitored to ensure a good user experience. Malicious actors may begin their attacks as regular users and try to escalate their privileges or access restricted areas of the system. Being able to spot this kind of behavior can help prevent attacks.

The operation phase will also include continued attempts to find and patch vulnerabilities in a system. This is about staying proactive and not assuming everything is secure following pre-deployment checks. There are always weaknesses lurking in live environments (such as zero-days). The best way to ensure security is to evaluate these weaknesses continuously and patch regularly to ensure your environment inherits any fixes for issues in your supply chain.

![image](https://github.com/juzweb/security/assets/2524790/128f9030-c1eb-44c8-a7f4-d1e425154f1b)

# Tooling
The best tooling for you will depend on the specifics of your pipeline and what you’re building. That said, there are some main areas to cover to ensure your operation phase remains secure.

**Scale securely**: Availability is important when running modern applications, but new servers shouldn't be spun up unless you're confident they’re secure. Ensuring any new infrastructure is in line with security requirements is essential. The tools listed below are a good starting point in ensuring your scalable infrastructure is safe.

- CloudCustodian – allows you to define rules for the configuration of all your cloud infrastructure in specific accounts, so you can prevent infrastructure that doesn’t fit your requirements from being launched.
- Chaos Monkey – a tool that will randomly terminate your servers in production to test your environment's resilience; if a new secure server isn't spun up in replacement, you're not very resilient!
- Cloud-Native – all major cloud providers have their own tools for assessing infrastructure in your accounts, usually with the option to import benchmarks from organizations such as NCSC. Examples include AWS' Security Hub, Azure's Defender for Cloud, and Google's Security Command Center.

**Find the leaks**: Everybody likes to think their projects are entirely secure, but we know this isn’t the case. The best way to find vulnerabilities is to enlist the help of those who weren’t involved with the project's development and will therefore provide an outside perspective.

- Bug bounties – offering bug bounties on your product will incentivize strangers to contact you when they find security issues. This makes them less likely to disclose issues to a public forum, where they could be exploited.
- Penetration testing – an even more proactive approach is to directly pay a professional to try and find weaknesses in your product. Various flavors of pen-testing determine how much information you give the professional beforehand. You should look for professionals who are associated with well-known companies or have certifications from the CREST, Tiger, CHECK, or Cyber schemes.

**Stop the intruders**: Depending on the scale of your system, manually spotting malicious behavior can be nigh impossible. The tools below can automate this by analyzing logs of user actions.

- Fail2ban – an intrusion prevention software that bans IP addresses based on malicious signs, such as multiple authentication failures, or actively searches for exploits.
- OSSEC – a similar tool that performs log analysis and has time-based alerts with the option of active response, so no input is required from the team.




