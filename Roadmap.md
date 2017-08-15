Currently the main focus of the team is to release the first stable, 1.0.0 version of this library. We are _very_ close: all the core components are implemented, APIs are largely "frozen" and there are very few bugs remaining. 

# Towards 1.0.0

Estimating software release dates is hard so instead here is a list of remaining work before a stable 1.0.0 release can be cut:

* `beta.1` - since Bootstrap 4 released its first beta, we did so as well and now are officially out of the alpha cycle!
* `beta.2-x` - subsequent betas will contain bug-fixes and smaller features with no or minimal breaking changes;
* `rc.1` - to be released when the library is stable (no bugs reported for common scenarios - we still might have bugs for corner cases) _and_ Bootstrap 4 goes RC.
* `1.0.0` - no critical bugs / regressions reported for rc(s) _and_ Bootstrap 4 final is released.

# Post 1.0.0

Starting from 1.0 we are going to use [semantic versioning](http://semver.org/) to flag / track releases. We will also consider aligning major releases of this library with the Angular release cycles so it is crystal-clear which version of ng-bootstrap should be used with a particular version of Angular.

It is hard to provide detailed post-1.0.0 plan at this point but here are the main areas of work for the upcoming major versions:
* Continued support / bug fixing for the existing widgets
* Animations
* More features for the existing widgets (we will prioritise issues based on no of 👍 votes so if you care about a particular feature now is the time to vote!) 
* Customisations (adding more flexibility / extension points to the existing widgets)
* More non-core widgets (ex. select2)