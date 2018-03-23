# Release

## Major x.0.0
// TODO

## Minor x.x.0
* [ ] go through `feat` commits and update new feature comments with `@since x.x.0` and deprecated ones with `@deprecated x.x.0 Explanation why here`
* [ ] commit documentation changes

## Version + publish
* [ ] bump up version in `package.json`
* [ ] generate and edit changelog (`gulp changelog`)
* [ ] commit `package.json` and changelog update with `chore: release [version]`
* [ ] tag a release (ex.: `git tag 1.0.0-alpha.1`)
* [ ] push master to GitHub (`git push upstream`)
* [ ] push tags to GitHub (`git push upstream --tags`)
* [ ] generate release (`gulp build`) and push to npm (`cd dist`, `npm publish`, `cd ..`)
* [ ] generate (`gulp build:demo`) and push (`gulp demo-push`) demo site 
* [ ] close a release [milestone](https://github.com/ng-bootstrap/ng-bootstrap/milestones)
* [ ] update [roadmap](https://github.com/ng-bootstrap/ng-bootstrap/wiki/Roadmap)
* [ ] let the World know!