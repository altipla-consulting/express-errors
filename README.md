
# express-errors
Debug errors while developing with Express.


## Installation

```sh
$ npm install @altipla/express-errors
```


## Usage

Add the handler always at the very end of the middleware chain. It does not propagate the error, so any middleware below it will not be called.

```ts
import express from 'express'
import { errorHandler } from '@altipla/express-errors'

const app = express()

app.get('/', (req, res) => {
  throw new Error('Something went wrong')
});

// (..add more routes here...)

app.use(errorHandler)
```
