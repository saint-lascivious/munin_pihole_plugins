# munin-pihole-plugins

[Munin](https://munin-monitoring.org) [plugins](https://gallery.munin-monitoring.org) and management script for monitoring various [Pi-hole®](https://github.com/pi-hole/pi-hole) statistics. Transforms a server into a powerful monitoring platform, as simple as [one](https://github.com/saint-lascivious/munin-pihole-plugins#step-one-download), [two](https://github.com/saint-lascivious/munin-pihole-plugins#step-two-install), [three](https://github.com/saint-lascivious/munin-pihole-plugins#step-three-wait), …[four](https://github.com/saint-lascivious/munin-pihole-plugins#step-four-monitor).

## Usage

### Step One: Download
* Download munin-pihole-plugins `master` branch
```
curl -sSL munin-pihole-plugins.sainternet.xyz -o munin-pihole-plugins && chmod +x munin-pihole-plugins
```

### Step Two: Install
* Install munin-pihole-plugins
```
./munin-pihole-plugins --install
```
Dependencies are checked and met automatically using `dpkg-query` and `apt` respectively. A copy of the `munin-pihole-plugins` script will be installed on the host in `/usr/local/bin` by default. The munin-pihole-plugins script directory can be [configured](https://github.com/saint-lascivious/munin-pihole-plugins#script-configuration), or the `munin-pihole-plugins` script installation may be disabled entirely.

### Step Three: …Wait
* Wait, around five minutes

While graphs are generated by the Munin master on-demand using cgi graph strategy, Munin nodes run plugins periodically, by default at 5 minute intervals past the hour. Check out the [command list](https://github.com/saint-lascivious/munin-pihole-plugins#command-list) while you wait.

### Step Four: Monitor
* Navigate to http://MUNIN_SERVER_FQDN_HOSTNAME_OR_IP/munin in a browser to view the Munin monitoring interface

If everything went well, you should find [munin-pihole-plugins graphs](https://github.com/saint-lascivious/munin-pihole-plugins#example-graph-gallery) available to view in the 'dns' category. Otherwise, see the [help section](https://github.com/saint-lascivious/munin-pihole-plugins#help-my-graphs-arent-showing-up).

## Command List
* List of `munin-pihole-plugins` commands

Usage: `munin-pihole-plugins {OPTION [PARAMETER]}`

| Option | GNU long option | Meaning |
| --- | --- | --- |
| `-h`, `help` | `--help` | Display help dialogue |
| `-i`, `install` | `--install` | Install munin-pihole-plugins |
| `-v`, `version` | `--version` | Display current and latest versions |
| `-U`, `uninstall` | `--uninstall` | Uninstall munin-pihole-plugins |
| `-V`, `variables` | `--variables` | Display or set environment variables |

Type `--help {OPTION}` for more detailed explanations of each command

Example: `munin-pihole-plugins --help install`

* List of optional parameters for the `-i`, `install`, `--install` and `-U`, `uninstall`, `--uninstall` commands

Basic installation or uninstallation tasks can be governed by passing an optional parameter to the `--install` or `--uninstall` commands.

| Optional Install Parameter | GNU long option | Function |
| --- | --- | --- |
| `-p`, `plugins` | `--plugins` | Install and configure `munin-node`, and `munin-pihole-plugins` plugins |
| `-P`, `plugins-only` | `--plugins-only` | As above, skipping dependency satisfaction |
| `-s`, `script` | `--script` | Install the munin-pihole-plugins script |
| `-S`, `script-only` | `--script-only` | As above, skipping dependency satisfaction |
| `-w`, `webserver` | `--webserver` | Install and configure `munin`, `lighttpd` and `lighttpd-external-munin-proxy` |
| `-W`, `webserver-only` | `--webserver-only` | As above, skipping dependency satisfaction |

Example: `munin-pihole-plugins --install --plugins`

| Optional Uninstall Parameter | GNU long option | Function |
| --- | --- | --- |
| `-p`, `plugins` | `--plugins` | Uninstall `munin-node`, `munin-pihole-plugins` plugins, and related configuration |
| `-P`, `plugins-only` | `--plugins-only` | As above, skipping dependency removal |
| `-s`, `script` | `--script` | Uninstall the munin-pihole-plugins script and related configuration |
| `-S`, `script-only` | `--script-only` | As above, skipping dependency removal |
| `-w`, `webserver` | `--webserver` | Uninstall `munin`, `lighttpd`, `lighttpd-external-munin-proxy`, and related configuration |
| `-W`, `webserver-only` | `--webserver-only` | As above, skipping dependency removal |

Example: `munin-pihole-plugins --uninstall --script-only`

## Example Graph Gallery
* pihole_blocked
![alt text][pihole_blocked-day.png]

[pihole_blocked-day.png]:https://raw.githubusercontent.com/saint-lascivious/munin-pihole-plugins/master/gallery/pihole_blocked-day.png "This plugin shows the number of domains blocked by Pi-hole®."

This plugin shows the number of domains blocked by Pi-hole®.

* pihole_cache
![alt text][pihole_cache-day.png]

[pihole_cache-day.png]:https://raw.githubusercontent.com/saint-lascivious/munin-pihole-plugins/master/gallery/pihole_cache-day.png "This plugin shows Pi-hole®'s cache."

This plugin shows Pi-hole®'s cache.

* pihole_cache_by_type
![alt text][pihole_cache_by_type-day.png]

[pihole_cache_by_type-day.png]:https://raw.githubusercontent.com/saint-lascivious/munin-pihole-plugins/master/gallery/pihole_cache_by_type-day.png "This plugin shows Pi-hole®'s cache by type."

This plugin shows Pi-hole®'s cache by type.

* pihole_clients
![alt text][pihole_clients-day.png]

[pihole_clients-day.png]:https://raw.githubusercontent.com/saint-lascivious/munin-pihole-plugins/master/gallery/pihole_clients-day.png "This plugin shows clients seen by Pi-hole®."

This plugin shows clients seen by Pi-hole®.

* pihole_percent
![alt text][pihole_percent-day.png]

[pihole_percent-day.png]:https://raw.githubusercontent.com/saint-lascivious/munin-pihole-plugins/master/gallery/pihole_percent-day.png "This plugin shows Pi-hole®'s blocked query percentage."

This plugin shows Pi-hole®'s blocked query percentage.

* pihole_queries
![alt text][pihole_queries-day.png]

[pihole_queries-day.png]:https://raw.githubusercontent.com/saint-lascivious/munin-pihole-plugins/master/gallery/pihole_queries-day.png "This plugin shows queries seen by Pi-hole®."

This plugin shows queries seen by Pi-hole®.

* pihole_replies_by_type
![alt text][pihole_replies_by_type-day.png]

[pihole_replies_by_type-day.png]:https://raw.githubusercontent.com/saint-lascivious/munin-pihole-plugins/master/gallery/pihole_replies_by_type-day.png "This plugin shows Pi-hole® replies by type."

This plugin shows Pi-hole® replies by type.

* pihole_status
![alt text][pihole_status-day.png]

[pihole_status-day.png]:https://raw.githubusercontent.com/saint-lascivious/munin-pihole-plugins/master/gallery/pihole_status-day.png "This plugin shows Pi-hole®'s blocking status."

This plugin shows Pi-hole®'s blocking status.

* pihole_unique_domains
![alt text][pihole_unique_domains-day.png]

[pihole_unique_domains-day.png]:https://raw.githubusercontent.com/saint-lascivious/munin-pihole-plugins/master/gallery/pihole_unique_domains-day.png "This plugin shows unique domains seen by Pi-hole®."

This plugin shows unique domains seen by Pi-hole®.

## Configuration

### Plugin Configuration
* Default `/etc/munin/plugin-conf.d/pihole.conf` plugin configuration
```
[pihole_*]
    user root
    env.host 127.0.0.1
    env.port 80
    env.api /admin/api.php
    env.cachesuffix ?getCacheInfo&auth=
    #env.webpassword PIHOLE_SETUPVARS_WEBPASSWORD_HERE
```
Provided munin-node and Pi-hole® exist on the same host, the default configuration should Just Work™. If you have a non-standard configuration or Pi-hole® is running on a seperate host, you will need to edit the plugin configuration. The plugin attempts to obtain this value itself, if it can not do so the `env.webpassword` value can be obtained from the Pihole host's `/etc/pihole/setupVars.conf` file.

### Script Configuration
* Usage

Initial installation, or without the `munin-pihole-plugins` script being locally installed: `export VARIABLE="VALUE"`

Example: `export VERBOSITY_LEVEL="4"`

Subsequent runs, with the `munin-pihole-plugins` script locally installed: `munin-pihole-plugins --variables VARIABLE VALUE`

Example: `munin-pihole-plugins --variables VERBOSITY_LEVEL 4`

Reset example: `munin-pihole-plugins --variables VERBOSITY_LEVEL RESET`

The configuration file, of which the default is `/etc/munin-pihole-plugins/munin-pihole-plugins.conf`, may be manually created or generated ahead of time if desired, useful for packaging or other automated deployment. This configuration file MUST be a plain text file and MUST consist of the format `VARIABLE=VALUE` (or `VARIABLE="VALUE"` for arrays, like `PLUGIN_LIST`), one variable per line, with no leading whitespace or indentation. Comments to assist usability may exist but MUST be preceeded with a hash (`#`) character.

* Default `munin-pihole-plugins` script environment variables

| Variable | Default Value |
| --- | --- |
| `BRANCH` | `master` |
| `DNS_PORT` | `53` |
| `DNS_SERVER` | `208.67.222.222` |
| `EXTERNAL_CONFIG_DIR` | `/etc/munin-pihole-plugins` |
| `EXTERNAL_CONFIG_FILE` | `munin-pihole-plugins.conf` |
| `INSTALL_PLUGINS` | `true` |
| `INSTALL_SCRIPT` | `true` |
| `INSTALL_WEBSERVER` | `true` |
| `LIGHTTPD_WEBROOT` | `/var/www/html` |
| `MUNIN_DIR` | `/etc/munin` |
| `MUNIN_CONFIG_DIR` | `/etc/munin/munin-conf.d` |
| `MUNIN_PLUGIN_DIR` | `/usr/share/munin/plugins` |
| `MUNIN_VERSION` | `stable` |
| `NODE_PLUGIN_DIR` | `/etc/munin/plugins` |
| `PLUGIN_CONFIG_DIR` | `/etc/munin/plugin-conf.d` |
| `PLUGIN_LIST` | `blocked cache cache_by_type clients percent queries replies_by_type status unique_domains` |
| `PROXY_CONFIG_DIR` | `/etc/lighttpd` |
| `SCRIPT_DIR` | `/usr/local/bin` |
| `SHOW_COLOR` | `true` |
| `SKIP_DEPENDENCY_CHECK` | `false` |
| `UPDATE_SELF` | `true` |
| `VERBOSITY_LEVEL` | `3` |

* `BRANCH`

The branch used when checking the `munin-pihole-plugins` script version or installing `munin-pihole-plugins`. Valid options are `development` and `master`, of which the default is `master`. Invalid options will be rejected.

* `DNS_PORT`

The port which the `munin-pihole-plugins` script will contact in order to contact `DNS_SERVER`.

* `DNS_SERVER`

The DNS server which the `munin-pihole-plugins` script will contact in order to retrieve its version information (from a `TXT` record at `munin-pihole-plugins.sainternet.xyz`). This should ideally be an IP rather than a hostname, and it should ideally be external, but I'm not your mother.

When the `munin-pihole-plugins` script is installed locally, the `-V`, `variables`, `--variables` command can set the value of `DNS_SERVER` using user input, or one of the following optional presets:

| `DNS_SERVER` Preset | Value |
| --- | --- |
| `CLOUDFLARE` | `1.1.1.1` |
| `COMODO` | `8.26.56.26` |
| `GOOGLE` | `8.8.8.8` |
| `LOCALHOST` | `127.0.0.1` |
| `OPENDNS` | `208.67.222.222` (default) |
| `QUAD9` | `9.9.9.9` |

Example: `munin-pihole-plugins --variables DNS_SERVER LOCALHOST`

* `EXTERNAL_CONFIG_DIR`

The directory in which an external configuration file should be located, to be created if required.

Example: `export EXTERNAL_CONFIG_DIR="/etc/munin-pihole-plugins"`

* `EXTERNAL_CONFIG_FILE`

The name of external configuration file `munin-pihole-plugins` should use, to be created if required.

Example: `export EXTERNAL_CONFIG_FILE="munin-pihole-plugins.conf"`

* `INSTALL_PLUGINS`

Disables installation of `munin-node` and `munin-pihole-plugins` plugins if set to any value other than `true`.

* `INSTALL_SCRIPT`

Disables installation of the `munin-pihole-plugins` script if set to any value other than `true`.

* `INSTALL_WEBSERVER`

Disables installation of the `munin` webserver and `lighttpd` proxy if set to any value other than `true`. Useful for additional Munin nodes in a multi-node, single-server environment.

* `LIGHTTPD_WEBROOT`

The directory in which, if installed, the Pi-hole® AdminLTE web interface should be found. The presence or absence of a `pihole` directory here is used to determine whether or not `munin-pihole-plugins` should offer to remove `lighttpd` during `munin-pihole-plugins` uninstallation. The `admin` directory is not used for this purpose due to the ambiguity of its name.

* `MUNIN_DIR`

The directory in which the `munin` munin.conf file should be located.

* `MUNIN_CONFIG_DIR`

The directory in which additional `munin` configuration files may be placed, the `munin-pihole-plugins` script will attempt to use this in favour of editing munin.conf directly.

* `MUNIN_PLUGIN_DIR`

The directory in which `munin` plugins should be located.

* `MUNIN_VERSION`

The Munin version to target when configuring the `lighttpd` proxy. Available options are `latest` and `stable`, with `stable` being the default value. The `latest` version should be selected for Munin versions 2.99 or higher.

| Tag | Munin Version Target |
| --- | --- |
| `latest` | munin 2.99+ |
| `stable` | munin 2.* |

* `NODE_PLUGIN_DIR`

The directory in which `munin-node` plugin symbolic links should be created.

* `PLUGIN_CONFIG_DIR`

The directory in which individual `munin-node` plugin configurations should be located.

* `PLUGIN_LIST`

A space separated list of `munin-pihole-plugins` plugin IDs used to determine which plugins will be installed.

| Plugin ID | Description |
| --- | --- |
| `blocked` | This plugin shows the number of domains blocked by Pi-hole®. |
| `cache` | This plugin shows Pi-hole®'s cache. |
| `cache_by_type` | This plugin shows Pi-hole®'s cache by type. |
| `clients` | This plugin shows clients seen by Pi-hole®. |
| `percent` | This plugin shows Pi-hole®'s blocked query percentage. |
| `queries` | This plugin shows queries seen by Pi-hole®. |
| `replies_by_type` | This plugin shows Pi-hole®'s replies by type. |
| `status` | This plugin shows Pi-hole®'s blocking status. |
| `unique_domains` | This plugin shows unique domains seen by Pi-hole®. |

Example: `export PLUGIN_LIST="blocked percent unique_domains"`


* `PROXY_CONFIG_DIR`

The directory in which `lighttpd`'s external.conf should be located.

* `SCRIPT_DIR`

The directory in which the `munin-pihole-plugins` script should be located when installed, the `munin-pihole-plugins` script will warn if this directory is not located in the host's $PATH variable and suggest how to correct this.

* `SHOW_COLOR`

Disables color output if set to any value other than `true`.

* `SKIP_DEPENDENCY_CHECK`

Disables `apt` and `dpkg-query` based dependency management if set to any value other than `false`.

* `UPDATE_SELF`

Disables self update of the `munin-pihole-plugins` script if set to any value other than `true`.

* `VERBOSITY_LEVEL`

Sets the munin-pihole-plugins script verbosity level on a scale from `0` to `4`, with `0` being total silence and `4` being the highest level of verbosity.

| Verbosity Level | Output |
| --- | --- |
| `0` | Silent |
| `1` | + Errors |
| `2` | ++ Questions and Warnings |
| `3` | +++ Information |
| `4` | ++++ Additional Information |

## Help! My graphs aren't showing up!
* Be patient

Graphs should be generated at five minute intervals. If you still do not see graphs after this time, try restarting the machine and waiting a further five minutes. If you still can not get any graphs to display, [contact me](https://github.com/saint-lascivious/munin-pihole-plugins#contact) for further support.

## Contact
* Discord
[SaintLascivious](https://discord.gg/NC7taVyn)

* Email
saint@sainternet.xyz

* IRC
[##saint-lascivious](https://webchat.freenode.net/##saint-lascivious)

* Reddit
[saint-lascivious](https://www.reddit.com/user/saint-lascivious)

![alt text][logo]

[logo]:https://vignette.wikia.nocookie.net/pokemon/images/7/76/265Wurmple.png "Using the spikes on its rear end, Wurmple peels the bark off trees and feeds on the sap that oozes out. This Pokémon's feet are tipped with suction pads that allow it to cling to glass without slipping."

## Related projects
* [lighttpd-external-munin-proxy](https://github.com/saint-lascivious/lighttpd-external-munin-proxy)

lighttpd external.conf for Munin webserver proxy

* [munin-unbound-plugins](https://github.com/saint-lascivious/munin-unbound-plugins)

Munin monitoring plugins for Unbound

* [Munin](https://github.com/munin-monitoring/munin)

Main repository for munin master / node / plugins

* [Pi-hole®](https://github.com/pi-hole/pi-hole)

A black hole for Internet advertisements

* [Unbound](https://github.com/NLnetLabs/unbound)

Unbound is a validating, recursive, caching DNS resolver.
