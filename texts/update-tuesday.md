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
3. Open the project in VSCode with `code .`
4. From Run-menu (CTRL + SHIFT + D by default) select and run extension tests.
5. You can also run the extension in debug mode from that same menu and try to download/run tests for an exercise to see if anything broke.

Currently held back packages:
* eslint@6.8.0 - waiting for @typescript-eslint/eslint-plugin

### Python editor

Update by doing the following:
1. Run `npx npm-check --update` in the repository's root directory.
2. Select all dependencies that aren't currently held back (see list below). It might be wise to update one at a time and test to see if anything breaks.
3. Run `npm run encode:worker` in the project root folder.
4. Go to the example-directory and run `npm start`
5. In a separate terminal go to the same directory and run `npm run cypress:open` to run E2E-tests.


### Material template

Update by doing the following:
1. Run `npx npm-check --update` in the repository's root directory.
2. Select all dependencies that aren't currently held back (see list below). It might be wise to update one at a time and test to see if anything breaks.
3. If something breaks, determine whether to hold back or fix some other way.

Currently held back packages:
* react-ace@4.4.0
* react-codemirror@1.0.0

react-ace and react-codemirror are dependencies of Code States Visualizer, which doesn't support newer versions. These can be updated after Code States Visualizer is updated to support newer versions.

### Quizzes Backend/ Quizzes Dashboard/ Quizzes Widget

Update by doing the following:
1. Run `yarn upgrade-interactive --latest` in the repository's root directory.
2. Select packages to update interactively or skip to update all - select ones that aren't currently held back (see list below). It might be wise to update one at a time and test to see if anything breaks.
3. If something breaks, determine whether to hold back or fix some other way.

Currently held back packages:

**Backend**:

**Dashboard**:

**Widget**:



