# partitioned-loops

[![npm version](https://badge.fury.io/js/partitioned-loops.svg)](https://www.npmjs.com/package/partitioned-loops)
[![npm downloads](https://img.shields.io/npm/dt/partitioned-loops.svg)](https://www.npmjs.com/package/partitioned-loops)
[![dependencies](https://img.shields.io/david/litichevskiydv/partitioned-loops.svg)](https://www.npmjs.com/package/partitioned-loops)
[![dev dependencies](https://img.shields.io/david/dev/litichevskiydv/partitioned-loops.svg)](https://www.npmjs.com/package/partitioned-loops)
[![Build Status](https://travis-ci.org/litichevskiydv/partitioned-loops.svg?branch=master)](https://travis-ci.org/litichevskiydv/partitioned-loops)
[![Coverage Status](https://coveralls.io/repos/github/litichevskiydv/partitioned-loops/badge.svg?branch=master)](https://coveralls.io/github/litichevskiydv/partitioned-loops?branch=master)

Library for partitioned loops organization

# Install

`npm i partitioned-loops`

# Usage

```javascript
const { forEachAsync } = require("partitioned-loops");

/*...*/

const finalState = await forEachAsync(
  [1, 2, 3, 4, 5],
  (currentValue, loopState) => {
    if (currentValue > 4) loopState.break = true;
    else loopState.sum += currentValue;
  },
  { sum: 0 }
);
```

```javascript
const { forAsync } = require("partitioned-loops");

/*...*/

const array = [1, 2, 3, 4, 5];
const finalState = await forAsync(
  0,
  array.length,
  (i, loopState) => {
    if (array[i] > 4) loopState.break = true;
    else loopState.sum += array[i];
  },
  { sum: 0 }
);
```
