# JSON-parser

# Build Your Own JSON Parser
This challenge is to build our own JSON parser.

Building a JSON parser is an easy way to learn about parsing techniques which are useful for everything from parsing simple data formats through to building a fully featured compiler for a programming language.

Parsing is often broken up into two stages: lexical analysis and [syntactic analysis](https://en.wikipedia.org/wiki/Parsing). Lexical analysis is the process of dividing a sequence of characters into meaningful chunks, called tokens. Syntactic analysis (which is also sometimes referred to as parsing) is the process of analysing the list of tokens to match it to a formal grammar.

You can read far more about building lexers, parses and compilers in what is regarded as the definitive book on compilers: Compilers: Principles, Techniques, and Tools - widely known as the “Dragon Book” (because there’s an illustration of a dragon on the cover).

### The Challenge - Building a JSON Parser
JSON (which stands for JavaScript Object Notation) is a lightweight data-interchange format, which is widely used for transmitting data over the Internet. It is formally defined by the IETF here: [https://tools.ietf.org/html/std90](https://www.rfc-editor.org/info/std90) or there’s a simpler graphical representation here: [https://www.json.org/json-en.html](https://www.json.org/json-en.html)

### Step Zero
This is software engineering so we’re zero-indexed and for this step we’re going to set our environment up ready to begin developing and testing our solution.

I’ll leave you to setup our IDE / editor of choice and programming language of choice. After that we can download some simple test data for the JSON parser from the [DropBox](https://www.dropbox.com/scl/fi/9vdw9wd9r5gw0azzehnzy/tests.zip?rlkey=mlp42ah3wmdav9w9kvekgk2fp&e=1&dl=0). We also have the same folder in this repository.

### Step 1
In this step our goal is to parse a valid simple JSON object, specifically: ‘{}’ and an invalid JSON file and correctly report which is which. So we should build a very simple lexer and parser for this step.

Your program should report to the standard output stream a suitable message and exit with the code 0 for valid and 1 for invalid. It is conventional for CLI tools to return 0 for success and between 1 and 255 for an error and allows us to combined CLI tools to create more powerful programs. Check out write our own wc tool for more on combing simple cli tools.

You can test our code against the files in the folder tests/step1. Consider automating the tests so we can run them repeatedly as we progress through the challenge.

### Step 2
In this step our goal is to extend the parser to parse a simple JSON object containing string keys and string values, i.e.:

`{"key": "value"}`

You can test against the files in the folder tests/step2.

### Step 3
In this step our goal is to extend the parser to parse a JSON object containing string, numeric, boolean and null values, i.e.:
```
{
  "key1": true,
  "key2": false,
  "key3": null,
  "key4": "value",
  "key5": 101
}
```
You can test against the files in the folder tests/step3.

### Step 4
In this step our goal is to extend the parser to parse a JSON object with object and array values, i.e.:
```
{
  "key": "value",
  "key-n": 101,
  "key-o": {},
  "key-l": []
}
```

You can test against the files in the folder tests/step4.

### Step 5
In this step our goal is to add some of our own tests to ensure we’re confident that our parse can handle valid JSON and will fail with useful error messages on invalid JSON.

Once we’re confident our parser is done and well tested we can try running it against the test suite here: http://www.json.org/JSON_checker/test.zip