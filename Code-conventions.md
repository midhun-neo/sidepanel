Let's describe the conventions we agreed upon.

### Instance variables

They are not private (with an exception seen below), users can always grab a reference from your element to access its internal variables:

```html
<rating #rating></rating>
{{rating.rate}}
```

They should have their type assigned to them, with the exception of initialized variables which have their type initialized implicitly.

```javascript
class Component {
  foo: number;
  bar: string;
  baz = 0;
}
```

An exception would be strings, they will have their type explicitly:

```javascript
class Component {
  stuff: Array<string> = [];
}
```

### Setters and Getters

If your component have inputs that could trigger other changes, you need to write a setter

```javascript
class Component {
  private _foo: string;

  @Input()
  set foo(newFoo: string) {
    this._foo = newFoo;
    this.doSomethingElse();
  }
}
```

The setter will have a parameter named like the setter, but prepended by new, in camelCase. Also notice how we prepended our instance variable with an underscore and marked it as private.

Since our instance variable is "private" now, we need to offer a getter too:

```javascript
class Component {
  private _foo: string;

  @Input()
  set foo(newFoo: string) {
    this._foo = newFoo;
    this.doSomethingElse();
  }

  get foo() { return this._foo; }
}
```

### Internal logic

If you have methods or variables that are just business logic and it is not meant to be usable as an input / output, you mark them as private. For example:

```javascript
class Component {
 ...
 private tempState: number;

 private generateState() {
   this.tempState = ...
   // Do other stuff
 }
}
```

Neither `generateState` nor `tempState` is really meant to be usable from the outside, they just define the internal private state. Keep in mind that `private` won't avoid a enduser of doing:

```html
<component #component></component> {{ component.tempState }}
```

It is just to add some semantics to our code.

### Testing conventions for components

We found that for a best testing coverage, On the one hand, you should test your business logic and on the other hand your UI logic.

For more details our tests to see what needs to be tested for each kind of test. Still, they basic skeleton for a test would be:

```javascript
describe('componentname', () => {
  // some common code / matchers / initialization

  describe('business logic', () => {
  });

  describe('UI', () => {
  });
});
```