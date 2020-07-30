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



