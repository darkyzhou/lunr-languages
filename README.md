# Notice

This project is a fork of [MihaiValentin/lunr-languages](https://github.com/MihaiValentin/lunr-languages), and having almost the same codebase except that I manually merge the [MR](https://github.com/MihaiValentin/lunr-languages/pull/53) by [@repairearth](https://github.com/MihaiValentin/lunr-languages/issues?q=is%3Apr+is%3Aopen+author%3Arepairearth) which adds the support for Chinese.

I(darkyzhou) did this because the original project seems to be frozen for over two years without any updates at all, and the MR is stuck from being merged for over two years too. 

In addition, the authors of lunr-languages and the MR seem to be hard to get in touch with, their Github profiles show that they hardly have any activities in the last 365 days.

I don't claim any responsibilities for the codebase it self, but if the fact that I publish this package is illegal or hurts someone else, please contact me to delete the project.

# Installation

```
npm i darkyzhou/lunr-languages-with-zh-support
```

# Usage

```js
var lunr = require("lunr")
require("darkyzhou/lunr-languages-with-zh-support/lunr.stemmer.support")(lunr)
require("darkyzhou/lunr-languages-with-zh-support/lunr.zh")(lunr)

var idx = lunr(function () {
  this.use(lunr.zh)
  this.ref('id')
  this.field('text')

  this.add({
    id: 1,
    text: "..."
  })
})

idx.search('pipe')
```