---
id: CLI
title: CLI commands
sidebar_label: CLI commands
---

## Commands list

* [`help`](CLI.md#help)
* [`exit`](CLI.md#exit)
* [`login`](CLI.md#login)
* [`register`](CLI.md#register)
* [`whoami`](CLI.md#whoami)
* [`applist`](CLI.md#applist)
* [`createapp`](CLI.md#createapp)
* [`appinfo`](CLI.md#appinfo)
* [`removeapp`](CLI.md#removeapp)
* [`logout`](CLI.md#logout)

## Reference

### `help`

| Options                    | Default | Description                                                                                                           |
| ------------------------ | ------- | --------------------------------------------------------------------------------------------------------------------- |
| `command name`             | `none` | Promts the usage of command. |

Promts the usage of command.If command is not specified promts the usage of cli.

### `exit`

Alias: `quit`

| Options                    | Default | Description                                                                                                           |
| ------------------------ | ------- | --------------------------------------------------------------------------------------------------------------------- |
| `--help`             | `none` | Promts the usage of command. |

Exits application.

### `login`

| Options                    | Default | Description                                                                                                           |
| ------------------------ | ------- | --------------------------------------------------------------------------------------------------------------------- |
| `--help`             | `none` | Promts the usage of command. |

Promts to enter username and password. Loggs into the account if it exists

### `register`

| Options                    | Default | Description                                                                                                           |
| ------------------------ | ------- | --------------------------------------------------------------------------------------------------------------------- |
| `--help`             | `none` | Promts the usage of command. |

Promts to enter username, password and email.Registers the account.

### `whoami`

| Options                    | Default | Description                                                                                                           |
| ------------------------ | ------- | --------------------------------------------------------------------------------------------------------------------- |
| `--help`             | `none` | Promts the usage of command. |

Prints info about current logged in user.

### `applist`

| Options                    | Default | Description                                                                                                           |
| ------------------------ | ------- | --------------------------------------------------------------------------------------------------------------------- |
| `--help`             | `none` | Promts the usage of command. |

List all apps of current logged in user.

### `createapp`

| Options                    | Default | Description                                                                                                           |
| ------------------------ | ------- | --------------------------------------------------------------------------------------------------------------------- |
| `--help`             | `none` | Promts the usage of command. |

Promts to enter an app name to create it.

### `appinfo`

| Options                    | Default | Description                                                                                                           |
| ------------------------ | ------- | --------------------------------------------------------------------------------------------------------------------- |
| `--help`             | `none` | Promts the usage of command. |

Promts to enter the app name and prints app info.

### `removeapp`

| Options                    | Default | Description                                                                                                           |
| ------------------------ | ------- | --------------------------------------------------------------------------------------------------------------------- |
| `--help`             | `none` | Promts the usage of command. |

Promts to enter the app name to remove it.

### `logout`

| Options                    | Default | Description                                                                                                           |
| ------------------------ | ------- | --------------------------------------------------------------------------------------------------------------------- |
| `--help`             | `none` | Promts the usage of command. |

Promts message about successful logout