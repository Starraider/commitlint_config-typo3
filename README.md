# commitlint/config-typo3

[![Donate](https://img.shields.io/badge/Donate-PayPal-green.svg)](https://PayPal.me/SvenKalbhenn)
![GitHub](https://img.shields.io/github/license/Starraider/commitlint_config-typo3)
![GitHub issues](https://img.shields.io/github/issues/Starraider/commitlint_config-typo3)
![Lint Code Base](https://github.com/Starraider/commitlint_config-typo3/workflows/Lint%20Code%20Base/badge.svg)

This is a config file, if you want to use commitlint in TYPO3 projects, to make sure your commit messages are in the correct format [as described in the TYPO3 documentation](https://docs.typo3.org/m/typo3/guide-contributionworkflow/master/en-us/Appendix/CommitMessage.html)

## If you use git at the command line

I would recommend to use [typicode/husky](https://github.com/typicode/husky):

    yarn add husky --dev

or

    npm install husky --save-dev

You also need [commitlint](https://github.com/conventional-changelog/commitlint), [commitlint/config-conventional](https://github.com/conventional-changelog/commitlint/tree/master/%40commitlint/config-conventional) and [@commitlint/parse](https://www.npmjs.com/package/@commitlint/parse):

    yarn add commitlint --dev
    yarn add @commitlint/config-conventional --dev
    yarn add @commitlint/parse --dev

or

    npm install --save-dev @commitlint/config-conventional @commitlint/cli @commitlint/parse

Create a .huskyrc file in the root folder of your project, which runs commitlint during the Git commit-msg hook:

    {
        "hooks": {
            "commit-msg": "commitlint -E HUSKY_GIT_PARAMS"
        }
    }

Finally copy the [commitlint.config.js](https://github.com/Starraider/commitlint_config-typo3/blob/master/commitlint.config.js) to the root of your project and you are ready to go.

## If you use git in Visual Studio Code

First go to the Extension-Manager in Visual Studio Code and install the extension "[VSCode Conventional Commits](https://github.com/vivaxy/vscode-conventional-commits)".

To make our own commitlint.config.js work, you have to install [commitlint/config-conventional](https://github.com/conventional-changelog/commitlint/tree/master/%40commitlint/config-conventional).
You can install it localy (which I recommend) or globaly:

    yarn add @commitlint/config-conventional --dev

or

    npm install --save-dev @commitlint/config-conventional

Finally copy the [commitlint.config.js](https://github.com/Starraider/commitlint_config-typo3/blob/master/commitlint.config.js) to the root of your project.

Restart Visual Studio Code and it should work.

Info on how to use "VSCode Conventional Commits" you can find in the [documentation](https://github.com/vivaxy/vscode-conventional-commits).

## Known bugs

According to the [TYPO3 documentation](https://docs.typo3.org/m/typo3/guide-contributionworkflow/master/en-us/Appendix/CommitMessage.html), there should be no colon ":" after the typ.

    [TASK] Remove colon in pattern -> correct
    [TASK]: Remove colon in pattern -> false

But the "[VSCode Conventional Commits](https://github.com/vivaxy/vscode-conventional-commits)" plugin for Visual Studio Code puts always a colon between the typ and the subject. Therefore the headerPattern has to tolerate the colon.

## Additional resources

- [https://commitlint.js.org/](https://commitlint.js.org/)
- [commitlint](https://github.com/conventional-changelog/commitlint)
- [commitlint/config-conventional](https://github.com/conventional-changelog/commitlint/tree/master/%40commitlint/config-conventional)
