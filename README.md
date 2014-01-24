# Natural Language Hours Parsing

The goal of this challenge is to create a parser that can read store opening hours written by a human and produce a machine-readable canonical (structured) representation.

For example:

```
var hours = require('kites-challenge-1')
var input = 'Sun.-Thur. 11:00-23:00, Friday-Sat. 1100-0000'
var output = hours.parse(input)
console.log(output)  // S0-4:1100-2300;5-6:1100-2400
```

Please also read [the FAQ](https://github.com/kites/kites-challenge-1/wiki).

## The Output Format

The first thing you should do is read `test/index.js`. It is the **canonical reference**. As long as your parser correctly implements the reference tests, it is considered a correct solution.

Some English notes:

* There is only one correct output for a given input string.
* The parser deals with input hours overlaps.
* A day begins at 0000 and ends at 2800.

# Usage

## Instructions

1. Clone this repository to your own Github public repository and development machine; do **NOT** fork, as other candidates would be able to see your solution
2. Run `npm install`
3. Implement `hours.parse` in `lib/index.js`
4. Ensure all tests pass in node via `npm test`
5. Ensure all tests pass in phantomjs and all browsers
6. When finished, send us a link to the public repository you used

## Hints

* Before starting, study the input **grammar** in `test/index.js` very carefully.
* We deliberately excluded some edge cases to make your implementation easier. You do not need to implement a full-blown solution that will parse every possible way of writing store opening hours; just the ones listed in the test file.
* After writing a correct implementation in English, dealing with Chinese input should be relatively trivial.
* At Kites, we use [zuul](https://github.com/defunctzombie/zuul) and [SauceLabs](https://saucelabs.com/) to do our browser testing. SauceLabs includes nice [free testing support](https://saucelabs.com/opensauce) for public repositories.

## Scoring

To pass, you must provide supporting proof or very clear instructions for how to build and verify your solution passes tests in node, phantomjs, and all browsers. If your solution fails for any subset of platforms or platform versions (e.g. passes every Firefox except Firefox 24.0), you must document the failure and explain why.

**You will be graded on how easy-to-{read,maintain,verify} your code and documentation are.**

Ideally your solution is **easily extensible** as we add additional types of test cases. We *strongly encourage* you to casually browse the web and research other ways humans write opening hours. A trivial example: how much work would it be to accomodate hours that look like "9:30 a.m. - 5:00 p.m. Mon to Fri"?

Bonus points for including additional (even if skipped) tests in your solution from this research.

