# Release

## Major x.0.0
* [ ] make sure all deprecations to be removed in `x.0.0` are removed

## Minor x.x.0
* [ ] go through `feat` commits and update new feature comments with `@since x.x.0` and deprecated ones with `@deprecated x.x.0 Explanation why here`
* [ ] for each new API field check if `static ngAcceptInputType_XXX: XXX;` needs to be added
* [ ] commit documentation changes

## Version X.X.X + publish

* [ ] make sure you're on the `master` branch
* [ ] bump up version to `X.X.X` in `package.json` and in `src/package.json`
* [ ] generate and edit changelog (`yarn changelog`)
* [ ] commit both `package.json` files and changelog updates with `docs: release X.X.X`
* [ ] tag a release (`git tag X.X.X`)
* [ ] build a release (`yarn ngb:build`)
* [ ] push to npm (`cd dist/ng-bootstrap`, `npm publish`, `cd ../..`). There is no way of NOT rewriting the `latest` tag in npm, so when publishing OLDER releases, you have to manually restore the `latest` tag with `npm dist-tags add @ng-bootstrap/ng-bootstrap@Z.Z.Z latest`
* [ ] push `master` to GitHub (`git push upstream`)
* [ ] push tags to GitHub (`git push upstream --tags`)
* [ ] run `yarn demo` and check StackBlitzes work with the just published `ng-bootstrap` version (ex. see [#3460](https://github.com/ng-bootstrap/ng-bootstrap/issues/3460))
* [ ] build (`yarn demo:build`) and push (`yarn demo:publish`) demo site
* [ ] close a release [milestone](https://github.com/ng-bootstrap/ng-bootstrap/milestones)
* [ ] let the World know!