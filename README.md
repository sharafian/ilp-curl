# ILP Curl
> curl-like CLI for ILP paid requests

## Usage

```sh
# install the package globally to add binaries
$ npm install -g ilp-curl

# Configure an ILP account. Currently, the easiest way to do this is with the
# XRP testnet, but other networks and currencies are supported.  Go to
# https://ripple.com/build/xrp-test-net/ to get testnet credentials
$ export ILP_PLUGIN='ilp-plugin-xrp-escrow'
$ export ILP_CREDENTIALS='{"server":"wss://s.altnet.rippletest.net:51233","secret":"..."}'

# make a paid POST request with JSON parameters
$ ilp-curl ilp.example.com/sms --json -F to='+15551234567' -F text='hello'

# make a paid POST request with JSON parameters and a max amount of 0.1 XRP
$ ilp-curl ilp.example.com/sms --json -F to='+15551234567' -F text='hello' --amount 0.1

# make a paid GET request
$ ilp-curl -X GET ilp.example.com/images

# make a paid and authenticated request
$ ilp-curl -X GET ilp.example.com/images --user admin:password
```

## More Options

```
Options:
  --help            Show help                                          [boolean]
  --version         Show version number                                [boolean]
  --data, -d        body data
  --json, -j        send data as json
  --header, -H      header with data                       [array] [default: []]
  --form, -F        form data                              [array] [default: []]
  --max-redirs      max number of redirects                [number] [default: 0]
  --request, -X     http method to use                         [default: "POST"]
  --url             url to fetch
  --user, -u        <user:password> for basic auth
  --max-amount, -a  maximum amount (in currency of ILP plugin)      [default: 1]
```
