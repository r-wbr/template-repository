# Structure
This repository contains collection of templates and scripts to deploy a new Azure environment, composed of a modular platform landing zone and landing zones for different purposes, like lift & shift migration, applications, or other workloads.

## Folders
🗂️src (source)  
The source code folder. Contains templates based on different languages.  
📗lib (library)  
Contains library files, like configuration files for resources or affix lists. Does not contain child resources!  
🗒️doc (documentation)  
Contains the project documentation.  
🖼️img (resources)  
Contains static image resources for the repository, like architecture drawings or media images.  
🛠️tools  
Contains scripts for deployments or other tasks.  

## Documentation
The documentation readme file should contain the following:
- A brief description of the project.
- The actual status of the project.
- Who maintains and how to contribute.
- Known issues or a FAQ.

# Structure
Each template, policy definition or ruleset must be contained in its own folder, whereby deployments are put in the source folder, based on the used language and policies or rulesets in the library folder. For consistency create all files and folders in **camelCase** notation.

## Templates
The name of the deployment folder should include a short description of the deployed resources or modules. Include a README.md file that explains the deployed resources, child resources, possible auto-generated values, parameters which need to be defined before deployment and the deployment scope.

### Azure resource manager templates
📁src\📁arm\📁templateName\  
📄azuredeploy.json  
📄azuredeploy.parameters.json  
📄README.md  

### Bicep templates
📁src\📁bicep\📁templateName\  
📄main.bicep  
📄main.bicepparam  
📄README.md  
📁src\📁bicep\📁templateName\📁modules\  
📄moduleName.bicep  

### Terraform templates
📁src\📁terraform\📁templateName\  
📄main.tf  
📄variables.tf  
📄moduleName.tf  
📄README.md  

## Tools
Include the function and dependencies in the script file as comment.  
📁tools\📁powershell\  
📄scriptName.ps1  

## Library
The library includes reusable configuration or ruleset files which can be included in, or referenced from, other templates. Include a README.md file that File that provides an overview of the configuration files and their function.

📁lib\  
📄configName.yaml  
📄README.md

### Policy definitions
The name of the policy definition folder and file should include the relevant resource provider or category and a short description of the policy rule. Include a README.md file that explains how the Azure Policy works, and to which scope it must be assigned.

📁lib\📁policies\📁policyName\  
📄policyName.json  
📄README.md  

### Network security group or firewall rules
The name of the rulset folder and file should include the targeted workload or service and expected effects. Include a README.md file that explains the used service tags, dependent application security groups and possible IP-address ranges or IP-groups, hardcoded or as parameters.

📁lib\📁rulesets\📁rulesetName\  
📄rulesetName.json  
📄README.md  