If you compare a list of components on the official [Bootstrap 4 documentation site](https://v4-alpha.getbootstrap.com/components) with the list on the [ng-bootstrap demo site](https://ng-bootstrap.github.io/#/components) you will notice that those 2 list don't match. On one hand we've got more components (ex. date-picker, typeahead) but also lacking equivalent of some components (ex. badge, card). 2 sections below try to explain our rationale when deciding what should be implemented as a ng-bootstrap component.

# Bootstrap 4 components without ng-bootstrap equivalents

There are many "components" on the [Bootstrap 4 documentation site](https://v4-alpha.getbootstrap.com/components) that are simple HTML tags with associated CSS classes but no JS behaviour whatsoever. Examples of such simple components include [badges](https://v4-alpha.getbootstrap.com/components/badge/), [breadcrumbs](https://v4-alpha.getbootstrap.com/components/breadcrumb/) or [cards](https://v4-alpha.getbootstrap.com/components/card/).

While we could create an Angular wrapper around those simple HTML structures the value of doing so would be minimal. Let's take [badges](https://v4-alpha.getbootstrap.com/components/badge/) as an example. To use raw Bootstrap's HTML one needs to write:

```html
<span class="badge badge-pill badge-success">Success</span>
```

By turning this markup into an Angular component we would end up with something similar to:

```html
<ng-badge [pill]="true" type="success">Success</ng-badge>
```

In this example one needs to write almost _exactly_ the same amount of code to display a badge. So we are not cutting on code to write but still introducing a new abstraction that has some cost:
* people need to learn API instead of just looking up HTML + CSS structure in the Bootstrap's documentation
* ng-bootstrap library gets bigger
* Angular will have to generate code / create date structures associated with a new component so performance would suffer.

We are very careful about _not_ coding / shipping components or directives that would introduce new abstractions without providing value. A component or directive needs to do something "useful" to make it into ng-bootstrap codebase. In general we see those things as providing value and thus justifying new abstraction:
* JS behaviour (ex. positioning tooltips, toggling collapse with animations, opening modal etc.);
* encapsulating markup that is repetitive / verbose to write by hand;
* enhancing markup with accessibility support (screen readers, keyboard navigation etc.) that would be tricky to do "by hand";

Based on the above criteria we've decided to _not_ implement as ng-bootstrap components / directives:
* [badges](https://v4-alpha.getbootstrap.com/components/badge/) 
* [breadcrumb](https://v4-alpha.getbootstrap.com/components/breadcrumb/)
* [jumbotron](https://v4-alpha.getbootstrap.com/components/jumbotron/)
* [list group](https://v4-alpha.getbootstrap.com/components/list-group/)
* [navbar](https://v4-alpha.getbootstrap.com/components/navbar/)

Obviously it is not always a "clean cut" and even within the team we had lengthy discussions about supporting cards or navbars. Given this we are open to hear community's feedback: if you've got a use-case / API proposal that makes new abstraction "worthwhile", please open an issue with the API proposal.  

# ng-bootstrap components without Bootstrap 4 equivalents

We've implemented a number of components that don't have equivalents in Bootstrap 4 CSS:
* [datepicker](https://ng-bootstrap.github.io/#/components/datepicker)
* [rating](https://ng-bootstrap.github.io/#/components/rating)
* [timepicker](https://ng-bootstrap.github.io/#/components/timepicker) 
* [typeahead](https://ng-bootstrap.github.io/#/components/typeahead)

The above components are commonly used in web applications (especially datepicker and typeahead) so it is hard to skip those in a general-purpose widget library like ng-bootstrap. We plan on adding more widgets like those long-term and we are considering selec2-like components, data grids, tree view and others. But before making any progress in this area we want to stabilise existing widgets and update our infrastructure (build, documentation etc.) so additional components can be maintained / released separately from the core set of widgets.

# And all the rest...

Then there are components that _are_ part of Bootstrap 4 CSS and for which we would _love_ to have Angular directives / components:
* inputs / forms - markup + CSS is quite verbose so encapsulating it with proper Angular forms support (data binding, validation) would be huge win;
* tables / data grids - many applications needs some forms of list / data tables and it often feels like creating markup for those is very repetitive;
* tree views.

In all of the above cases we would _love_ to have ng-bootstrap directives / widgets but so far we haven't found APIs / designs that would be useful and flexible enough and at the same time. But we are keeping an eye on those use-cases so if you've got API / design proposal please open an issue to discuss.   