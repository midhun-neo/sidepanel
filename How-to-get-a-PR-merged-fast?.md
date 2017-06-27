# How to get a PR merged fast?

At ng-bootstrap we love contributions and really appreciate all the work put into preparing pull requests. We want to get in all the quality contributions as soon as possible and to integrate your work. At the same time we can't guarantee that all the PRs will be merged. It is also hard to estimate time needed to review / merge a PR. 

Then again, we want your contribution to be integrated as soon as possible so here are the tips for getting in your PR _fast_. 

## General rules

Please try to keep your PR as small as possible (like _really_ small). You can do the following to avoid big diffs that makes PRs hard to review and integrate:
* send a separate PRs for separate changes (example: don't mix bug fixes with refactoring or typo fixes; have just one bug fix / feature in a PR);
* preserve the existing formatting so diff doesn't contain formatting changes. Don't add / remove blank lines. You can run  `gulp check-format` to check / enforce code formatting. 

After sending a PR please verify that the TravisCI build is all green (we are performing many automatic checks on each diff, including tests and code formatting). 

## Bug fix PRs

If your PR fixes an issue, it should contain at least one unit test that reproduces the error. Then the minimum code needed to fix the bug. 

## New features

Do you have a cool feature in mind? Before you attempt to implement it, we ask you to create a new issue where you describe your new feature and why do you think it would be a good addition to the library.

If your idea is approved, here is your check list of needed steps for the PR:

* Unit tests
* The feature code
* Documentation for the new features
* Optionally a demo app for the docs (if it makes sense)

Please, don't open a PR for features without discussing those first. We don't want to waste your time.

## Documentation typos

This are the easy ones, just open a PR and it will probably be merged right away!

## Documentation demo

Do you feel like there is a missing key demo on the documentation? If so, please open an issue so we can discuss it.

If we feel the same thing, your PR with the demo will be merged super fast.

---

Having this in mind, if a PR follow this steps, it will be merged quite fast!