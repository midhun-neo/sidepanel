# Code conventions

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

An exception would be strings (and other complex types), they will have their type explicitly:

```javascript
class Component {
  stuff: string[] = [];
}
```

### Setters and Getters

If your component have inputs that could trigger other changes, you need to write a setter

```javascript
class Component {
  private _foo: string;

  @Input()
  set foo(value: string) {
    this._foo = value;
    this.doSomethingElse();
  }
}
```

The setter will have a parameter named `value`. Also notice how we prepended our instance variable with an underscore and marked it as private.

Since our instance variable is "private" now, we need to offer a getter too:

```javascript
class Component {
  private _foo: string;

  @Input()
  set foo(value: string) {
    this._foo = value;
    this.doSomethingElse();
  }

  get foo() { return this._foo; }
}
```

### Internal logic

For semantics, if you have methods or variables that are just business logic and it is not meant to be usable as an input / output, you mark them as private. For example:

```javascript
class Component {
 ...
 private _tempState: number;

 private _generateState() {
   this.tempState = ...
   // Do other stuff
 }
}
```

Neither `_generateState` nor `_tempState` is really meant to be usable from the outside, they just define the internal private state. Keep in mind that `private` won't avoid a enduser of doing:

```html
<component #component></component> {{ component._tempState }}
```

But at least the user will know that he "shouldn't" do it.

On the other hand, if some variable / method is being used in the template, it is not considered private so it doesn't have the `private` keyword nor the underscore.

### Testing conventions for components

We found that for a best testing coverage, On the one hand, you should test your business logic and on the other hand your UI logic. Business logic tests are not always doable (if your component is too tied to the DOM), but they could be a worthy addition.

For more details, check our tests to see what needs to be tested for each kind of test. Still, the basic skeleton for a test would be:

```javascript
// imports

describe('componentname', () => {
  // some common code / matchers / initialization

  describe('business logic', () => {
  });

  describe('UI logic', () => {
  });
});
```

If there are no business logic tests yet, you can skip the inner describes:

```javascript
// imports

describe('componentname', () => {
  // some common code / matchers / initialization

  // UI logic tests
});
```

### Component internal organization

We organize our component like (always in alphabetical order):

```typescript
class MyComp {
  // private variables and then public
  private _bar: string;
  private _foo: number;
  myVar = 10;

  // Inputs and input setters (with empty spaces between)
  @Input() anInput: boolean;
  @Input() baz: string;

  @Input()
  set foo(...) { ... }

  get foo() { ... }

  @Input()
  set rate(...) { ... }

  get rate() { ... }

  @Input() width: number;

  // Outputs
  @Ouput() fooChange = new EventEmitter();
  @Ouput() rateChange = new EventEmitter();

  // Methods (If there is a constructor, always first)
  constructor() { ... }

  doSomething() { ... }

  editFoo() { ... }

  // Private methods
  private _internalStuff() { ... }

  private _rateCalculation() { ... }
}
```

  