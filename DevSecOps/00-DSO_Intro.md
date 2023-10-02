# The evolution of software development
The legacy approach to software development is based on the ‘waterfall’ project management style. This approach involves mapping out requirements for the project, followed by development, security and legal sign-off, and finally, the deployment of a product.

The waterfall method is no longer functional; the risk of losing the first-mover advantage is too great. As a result, organizations devised another way to rapidly release new features – the ‘agile’ methodology, which involves continuously iterating between development and testing. However, operations engineers couldn't match the agility of this approach; bottlenecking the delivery process and negating any improvements to development speed.

Instead, DevOps combines system development and IT operations to shorten system development life cycles. By aligning development and operations teams, DevOps has made software delivery quicker and more user-focused, improving development quality and operational reliability. This has provided DevOps teams with the tools and techniques to not only develop products but also deploy and manage them in production, enabling rapid turnaround by removing the bottlenecks that the agile methodology faced.

Nonetheless, developing at speed can seem incompatible with the checks and balances of security, which often get siloed and operate only at the end of the life cycle as a go/no-go function. As a result, many security defects were observed in these small, high-functioning teams.

![image](https://github.com/juzweb/security/assets/2524790/9f94c633-9ecc-48e3-ac62-3d064917d2b2)

It's more important now than ever that security is ‘shifted to the left’ – meaning it should be included from the very start of the process with clearly defined processes such as:

- Threat modeling
- Vulnerability reduction (such as enforced encryption)
- Security-driven testing
By acting on security best practices during the stages of development and operations, and embedding automated security testing, DevSecOps increases the security of software delivery. Responsibilities are shared across teams, allowing security issues to be identified and resolved throughout the software development lifecycle (SDLC) rather than post-release.

# Why DevSecOps?
Tackling security issues earlier in the delivery process improves an organization's security posture and can minimize the number and severity of vulnerabilities reaching production. This leads to fewer costs from fixing security flaws, both in financial and reputational terms.

DevOps allows teams to rapidly release new features and iterate on them through automated development and deployment pipelines. Empowered DevSecOps teams will self-sufficiently cycle through software development; if security issues are detected, fixes are planned, built, tested, released, and monitored, so problems can be remediated without the need for intervention or sign-off. These rapid and efficient cycles wouldn't be possible, however, without automation.

# CI/CD and the security overlay
Continuous integration and continuous deployment (CI/CD) is a practice that applies to automated delivery pipelines, whereby a developer commits a small change to a codebase that's automatically uploaded, packaged, built, tested, and deployed to live environments. Organizations running this kind of operation include Spotify and Netflix, which often commit changes to their production code hundreds of times a day.

To enable a security overlay, we must make pragmatic decisions and use automated tooling and testing. This ensures that security is maintained throughout the CI/CD cycle.

There are several places where automated security testing can be injected into the CI/CD pipeline to allow for the rapid and secure release of new features. Over the course of this series, we'll cover each stage of the DevSecOps pipeline in more detail, but below you can find some examples of how security can be integrated into each stage of the cycle.

- Planning – this is the least automated stage of the cycle, where analyzing change impact and performing threat modeling promote early identification of potential security issues that may appear later in the cycle.
- Coding – security plugins like OWASP's Find Sec Bugs in integrated development environments (IDEs) can alert developers to issues as soon as code is typed (example in the image below). Between this and the static analysis of code upon committal, many common vulnerabilities are caught before the build stage, significantly reducing fix time.
- Building – once code is committed, build stage security can perform software composition analysis to check for vulnerabilities in dependencies, or sign binaries with PGP keys to validate integrity.
- Testing – in test environments, applications can be dynamically tested for security vulnerabilities in application flows, using tools such as OWASP's Zed Attack Proxy to insert runtime testing into the CI/CD pipeline.
- Releasing – during the release phase, access controls are tested and the runtime environment infrastructure is provisioned, ideally using configuration management tools (such as Terraform or Ansible) to introduce immutability to the environment.
- Deploying – automated patching ensures that software dependencies are the most up-to-date secure version in production and chaos engineering tests the system against insecurities.
- Operating – penetration testing and bug bounty programs should identify or responsibly disclose bugs in production environments, and automated incident response tools such as intrusion prevention systems should mitigate threats in real time.
- Monitoring – logs from monitoring tools like Splunk should be centralized and generate alerts in the appropriate channels, such as Slack or by email.

# A note on SecDevOps
In the field of software development, a small debate rages on: is it “SecDevOps”, or “DevSecOps”? We'll leave it up to you to decide, but here are the two conflicting arguments:

- SecDevOps – all members of DevOps team should be security professionals: While this approach requires significant training for those from development backgrounds, it means security is considered in every step of the process, rather than as an afterthought. Alternatively, some SecDevOps organizations have dedicated security teams that define policies for DevOps engineers to adhere to, outlining policies, providing training, and focusing explicitly on security.
- It's just semantics, the two are interchangeable: DevSecOps shares the responsibility for security across teams and throughout the pipeline; whether DevOps engineers are also security professionals does not matter, so long as they adhere to security best practices, be that via automated testing or by following policies outlined by a dedicated security team.





