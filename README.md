# react-countdown-date

This a small component that will only reveal it's children once it's given date
has passed. And will show a countdown as place holder.

## Installation

The module is released in the public npm registry and can be installed by
running:

```
npm install --save react-countdown-date
```

Please note that this module is written in ES6, so you might need to run a babel
compiler over the code before it can work in your project.

## API

The component accepts the following properties:

- `date` **required** The date on which the contents should be shown.
- `prefix` Component, or text that will be prepend to the countdown.
- `passed` An optional callback function which will be executed when the date
  has passed.

```js
import Countdown from 'react-countdown-date';
import React, { Component } from 'react';

class Example extends Component {
  render() {
    return (
      <Countdown date={ this.props.date }>
        The time has passed, this text is now showing instead.
      </Countdown>
    );
  }
}
```

When we render the example component above it would output the following HTML
structure:

```html
<div class='countdown active'>
  <div class='days'>
    10
    <span>Days</span>
  </div>
  <div class='sep'>:</div>

  <div class='hours'>
    7
    <span>Hours</span>
  </div>
  <div class='sep'>:</div>

  <div class='mins'>
    43
    <span>Minutes</span>
  </div>
  <div class='sep'>:</div>

  <div class='secs'>
    09
    <span>Seconds</span>
  </div>
  <div class='sep'>:</div>
</div>
```

It's worth nothing that once there are only 10 seconds left on the clock,
a `finalcountdown` is added to the `secs` class name. If the supplied `date` has
passed it would result in the follow:

```html
<div class='countdown inactive'>
  Your children here
</div>
```

## License

MIT
