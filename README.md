# eslint-gitstaged

Using **current git staged files** to find out modfied and added files passing eslint, to prevent lint the whole repository again and again.  This is a nice package to use along with `git precommit`.

## Install

```
npm install eslint-gitstaged
```

## Command line usage

Install global

```
npm i -g eslint-gitstaged
```

Usage

```
Usage: eslintgs [options] [command]

  Commands:

    help  Display help

  Options:

    -e, --eslint [value]  eslint.json file path (defaults to "./.eslintrc.json")
    -E, --ext [value]     extension names, can use multiple extensions seperate with comma (defaults to "js,jsx")
    -g, --git [value]     your git directory, where your .git exist (defaults to ".")
    -h, --help            Output usage information
    -v, --version         Output the version number
```

## API

### EslintGitStaged(eslintrcPath, gitPath, extension)

- eslintrcPath: path to your eslintrc file
- gitPath: path to your `.git`
- extension `string | string[]`: which kind of extensions do you want to lint with eslint.

## Usage

```js
// EslintGitStaged(<eslintrc path>, <git repository path>, <extension default 'js'>)
new EslintGitStaged(resolve(__dirname, "./.eslintrc.js"), resolve(__dirname, "../"), ".js").start()
      .then((result) => {
        // success no lint error, done lint
      })
      .catch((err) => {
        // err, when lint failed
      });
```

## Tslint users

- https://github.com/Canner/tslint-gitstaged

## License

MIT
