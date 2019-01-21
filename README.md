# test-passport-jest-memory-leak
Minimal change set to reproduce issue. When running `npm run test` on this repository, the `--detectLeaks` flag finds
a memory leak.

```
  > passport-jest-test@0.0.1 test /Users/jaredcasner/code/test
  > jest --detectLeaks --config ./jest.config.js

  FAIL  src/index.spec.js
    ● Test suite failed to run

      EXPERIMENTAL FEATURE!
      Your test suite is leaking memory. Please ensure all references are cleaned.

      There is a number of things that can leak memory:
        - Async operations that have not finished (e.g. fs.readFile).
        - Timers not properly mocked (e.g. setInterval, setTimeout).
        - Keeping references to the global scope.

        at node_modules/jest/node_modules/jest-cli/build/TestScheduler.js:275:22

  Test Suites: 1 failed, 1 total
```
