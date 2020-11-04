#### Test Task

Implement a single page application which reads measurements from stream (WebSocket). The changes should be reflected as soon as they are updated. Measurements can be one of following types "string", "float" or array with coordinates (Location)

The visualization can be in a form of a table, but feel free to use other options.

_Requirements:_
- ES6
- React.js
- track your development in github
- documentation how to build and run the app

Managing of application state and side effects is a matter of choice.
All other additions or improvements to main requirements like adding tests and code quality will be also evaluated. 

#### API Description

The API consists of websocket stream, accessible at ```wss://jsdemo.envdev.io/ws```. The stream is pushing data as array of timeseries with metadata and measurements. A timeserie is key-value map of structure:

- _id uniquely identifies the timeserie
- _name_, e.g. Pressure, Temperature, Serial
- _unit_, e.g. V, mg/m³
- _measurements_ is an array of timestamp (uniq epoch) and value tuples

Example:
```
[
  {
    "name":"Pressure",
    "unit":"hPa",
    "measurements":[
    ],
    "_id":"58c15afe518ca70001b80345"
  },
  {
    "name":"PM1",
    "unit":"mg/m³",
    "measurements":[
      [
        1489066748,
        0.35888445412371583
      ],
      [
        1489066749,
        0.38890237784380327
      ],
      [
        1489066750,
        0.36088984314940226
      ]
    ],
    "_id":"58c15afe518ca70001b80340"
  },
  {
    "name":"Location",
    "measurements":[
      [
        1489066746,
        [
          40.55404852193788,
          -73.27629907400552
        ]
      ],
    "_id":"58c15afe518ca70001b80343"
  }
]
```
