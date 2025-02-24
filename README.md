# GitHub Linker

This is a fork of [GitHub Linker](https://github.com/mblode/vscode-github-linker) with some changes.

It supports getting a permalink even if your branch isn't listed as a remote in .git/config. If you've pushed or pulled from GitHub, that's enough. And if your branch is not pushed to GitHub, it will use the default branch, which defaults to "main" but can be overridden in the settings. It also adds a command to copy the permalink for the default branch at any time.

The extension is not currently in the marketplace. To install it:

```
git clone --depth 1 -b mms/allow-default-branch https://github.com/MaxPower15/github-linker
cd github-linker
npm install
npm run compile
npm install -g @vscode/vsce
vsce package

# Choose one (or both) of these depending on whether you're installing to VS Code or Cursor
code --install-extension github-linker-0.0.1.vsix
cursor --install-extension github-linker-0.0.1.vsix
```

## Features

GitHub linker allows you to select a piece of text and create a permanent link to GitHub.com for that piece of text. Just select the text, right click, and you'll see two new options.

**Copy a permanent link to the clipboard**

![](gifs/github-linker.gif)

For example:

https://github.com/integrations/jira/blob/d1a890ae8a7092ca08cb9fdf527fcc25f471e68c/lib/models/index.js#L9-L15

**Copy a permanent link and code as markdown**

![](gifs/github-linker2.gif)

The second option not only copies the link but also copies the piece of selected text properly wrapped in a markdown code block with the programming language correctly specified. For example:

    https://github.com/integrations/jira/blob/d1a890ae8a7092ca08cb9fdf527fcc25f471e68c/lib/models/index.js#L9-L15

    ```javascript
    Object.assign(config, {
      operatorsAliases: false,
      benchmark: true,
      logging: (query, ms) => {
        logger.debug({ ms }, query)
      }
    })
    ```

Which will be rendered as:

https://github.com/integrations/jira/blob/d1a890ae8a7092ca08cb9fdf527fcc25f471e68c/lib/models/index.js#L9-L15

```javascript
Object.assign(config, {
  operatorsAliases: false,
  benchmark: true,
  logging: (query, ms) => {
    logger.debug({ ms }, query)
  }
})
```

## Requirements

The file must be tracked in a git repo and the current branch must be pushed to GitHub.com.

If you've made changes to the file that are not pushed to GitHub.com, the link may be inaccurate.

**Enjoy!**

Extension icon made by [Freepik](https://www.freepik.com/ "Freepik") from [www.flaticon.com](https://www.flaticon.com/ "Flaticon") is licensed by [CC 3.0 BY](http://creativecommons.org/licenses/by/3.0/ "Creative Commons BY 3.0")
