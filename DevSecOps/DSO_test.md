# The test phase
The testing stage is the second part of the DevOps lifecycle's continuous testing section. Like the build phase, this stage is mostly automated in CI/CD pipelines, but some organizations prefer to supplement automated testing with rigorous manual reviews.

Unlike the previous phase, in which changes are often tested in lightweight Docker containers, testing in this phase usually occurs in full-scale review or staging environments. This lets DevOps and quality assurance (QA) engineers test for issues in integration, performance, infrastructure, and networking. Testing is often managed by continuous integration tools like Jenkins. This allows QA engineers to test multiple changes in parallel.

![image](https://github.com/juzweb/security/assets/2524790/b93463e5-285e-4635-867e-d7dac680c291)

# Testing requirements
In this phase, testing often occurs in the form of dynamic application security testing (DAST), integration tests, or performance tests. Each of these types requires a suite of test cases to be developed, against which new builds can be tested. Each test should check a certain aspect of the new code or feature, such as security or integration. These tests must be thoroughly tested themselves when written to ensure they don't return false negatives for errors.

Like in the building phase, time-consuming and costly tests should not be run unnecessarily. This can be seen in a diagram of Mike Cohn's test pyramid below, where tests that are more isolated (yet cheaper and faster) are run first.

![image](https://github.com/juzweb/security/assets/2524790/b9c09a2b-70b2-4dc4-bec7-2b7c9fb05c30)


# Security considerations
The primary security consideration of this phase is dynamic application security testing. In the previous build phase, source code and binaries are scanned for vulnerabilities during static application security testing (SAST) within containers. While the testing phase should still include some SAST, often performed manually by QA engineers, the main component of this phase is DAST. In contrast to SAST, DAST tests the application at runtime.

Automated DAST tools can simulate attacks against a web application, checking application flows such as user authentication and authorization and encryption. This can be used to check for critical vulnerabilities throughout the OWASP Top 10, such as SQL injection or cross-site scripting, using techniques like fuzz testing. Fuzzing is when random data is input into parameters to try and induce errors. Additionally, different DAST tools scan APIs and web endpoints, test for unexpected network calls, and check for unsanitized inputs.

The testing phase should also review:

- **Logging** to ensure security metrics are captured correctly.
- **Access controls** to ensure least privilege principles are adhered to and that there are no unexpected access permissions.
- **Infrastructure testing and compliance checks** to ensure infrastructure is behaving as expected by testing APIs and endpoints across networks.

![image](https://github.com/juzweb/security/assets/2524790/b25f7f61-f0dd-4f1b-b9a1-174a1daf1b8d)

# Tooling – DAST
Dynamic application security testing covers such a broad spectrum that there are numerous tools available. Many of them are highly specialized to find specific types of vulnerabilities, while others are designed for general sweeps across an application's surface.

Here are some examples of useful tools:

**Fuzzing**: tools such as BooFuzz or OWASP ZAP's Fuzzer feature will input random data into an application's input parameters to induce errors or exceptions. This helps identify potential points of vulnerability for further investigation.

**SSL/ TLS configuration testing**: SSLyze is an example of a highly specialized DAST tool. It verifies encryption settings on servers, testing certificates, cipher suites, and more, and tests against common TLS vulnerabilities.

**Web application vulnerability scanners**: generalized scanners such as Codename SCNR, OWASP ZAP, SecApps Suite, and PortSwigger's Burp Suite can all test web applications for vulnerabilities. This includes checks for SQL injection, cross-site scripting and request forgery, code and file injection, path traversal, and more. These scanners are highly comprehensive and, when integrated into CI/CD pipelines, provide useful insight into the security of web applications.

# Other DAST tooling

GitLab offers several DAST tools in one place, designed to scan both websites and APIs for vulnerabilities. Being part of GitLab means this is designed to be part of an automated GitLab CI/CD pipeline and may integrate well with existing Git projects.

Several management tools also exist to wrap and summarize DAST testing results, making them more accessible to non-technical team members. Tools such as Tricentis qTest offer automation and extensive dashboarding for your testing.

![image](https://github.com/juzweb/security/assets/2524790/b58e6079-b6af-482f-88d9-ae1cc9cd0db8)

# Tooling – infrastructure
Dynamic scans can detect a range of vulnerabilities in a web application, but it's also important to test the security and compliance of surrounding infrastructure.

Here are a few tools to help with the job:

Infrastructure testing: tools such as Terratest, Test Kitchen, or ServerSpec enable DevOps teams to test servers and infrastructure code by making API calls, HTTP requests, and so on. Similarly, Tenable's Nessus can probe networks for points of entry to identify vulnerabilities in an application's surface.
Infrastructure compliance: the Open Policy Agent's policy engine allows DevOps teams to write custom rules for how their web application should behave (such as defining access to service APIs or resources that users can call operations on). These are then enforced throughout the stack. Combining this with tools such as Chef's Inspec (a customizable infrastructure testing framework) can ensure your newest infrastructure changes comply with your requirements.


