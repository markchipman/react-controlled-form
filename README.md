# Controlled Forms

react-controlled-form aims to **simplify form management** with React and Redux.<br>
It ships functional APIs to create your very own form fields and is built with **flexibility** and **customization** in mind.<br>

It allows you to **bring your own components**.<br>
You do not have to struggle with predefined input components ever again!

<img alt="TravisCI" src="https://travis-ci.org/rofrischmann/react-controlled-form.svg?branch=master"> <a href="https://codeclimate.com/github/rofrischmann/react-controlled-form/coverage"><img alt="Test Coverage" src="https://codeclimate.com/github/rofrischmann/react-controlled-form/badges/coverage.svg"></a> <img alt="npm downloads" src="https://img.shields.io/npm/dm/react-controlled-form.svg"> <img alt="npm version" src="https://badge.fury.io/js/react-controlled-form.svg">

## Installation
```sh
yarn add react-controlled-form react react-redux redux
```
> Controlled Forms requires `react-redux` to be installed in your project. Therefore, `react` and `redux` must also be installed.

## Benefits
* simple functional API
* Redux-driven state management
* full flexibility
* custom form fields
* reactive forms


## The Gist
```javascript
import { Form, Field } from 'react-controlled-form'

function Input({
  value,
  updateField,
  isRequired,
  isValid
}) {
  // we could also do validation here and
  // update isValid in updateField respectively
  function onChange(e) {
    updateField({ value: e.target.value })
  }

  return (
    <input
      value={value}
      required={isRequired}
      disabled={!isEnabled}
      onChange={onChange}
    />
  )
}

function UserForm({
  data
}) {
  const onSubmit = () => console.log("Submitted: ", data)

  return (
    <form onSubmit={onSubmit}>
      <Field fieldId="firstname" render={Input} />
      <Field fieldId="lastname" render={Input} />
      <button type="submit">Submit</button>
    </form>
  )
}

export default () => (
  <Form formId="user" render={UserForm} />
)
```

## Documentation

* [Introduction](https://react-controlled-form.js.org/docs/Introduction.html)
* [Basics](https://react-controlled-form.js.org/docs/Basics.html)
* [Guides](https://react-controlled-form.js.org/docs/Guides.html)
* [API Reference](https://react-controlled-form.js.org/docs/API.html)

## Examples

* [Simple Example](https://react-controlled-form.js.org/docs/introduction/Examples.html#simple) ([demo](https://simple-example-uoacokwwxl.now.sh) | [source](examples/simple))
* [Validation Example](https://react-controlled-form.js.org/docs/introduction/Examples.html#validation) ([demo](https://form-validation-owxkpobide.now.sh) | [source](examples/validation))
* [Third-Party Component  Example](https://react-controlled-form.js.org/docs/introduction/Examples.html#third-party-component) ([demo](https://third-party-component-wrnwzikaxz.now.sh) | [source](examples/third-party-component))

## License
react-controlled-form is licensed under the [MIT License](http://opensource.org/licenses/MIT).<br>
Documentation is licensed under [Creative Common License](http://creativecommons.org/licenses/by/4.0/).<br>
Created with ♥ by [@rofrischmann](http://rofrischmann.de) and all the great contributors.
