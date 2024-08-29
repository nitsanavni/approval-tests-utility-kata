# Approval Tests Utility Kata

## Context

- How to test a testing utility?
- Practice leveraging LLMs

## The Task

Build an Approval Tests utility.

In your programming language of choice, build a function called `verify` that takes a `received` string and a `testName` string.
The function should:

- Compare `received` with the approved text stored in the `{testName}.approved` file \*
- If the strings match: do nothing and return
- If there's a mismatch:
  1. Throw a `Mismatch` exception
  2. Launch a diff tool (e.g. Beyond Compare):

      comparing between `{testName}.received` (needs to be created) and `{testName}.approved`

\* If the approved file does not exist yet, create an empty one

Make sure to have fun using your new testing utility on a different kata.

## Extensions

- Support injecting a different diff tool
- Wrap the approvals functionality in a cli app `verify`, used like this:

    ```shell
    echo "this is my test result (aka received)" | verify --test-name "my test"
    ```

    The process should exit with status 0 (test passed) or 1 (test failed).

- Add support to automatically approve test results
- Infer `testName` from the calling test function name
