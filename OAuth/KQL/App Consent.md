//Track when application is allowed and provides details on app and resource

AuditLogs
| where TimeGenerated > ago(1d) //Can change time range to whenever
| where OperationName == "Consent to application"
| extend ActorUPN = InitiatedBy.user.userPrincipalName
| extend ActorIP = InitiatedBy.user.ipAddress
| extend ActorID = InitiatedBy.user.id
| extend Application = TargetResources[0].displayName
| extend ApplicationId = TargetResources[0].id
| mv-expand ExpandedTargets = TargetResources[0].modifiedProperties
| where ExpandedTargets.displayName startswith "ConsentAction.Permissions"
| mv-expand Consents=ExpandedTargets.newValue
| extend Consents = split(Consents, "],")
| mv-expand Consents
| parse-kv Consents as (ClientId:string, PrincipalId: string, ResourceId: string, ConsentType:string, Scope:string) with (pair_delimiter=',', kv_delimiter=':')
| project TimeGenerated, Application, ApplicationId, ActorUPN, ActorID, ActorIP, Result, ClientId, PrincipalId, ResourceId, ConsentType, Scope, ResultReason




UEBA Settings
![image](https://github.com/MSJosh/TTTTUB/assets/120500937/bcac2162-666f-4479-b4d9-fe8b9a71f017)
