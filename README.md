# Timmo's Home Assistant apps

All my Home Assistant apps in one repository. Add it once to get every app below.

[![Add this repository to your Home Assistant.](https://my.home-assistant.io/badges/supervisor_add_addon_repository.svg)](https://my.home-assistant.io/redirect/supervisor_add_addon_repository/?repository_url=https%3A%2F%2Fgithub.com%2Ftimmo001%2Fhome-assistant-apps)

| App | Description |
| --- | --- |
| [Triage](https://github.com/timmo001/triage) | Collect crashes and errors from your machines, and decide which are worth fixing |
| [OpenCode](https://github.com/timmo001/app-opencode) | An AI coding agent for your Home Assistant setup, powered by OpenCode |

Each app also has its own repository you can add instead. Add this repository or an app's own repository, not both. Home Assistant treats them as different apps, so moving between them starts with empty settings and data, and a backup restores only to the repository it came from.

## How it works

Each app's release sends its repository and tag here once its image is pushed. [Update app](.github/workflows/update-app.yml) then copies that release's app folder in, with the release notes as its changelog. Only repositories listed in [`apps.yml`](apps.yml) are accepted. The source and issues live in each app's own repository.
