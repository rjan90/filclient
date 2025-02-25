# filc

filc is a simple command line interface for `filclient`. It's great for basic storage/retrieval deals, checking wallet balance, and testing.

## Setup

### Install
Using filc requires some system dependencies

Ubuntu/Debian:
```
sudo apt install ocl-icd-opencl-dev build-essential jq pkg-config libhwloc-dev wget -y && sudo apt upgrade -y
```

**Go**

To build filc, you need a working installation of Go 1.16.4 or higher:

```
wget -c https://golang.org/dl/go1.16.4.linux-amd64.tar.gz -O - | sudo tar -xz -C /usr/local
```

>You’ll need to add /usr/local/go/bin to your path. For most Linux distributions you can run something like:
>echo 'export PATH=$PATH:/usr/local/go/bin' >> ~/.bashrc && source ~/.bashrc
>
>See the official Golang installation instructions if you get stuck.

**Build and install**

Once all the dependencies are installed, you can build filc

1. Clone the repository
```
git clone https://github.com/application-research/filclient.git
cd filclient
```

2. Build
```
make all
cd filc
go build
```

### Lotus Connection
filc currently needs a connection to a synced Lotus node to function. By default, filc will attempt to connect to a node hosted at `localhost`. If you don't have a self-hosted Lotus node, an alternative address can be specified by setting the environment variable `FULLNODE_API_INFO` (you'll probably want `FULLNODE_API_INFO=wss://api.chain.love`).

### Wallet Setup
Currently, filc will automatically generate a wallet address for you on first run. If you already have a wallet you'd like to use, you can grab the corresponding file starting with `O5` from your existing wallet folder (e.g. `~/.lotus/keystore/`) and place it into `~/.filc/wallet/`.