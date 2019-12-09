⚡ Lightweight Node.js HTTP client.

![logo](./logo.png)

## Install

```
npm i lightning-request
```

## Why lightning-request?

lightning-request is the most lightweight HTTP client for Node, it provides a number of extremely useful features.

## Use lightning-request

First, require the library.

```
const request = require('lightning-request');
```

Then let's make a request in an async function.

```
const request = require('lightning-request');

(async function() {
  try {
    const result = await request({
      url: 'https://github.com/node-labx/lightning-request',
    });
    console.log(result.statusCode); // response status code
    console.log(result.body); // response body
  } catch (error) {
    console.log(error);
  }
})();
```

## Request Config

These are the available config options for making requests. Only the url is required. Requests will default to GET if method is not specified.

```
{
  // `url` is the server URL that will be used for the request
  url: 'http://www.example/test',

  // `method` is the request method to be used when making the request
  method: 'get', // default

  // `headers` are custom headers to be sent
  headers: {'X-Requested-With': 'XMLHttpRequest'},

  // `data` is the data to be sent as the request body
  data: {
    firstName: 'Fred'
  },

  // `timeout` specifies the number of milliseconds before the request times out.
  // If the request takes longer than `timeout`, the request will be aborted.
  timeout: 1000, // default is `15000` (no timeout)

  // `responseType` indicates the type of data that the server will respond with
  // options are: 'json', 'text'
  responseType: 'json', // default

  // `agent` define a custom agent to be used when performing http or https requests,
  // respectively, in node.js. This allows options to be added like `keepAlive` that are not enabled by default.
  agent: new http.Agent({ keepAlive: true }),
}
```

## Response Schema

The response for a request contains the following information.

```
{
  // `statusCode` is the HTTP status code from the server response
  statusCode: 200,

  // `statusMessage` is the HTTP status message from the server response
  statusMessage: 'OK',

  // `headers` the headers that the server responded with All header names are lower cased
  headers: {},

  // `body` is the response data that was provided by the server
  body: {}
}
```

## Contributing

- Fork this repo
- Clone your repo
- Install dependencies
- Checkout a feature branch
- Feel free to add your features
- Make sure your features are fully tested
- Open a pull request, and enjoy <3

## License

[MIT](LICENSE)
