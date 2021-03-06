# fastify-crons

A plugin to schedule cron jobs

https://en.wikipedia.org/wiki/Cron

![Node.js CI](https://github.com/heply/fastify-crons/workflows/Node.js%20CI/badge.svg)

## Install

```bash
$ npm i --save fastify-crons
```

## Usage

```js
fastify.register(require('fastify-crons'), {
  timezone: 'Europe/Rome'
})

fastify.crons.schedule('*/2 * * * *', () => {
  console.log('Hi!')
})

// OR:

const task = fastify.crons.schedule('*/2 * * * *', () => {
  console.log('Hi!')
}, {
  scheduled: false
})

task.start()
```

Under the hood, [node-cron](https://www.npmjs.com/package/node-cron#options) is used.

## Options

| Name        | Description                                                                                 |
|-------------|---------------------------------------------------------------------------------------------|
| `timezone`  | Can be used to set the global reference timezone for all scheduled jobs. By default is UTC. |

## Test

```bash
$ npm test
```

## Acknowledgements

This project is kindly sponsored by:

[![heply](https://raw.githack.com/heply/brand/master/heply-logo.svg)](https://www.heply.it)

## License

Licensed under [MIT](./LICENSE)

