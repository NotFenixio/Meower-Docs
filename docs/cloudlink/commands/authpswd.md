---
slug: /cloudlink/commands/authpswd
sidebar_label: authpswd
---

# `authpswd`

This command is used to log into the Meower CloudLink server.

:::warning
Although this can be used to get a token, a new and more efficient way has been developed, using a single HTTP request. Head over to the [Authentication section](/rest-api/intro/authentication) to check it.
:::

## Request

<!-- prettier-ignore-start -->
| Field | Type | Description |
| - | - | - |
| username | string | The username of the account to log into. This has to be between 1 and 20 characters. |
| pswd | string | The password or a token of the account to log into. This has to be between 1 and 255 characters. |
<!-- prettier-ignore-end -->

## Response

<!-- prettier-ignore-start -->
| Status code | Description |
| - | - |
| I:011 \| Invalid Password | If the password of the account was invalid. |
| I:100 \| OK | If the log in attempt was succesful. This also sends an `auth` packet. |
| E:018 \| Account Banned | If the account was banned. |
| E:025 \| Deleted | If the account was deleted and can't be logged into. |
| E:101 \| Syntax | If either `username` or `pswd` aren't included in the packet, or the length limits for them aren't met. |
| E:102 \| Datatype | If the provided `val` is not an object, or if the `username` or `pswd` aren't strings. |
| E:103 \| ID not found | If the given user does not exist. |
<!-- prettier-ignore-end -->
