---
layout: post
title: Armory Halyard
order: 20
---
{:.no_toc}
* This is a placeholder for an unordered list that will be replaced with ToC. To exclude a header, add {:.no_toc} after it.
{:toc}

## hal

A tool for configuring, installing, and updating Spinnaker.

If this is your first time using Halyard to install Spinnaker we recommend that you skim the documentation on www.spinnaker.io/docs for some familiarity with the product. If at any point you get stuck using 'hal', every command can be suffixed with '--help' for usage information.


#### Usage
```
hal [parameters] [subcommands]
```
#### Global Parameters
 * `--daemon-endpoint`: If supplied, connect to the daemon at this address.
 * `--options`: Get options for the specified field name.
 * `-a, --alpha`: Enable alpha halyard features.
 * `-c, --color`: Enable terminal color output.
 * `-d, --debug`: Show detailed network traffic with halyard daemon.
 * `-h, --help`: (*Default*: `false`) Display help text about this command.
 * `-l, --log`: Set the log level of the CLI.
 * `-o, --output`: Format the CLIs output.
 * `-q, --quiet`: Show no task information or messages. When set, ANSI formatting will be disabled, and all prompts will be accepted.

#### Parameters
 * `--docs`: (*Default*: `false`) Print markdown docs for the hal CLI.
 * `--print-bash-completion`: (*Default*: `false`) Print bash command completion. This is used during the installation of Halyard.
 * `--ready`: (*Default*: `false`) Check if Halyard is up and running. Will exit with non-zero return code when it isn't.
 * `--version, -v`: (*Default*: `false`) Version of Halyard.

#### Subcommands
 * `armory`: Armory-specific commands are described here.

---
## hal armory

Armory-specific commands are described here.

#### Usage
```
hal armory [subcommands]
```

#### Subcommands
 * `diagnostics`: Configure diagnostics reporting
 * `dinghy`: Configure Dinghy pipelines as code
 * `secrets`: Configure secrets management
 * `init`: Runs Armory installer

---
## hal armory diagnostics

Configure diagnostics reporting

#### Usage
```
hal armory diagnostics [parameters] [subcommands]
```

#### Parameters
 * `--deployment`: If supplied, use this Halyard deployment. This will _not_ create a new deployment.
 * `--no-validate`: (*Default*: `false`) Skip validation.

#### Subcommands
 * `disable`: Disable diagnostics
 * `edit`: Edit diagnostics settings
 * `enable`: Enable diagnostics

---
## hal armory diagnostics disable

Disable diagnostics

#### Usage
```
hal armory diagnostics disable [parameters]
```

#### Parameters
 * `--deployment`: If supplied, use this Halyard deployment. This will _not_ create a new deployment.
 * `--no-validate`: (*Default*: `false`) Skip validation.


---
## hal armory diagnostics edit

Edit diagnostics settings

#### Usage
```
hal armory diagnostics edit [parameters]
```

#### Parameters
 * `--deployment`: If supplied, use this Halyard deployment. This will _not_ create a new deployment.
 * `--no-validate`: (*Default*: `false`) Skip validation.
 * `--uuid`: (*Required*) UUID of the Armory installation


---
## hal armory diagnostics enable

Enable diagnostics

#### Usage
```
hal armory diagnostics enable [parameters]
```

#### Parameters
 * `--deployment`: If supplied, use this Halyard deployment. This will _not_ create a new deployment.
 * `--no-validate`: (*Default*: `false`) Skip validation.


---
## hal armory dinghy

Configure Dinghy pipelines as code

#### Usage
```
hal armory dinghy [parameters] [subcommands]
```

#### Parameters
 * `--deployment`: If supplied, use this Halyard deployment. This will _not_ create a new deployment.
 * `--no-validate`: (*Default*: `false`) Skip validation.

#### Subcommands
 * `disable`: Disable Dinghy
 * `edit`: Edit Dinghy settings
 * `enable`: Enable Dinghy
 * `slack`: Configure Slack notifications (Halyard >= 1.6.3)

---
## hal armory dinghy disable

Disable Dinghy

#### Usage
```
hal armory dinghy disable [parameters]
```

#### Parameters
 * `--deployment`: If supplied, use this Halyard deployment. This will _not_ create a new deployment.
 * `--no-validate`: (*Default*: `false`) Skip validation.


---
## hal armory dinghy edit

Edit Dinghy settings

#### Usage
```
hal armory dinghy edit [parameters]
```

#### Parameters
 * `--autolock-pipelines`: (*Default*: `true`) Lock pipelines in the UI before overwriting on change.
 * `--deployment`: If supplied, use this Halyard deployment. This will _not_ create a new deployment.
 * `--dinghyfile-name`: (*Default*: `dinghyfile`) Name of the file in application repositories which contains pipelines
 * `--fiat-user`: Fiat user to use for Dinghy operations.
 * `--github-endpoint`: (*Default*: `https://api.github.com`) Github API endpoint. Useful if you're using Github Enterprise.
 * `--github-token`: (*Sensitive data* - user will be prompted on standard input) GitHub token.
 * `--no-validate`: (*Default*: `false`) Skip validation.
 * `--stash-endpoint`: Stash API endpoint.
 * `--stash-token`: (*Sensitive data* - user will be prompted on standard input) Stash token.
 * `--stash-username`: Stash username.
 * `--template-org`: (*Required*) SCM organization or namespace where application and template repositories are located.
 * `--template-repo`: (*Required*) SCM repository where module templates are located.


