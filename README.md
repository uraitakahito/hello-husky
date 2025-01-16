This is a repository to try out [husky](https://github.com/typicode/husky).

## Git Hooks

Individual Git hooks are scripts, and hooks targeting a specific repository are grouped in the `.git/hooks` directory.
Git does not copy hooks between repositories. Even if you run git clone or git fetch targeting another repository, the hooks of that repository are not inherited. Hook scripts must be copied manually.

By adding the `--no-verify` option to the git command, you can disable hooks.

```console
% git commit --no-verify
% git push --no-verify
```

## Husky

### What does `husky init` initialize?

[bin.js](https://github.com/typicode/husky/blob/0692639896ea5b5dd5ffc607575f6f870b21cb0f/bin.js) is called.

[index.js](https://github.com/typicode/husky/blob/0692639896ea5b5dd5ffc607575f6f870b21cb0f/index.js) is imported.

`husky` is [registered](https://github.com/typicode/husky/blob/0692639896ea5b5dd5ffc607575f6f870b21cb0f/bin.js#L14) in `scripts.prepare` of `package.json`.

`core.hooksPath` of `.git/config` is set ([where it is called](https://github.com/typicode/husky/blob/0692639896ea5b5dd5ffc607575f6f870b21cb0f/bin.js#L16) and [the function implementation](https://github.com/typicode/husky/blob/0692639896ea5b5dd5ffc607575f6f870b21cb0f/index.js#L14)).

The `h` script is [copied](https://github.com/typicode/husky/blob/0692639896ea5b5dd5ffc607575f6f870b21cb0f/index.js#L21) to `.husky/_`.

Various hooks are [copied](https://github.com/typicode/husky/blob/0692639896ea5b5dd5ffc607575f6f870b21cb0f/index.js#L22) to `.husky/_`.

`husky.sh` is [copied](https://github.com/typicode/husky/blob/0692639896ea5b5dd5ffc607575f6f870b21cb0f/index.js#L23) to `.husky/_`.
