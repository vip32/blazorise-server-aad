# blazorise-server-aad

+ Blazor Server

+ Blazorise: https://github.com/stsrki/Blazorise

+ AAD app roles: https://docs.microsoft.com/en-us/azure/architecture/multitenant-identity/app-roles
+ AAD + GraphApi + new Microsoft.Identity.Web: https://developer.microsoft.com/en-us/identity/blogs/how-to-build-a-blazor-web-app-with-azure-active-directory-authentication-and-microsoft-graph/


### Azure Setup
- create an AAD app registration (usualy done when creating new webapp in VS + Authentication)
- App registration generate clientsecret, put in appsettings.clientsecret
- App registration (setup roles), change manifest (JSON) 
```
"appRoles": [
        {
            "allowedMemberTypes": [
                "User"
            ],
            "description": "Editors Have the ability to manage owned tasks.",
            "displayName": "Editor",
            "id": "d1c2ade8-98f8-45fd-aa4a-6d06b947c31f",
            "isEnabled": true,
            "lang": null,
            "origin": "Application",
            "value": "Editor"
        },
        {
            "allowedMemberTypes": [
                "User"
            ],
            "description": "Administrator Have the ability to manage all tasks.",
            "displayName": "Administrator",
            "id": "d1c2ade8-98f8-45fd-aa4a-6d06b947c30f",
            "isEnabled": true,
            "lang": null,
            "origin": "Application",
            "value": "Administrator"
        }
    ],
```
- Enterprise application, add User + assing Role
- Application, role available as claim (See Pages\Dashboard.razor)