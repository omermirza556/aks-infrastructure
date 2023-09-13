# Summary

Hosts ***Azure Kubernetes Service*** (AKS) and ***Azure Container Registry*** (ACR) ***Azure Resource Management*** (ARM) templates for CI/CD deployments.

# Templates

There are multiple ways to store ***infrastructure as code*** (IAC) for Azure Resources. Common solutions include:
- ARM Templates
- Bicep Templates
- Terraform Templates

This solution uses ARM templates for infrastructure deployment. ***ARM templates have two major advantages***:

- When going through the Azure portal to create resources, you are given the option to download ARM template representations and parameters before the resource is actually created.

- If the resource is already existing, you can generate an ARM template for the resource to implement with ***Continuous Integration and Continious Delivery/Deployments*** (CI/CD) pipelines.


# Parameters

In the resource template file you can see that it makes use of variables that are referenced through the rest of the template. 
- You can set these variables/parameters to a default value, but it is better to have a dedicated file to host these parameters.
- The main advantage is being able to reuse a resource template for consistency between environments, only changing environment specific variables.

# How to Run

**Requirements:**

- An Active ***Azure Subscription***

- An ***Azure DevOps*** workspace

- An ***Azure Service Connection*** in Azure DevOps

**Optional:**

- ***GitHub*** - Since Azure DevOps contains its own Git repos, using GitHub is optional.

- ***Visual Studio Code*** - While optional, using VSCode makes working with templates so much easier. There are a lot of useful extensions to use. Here are a few recomendations:
    - json
    - GitHub Repositories
    - Azure CLI Tools
    - Azure Account
    - Azure Repos
    - Azure Resources

**The typical workflow to deploy ARM templates are as follows:**

- Commit code to a Git repository. I have used both GitHub and Azure DevOps Repos to store code.

- Create an Azure Pipeline to package up the project as an artifact. This is typically referred to as a build pipeline. 

- Create another pipeline to take that artifact and deploy it to the Azure environment. This is typically referred to as a release pipeline.

# Glossary

***Git*** - A distributed version control system that tracks changes in any set of computer files.

***Azure DevOps*** - A Microsoft product that provides version control, reporting, requirements management, project management, automated builds, testing and release management capabilities. It covers the entire application lifecycle and enables DevOps capabilities.

***Azure Service Connection*** - A defined connection that allows Azure DevOps to communicate with an external service.

***Artifact*** - The designated Azure name for all by-products of the coding and build process.

***Build Pipeline*** - Used to generate Artifacts out of Source Code.

***Release Pipeline*** - Consumes the Artifacts and conducts follow-up actions within a multi-staging system.

***Continuous Integration (CI)*** - The practice of integrating all your code changes into the main branch of a shared source code repository early and often.

***Continious Delivery/Deployments (CD)*** - A software development practice that works in conjunction with CI to automate the infrastructure provisioning and application release process


