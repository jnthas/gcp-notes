# GCP Notes

Compute, Storage, Big Data, Machine Learning



## Introduction

Resource hierarchy levels:
- Project Node > Folders (depto, teams, projects) > Resources (Storage, etc)
- A project has ProjectId and ProjectNumber that are immutable and unique and ProjectName. ProjectNumber value is assigned by GCP.
- Use folder to assign policies
- Policies inherits from parents; and a more restrictive policy overwrite a less one. If you set a policy in a organization level all sub nodes will automatically inherited from organization.
- Important Rule: a most restrictive rule always replace a less one. eg. Organization > only view, Folder > modify --> The user could modify that folder.
- Services and APIs are enabled in a Project  



## IAM

- Who + can do what + on which resource
- "Who" can be a google account, group, service account or g suite domain
- There are 3 types of roles: Primitive, Predefined and Custom



### Primitive
Apply across all GCP services; it means that it's not possible to specify a resource, only all resources.
It can be **Owner** (invite members), **Editor** (deploy, configure), **Viewer** (read only) or **Billing Adm**
If you have sensitive data on a project, Primitive Role is **too coarse**!!!

### Predefined
Apply to a particular resuorce, project, folder or org. For example, a role applies to all users on a group, that can do all action in all VMs on project "A"

### Custom
Fine grained permissions, where users has the minimum to do their job. Cautions about custom roles: 
1) have to decide to use and manage the permissions 
2) custom roles can only be used project or org level (not folder)

### Server-to-server interactions

- It's possible to give permission to a resource (like a VM) to store data in a google cloud storage service. 
- It doesn't use password, but criptographic keys

  

## Interacting with GCP

- Web user interface
- CLI
- Console Mobile App
- REST-Based API
  - APIs Explorer - tool to try GCP API using browser 



## Cloud Marketplace (Cloud Launcher)

- It's a marketplace with pre-built solutions made by Google or third-party
- There is no need to configure, but it's possible before the deployment
- Most packages are no-additional charge but some of them, yes (particularly made by third-party)
- GCP updates base images to fix vulnerabilities but it won't update deployed images. It should be done manually