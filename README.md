# GitHub Action to run your Laravel application's test suite.

This GitHub Action will run your [Laravel](https://laravel.com) application's test suite with `php artisan test`.

For more information about testing your Laravel application see the [official documentation](https://laravel.com/docs/testing).

## Usage

To use this action, call it as a step in one of your workflows.

See [action.yml](action.yml)

<!-- start usage -->
```yaml
name: 'Test'

on:
  pull_request:
  workflow_dispatch:

jobs:
  test:
    runs-on: ubuntu-latest
    name: Test
    steps:
      - uses: actions/checkout@v3
      - uses: halaslabs/laravel-test-runner@v1
        with:
          php-version: 8.2
```
<!-- end usage -->

A demo of the action can be seen here: https://github.com/halaslabs/laravel-test-runner/actions/workflows/test.yml

### Inputs

```yaml
- uses: halaslabs/laravel-test-runner@v1
  with:
    # Version of php to install for running the test suite.
    # For supported versions, see: https://github.com/shivammathur/setup-php#tada-php-support
    # default: 8.2
    php-version: '8.2'

    # If true, we run https://github.com/shivammathur/setup-php prior to running your laravel tests
    # If false, you are in charge of setting php as needed for your application.
    # default: true
    setup: 'true'
```
