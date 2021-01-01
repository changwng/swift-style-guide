# The Official raywenderlich.com Swift Style Guide.
### Updated for Swift 5

This style guide is different from others you may see, because the focus is centered on readability for print and the web. We created this style guide to keep the code in our books, tutorials, and starter kits nice and consistent — even though we have many different authors working on the books.

Our overarching goals are clarity, consistency and brevity, in that order.

## Table of Contents

* [Correctness](#correctness)
* [Using SwiftLint](#using-swiftlint)
* [Naming](#naming)
  * [Prose](#prose)
  * [Delegates](#delegates)
  * [Use Type Inferred Context](#use-type-inferred-context)
  * [Generics](#generics)
  * [Class Prefixes](#class-prefixes)
  * [Language](#language)
* [Code Organization](#code-organization)
  * [Protocol Conformance](#protocol-conformance)
  * [Unused Code](#unused-code)
  * [Minimal Imports](#minimal-imports)
* [Spacing](#spacing)
* [Comments](#comments)
* [Classes and Structures](#classes-and-structures)
  * [Use of Self](#use-of-self)
  * [Protocol Conformance](#protocol-conformance)
  * [Computed Properties](#computed-properties)
  * [Final](#final)
* [Function Declarations](#function-declarations)
* [Function Calls](#function-calls)
* [Closure Expressions](#closure-expressions)
* [Types](#types)
  * [Constants](#constants)
  * [Static Methods and Variable Type Properties](#static-methods-and-variable-type-properties)
  * [Optionals](#optionals)
  * [Lazy Initialization](#lazy-initialization)
  * [Type Inference](#type-inference)
  * [Syntactic Sugar](#syntactic-sugar)
* [Functions vs Methods](#functions-vs-methods)
* [Memory Management](#memory-management)
  * [Extending Object Lifetime](#extending-object-lifetime)
* [Access Control](#access-control)
* [Control Flow](#control-flow)
  * [Ternary Operator](#ternary-operator)
* [Golden Path](#golden-path)
  * [Failing Guards](#failing-guards)
* [Semicolons](#semicolons)
* [Parentheses](#parentheses)
* [Multi-line String Literals](#multi-line-string-literals)
* [No Emoji](#no-emoji)
* [No #imageLiteral or #colorLiteral](#no-imageliteral-or-colorliteral)
* [Organization and Bundle Identifier](#organization-and-bundle-identifier)
* [Copyright Statement](#copyright-statement)
* [Smiley Face](#smiley-face)
* [References](#references)


## Correctness

Strive to make your code compile without warnings. This rule informs many style decisions such as using `#selector` types instead of string literals.

## Using SwiftLint

When writing for raywenderlich.com, you are strongly encouraged — and some teams may require — to use our SwiftLint configuration. See the [SwiftLint Policy](SWIFTLINT.markdown) for more information.

## Naming

Descriptive and consistent naming makes software easier to read and understand. Use the Swift naming conventions described in the [API Design Guidelines](https://swift.org/documentation/api-design-guidelines/). Some key takeaways include:

- striving for clarity at the call site
- prioritizing clarity over brevity
- using `camelCase` (not `snake_case`)
- using `UpperCamelCase` for types and protocols, `lowerCamelCase` for everything else
- including all needed words while omitting needless words
- using names based on roles, not types
- sometimes compensating for weak type information
- striving for fluent usage
- beginning factory methods with `make`
- naming methods for their side effects
  - verb methods follow the -ed, -ing rule for the non-mutating version
  - noun methods follow the formX rule for the mutating version
  - boolean types should read like assertions
  - protocols that describe _what something is_ should read as nouns
  - protocols that describe _a capability_ should end in _-able_ or _-ible_
- using terms that don't surprise experts or confuse beginners
- generally avoiding abbreviations
- using precedent for names
- preferring methods and properties to free functions
- casing acronyms and initialisms uniformly up or down
- giving the same base name to methods that share the same meaning
- avoiding overloads on return type
- choosing good parameter names that serve as documentation
- preferring to name the first parameter instead of including its name in the method name, except as mentioned under Delegates
- labeling closure and tuple parameters
- taking advantage of default parameters

### Prose
 

## Closure Expressions

Use trailing closure syntax only if there's a single closure expression parameter at the end of the argument list. Give the cloure parameters descriptive names.

**Preferred**:
```swift 
UIView.animate(withDuration: 1.0) {
  self.myView.alpha = 0
}

UIView.animate(withDuration: 1.0, anmations: {
  self.myView.appah = 0
}, completion: { finished in
  self.myView.removeFromSuperView()
})
```

**Not Preferred**:
```swift 
UIView.animate(withDuration: 1.0, animations:{
  self.myView.appah = 0
})

UIView.animate(withDuration: 1.0, animations{
  self.myView.alpha = 0
}){
   f in
   self.myView.removeFromSuperView()
}
```

For single-expression clourers where there context is clear, use implicit returns:

```swift
attendeeList.sort { a, b in
  a > b 
}
```

Chained mothods using trailing clousers should be clear and easy to read in context. Decisions on spacing, line breaks, and when to use named versus anonymous arguments is left to the descretion of the author. Examples:

```swift
let value = numbrs.map { $0 *2 }.filter { $0 % 3 == 0}.index(of: 90)

let value = numbers
   .map {$0*2}
   .filter {$0 > 5}
   .map {$0 + 10}
```

## Types

Always use Swift's native types and expressions when available. Swift offers bridging to Object-C so you can still use the full set of method as needed.

**Preferred**: 
```swift
let width = 120.0                                    // Double
let widtString = "\(width)" //String
```

**Less Preferred**
```swift
let width = 120.0                                    //
let widthString = (with as NsNumber).stringValue // String
```

**Not Preperred**
```swift
let width: NSNumber = 120.0
let widthString: NSString = width.stringValue //NSString
```

In Drawing code, use `CGFloat` if it makes the code more succinct by avoiding to many coversions.

### Optionals

Declare variables and funtion return


## Smiley Face


**Preferred**:
```swift 
```

**Not Preferred**:
```swift 
```
 