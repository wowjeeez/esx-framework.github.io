# Modules 
*_There is no more `esx_` resource on this version. This had been deprecated in favor of modules_*

## What's a module?
A module is an isolated block that works independently from any resource or any other module (except the core modules provided by ESX)

## How does modules work?
You can compose modules using any of these parts:

- client - handle all client logic

- server - handle all server logic 

- shared - handles logic for both sides

Each part are again divided into three parts in order to make things more clear:

- events.lua : Responsible for handling events (the code to execute when an event is received)

- main.lua : Responsible for importing the needed core modules and managing the module state. (control flow)

- module.lua : Utility functions, supporting code.

## How to install a module?
Grab the module you'd like to install. Paste it in the `es_extended/modules/__user__/` directory and add the module name to the list of the `es_extended/modules/__user__/modules.json` file. `modules.json` should look something like this :

```json
[
  "module-name-here"
]
```

**__WARNING:__** __The file may not exist if it's your first installation, just create a file named `modules.json` in the `es_extended/modules/__user__/` directory.__

## Why is this pattern a better approach?
For a better and cleaner codebase it's obviously better to have a pattern already set. You'll end up with organized files and modules.

Another thing is the performance, so far, it's more optimized to work this way other then calling the `getSharedObject` everywhere.