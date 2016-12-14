[![NPM](https://nodei.co/npm/jschardet.png?downloads=true&downloadRank=true)](https://nodei.co/npm/jschardet/)

JsChardet-EastAsia
==================

JsChardet - Port of python's [chardet](https://github.com/chardet/chardet).
JsChardet-EastAsia - Modified from [JsChardet](https://github.com/aadsm/jschardet), just remaining east asia characters.

License
-------

LGPL

How To Use It
-------------

### Node
```   
npm install jschardet-eastasia
```

    var jschardet = require("jschardet-eastasia")

    // "àíàçã" in UTF-8
    jschardet.detect("\xc3\xa0\xc3\xad\xc3\xa0\xc3\xa7\xc3\xa3")
    // { encoding: "UTF-8", confidence: 0.9690625 }

    // "次常用國字標準字體表" in Big5
    jschardet.detect("\xa6\xb8\xb1\x60\xa5\xce\xb0\xea\xa6\x72\xbc\xd0\xb7\xc7\xa6\x72\xc5\xe9\xaa\xed")
    // { encoding: "Big5", confidence: 0.99 }

### Browser
Copy and include [jschardet_eastasia.min.js](https://github.com/jiangzhuo/jschardet-eastasia/tree/master/dist/jschardet_eastasia.min.js) in your web page.

Options
-------

```javascript
// See all information related to the confidence levels of each encoding.
// This is useful to see why you're not getting the expected encoding.
jschardet.Constants._debug = true;

// Default minimum accepted confidence level is 0.20 but sometimes this is not
// enough, specially when dealing with files mostly with numbers.
// To change this to 0 to always get something or any other value that can
// work for you.
jschardet.Constants.MINIMUM_THRESHOLD = 0;
```

Supported Charsets
------------------

* Big5, GB2312/GB18030, EUC-TW, HZ-GB-2312, and ISO-2022-CN (Traditional and Simplified Chinese)
* EUC-JP, SHIFT_JIS, and ISO-2022-JP (Japanese)
* EUC-KR and ISO-2022-KR (Korean)
* UTF-32 BE, LE, 3412-ordered, or 2143-ordered (with a BOM)
* UTF-16 BE or LE (with a BOM)
* UTF-8 (with or without a BOM)
* ASCII

Technical Information
---------------------

I haven't been able to create tests to correctly detect:

* ISO-2022-CN
* EUC-CN

Development
-----------
Use `npm run dist` to update the distribution files. They're available at https://github.com/jiangzhuo/jschardet-eastasia/tree/master/dist.

Authors
-------

Ported from python to JavaScript by António Afonso (https://github.com/aadsm/jschardet)

Transformed into an npm package by Markus Ast (https://github.com/brainafk)
