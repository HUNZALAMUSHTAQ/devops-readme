###  Pipelines with Azure Devops 
Here how current Azure pipelines are configured right now. 
### Build pipelines 

- Import JSON File into Azure pipelines
- Add bitbucket repository 
- select brach working on
- remember to change arguments /p: environment=Dev in pipeline according to your requirement in - task: DotNetCoreCLI@2 .
- Add secrets to your variables in Azure Pipelines
- Add (AES Encryption in Azure Artifacts ) connect restore with this feed and also check Nuget option as well.
- `dotnet nuget push --source "AESEncryption" --api-key az <package-path>`

### Release Pipeline 

- Connect Artifacts from your build pipelines as per requirements.
- It contains 2 task IIS and SQL Deployement
- Add DB_USER and DB_PASSWORD in variables in release pipelines 
- Assign DB user permissions for DB ownership(User Mapping), create DB (server role), Manage, Also edit securables for this user Alter any DB , Connect any DB, Connect SQL, Create any DB. 
- Also allow it to sign in SQL Server Authentication.

```json
{
  "source": 2,
  "revision": 32,
  "description": null,
  "createdBy": {
    "displayName": "Health Quest Developer",
    "url": "https://spsprodcus5.vssps.visualstudio.com/A3a50f23e-1c49-4464-8471-5944875a86e6/_apis/Identities/91e62f48-5d06-6e16-b501-6ee42e2c3bc5",
    "_links": {
      "avatar": {
        "href": "https://dev.azure.com/healthquestdeveloper/_apis/GraphProfile/MemberAvatars/msa.OTFlNjJmNDgtNWQwNi03ZTE2LWI1MDEtNmVlNDJlMmMzYmM1"
      }
    },
    "id": "91e62f48-5d06-6e16-b501-6ee42e2c3bc5",
    "uniqueName": "healthquestdeveloper@outlook.com",
    "imageUrl": "https://dev.azure.com/healthquestdeveloper/_apis/GraphProfile/MemberAvatars/msa.OTFlNjJmNDgtNWQwNi03ZTE2LWI1MDEtNmVlNDJlMmMzYmM1",
    "descriptor": "msa.OTFlNjJmNDgtNWQwNi03ZTE2LWI1MDEtNmVlNDJlMmMzYmM1"
  },
  "createdOn": "2024-02-19T10:02:49.940Z",
  "modifiedBy": {
    "displayName": "Health Quest Developer",
    "url": "https://spsprodcus5.vssps.visualstudio.com/A3a50f23e-1c49-4464-8471-5944875a86e6/_apis/Identities/91e62f48-5d06-6e16-b501-6ee42e2c3bc5",
    "_links": {
      "avatar": {
        "href": "https://dev.azure.com/healthquestdeveloper/_apis/GraphProfile/MemberAvatars/msa.OTFlNjJmNDgtNWQwNi03ZTE2LWI1MDEtNmVlNDJlMmMzYmM1"
      }
    },
    "id": "91e62f48-5d06-6e16-b501-6ee42e2c3bc5",
    "uniqueName": "healthquestdeveloper@outlook.com",
    "imageUrl": "https://dev.azure.com/healthquestdeveloper/_apis/GraphProfile/MemberAvatars/msa.OTFlNjJmNDgtNWQwNi03ZTE2LWI1MDEtNmVlNDJlMmMzYmM1",
    "descriptor": "msa.OTFlNjJmNDgtNWQwNi03ZTE2LWI1MDEtNmVlNDJlMmMzYmM1"
  },
  "modifiedOn": "2024-03-06T14:08:58.537Z",
  "isDeleted": false,
  "isDisabled": false,
  "lastRelease": {
    "id": 72,
    "name": "Release-36",
    "artifacts": [],
    "_links": {},
    "description": "",
    "releaseDefinition": { "id": 2, "projectReference": null, "_links": {} },
    "createdOn": "2024-03-06T14:09:03.727Z",
    "createdBy": {
      "displayName": "Health Quest Developer",
      "url": "https://spsprodcus5.vssps.visualstudio.com/A3a50f23e-1c49-4464-8471-5944875a86e6/_apis/Identities/91e62f48-5d06-6e16-b501-6ee42e2c3bc5",
      "_links": {
        "avatar": {
          "href": "https://dev.azure.com/healthquestdeveloper/_apis/GraphProfile/MemberAvatars/msa.OTFlNjJmNDgtNWQwNi03ZTE2LWI1MDEtNmVlNDJlMmMzYmM1"
        }
      },
      "id": "91e62f48-5d06-6e16-b501-6ee42e2c3bc5",
      "uniqueName": "healthquestdeveloper@outlook.com",
      "imageUrl": "https://dev.azure.com/healthquestdeveloper/_apis/GraphProfile/MemberAvatars/msa.OTFlNjJmNDgtNWQwNi03ZTE2LWI1MDEtNmVlNDJlMmMzYmM1",
      "descriptor": "msa.OTFlNjJmNDgtNWQwNi03ZTE2LWI1MDEtNmVlNDJlMmMzYmM1"
    }
  },
  "variables": {
    "DB_USER": { "value": "azagent" },
    "DB_PASSWORD": { "value": "SHA123@" }
  },
  "variableGroups": [],
  "environments": [
    {
      "id": 2,
      "name": "IIS Deployment on-prem",
      "rank": 1,
      "owner": {
        "displayName": "Health Quest Developer",
        "url": "https://spsprodcus5.vssps.visualstudio.com/A3a50f23e-1c49-4464-8471-5944875a86e6/_apis/Identities/91e62f48-5d06-6e16-b501-6ee42e2c3bc5",
        "_links": {
          "avatar": {
            "href": "https://dev.azure.com/healthquestdeveloper/_apis/GraphProfile/MemberAvatars/msa.OTFlNjJmNDgtNWQwNi03ZTE2LWI1MDEtNmVlNDJlMmMzYmM1"
          }
        },
        "id": "91e62f48-5d06-6e16-b501-6ee42e2c3bc5",
        "uniqueName": "healthquestdeveloper@outlook.com",
        "imageUrl": "https://dev.azure.com/healthquestdeveloper/_apis/GraphProfile/MemberAvatars/msa.OTFlNjJmNDgtNWQwNi03ZTE2LWI1MDEtNmVlNDJlMmMzYmM1",
        "descriptor": "msa.OTFlNjJmNDgtNWQwNi03ZTE2LWI1MDEtNmVlNDJlMmMzYmM1"
      },
      "variables": {},
      "variableGroups": [],
      "preDeployApprovals": {
        "approvals": [
          { "rank": 1, "isAutomated": true, "isNotificationOn": false, "id": 4 }
        ],
        "approvalOptions": {
          "requiredApproverCount": null,
          "releaseCreatorCanBeApprover": false,
          "autoTriggeredAndPreviousEnvironmentApprovedCanBeSkipped": false,
          "enforceIdentityRevalidation": false,
          "timeoutInMinutes": 0,
          "executionOrder": 1
        }
      },
      "deployStep": { "id": 5 },
      "postDeployApprovals": {
        "approvals": [
          { "rank": 1, "isAutomated": true, "isNotificationOn": false, "id": 6 }
        ],
        "approvalOptions": {
          "requiredApproverCount": null,
          "releaseCreatorCanBeApprover": false,
          "autoTriggeredAndPreviousEnvironmentApprovedCanBeSkipped": false,
          "enforceIdentityRevalidation": false,
          "timeoutInMinutes": 0,
          "executionOrder": 2
        }
      },
      "deployPhases": [
        {
          "deploymentInput": {
            "healthPercent": 0,
            "deploymentHealthOption": "Custom",
            "tags": [],
            "skipArtifactsDownload": false,
            "artifactsDownloadInput": { "downloadInputs": [] },
            "queueId": 11,
            "demands": [],
            "enableAccessToken": false,
            "timeoutInMinutes": 0,
            "jobCancelTimeoutInMinutes": 1,
            "condition": "succeeded()",
            "overrideInputs": {}
          },
          "rank": 1,
          "phaseType": 4,
          "name": "IIS Deployment",
          "refName": null,
          "workflowTasks": [
            {
              "environment": {},
              "taskId": "1b467810-6725-4b6d-accd-886174c09bba",
              "version": "0.*",
              "name": "IIS Web App Deploy",
              "refName": "",
              "enabled": true,
              "alwaysRun": false,
              "continueOnError": false,
              "timeoutInMinutes": 0,
              "retryCountOnTaskFailure": 0,
              "definitionType": null,
              "overrideInputs": {},
              "condition": "succeeded()",
              "inputs": {
                "WebSiteName": "$(Parameters.WebsiteName)",
                "VirtualApplication": "Backend",
                "Package": "$(System.DefaultWorkingDirectory)\\**\\*.zip",
                "SetParametersFile": "",
                "RemoveAdditionalFilesFlag": "false",
                "ExcludeFilesFromAppDataFlag": "false",
                "TakeAppOfflineFlag": "true",
                "AdditionalArguments": "",
                "XmlTransformation": "false",
                "XmlVariableSubstitution": "True",
                "JSONFiles": ""
              }
            },
            {
              "environment": {},
              "taskId": "1b2aec60-dc49-11e6-9b76-63056e018cac",
              "version": "0.*",
              "name": "IIS Web App Manage",
              "refName": "",
              "enabled": false,
              "alwaysRun": false,
              "continueOnError": false,
              "timeoutInMinutes": 0,
              "retryCountOnTaskFailure": 0,
              "definitionType": null,
              "overrideInputs": {},
              "condition": "succeeded()",
              "inputs": {
                "EnableIIS": "false",
                "IISDeploymentType": "$(Parameters.IISDeploymentType)",
                "ActionIISWebsite": "$(Parameters.ActionIISWebsite)",
                "ActionIISApplicationPool": "CreateOrUpdateAppPool",
                "StartStopWebsiteName": "$(Parameters.WebsiteName)",
                "WebsiteName": "$(Parameters.WebsiteName)",
                "WebsitePhysicalPath": "C:\\inetpub\\wwwroot\\Dev2\\Backend",
                "WebsitePhysicalPathAuth": "WebsiteUserPassThrough",
                "WebsiteAuthUserName": "",
                "WebsiteAuthUserPassword": "",
                "AddBinding": "$(Parameters.AddBinding)",
                "Protocol": "http",
                "IPAddress": "All Unassigned",
                "Port": "80",
                "ServerNameIndication": "false",
                "HostNameWithOutSNI": "",
                "HostNameWithHttp": "",
                "HostNameWithSNI": "",
                "SSLCertThumbPrint": "",
                "Bindings": "$(Parameters.Bindings)",
                "CreateOrUpdateAppPoolForWebsite": "false",
                "ConfigureAuthenticationForWebsite": "false",
                "AppPoolNameForWebsite": "Dev",
                "DotNetVersionForWebsite": "v4.0",
                "PipeLineModeForWebsite": "Integrated",
                "AppPoolIdentityForWebsite": "ApplicationPoolIdentity",
                "AppPoolUsernameForWebsite": "",
                "AppPoolPasswordForWebsite": "",
                "AnonymousAuthenticationForWebsite": "false",
                "BasicAuthenticationForWebsite": "false",
                "WindowsAuthenticationForWebsite": "true",
                "ParentWebsiteNameForVD": "$(Parameters.WebsiteName)",
                "VirtualPathForVD": "$(Parameters.VirtualPathForApplication)",
                "PhysicalPathForVD": "%SystemDrive%\\inetpub\\wwwroot",
                "VDPhysicalPathAuth": "VDUserPassThrough",
                "VDAuthUserName": "",
                "VDAuthUserPassword": "",
                "ParentWebsiteNameForApplication": "$(Parameters.WebsiteName)",
                "VirtualPathForApplication": "$(Parameters.VirtualPathForApplication)",
                "PhysicalPathForApplication": "%SystemDrive%\\inetpub\\wwwroot",
                "ApplicationPhysicalPathAuth": "ApplicationUserPassThrough",
                "ApplicationAuthUserName": "",
                "ApplicationAuthUserPassword": "",
                "CreateOrUpdateAppPoolForApplication": "false",
                "AppPoolNameForApplication": "",
                "DotNetVersionForApplication": "v4.0",
                "PipeLineModeForApplication": "Integrated",
                "AppPoolIdentityForApplication": "ApplicationPoolIdentity",
                "AppPoolUsernameForApplication": "",
                "AppPoolPasswordForApplication": "",
                "AppPoolName": "$(Parameters.AppPoolName)",
                "DotNetVersion": "v4.0",
                "PipeLineMode": "Integrated",
                "AppPoolIdentity": "ApplicationPoolIdentity",
                "AppPoolUsername": "",
                "AppPoolPassword": "",
                "StartStopRecycleAppPoolName": "",
                "AppCmdCommands": ""
              }
            }
          ]
        }
      ],
      "environmentOptions": {
        "emailNotificationType": "OnlyOnFailure",
        "emailRecipients": "release.environment.owner;release.creator",
        "skipArtifactsDownload": false,
        "timeoutInMinutes": 0,
        "enableAccessToken": false,
        "publishDeploymentStatus": true,
        "badgeEnabled": false,
        "autoLinkWorkItems": false,
        "pullRequestDeploymentEnabled": false
      },
      "demands": [],
      "conditions": [
        {
          "name": "ReleaseStarted",
          "conditionType": 1,
          "value": "",
          "result": null
        }
      ],
      "executionPolicy": { "concurrencyCount": 1, "queueDepthCount": 0 },
      "schedules": [],
      "currentRelease": {
        "id": 72,
        "url": "https://vsrm.dev.azure.com/healthquestdeveloper/48af52c3-c4ed-4bd4-aaa6-911ceea2f37c/_apis/Release/releases/72",
        "_links": {}
      },
      "retentionPolicy": {
        "daysToKeep": 30,
        "releasesToKeep": 3,
        "retainBuild": true
      },
      "processParameters": {
        "inputs": [
          {
            "aliases": [],
            "options": {
              "IISWebsite": "IIS Website",
              "IISWebApplication": "IIS Web Application",
              "IISVirtualDirectory": "IIS Virtual Directory",
              "IISApplicationPool": "IIS Application Pool"
            },
            "properties": {},
            "name": "IISDeploymentType",
            "label": "Configuration type",
            "defaultValue": "IISWebsite",
            "required": true,
            "type": "pickList",
            "helpMarkDown": "You can create or update sites, applications, virtual directories, and application pools.",
            "groupName": ""
          },
          {
            "aliases": [],
            "options": {
              "CreateOrUpdateWebsite": "Create Or Update",
              "StartWebsite": "Start",
              "StopWebsite": "Stop"
            },
            "properties": {},
            "name": "ActionIISWebsite",
            "label": "Action",
            "defaultValue": "CreateOrUpdateWebsite",
            "required": true,
            "type": "pickList",
            "helpMarkDown": "Select the appropriate action that you want to perform on an IIS website.<br /><br />\\\"Create Or Update\\\" will create a website or update an existing website.<br /><br /> Start, Stop will start or stop the website respectively.",
            "visibleRule": "IISDeploymentType = IISWebsite",
            "groupName": ""
          },
          {
            "aliases": [],
            "options": {},
            "properties": {},
            "name": "WebsiteName",
            "label": "Website name",
            "defaultValue": "DevPipeline",
            "required": true,
            "type": "string",
            "helpMarkDown": "Provide the name of the IIS website to create or update.",
            "groupName": ""
          },
          {
            "aliases": [],
            "options": {},
            "properties": {},
            "name": "AddBinding",
            "label": "Add binding",
            "defaultValue": "True",
            "type": "boolean",
            "helpMarkDown": "Select the option to add port binding for the website.",
            "visibleRule": "IISDeploymentType = IISWebsite && ActionIISWebsite = CreateOrUpdateWebsite",
            "groupName": ""
          },
          {
            "aliases": [],
            "options": {},
            "properties": {
              "resizable": "true",
              "editorExtension": "ms.vss-services-azure.iis-multiple-binding",
              "displayFormat": "{{#bindings}}{{protocol}}/{{ipAddress}}:{{port}}:{{hostname}}\n{{/bindings}}"
            },
            "name": "Bindings",
            "label": "Add bindings",
            "defaultValue": "{\"bindings\":[{\"protocol\":\"https\",\"ipAddress\":\"All Unassigned\",\"port\":\"9091\",\"hostname\":\"\",\"sslThumbprint\":\"a04e6fd70061e4fde149c5f11eac7b1855a64a26\",\"sniFlag\":false}]}",
            "required": true,
            "type": "multiLine",
            "helpMarkDown": "Click on the extension [...] button to add bindings for the website.",
            "visibleRule": "IISDeploymentType = IISWebsite && ActionIISWebsite = CreateOrUpdateWebsite && AddBinding = true",
            "groupName": ""
          },
          {
            "aliases": [],
            "options": {},
            "properties": {},
            "name": "AppPoolName",
            "label": "Application pool name",
            "defaultValue": "",
            "required": true,
            "type": "string",
            "helpMarkDown": "Provide the name of the IIS application pool to create or update.",
            "visibleRule": "IISDeploymentType = IISApplicationPool",
            "groupName": ""
          },
          {
            "aliases": [],
            "options": {},
            "properties": {},
            "name": "VirtualPathForApplication",
            "label": "Virtual path",
            "defaultValue": "",
            "required": true,
            "type": "string",
            "helpMarkDown": "Provide the virtual path of the application. <br /><br />Example: To create an application Site/Application enter /Application. The parent website should be already existing.",
            "visibleRule": "IISDeploymentType = IISWebApplication || IISDeploymentType = IISVirtualDirectory",
            "groupName": ""
          }
        ]
      },
      "properties": {
        "BoardsEnvironmentType": {
          "$type": "System.String",
          "$value": "unmapped"
        },
        "LinkBoardsWorkItems": { "$type": "System.String", "$value": "False" }
      },
      "preDeploymentGates": { "id": 0, "gatesOptions": null, "gates": [] },
      "postDeploymentGates": { "id": 0, "gatesOptions": null, "gates": [] },
      "environmentTriggers": [],
      "badgeUrl": "https://vsrm.dev.azure.com/healthquestdeveloper/_apis/public/Release/badge/48af52c3-c4ed-4bd4-aaa6-911ceea2f37c/2/2"
    },
    {
      "id": 4,
      "name": "DB Deployment",
      "rank": 2,
      "owner": {
        "displayName": "Health Quest Developer",
        "url": "https://spsprodcus5.vssps.visualstudio.com/A3a50f23e-1c49-4464-8471-5944875a86e6/_apis/Identities/91e62f48-5d06-6e16-b501-6ee42e2c3bc5",
        "_links": {
          "avatar": {
            "href": "https://dev.azure.com/healthquestdeveloper/_apis/GraphProfile/MemberAvatars/msa.OTFlNjJmNDgtNWQwNi03ZTE2LWI1MDEtNmVlNDJlMmMzYmM1"
          }
        },
        "id": "91e62f48-5d06-6e16-b501-6ee42e2c3bc5",
        "uniqueName": "healthquestdeveloper@outlook.com",
        "imageUrl": "https://dev.azure.com/healthquestdeveloper/_apis/GraphProfile/MemberAvatars/msa.OTFlNjJmNDgtNWQwNi03ZTE2LWI1MDEtNmVlNDJlMmMzYmM1",
        "descriptor": "msa.OTFlNjJmNDgtNWQwNi03ZTE2LWI1MDEtNmVlNDJlMmMzYmM1"
      },
      "variables": {},
      "variableGroups": [],
      "preDeployApprovals": {
        "approvals": [
          {
            "rank": 1,
            "isAutomated": true,
            "isNotificationOn": false,
            "id": 10
          }
        ],
        "approvalOptions": {
          "requiredApproverCount": null,
          "releaseCreatorCanBeApprover": false,
          "autoTriggeredAndPreviousEnvironmentApprovedCanBeSkipped": false,
          "enforceIdentityRevalidation": false,
          "timeoutInMinutes": 0,
          "executionOrder": 1
        }
      },
      "deployStep": { "id": 11 },
      "postDeployApprovals": {
        "approvals": [
          {
            "rank": 1,
            "isAutomated": true,
            "isNotificationOn": false,
            "id": 12
          }
        ],
        "approvalOptions": {
          "requiredApproverCount": null,
          "releaseCreatorCanBeApprover": false,
          "autoTriggeredAndPreviousEnvironmentApprovedCanBeSkipped": false,
          "enforceIdentityRevalidation": false,
          "timeoutInMinutes": 0,
          "executionOrder": 2
        }
      },
      "deployPhases": [
        {
          "deploymentInput": {
            "parallelExecution": { "parallelExecutionType": 0 },
            "agentSpecification": null,
            "skipArtifactsDownload": false,
            "artifactsDownloadInput": { "downloadInputs": [] },
            "queueId": 12,
            "demands": [],
            "enableAccessToken": false,
            "timeoutInMinutes": 0,
            "jobCancelTimeoutInMinutes": 1,
            "condition": "succeeded()",
            "overrideInputs": {}
          },
          "rank": 1,
          "phaseType": 1,
          "name": "Agent job",
          "refName": null,
          "workflowTasks": [
            {
              "environment": {},
              "taskId": "4b506f7f-720f-47bb-bf21-029bac6a690d",
              "version": "0.*",
              "name": "Deploy using : sql script",
              "refName": "",
              "enabled": true,
              "alwaysRun": false,
              "continueOnError": false,
              "timeoutInMinutes": 0,
              "retryCountOnTaskFailure": 0,
              "definitionType": "task",
              "overrideInputs": {},
              "condition": "succeeded()",
              "inputs": {
                "TaskType": "sqlQuery",
                "DacpacFile": "",
                "SqlFile": "$(System.DefaultWorkingDirectory)\\_Health Quest-ASP.NET Core-CI\\drop\\migrations\\HealthQuestDBContext.sql",
                "ExecuteInTransaction": "false",
                "ExclusiveLock": "false",
                "AppLockName": "",
                "InlineSql": "",
                "TargetMethod": "server",
                "ServerName": "localhost,1433",
                "DatabaseName": "azagent-dev",
                "AuthScheme": "sqlServerAuthentication",
                "SqlUsername": "$(DB_USER)",
                "SqlPassword": "$(DB_PASSWORD)",
                "ConnectionString": "",
                "PublishProfile": "",
                "AdditionalArguments": "",
                "AdditionalArgumentsSql": ""
              }
            }
          ]
        }
      ],
      "environmentOptions": {
        "emailNotificationType": "OnlyOnFailure",
        "emailRecipients": "release.environment.owner;release.creator",
        "skipArtifactsDownload": false,
        "timeoutInMinutes": 0,
        "enableAccessToken": false,
        "publishDeploymentStatus": true,
        "badgeEnabled": false,
        "autoLinkWorkItems": false,
        "pullRequestDeploymentEnabled": false
      },
      "demands": [],
      "conditions": [
        {
          "name": "IIS Deployment on-prem",
          "conditionType": 2,
          "value": "4",
          "result": null
        }
      ],
      "executionPolicy": { "concurrencyCount": 1, "queueDepthCount": 0 },
      "schedules": [],
      "currentRelease": {
        "id": 72,
        "url": "https://vsrm.dev.azure.com/healthquestdeveloper/48af52c3-c4ed-4bd4-aaa6-911ceea2f37c/_apis/Release/releases/72",
        "_links": {}
      },
      "retentionPolicy": {
        "daysToKeep": 30,
        "releasesToKeep": 3,
        "retainBuild": true
      },
      "processParameters": {},
      "properties": {
        "BoardsEnvironmentType": {
          "$type": "System.String",
          "$value": "unmapped"
        },
        "LinkBoardsWorkItems": { "$type": "System.String", "$value": "False" }
      },
      "preDeploymentGates": { "id": 0, "gatesOptions": null, "gates": [] },
      "postDeploymentGates": { "id": 0, "gatesOptions": null, "gates": [] },
      "environmentTriggers": [],
      "badgeUrl": "https://vsrm.dev.azure.com/healthquestdeveloper/_apis/public/Release/badge/48af52c3-c4ed-4bd4-aaa6-911ceea2f37c/2/4"
    }
  ],
  "artifacts": [
    {
      "sourceId": "48af52c3-c4ed-4bd4-aaa6-911ceea2f37c:2",
      "type": "Build",
      "alias": "_Health Quest-ASP.NET Core-CI",
      "definitionReference": {
        "artifactSourceDefinitionUrl": {
          "id": "https://dev.azure.com/healthquestdeveloper/_permalink/_build/index?collectionId=4740632f-ce77-4200-bd86-dcec786f3fca&projectId=48af52c3-c4ed-4bd4-aaa6-911ceea2f37c&definitionId=2",
          "name": ""
        },
        "defaultVersionBranch": { "id": "", "name": "" },
        "defaultVersionSpecific": { "id": "", "name": "" },
        "defaultVersionTags": { "id": "", "name": "" },
        "defaultVersionType": { "id": "latestType", "name": "Latest" },
        "definition": { "id": "2", "name": "Health Quest-ASP.NET Core-CI" },
        "definitions": { "id": "", "name": "" },
        "IsMultiDefinitionType": { "id": "False", "name": "False" },
        "project": {
          "id": "48af52c3-c4ed-4bd4-aaa6-911ceea2f37c",
          "name": "Health Quest"
        },
        "repository": { "id": "", "name": "" }
      },
      "isPrimary": true,
      "isRetained": false
    }
  ],
  "triggers": [
    {
      "artifactAlias": "_Health Quest-ASP.NET Core-CI",
      "triggerConditions": [],
      "triggerType": 1
    }
  ],
  "releaseNameFormat": "Release-$(rev:r)",
  "tags": [],
  "properties": {
    "DefinitionCreationSource": {
      "$type": "System.String",
      "$value": "ReleaseNew"
    },
    "IntegrateBoardsWorkItems": { "$type": "System.String", "$value": "False" },
    "IntegrateJiraWorkItems": { "$type": "System.String", "$value": "false" }
  },
  "id": 2,
  "name": "Folio3 HealthQuest Release",
  "path": "\\",
  "projectReference": null,
  "url": "https://vsrm.dev.azure.com/healthquestdeveloper/48af52c3-c4ed-4bd4-aaa6-911ceea2f37c/_apis/Release/definitions/2",
  "_links": {
    "self": {
      "href": "https://vsrm.dev.azure.com/healthquestdeveloper/48af52c3-c4ed-4bd4-aaa6-911ceea2f37c/_apis/Release/definitions/2"
    },
    "web": {
      "href": "https://dev.azure.com/healthquestdeveloper/48af52c3-c4ed-4bd4-aaa6-911ceea2f37c/_release?definitionId=2"
    }
  }
}

```


