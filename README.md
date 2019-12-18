# GitHub Organization

|Name|Location|Description|
|--|--|--|
|`imager-core`|[imager-io/imager-core](https://github.com/imager-io/imager-core)|Low-Level Implementation|
|`imager-tools`|[imager-io/imager-tools](https://github.com/imager-io/imager-tools)|CLI & Other Executable Tools|
|`imager-io-js`|[imager-io/imager-io-js](https://github.com/imager-io/imager-io-js)|JavaScript Support (Compiled for NodeJS)|

## Miscellaneous

|Name|Location|Description|
|--|--|--|
|`imager.io`|[imager-io/imager.io](https://github.com/imager-io/imager.io)|Imagers Website or Landing Page|

<hr/>

# Imager - **2019**

**Supports only JPEG images. But does this really well (see benchmarks).**

## Features

### Brute Force Image Optimization

> Optimizes the compression using ML based metrics in a trial ’n error sorta manner.

This is a tool that can competitively optimize (e.g.) extremely noisy, high resolution images; at the expense of increased encoding time and CPU overhead. This is a tradeoff that should be suitable for over 90% of online content, where site performance matters.

It's pretty easy too.

<small>Using the CLI interface:</small>
```shell
$ imager -i path/to/input/images/*.jpeg -o output/
```

<small>Using the HTTP server:</small>
```shell
$ imager-server --address 127.0.0.1:3000
```

```shell
$ http 127.0.0.1:3000/opt < path/to/input/image.jpeg > path/to/output/image.jpeg
```

<small>Using the JavaScript non-blocking API:</small>

```javascript
const {ImageBuffer} = require("imager-io");
ImageBuffer
	.open("source-image.jpeg")
	.then(buffer => buffer.opt())
	.then(buffer => buffer.save("result.jpeg"))
	.then(() => console.log("done"));
```


## [Image Compression Benchmarks](https://github.com/colbyn/imager-bench-2019-11-2)

```text
source        : ▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇ 39.00M (4 images)
kraken.io     : ▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇ 24M
jpegmini.com  : ▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇ 16M
compression.ai: ▇▇▇▇▇▇▇▇ 8.90M
imager        : ▇▇▇▇ 4.20M
```

## [Download & Install](https://github.com/imager-io/imager/releases)

Prebuilt binaries can be found [here](https://github.com/imager-io/imager/releases).

# Imager - early to mid **2020**

Lots of stuff under development, including support for a multitude of image formats. Potentially with experimental support for video!

See [imager-core](https://github.com/imager-io/imager-core) for current implementation details and progress.

<hr/>

Copyright 2019 Colbyn Wadman