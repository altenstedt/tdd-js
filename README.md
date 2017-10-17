What is this?
-------------

This is the setup for the TDD course for JavaScript. You will need
Node.js installed to build and run tests.

  * https://nodejs.org/

The intent here is to show how to setup a package so that you can
start writing unit tests with Node.js and JavaScript. 

Create an npm package in a empty folder

    npm init -y

Install Jasmine

    npm install jasmine --save-dev

Open file `package.json` and edit the `scripts` node:

```json
"scripts": {
  "test": "jasmine"
},
```

Create folders for tests

    mkdir spec/support
    mkdir spec/unit

Create a file jasmine.json in the spec/support folder:

```json
{
  "spec_dir": "spec",
  "spec_files": [
    "**/*[sS]pec.js"
  ],
  "helpers": [
    "helpers/**/*.js"
  ],
  "stopSpecOnExpectationFailure": false,
  "random": false
}
```

Create your tests in the spec/unit folder, for example:

```js
describe("The class under test", () => {
    it("should work", () => {
        expect(1).toBe(1);
    });
});
```

Run the tests using npm:

    npm test