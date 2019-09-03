# Release

## Major x.0.0
* [ ] make sure all deprecations to be removed in `x.0.0` are removed

## Minor x.x.0
* [ ] go through `feat` commits and update new feature comments with `@since x.x.0` and deprecated ones with `@deprecated x.x.0 Explanation why here`
* [ ] commit documentation changes

## Version X.X.X + publish

* [ ] bump up version to `X.X.X` in `package.json` and in `src/package.json`
* [ ] generate and edit changelog (`yarn changelog`)
* [ ] commit both `package.json` files and changelog updates with `chore: release X.X.X`
* [ ] tag a release (ex.: `git tag X.X.X`)
* [ ] generate release (`yarn ngb:build`)
* [ ] push to npm (`cd dist/ng-bootstrap`, `npm publish`, `cd ../..`). To avoid rewriting `latest` tag in npm, use `npm publish --tag X.X.X` for older patches (to be confirmed...)
* [ ] push master to GitHub (`git push upstream`)
* [ ] push tags to GitHub (`git push upstream --tags`)
* [ ] generate (`yarn demo:build`) and push (`yarn demo:publish`) demo site 
* [ ] close a release [milestone](https://github.com/ng-bootstrap/ng-bootstrap/milestones)
* [ ] update [roadmap](https://github.com/ng-bootstrap/ng-bootstrap/wiki/Roadmap)
* [ ] let the World know!