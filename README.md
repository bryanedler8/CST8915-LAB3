# CST8915-LAB3
# CST8915 Lab 1: Algonquin Pet Store on Azure VM

**Student Name**: [Your Name]
**Student ID**: [Your Student ID]
**Course**: CST8915 Full-stack Cloud-native Development
**Semester**: Winter 2026

---

## Demo Video

🎥 [Watch Demo Video](https://www.youtube.com/watch?v=YOUR_VIDEO_ID)

---

## Reflection Questions

### What challenges did you encounter when configuring environment variables in the GitHub Actions workflow?


When setting up environment variables in GitHub Actions, several practical difficulties were observed.
Firstly, managing sensitive information such as API keys and database passwords required the use of GitHub Secrets. Ensuring that these secrets were correctly referenced and not accidentally printed in logs demanded careful attention.
Secondly, handling different values for development, staging, and production environments within the same workflow was complex without duplicating code. This was addressed using GitHub Environments and variable contexts.
Additionally, syntax errors were common, particularly when distinguishing between vars, secrets, and the env context. Another issue involved passing non-string values, such as numbers or boolean flags, into scripts or containers, which sometimes caused unexpected behaviour.
Finally, when using matrix builds for multiple microservices, dynamically assigning the correct variables to each job increased the complexity of the workflow.


### How does deploying microservices on Azure Web App Service differ from running them locally?

Running microservices locally and deploying them on Azure Web App Service involves several important differences.

Environment and Dependencies: Locally, services run on fixed ports and rely on local configuration files such as .env. On Azure, configuration is managed through Application Settings, which are injected as environment variables at runtime.

Infrastructure and Scaling: A local setup typically runs a single instance of each service. In contrast, Azure Web App supports automatic scaling, load balancing, and multiple instances without manual intervention.

Persistence and Storage: Local environments often allow read and write access to the file system. On Azure, the file system is ephemeral and not intended for persistent storage; external services such as Azure Blob Storage or databases must be used instead.  

### Why is it important to use environment variables for configurations in a cloud environment?

Environment variables help with:  

Separation of Code and Configuration: By storing configuration outside the source code, the same build artifact can be deployed across multiple stages such as development, testing, and production without being recompiled.

Security Enhancement: Environment variables prevent hardcoded credentials from being committed to version control. Cloud platforms encrypt these variables and allow secure integration with services like Azure Key Vault.

Operational Flexibility: Configuration values such as database connection strings, API endpoints, or feature toggles can be modified by operations teams without requiring a new deployment or code change.



