# The code phase
The coding stage is the second part of the continuous development section of the DevOps lifecycle, where the new application or feature is coded. Developers write new code with ‘live’ security feedback from plugins in integrated development environments. When the code is ready to be pushed to the central repository, pre-commit checks are made to statically scan the code for security vulnerabilities. Finally, upon committing or ‘checking in’ the code, the CI/CD pipeline comes into play, with the new code being continuously integrated into the main codebase. The build phase comes next, where post-commit static analysis security tests can be carried out.

From a DevOps perspective, it's important to enable version control tools like Git or SVN in the coding phase. These tools track the history of code changes and enable multiple collaborators to work simultaneously on the same code, speeding up development. From a security perspective, version control tools can be used to track who makes changes to code – useful for catching malicious actors. This also helps identify which commit a change belongs to, allowing it to be reverted easily if vulnerabilities have been introduced.

![image](https://github.com/juzweb/security/assets/2524790/39b1bfc7-f27c-409f-aba0-b3a3c7cbab95)

# Security considerations
The main concern in the coding phase is to prevent vulnerable code from being introduced to the application. There are several areas to be aware of in this phase:

- Integrated development environments – using security plugins in these environments alert developers to security issues as soon as they're typed.
- Gatekeeping and dependency management – code is often imported from third-party libraries and re-used throughout applications. This speeds up development, but means that if a component is vulnerable, it could affect many areas of the application. Code should be tested when first imported to ensure it isn't malicious or doesn't contain vulnerabilities. Dependency management tools like Node Package Manager (npm) keep dependencies organized and up to date, ensuring the latest vulnerability patches are applied.
- Requirements and standards – these should be adhered to when coding so that the latest security best practices are followed. Requirements and standards can prevent developers from using insecure coding methodologies that a code scanner won't always pick up.
- Secrets management – these tools should be used to securely store and manage secrets, rather than hardcoding passwords, certificates, or other credentials into the codebase.
- Pre-commit checks – before code is committed to a central repository, it should be statically scanned for vulnerabilities to ensure that secrets such as credentials or API keys won't be committed to source control. These tests should be triggered before every commit.
- Code reviews – the manual review of new code by security experts can often pick up insecure practices and offer alternative solutions, as well as identify areas where code is not compliant with expected standards or current regulations.

![image](https://github.com/juzweb/security/assets/2524790/165d5ca2-36d6-490c-96c8-afa22b5faf4e)

# Tooling
Code can be written in various languages, so it's important to find the right tools for the job. Luckily, many tools can be found in a range of languages, and some even have multilingual support.

Here are some examples of tools that you may find useful:

- IDE security plugins – plugins like Microsoft's DevSkim or SonarSource's SonarLint can perform real-time scanning and highlight security issues in multiple languages. Some specialist plugins also scan for security flaws in certain languages, such as Puma Security's Puma Scan for C# or OWASP's Find Security Bugs for Java.
- Dependency management – tools like Dependabot can be used to scan open-source GitHub repositories before you import their code, allowing you to gatekeep against vulnerabilities. Meanwhile, npm has a built-in an audit command in its CLI package for auditing packages, and OWASP has released Dependency-Check to scan for vulnerabilities in dependencies.
- Secure coding standards – many respected organizations have laid out standards for secure coding, such as OWASP's Proactive Controls, SAFECode's Fundamental Practices for Secure Software Development, and US CERT's Secure Coding Standards. Adhering to these guidelines can help prevent vulnerabilities from being introduced to your code. Tools like CheckStyle can also be used to automate the checking of your own custom standards, tighten rules, or enforce the use of certain standards.
- Secret management tools – popular tools such as HashiCorp Vault, AWS Secrets Manager, and CyberArk's Conjur Secrets Manager offer cloud-native secrets management for applications. The best secrets managers integrate into a range of CI/CD pipelines and automate the regular rotation of credentials, preventing the need for sensitive values to be hard coded.
- Pre-commit security hooks – even with secret management tools and integrated security plugins, some vulnerabilities and secrets can slip through the cracks. The pre-commit hook can address this by scanning for vulnerabilities and secrets, and preventing insecure code from being checked into central repositories. Example tools include AWS Lab's git-secrets, OWASP SEDATED, or ThoughtWork's Talisman.
- Code reviews – as much as rapid DevSecOps cycles promote automation, some things simply can't be automated. A manual code review by another professional developer, who is security-conscious and familiar with the code, can help identify bad practices or vulnerabilities. Useful tools for code reviews include GitHub's integrated pull request feature, GitLab's merge request feature, or external tools like Gerrit.





