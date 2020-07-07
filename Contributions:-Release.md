# Release

## Major x.0.0
* [ ] make sure all deprecations to be removed in `x.0.0` are removed
* [ ] check that schematics generate use correct Angular, Bootstrap and ng-bootstrap versions

## Minor x.x.0
* [ ] go through `feat` commits and update new feature comments with `@since x.x.0` and deprecated ones with `@deprecated x.x.0 Explanation why here`
* [ ] for each new API field check if `static ngAcceptInputType_XXX: XXX;` needs to be added
* [ ] commit documentation changes

## Version X.X.X + publish

* [ ] make sure you're on the `master` branch and you're ready to release
* [ ] generate the new release (`yarn version`). This will generate a tagged release commit with changelog updates, build the library and the demo site.
* [ ] check the `CHANGELOG.md` in the last commit. If necessary update the file and run `yarn:changelog-patch` to amend changelog and update the git release tag.
* [ ] push to npm (`cd dist/ng-bootstrap`, `npm publish`, `cd ../..`). There is no way of NOT rewriting the `latest` tag in npm, so when publishing OLDER releases, you have to manually restore the `latest` tag with `npm dist-tags add @ng-bootstrap/ng-bootstrap@Z.Z.Z latest`
* [ ] push `master` to GitHub (`git push upstream`)
* [ ] push tags to GitHub (`git push upstream --tags`)
* [ ] push the demo site (`yarn demo:publish`)
* [ ] close the release [milestone](https://github.com/ng-bootstrap/ng-bootstrap/milestones)
* [ ] let the World know!