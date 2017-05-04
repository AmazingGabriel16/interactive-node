# Beam Interactive Node 2
[![Build Status](https://travis-ci.org/WatchBeam/beam-interactive-node2.svg?branch=master)](https://travis-ci.org/WatchBeam/beam-interactive-node2)

A TypeScript, NodeJS and Browser compatible client for [Beam.pro's interactive 2 Protocol](https://dev.beam.pro/reference/interactive/protocol.pdf). 

For an introduction to interactive2 checkout the [reference docs](https://dev.beam.pro/reference/interactive/index.html) on the developers site.

## Installation
You can use npm(recommended) or download a zip from the [releases page](https://github.com/WatchBeam/beam-interactive-node2/releases).

### Browser

```html
<script src="dist/interactive.js"></script>
```

### Node
```
npm i --save beam-interactive-node2
```
## Usage

### Authentication
[OAuth 2.0](https://tools.ietf.org/html/rfc6749) is used for authentication. Valid bearer tokens can be passed in the [Client.open](https://watchbeam.github.io/beam-interactive-node2/classes/client.html#open) method.

For more information about Beam's OAuth visit the [OAuth reference page](https://dev.beam.pro/reference/oauth/index.html) on our developer site.

### Browser

#### index.html
```html
<doctype html>
<html>
    <head>
        <title>Interactive 2</title>
    </head>
    <body>
        <script src="js/interactive.js"></script>
        <script src="js/app.js"></script>
    </body>
</html>
```

#### app.js
```js
const client = new interactive.GameClient();

client.open({
    authToken: '<OAuth Token>',
    url: '<Server Url>',
    versionId: 1234,
});
```
### Node

#### JavaScript
```js
const interactive = require('beam-interactive-node2');
const ws = require('ws');

interactive.setWebSocket(ws);

const client = new interactive.GameClient();

client.open({
    authToken: '<OAuth Token>',
    url: '<Server Url>',
    versionId: 1234,
});
```

#### TypeScript
```ts
import { GameClient, setWebSocket } from 'beam-interactive-node2';
import * as ws from 'ws';

setWebSocket(ws);

const client = new GameClient();

client.open({
    authToken: '<OAuth Token>',
    url: '<Server Url>',
    versionId: 1234,
});
```

## Examples

Checkout our [examples](examples/) to get up to speed quickly!

* [basic](examples/basic.ts) - Connects and sets up 5 buttons, when they are clicked the participant is charged 1 spark.
* [dynamicControls](examples/dynamicControls.ts) - Connects and then creates and destroys 5 buttons with random text.
* [joystick](examples/joystick.ts) - Connects and creates a joystick, logs participant coordinate values.

## Documentation

Checkout our reference docs [here](https://watchbeam.github.io/beam-interactive-node2/).

## Development

To get a development environment setup:
1. Clone this repository
1. `npm install`
1. `npm run build`

### Contributing

Thanks for your interested in contributing, checkout [TODO.md](TODO.md) for a list of tasks!

Open a [Pull Request](https://github.com/WatchBeam/beam-interactive-node2/pulls) we'd love to see your contributions.