---
## hal armory dinghy enable

Enable Dinghy

#### Usage
```
hal armory dinghy enable [parameters]
```

#### Parameters
 * `--deployment`: If supplied, use this Halyard deployment. This will _not_ create a new deployment.
 * `--no-validate`: (*Default*: `false`) Skip validation.

---
## hal armory dinghy slack

Configure Dinghy to send processing results to a Slack channel  (Halyard >= 1.6.3)

#### Usage
```
hal armory dinghy slack [enable|disable]
```

#### Parameters
 * `--deployment`: If supplied, use this Halyard deployment. This will _not_ create a new deployment.
 * `--no-validate`: (*Default*: `false`) Skip validation.

#### Subcommands
 * `enable`: Enable Slack notifications/edit Slack channel
 * `disable`: Disable Slack notifications

---
## hal armory dinghy slack enable

Enable Slack notifications from Dinghy (Halyard >= 1.6.3)

#### Usage
```
hal armory dinghy slack enable [parameters]
```

#### Parameters
 * `--channel`: If supplied, sets the channel notifications will be sent to.
 * `--deployment`: If supplied, use this Halyard deployment. This will _not_ create a new deployment.
 * `--no-validate`: (*Default*: `false`) Skip validation.

---
## hal armory dinghy slack disable

Disable Slack notifications from Dinghy (Halyard >= 1.6.3)

#### Usage
```
hal armory dinghy slack disable [parameters]
```

#### Parameters
 * `--deployment`: If supplied, use this Halyard deployment. This will _not_ create a new deployment.
 * `--no-validate`: (*Default*: `false`) Skip validation.

---
## hal armory init

Runs Armory installer

#### Usage
```
hal armory init [parameters]
```

#### Parameters
 * `--allow-small`: Passed to armory-install. Don't stop installation if cluster does not have enough resources
 * `--deployment`: If supplied, use this Halyard deployment. This will _not_ create a new deployment.
 * `--edge`: Passed to armory-install. Set if you want to run on the latest version
 * `--no-diagnostics`: Turns off all diagnostics
 * `--no-validate`: (*Default*: `false`) Skip validation.
 * `--path`: The path to where armory-install is already installed


## hal armory secrets 

Configure secrets management

#### Usage
```
hal armory secrets [subcommands] [parameters]
```

#### Parameters
 * `--deployment`: If supplied, use this Halyard deployment. This will _not_ create a new deployment.
 * `--no-validate`: (*Default*: `false`) Skip validation.

#### Subcommands
 * `vault`: Configure secrets management with Vault

---
## hal armory secrets vault

Configure settings for secrets management with Vault in the Spinnaker services. [See our documentation for configuring Halyard itself to use Vault](https://docs.armory.io/spinnaker-install-admin-guides/secrets-vault/#configuring-halyard-to-use-vault-secrets).

#### Usage
```
hal armory secrets vault [subcommands] [parameters]
```

#### Parameters
 * `--deployment`: If supplied, use this Halyard deployment. This will _not_ create a new deployment.
 * `--no-validate`: (*Default*: `false`) Skip validation.

#### Subcommands
 * `disable`: Disable secret engine
 * `edit`: Edit secrets settings
 * `enable`: Enable secret engine

---
## hal armory secrets vault disable

Disable Vault secret engine

#### Usage
```
hal armory secrets vault disable [parameters]
```

#### Parameters
 * `--deployment`: If supplied, use this Halyard deployment. This will _not_ create a new deployment.
 * `--no-validate`: (*Default*: `false`) Skip validation.

---
## hal armory secrets vault edit

Edit Vault secret engine settings

#### Usage
```
hal armory secrets vault edit [parameters]
```

#### Parameters
 * `--auth-method`: (*Required*) Method used to authenticate with the Vault endpoint. Must be either `KUBERNETES` for [Kubernetes service account auth](https://www.vaultproject.io/docs/auth/kubernetes.html) or `TOKEN` for [Vault token auth](https://www.vaultproject.io/docs/auth/token.html). The `TOKEN` method will require a `VAULT_TOKEN` environment variable set [for Halyard and the services](https://docs.armory.io/spinnaker-install-admin-guides/secrets-vault/#2-token-authentication).
 * `--deployment`: If supplied, use this Halyard deployment. This will _not_ create a new deployment.
 * `--no-validate`: (*Default*: `false`) Skip validation.
 * `--path`: (*Default*: `kubernetes`) (Applies to `KUBERNETES` [authentication method](https://www.vaultproject.io/docs/auth/kubernetes.html)) Path of the kubernetes authentication backend mount.
 * `--role`: (Applies to `KUBERNETES` [authentication method](https://www.vaultproject.io/docs/auth/kubernetes.html)) Name of the role against which the login is being attempted.
 * `--url`: (*Required*) URL of the Vault endpoint from Spinnaker services.


---
## hal armory secrets vault enable

Enable Vault secret engine

#### Usage
```
hal armory secrets vault enable [parameters]
```

#### Parameters
 * `--deployment`: If supplied, use this Halyard deployment. This will _not_ create a new deployment.
 * `--no-validate`: (*Default*: `false`) Skip validation.




