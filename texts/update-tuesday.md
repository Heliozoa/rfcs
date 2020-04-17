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
* Material template (ohjelmointi-20)

### Material template

Update by doing the following:
1. Run `npx npm-check --update` in the repository's root directory.
2. Select all dependencies that aren't currently held back (see list below). It might be wise to update one at a time and test to see if anything breaks.
3. If something breaks, determine whether to hold back or fix some other way.

Currently held back packages:
* react-ace@4.4.0
* react-codemirror@1.0.0

react-ace and react-codemirror are dependencies of Code States Visualizer, which doesn't support newer versions. These can be updated after Code States Visualizer is updated to support newer versions.
