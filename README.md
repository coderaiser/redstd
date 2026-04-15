# redstd [![License][LicenseIMGURL]][LicenseURL] [![NPM version][NPMIMGURL]][NPMURL] [![Build Status][BuildStatusIMGURL]][BuildStatusURL] [![Coverage Status][CoverageIMGURL]][CoverageURL]

![image](https://user-images.githubusercontent.com/1573141/223524904-4175548f-1e30-4745-bf2e-c2f4ea39fef5.png)

[NPMURL]: https://npmjs.org/package/read-stdin "npm"
[NPMIMGURL]: https://img.shields.io/npm/v/read-stdin.svg?style=flat
[BuildStatusURL]: https://github.com/coderaiser/read-stdin/actions?query=workflow%3A%22Node+CI%22 "Build Status"
[BuildStatusIMGURL]: https://github.com/coderaiser/read-stdin/workflows/Node%20CI/badge.svg
[LicenseURL]: https://tldrlegal.com/license/mit-license "MIT License"
[LicenseIMGURL]: https://img.shields.io/badge/license-MIT-317BF9.svg?style=flat
[CoverageURL]: https://coveralls.io/github/coderaiser/read-stdin?branch=master
[CoverageIMGURL]: https://coveralls.io/repos/coderaiser/read-stdin/badge.svg?branch=master&service=github

Read `stdin` to have ability to use pipes like: `cat README.md | less` or

```sh
cat README.md | node -e "const {readStdin} = await import('redstd'); console.log(await readStdin())"
```

When you pass nothing to stdin - everything just works, so you can read from stdout or from file

## Install

```
npm i redstd
```

# Usage

```js
import {readFile} from 'node:fs/promises';
const {readStdin} = await import('redstd'); 
const input = await readStdin();

if (!input) {
    console.log(await readFile('./README.md'));
    process.exit();
}

console.log(input);
```

## License

MIT
