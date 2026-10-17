# Contributing to Wunderlab

Thanks for helping out. Wunderlab is built from several repositories, so here is where things go.

## Where to file things

- **Bugs and feature requests:** open an issue in [wunderlab-ai/wunderlab](https://github.com/wunderlab-ai/wunderlab/issues) and label it with the module it concerns. Module repositories point back here.
- **Code changes:** open a pull request in the repository that owns the code. If a module lives in its own repository (for example `engine-cuda` or `roles`), the pull request goes there. Everything else goes to the main repository.
- **Security problems:** see [SECURITY.md](SECURITY.md). Don't open a public issue.

## Setting up

```bash
git config --global submodule.recurse true
git clone --recurse-submodules https://github.com/wunderlab-ai/wunderlab
```

Build and test instructions for each part live in its folder's README.

## Changing a submodule

Submodules start on a detached HEAD, and the order of operations matters:

1. `cd` into the module, switch to `main`, make and commit your change, and push **the module** first.
2. Back in the main repository, `git add` the module path and commit the pointer bump, then push.

Setting `git config --global push.recurseSubmodules check` stops you from pushing a pointer to a commit that doesn't exist upstream.

## Pull requests

- Keep each pull request focused on one change, and explain why it's needed.
- Add or update tests. Scheduler, sandbox, and environment changes need tests for the failure paths (timeouts, cancellation, kills), not just the happy path.
- Match the existing style: `clang-format` for C++, Pint for PHP, Prettier and ESLint for TypeScript. CI checks all of these.
- Sign off your commits (`git commit -s`) to certify the [Developer Certificate of Origin](https://developercertificate.org).
- By contributing, you agree that your work is licensed under the license of the repository you contribute to.

## Contributing roles and presets

Agent roles, curator instructions, and network presets live in the `roles` repository as plain data, so you don't need a C++ toolchain to improve them. Include benchmark results from `bench` when you change a role's behavior.

## Be kind

Be respectful and constructive. Assume good faith, and focus on the work.
