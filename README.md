# zt-tools: zerotier python API wrapper, command replacements, and host updater

## concept
ZeroTeir provides a controller and central web site API for enumerated tasks.
Enumeration of network members is provided by the central site (web ui).

## central web site url configuration
For a self hosted Central UI (zero-ui  is one)

Place zt-tools.ini config file in HOME directory like so:

[sitetag]
url = http://site.com
token_url = http://site.com

[sitetag1]
url = http://site1.com
token_url = http://site1.com

https://github.com/dec0dOS/zero-ui
Zero-UI provides a few of the API functions of zerotier.com, but with a different token system and a slightly different URL.

## authorization tokens

### central auth
auth tokens are generated from the zerotier.com interface "account" menu
https://my.zerotier.com/account

### zero-ui flavor central auth
auth token is kept in identity.secret
see https://zerotier.atlassian.net/wiki/spaces/SD/pages/327693/How+to+Clear+Reset+your+ZeroTier+Address

### service (local controller) auth
auth token is for zero-ui are kept in the db.json file used to configure zero-ui.
see https://github.com/dec0dOS/zero-ui/discussions/11

# programs

## zthosts.py
A program which updates /etc/hosts with the zerotier network members from either zerotier.com or a local zero-ui installation.

## ztc-cmd.py
A subsitute for zerotier-cli command.

## zts-cmd.py
A command line tool for querying the zerotier.com or zero-ui web API.

# modules

## ztcentral.py
Module which provides a dataclass typed python wrapper for the ZeroTier Central.
this is suitable for working with zerotier.com
https://docs.zerotier.com/central/v1/

## ZtUiCentral in ztcentral.py
Module which provides a dataclass typed python wrapper for the Zero-UI web interface.

add your zero-ui URL to this class

## ztservice.py
Module which provides a dataclass typed python wrapper for the ZeroTier service (local node) API
https://docs.zerotier.com/service/v1/

## ztuil.py
Provides common utilies used by other modules.

## compatability
Used on Linux.  Support for finding controller key borrowed from https://github.com/freepn/ztcli-async

## todo
   * add the put/delete members

## libraries used
   * API wrappers use requests module
   * commands use typer module
