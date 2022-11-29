# vscode

## Configure new task:
https://code.visualstudio.com/docs/editor/tasks#vscode

```
{
        // See https://go.microsoft.com/fwlink/?LinkId=733558
        // for the documentation about the tasks.json format
        "version": "2.0.0",
        "tasks": [
                {
                        "label": "get-class",
                        "type": "shell",
                        "command": "sfdx",
                        "args": [
                                "force:source:retrieve",
                                "-m",
                                "\"${input:varObjects}\""
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
                        "type": "promptString",
                        "id": "varObjects",
                        "description": "Objects to retieve",
                        "default": "ApexClass:Constant"
                }
        ]
}

```
