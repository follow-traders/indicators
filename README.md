# Streaming Technical Indicators
## High performance for you trading application

The main feature of these indicators is their continuous operation, which means that you can use them both for real trading and for teaching trading strategies on history, since this is a passage from the beginning to the end of the stream of candles. This approach allows you to reduce the number of necessary calculations by tens of times and is the most optimal in terms of performance.

## Features
- High perfomance
- Easy to use with candles streaming
- Minimal state for calculation
- Typescript

## Download

Releases are available under Node Package Manager (npm):

    npm install @follow-traders/indicators

## Exapmle with Simple Moving Average

```js
import { SMA } from '@follow-traders/indicators';
const sma = new SMA(4); // Create SMA with 4 period

// SMA workflow
//=> [ '2.50', '3.50', '4.50', '5.50', '6.50', '7.50' ]
//=>   │       │       │       │       │       └─(6+7+8+9)/4
//=>   │       │       │       │       └─(5+6+7+8)/4
//=>   │       │       │       └─(4+5+6+7)/4
//=>   │       │       └─(3+4+5+6)/4
//=>   │       └─(2+3+4+5)/4
//=>   └─(1+2+3+4)/4

sma.nextValue(1); // undefiend
sma.nextValue(2); // undefiend
sma.nextValue(3); // undefiend
sma.nextValue(4); // 2.50
sma.nextValue(5); // 3.50
sma.nextValue(6); // 4.50
sma.nextValue(7); // 5.50
sma.nextValue(8); // 6.50
sma.nextValue(9); // 7.50

```


### Currently available indicators
- SMA
- EMA
- RSI
- STOCHASTIC

### Extra indicators by FT
- MOVE (direction move with power no less than p)
- WAVE (directional move with bearish or bullish candle series and power p)