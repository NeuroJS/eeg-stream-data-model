# Data Model Standard for EEG Streams

The purpose of this document is to promote a discussion for standardizing a data model for streaming EEG.

> Data should always assume a data buffer.

Example in JSON format:

```js

{
  "metric": String // E.g. EEG, ACCL, etc (optional)
  "source": String // E.g. Muse, OpenBCI, etc (optional)
  "sampleRate": Number // E.g. 250. always in hz (optional)
  "mock": Boolean // E.g. false (optional)
  "buffer": [ // List of samples
    {
      "timestamp": Date, 
      "data": [ // List of channels
        {
          "id": String // E.g. FP1, FP2, F3, F4, C3, C4, etc (optional)
          "value": Number
        },
        ...
      ]
    }
  ]
}

```

