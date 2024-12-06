# alpha
A set of configuration scripts, dotfiles and notes that I use to seed and
maintain all my hosts.

## Notes for macOS
- Optionally follow the preliminary macOS [setup guide](macos/README.md).
- Install Apple CLI Tools `xcode-select --install`.
- Add the following location to Spotlight Privacy list `/Library/Developer`.
- Clone this repo and run: `./bootstrap.sh`.
- Start neovim and let the LSP servers install.
- Add Kitty to the Developer Tools category in Privacy & Security, within System
  Settings.
- Open applications and configure them as needed.
  - Set Brave's `Tab Scrolling` flag to `Enabled - tabs shrink to pinned tab width`.
- Disable auto-updates: `bash shared_macos/scripts/disable-updates.sh`.
- Press `Cmd+Shift+5`, select `Options` and then set screenshots' folder.
- Clone the [docker-containers](https://github.com/parteincerta/docker-containers)
  repo and setup the Docker containers.
- Revisit Notifications, Login Items, Spotlight and re-access accordingly.
- Configure VPNs and show them in the Menu Bar.
- Shutdown Ethernet/Wi-Fi and run Onyx. Revoke its permissions afterwards.
- Reboot.

### Maintenance
- Check for macOS updates:
  * To list available updates: `softwareupdate --list`.
  * To install an update: `softwareupdate --install <label>`.
  * To install an update and restart: `sudo softwareupdate --install --restart <label>`.
- Homebrew maintenance commands:
  * Update Homebrew and the list of formulae: `brew update`.
  * List outdated formulae: `brew outdated --greedy`.
  * Upgrade all installed formulae and casks: `brew upgrade --greedy`.
  * Formulae w/ special upgrade instructions:
    * `brew install --ignore-dependencies gradle jdtls maven zls`.
    * `brew unlink python@3.13 openssl@3`.
  * Purge cache: `brew cleanup [--dry-run]`.
  * List dependencies of a formula: `brew deps --tree <formula>`.
  * List installed dependencies of a formula: `brew uses --installed <formula>`.
  * List installed formulae which are not dependencies of others: `brew leaves`.
  * List artifacts of a formula: `brew ls <formula>`.
- Hosts file maintenance steps:
  * Check for [hosts files][macos-maintenance-01] updates.
  * Update the version reference in
    [install-hosts.sh](shared/scripts/install-hosts.sh).
  * Update the hosts file: `bash shared/scripts/install-hosts.sh`.
- Docker maintenance steps:
	- Check for updated extensions in Docker Desktop.
	- Check for new versions of base images / components.
	- Run `docker compose up` for updated images.
	- Run `docker image prune --all` to remove unused images.
	- Run `docker system prune` to remove unused artifacts.
- mise maintenance commands:
  * List installed plugins: `mise plugins list`.
  * List all available plugins: `mise plugins list-all`.
  * Install a new plugin: `mise plugins install <plugin>`.
  * Update installed plugins: `mise plugins upgrade`.
  * Remove plugin: `mise remove <plugin>`.
  * List outdated installed tools: `mise outdated`.
  * Check latest available tool version: `mise latest <plugin>[@version]`.
  * Install latest available tool version: `mise install <plugin>[@version]`.
  * Remove tool version: `mise remove <plugin>@<version>`.
  * List available versions of a tool tools: `mise ls-remote <plugin>`.
  * Update all outdated tools: `mise upgrade`.
  * Update a given tool, if an update is available: `mise upgrade <plugin>@<version>`.
- mise for AMD64 maintenance commands:
  * Check for [mise][macos-maintenance-05] updates for the AMD64 version.
  * Update the version reference in
    [install-mise-amd64.sh](shared/scripts/install-mise-amd64.sh).
  * Update the AMD64 version: `bash shared/scripts/install-mise-amd64.sh`.
  * Use the same instructions used for regular mise to manage the AMD64 tools.
- MongoDB utilities maintenance steps:
  * Check for [MongoDB Shell][macos-maintenance-02] and
    [MongoDB Tools][macos-maintenance-03] updates.
  * Update the version references in
    [install-mongo-utils.sh](shared/scripts/install-mongo-utils.sh).
  * Update Shell: `bash shared/scripts/install-mongo-utils.sh shell`.
  * Update Tools: `bash shared/scripts/install-mongo-utils.sh tools`.
- Neovim maintenance commands:
  * Update Lazy's plugins: `:Lazy sync`.
  * Update Mason's registry: `:MasonUpdate`.
  * Update Mason's LSPs: `:Mason` -> Press the `U` key.
  * Update TreeSitter's parsers: `TSUpdateSync`.
- Python maintenance commands:
  * `pip3 list --user --outdated`.
  * `pip3 install --user --upgrade <package>`.
- vcpkg maintenance commands:
  * Check for [vcpkg][macos-maintenance-06] updates.
  * Update the version tag in [install-vcpkg.sh](shared/scripts/install-vcpkg.sh).
  * Update vcpkg: `bash shared/scripts/install-vcpkg.sh`.
- Other maintenance commands:
  * Install the dotfiles: `./configure.sh`.
  * Export configurations: `bash shared_macos/scripts/export-defaults.sh`.
  * Disable auto-updates: `bash shared_macos/scripts/disable-updates.sh`.
  * Update Brave's Content Filters lists.
- Check for VSCode plugins updates.
- Check for App Store updates.
- Check for [OpenCore Legacy Patcher][macos-maintenance-04] updates.

[macos-maintenance-01]: https://github.com/StevenBlack/hosts/releases
[macos-maintenance-02]: https://github.com/mongodb-js/mongosh/releases
[macos-maintenance-03]: https://github.com/mongodb/mongo-tools/tags
[macos-maintenance-04]: https://github.com/dortania/OpenCore-Legacy-Patcher/releases
[macos-maintenance-05]: https://github.com/jdx/mise/releases
[macos-maintenance-06]: https://github.com/microsoft/vcpkg/releases