### Azure Pipeline [Agents](https://learn.microsoft.com/en-us/azure/devops/pipelines/agents/agents?view=azure-devops&tabs=yaml%2Cbrowser) 

Currenty we are using two agents:
- Microsoft  Hosted Agents (MHSA)
- Self Hosted Agents (SHA)


![Untitled](https://github.com/HUNZALAMUSHTAQ/devops-readme/assets/75185145/89be01f4-df08-41ad-9582-90ec489169ce)



## Here how to add SHA. 

There are 3 Pools in Agents you can create as many pool you like according to your needs 
- Azure Pipeline (**MHSA**)
- Self Hosted Agents (**HSA**)


![image](https://github.com/HUNZALAMUSHTAQ/devops-readme/assets/75185145/ba55a177-dcee-4a5f-a59b-67404deed78c)

You add agents in your pool by clicking New agents according to your system specifications. 

![image](https://github.com/HUNZALAMUSHTAQ/devops-readme/assets/75185145/8d309d96-7aee-48fe-b2c4-34f042e76aae)

Configure your account by following the steps outlined [here](https://learn.microsoft.com/en-us/azure/devops/pipelines/agents/windows-agent?view=azure-devops#permissions).

![image](https://github.com/HUNZALAMUSHTAQ/devops-readme/assets/75185145/dc470d18-6675-4487-b745-e836c15abf18)



**Why Azure artifacts  ?**

We have our own AES Encryption Package used in Health Quest other than Nuget Packages we restore packages from azure artifacts and Nuget itself. 

Manage all package types (NuGet, npm, Maven, etc.) across various programming languages from a single platform, simplifying package management.

***Publish Package to Azure Artifacts *
**

`dotnet nuget push --source "AESEncryption" --api-key az <package-path>`

***How to create, host, and share packages with Azure Artifacts* **[click here](https://www.youtube.com/watch?v=xHNXwqxV7Uc)

### Deployment Process
###### 1. Code Retrieval
*Source*: Latest code from Bitbucket repository

###### 2. Build Orchestration
![image](https://github.com/HUNZALAMUSHTAQ/devops-readme/assets/75185145/fc4e2e07-371f-4a29-af8b-678cee5cf94c)



Build pipeline on Azure Pipelines build process is done on **SHA** or **MHSA**. Select Agent according to your requirements.

###### 3. Web Application Deployment and Database Deployment

###### Release Pipelines 

***Target***:  On-premises **Folio3** machine and SQL Server database on Folio3 server

***Mechanism***: IIS (Internet Information Services) web server and On-premises SQL scripts executed directly generated from build pipelines.



![image](https://github.com/HUNZALAMUSHTAQ/devops-readme/assets/75185145/9de39615-8290-4c39-aa25-8c1633b8e2b3)

Here is how your Stages Look like: 

![image](https://github.com/HUNZALAMUSHTAQ/devops-readme/assets/75185145/1b7b65a0-f0e9-461a-8a15-a92be46ca94a)

#### [Deployment Group ](https://learn.microsoft.com/en-us/azure/devops/pipelines/release/deployment-groups/?view=azure-devops)
> A deployment group is a logical set of deployment target machines that have agents installed on each one. Deployment groups represent the physical environments; for example, "Dev", "Test", "UAT", and "Production". In effect, a deployment group is just another grouping of agents, much like an agent pool.

![image](https://github.com/HUNZALAMUSHTAQ/devops-readme/assets/75185145/57fdb3ec-ee63-42c4-a6c3-56bb48fc5aa3)

Deployment groups define sets of target machines for deployments (Dev, Test, Production), while agent pools manage the deployment agents that execute tasks on those machines.

In our case we are deploying to the folio3 machine **(on-premise)**.

### FAQ
**What is a parallel job?**

Each running job consumes a *parallel job* that runs on an agent.
When not enough job? The jobs are queued up and run one after the other.

**Are there any limits on the number of builds and release pipelines that I can create?**

No. You can create hundreds or even thousands of pipelines for no charge. You can register any number of self-hosted agents for no charge.

