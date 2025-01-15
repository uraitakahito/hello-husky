This is a repository to try out [husky](https://github.com/typicode/husky).

## Notes

Individual Git hooks are scripts, and hooks targeting a specific repository are grouped in the .git/hooks directory.
Git does not copy hooks between repositories. Even if you run git clone or git fetch targeting another repository, the hooks of that repository are not inherited. Hook scripts must be copied manually.
