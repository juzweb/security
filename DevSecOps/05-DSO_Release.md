# The release phase
The release stage is the fifth part of the DevOps lifecycle's continuous development section. At this point, your code should have passed automated tests and you should be confident that it won't create any issues when run. In this stage, we focus on any environment configuration changes needed to facilitate the release of code.

![image](https://github.com/juzweb/security/assets/2524790/04cfe990-beb2-4862-8ad8-b443a440cda4)

# Security considerations
As with any stage in the DevSecOps cycle, security considerations must be made whenever changes are introduced. This is to ensure changes do not cause performance issues or affect security when introduced to the live system.

Changes such as additional network rules, new permissions, and new certificates should be reviewed to ensure they follow the principle of least privilege. They should only allow the minimum level of access and permissions required for a user or application to perform its function.

Changes such as new infrastructure and software packages should be reviewed to ensure they're configured securely. This can be achieved by applying hardening configurations and scanning dependencies for security vulnerabilities, for example.

It's best to make changes in an auditable and automatable manner. You could do so by managing your infrastructure and configurations as code within a source control repository such as Git or SVN. Using the source control management system, developers can request changes via pull requests and log decisions as part of the review process. Continuous integration/deployment (CI/CD) pipelines use configuration management tools to ensure the live infrastructure state does not drift from source control.

Security checks built into your CI/CD pipeline are triggered on pull requests and commits, which should scan infrastructure as code (IaC) changes for best practices and insecure configuration. The pipeline should test changes in a staging environment to check functionality and whether standards such as CIS and NIST are met. Any changes that don't meet your pipeline criteria are highlighted for further investigation before release.

Once all the checks in the pipeline at this stage have been passed, you can be confident that code and environmental changes meet your security standards. You can then proceed to the next stage in DevSecOps.

![image](https://github.com/juzweb/security/assets/2524790/79bd697f-a287-4835-af43-65ec3b016fae)

# Tooling
Your applications can be deployed in numerous ways, either on-premise, in the cloud, or a combination of the two. Various languages and automation tools have been developed to make this easier for developers and operation teams.

The tools you use will depend on the environments you're deploying to, the skills in your team, and your own assessments. Luckily, there are a plethora of tools to choose from.

Here are some tools you may find useful for each activity in the release phase:

**Infrastructure as code**: Managing the provisioning and configuration of infrastructure through code.

- Terraform – codifies cloud APIs into declarative files using Hashicorp language.
- Ansible – software provisioning and configuration tool that uses Yaml and SSH.
- Puppet – manages the configuration of systems using puppet declarative language.

**Cloud configuration**: Using the cloud provider's configuration tools to deploy and configure cloud resources.

- AWS Cloudformation – manages AWS resources using YAML or JSON.
- Azure Resource Manager – manages Azure resources using JSON.
- Google Cloud Deployment Manager – manages Google Cloud resources using Jinja or Python.

**Infrastructure as code (IaC) scanning**: Scanning IaC for misconfigurations before it's deployed. Most tools support multiple languages – Terraform is the most popular, alongside those used by GCP, AWS, and Azure.

- Checkov – used to manage and analyze infrastructure as code (IaC) scan results.
- KICS – used to find security vulnerabilities and compliance issues.
- Terrascan – used to detect compliance and security violations.
Feel free to check out the below lab to get some practical experience in IaC scanning.

**Security testing**: Running automated attacks against your infrastructure to check changes are secure.

- OWASP Zed Attack Proxy – a free, high-performing application security scanner.
- sslyze – an SSL/TLS scanning tool that ensures the use of strong encryption and checks for vulnerabilities.

**Infrastructure testing**: Testing the state of your infrastructure to check the configuration is as expected.

- Serverspec – tests your server's actual state by executing commands locally.
- Terratest – validates that the infrastructure works correctly by making calls via SSH, HTTP, and so on.

**Infrastructure compliance**: Comparing the live state of your infrastructure against the desired state and well-known standards such as CIS and NIST. Also involves detecting violations and automating remediation.

- Inspec – checks actual state against expected state and compares it with compliance standards.
- Open Policy Agent – enforces configurations to comply with standards using Rego language.
- Conftest – writes tests against structured configuration data to ensure it meets standards.



