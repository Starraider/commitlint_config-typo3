# commitlint/config-typo3

## If you use git at the command line

I would recommend to use [typicode/husky](https://github.com/typicode/husky) and [Commitizen](https://commitizen.github.io/cz-cli/)

## If you use git in Visual Studio Code

First go to the Extension-Manager in Visual Studio Code and install the extension "[VSCode Conventional Commits](https://github.com/vivaxy/vscode-conventional-commits)".

To make our own commitlint.config.js work, you have to install [commitlint/config-conventional](https://github.com/conventional-changelog/commitlint/tree/master/%40commitlint/config-conventional). 
You can install it localy (which I recommend) or globaly:

    yarn add @commitlint/config-conventional --dev

or

    npm install --save-dev @commitlint/config-conventional @commitlint/cli

Then copy the commitlint.config.js to the root of your project. 

After you have restarted Visual Studio Code, the "[VSCode Conventional Commits](https://github.com/vivaxy/vscode-conventional-commits)" extension will use our commitlint.config.js each time you write a commit message.

https://www.youtube.com/watch?v=6u9gmwTl3bY
https://www.youtube.com/watch?v=O4ZIJgOWj_A
