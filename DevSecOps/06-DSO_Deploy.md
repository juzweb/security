# The deploy phase
Think of the deploy phase as the process of getting your tested and released product into the hands of users as quickly and securely as possible. You might do this several times a day, so automation should be a priority. Improving and automating your process means less disruption to the service, so customers can use the product quicker.

# Changes to infrastructure
As your product grows and evolves, it’s only natural that your resource requirements will change. Different servers with more computing power, running other operating systems, or performing additional tasks are all likely to be required at some point during the lifespan of your project.

The newest release will have already been running in a test environment, so you should have a good idea of what you need in terms of computing resources. Your deployment phase should then look to implement these changes to your live environment using infrastructure as code (IaC) wherever possible. This will reduce the scope for human error in the deployment, improve the reproducibility of changes you’ve made, and provide you with a record of what you changed as part of the deployment. Tools like Bridgecrew's Checkov or Tenable's Terrascan can scan IaC, like Terraform files or Kubernetes manifests, for vulnerabilities and bad practices. Once your IaC is deployed, tools like Gruntwork's Terratest can then interact with the infrastructure to automatically test it.

# Changes to databases
Modern organizations also consider database management in their DevSecOps scope. Changes to the functionality and scale of your applications will likely require changes to the configuration of your databases. You should build the deployment pipeline to enable database change integrations, even if they don’t necessarily occur with every deployment.

You can build clone databases to test new functionality or configurations that your development team asks for by taking snapshots and backups of live databases. Upon deployment, you can compare and merge the databases into a live environment alongside your code upgrade.

# Changes to code
Finally, there's the task of getting the software aspects of your project into the live environment. The latest artifacts should be made available to the deployment pipeline, and you should utilize scripts whenever possible to upgrade and install the latest versions onto your systems.

Logging and reporting should be detailed and reliable enough to give you a complete picture of when and where products were deployed on systems and if there were any issues during the process. Automated tests can run after deployments to ensure your critical functions are working as expected. If you perform a phased deployment, where different systems get updated at various times, it's vital to know which areas have been updated so issues can be traced back to the deployment.

![image](https://github.com/juzweb/security/assets/2524790/35df7388-49dc-4673-bad1-bc21ff73faec)

# Security considerations

# Accountability and integrity
The deployment phase revolves around making changes to your live environment and should therefore be a point of particular focus from a security perspective. One security aspect of deployments is the accountability and integrity of the deployment. This is all about making sure the team has approved the code and your changes. You should have a clear record of the deployed changes, who wrote them, and who approved them. You also need to ensure that these records are tamper-proof to maintain non-repudiation.

# Security of changes
You should then consider the changes themselves. Although your team should have thoroughly tested any changes in the earlier stages, the live environment is likely to differ slightly from any testing environment. So it's best practice to perform tests that verify the security of the changes in this new environment.

After a deployment check, you should run a system and infrastructure security scan (more detailed than your day-to-day alerting) to check the changes haven't accidentally introduced any vulnerabilities. These scans vary depending on the systems used but can involve port scanning, static code analysis, and even automated pen tests.

These in-depth checks form part of the final stages of the deployment phase, where you mark the deployment as complete with no urgent actions for your team to fix. The product may require non-urgent changes based on the deployment, but these can often be added to the general backlog and fixed in a later iteration.

# Principles of infosec
When deploying changes to databases, it's important to remember the core principles of information security: integrity, availability, and confidentiality. Implement them into your pipeline process.

You might move data between environments, so you should consider whether it's encrypted in transit as well as at rest to maintain confidentiality. In addition, if you're handling personal data, you should ensure that any personally identifiable information (PII) gets shielded where required.

You should also maintain data integrity by ensuring any merges happen with the correct, most up-to-date information you have available. Finally, any changes shouldn't cause your systems or users to lose availability to their data., so make sure access controls reflect the latest changes to your databases and the merge doesn't result in any corrupted data.

![image](https://github.com/juzweb/security/assets/2524790/8fa0a00e-116b-466f-944c-f687e740a1a8)

# Tooling
**GitHub actions**: If you store your code on GitHub, actions allow you to define automated workflows that'll be triggered when you merge your code or open pull requests. They can scan your code for vulnerabilities, run your testing scripts against changes to ensure they meet your requirements, or directly deploy the code to cloud environments. You can get pre-made actions that the community has created or write your own.

**BitBucket pipelines**: This is an Atlassian tool that allows you to deploy with automated workflows from its code repository Bitbucket. If integrated with your environment, you can see which version of your product is running in different environments. You can define the steps you want to take during the deployment in a YAML file, which can include running static code tests or pushing the latest version to a cloud storage service where your systems can access it.

**Liquibase**: Marketed as version control for your database, Liquibase allows you to integrate lots of DevSecOps practices into database management. Their product allows for flexible schema changes with support for major formats such as XML and JSON. You can perform migrations with rerunnable or non-rerunnable modifications, and it will enable you to roll back to previous versions or schemas as required.

**Tripwire**: This tool offers several products to help with the DevSecOps deployment phase. One, in particular, is its file integrity management product that aims to help you ensure non-repudiation by automatically detecting changes to files, who made them, and whether the change generated a non-compliance.






