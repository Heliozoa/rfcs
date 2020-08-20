# Summary
[summary]: #summary

On the second tuesday of every month, we will systematically update all of the dependencies on the projects that are in production use.

# Description
[description]: #description

The projects that are in this update program are listed below:

* MOOC.fi frontend
* MOOC.fi backend
* Quizzes dashboard
* Quizzes backend
* Quizzes widget
* Elements of AI material
* Visual Studio Code
* Python editor
* Material template (ohjelmointi-20)
* Certificates
* java-programming
* likert-react
* tmc-langs-rust

### Visual Studio Code

Update by doing the following:
1. Run `npx npm-check --update` in the repository's root directory.
2. Select all dependencies that aren't currently held back (see list below). It might be wise to update one at a time and test to see if anything breaks.
3. Make sure that updates didn't break anything by doing the following:
   * Close VSCode before running tests (recommended).
   * In backend directory, run `npm run setup` and `npm start` to start the testing backend.
   * In root folder, run test suites with `npm test` and `npm run ui-test`
4. Consider [publishing a new release](https://github.com/rage/tmc-vscode/blob/master/docs/publish.md)

Currently held back packages:
* `@types/vscode@1.40.0` - Needs to match the plugin's lowest supported VSCode version.

### Python editor

Update by doing the following:
1. Run `npx npm-check --update` in the repository's root directory.
2. Select all dependencies that aren't currently held back (see list below). It might be wise to update one at a time and test to see if anything breaks.
3. Run `npm run encode:worker` in the project root folder.
4. Go to the example-directory and run `npm start`
5. In a separate terminal go to the same directory and run `npm run cypress:open` to run E2E-tests.
6. Update the version number accordingly in `package.json`, `package-lock.json` and `src/constants/index.ts`
7. Login to npm with `npm login` and publish a new version with `npm publish`

### Material template

Update by doing the following:
1. Run `npx npm-check --update` in the repository's root directory.
2. Select all dependencies that aren't currently held back (see list below). It might be wise to update one at a time and test to see if anything breaks.
3. If something breaks, determine whether to hold back or fix some other way.

Currently held back packages:
* typesafe-actions@4.4.2 - waiting for @moocfi-quizzes to update typesafe-actions
* graphql@14.6.0 - waiting for [gatsby-recipes](https://github.com/gatsbyjs/gatsby/blob/master/packages/gatsby-recipes/package.json) to update dependency
* likert-react - latest version is 0.0.0-beta6

### Quizzes Backend/ Quizzes Dashboard/ Quizzes Widget

Update by doing the following in each package directory:
1. Run `npm outdated` to list outdated dependencies.
2. Run `npm install package-name@latest` to update dependency - select ones that aren't currently held back (see list below). It might be wise to update one at a time and test to see if anything breaks.
3. If something breaks, determine whether to hold back or fix some other way.

Currently held back packages:

**Backend**:

routing-controllers
typeorm

**Dashboard**:

typesafe-actions

**Widget**:

typesafe-actions

### tmc-langs-rust
Outdated Rust dependencies can be checked using [cargo-outdated](https://crates.io/crates/cargo-outdated).

1. If not installed yet, install cargo-outdated with `cargo install cargo-outdated`.
2. Call `cargo outdated -R` in the project root.
3. Update the listed dependencies in the appropriate Cargo.toml files.

Example output:
```
tmc-langs-core
================
Name      Project  Compat  Latest  Kind    Platform
----      -------  ------  ------  ----    --------
tempfile  2.2.0    ---     3.1.0   Normal  ---

tmc-langs-python3
================
Name     Project  Compat  Latest  Kind    Platform
----     -------  ------  ------  ----    --------
log      0.3.9    ---     0.4.11  Normal  ---
```
In this case, tmc-langs-core/Cargo.toml's `tempfile = "2"` should be updated to `tempfile = "3"` and plugins/python3/Cargo.toml's `log = "0.3"` should be updated to `log = "0.4"`.

**NOTE**: Updating the Java plugin's dependency on j4rs requires more care, because updating it also requires updating the bundled j4rs JAR to the same version. This is also why j4rs's version is specified down to the minor version, unlike with other dependencies.
