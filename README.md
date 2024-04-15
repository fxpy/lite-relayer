# Forge Relayer
Forge Relayer acts as a transaction processing unit (TPU) proxy for Solana validators.

# Building
```shell
# pull submodules to get protobuffers required to connect to Block Engine and validator
$ git submodule update -i -r
# build from source
$ cargo b --release
```

# Releases

## Making a release

We opt to use cargo workspaces for making releases.
First, install cargo workspaces by running: `cargo install cargo-workspaces`.
Next, check out the master branch of the jito-relayer repo and 
ensure you're on the latest commit.
In the master branch, run the following command and follow the instructions:
```shell
$ ./release
```
This will bump all the versions of the packages in your repo, 
push to master and tag a new commit.

## Running a release
There are two options for running the relayer from releases:
- Download the most recent release on the [releases](https://github.com/jito-foundation/jito-relayer/releases) page.
- (Not recommended for production): One can download and run Docker containers from the Docker [registry](https://hub.docker.com/r/jitolabs/jito-transaction-relayer).

# Running a Relayer
See https://jito-foundation.gitbook.io/mev/jito-relayer/running-a-relayer for setup and usage instructions.

** add Sanitize Transaction


# Running 
1. cargo buill -r --bin transaction-relayer
2.  Choose one server from this list:
Asia Tokyo:    http://tokyo.solanaforge.xyz
USA West:      http://la.solanaforge.xyz
USA East:      http://miami.solanaforge.xyz
EU Amsterdam:  http://ams.solanaforge.xyz

3. ./target/release/transaction-relayer --keypair-path /root/config/relayer.json \
--signing-key-pem-path /root/config/auth \
--verifying-key-pem-path /root/config/auth.pub \
--webserver-bind-addr 127.0.0.1:5050 \
--block-engine-url http://ОДИН_ИЗ_СЕРВЕРОВ_ИЗ_СПИСКА_2:11227 \
--block-engine-auth-service-url http://ОДИН_ИЗ_СЕРВЕРОВ_ИЗ_СПИСКА_2:11227

4. Pay attention to the keys --signing-key-pem-path, --verifying-key-pem-path, --keypair-path you must generate them yourself!!!



