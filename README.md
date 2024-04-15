# Forge Relayer
Forge Relayer acts as a transaction processing unit (TPU) proxy for Solana validators.

# Building
```shell
# pull submodules to get protobuffers required to connect to Block Engine and validator
$ git submodule update -i -r
# build from source
$ cargo b --release
```

# Running 
1. cargo buill -r --bin transaction-relayer
2.  Choose one server from this list:
```
Asia Tokyo:    http://tokyo.solanaforge.xyz
USA West:      http://la.solanaforge.xyz
USA East:      http://miami.solanaforge.xyz
EU Amsterdam:  http://ams.solanaforge.xyz
```

3. Run
```
./target/release/transaction-relayer --keypair-path /root/config/relayer.json \
--signing-key-pem-path /root/config/auth \
--verifying-key-pem-path /root/config/auth.pub \
--webserver-bind-addr 127.0.0.1:5050 \
--block-engine-url http://ОДИН_ИЗ_СЕРВЕРОВ_ИЗ_СПИСКА_2:11227 \
--block-engine-auth-service-url http://ОДИН_ИЗ_СЕРВЕРОВ_ИЗ_СПИСКА_2:11227
```

4. Pay attention to the keys --signing-key-pem-path, --verifying-key-pem-path, --keypair-path you must generate them yourself!!!



