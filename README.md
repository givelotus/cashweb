# cashweb
CashWeb backend. Send peer-to-peer E2E encrypted messages with crypto as spam protection mechanism.

# Building From Source
## Linux (openSUSE)
1. Install the `protobuf-devel` package: `sudo zypper install protobuf-devel`
2. Clone this repo: `git clone https://github.com/givelotus/cashweb.git`
3. Clone the `bitcoinsuite` repo into the same directory (i.e. so that it is next to the `cashweb` directory): `git clone https://github.com/givelotus/bitcoinsuite`
4. Change into `cashweb` directory: `cd cashweb`
5. Add the following contents to `cashwebd-exe/config.toml` (create file if it doesn't exist):
```
host = "127.0.0.1:6543"
url = "http://127.0.0.1:6543"

[registry]
db_path = "./test_db"
net = "mainnet"
peers = []

[bitcoin_rpc]
url = "http://127.0.0.1:10604"
rpc_user = "lotus"
rpc_pass = "lotus"
```
6. Build and run cashweb: `cargo run cashwebd-exe/config.toml`

The build process will take some time to complete. If successful, you should see a message similar to the following:
```
2023-03-07T01:31:36.979388Z  INFO Listening on 127.0.0.1:6543
```
