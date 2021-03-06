# proxmox-client
A node.js client for the Proxmox API

## Usage example

```js
const proxmox = require('proxmox-client');

proxmox.auth('localhost:8006', 'root', 'tokenName', 'token', 'pam');

// possible other file
const proxmox = require('proxmox-client');

proxmox.get('/nodes').then((res) => {
  if(res.status !== 200) {
    console.log("statusCode is not 200");
  }
  res = JSON.parse(res.text).data;
  console.log(res);
});
```

## API

### `proxmox.auth(host, user, tokenName, token, realm = 'pam')`

Stores tha auth information

### `proxmox.get(path)`

Sends a GET Request to the defined path and returns a superagent request

### `proxmox.post(path, body)`

Sends a POST Request to the defined path with the defined body and returns a superagent request

### `proxmox.put(path, body)`

Sends a PUT Request to the defined path with the defined body and returns a superagent request

### `proxmox.delete(path)`

Sends a DELETE Request to the defined path and returns a superagent request

### `proxmox.del(path)`

Sends a DELETE Request to the defined path and returns a superagent request

## License

GPL-3.0