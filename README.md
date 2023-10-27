# vscode

## node.js
https://www.geeksforgeeks.org/installation-of-node-js-on-windows/

## Config 1st time:
https://marketplace.visualstudio.com/items?itemName=salesforce.salesforcedx-vscode

## Salesforce Extension Pack
https://marketplace.visualstudio.com/items?itemName=salesforce.salesforcedx-vscode

## Salesforce CLI:
https://github.com/salesforcecli/cli/
https://developer.salesforce.com/tools/salesforcecli
https://developer.salesforce.com/docs/atlas.en-us.sfdx_setup.meta/sfdx_setup/sfdx_setup_install_cli.htm#sfdx_setup_install_cli_windows

#### sfdx config
https://developer.salesforce.com/docs/atlas.en-us.sfdx_dev.meta/sfdx_dev/sfdx_dev_ws_config.htm
#### troubleshooting
https://developer.salesforce.com/tools/vscode/en/troubleshooting

npm uninstall package-name

## PMD
https://docs.pmd-code.org/latest/pmd_rules_apex_bestpractices.html

## Configure new task:
https://code.visualstudio.com/docs/editor/tasks#vscode

```
{
        // See https://go.microsoft.com/fwlink/?LinkId=733558
        // for the documentation about the tasks.json format
        "version": "2.0.0",
        "tasks": [
                {
                        "label": "sf-get",
                        "type": "shell",
                        "command": "sfdx",
                        "args": [
                                "force:source:retrieve",
                                "-m",
                                "\"${input:varType}:${input:varObjectName}\""
                        ],
                        "group": "build",
                        "presentation": {
                                // Reveal the output only if unrecognized errors occur.
                                "reveal": "always"
                        },
                        // Use the standard MS compiler pattern to detect errors, warnings and infos
                        "problemMatcher": "$eslint-compact"
                }
        ],
        "inputs": [
                {
                        "type": "pickString",
                        "id": "varType",
                        "description": "What type of Object?",
                        "options": [
                          "ApexClass",
                          "ApexTrigger",
                          "LightningComponentBundle",
                          "AuraDefinitionBundle",
                          "CustomObject",
                          "Flow"
                        ],
                        "default": "ApexClass"
                },
                {
                        "type": "promptString",
                        "id": "varObjectName",
                        "description": "Objects to retieve",
                        "default": "Constant"
                }
        ]
}

```
