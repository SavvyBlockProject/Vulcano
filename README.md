

VULCANO Testnet Fork

Modifications can be made to this fork as a temporary testnet for Vulcano. It uses the production blockchain up to the point the testnet started operating (block 498075).

The simplest way to bring coins onto this testnet is to create a test build from this repo, with whatever additional changes are desired for testing, sync the blockchain (the production snapshot or a testnet snapshot can be used), stop the node, and replace the wallet.dat with a production Vulcano wallet.dat. 

Please use addnode lines to connect to the three primary testnet nodes:

addnode=149.28.114.108:12886
addnode=144.202.51.100:12886
addnode=144.202.61.237:12886

Delete any peers.dat files before starting your testnet node to avoid having it try to connect to production Vulcano nodes.

Particularly for Linux nodes, I recommend limiting the server to only communicating over SSH and the ports for this fork so that it cannot communicate over the production Vulcano ports, e.g.:

ufw allow ssh/tcp
ufw limit ssh/tcp
ufw allow 12886/tcp
ufw allow 12885/tcp
ufw logging on
ufw enable

USE THIS AT YOUR OWN RISK. Only minimal changes have been made from the production Vulcano, primarily just a port change to 12886. Since the addresses and the past blockchain history are shared between this and production Vulcano, it would be very easy to think you are on production or testnet while being connected to the other, and mistakenly make transactions on the wrong chain.

Vulcano devs will be added upon request to this repo so they can pull in changes. Please contact me if you need the primary three testnet nodes updated with the latest changes and I will do a rebuild and restart the nodes.

