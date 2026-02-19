## Command-line options

- `--local` allow the Bot API server to serve local requests
- `--http-port=8081` HTTP listening port\
  Default is 8081
- `--http-stat-port=8082` HTTP statistics port
- `--dir=` server working directory
- `--temp-dir=` directory for storing HTTP server temporary files
- `--filter=` \<remainder>/\<modulo>. Allow only bots with `bot_user_id % modulo == remainder`
- `--max-webhook-connections=` default value of the maximum webhook connections per bot
- `--http-ip-address=` local IP address, HTTP connections to which will be accepted.\
  By default, connections to any local IPv4 address are accepted
- `--http-stat-ip-address=` local IP address, HTTP statistics connections to which will be accepted.\
  By default, statistics connections to any local IPv4 address are accepted
- `--log=` path to the file where the log will be written
- `--verbosity=` log verbosity level
- `--memory-verbosity=` memory log verbosity level\
  Defaults to 3
- `--log-max-file-size=` maximum size of the log file in bytes before it will be auto-rotated\
  Default is 2000000000
- `--username=` effective user name to switch to
- `--groupname=` effective group name to switch to
- `--max-connections=` maximum number of open file descriptors
- `--cpu-affinity=` CPU affinity as 64-bit mask\
  Defaults to all available CPUs
- `--main-thread-affinity=` CPU affinity of the main thread as 64-bit mask\
  Defaults to the value of the option --cpu-affinity
- `--proxy=` HTTP proxy server for *outgoing webhook* requests in the format `http://host:port`
- `--tdlib-proxy-type=` Type of TDLib proxy (SOCKS5, HTTP, or MTPROTO)
- `--proxy-server=` Server address of the TDLib proxy
- `--proxy-port=` Port of the TDLib proxy
- `--proxy-login=` Username for the TDLib proxy
- `--proxy-password=` Password for the TDLib proxy
- `--proxy-secret=` Secret for the TDLib MTProto proxy


## Examples with proxy

#### MTProto
./telegram-bot-api --api-id=YOUR_API_ID --api-hash=YOUR_API_HASH \
  --proxy-server=127.0.0.1 --proxy-port=443 --tdlib-proxy-type=mtproto \
  --proxy-secret=secret_here

#### SOCKS5
./telegram-bot-api --api-id=YOUR_API_ID --api-hash=YOUR_API_HASH \
  --proxy-server=127.0.0.1 --proxy-port=1080 --tdlib-proxy-type=socks5 \
  --proxy-login=username --proxy-password=password

#### HTTP
./telegram-bot-api --api-id=YOUR_API_ID --api-hash=YOUR_API_HASH \
  --proxy-server=127.0.0.1 --proxy-port=8080 --tdlib-proxy-type=http \
  --proxy-login=username --proxy-password=password