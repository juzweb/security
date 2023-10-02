# The monitoring phase
The monitoring phase is the eighth phase in the DevOps lifecycle. It’s important to remember this isn’t the “last” phase – the DevSecOps cycle is continuous. The monitoring phase should be approached as a way to determine the future of your product.

In this phase, you should integrate reports and logs generated by the tools across your pipeline, with the aim to consolidate and centrally monitor them, and remove any redundant duplicates. You can then create alerts based on the severity and impact of the information. You should also continuously iterate which parts of your systems generate alerts and how they're handled. It’s essential to try and distinguish between informative alerts that don’t require direct action and critical alerts that require intervention, or even better, an automated response.

As well as the technical aspects of your project, it’s also important to monitor the processes surrounding it. Looking at the metrics of code reviews and access requests, for example, will allow your team to “shift left” and solve issues, remove bottlenecks, and fix bugs earlier in the development process.

When developing a monitoring solution for your project, it can be easy to get carried away and start throwing alerts up everywhere. While logging should be pervasive throughout all aspects of your project, you should think about which activities generate alerts. If you start throwing alerts about inconsequential activity, it'll be hard for your teams to sift through the noise and identify more critical alerts. In the worst-case scenario, you’ll spend a lot of time building alerts that nobody pays attention to. Deliberate as a team to determine the metrics you care about most. Implementing alerts at a gradual pace will help you learn what works for your team as you expand your capabilities.

![image](https://github.com/juzweb/security/assets/2524790/49c260fd-387f-411a-bc98-35f49b222381)

# Security considerations
Monitoring for “security” can include underlying hardware, network traffic, applications/microservices, containers, interfaces, and behavior monitoring. These will generate logs, which can seem vague and all-consuming. To gain a holistic view, you can use a logging agent to forward these logs to a centralized system that aggregates them.

**Behavior monitoring** includes both user accounts and developer accounts. Spotting a compromised account early is the easiest way to minimize the impact of a security incident. You should be monitoring multiple failed login attempts, impossible travel (when a user is appearing from two distant IP addresses simultaneously), or large amounts of usually rare administrative activity. Pairing this with the principle of least privilege when determining permissions of different accounts will ensure that potential damage from leaked credentials is ring-fenced as much as possible.

**Security scans** of your infrastructure and related systems should involve a combination of vulnerability assessments and compliance scans. Vulnerability assessments will look at the code/programs running on the systems and their dependencies to detect whether they harbor any known vulnerabilities. On the other hand, compliance scans will look at the configuration of the systems, both at an individual level and how they interact with each other. You should generate logs for each scan or assessment, and you can then raise alerts when they find vulnerabilities or noncompliance.

The alerts you implement should allow you to be proactive from a security perspective. Intrusion detection systems should generate alerts when they suspect a malicious user has gained access to your systems, but the alert should also prompt you to implement intrusion prevention systems to help prevent future security incidents.

System overviews, dashboards, and alerts can provide detailed information about your environment. The principle of least privilege should determine who can access this information. Instead of having one dashboard or report that contains all of this data, it's worth considering a modular approach, so each team or individual only sees the information relevant to them.

![image](https://github.com/juzweb/security/assets/2524790/ec879d69-ce41-45a9-8d76-3b2c095d291f)

# Tooling
The specifics of your project will determine which tools are best suited to it. In general, you should look for tooling that can integrate logs from as many of your systems as possible, offering flexible, customizable alerting. A wide scope will make it easier for you to find the best tools for your project.

You can use some of the tools listed below to enhance your monitoring capabilities:

**Arachni** is a vulnerability scanner that can be used to assess the security of web applications. This can be run on a schedule and alerts can be generated based on its findings.

**Snort** is an open-source intrusion detection system that uses sets of rules to detect malicious network activity and alert you to potential security breaches. It can also be turned into an intrusion prevention system by allowing it to deny packets based on the set of rules.

**DataDog** is an enterprise tool that offers a wide range of logging and monitoring solutions. It connects to big cloud providers and integrates with many corporate tools, making it a good candidate for aggregating your monitoring. DataDog, alongside other monitoring integrators, also allows you to set up alerts based on the logs it's collecting. These alerts can then be integrated into the most convenient messaging system (such as e-mail, Slack, and Microsoft Teams).

**Elastic** offers an observability platform that can provide unified visibility and benefits from the integration of ElasticSearch, allowing you to use it to search across all aggregated logs.

**Graylog** has an open-source version of its log collector and manager as well as its enterprise products. This allows you to store and analyze log data while giving you the flexibility to customize it to your needs.

All major cloud providers have logging and alerting services. AWS's CloudTrail records all activity in your accounts, and CloudWatch allows you to build alerts based on the filtered CloudTrail logs. Azure Monitor Logs and Google Cloud Logging also offer similar functionality on their platforms.









