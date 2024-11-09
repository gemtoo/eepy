# Eepy - dockerized eepsite base

## Why this exists?
To easily and securely run sites in the I2P network.

## How to use it?
0. Ensure you are running as `root` user. Non-`root` users that are in `docker` group will have permission issues.
1. Launch the containers.
```
docker compose up -d && docker compose logs -f
```
2. In browser, open `i2pd` web console at `http://localhost:17070` -> Go to I2P tunnels section -> There should be a single entry:
```
eepsite => <random-sequence-of-characters>.b32.i2p
```
3. Done. The `<random-sequence-of-characters>.b32.i2p` is your brand new eepsite. Open this link with any I2P capable browser. It's working if you see:
```
Hello I2P!
```

## Notes
1. Your eepsite might not be instantly available at `<random-sequence-of-characters>.b32.i2p`, give it a couple of minutes to propagate over the I2P network.
2. By default, the `/` of the eepsite is located in `./eepsite`.

## Troubleshooting
If `i2pd` container complains on incorrect permissions, use the next approach:
```
chmod -Rv 777 ./configs/i2p
```
