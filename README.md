# Notice (2021-6-18)

This repository is not longer needed because lunr-languages now natively supports Chinese since [v1.5.0](https://github.com/MihaiValentin/lunr-languages/releases/tag/1.5.0). Go and get it!

# About

This project is a fork of [MihaiValentin/lunr-languages](https://github.com/MihaiValentin/lunr-languages), and having almost the same codebase except that I manually merge the [MR](https://github.com/MihaiValentin/lunr-languages/pull/53) by [@repairearth](https://github.com/MihaiValentin/lunr-languages/issues?q=is%3Apr+is%3Aopen+author%3Arepairearth) which adds the support for Chinese.

I(darkyzhou) did this because the original project seems to be frozen for over two years without any updates at all, and the MR is stuck from being merged for over two years too.

In addition, the authors of lunr-languages and the MR seem to be hard to get in touch with, their Github profiles show that they hardly have any activities in the last 365 days.

I don't claim any responsibilities for the codebase it self, but if the fact that I publish this package is illegal or hurts someone else, please contact me to delete the project.

# Usage

### Browser

Unfortunately, this package cannot run on browser environment because it depends on the package `nodejieba` to achieve word splitting for Chinese and the library is bound to node.js environment, furthermore, the package's size is about 5MB which is unacceptable in web environment.

I am investigating if there is another library that can offer similar functions as well as can run on browsers.

### Node.js

Install the package using `npm i lunr-languages-zh`, then refer to the example below:

```js
var lunr = require('lunr');
// load these necessary libraries
require('lunr-languages-zh/lunr.stemmer.support')(lunr);
require('lunr-languages-zh/lunr.zh')(lunr);

var idx = lunr(function () {
  this.use(lunr.zh); // load the support for Chinese
  
  this.ref('id');
  this.field('text');

  this.add({
    id: 1,
    text: '...',
  });
});

idx.search('pipe');
```
