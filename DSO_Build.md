# The build phase
The building stage is the first part of the DevOps lifecycle's 'continuous testing' section. In many CI/CD pipelines, this phase of the cycle is almost entirely automated.

Once code is committed, further static testing is carried out. If these tests pass (and software composition analysis confirms that dependencies are vulnerability-free), code can be compiled and built, allowing unit testing to be performed. If the build passes all security and integration tests, the new feature will then be ready for the testing phase, where larger-scale, more rigorous testing occurs.

Everything in this phase is usually tied together by a build server, especially in fully automated pipelines. These build servers induce dependency checks, build code, trigger automated testing, and collate reports and metrics fed back from tests. This automation reduces testing time and the possibility for human error, and allows multiple new features to be continuously tested simultaneously. In addition, developers can rapidly receive feedback, allowing for quick iteration.

# Unit testing
In this phase, testing often occurs in the form of unit tests. These test functionality and security using the smallest feasible codebase around the change code. If possible, they should not involve external functions or a full review environment.

Unit tests require a suite of test cases to be developed, against which new builds can be tested (where each test checks for one specific vulnerability or risk). These tests must be thoroughly tested when written to ensure they don't return false negatives for errors.

Critical, quick, and less expensive tests should be run first, and failures should be rapidly returned to prevent the unnecessary running of slow or expensive tests. These unit tests are often run locally by developers, using containers instead of full-scale environments, to enable rapid feedback and iteration.

![image](https://github.com/juzweb/security/assets/2524790/40055739-5acd-46c8-885f-e50291759216)

# Security considerations
The primary aim of the build phase is to compile, build, and test new areas of code, ensuring that vulnerabilities aren't being introduced to the product.

Here are some core areas to be considered in this phase:

- **Static application security testing (SAST)** – the security of your application should be tested against the most common vulnerabilities, such as those defined by the OWASP Top 10.
- **Software composition analysis (SCA)** – the SCA process involves identifying any third-party dependencies used, ensuring their license is compatible with your product, and scanning any open-source libraries to check for vulnerabilities. This prevents the accidental import of vulnerabilities from untrusted sources.
- **Infrastructure hardening and testing** – while much of infrastructure security such as infrastructure as code (IaC) analysis and cloud configuration management occurs in the release phase of the cycle, shifting left means security should be tested as early as possible. In the build stage, you should ensure you're building secure images and infrastructure using container and Kubernetes hardening, and verify this with container scanning. This will strengthen and test the security of your container environments before new builds are deployed to full-scale testing environments.
- **Gathering metrics** – if a build fails a test, developers will have to return to the coding phase, or even the planning phase if the issue is not easily remediable. Suitable reporting will make it easier to identify failed tests and the cause of security issues.
- **Integrity validation** – any binary releases should be signed with PGP keys, and code artifacts stored in private repositories. This can validate the integrity of your binaries, and protect your builds from intellectual property theft.

![image](https://github.com/juzweb/security/assets/2524790/d13a6029-fd1b-4806-8dc6-1b9e222dce5a)

# Tooling
The core tool of the build phase is a build server, to automate building and trigger testing in a continuously integrated pipeline. The best build server or continuous integration (CI) server for an organization will depend on its needs, but popular examples include GitLab CI or Jenkins. These servers are an integral part of the CI/CD pipeline and must be set up securely. Anyone who can compromise your build pipeline will usually have access to all your environments (such as development and production) and could compromise your code.

From a security perspective, here are some tools to consider:

- **Static Application Security Testing** – some SAST tools will be specialized for certain frameworks, such as Brakeman (Ruby on Rails) or Phan (PHP). Others, such as Coverity or SonarQube, can cover multiple languages and frameworks. Many SAST products come as CLI tools and IDE plugins, so can be used in both the coding and building phases.
- **Software composition analysis** – specialized tools such as Synopsys' BlackDuck combine dependency scanning with compliance checks to ensure security when using third-party dependencies.
- **Infrastructure hardening and testing** – for Kubernetes hardening, a range of tools exist which can scan your cluster and configuration for vulnerabilities and insecure permissions. Examples include Aqua Security's kube-hunter, kubesec.io, or Cyber Ark's Kubiscan. You can also use Linux security modules such as AppArmor to harden Kubernetes pods. Tools such as Bane can generate AppArmor profiles for you, or alternatively, Linux kernel enhancements like grsecurity can secure the kernel for your Kubernetes pods. Check out the lab linked below to learn more about hardening Kubernetes pods.
- **When hardening containers**, standards such as CIS benchmarks can provide guidance on best security practices. Tools such as Trivy, Docker Bench, or Clair can then be used to scan containers for potential vulnerabilities. You can learn more about container scanning in the labs linked below.





