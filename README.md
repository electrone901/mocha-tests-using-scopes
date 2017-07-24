# Mocha & Chai Tests using functions & Scopes

These are simple tests using Mocha and Chai to master functions and scopes.

# How to use this repository

Run the specrunner.html file in a browser. This document shows all passed test. 

The **functions.js** folder holds all the pssing tests that are being displayed in **SpecRunner.html**.

# Notes on Test: 
A test block starts with an `it` function. The `it` function takes two arguments. The first one is a statement describing the rule addressed by the test. The second is a function that will either evaluate to true or false using the `expect` function. The expect statement (`expect(ACTUAL === 'inner').to.be.true;`) will evaluate if the statement between the parens `ACTUAL === 'inner'` is true. You can almost read it like plain English. The expect statement below "expects that the variable ACTUAL equals the value 'inner' to be true".

####Failing Test Example

      it('a function has access to its own local scope variables',

      function () {
        var fn = function () {
          var name = 'inner';
          ACTUAL = name;
        };
        fn();
        expect(ACTUAL === '???').to.be.true;
        //change '???' to what ACTUAL evaluates to.
      });

####Passing Test Example

      it('a function has access to its own local scope variables',

      function () {
        var fn = function () {
          var name = 'inner';
          ACTUAL = name;
        };
        fn();
        expect(ACTUAL === 'inner').to.be.true;
        //changed '???' to 'inner'
        //(because we assigned ACTUAL, a global variable to name inside fn)
      });


