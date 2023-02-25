# Swift Style Guide

## Table of Contents

* [Formating](#formating)
* [Naming](#naming)
* [Property Wrappers](#property-wrappers)
* [Closures](#closures)

## Formating

* Use 2 spaces to indent lines.
* Trim trailing whitespace in all lines.
* Add newline at end of file.

## Naming

* Use PascalCase only when naming classes, structures, protocols, enumerations and generics.

  ```swift
  // bad
  protocol planet {
    // ...
  }
  
  // good
  protocol Planet {
    // ...
  }
  ```
  
* Use camelCase for everything else.

  ```swift
  // bad
  let luke_skywalker = "Luke Skywalker"
  
  // good
  let lukeSkywalker = "Luke Skywalker"
  ```

## Property Wrappers

* TODO

  ```swift
  // bad
  @objc(Planet) class Planet {  
    @available(iOS 11.0, *) func method() {
      // ...
    }
  }
  
  // good
  @objc(Planet) 
  class Planet {
    @available(iOS 11.0, *)
    func method() {
      // ...
    }
  }
  ```


## Closures

* Favor `Void` return types over `()` in closure declarations. If you must specify a `Void` return type in a function declaration, use `Void` rather than `()` to improve readability.

  ```swift
  // bad
  func method(completion: () -> ()) {
    // ...
  }
  
  // good
  func method(completion: () -> Void) {
    // ...
  }
  ```

* Use trailing closure syntax only if there's a single closure expression parameter at the end of the argument list. Give the closure parameters descriptive names.

  ```swift
  // bad
  UIView.animate(withDuration: 1.0, animations: {
    // ...
  })
  
  UIView.animate(withDuration: 1.0, animations: {
    // ...
  }) { _ in
    // ...
  }
  
  // good
  UIView.animate(withDuration: 1.0) {
    // ...
  }
  
  UIView.animate(withDuration: 1.0, animations: {
    // ...
  }, completion: { _ in
    // ...
  })
  ```

