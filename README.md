[<img alt="TAI Lab." width="59px" src="https://github.com/ladooniani/Terbinari-CBM-Robot/blob/main/images/dropsuit.png" />](https://github.com/ladooniani/dropsuit#readme)

<!--
[![npm version](https://img.shields.io/npm/v/dropsuit-bow.svg?style=flat)](https://www.npmjs.com/package/dropsuit-bow) [![npm](https://img.shields.io/npm/dt/dropsuit-bow.svg?style=flat-square)](https://www.npmjs.com/package/dropsuit-bow) [![License](https://img.shields.io/npm/l/dropsuit-bow.svg)](https://www.npmjs.com/package/dropsuit-bow)
-->

# DropSuit NLP: bow Function for Generating a Bag of Words

[DropSuit](https://github.com/ladooniani/dropsuit#readme) NLP is an open-source JavaScript and Node.js library that offers diverse functions for natural language processing and data manipulation. The bow function is a part of this library and is used for generating a bag of words from input text and data requests. This function returns an array of 'bag of words'. The bow function is open-source and available under the Apache License 2.0.

### Installation

Add the library function by installing it via npm:

```
npm install dropsuit-bow
```

### Usage

Import the library in your project:

```
const dropsuit_bow = require("dropsuit-bow");

```

The provided code imports the Dropsuit Bow library into your project. You can create a new instance of the dropsuit_bow class by passing in null as the argument, which will process the basic bag of words from the input sentence. If you want to see the processing results in the terminal, you can set the second argument to true when creating the instance, like this:

```
let dsbow = new dropsuit_bow(null, false);
```

#### bow(input: string|array|null)

- **input**: Input sentence string, or leave as null to use constructor input.

#### Return option:

- **vector()** Returns the bag of words (BOW) with word count pairs in the format of `{ 'word': 1 }`.
- **values()** Returns the numeric BOW values array `[ 0, 1 ]`
- **chars()** Returns character frequency vector `{ 'a': 1 }`.
- **tokens()** Returns an array of processed tokens.

```
let input = "John likes to watch movies. Mary likes movies too.";

let out = dsbow.bow(input);
console.log(out);
```

Processing output:

```

{
  bow_vect: { john: 1, likes: 2, to: 1, watch: 1, movies: 2, mary: 1, too: 1 },
  val_vect: [
    1, 2, 1, 1,
    2, 1, 1
  ],
  char_frq: {
    j: 1,
    o: 6,
    h: 2,
    n: 1,
    l: 2,
    i: 4,
    k: 2,
    e: 4,
    s: 4,
    t: 3,
    w: 1,
    a: 2,
    c: 1,
    m: 3,
    v: 2,
    r: 1,
    y: 1
  },
  proc_str: 'john likes to watch movies mary likes movies too',
  cont_str: 'johnlikestowatchmoviesmarylikesmoviestoo',
  tokenized: [
    'john',   'likes',
    'to',     'watch',
    'movies', 'mary',
    'too'
  ],
  vector: [Function: vector],
  values: [Function: values],
  chars: [Function: chars],
  tokens: [Function: tokens]
}

```

Refer to the [tests](https://github.com/ladooniani/dropsuit-bow/blob/main/test/index.test.js) for more information on how to use additional options for Bag of Words. You can provide an 'intentData' object from the [intents.json](https://github.com/ladooniani/dropsuit-bow/blob/main/test/intents.json) file to the constructor using the 'jsonIntStrct' function, as shown below:

```
const json_data = require("dropsuit-bow/jsobj.js");
let intentData = json_data.jsonIntStrct("assets/json/intents.json");

```

Alternatively, you can provide an array of strings to the constructor as input:

```
let inputArray = [
  "John likes to watch movies. Mary likes movies too.",
  "Mary also likes to watch football games.",
];
```
<!--
## Links

- npm: https://www.npmjs.com/package/dropsuit-bow
-->
## Supporting DropSuit

DropSuit is an open-source library and I am dedicated to ensuring its continued development and improvement. If you have any questions, feedback, or encounter any issues, please reach out through the [support via PayPal](https://www.paypal.com/paypalme/dropsuit?country.x=GE&locale.x=en_US), and read more about [support details](https://github.com/ladooniani/dropsuit/blob/main/Support.md).

Your support is crucial for the library's success. You can also contribute to the project by submitting bug reports, feature requests, or by providing feedback. Sharing the library with others who may find it useful and giving it a star on GitHub are also great ways to show your support. Thank you for using DropSuit!

## License

[Apache License 2.0](LICENSE.txt)
