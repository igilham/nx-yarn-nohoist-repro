# Reproduction for an issue with Nx and nohoist

This is to demonstrate an issue encountered when using Nx with Yarn Workspaces and an aggressive `nohoist` configuration.

To demonstrate the problem, install the dependencies then try any common nx build command.

```shell
yarn --frozen-lockfile
yarn nx run-many --target=build
```

In this scenario Nx does not execute most commands because the way it classifies whether it is running globally or locally cannot currently account for the different paths in use when the dependencies have been arranged with `nohoist`.

Installing Nx globally does not seem to help.
