# Welcome to Flow Launcher's plugins repository

This repository contains the information for community-made plugins used in [Flow](https://github.com/Flow-Launcher/Flow.Launcher) and how to make new submissions.

[![AutoUpdate](https://github.com/Flow-Launcher/Flow.Launcher.PluginsManifest/actions/workflows/updater.yaml/badge.svg?branch=plugin_api_v2)](https://github.com/Flow-Launcher/Flow.Launcher.PluginsManifest/actions/workflows/updater.yaml)

## Plugin list

Looking for a list of currently available plugins in Flow? Visit [here](https://flow-launcher.github.io/docs/#/plugins)

## How to submit your plugin

1. Create a file named `${name}-${uuid}.json` in the _plugins_ directory.
2. Copy these items from your plugin project's plugin.json file:
   - `ID`
   - `Name`
   - `Description`
   - `Author`
   - `Version`
   - `Language`
   - `Website`
3. Add `UrlDownload`, `UrlSourceCode`, and `IcoPath` to the file.
4. It should look like this:
   ```json
   {
     "ID": "Unique GUID from your plugin.json",  
     "Name": "Plugin name",
     "Description": "Short description",
     "Author": "Author",
     "Version": "Version from your plugin.json",
     "Language": "Programming language",
     "Website": "Plugin website",
     "UrlDownload": "URL to download",
     "UrlSourceCode": "URL to source code",
     "IcoPath": "Plugin icon image's CDN URL, e.g. https://cdn.jsdelivr.net/gh/Flow-Launcher/Flow.Launcher/Plugins/Flow.Launcher.Plugin.Explorer/Images/explorer.png"
   }
   ```
5. For `IcoPath`, use a CDN provider for global accessibility. [jsdelivr.com](https://www.jsdelivr.com/) for example as shown above, works well with GitHub repositories.
6. It is a requirement to set up a GitHub Actions workflow for automated build and release. Follow the guide [here](https://www.flowlauncher.com/docs/#/py-setup-project?id=_1-add-github-workflow) and use [this](https://github.com/Flow-Launcher/Flow.Launcher.Plugin.HelloWorldPython/blob/main/.github/workflows/Publish%20Release.yml) as an example.
7. Submit a pull request.
8. The plugin will be available in Flow after the pull request is approved by the Flow Launcher Team.

Flow downloads the plugins manifest file from various CDN providers, so when your new plugin appears is dependant on when these providers next sync the updated file, and this can be anywhere from one to three hours.

Every three hours the *CI* in this repository will check for new updates from plugins and automatically update them to the latest version. 

Plugin submissions that could potentially harm the computer or contains malicious code will not be accepted.

## Plugin Store

Users will be able to install your plugin via the store or type `pm install <your-plugin-name>`:
<p align="center"><img src="https://user-images.githubusercontent.com/6903107/207155616-d559f0d2-ee95-4072-a7bc-3ffcc2faec27.png" width="800"></p>

## Have a plugin enhancement request or issue?

This repository does not track enhancement requests or issues for plugins, it is up to the plugin developers to maintain their own plugin.

If you would like to contribute, submit a request or issue, please visit the plugin's repository via the 'UrlSourceCode' link or from `pm install`, `shift enter`/`right click` on the plugin to go to the context menu and select 'Suggest an enhancement or submit an issue'.
