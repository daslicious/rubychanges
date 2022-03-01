---
title: Ruby Evolution
prev: /
next: 3.1
---

# Ruby Evolution

## Language changes[](#language-changes)

* **2.0** Default source encoding is changed to UTF-8 (was US-ASCII)
<!--
* **2.0** No warning for unused variables starting with `_`
-->
* **2.3** **Safe navigation operator**
* [2.4](2.4.md#multiple-assignment-allowed-in-conditional-expression) Multiple assignment allowed in conditional expression
* [2.4](2.4.md#toplevel-return) Toplevel `return`
<!--
* [2.5](2.5.md#top-level-constant-look-up-is-removed) Top-level constant look-up is removed
-->
* [2.6](2.6.md#non-ascii-constant-names) Non-ASCII constant names
* [2.7](2.7.md#safe-and-taint-concepts-are-deprecated-in-general) "Safe" and "taint" concepts are deprecated in general
* [2.7](2.7.md#selfprivate_method) `self.<private_method>` (<a class="ruby-doc" href="https://ruby-doc.org/core-2.7.0/doc/syntax/modules_and_classes_rdoc.html#label-Visibility"><code>doc/syntax/modules_and_classes.rdoc#Visibility</code></a>)
* [3.0](3.0.md#changes-in-class-variable-behavior) Changes in class variable behavior
* [3.0](3.0.md#types) **Types**
<!--
* [3.1](3.1.md#multiple-assignment-evaluation-order-change) Multiple assignment evaluation order change (—)
-->

## Freezing[](#freezing)

TODO: Explanations

* **2.0** Fixnums, Bignums and Floats are frozen.
* **2.1** All symbols are now frozen.
* **2.2** `nil`/`true`/`false` objects are frozen.
* **2.3** `String#+@` and `#-@` are added to get mutable/frozen strings.
* [2.4](2.4.md#objectclonefreeze-false) `#clone(freeze: false)` (<a class="ruby-doc" href="https://ruby-doc.org/core-2.4.0/Object.html#method-i-clone"><code>Object#clone</code></a>)
* [2.7](2.7.md#core-methods-returning-frozen-strings) Core methods returning frozen strings (—)
* [3.0](3.0.md#objectclonefreeze-true) `#clone(freeze: true)` (<a class="ruby-doc" href="https://docs.ruby-lang.org/en/3.0.0/Kernel.html#method-i-clone"><code>Kernel#clone</code></a>)
* [3.0](3.0.md#objectclone-passes-freeze-argument-to-initialize_clone) `Object#clone` passes `freeze:` argument to `#initialize_clone` (<a class="ruby-doc" href="https://docs.ruby-lang.org/en/3.0.0/Kernel.html#method-i-clone"><code>Kernel#clone</code></a>)
* [3.0](3.0.md#interpolated-string-literals-are-no-longer-frozen-when--frozen-string-literal-true-is-used) Interpolated String literals are no longer frozen when `# frozen-string-literal: true` is used (<a class="ruby-doc" href="https://docs.ruby-lang.org/en/3.0.0/doc/syntax/comments_rdoc.html#label-frozen_string_literal+Directive"><code>doc/syntax/comments.rdoc</code></a>)
* [3.0](3.0.md#regexp-and-range-objects-are-frozen) `Regexp` and `Range` objects are frozen

## Pattern-matching[](#pattern-matching)

* [2.7](2.7.md#pattern-matching) **Pattern-matching introduced as an experimental feature**
* [3.0](3.0.md#one-line-pattern-matching-with-) One-line pattern matching with `=>` (<a class="ruby-doc" href="https://docs.ruby-lang.org/en/3.0.0/doc/syntax/pattern_matching_rdoc.html"><code>doc/syntax/pattern_matching.rdoc</code></a>)
* [3.0](3.0.md#in-as-a-truefalse-check) `in` as a `true`/`false` check (<a class="ruby-doc" href="https://docs.ruby-lang.org/en/3.0.0/doc/syntax/pattern_matching_rdoc.html"><code>doc/syntax/pattern_matching.rdoc</code></a>)
* [3.0](3.0.md#find-pattern) Find pattern (<a class="ruby-doc" href="https://docs.ruby-lang.org/en/3.0.0/doc/syntax/pattern_matching_rdoc.html"><code>doc/syntax/pattern_matching.rdoc</code></a>)
* [3.1](3.1.md#expressions-and-non-local-variables-allowed-in-pin-operator-) Expressions and non-local variables allowed in pin operator `^` (<a class="ruby-doc" href="https://docs.ruby-lang.org/en/3.1/doc/syntax/pattern_matching_rdoc.html#label-Variable+pinning">doc/syntax/pattern_matching.rdoc#Variable pinning</a>)
* [3.1](3.1.md#parentheses-can-be-omitted-in-one-line-pattern-matching) Parentheses can be omitted in one-line pattern matching. (<a class="ruby-doc" href="https://docs.ruby-lang.org/en/3.1/doc/syntax/pattern_matching_rdoc.html#label-Patterns"><code>doc/syntax/pattern_matching.rdoc#Patterns</code></a>)

## Refinements[](#refinements)

* **2.0** **Refinements are introduced as experimental feature** with `Module#refine` and top-level `using`
* **2.1** `Module#refine` and top-level `using` is no longer experimental
* **2.1** `Module#using` introduced to activate refinements only in some particular module
* [2.4](2.4.md#refinements-are-supported-in-symbolto_proc-and-send) Refinements are supported in `Symbol#to_proc` and `send` (—)
* [2.4](2.4.md#refine-can-refine-modules-too) `refine` can refine modules, too (<a class="ruby-doc" href="https://ruby-doc.org/core-2.4.0/Module.html#method-i-refine"><code>Module#refine</code></a>)
* [2.4](2.4.md#moduleused_modules) `Module.used_modules` (<a class="ruby-doc" href="https://ruby-doc.org/core-2.4.0/Module.html#method-c-used_modules"><code>Module.used_modules</code></a>)
* [2.5](2.5.md#refinements-work-in-string-interpolations) Refinements work in string interpolations (—)
* [2.6](2.6.md#refinements-improved-visibility) Improved refinements visibility (—)
* [2.7](2.7.md#refinements-in-methodinstance_method) Refinements in `#method`/`#instance_method` (—)
* [3.1](3.1.md#refinement-class) `Refinement` class (<a class="ruby-doc" href="https://docs.ruby-lang.org/en/3.1/Refinement.html"><code>Refinement</code></a>)

## `Kernel`[](#kernel)

TODO: Short explanation

* **2.0** `#__dir__`: absolute path to current source file
* **2.0** `#caller_locations` which returns an array of frame information objects.
* **2.0** `#caller` accepts second optional argument `n` which specify required caller size.
* **2.2** `#throw` raises `UncaughtThrowError`, subclass of `ArgumentError` when there is no corresponding catch block, instead of `ArgumentError`.
* **2.3** `#loop`: when stopped by a `StopIteration` exception, returns what the enumerator has returned instead of `nil`
* [2.5](2.5.md#pp) `#pp` is available without `require 'pp'`
* [2.6](2.6.md#numeric-methods-have-exception-argument) `<Numeric>(exception: true/false)` argument (<a class="ruby-doc" href="https://ruby-doc.org/core-2.6/Kernel.html#method-i-Integer"><code>Kernel#Integer</code></a>, <a class="ruby-doc" href="https://ruby-doc.org/core-2.6/Kernel.html#method-i-Float"><code>Kernel#Float</code></a>, <a class="ruby-doc" href="https://ruby-doc.org/core-2.6/Kernel.html#method-i-Rational"><code>Kernel#Rational</code></a>, <a class="ruby-doc" href="https://ruby-doc.org/core-2.6/Kernel.html#method-i-Complex"><code>Kernel#Complex</code></a>, <a class="ruby-doc" href="https://ruby-doc.org/stdlib-2.6/libdoc/bigdecimal/rdoc/Kernel.html#method-i-BigDecimal"><code>Kernel#BigDecimal</code></a>)
* [2.6](2.6.md#system-has-exception-argument) `#system(exception: true/false)` argument (<a class="ruby-doc" href="https://ruby-doc.org/core-2.6/Kernel.html#method-i-system"><code>Kernel#system</code></a> (unfortunately, seems documentation haven't been updated with new feature))
<!--
* [3.0](3.0.md#kerneleval-changed-processing-of-__file__-and-__line__) `#eval` changed processing of `__FILE__` and `__LINE__` (—)
-->
* [3.1](3.1.md#kernelload-module-as-a-second-argument) `#load` allows to pass module as a second argument (<a class="ruby-doc" href="https://docs.ruby-lang.org/en/3.1/Kernel.html#method-i-load"><code>Kernel#load</code></a>)


## `Object`[](#object)

* **2.0** `respond_to?` against a protected method now returns false unless the second argument is true.
* **2.0** `#inspect` does not call `#to_s` anymore (it used to call redefined `#to_s`).
* **2.0** `#respond_to_missing?`, `#initialize_clone`, `#initialize_dup` are now private.
* **2.1** `#singleton_method`
* **2.2** `#itself`
* [2.5](2.5.md#yield_self) `#yield_self`
* [2.6](2.6.md#then-as-an-alias-for-yield_self) ...which in the next version was renamed to **`#then`**

## `Method`[](#method)

* **2.0** Added keyword arguments.
* **2.0** top-level `define_method` which defines a global function.
* **2.1** Required keyword arguments
* **2.1** `def` now returns the symbol of its name instead of nil.
* **2.1** `Module#define_method` and `Object#define_singleton_method` now return the symbols of the defined methods, not the methods/procs
* **2.2** `Method#curry([ arity ])`
* **2.2** `Method#super_method`
* [2.5](2.5.md#method) `Method#===` (<a class="ruby-doc" href="https://ruby-doc.org/core-2.5.0/Method.html#method-i-3D-3D-3D"><code>Method#===</code></a>)
* [2.7](2.7.md#keyword-argument-related-changes) Big Keyword Argument Separation
* [2.7](2.7.md#better-methodinspect) Better `Method#inspect` (<a class="ruby-doc" href="https://ruby-doc.org/core-2.7.0/Method.html#method-i-inspect"><code>Method#inspect</code></a>)
* [2.7](2.7.md#unboundmethodbind_call) `UnboundMethod#bind_call` (<a class="ruby-doc" href="https://ruby-doc.org/core-2.7.0/UnboundMethod.html#method-i-bind_call"><code>UnboundMethod#bind_call</code></a>)
* [3.0](3.0.md#arguments-forwarding--supports-leading-arguments) Arguments forwarding (`...`) supports leading arguments (<a class="ruby-doc" href="https://docs.ruby-lang.org/en/master/doc/syntax/methods_rdoc.html#label-Argument+forwarding"><code>doc/syntax/methods.rdoc</code></a> _<small>(the link is to a `master` version, docs were merged post 3.0 release)</small>_)
* [3.0](3.0.md#endless-method-definition) "Endless" method definition (<a class="ruby-doc" href="https://docs.ruby-lang.org/en/master/doc/syntax/methods_rdoc.html"><code>doc/syntax/methods.rdoc</code></a> _<small>(the link is to a `master` version, docs were merged post 3.0 release)</small>_)
* [3.1](3.1.md#methodunboundmethod-public-private-protected) `Method`/`UnboundMethod`: `#public?`, `#private?`, `#protected?` (<a class="ruby-doc" href="https://docs.ruby-lang.org/en/3.1/Method.html#method-i-private-3F"><code>Method#private?</code></a>, <a class="ruby-doc" href="https://docs.ruby-lang.org/en/3.1/UnboundMethod.html#method-i-private-3F"><code>UnboundMethod#private?</code></a>)
* [3.1](3.1.md#inside-endless-method-definitions-method-calls-without-parenthesis-are-allowed) Inside "endless" method definitions, method calls without parenthesis are allowed (— (<a class="ruby-doc" href="https://docs.ruby-lang.org/en/3.1/doc/syntax/methods_rdoc.html"><code>doc/syntax/methods.rdoc</code></a> doesn't mention new or old behavior.))
* [3.1](3.1.md#values-in-hash-literals-and-keyword-arguments-can-be-omitted) Values in keyword arguments can be omitted ( <a class="ruby-doc" href="https://docs.ruby-lang.org/en/3.1/doc/syntax/literals_rdoc.html#label-Hash+Literals">doc/syntax/literals.rdoc#Hash Literals</a>, <a class="ruby-doc" href="https://docs.ruby-lang.org/en/3.1/doc/syntax/methods_rdoc.html#label-Keyword+Arguments">doc/methods.rdoc#Keyword Arguments</a>, <a class="ruby-doc" href="https://docs.ruby-lang.org/en/3.1/Hash.html"><code>Hash</code></a>)
* [3.1](3.1.md#anonymous-block-argument) Anonymous block argument (<a class="ruby-doc" href="https://docs.ruby-lang.org/en/3.1/doc/syntax/methods_rdoc.html#label-Block+Argument">doc/syntax/methods.rdoc#Block Argument</a>)

## `Proc`[](#proc)

* **2.0** removed `Proc#==` and `#eql?` so two procs are == only when they are the same object.
* **2.1** Returning from lambda proc now always exits from the Proc, not from the method where the lambda is created.  Returning from non-lambda proc exits from the method, same as the former behavior.
* **2.2** `ArgumentError` is no longer raised when lambda `Proc` is passed as a block, and the number of yielded arguments does not match the formal arguments of the lambda, if just an array is yielded and its length matches.
* [2.6](2.6.md#proc-composition) `Proc` composition (—)
* [2.7](2.7.md#numbered-block-parameters) Numbered block parameters ([Proc#Numbered parameters](https://docs.rubocop.org/en/stable/cops_layout/))
<!--
* [3.0](3.0.md#procs-with-rest-arguments-and-keywords-change-of-autosplatting-behavior) Keyword arguments are now fully separated from positional arguments: Procs with "rest" arguments and keywords: change of autosplatting behavior (—)
* [3.0](3.0.md#symbolto_proc-reported-as-lambda) Procs/lambdas: `Symbol#to_proc` reported as lambda (—)
* [3.0](3.0.md#kernellambda-warns-if-called-without-a-literal-block) `Kernel#lambda` warns if called without a literal block (—)
* [3.0](3.0.md#proc-and-eql) Procs/lambdas: `Proc#==` and `#eql?` (<a class="ruby-doc" href="https://docs.ruby-lang.org/en/3.0.0/Proc.html#method-i-3D-3D"><code>Proc#==</code></a>)
-->

## `Module`[](#module)

* **2.0** `Module#define_method` accepts a UnboundMethod from a Module.
* **2.0** `Module#prepend`, `.prepended` and `.prepend_features`
* **2.0** `Module#const_get` accepts a qualified constant string, e.g. `Object.const_get("Foo::Bar::Baz")`
* **2.1** `Module#ancestors`
* **2.1** The ancestors of a singleton class now include singleton classes,  in particular itself.
* **2.1** `Module#singleton_class?`
* **2.1** `Module#include` and `#prepend` are now public methods.
* **2.3** `Module#deprecate_constant`
* [2.5](2.5.md#module-methods-for-defining-methods-and-accessors-became-public) `Module`: methods for defining methods and accessors became public (—)
* [2.6](2.6.md#modulemethod_defined-inherit-argument) `Module#method_defined?`: `inherit` argument (<a class="ruby-doc" href="https://ruby-doc.org/core-2.6/Module.html#method-i-method_defined-3F"><code>Module#method_defined?</code></a>, <a class="ruby-doc" href="https://ruby-doc.org/core-2.6/Module.html#method-i-private_method_defined-3F"><code>Module#private_method_defined?</code></a>, <a class="ruby-doc" href="https://ruby-doc.org/core-2.6/Module.html#method-i-protected_method_defined-3F"><code>Module#protected_method_defined?</code></a>, <a class="ruby-doc" href="https://ruby-doc.org/core-2.6/Module.html#method-i-public_method_defined-3F"><code>Module#public_method_defined?</code></a>)
* [2.7](2.7.md#const_source_location) `Module#const_source_location` (<a class="ruby-doc" href="https://ruby-doc.org/core-2.7.0/Module.html#method-i-const_source_location"><code>Module#const_source_location</code></a>)
* [2.7](2.7.md#autoload-inherit-argument) `Module#autoload?`: `inherit` argument (<a class="ruby-doc" href="https://ruby-doc.org/core-2.7.0/Module.html#method-i-autoload-3F"><code>Module#autoload?</code></a>)
* [3.0](3.0.md#include-and-prepend-now-affects-modules-including-the-receiver) `Module#include` and `#prepend` now affects modules including the receiver (—)
* [3.0](3.0.md#improved-method-visibility-declaration) `Module`: Improved method visibility declaration (—)
* [3.1](3.1.md#classsubclasses) `Class#subclasses` (<a class="ruby-doc" href="https://docs.ruby-lang.org/en/3.1/Class.html#method-i-subclasses"><code>Class#subclasses</code></a>)
* [3.1](3.1.md#moduleprepend-behavior-change) `Module#prepend` behavior change (<a class="ruby-doc" href="https://docs.ruby-lang.org/en/3.1/Module.html#method-i-prepend"><code>Module#prepend</code></a> _(not that it actually documents new—or old—behavior)_)
* [3.1](3.1.md#moduleprivate-public-protected-and-module_function-return-their-arguments) `Module#private`, `#public`, `#protected`, and `#module_function` return their arguments (<a class="ruby-doc" href="https://docs.ruby-lang.org/en/3.1/Module.html#method-i-private"><code>Module#private</code></a>,   <a class="ruby-doc" href="https://docs.ruby-lang.org/en/3.1/Module.html#method-i-public"><code>Module#public</code></a>, <a class="ruby-doc" href="https://docs.ruby-lang.org/en/3.1/Module.html#method-i-protected"><code>Module#protected</code></a>, <a class="ruby-doc" href="https://docs.ruby-lang.org/en/3.1/Module.html#method-i-module_function"><code>Module#module_function</code></a>)

## `Comparable`[](#comparable)

Included in many classes to implement `#<`, `#<=`, etc.

* **2.3** `#==` no longer rescues exceptions
* [2.4](2.4.md#comparableclamp) `#clamp` (<a class="ruby-doc" href="https://ruby-doc.org/core-2.4.0/Comparable.html#method-i-clamp"><code>Comparable#clamp</code></a>)
* [2.7](2.7.md#comparableclamp-with-range) `#clamp` supports `Range` argument (<a class="ruby-doc" href="https://ruby-doc.org/core-2.7.0/Comparable.html#method-i-clamp"><code>Comparable#clamp</code></a>)

## `Numeric`[](#numeric)

* **2.1** `Fixnum#bit_length`, `Bignum#bit_length`
* **2.1** `Numeric#step` allows the limit argument to be omitted. Keyword arguments `to` and `by` are introduced for ease of use.
* **2.1** Added suffixes for integer and float literals: `r`, `i`, and `ri`.
<!--
* **2.2** `Math.log` now raises `Math::DomainError` instead of returning NaN if the  base is less than 0, and returns NaN instead of -infinity if both of two arguments are 0.
* **2.2** `Math.atan2` now returns values like as expected by C99 if both two arguments are infinity.
-->
* **2.2** `Float#next_float`, `#prev_float`
* **2.3** `Numeric#positive?` and `#negative?`
* [2.4](2.4.md#fixnum-and-bignum-are-unified-into-integer) `Fixnum` and `Bignum` are unified into `Integer` (<a class="ruby-doc" href="https://ruby-doc.org/core-2.4.0/Integer.html"><code>Integer</code></a>)
* [2.4](2.4.md#numericfinite-and-infinite) `Numeric#finite?` and `#infinite?` (<a class="ruby-doc" href="https://ruby-doc.org/core-2.4.0/Numeric.html#method-i-infinite-3F"><code>Numeric#infinite?</code></a>, <a class="ruby-doc" href="https://ruby-doc.org/core-2.4.0/Numeric.html#method-i-finite-3F"><code>Numeric#finite?</code></a>)
* [2.4](2.4.md#integerdigits) `Integer#digits` (<a class="ruby-doc" href="https://ruby-doc.org/core-2.4.0/Integer.html#method-i-digits"><code>Integer.html#digits</code></a>)
* [2.4](2.4.md#ndigits-optional-argument-for-rounding-methods) `ndigits` optional argument for rounding methods (<a class="ruby-doc" href="https://ruby-doc.org/core-2.4.0/Numeric.html#method-i-ceil"><code>Numeric#ceil</code></a>, <a class="ruby-doc" href="https://ruby-doc.org/core-2.4.0/Numeric.html#method-i-floor"><code>Numeric#floor</code></a>, <a class="ruby-doc" href="https://ruby-doc.org/core-2.4.0/Numeric.html#method-i-truncate"><code>Numeric#truncate</code></a> (in fact, `Integer` and `Float` classes are affected, because `Rational` had the same option long ago).)
* [2.4](2.4.md#half-option-for-round-method) `half:` option for `#round` method ((feature introduced in 2.4, but comprehensive docs were written in 2.5) <a class="ruby-doc" href="https://ruby-doc.org/core-2.5.0/Integer.html#method-i-round"><code>Integer#round</code></a>, <a class="ruby-doc" href="https://ruby-doc.org/core-2.5.0/Float.html#method-i-round"><code>Float#round</code></a>, <a class="ruby-doc" href="https://ruby-doc.org/core-2.5.0/Rational.html#method-i-round"><code>Rational#round</code></a>)
* [2.5](2.5.md#pow-modulo-argument) `Integer#pow`: modulo argument (<a class="ruby-doc" href="https://ruby-doc.org/core-2.5.0/Integer.html#method-i-pow"><code>Integer#pow</code></a>)
* [2.5](2.5.md#allbits-anybits-nobits) `Integer#allbits?`, `#anybits?`, `#nobits?` (<a class="ruby-doc" href="https://ruby-doc.org/core-2.5.0/Integer.html#method-i-allbits-3F"><code>Integer#allbits?</code></a>, <a class="ruby-doc" href="https://ruby-doc.org/core-2.5.0/Integer.html#method-i-allbits-3F"><code>Integer#anybits?</code></a>, <a class="ruby-doc" href="https://ruby-doc.org/core-2.5.0/Integer.html#method-i-allbits-3F"><code>Integer#nobits?</code></a>)
* [2.5](2.5.md#sqrt) `Integer.sqrt` (<a class="ruby-doc" href="https://ruby-doc.org/core-2.5.0/Integer.html#method-c-sqrt"><code>Integer.sqrt</code></a>)
* [2.7](2.7.md#integer-with-range) `Integer[]` with range (<a class="ruby-doc" href="https://ruby-doc.org/core-2.7.0/Integer.html#method-i-5B-5D"><code>Integer#[]</code></a>)
<!--
* [2.7](2.7.md#complex) `Complex#<=>` (<a class="ruby-doc" href="https://ruby-doc.org/core-2.7.0/Complex.html#method-i-3C-3D-3E"><code>Complex#<=></code></a>)
-->
* [3.1](3.1.md#integertry_convert) `Integer.try_convert` (<a class="ruby-doc" href="https://docs.ruby-lang.org/en/3.1/Integer.html#method-c-try_convert"><code>Integer.try_convert</code></a>)

## Strings, symbols and regexps[](#strings-symbols-and-regexps)

* **2.0** Switch Regexp engine to <a class="github" href="https://github.com/k-takata/Onigmo">Onigmo</a>
* **2.0** Iconv has been removed. Use String#encode instead.
* **2.0** Added `%i` and `%I` for symbol list creation
* **2.0** `String#b` returning a copied string whose encoding is ASCII-8BIT.
* **2.0** `String#lines`, `#chars`, `#codepoints`, `#bytes` now returns an array instead of an enumerator.
* **2.1** `"literal".freeze` is now optimized to return the same object
* **2.1** `String#scrub` and `String#scrub!` verify and fix invalid byte sequence.
* **2.1** `pack/unpack` (Array/String): `Q!` and `q!` directives for long long type if platform has the type.
* **2.2** Most symbols which are returned by `String#to_sym` are GC-able.
* **2.2** `String#unicode_normalize`, `#unicode_normalize!`, `#unicode_normalized?`
* **2.3** new string literal, here document starts with `<<~`
* **2.3** `String.new` now accepts new option parameter `encoding`
* [2.4](2.4.md#unicode-case-conversions) Unicode case conversions (<a class="ruby-doc" href="https://ruby-doc.org/core-2.4.0/String.html#method-i-downcase"><code>String#downcase</code></a>, <a class="ruby-doc" href="https://ruby-doc.org/core-2.4.0/String.html#method-i-upcase"><code>String#upcase</code></a>, <a class="ruby-doc" href="https://ruby-doc.org/core-2.4.0/String.html#method-i-capitalize"><code>String#capitalize</code></a>, <a class="ruby-doc" href="https://ruby-doc.org/core-2.4.0/String.html#method-i-swapcase"><code>String#swapcase</code></a>, <a class="ruby-doc" href="https://ruby-doc.org/core-2.4.0/Symbol.html#method-i-downcase"><code>Symbol#downcase</code></a>, <a class="ruby-doc" href="https://ruby-doc.org/core-2.4.0/Symbol.html#method-i-upcase"><code>Symbol#upcase</code></a>, <a class="ruby-doc" href="https://ruby-doc.org/core-2.4.0/Symbol.html#method-i-capitalize"><code>Symbol#capitalize</code></a>, <a class="ruby-doc" href="https://ruby-doc.org/core-2.4.0/Symbol.html#method-i-swapcase"><code>Symbol#swapcase</code></a>,)
* [2.4](2.4.md#stringnewcapacity-size) `String.new(capacity: size)` (<a class="ruby-doc" href="https://ruby-doc.org/core-2.4.0/String.html#method-c-new"><code>String::new</code></a>)
* [2.4](2.4.md#casecmp) `#casecmp?` (<a class="ruby-doc" href="https://ruby-doc.org/core-2.4.0/String.html#method-i-casecmp-3F"><code>String#casecmp?</code></a>, <a class="ruby-doc" href="https://ruby-doc.org/core-2.4.0/Symbol.html#method-i-casecmp-3F"><code>Symbol#casecmp?</code></a>)
* [2.4](2.4.md#stringconcat-and-prepend-accept-multiple-arguments) `String#concat` and `#prepend` accept multiple arguments (<a class="ruby-doc" href="https://ruby-doc.org/core-2.4.0/String.html#method-i-concat"><code>String#concat</code></a>, <a class="ruby-doc" href="https://ruby-doc.org/core-2.4.0/String.html#method-i-prepend"><code>String#prepend</code></a>)
* [2.4](2.4.md#stringunpack1) `String#unpack1` (<a class="ruby-doc" href="https://ruby-doc.org/core-2.4.0/String.html#method-i-unpack1"><code>String#unpack1</code></a>)
* [2.4](2.4.md#match-method) `#match?` method (<a class="ruby-doc" href="https://ruby-doc.org/core-2.4.0/Regexp.html#method-i-match-3F"><code>Regexp#match?</code></a>, <a class="ruby-doc" href="https://ruby-doc.org/core-2.4.0/String.html#method-i-match-3F"><code>String#match?</code></a>, <a class="ruby-doc" href="https://ruby-doc.org/core-2.4.0/Symbol.html#method-i-match-3F"><code>Symbol#match?</code></a>)
* [2.4](2.4.md#matchdata-better-support-for-named-captures) `MatchData`: better support for named captures (<a class="ruby-doc" href="https://ruby-doc.org/core-2.4.0/MatchData.html#method-i-named_captures"><code>MatchData#named_captures</code></a>, <a class="ruby-doc" href="https://ruby-doc.org/core-2.4.0/MatchData.html#method-i-values_at"><code>MatchData#values_at</code></a>)
* [2.5](2.5.md#delete_prefix-delete_prefix-delete_suffix-delete_suffix) `String#delete_prefix`, `#delete_prefix!`, `#delete_suffix`, `#delete_suffix!` (<a class="ruby-doc" href="https://ruby-doc.org/core-2.5.0/String.html#method-i-delete_prefix"><code>String#delete_prefix</code></a>, <a class="ruby-doc" href="https://ruby-doc.org/core-2.5.0/String.html#method-i-delete_suffix"><code>String#delete_suffix</code></a>)
* [2.5](2.5.md#each_grapheme_cluster-and-grapheme_clusters) `String#each_grapheme_cluster` and `#grapheme_clusters` (<a class="ruby-doc" href="https://ruby-doc.org/core-2.5.0/String.html#method-i-each_grapheme_cluster"><code>String#each_grapheme_cluster</code></a>, <a class="ruby-doc" href="https://ruby-doc.org/core-2.5.0/String.html#method-i-grapheme_clusters"><code>String#grapheme_clusters</code></a>)
* [2.5](2.5.md#undump) `String#undump` (<a class="ruby-doc" href="https://ruby-doc.org/core-2.5.0/String.html#method-i-undump"><code>String#undump</code></a>)
* [2.5](2.5.md#casecmp-and-casecmp-return-nil-for-non-string-arguments) `String#casecmp` and `#casecmp?` return `nil` for non-string arguments (<a class="ruby-doc" href="https://ruby-doc.org/core-2.5.0/String.html#method-i-casecmp"><code>String#casecmp</code></a>, <a class="ruby-doc" href="https://ruby-doc.org/core-2.5.0/String.html#method-i-casecmp-3F"><code>String#casecmp?</code></a>)
* [2.5](2.5.md#start_with-accepts-a-regexp) `String#start_with?` accepts a regexp (<a class="ruby-doc" href="https://ruby-doc.org/core-2.6/String.html#method-i-start_with-3F"><code>String#start_with?</code></a> (introduced in 2.5, but documented in 2.6))
* [2.5](2.5.md#string--optimized-for-memory-preserving) `String#-@` optimized for memory preserving (<a class="ruby-doc" href="https://ruby-doc.org/core-2.5.0/String.html#method-i-2D-40"><code>String#-@</code></a>)
* [2.5](2.5.md#regexp-absence-operator) `Regexp`: absence operator (—)
* [2.6](2.6.md#stringsplit-with-block) `String#split` with block (<a class="ruby-doc" href="https://ruby-doc.org/core-2.6/String.html#method-i-split"><code>String#split</code></a>)
* [2.7](2.7.md#symbolstart_with-and-end_with) `Symbol#start_with?` and `#end_with?` (<a class="ruby-doc" href="https://ruby-doc.org/core-2.7.0/Symbol.html#method-i-end_with-3F"><code>Symbol#end_with?</code></a>, <a class="ruby-doc" href="https://ruby-doc.org/core-2.7.0/Symbol.html#method-i-start_with-3F"><code>Symbol#start_with?</code></a>)
* [3.0](3.0.md#string-always-returning-string) `String`: always returning `String` (—)
* [3.0](3.0.md#symbolname) `Symbol#name` (<a class="ruby-doc" href="https://docs.ruby-lang.org/en/3.0.0/Symbol.html#method-i-name"><code>Symbol#name</code></a>)
* [3.1](3.1.md#stringunpack-and-unpack1-offset-argument) `String#unpack` and `#unpack1`: `offset:` argument (<a class="ruby-doc" href="https://docs.ruby-lang.org/en/3.1/String.html#method-i-unpack"><code>String#unpack</code></a>, <a class="ruby-doc" href="https://docs.ruby-lang.org/en/3.1/String.html#method-i-unpack1"><code>String#unpack1</code></a>)
* [3.1](3.1.md#matchdatamatch-and-match_length) `MatchData#match` and `#match_length` (<a class="ruby-doc" href="https://docs.ruby-lang.org/en/3.1/MatchData.html#method-i-match"><code>MatchData#match</code></a>, <a class="ruby-doc" href="https://docs.ruby-lang.org/en/3.1/MatchData.html#method-i-match_length"><code>MatchData#match_length</code></a>)
* [3.1](3.1.md#iobuffer) `IO::Buffer` (<a class="ruby-doc" href="https://docs.ruby-lang.org/en/3.1/IO/Buffer.html"><code>IO::Buffer</code></a>)

## `Struct`[](#struct)

* [2.5](2.5.md#struct-with-keyword-arguments) `Struct.new(..., keyword_init: true)` (<a class="ruby-doc" href="https://ruby-doc.org/core-2.5.0/Struct.html#method-c-new"><code>Struct.new</code></a>)
* [3.1](3.1.md#warning-on-passing-keywords-to-a-non-keyword-initialized-struct) Warning on passing keywords to a non-keyword-initialized struct (—)
* [3.1](3.1.md#structclasskeyword_init) `StructClass#keyword_init?` (<a class="ruby-doc" href="https://docs.ruby-lang.org/en/3.1/Struct.html#method-c-keyword_init-3F"><code>Strict::keyword_init?</code></a>)

## `Time`[](#time)

* **2.0** `Time#to_s` now returns US-ASCII encoding instead of BINARY.
* [2.5](2.5.md#timeat-units) `Time.at`: units (<a class="ruby-doc" href="https://ruby-doc.org/core-2.5.0/Time.html#method-c-at"><code>Time.at</code></a>)
* [2.6](2.6.md#time-support-for-timezones) Support for timezones (<a class="ruby-doc" href="https://ruby-doc.org/core-2.6/Time.html#class-Time-label-Timezone+argument">Time: Timezone argument</a>)
* [2.7](2.7.md#floor-and-ceil) `#floor` and `#ceil` (<a class="ruby-doc" href="https://ruby-doc.org/core-2.7.0/Time.html#method-i-floor"><code>Time#floor</code></a>, <a class="ruby-doc" href="https://ruby-doc.org/core-2.7.0/Time.html#method-i-ceil"><code>Time#ceil</code></a>)
* [2.7](2.7.md#inspect-includes-subseconds) `Time#inspect` includes subseconds (<a class="ruby-doc" href="https://ruby-doc.org/core-2.7.0/Time.html#method-i-inspect"><code>Time#inspect</code></a>)
* [3.1](3.1.md#in-parameter-for-constructing-time) `in:` parameter for constructing time (<a class="ruby-doc" href="https://docs.ruby-lang.org/en/3.1/Time.html#method-c-new"><code>Time.new</code></a>, <a class="ruby-doc" href="https://docs.ruby-lang.org/en/3.1/Time.html#method-c-at"><code>Time.at</code></a>, <a class="ruby-doc" href="https://docs.ruby-lang.org/en/3.1/Time.html#method-c-now"><code>Time.now</code></a>)
* [3.1](3.1.md#strftime-supports--0000-offset) `#strftime` supports `-00:00` offset (<a class="ruby-doc" href="https://docs.ruby-lang.org/en/3.1/Time.html#method-i-strftime"><code>Time#strftime</code></a>)

## `Range`[](#range)

* **2.0** `Range#size`
* **2.0** `Range#bsearch`
* [2.6](2.6.md#endless-range-1) Endless range: `(1..)` (<a class="ruby-doc" href="https://ruby-doc.org/core-2.6/Range.html#class-Range-label-Endless+Ranges">Range: Endless ranges</a>)
* [2.6](2.6.md#range-uses-cover-instead-of-include) `#===` uses `#cover?` instead of `#include?` (—)
* [2.6](2.6.md#rangecover-accepts-range-argument) `#cover?` accepts range argument (—)
* [2.6](2.6.md#range-alias) `#%` alias for `#step` (—)
* [2.6](2.6.md#enumeratorarithmeticsequence) `Enumerator::ArithmeticSequence` (<a class="ruby-doc" href="https://ruby-doc.org/core-2.6.0.preview2/Enumerator/ArithmeticSequence.html"><code>Enumerator::ArithmeticSequence</code></a>, <a class="ruby-doc" href="https://ruby-doc.org/core-2.6/Range.html#method-i-step"><code>Range#step</code></a>, <a class="ruby-doc" href="https://ruby-doc.org/core-2.6/Numeric.html#method-i-step"><code>Numeric#step</code></a>)
* [2.7](2.7.md#beginless-range) Beginless range: `(...100)` (<a class="ruby-doc" href="https://ruby-doc.org/core-2.7.0/doc/syntax/literals_rdoc.html#label-Ranges"><code>doc/syntax/literals.rdoc#Ranges</code></a>)
* [2.7](2.7.md#for-string) `#===` for `String` (<a class="ruby-doc" href="https://ruby-doc.org/core-2.7.0/Range.html#method-i-3D-3D-3D"><code>Range#===</code></a>)
* [2.7](2.7.md#minmax-implementation-change) `#minmax` implementation change (<a class="ruby-doc" href="https://ruby-doc.org/core-2.7.0/Range.html#method-i-minmax"><code>Range#minmax</code></a>)

## Enumerables and collections[](#enumerables-and-collections)

* **2.3** `#dig` to `Array`, `Hash`, and `Struct`

### `Enumerable`[](#enumerable)

* **2.0** added `Enumerable#lazy` method for lazy enumeration. new class `Enumerator::Lazy` for lazy enumeration
* **2.1** `#to_h`
* **2.2** `#slice_after`, `#slice_when`
* **2.2** `#min`, `#min_by`, `#max` and `#max_by` supports optional argument to return multiple elements.
* **2.3** `#grep_v`
* **2.3** `#chunk_while`
* **2.3** `Enumerable#chunk` and `#slice_before` no longer takes the `initial_state` argument
* [2.4](2.4.md#enumerablechunk-without-a-block-returns-an-enumerator) `Enumerable#chunk` without a block returns an `Enumerator` (<a class="ruby-doc" href="https://ruby-doc.org/core-2.4.0/Enumerable.html#method-i-chunk"><code>Enumerable#chunk</code></a>)
* [2.4](2.4.md#sum) `#sum` (<a class="ruby-doc" href="https://ruby-doc.org/core-2.4.0/Enumerable.html#method-i-sum"><code>Enumerable#sum</code></a>, <a class="ruby-doc" href="https://ruby-doc.org/core-2.4.0/Array.html#method-i-sum"><code>Array#sum</code></a>)
* [2.4](2.4.md#uniq) `#uniq` (<a class="ruby-doc" href="https://ruby-doc.org/core-2.4.0/Enumerable.html#method-i-uniq"><code>Enumerable#iniq</code></a>, <a class="ruby-doc" href="https://ruby-doc.org/core-2.4.0/Enumerator/Lazy.html#method-i-uniq"><code>Enumerator::Lazy#uniq</code></a>)
* [2.5](2.5.md#enumerableany-all-none-and-one-accept-patterns) `#any?`, `#all?`, `#none?`, and `#one?` accept patterns (<a class="ruby-doc" href="https://ruby-doc.org/core-2.5.0/Enumerable.html#method-i-all-3F"><code>Enumerable#all?</code></a>, <a class="ruby-doc" href="https://ruby-doc.org/core-2.5.0/Enumerable.html#method-i-any-3F"><code>Enumerable#any?</code></a>, <a class="ruby-doc" href="https://ruby-doc.org/core-2.5.0/Enumerable.html#method-i-none-3F"><code>Enumerable#none?</code></a>, <a class="ruby-doc" href="https://ruby-doc.org/core-2.5.0/Enumerable.html#method-i-one-3F"><code>Enumerable#one?</code></a>)
* [2.6](2.6.md#filterfilter) `#filter`/`#filter!` alias for `#select`/`#select!`
* [2.6](2.6.md#to_h-with-a-block) `#to_h` with a block (<a class="ruby-doc" href="https://ruby-doc.org/core-2.6/Enumerable.html#method-i-to_h"><code>Enumerable#to_h</code></a>, <a class="ruby-doc" href="https://ruby-doc.org/core-2.6/Array.html#method-i-to_h"><code>Array#to_h</code></a>, <a class="ruby-doc" href="https://ruby-doc.org/core-2.6/ENV.html#method-c-to_h"><code>ENV.to_h</code></a>, <a class="ruby-doc" href="https://ruby-doc.org/core-2.6/Hash.html#method-i-to_h"><code>Hash#to_h</code></a>, <a class="ruby-doc" href="https://ruby-doc.org/core-2.6/Struct.html#method-i-to_h"><code>Struct#to_h</code></a>)
* [2.7](2.7.md#enumerablefilter_map) `#filter_map` (<a class="ruby-doc" href="https://ruby-doc.org/core-2.7.0/Enumerable.html#method-i-filter_map"><code>Enumerable#filter_map</code></a>)
* [2.7](2.7.md#enumerabletally) `#tally` (<a class="ruby-doc" href="https://ruby-doc.org/core-2.7.0/Enumerable.html#method-i-tally"><code>Enumerable#tally</code></a>)
* [3.1](3.1.md#enumerabletally-now-accepts-an-optional-hash-to-count) `#tally` now accepts an optional hash to count (<a class="ruby-doc" href="https://docs.ruby-lang.org/en/3.1/Enumerable.html#method-i-tally"><code>Enumerable#tally</code></a>)
* [3.1](3.1.md#enumerableeach_cons-and-each_slice-return-a-receiver) `#each_cons` and `#each_slice` return a receiver (<a class="ruby-doc" href="https://docs.ruby-lang.org/en/3.1/Enumerable.html#method-i-each_cons"><code>Enumerable#each_cons</code></a>, <a class="ruby-doc" href="https://docs.ruby-lang.org/en/3.1/Enumerable.html#method-i-each_slice"><code>Enumerable#each_slice</code></a>)
* [3.1](3.1.md#enumerablecompact-and-enumeratorlazycompact) `#compact` (<a class="ruby-doc" href="https://docs.ruby-lang.org/en/3.1/Enumerable.html#method-i-compact"><code>Enumerable#compact</code></a>, <a class="ruby-doc" href="https://docs.ruby-lang.org/en/3.1/Enumerator/Lazy.html#method-i-compact"><code>Enumerator::Lazy#compact</code></a>)

### `Enumerator`[](#enumerator)

* **2.0** added `Enumerator#size` for lazy size evaluation. `Enumerator.new` accept an argument for lazy size evaluation.
* **2.0** `Kernel#to_enum` and `#enum_for` accept a block for lazy size evaluation.
* [2.6](2.6.md#enumerator-chaining) `Enumerator` chaining (<a class="ruby-doc" href="https://ruby-doc.org/core-2.6/Enumerator.html#method-i-2B"><code>Enumerator#+</code></a>, <a class="ruby-doc" href="https://ruby-doc.org/core-2.6/Enumerable.html#method-i-chain"><code>Enumerable#chain</code></a>, <a class="ruby-doc" href="https://ruby-doc.org/core-2.6/Enumerator/Chain.html"><code>Enumerator::Chain</code></a>)
* [2.7](2.7.md#enumeratorproduce) `Enumerator.produce` ([Enumerator.produce]())
* [2.7](2.7.md#enumeratorlazyeager) `Enumerator::Lazy#eager` (<a class="ruby-doc" href="https://ruby-doc.org/core-2.7.0/Enumerator/Lazy.html#method-i-eager"><code>Enumerator::Lazy#eager</code></a>)
* [2.7](2.7.md#enumeratoryielderto_proc) `Enumerator::Yielder#to_proc` (<a class="ruby-doc" href="https://ruby-doc.org/core-2.7.0/Enumerator/Yielder.html#method-i-to_proc"><code>Enumerator::Yielder#to_proc</code></a>)
* [3.1](3.1.md#enumerablecompact-and-enumeratorlazycompact) `Enumerator::Lazy#compact` (<a class="ruby-doc" href="https://docs.ruby-lang.org/en/3.1/Enumerable.html#method-i-compact"><code>Enumerable#compact</code></a>, <a class="ruby-doc" href="https://docs.ruby-lang.org/en/3.1/Enumerator/Lazy.html#method-i-compact"><code>Enumerator::Lazy#compact</code></a>)

### `Array`[](#array)

* **2.0** `Array#bsearch`
* **2.0** random parameter of `Array#shuffle!` and `#sample` now will be called with one argument, maximum value.
* **2.0** when given Range arguments, `Array#values_at` now returns nil for each value that is out-of-range.
* **2.3** `Array#bsearch_index`
* [2.4](2.4.md#arraymax-and-min) `#max` and `#min` (<a class="ruby-doc" href="https://ruby-doc.org/core-2.4.0/Array.html#method-i-max"><code>Array#max</code></a>, <a class="ruby-doc" href="https://ruby-doc.org/core-2.4.0/Array.html#method-i-max"><code>Array#min</code></a>)
* [2.4](2.4.md#arrayconcat-takes-multiple-arguments) `#concat` takes multiple arguments (<a class="ruby-doc" href="https://ruby-doc.org/core-2.4.0/Array.html#method-i-concat"><code>Array#concat</code></a>)
* [2.4](2.4.md#arraypackbuffer) `#pack(buffer:)` (<a class="ruby-doc" href="https://ruby-doc.org/core-2.4.0/Array.html#method-i-pack"><code>Array#pack</code></a>)
* [2.5](2.5.md#arrayappend-and-prepend) `#append` and `#prepend` (<a class="ruby-doc" href="https://ruby-doc.org/core-2.5.0/Array.html#method-i-append"><code>Array#append</code></a>, <a class="ruby-doc" href="https://ruby-doc.org/core-2.5.0/Array.html#method-i-prepend"><code>Array#prepend</code></a>)
* [2.6](2.6.md#arrayunion-and-arraydifference) `#union` and `#difference` (<a class="ruby-doc" href="https://ruby-doc.org/core-2.6/Array.html#method-i-union"><code>Array#union</code></a>, <a class="ruby-doc" href="https://ruby-doc.org/core-2.6/Array.html#method-i-difference"><code>Array#difference</code></a>)
* [2.7](2.7.md#arrayintersection) `#intersection` (<a class="ruby-doc" href="https://ruby-doc.org/core-2.7.0/Array.html#method-i-intersection"><code>Array#intersection</code></a>)
* [3.0](3.0.md#array-always-returning-array) Always returning `Array` (—)
* [3.0](3.0.md#array-slicing-with-enumeratorarithmeticsequence) Slicing with `Enumerator::ArithmeticSequence` (<a class="ruby-doc" href="https://docs.ruby-lang.org/en/3.0.0/Array.html#method-i-5B-5D"><code>Array#[]</code></a>)
* [3.1](3.1.md#arrayintersect) `#intersect?` (<a class="ruby-doc" href="https://docs.ruby-lang.org/en/3.1/Array.html#method-i-intersect-3F"><code>Array#intersect?</code></a>)

### `Hash`[](#hash)

* **2.0** `Hash#to_h` as explicit conversion method, like Array#to_a.
* **2.0** added `nil.to_h` which returns `{}`
* **2.0** `Struct#to_h`
* **2.0** `Kernel#Hash`
* **2.2** Change overriding policy for duplicated key: `{**hash1, **hash2}` contains values of `hash2` for duplicated keys.
* **2.2** Hash literal: Symbol key followed by a colon can be quoted.
* **2.3** `#fetch_values`
* **2.3** `#<=`, `#<`, `#>=`, `#>`
* **2.3** `#to_proc`
* [2.4](2.4.md#hashcompact-and-compact) `#compact` and `#compact!` (<a class="ruby-doc" href="https://ruby-doc.org/core-2.4.0/Hash.html#method-i-compact"><code>Hash#compact</code></a>, <a class="ruby-doc" href="https://ruby-doc.org/core-2.4.0/Hash.html#method-i-compact-21"><code>Hash#compact!</code></a>)
* [2.4](2.4.md#hashtransform_values-and-transform_values) `#transform_values` and `#transform_values!` (<a class="ruby-doc" href="https://ruby-doc.org/core-2.4.0/Hash.html#method-i-transform_values"><code>Hash#transform_values</code></a>, <a class="ruby-doc" href="https://ruby-doc.org/core-2.4.0/Hash.html#method-i-transform_values-21"><code>Hash#transform_values!</code></a>)
* [2.5](2.5.md#hashtransform_keys-and-transform_keys) `#transform_keys` and `#transform_keys!` (<a class="ruby-doc" href="https://ruby-doc.org/core-2.5.0/Hash.html#method-i-transform_keys"><code>Hash#transform_keys</code></a>, <a class="ruby-doc" href="https://ruby-doc.org/core-2.5.0/Hash.html#method-i-transform_keys-21"><code>Hash#transform_keys!</code></a>)
* [2.5](2.5.md#hashslice) `#slice` (<a class="ruby-doc" href="https://ruby-doc.org/core-2.5.0/Hash.html#method-i-slice"><code>Hash#slice</code></a>)
* [2.6](2.6.md#hashmerge-with-multiple-arguments) `#merge` with multiple arguments (<a class="ruby-doc" href="https://ruby-doc.org/core-2.6/Hash.html#method-i-merge"><code>Hash#merge</code></a>)
* [3.0](3.0.md#hashexcept) `#except` (<a class="ruby-doc" href="https://docs.ruby-lang.org/en/3.0.0/Hash.html#method-i-except"><code>Hash#except</code></a>, <a class="ruby-doc" href="https://docs.ruby-lang.org/en/3.0.0/ENV.html#method-c-except"><code>ENV.except</code></a>)
* [3.0](3.0.md#hashtransform_keys-argument-for-key-renaming) `#transform_keys`: argument for key renaming (<a class="ruby-doc" href="https://docs.ruby-lang.org/en/3.0.0/Hash.html#method-i-transform_keys"><code>Hash#transform_keys</code></a>)
* [3.0](3.0.md#hasheach-consistently-yields-a-2-element-array-to-lambdas) `#each` consistently yields a 2-element array to lambdas (—)
* [3.1](3.1.md#values-in-hash-literals-and-keyword-arguments-can-be-omitted) Values in Hash literals can be omitted ( <a class="ruby-doc" href="https://docs.ruby-lang.org/en/3.1/doc/syntax/literals_rdoc.html#label-Hash+Literals">doc/syntax/literals.rdoc#Hash Literals</a>, <a class="ruby-doc" href="https://docs.ruby-lang.org/en/3.1/doc/syntax/methods_rdoc.html#label-Keyword+Arguments">doc/methods.rdoc#Keyword Arguments</a>, <a class="ruby-doc" href="https://docs.ruby-lang.org/en/3.1/Hash.html"><code>Hash</code></a>)

### `Set`[](#set)

TODO: Explanation, SOME links

* **2.1** `#intersect?` and `#disjoint?`
* **2.4** `#compare_by_identity` and `#compare_by_identity?`
* **2.5** `#to_s` as alias to `#inspect`
* **2.5** `#===` as alias to `#include?`
* **2.5** `#reset`
* **3.0** `SortedSet` has been removed for dependency and performance reasons (it silently depended upon rbtree gem).
* **3.0** `#join` is added as a shorthand for .to_a.join. Discussion: Feature #16991.
* **3.0** `#<=>`

### Other collections[](#other-collections)

* **2.0** `ObjectSpace::WeakMap` introduced
* **2.3** `Thread::Queue#close` is added to notice a termination
* [2.7](2.7.md#objectspaceweakmap-now-accepts-non-gc-able-objects) `ObjectSpace::WeakMap#[]=` now accepts non-GC-able objects (<a class="ruby-doc" href="https://ruby-doc.org/core-2.7.0/ObjectSpace/WeakMap.html#method-i-5B-5D-3D"><code>WeekMap#[]=</code></a>)
* [3.1](3.1.md#threadqueueinitialize-initial-values-can-be-passed-to-initializer) `Thread::Queue#initialize`: initial values can be passed to initializer (<a class="ruby-doc" href="https://docs.ruby-lang.org/en/3.1/Thread/Queue.html#method-c-new"><code>Thread::Queue.new</code></a>)

## Filesystem and IO[](#filesystem-and-io)

* **2.0** `IO#lines`, `#bytes`, `#chars` and `#codepoints` are deprecated.
* **2.0** `ARGF#codepoints` and `#each_codepoint`
* **2.0** `File.fnmatch?` now expands braces in the pattern if File::FNM_EXTGLOB option is given.
* **2.1** `IO#seek` supports SEEK_DATA and SEEK_HOLE as whence.
* **2.1** `IO#seek` accepts symbols (:CUR, :END, :SET, :DATA, :HOLE) for 2nd argument.
* **2.1** `IO#read_nonblock` accepts optional `exception: false` to return symbols
* **2.1** `IO#write_nonblock` accepts optional `exception: false` to return symbols
* **2.2** `IO#read_nonblock` and `#write_nonblock` for pipes on Windows are supported.
* **2.2** `Dir#fileno`
* **2.2** `File.birthtime` `#birthtime`, `File::Stat#birthtime`
* **2.3** `File.mkfifo`
* **2.3** `File::TMPFILE`
* **2.3** `IO`: new mode flag `File::SHARE_DELETE`
* **2.3** `IO`: new option parameter `flags:`
* **2.3** `ARGF.read_nonblock` supports `exception: false` like IO#read_nonblock. [Feature #11358]
* [2.4](2.4.md#chomp-option-for-string-splitting) `chomp:` option for string splitting (—)
* [2.4](2.4.md#empty-method-for-filesystem-objects) `#empty?` method for filesystem objects (<a class="ruby-doc" href="https://ruby-doc.org/core-2.4.0/Dir.html#method-c-empty-3F"><code>Dir#empty?</code></a>, <a class="ruby-doc" href="https://ruby-doc.org/core-2.4.0/File.html#method-c-empty-3F"><code>File#empty?</code></a>, _(stdlib)_ <a class="ruby-doc" href="https://ruby-doc.org/stdlib-2.4.0/libdoc/pathname/rdoc/Pathname.html#method-i-empty-3F"><code>Pathname#empty?</code></a>)
* [2.5](2.5.md#iopread-and-pwrite) `IO#pread` and `#pwrite` (<a class="ruby-doc" href="https://ruby-doc.org/core-2.5.0/IO.html#method-i-pread"><code>IO#pread</code></a>, <a class="ruby-doc" href="https://ruby-doc.org/core-2.5.0/IO.html#method-i-pwrite"><code>IO#pwrite</code></a>)
* [2.5](2.5.md#iowrite-accepts-multiple-arguments) `IO#write` accepts multiple arguments (<a class="ruby-doc" href="https://ruby-doc.org/core-2.5.0/IO.html#method-i-write"><code>IO#write</code></a>)
* [2.5](2.5.md#fileopen-better-supports-newline-option) `File.open` better supports `newline:` option (— (it is _almost_ documented by referring from <a class="ruby-doc" href="https://ruby-doc.org/core-2.5.0/IO.html#method-c-new"><code>IO.new</code></a> docs to <a class="ruby-doc" href="https://ruby-doc.org/core-2.5.0/String.html#method-i-encode"><code>String#encode</code></a> docs, where at least longer form `newline_universal: true` is mentioned))
* [2.5](2.5.md#filepath-raises-when-opened-with-fileconstantstmpfile-option) `File#path` raises when opened with `File::Constants::TMPFILE` option. (<a class="ruby-doc" href="https://ruby-doc.org/core-2.5.0/File.html#method-c-path"><code>File#path</code></a>)
* [2.5](2.5.md#filelutime) `File.lutime` (<a class="ruby-doc" href="https://ruby-doc.org/core-2.5.0/File.html#method-c-lutime"><code>File.lutime</code></a>)
* [2.5](2.5.md#dirchildren-and-each_child)  `Dir.children` and `.each_child` (<a class="ruby-doc" href="https://ruby-doc.org/core-2.5.0/Dir.html#method-c-children"><code>Dir.children</code></a>, <a class="ruby-doc" href="https://ruby-doc.org/core-2.5.0/Dir.html#method-c-each_child"><code>Dir.each_child</code></a>)
* [2.5](2.5.md#dirglob-base-argument) `Dir.glob`: `base:` argument (<a class="ruby-doc" href="https://ruby-doc.org/core-2.5.0/Dir.html#method-c-glob"><code>Dir.glob</code></a>)
* [2.6](2.6.md#direach_child-and-dirchildren) `Dir#each_child` and `Dir#children` (<a class="ruby-doc" href="https://ruby-doc.org/core-2.6/Dir.html#method-i-each_child"><code>Dir#each_child</code></a>, <a class="ruby-doc" href="https://ruby-doc.org/core-2.6/Dir.html#method-i-children"><code>Dir#children</code></a>)
* [2.6](2.6.md#io-open-mode-x) IO open mode: `'x'` (<a class="ruby-doc" href="https://ruby-doc.org/core-2.6/IO.html#method-c-new-label-IO+Open+Mode">IO: Open mode</a>)
* [2.7](2.7.md#ioset_encoding_by_bom) `IO#set_encoding_by_bom` (<a class="ruby-doc" href="https://ruby-doc.org/core-2.7.0/IO.html#method-i-set_encoding_by_bom"><code>IO#set_encoding_by_bom</code></a>)
* [2.7](2.7.md#dirglob-and-dir-not-allow-0-separated-patterns) `Dir.glob` and `Dir.[]` not allow `\0`-separated patterns (<a class="ruby-doc" href="https://ruby-doc.org/core-2.7.0/Dir.html#method-c-glob"><code>Dir.glob</code></a>)
* [2.7](2.7.md#fileextname-returns-a--string-at-a-name-ending-with-a-dot) `File.extname` returns a `"."` string at a name ending with a dot. ([File.extname](https://bugs.ruby-lang.org/issues/15267))
* [3.0](3.0.md#dirglob-and-dir-result-sorting) `Dir.glob` and `Dir.[]` result sorting (<a class="ruby-doc" href="https://docs.ruby-lang.org/en/3.0.0/Dir.html#method-c-glob"><code>Dir.glob</code></a>)
* [3.1](3.1.md#filedirname-optional-level-to-go-up-the-directory-tree) `File.dirname`: optional `level` to go up the directory tree (<a class="ruby-doc" href="https://docs.ruby-lang.org/en/3.1/File.html#method-c-dirname"><code>File.dirname</code></a>)

## Exceptions[](#exceptions)

* **2.0** added `LoadError#path` method to return the file name that could not be loaded.
* **2.1** `Exception#cause` provides the previous exception which has been caught at where raising the new exception.
* **2.3** `NameError#receiver`
* **2.3** `NameError`, `NoMethodError`: `did_you_mean`
* [2.5](2.5.md#rescueelseensure-are-allowed-inside-blocks) `rescue`/`else`/`ensure` are allowed inside blocks (—)
* [2.5](2.5.md#backtrace-and-error-message-in-reverse-order) Backtrace and error message in reverse order (—)
* [2.5](2.5.md#exceptionfull_message) `Exception#full_message` (<a class="ruby-doc" href="https://ruby-doc.org/core-2.5.0/Exception.html#method-i-full_message"><code>Exception#full_message</code></a>)
* [2.5](2.5.md#keyerrorreceiver-and-key) `KeyError#receiver` and `#key` (<a class="ruby-doc" href="https://ruby-doc.org/core-2.5.0/KeyError.html"><code>KeyError</code></a>)
* [2.5](2.5.md#new-class-frozenerror) New class: `FrozenError` (<a class="ruby-doc" href="https://ruby-doc.org/core-2.5.0/FrozenError.html"><code>FrozenError</code></a>)
* [2.5](2.5.md#dont-hide-coercion-errors) Don't hide coercion errors (—)
* [2.6](2.6.md#else-in-exception-handling-context) Language: `else` in exception-handling context (—)
* [2.6](2.6.md#new-arguments-receiver-and-key) New arguments: `receiver:` and `key:` (<a class="ruby-doc" href="https://ruby-doc.org/core-2.6/NameError.html#method-c-new"><code>NameError::new</code></a>, <a class="ruby-doc" href="https://ruby-doc.org/core-2.6/NoMethodError.html#method-c-new"><code>NoMethodError::new</code></a> _(docs not updated)_, <a class="ruby-doc" href="https://ruby-doc.org/core-2.6/KeyError.html#method-c-new"><code>KeyError::new</code></a>)
* [2.6](2.6.md#exceptionfull_message-options) `Exception#full_message` options (<a class="ruby-doc" href="https://ruby-doc.org/core-2.6/Exception.html#method-i-full_message"><code>Exception#full_message</code></a>)
* [2.6](2.6.md#exception-output-tweaking) Exception output tweaking (—)
* [2.7](2.7.md#frozenerror-receiver-argument) `FrozenError`: receiver argument (<a class="ruby-doc" href="https://ruby-doc.org/core-2.7.0/FrozenError.html#method-c-new"><code>FrozenError#new</code></a>)
* [3.0](3.0.md#exception-output-order-is-changed----again) Exception output order is changed -- again (—)
* [3.1](3.1.md#threadbacktracelimit) `Thread::Backtrace.limit` (<a class="ruby-doc" href="https://docs.ruby-lang.org/en/3.1/Thread/Backtrace.html#method-c-limit"><code>Thread::Backtrace.limit</code></a>)

### `Warning`[](#warning)

* **2.0** `Kernel#warn` accepts multiple args in like `#puts`.
* [2.4](2.4.md#warning-module) `Warning` module introduced (_(introduced in 2.4, but documented in 2.5)_ <a class="ruby-doc" href="https://ruby-doc.org/core-2.5.0/Warning.html"><code>Warning</code></a>)
* [2.5](2.5.md#warn-uplevel-keyword-argument) `#warn(uplevel: ...)` keyword argument (<a class="ruby-doc" href="https://ruby-doc.org/core-2.6/Kernel.html#method-i-warn"><code>Kernel#warn</code></a> (it became somewhat documented at Ruby 2.6, but the feature itself has been available since 2.5))
* [2.5](2.5.md#warn-call-warningwarn) `#warn` calls `Warning.warn` (—)
* [2.7](2.7.md#warning-and-) `Warning::[]` and `::[]=` (<a class="ruby-doc" href="https://ruby-doc.org/core-2.7.0/Warning.html#method-c-5B-5D"><code>Warning::[]</code></a>, <a class="ruby-doc" href="https://ruby-doc.org/core-2.7.0/Warning.html#method-c-5B-5D-3D"><code>Warning::[]=</code></a>)
* [3.0](3.0.md#warningwarn-category-keyword-argument) `Warning#warn(category: ....)` keyword argument. (<a class="ruby-doc" href="https://docs.ruby-lang.org/en/3.0.0/Warning.html#method-i-warn"><code>Warning#warn</code></a>, <a class="ruby-doc" href="https://docs.ruby-lang.org/en/3.0.0/Kernel.html#method-i-warn"><code>Kernel#warn</code></a>)

## Concurrency and parallelism[](#concurrency-and-parallelism)

### `Thread`[](#thread)

* **2.0** `Thread#thread_variable_get`, `#thread_variable_set`, `#thread_variables`, `#thread_variable?`
* **2.0** `Thread.handle_interrupt` as well as instance and singleton methods `pending_interrupt?` for asynchronous handling of exceptions
* **2.0** `Thread#backtrace_locations` and new class `Thread::Backtrace::Location` to hold backtrace location information. These are returned by `Thread#backtrace_locations` and `Kernel#caller_locations`.
* **2.0** `Thread#join` and `#value` now raises a `ThreadError` if target thread  is the current or main thread.
* **2.3** `Thread#name`, `#name=`
* [2.4](2.4.md#threadreport_on_exception-and-threadreport_on_exception) `#report_on_exception` and `.report_on_exception` (<a class="ruby-doc" href="https://ruby-doc.org/core-2.4.0/Thread.html#method-c-report_on_exception"><code>Thread.report_on_exception</code></a>, <a class="ruby-doc" href="https://ruby-doc.org/core-2.4.0/Thread.html#method-c-report_on_exception-3D"><code>Thread.report_on_exception=</code></a>, <a class="ruby-doc" href="https://ruby-doc.org/core-2.4.0/Thread.html#method-i-report_on_exception"><code>Thread#report_on_exception</code></a>, <a class="ruby-doc" href="https://ruby-doc.org/core-2.4.0/Thread.html#method-i-report_on_exception-3D"><code>Thread#report_on_exception</code></a>)
* [2.5](2.5.md#threadfetch) `#fetch` (<a class="ruby-doc" href="https://ruby-doc.org/core-2.6/Thread.html#method-i-fetch"><code>Thread#fetch</code></a> (feature is present since Ruby 2.5, but explanations added later))
* [3.0](3.0.md#threadignore_deadlock-accessor) `Thread.ignore_deadlock` accessor (<a class="ruby-doc" href="https://docs.ruby-lang.org/en/3.0.0/Thread.html#method-c-ignore_deadlock-3D"><code>Thread.ignore_deadlock=</code></a>, <a class="ruby-doc" href="https://docs.ruby-lang.org/en/3.0.0/Thread.html#method-c-ignore_deadlock"><code>Thread.ignore_deadlock</code></a>)
* [3.1](3.1.md#threadnative_thread_id) `Thread#native_thread_id` (<a class="ruby-doc" href="https://docs.ruby-lang.org/en/3.1/Thread.html#method-i-native_thread_id"><code>Thread#native_thread_id</code></a>)

### `Process`[](#process)

* **2.0** `Process.getsid` for getting session id (unix only).
* **2.1** `Process.argv0()` returns the original value of $0.
* **2.1** `Process.setproctitle()` sets the process title without affecting $0.
* **2.1** `Process.clock_gettime` and `.clock_getres`
* **2.2** Process execution methods such as `Process.spawn` opens the file in write  mode for redirect from `[:out, :err]`.
* [2.5](2.5.md#processlast_status-as-an-alias-of-) `Process.last_status` as an alias of `$?` (<a class="ruby-doc" href="https://ruby-doc.org/core-2.5.0/Process.html#method-c-last_status"><code>Process.last_status</code></a>)
* [3.1](3.1.md#process_fork) `Process._fork` (<a class="ruby-doc" href="https://docs.ruby-lang.org/en/3.1/Process.html#method-c-_fork"><code>Process.\_fork</code></a>)

### `Fiber`[](#fiber)

* **2.0** `Fiber#resume` cannot resume a fiber which invokes `Fiber#transfer`.
* **2.2** callcc is obsolete. use Fiber instead.
* [2.7](2.7.md#fiberraise) `#raise` (<a class="ruby-doc" href="https://ruby-doc.org/core-2.7.0/Fiber.html#method-i-raise"><code>Fiber#raise</code></a>)
* [3.0](3.0.md#non-blocking-fiber-and-scheduler) Non-blocking `Fiber` and scheduler (<a class="ruby-doc" href="https://docs.ruby-lang.org/en/master/Fiber.html#class-Fiber-label-Non-blocking+Fibers"><code>Fiber</code></a> (class documentation), <a class="ruby-doc" href="https://docs.ruby-lang.org/en/master/Fiber/SchedulerInterface.html"><code>Fiber::SchedulerInterface</code></a> (definition of the interface which the scheduler must implement, <a class="ruby-doc" href="https://docs.ruby-lang.org/en/3.0.0/doc/fiber_md.html"><code>doc/fiber.md</code></a> (design documentation).)
* [3.0](3.0.md#fiberbacktrace--backtrace_locations) `#backtrace` & `#backtrace_locations` (<a class="ruby-doc" href="https://docs.ruby-lang.org/en/3.0.0/Fiber.html#method-i-backtrace"><code>Fiber#backtrace</code></a>, <a class="ruby-doc" href="https://docs.ruby-lang.org/en/3.0.0/Fiber.html#method-i-backtrace_locations"><code>Fiber#backtrace_locations</code></a>,)
* [3.0](3.0.md#fibertransfer-limitations-changed) `#transfer` limitations changed (<a class="ruby-doc" href="https://docs.ruby-lang.org/en/3.0.0/Fiber.html#method-i-transfer"><code>Fiber#transfer</code></a>)
* [3.1](3.1.md#fiber-scheduler-new-hooks) New hooks for fiber scheduler (<a class="ruby-doc" href="https://docs.ruby-lang.org/en/3.1/Fiber/SchedulerInterface.html#method-i-address_resolve"><code>Fiber::SchedulerInterface#address_resolve</code></a>, <a class="ruby-doc" href="https://docs.ruby-lang.org/en/3.1/Fiber/SchedulerInterface.html#method-i-timeout_after"><code>Fiber::SchedulerInterface#timeout_after</code></a>, <a class="ruby-doc" href="https://docs.ruby-lang.org/en/3.1/Fiber/SchedulerInterface.html#method-i-io_read"><code>Fiber::SchedulerInterface#io_read</code></a>, <a class="ruby-doc" href="https://docs.ruby-lang.org/en/3.1/Fiber/SchedulerInterface.html#method-i-io_write"><code>Fiber::SchedulerInterface#io_write</code></a>)

### `Ractor`[](#ractor)

* [3.0](3.0.md#ractors) **Ractors introduced** (<a class="ruby-doc" href="https://docs.ruby-lang.org/en/3.0.0/Ractor.html"><code>Ractor</code></a> (class documentation), <a class="ruby-doc" href="https://docs.ruby-lang.org/en/3.0.0/doc/ractor_md.html"><code>doc/ractor.md</code></a> (design documentation).)
* [3.1](3.1.md#ractors-can-access-module-instance-variables) Ractors can access module instance variables (<a class="ruby-doc" href="https://docs.ruby-lang.org/en/3.1/Ractor.html#class-Ractor-label-Shareable+and+unshareable+objects">Ractor#Shareable and unshareable objects</a> (docs aren't updated yet))

## Debugging and internals[](#debugging-and-internals)

* [2.6](2.6.md#rubyvmabstractsyntaxtree) <a class="ruby-doc" href="https://ruby-doc.org/core-2.6/RubyVM/AbstractSyntaxTree.html"><code>RubyVM::AbstractSyntaxTree</code></a> introduced
* [2.6](2.6.md#rubyvmresolve_feature_path) `RubyVM.resolve_feature_path`
* [2.7](2.7.md#load_pathresolve_feature_path) ...and was renamed to `$LOAD_PATH.resolve_feature_path`
* [2.7](2.7.md#resolve_feature_path-behavior-for-loaded-features-fixed) `$LOAD_PATH.resolve_feature_path` behavior for loaded features fixed (— _(see above)_)
* [3.1](3.1.md#load_pathresolve_feature_path-does-not-raise) `$LOAD_PATH.resolve_feature_path` does not raise (<a class="ruby-doc" href="https://docs.ruby-lang.org/en/3.1/doc/globals_rdoc.html"><code>doc/globals.rdoc</code></a>)

### `Binding`[](#binding)

TODO: short explanation

* **2.1** `#local_variable_get(symbol)`, `#local_variable_set(symbol, obj)`, `#local_variable_defined?(symbol)`
* **2.2** `#local_variables`
* **2.2** `#receiver`
* [2.6](2.6.md#bindingsource_location) `#source_location` (<a class="ruby-doc" href="https://ruby-doc.org/core-2.6/Binding.html#method-i-source_location"><code>Binding#source_location</code></a>)

### `GC`[](#gc)

TODO: Explanation that "Not algorithms"

* **2.0** `GC::Profiler.raw_data` which returns raw profile data for GC.
* **2.1** introduced the generational GC a.k.a RGenGC.
* **2.2** `GC.latest_gc_info` returns `:state` to represent current GC status.
* **2.2** Introduce incremental marking for major GC. [Feature #10137]
* **2.2** Rename `GC.stat` entries
* [2.7](2.7.md#gccompact) `GC.compact` (<a class="ruby-doc" href="https://ruby-doc.org/core-2.7.0/GC.html#method-c-compact"><code>GC.compact</code></a>)
* [3.0](3.0.md#gcauto_compact-accessor) `GC.auto_compact` accessor (<a class="ruby-doc" href="https://docs.ruby-lang.org/en/3.0.0/GC.html#method-c-auto_compact"><code>GC.auto_compact</code></a>, <a class="ruby-doc" href="https://docs.ruby-lang.org/en/3.0.0/GC.html#method-c-auto_compact-3D"><code>GC.auto_compact=</code></a>)
* [3.1](3.1.md#gc-measuring-total-time) Measuring total time spent in GC (<a class="ruby-doc" href="https://docs.ruby-lang.org/en/3.1/GC.html#method-c-measure_total_time"><code>GC.measure_total_time</code></a>, <a class="ruby-doc" href="https://docs.ruby-lang.org/en/3.1/GC.html#method-c-measure_total_time-3D"><code>GC.measure_total_time=</code></a>, <a class="ruby-doc" href="https://docs.ruby-lang.org/en/3.1/GC.html#method-c-stat"><code>GC.stat</code></a>, <a class="ruby-doc" href="https://docs.ruby-lang.org/en/3.1/GC.html#method-c-total_time"><code>GC.total_time</code></a>)

### `TracePoint`[](#tracepoint)

* **2.0** **`TracePoint` class is introduced** as a replacement of `set_trace_func`
* [2.4](2.4.md#tracepointcallee_id) `#callee_id` (<a class="ruby-doc" href="https://ruby-doc.org/core-2.4.0/TracePoint.html#method-i-callee_id"><code>TracePoint#callee_id</code></a>)
* [2.6](2.6.md#parameters) `#parameters` (<a class="ruby-doc" href="https://ruby-doc.org/core-2.6/TracePoint.html#method-i-parameters"><code>TracePoint#parameters</code></a>)
* [2.6](2.6.md#script_compiled-event) `:script_compiled` event (<a class="ruby-doc" href="https://ruby-doc.org/core-2.6/TracePoint.html#class-TracePoint-label-Events">TracePoint: Events</a> (though new event seems to be omitted), <a class="ruby-doc" href="https://ruby-doc.org/core-2.6/TracePoint.html#method-i-instruction_sequence"><code>TracePoint#instruction_sequence</code></a>, <a class="ruby-doc" href="https://ruby-doc.org/core-2.6/TracePoint.html#method-i-eval_script"><code>TracePoint#eval_script</code></a>)
* [2.6](2.6.md#enable-new-params-target-and-target_line) `#enable`: new params `target:` and `target_line:` (<a class="ruby-doc" href="https://ruby-doc.org/core-2.6/TracePoint.html#method-i-enable"><code>TracePoint#enable</code></a> (not much, though...))
* [3.1](3.1.md#tracepointallow_reentry) `.allow_reentry` (<a class="ruby-doc" href="https://docs.ruby-lang.org/en/3.1/TracePoint.html#method-c-allow_reentry"><code>TracePoint.allow_reentry</code></a>)

### `RubyVM::InstructionSequence`[](#rubyvminstructionsequence)

* **2.0** `RubyVM::InstructionSequence.of` to get the instruction sequence from a method or a block.
* **2.0** `RubyVM::InstructionSequence#path`, `#absolute_path`, `#label`, `#base_label` and `#first_lineno` to retrieve information from where the instruction sequence was defined.
* **2.3** `RubyVM::InstructionSequence#to_binary(extra_data = nil)`
* **2.3** `RubyVM::InstructionSequence.load_from_binary(binary)`
* **2.3** `RubyVM::InstructionSequence.load_from_binary_extra_data(binary)`
* [2.5](2.5.md#rubyvminstructionsequence-new-methods) <a class="ruby-doc" href="https://ruby-doc.org/core-2.5.0/RubyVM/InstructionSequence.html#method-i-each_child"><code>RubyVM::InstructionSequence#each_child</code></a>, <a class="ruby-doc" href="https://ruby-doc.org/core-2.5.0/RubyVM/InstructionSequence.html#method-i-trace_points"><code>RubyVM::InstructionSequence#trace_points</code></a>

<!--

* [2.5](2.5.md#misc) Misc (—)
* [2.6](2.6.md#misc) Language: Misc (—)
* [2.6](2.6.md#minor-changes) Minor changes (—)
* [2.7](2.7.md#other-syntax-changes) Language: Other syntax changes (—)
* [3.0](3.0.md#other-changes) Language changes: Other changes (—)

* [3.0](3.0.md#randomdefault-behavior-change) `Random::DEFAULT` behavior change (<a class="ruby-doc" href="https://docs.ruby-lang.org/en/3.0.0/Random.html"><code>Random</code></a>)

* [3.1](3.1.md#marshalload-accepts-a-freeze-option) `Marshal.load` accepts a `freeze:` option (<a class="ruby-doc" href="https://docs.ruby-lang.org/en/3.1/Marshal.html#method-c-load"><code>Marshal.load</code></a>)

-->
