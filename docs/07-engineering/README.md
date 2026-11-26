# Engineering

How to work in this repository. Toolchain facts below come from the build. Code style, package rules, and test naming become living pages in this folder when they are agreed.

## Layout

```text
src/main/java/com/huylq/identityservice/   application code
src/main/resources/                       configuration and, later, Flyway migrations
src/test/java/                            tests
docs/                                     this documentation
```

Package root: `com.huylq.identityservice`.

Spring Modulith is on the classpath. Module packages wait for an accepted architecture page and the decision that chose them. See [architecture](../04-architecture/README.md).

## Build

```text
./gradlew test
./gradlew bootRun
```

`test` is the check the repository supports today. A supported local run is written up as `local-setup.md` in this folder once it works. The build expects a database and security configuration this tree does not contain yet.

## Tests

`IdentityServiceApplicationTests.contextLoads` loads the application context.

Add further tests with the slice they cover. Put the requirement or design path in the tracked document's `code` field so the [traceability table](../09-quality/traceability.md) can find the proof.

## Secrets

Local and secret configuration stays out of git. The file names are listed in [operations](../08-operations/README.md).

`HELP.md` is Spring Initializr output, gitignored, and not maintained.
