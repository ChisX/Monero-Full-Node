# Usage #
Do not Place this folder within a directory with a multi-word name
and remember to run the script as administrator or they won't work

Choose the proper script to run based on your operating system, and
run as administrator. You can - and are encouraged to - at any time
inspect the contents to ensure that the operations are not malicious
in nature.

:warning: Linux not fully supported yet!

# Scripts #
## xmr_activate ##
Launches the monero daemon with standard options, which download the full monero
blockchain onto your computer's hard-drive. This step is essential, but as the entire
blockchain takes up an enormous and increasing amount of storage (at time of writing
over 100 GB).

## xmr_prune ##
Launches the monero daemon with certain custom-selected options, which will query only
pruned-nodes when synchronizing with the monero blockchain, and prune it even further if
possible. These parameters lead to downloading a minimal-size blockchain on your computer
(normally over 100GB), now at 37.5 GB(September 2021).

## xmr_wallet ##
After the blockchain has been downloaded onto your computer, you only need a few more
preparations for the computer to be converted into a functional node. This script will
bind to a running instance of the monero daemon program (activated by either of the 2
scripts noted above), and create a standard wallet, providing you with a view key and an
address, in addition to a mnemonic phrase you can use to sign transactions and import
your account to another device or online wallet service.

You may also be prompted with a choice to enable background mining under this new account.
You can do so, or defer and use a different account via the xmr_connect script. For your
convenience, the batch scripts have been configured to store your wallet files within the
'wallets' folder of this directory.

## xmr_connect ##
In case you have selected not to connect your newly created account to the daemon and start
to mine monero when your computer enters an idle state, or if you have temporarily stopped.
The script will run to connect the first wallet file, but you can also choose a different
one by opening a terminal as administrator and running the following command:

> xmr_connect <WALLET NAME>

You can even have multiple wallets connected at a time. This command interfaces your wallet
of choice to the monero daemon program, which allows you to execute various commands, should
you have a need for them.

Note that this background mining will only activate when your computer has resources to spare,
like if you have stepped away from it for a time or you have resource-sparing applications
running. To dedicate a larget portion of your processing power towards, refer to running the
xmr_mine script, as described below.

## xmr_mine ##
This script will launch the monero protocol's mining functions using your own computer's
processor and storage capacity, thus directly contributing said resources to the monero
peer network of mining nodes. Note that you are required to first create a wallet through
the use of the xmr_wallet script. In doing so, note the address you generated, for you
must specify one to receive mining rewards.

To begin mining monero, simply run the xmr_mine script. This will open a new terminal window
which will display live messages and stats on your mining contributions, allowing you to also
inspect the hashrate for your own CPU (pressing 'h') and the results of your overall
processing (pressing 's'). You can also pause/resume your connection to the mining pool, which
by default is the "xmrpool.eu" (pressing 'p'/'r', respectively).

When you open a monero wallet with xmr_connect, you will see a notification that states
which wallet you have opened, quoting a string of letters and numbers. That is your monero
address. Note that you can also paste that address on the pool's website if you want to
check and compare your contributions to other miners within the pool(https://web.xmrpool.eu/).
You can stop mining at any time by pressing Ctrl+C or simply closing the window terminal.
