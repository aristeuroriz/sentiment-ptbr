## sentiment (pt-BR)
#### AFINN-based sentiment analysis for Node.js (pt-BR)

### Forked from (https://github.com/thisandagain/sentiment) and modified by Aristeu Roriz for test use only


Sentiment is a Node.js module that uses the [AFINN-111](http://www2.imm.dtu.dk/pubdb/views/publication_details.php?id=6010) wordlist to perform [sentiment analysis](http://en.wikipedia.org/wiki/Sentiment_analysis) on arbitrary blocks of input text. Sentiment provides serveral things:

- Performance (see benchmarks below)
- The ability to append and overwrite word / value pairs from the AFINN wordlist
- A build process that makes updating sentiment to future versions of the AFINN word list trivial

### Installation
```bash
npm install sentiment-ptbr
```

### Usage
```javascript
var sentiment = require('sentiment-ptbr');

var r1 = sentiment('Gatos são estúpidos!');
console.dir(r1);        // Score: -2, Comparative: -0.666

var r2 = sentiment('Gatos são incríveis!');
console.dir(r2);        // Score: 4, Comparative: 1
```

### Adding / overwriting words
You can append and/or overwrite values from AFINN by simply injecting key/value pairs into a sentiment method call:
```javascript
var sentiment = require('sentiment-ptbr');

var result = sentiment('Gatos são incríveis!', {
    'gatos': 5,
    'incríveis': 2  
});
console.dir(result);    // Score: 7, Comparative: 1.75
```
