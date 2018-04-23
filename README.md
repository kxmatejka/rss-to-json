Smart rss to json
=================

DISCONTINUED - library has been [forked](https://www.npmjs.com/package/feed-to-json-promise) by company Economia a.s. which I am an employee

---

Util for parse ATOM and RSS feed resources and normalize them to JSON object.

## Install

```sh
npm install smart-rss-to-json --save
```

## ES6 import

```js
import Rss from 'smart-rss-to-json'
``` 

## Node js import

```js
const Rss = require('smart-rss-to-json')
```

## Example

```js
import Rss from 'smart-rss-to-json'

const rss = new Rss()
rss.load('https://www.aktualne.cz/mrss/').then(feed => {
  console.log(feed)
}).catch(error => {
  console.error(error)
})
```

## Result
```json

{
  "title": "Aktuálně.cz",
  "description": "Aktuálně.cz - kompletní zpravodajství, zprávy z domova i ze světa",
  "link": "https://www.aktualne.cz/",
  "domain": "aktualne.cz",
  "name": "aktualne",
  "image": {
    "url": "https://i0.cz/bbx-8/aktualnehp/img/acz-desktop-logo-dark.png",
    "title": "Aktuálně.cz",
    "description": "Aktuálně.cz - kompletní zpravodajství",
    "width": "436",
    "height": "374"
  },
  "items":[
    {
      "title": "Držme si palce, ať přijde změna, řekl Hilšer. Žena mu zakázala další kandidaturu do sedmdesáti",
      "description": "Průzkumy Marku Hilšerovi předpovídaly maximálně pět procent, nakonec dosáhl téměř na devět. Jiřímu Drahošovi nabídl pomoc v kampani před druhým kolem.",
      "link": "https://zpravy.aktualne.cz/domaci/drama-dopadlo-dobre-drzme-si-palce-at-prijde-zmena-rekl-hils/r~415cedd2f88811e7988aac1f6b220ee8/",
      "date": "Sat, 13 Jan 2018 23:15:13 +0100",
      "timestamp": 1515881713000,
      "media": {
        "thumbnail": {
            "url": "https://cdn.i0.cz/public-data/34/08/fc1aa5f739dd8ba762522e86747f_r4:3_w200_h150_gf1ea9e8af87c11e7afac0cc47ab5f122.jpg",
            "title": "Hilšer",
            "description": "Držme si palce",
            "width": "200",
            "height:": "150"
        },
        "content": [
          {
            "url": "https://cdn.i0.cz/public-data/34/08/fc1aa5f739dd8ba762522e86747f_r3:2_w396_h264_gf1ea9e8af87c11e7afac0cc47ab5f122.jpg",
            "title": "Hilšer",
            "description": "Držme si palce",
            "width": "396",
            "height:": "264"
          }
        ]
      }
    }
  ]
}
```

## Options

Name | Default | Required | Description
--- | --- | --- | ---
timeout | 1000 | false | timeout for http request
maxCount | null | false | maximum number of items in feed
maxTimeDiff | null | false | maximum difference in seconds between current timestamp and item date

