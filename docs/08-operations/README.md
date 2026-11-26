# Operations

Configuration, environments, and recovery. There is no deployment yet.

The shape of a deployment (one process, which datastore) is an [architecture](../04-architecture/README.md) page. The steps to ship it will be `deployment.md` in this folder, written when an environment exists.

## Configuration today

`src/main/resources/application.yaml` sets the application name and nothing else.

When real keys exist, add `configuration.md` here. For each key record the meaning, the default, and whether the value is secret. Secret values stay out of git and out of docs.

## Secrets

`.gitignore` already excludes local and secret configuration:

- `.env` and `.env.*`, except `.env.example`
- `application-local.yaml`, `application-local.yml`, `application-local.properties`
- `application-secret.yaml`, `application-secret.yml`, `application-secret.properties`
- those same names under `src/main/resources/`

`.env.example` may list variable names with fake values. It is the file other people copy.

## Runbooks

Recovery steps for a real failure live in [runbooks](runbooks/README.md). Write a runbook when the failure mode exists, rather than for an outage that has not happened.
