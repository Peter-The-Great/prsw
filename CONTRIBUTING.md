# How to Contribute

Contributions are encouraged from anyone. This project follows the 
[Code of Conduct](https://www.python.org/psf/codeofconduct/) by the Python
Software Foundation.

Please use the following steps to get started:

1. Fork and clone the repo:

    ```
    $ git clone git@github.com:your-username/prsw.git
    ```

2. Make your changes and include tests that cover your change.

    Run the static analysis tools locally to help ensure it fits within the
    project expectations:

    ```
    $ python pre_push.py

    pre_push.py: Success!
    ```

3. Push your fork and [submit a pull request](https://github.com/jvoss/prsw/compare).

    Please follow these simple guidelines:

    * Always add documentation for your code and do your best to write meaningful tests.
    * Follow [PEP 8](https://peps.python.org/pep-0008/).
    * Write good [conventional](https://www.conventionalcommits.org/en/v1.0.0/)
    commit messages
