# react-wheel-of-prizes

> It is a wheel of prizes game built using react. Originally by [shekharramola](https://github.com/shekharramola), this version has been adapted to allow React 17 and above

[![NPM](https://img.shields.io/npm/v/react-wheel-of-prizes.svg)](https://www.npmjs.com/package/react-wheel-of-prizes) [![JavaScript Style Guide](https://img.shields.io/badge/code_style-standard-brightgreen.svg)](https://standardjs.com)

## Install

```bash
npm install --save react-wheel-of-prizes-react18-compatible
```

Before spinning, this is how it will look
![before spinning](https://github.com/khairyo/react-wheel-of-prizes/blob/681e8bd20c64c9066c5ab10dbcb4b300bcb5f50a/before.png)
After spinning, this is how it will look
![after spinning](https://github.com/khairyo/react-wheel-of-prizes/blob/681e8bd20c64c9066c5ab10dbcb4b300bcb5f50a/after.png)

This component package is fully configurable. you should pass your own array of segColors, array of segments. these are compulsory while winningSegment is optional. if it is not provided then it will be completely random. there is a callback function onFinished where you will get the winning segment.

Also if you want to match with your theme, you can provide primary, contrast color and also the button text. these all are optional.

Now you can also control it's size and play with the upDuration and downDuration property to control it's speed.

Wheel of fortune will run only once by default but if you want to run it more than once then you need to pass `isOnlyOnce={false}`

| Properties     |   default value   | Optional |
| -------------- | :---------------: | -------: |
| segments       |         NA        |       No |
| segColors      |         NA        |       No |
| winningSegment |         NA        |      Yes |
| primaryColor   |       'black'     |      Yes |
| contrastColor  |       'white'     |      Yes |
| buttonText     |       'spin'      |      Yes |
| isOnlyOnce     |        true       |      Yes |
| upDuration     |         100       |      Yes |
| downDuration   |        1000       |      Yes |
| fontFamily     |   'proxima-nova'  |      Yes |
| size           | window.innerWidth |      Yes |

## Usage
This is a sample React component.

```tsx
import React from 'react';
import WheelComponent from 'react-wheel-of-prizes-react18-compatible';

const SpinWheelComponent = () => {
  const segments = [
    'better luck next time',
    'won 70',
    'won 10',
    'better luck next time',
    'won 2',
    'won uber pass',
    'better luck next time',
    'won a voucher'
  ]
  const segColors = [
    '#EE4040',
    '#F0CF50',
    '#815CD1',
    '#3DA5E0',
    '#34A24F',
    '#F9AA1F',
    '#EC3F3F',
    '#FF9000'
  ]
  const onFinished = (winner: string) => {
    console.log(winner)
  }
  return (
    <WheelComponent
      segments={segments}
      segColors={segColors}
      winningSegment='won 10'
      onFinished={(winner) => onFinished(winner)}
      primaryColor='black'
      contrastColor='white'
      buttonText='Spin'
      isOnlyOnce={false}
      size={290}
      upDuration={100}
      downDuration={1000}
      fontFamily='Arial'
      />
  );  
};

export default SpinWheelComponent;
```

## License

GNU General Public License v3.0 © [shekharramola](https://github.com/shekharramola)

