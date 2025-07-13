Managed identities provide an identity for applications to use when connecting to resources that support Azure Active Directory (Azure AD) authentication. We can access Graph API either using service principal object in Azure or using Managed Identity.   

 

When it comes to service Principal, we can grant API Permissions to the service principal object in Azure but incase of Managed Identity, we do not have option to provide Graph API permission for Managed Identity object via portal.  Hence we need to use the below PowerShell script to grant Graph API Permission (Application Permission) to the managed Identity object.

 

 In this blog, we will see how to grant graph API permission to the Managed Identity object

 

Note: To provide Graph API Permission you need to be Global Administrator in Azure Active Directory

 

Below Parameters needs to be modified as per your resources:

TenantID : Provide the tenantID of your subscription
GraphAppId : This parameter is optional. We don’t have to change this value. This corresponds to Graph API Guid.
DisplayNameofMSI :  Provide your Logic App name. Since managed identity will be created in the same name as the resource on which identity is enabled, we can provide the Logic App name
Permissions : Provide the appropriate Graph API Permission. https://docs.microsoft.com/en-us/graph/permissions-reference. Note: These are application permission.
