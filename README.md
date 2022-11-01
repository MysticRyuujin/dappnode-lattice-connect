# Lattice-Connect DAppNode Package

[![DAppNodeStore Unavailable](https://img.shields.io/badge/DAppNodeStore-Unavailable-red.svg)](http://my.dappnode/#/installer/lattice-connect.public.dappnode.eth)

(Because I get EVM errors trying to publish it...just use the IPFS hash in the release)

[![Grid Plus github](https://img.shields.io/badge/GithubRepo-blue.svg)](https://github.com/gridplus/lattice-connect-v2) (Official)

Lattice-Connect is a self hosted relay service for your GridPlus Lattice1 - it allows you to avoid using GridPlus' centralized relay service and host your own. See their official GitHubRepo above for more information.

This package exposes a random DAppNode host port to the internal port of `:8080` - if you want to connect to the lattice-connect externally consider setting this port manually in the network config options of the package.

**WARNING: The default GridPlus Wallet (https://lattice.gridplus.io/) is only accessible over HTTPS. You'll need to install the [Lattice-Manager](https://github.com/MysticRyuujin/dappnode-lattice-manager) package to manage your Lattice1 or expose port 8080 over HTTPS in the package's network settings whenever you want to upload an ABI pack OR when configuring MetaMask for the first time (this is not recommended). You should remove this mapping when not in use. MetaMask only needs it during initial setup.**

You can get around this requirement by using [Frame](https://frame.sh/)

As of v2 of this package there is no longer a requirement to SSH to the Lattice1 and configure it. This package works without any additional configuration and does not require you to "undo" the custom configuration of v1 either, if you have done so previously.

After installation check the container logs and you should see something like:

```json
{"level":30,"time":1667325463192,"pid":15,"hostname":"lattice-connect","msg":".: [!] MQTT client connected"}
```

## License

This project is licensed under the GNU General Public License v3.0 - see the [LICENSE](LICENSE) file for details
