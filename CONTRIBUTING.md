# Contributing to CC WordPress Plugin

Thank you for your interest in contributing to CC WordPress Plugin! This document is
a set of guidelines to help you contribute to this project.


## Code of Conduct

By participating in this project, you are expected to uphold our [Code of
Conduct][code_of_conduct].

[code_of_conduct]:https://creativecommons.github.io/community/code-of-conduct/


## Project Documentation

Please consult the [`README`](README.md) for the complete project documentation.


## How to Contribute

Make sure you have gone through our general [Contributing Code][contributing]
guidelines on the Creative Common Open Source website.

[contributing]:https://creativecommons.github.io/contributing-code/


### Development

Master branch is for the releases. Development will be done in the development
branch.  Occasionally other branches may be available to test new features or
play with new ideas, but they may be deleted anytime so don't rely on those
branches. To start contributing code, checkout the `develop` branch.

### WordPress Coding Standards

Creative Commons plugin for WordPress follows [WordPress Coding
Standards][standards] and [WordPress Documentation Standards][inline].  Before
pushing your work/contribution, make sure it closely follows these standards
otherwise it will not be accepted. We use a PHP_CodeSniffer setup with
`'WordPress'` sniff to check the code against the standards.

[standards]: https://make.wordpress.org/core/handbook/best-practices/coding-standards/
[inline]: https://make.wordpress.org/core/handbook/best-practices/inline-documentation-standards/


### Recommended Setup for WordPress Coding Standards

If you are not setup to detect WPCS errors, consider the following steps.

1. **Install Composer**

   Make sure that you have the current version of PHP installed. Then the first
   step is to install [Composer](https://getcomposer.org/). Install it Globally
   by following its [documentation](https://getcomposer.org/doc/00-intro.md)
   for your particular OS.

2. **Install PHP_CodeSniffer**

   Install [PHPCS](https://github.com/squizlabs/PHP_CodeSniffer) by running the
   following command in your terminal:
   ```shell
   composer global require squizlabs/php_codesniffer
   ```

3. **Confirm Installation**

   Check your installation by `which phpcs`, You should get the path to the
   phpcs executable. If you don't get anything for `which phpcs`, you need to
   add this to your .zshrc or .bash_profile (or your shell’s own profile file)
   so it will make terminal look in that folder too:
   ```shell
   export PATH="$HOME/.composer/vendor/bin:$PATH"
   ```

4. **Setup WPCS**

   Clone the official [WordPress Coding Standards repository][wpcs-repo] in
   your home folder. To do so, run the following commands:
   ```shell
   cd
   git clone git@github.com:WordPress-Coding-Standards/WordPress-Coding-Standards.git wpcs
   ```

5. **Tell PHPCS about this directory**

   We need to add the ~/wpcs folder, where we cloned wpcs, to the installed
   paths of phpcs. Replace the path with the path of your wpcs directory:
   ```shell
   phpcs --config-set installed_paths /Users/your-username/wpcs
   ```

6. **Check Installation**

   Confirm that it is working by running the following command:
   ```shell
   phpcs-i
   ```
   The output should be:
   ```
   The installed coding standards are PEAR, Zend, PSR2, MySource, Squiz, PSR1,
   PSR12, WordPress-VIP, WordPress, WordPress-Extra, WordPress-Docs and
   WordPress-Core
   ```
   If it does not include the WordPress Standards, most probably the
   installed_paths config option is wrong. Make sure that it points to the
   right directory.

7. **Visual Studio Code Workflow**

   To configure VSCode so that it may report errors right in the editor,
   install [phpcs extension][phpcs]. Open User Settings and add the following
   settings:
   ```
   "phpcs.executablePath": "/usr/local/bin/phpcs",
   "phpcs.standard": "WordPress"
   ```
   Now, phpcs will report errors inside VSCode. If you are using some other
   editor, consult its documentation. Once there are no reported errors in your
   fix, you are good to go.

[wpcs-repo]: https://github.com/WordPress-Coding-Standards/WordPress-Coding-Standards
[phpcs]: https://marketplace.visualstudio.com/items?itemName=ikappas.phpcs


## Questions or Thoughts?

Talk to us on [our developer mailing list or Slack community][community].

[community]:https://creativecommons.github.io/community/
