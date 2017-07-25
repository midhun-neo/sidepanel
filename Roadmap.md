Currently the main focus of the team is to release the first stable, 1.0.0 version of this library. We are _very_ close: all the core components are implemented, APIs are largely "frozen" and there are very few bugs remaining. 

# Towards 1.0.0

Estimating software release dates is hard so instead here is a list of remaining work before a stable 1.0.0 release can be cut:

* `alpha.x` - we are going to continue work on alpha releases (bug fixes and features) waiting for [Bootstrap 4 going beta](https://github.com/twbs/bootstrap/milestone/41). As soon as Bootstrap 4 goes beta we are going to update this library and will be ready to cut first beta of ng-bootstrap.
* `beta.0` - will be released when base functionality for all the core components is ready _and_ Bootstrap 4 released its first beta. You can track progress towards beta.0 in the [dedicated milestone](https://github.com/ng-bootstrap/ng-bootstrap/milestone/32)
* `beta.1-x` - subsequent betas will contain bug-fixes and smaller features with no or minimal breaking changes;
* `rc.0` - to be released when the library is stable (no bugs reported for common scenarios - we still might have bugs for corner cases)
* `1.0.0` - no critical bugs / regressions reported for rc(s)

# Post 1.0.0

Starting from 1.0 we are going to use [semantic versioning](http://semver.org/) to flag / track releases. We will also consider aligning major releases of this library with the Angular release cycles so it is crystal-clear which version of ng-bootstrap should be used with a particular version of Angular.

It is hard to provide detailed post-1.0.0 plan at this point but here are the main areas of work for the upcoming major versions:
* Continued support / bug fixing for the existing widgets
* Animations
* More features for the existing widgets
* Customisations (adding more flexibility / extension points to the existing widgets)
* More non-core widgets (ex. select2)