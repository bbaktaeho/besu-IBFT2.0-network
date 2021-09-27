# Test Env

### Prerequisites

- java 11
- besu
- docker, docker-compose

### Settings

do not use Docker

- local

  ```bash
  pwd

  besu-private-net-ibft
  ```

  ```bash
  ./generate.sh
  ```

  Start the first node1 as the bootnode.

  ```bash
  cd node1
  besu --data-path=data --genesis-file=../genesis.json --rpc-http-enabled --rpc-http-api=ETH,NET,IBFT --host-allowlist="\*" --rpc-http-cors-origins="all"
  ```

  the default of p2p-port is 30303. <br><br>

  Copy the enode URL and create a new terminal for each node.

  ```bash
  cd node2
  besu --data-path=data --genesis-file=../genesis.json --bootnodes=<enode URL> --p2p-port=30304 --rpc-http-enabled --rpc-http-api=ETH,NET,IBFT --host-allowlist="*" --rpc-http-cors-origins="all" --rpc-http-port=8546
  ```

  ```bash
  cd node3
  besu --data-path=data --genesis-file=../genesis.json --bootnodes=<enode URL> --p2p-port=30305 --rpc-http-enabled --rpc-http-api=ETH,NET,IBFT --host-allowlist="*" --rpc-http-cors-origins="all" --rpc-http-port=8547
  ```

  ```bash
  cd node4
  besu --data-path=data --genesis-file=../genesis.json --bootnodes=<enode URL> --p2p-port=30306 --rpc-http-enabled --rpc-http-api=ETH,NET,IBFT --host-allowlist="*" --rpc-http-cors-origins="all" --rpc-http-port=8548
  ```
