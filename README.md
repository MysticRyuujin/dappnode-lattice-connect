# Lattice-Connect DAppNode Package

[![DAppNodeStore Available](https://img.shields.io/badge/DAppNodeStore-Available-brightgreen.svg)](http://my.dappnode/#/installer/lattice-connect.public.dappnode.eth)

[![Grid Plus github](https://img.shields.io/badge/GithubRepo-blue.svg)](https://github.com/gridplus/lattice-connect-v2) (Official)

Lattice-Connect is a self hosted relay service for your GridPlus Lattice1 - it allows you to avoid using GridPlus' centralized relay service and host your own. See their official GitHubRepo above for more information.

This package exposes a random DAppNode host port to the internal port of `8080/tcp` - if you want to connect to the lattice-connect externally consider setting this port manually in the network config options of the package.

## Setup Information

In the Setup Wizard you will be asked a URL for the Lattice1 - if your Lattice1 is connected to the DAppNode WiFi then you may be able to use the built in `GridPlus-xxxxxxxxxxx.local` name (I have not tried this). However, on my network the Lattice is connected externally so it's on the same LAN, but not "inside" the DAppNode VPN, therefor I just use a static IP address or DNS name on my network.

In v1 your Lattice1 would "call home" to the relay, in v2 the relay initiates the connection to the Lattice1 - This means that if you have a firewall between the DAppNode and your Lattice1 - you must allow `TCP Port 1883` through your firewall.

**WARNING: The default GridPlus Wallet [lattice.gridplus.io](https://lattice.gridplus.io/) is only accessible over HTTPS. You'll need to install the [Lattice-Manager](https://github.com/MysticRyuujin/dappnode-lattice-manager) package to manage your Lattice1 or expose port 8080 over HTTPS in the package's network settings when configuring MetaMask for the first time (this is not recommended). You should remove this mapping when not in use. MetaMask only needs it during initial setup.**

You can get around this requirement by using [Frame](https://frame.sh/)

As of v2 of this package there is no longer a requirement to SSH to the Lattice1 and configure it. This package works without any additional configuration and does not require you to "undo" the custom configuration of v1 either, if you have done so previously.

After installation check the container logs and you should see something like:

```json
{"level":30,"time":1667325463192,"pid":15,"hostname":"lattice-connect","msg":".: [!] MQTT client connected"}
```

## License

This project is licensed under the GNU General Public License v3.0 - see the [LICENSE](LICENSE) file for details
