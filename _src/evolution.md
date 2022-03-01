---
title: Ruby Evolution
prev: /
next: 3.1
---

# Ruby Evolution

## Generic

* **2.0** Default source encoding is changed to UTF-8 (was US-ASCII)
<!--
* **2.0** No warning for unused variables starting with `_`
-->
<!--
* [2.5](2.5.md#top-level-constant-look-up-is-removed) Top-level constant look-up is removed
-->
* [2.6](2.6.md#non-ascii-constant-names) Non-ASCII constant names
* [2.7](2.7.md#safe-and-taint-concepts-are-deprecated-in-general) "Safe" and "taint" concepts are deprecated in general
* [3.0](3.0.md#changes-in-class-variable-behavior) Changes in class variable behavior
* [3.0](3.0.md#types) **Types**
<!--
* [3.1](3.1.md#multiple-assignment-evaluation-order-change) Multiple assignment evaluation order change (—)
-->

## Expressions

* **2.3** **Safe navigation operator**:
  ```ruby
  s = 'test'
  s&.length # => 4
  s = nil
  s&.length # => nil, instead of NoMethodError
  ```
* [2.4](2.4.md#multiple-assignment-allowed-in-conditional-expression) Multiple assignment allowed in conditional expression
* [2.4](2.4.md#toplevel-return) Toplevel `return`
* [2.7](2.7.md#selfprivate_method) `self.<private_method>` ([doc/syntax/modules_and_classes.rdoc#Visibility](https://ruby-doc.org/core-2.7.0/doc/syntax/modules_and_classes_rdoc.html#label-Visibility))

### Pattern-matching

* [2.7](2.7.md#pattern-matching) **Pattern-matching introduced as an experimental feature**
* [3.0](3.0.md#one-line-pattern-matching-with-) `=>` pattern-matching expression introduced
  ```ruby
  {a: 1, b: 2} => {a:} # -- deconstructs and assigns to local variable `a`; fails if pattern not matched
  long.chain.of.computations => result # can also be used as a "rightward assignment"
  ```
* [3.0](3.0.md#in-as-a-truefalse-check) `in` pattern-matching expression repurposed as a `true`/`false` check
 ```ruby
  if {a: 1, b: 2} in {a:} # just "check if match", returning true/false; also deconstructs
  # ...
  ```
* [3.0](3.0.md#find-pattern) Find pattern ([doc/syntax/pattern_matching.rdoc](https://docs.ruby-lang.org/en/3.0.0/doc/syntax/pattern_matching_rdoc.html))
* [3.1](3.1.md#expressions-and-non-local-variables-allowed-in-pin-operator-) Expressions and non-local variables allowed in pin operator `^` ([doc/syntax/pattern_matching.rdoc#Variable pinning](https://docs.ruby-lang.org/en/3.1/doc/syntax/pattern_matching_rdoc.html#label-Variable+pinning))
* [3.1](3.1.md#parentheses-can-be-omitted-in-one-line-pattern-matching) Parentheses can be omitted in one-line pattern matching:
  ```ruby
  {a: 1, b: 2} => a:
  ```

## `Kernel`

TODO: Short explanation

* **2.0** `#__dir__`: absolute path to current source file
* **2.0** `#caller_locations` which returns an array of frame information objects.
* **2.0** `#caller` accepts second optional argument `n` which specify required caller size.
* **2.2** `#throw` raises `UncaughtThrowError`, subclass of `ArgumentError` when there is no corresponding catch block, instead of `ArgumentError`.
* **2.3** `#loop`: when stopped by a `StopIteration` exception, returns what the enumerator has returned instead of `nil`
* [2.5](2.5.md#pp) `#pp` is available without `require 'pp'`
* [2.6](2.6.md#numeric-methods-have-exception-argument) `<Numeric>(exception: true/false)` argument ([Kernel#Integer](https://ruby-doc.org/core-2.6/Kernel.html#method-i-Integer), [Kernel#Float](https://ruby-doc.org/core-2.6/Kernel.html#method-i-Float), [Kernel#Rational](https://ruby-doc.org/core-2.6/Kernel.html#method-i-Rational), [Kernel#Complex](https://ruby-doc.org/core-2.6/Kernel.html#method-i-Complex), [Kernel#BigDecimal](https://ruby-doc.org/stdlib-2.6/libdoc/bigdecimal/rdoc/Kernel.html#method-i-BigDecimal))
* [2.6](2.6.md#system-has-exception-argument) `#system(exception: true/false)` argument ([Kernel#system](https://ruby-doc.org/core-2.6/Kernel.html#method-i-system) (unfortunately, seems documentation haven't been updated with new feature))
<!--
* [3.0](3.0.md#kerneleval-changed-processing-of-__file__-and-__line__) `#eval` changed processing of `__FILE__` and `__LINE__` (—)
-->
* [3.1](3.1.md#kernelload-module-as-a-second-argument) `#load` allows to pass module as a second argument ([Kernel#load](https://docs.ruby-lang.org/en/3.1/Kernel.html#method-i-load))


## `Object`

* **2.0** `respond_to?` against a protected method now returns false unless the second argument is true.
* **2.0** `#inspect` does not call `#to_s` anymore (it used to call redefined `#to_s`).
* **2.0** `#respond_to_missing?`, `#initialize_clone`, `#initialize_dup` are now private.
* **2.1** `#singleton_method`
* **2.2** `#itself`
* [2.5](2.5.md#yield_self) / [2.6](2.6.md#then-as-an-alias-for-yield_self) **`#then`** (initially introduced as `#yield_self`)

## Methods and `Method` class

* **2.0** Added keyword arguments.
* **2.0** top-level `define_method` which defines a global function.
* **2.1** Required keyword arguments
* **2.1** `def` now returns the symbol of its name instead of nil.
* **2.1** `Module#define_method` and `Object#define_singleton_method` now return the symbols of the defined methods, not the methods/procs
* **2.2** `Method#curry`
* **2.2** `Method#super_method`
* [2.5](2.5.md#method) `Method#===` ([Method#===](https://ruby-doc.org/core-2.5.0/Method.html#method-i-3D-3D-3D))
* [2.7](2.7.md#keyword-argument-related-changes) Big Keyword Argument Separation
* [2.7](2.7.md#keyword-argument-related-changes) Introduce argument forwarding with `method(...)`
* [2.7](2.7.md#better-methodinspect) Better `Method#inspect` ([Method#inspect](https://ruby-doc.org/core-2.7.0/Method.html#method-i-inspect))
* [2.7](2.7.md#unboundmethodbind_call) `UnboundMethod#bind_call` ([UnboundMethod#bind_call](https://ruby-doc.org/core-2.7.0/UnboundMethod.html#method-i-bind_call))
* [3.0](3.0.md#arguments-forwarding--supports-leading-arguments) Arguments forwarding (`...`) supports leading arguments ([doc/syntax/methods.rdoc](https://docs.ruby-lang.org/en/master/doc/syntax/methods_rdoc.html#label-Argument+forwarding) _<small>(the link is to a `master` version, docs were merged post 3.0 release)</small>_)
* [3.0](3.0.md#endless-method-definition) "Endless" method definition ([doc/syntax/methods.rdoc](https://docs.ruby-lang.org/en/master/doc/syntax/methods_rdoc.html) _<small>(the link is to a `master` version, docs were merged post 3.0 release)</small>_)
* [3.1](3.1.md#methodunboundmethod-public-private-protected) `Method`/`UnboundMethod`: `#public?`, `#private?`, `#protected?` ([Method#private?](https://docs.ruby-lang.org/en/3.1/Method.html#method-i-private-3F), [UnboundMethod#private?](https://docs.ruby-lang.org/en/3.1/UnboundMethod.html#method-i-private-3F))
<!--
* [3.1](3.1.md#inside-endless-method-definitions-method-calls-without-parenthesis-are-allowed) Inside "endless" method definitions, method calls without parenthesis are allowed (— ([doc/syntax/methods.rdoc](https://docs.ruby-lang.org/en/3.1/doc/syntax/methods_rdoc.html) doesn't mention new or old behavior.))
-->
* [3.1](3.1.md#values-in-hash-literals-and-keyword-arguments-can-be-omitted) Values in keyword arguments can be omitted ( [doc/syntax/literals.rdoc#Hash Literals](https://docs.ruby-lang.org/en/3.1/doc/syntax/literals_rdoc.html#label-Hash+Literals), [doc/methods.rdoc#Keyword Arguments](https://docs.ruby-lang.org/en/3.1/doc/syntax/methods_rdoc.html#label-Keyword+Arguments), [Hash](https://docs.ruby-lang.org/en/3.1/Hash.html))
* [3.1](3.1.md#anonymous-block-argument) Anonymous block argument ([doc/syntax/methods.rdoc#Block Argument](https://docs.ruby-lang.org/en/3.1/doc/syntax/methods_rdoc.html#label-Block+Argument))

## Procs, blocks and `Proc` class

* **2.0** removed `Proc#==` and `#eql?` so two procs are == only when they are the same object.
<!--
* **2.1** Returning from lambda proc now always exits from the Proc, not from the method where the lambda is created.  Returning from non-lambda proc exits from the method, same as the former behavior.
-->
* **2.2** `ArgumentError` is no longer raised when lambda `Proc` is passed as a block, and the number of yielded arguments does not match the formal arguments of the lambda, if just an array is yielded and its length matches.
* [2.6](2.6.md#proc-composition) `Proc` composition with [>>](https://docs.ruby-lang.org/en/2.6.0/Proc.html#method-i-3E-3E) and [<<](https://docs.ruby-lang.org/en/2.6.0/Proc.html#method-i-3C-3C):
  ```ruby
  PROCESSOR = proc { |str| '{' + str + '}' } >> :upcase.to_proc >> TODO
  %w[test me please].map(&PROCESSORS) # => TODO
  ```
* [2.7](2.7.md#numbered-block-parameters) [Numbered block parameters](https://docs.ruby-lang.org/en/2.7.0/Proc.html#class-Proc-label-Numbered+parameters):
  ```ruby
  [1, 2, 3].map { _1 * 100 } # => 100, 200, 300
  ```
<!--
* [3.0](3.0.md#procs-with-rest-arguments-and-keywords-change-of-autosplatting-behavior) Keyword arguments are now fully separated from positional arguments: Procs with "rest" arguments and keywords: change of autosplatting behavior (—)
* [3.0](3.0.md#symbolto_proc-reported-as-lambda) Procs/lambdas: `Symbol#to_proc` reported as lambda (—)
* [3.0](3.0.md#kernellambda-warns-if-called-without-a-literal-block) `Kernel#lambda` warns if called without a literal block (—)
* [3.0](3.0.md#proc-and-eql) Procs/lambdas: `Proc#==` and `#eql?` ([Proc#==](https://docs.ruby-lang.org/en/3.0.0/Proc.html#method-i-3D-3D))
-->

## `Module`

* **2.0** `Module#define_method` accepts a UnboundMethod from a Module.
* **2.0** `Module#prepend`, `.prepended` and `.prepend_features`
* **2.0** `Module#const_get` accepts a qualified constant string, e.g. `Object.const_get("Foo::Bar::Baz")`
* **2.1** `Module#ancestors`
* **2.1** The ancestors of a singleton class now include singleton classes,  in particular itself.
* **2.1** `Module#singleton_class?`
* **2.1** `Module#include` and `#prepend` are now public methods.
* **2.3** `Module#deprecate_constant`
* [2.5](2.5.md#module-methods-for-defining-methods-and-accessors-became-public) `Module`: methods for defining methods and accessors became public (—)
* [2.6](2.6.md#modulemethod_defined-inherit-argument) `Module#method_defined?`: `inherit` argument ([Module#method_defined?](https://ruby-doc.org/core-2.6/Module.html#method-i-method_defined-3F), [Module#private_method_defined?](https://ruby-doc.org/core-2.6/Module.html#method-i-private_method_defined-3F), [Module#protected_method_defined?](https://ruby-doc.org/core-2.6/Module.html#method-i-protected_method_defined-3F), [Module#public_method_defined?](https://ruby-doc.org/core-2.6/Module.html#method-i-public_method_defined-3F))
* [2.7](2.7.md#const_source_location) `Module#const_source_location` ([Module#const_source_location](https://ruby-doc.org/core-2.7.0/Module.html#method-i-const_source_location))
* [2.7](2.7.md#autoload-inherit-argument) `Module#autoload?`: `inherit` argument ([Module#autoload?](https://ruby-doc.org/core-2.7.0/Module.html#method-i-autoload-3F))
* [3.0](3.0.md#include-and-prepend-now-affects-modules-including-the-receiver) `Module#include` and `#prepend` now affects modules including the receiver (—)
* [3.0](3.0.md#improved-method-visibility-declaration) `Module`: Improved method visibility declaration (—)
* [3.1](3.1.md#classsubclasses) `Class#subclasses` ([Class#subclasses](https://docs.ruby-lang.org/en/3.1/Class.html#method-i-subclasses))
* [3.1](3.1.md#moduleprepend-behavior-change) `Module#prepend` behavior change ([Module#prepend](https://docs.ruby-lang.org/en/3.1/Module.html#method-i-prepend) _(not that it actually documents new—or old—behavior)_)
* [3.1](3.1.md#moduleprivate-public-protected-and-module_function-return-their-arguments) `Module#private`, `#public`, `#protected`, and `#module_function` return their arguments ([Module#private](https://docs.ruby-lang.org/en/3.1/Module.html#method-i-private),   [Module#public](https://docs.ruby-lang.org/en/3.1/Module.html#method-i-public), [Module#protected](https://docs.ruby-lang.org/en/3.1/Module.html#method-i-protected), [Module#module_function](https://docs.ruby-lang.org/en/3.1/Module.html#method-i-module_function))

## `Comparable`

Included in many classes to implement `#<`, `#<=`, etc. Can be included in any object that defines method `#<=>` for object comparison (returning `-1`, `0`, `1`, or `nil`), and defines the rest.

* **2.3** `#==` no longer rescues exceptions (so if owner class' `<=>` raises, the user will see original exception)
* [2.4](2.4.md#comparableclamp) [Comparable#clamp](https://ruby-doc.org/core-2.4.0/Comparable.html#method-i-clamp):
  ```ruby
  123.clamp(50, 100) # => 100
  23.clamp(50, 100) # => 50
  53.clamp(50, 100) # => 53
  ```
* [2.7](2.7.md#comparableclamp-with-range) `#clamp` supports `Range` argument:
  ```ruby
  123.clamp(0..100)
  # one-sided clamp with endless/beginless ranges work too!
  -123.clamp(0..) #=> 0
  123.clamp(..100) #=> 100
  ```

## `Numeric`

* **2.1** `Fixnum#bit_length`, `Bignum#bit_length`
* **2.1** `Numeric#step` allows the limit argument to be omitted. Keyword arguments `to` and `by` are introduced for ease of use.
* **2.1** Added suffixes for integer and float literals: `r`, `i`, and `ri`.
<!--
* **2.2** `Math.log` now raises `Math::DomainError` instead of returning NaN if the  base is less than 0, and returns NaN instead of -infinity if both of two arguments are 0.
* **2.2** `Math.atan2` now returns values like as expected by C99 if both two arguments are infinity.
-->
* **2.2** `Float#next_float`, `#prev_float`
* **2.3** `Numeric#positive?` and `#negative?`
* [2.4](2.4.md#fixnum-and-bignum-are-unified-into-integer) `Fixnum` and `Bignum` are unified into [Integer](https://ruby-doc.org/core-2.4.0/Integer.html)
* [2.4](2.4.md#numericfinite-and-infinite) `Numeric#finite?` and `#infinite?` ([Numeric#infinite?](https://ruby-doc.org/core-2.4.0/Numeric.html#method-i-infinite-3F), [Numeric#finite?](https://ruby-doc.org/core-2.4.0/Numeric.html#method-i-finite-3F))
* [2.4](2.4.md#integerdigits) `Integer#digits` ([Integer.html#digits](https://ruby-doc.org/core-2.4.0/Integer.html#method-i-digits))
* [2.4](2.4.md#ndigits-optional-argument-for-rounding-methods) `ndigits` optional argument for rounding methods ([Numeric#ceil](https://ruby-doc.org/core-2.4.0/Numeric.html#method-i-ceil), [Numeric#floor](https://ruby-doc.org/core-2.4.0/Numeric.html#method-i-floor), [Numeric#truncate](https://ruby-doc.org/core-2.4.0/Numeric.html#method-i-truncate) (in fact, `Integer` and `Float` classes are affected, because `Rational` had the same option long ago).)
* [2.4](2.4.md#half-option-for-round-method) `half:` option for `#round` method ((feature introduced in 2.4, but comprehensive docs were written in 2.5) [Integer#round](https://ruby-doc.org/core-2.5.0/Integer.html#method-i-round), [Float#round](https://ruby-doc.org/core-2.5.0/Float.html#method-i-round), [Rational#round](https://ruby-doc.org/core-2.5.0/Rational.html#method-i-round))
* [2.5](2.5.md#pow-modulo-argument) `Integer#pow`: modulo argument ([Integer#pow](https://ruby-doc.org/core-2.5.0/Integer.html#method-i-pow))
* [2.5](2.5.md#allbits-anybits-nobits) `Integer#allbits?`, `#anybits?`, `#nobits?` ([Integer#allbits?](https://ruby-doc.org/core-2.5.0/Integer.html#method-i-allbits-3F), [Integer#anybits?](https://ruby-doc.org/core-2.5.0/Integer.html#method-i-allbits-3F), [Integer#nobits?](https://ruby-doc.org/core-2.5.0/Integer.html#method-i-allbits-3F))
  ```ruby
  # classic way of checking some flags:
  (object.flags & FLAG_ADMIN) > 0
  # new way:
  object.flags.anybits?(FLAG_ADMIN)
  ```
* [2.5](2.5.md#sqrt) `Integer.sqrt` ([Integer.sqrt](https://ruby-doc.org/core-2.5.0/Integer.html#method-c-sqrt))
* [2.7](2.7.md#integer-with-range) `Integer[]` with range ([Integer#[]](https://ruby-doc.org/core-2.7.0/Integer.html#method-i-5B-5D))
<!--
* [2.7](2.7.md#complex) `Complex#<=>` ([Complex#<=>](https://ruby-doc.org/core-2.7.0/Complex.html#method-i-3C-3D-3E))
-->
* [3.1](3.1.md#integertry_convert) [Integer.try_convert](https://docs.ruby-lang.org/en/3.1/Integer.html#method-c-try_convert)

## Strings, symbols and regexps

* **2.0** Switch Regexp engine to [Onigmo](https://github.com/k-takata/Onigmo)
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
* [2.4](2.4.md#unicode-case-conversions) Unicode case conversions ([String#downcase](https://ruby-doc.org/core-2.4.0/String.html#method-i-downcase), [String#upcase](https://ruby-doc.org/core-2.4.0/String.html#method-i-upcase), [String#capitalize](https://ruby-doc.org/core-2.4.0/String.html#method-i-capitalize), [String#swapcase](https://ruby-doc.org/core-2.4.0/String.html#method-i-swapcase), [Symbol#downcase](https://ruby-doc.org/core-2.4.0/Symbol.html#method-i-downcase), [Symbol#upcase](https://ruby-doc.org/core-2.4.0/Symbol.html#method-i-upcase), [Symbol#capitalize](https://ruby-doc.org/core-2.4.0/Symbol.html#method-i-capitalize), [Symbol#swapcase](https://ruby-doc.org/core-2.4.0/Symbol.html#method-i-swapcase),)
* [2.4](2.4.md#stringnewcapacity-size) `String.new(capacity: size)` ([String::new](https://ruby-doc.org/core-2.4.0/String.html#method-c-new))
* [2.4](2.4.md#casecmp) `#casecmp?` ([String#casecmp?](https://ruby-doc.org/core-2.4.0/String.html#method-i-casecmp-3F), [Symbol#casecmp?](https://ruby-doc.org/core-2.4.0/Symbol.html#method-i-casecmp-3F))
* [2.4](2.4.md#stringconcat-and-prepend-accept-multiple-arguments) `String#concat` and `#prepend` accept multiple arguments ([String#concat](https://ruby-doc.org/core-2.4.0/String.html#method-i-concat), [String#prepend](https://ruby-doc.org/core-2.4.0/String.html#method-i-prepend))
* [2.4](2.4.md#stringunpack1) `String#unpack1` ([String#unpack1](https://ruby-doc.org/core-2.4.0/String.html#method-i-unpack1))
* [2.4](2.4.md#match-method) `#match?` method ([Regexp#match?](https://ruby-doc.org/core-2.4.0/Regexp.html#method-i-match-3F), [String#match?](https://ruby-doc.org/core-2.4.0/String.html#method-i-match-3F), [Symbol#match?](https://ruby-doc.org/core-2.4.0/Symbol.html#method-i-match-3F))
* [2.4](2.4.md#matchdata-better-support-for-named-captures) `MatchData`: better support for named captures ([MatchData#named_captures](https://ruby-doc.org/core-2.4.0/MatchData.html#method-i-named_captures), [MatchData#values_at](https://ruby-doc.org/core-2.4.0/MatchData.html#method-i-values_at))
* [2.5](2.5.md#delete_prefix-delete_prefix-delete_suffix-delete_suffix) `String#delete_prefix`, `#delete_prefix!`, `#delete_suffix`, `#delete_suffix!` ([String#delete_prefix](https://ruby-doc.org/core-2.5.0/String.html#method-i-delete_prefix), [String#delete_suffix](https://ruby-doc.org/core-2.5.0/String.html#method-i-delete_suffix))
* [2.5](2.5.md#each_grapheme_cluster-and-grapheme_clusters) `String#each_grapheme_cluster` and `#grapheme_clusters` ([String#each_grapheme_cluster](https://ruby-doc.org/core-2.5.0/String.html#method-i-each_grapheme_cluster), [String#grapheme_clusters](https://ruby-doc.org/core-2.5.0/String.html#method-i-grapheme_clusters))
* [2.5](2.5.md#undump) `String#undump` ([String#undump](https://ruby-doc.org/core-2.5.0/String.html#method-i-undump))
* [2.5](2.5.md#casecmp-and-casecmp-return-nil-for-non-string-arguments) `String#casecmp` and `#casecmp?` return `nil` for non-string arguments ([String#casecmp](https://ruby-doc.org/core-2.5.0/String.html#method-i-casecmp), [String#casecmp?](https://ruby-doc.org/core-2.5.0/String.html#method-i-casecmp-3F))
* [2.5](2.5.md#start_with-accepts-a-regexp) `String#start_with?` accepts a regexp ([String#start_with?](https://ruby-doc.org/core-2.6/String.html#method-i-start_with-3F) (introduced in 2.5, but documented in 2.6))
* [2.5](2.5.md#string--optimized-for-memory-preserving) `String#-@` optimized for memory preserving ([String#-@](https://ruby-doc.org/core-2.5.0/String.html#method-i-2D-40))
* [2.5](2.5.md#regexp-absence-operator) `Regexp`: absence operator (—)
* [2.6](2.6.md#stringsplit-with-block) `String#split` with block ([String#split](https://ruby-doc.org/core-2.6/String.html#method-i-split))
* [2.7](2.7.md#symbolstart_with-and-end_with) `Symbol#start_with?` and `#end_with?` ([Symbol#end_with?](https://ruby-doc.org/core-2.7.0/Symbol.html#method-i-end_with-3F), [Symbol#start_with?](https://ruby-doc.org/core-2.7.0/Symbol.html#method-i-start_with-3F))
* [3.0](3.0.md#string-always-returning-string) `String`: always returning `String` (—)
* [3.1](3.1.md#stringunpack-and-unpack1-offset-argument) `String#unpack` and `#unpack1`: `offset:` argument ([String#unpack](https://docs.ruby-lang.org/en/3.1/String.html#method-i-unpack), [String#unpack1](https://docs.ruby-lang.org/en/3.1/String.html#method-i-unpack1))
* [3.1](3.1.md#matchdatamatch-and-match_length) `MatchData#match` and `#match_length` ([MatchData#match](https://docs.ruby-lang.org/en/3.1/MatchData.html#method-i-match), [MatchData#match_length](https://docs.ruby-lang.org/en/3.1/MatchData.html#method-i-match_length))
* [3.1](3.1.md#iobuffer) `IO::Buffer` ([IO::Buffer](https://docs.ruby-lang.org/en/3.1/IO/Buffer.html))

## `Struct`

* [2.5](2.5.md#struct-with-keyword-arguments) **Structs initialized by keywords**:
  ```ruby
  User = Struct.new(:name, :email, keyword_init: true)
  User.new(name: 'Matz', email: 'matz@ruby-lang.org')
  ```
* [3.1](3.1.md#warning-on-passing-keywords-to-a-non-keyword-initialized-struct) Warning on passing keywords to a non-keyword-initialized struct (—)
* [3.1](3.1.md#structclasskeyword_init) `StructClass#keyword_init?` ([Strict::keyword_init?](https://docs.ruby-lang.org/en/3.1/Struct.html#method-c-keyword_init-3F))

## `Time`

* **2.0** `Time#to_s` now returns US-ASCII encoding instead of BINARY.
* [2.5](2.5.md#timeat-units) `Time.at`: units ([Time.at](https://ruby-doc.org/core-2.5.0/Time.html#method-c-at))
* [2.6](2.6.md#time-support-for-timezones) **Support for [timezones](https://ruby-doc.org/core-2.6/Time.html#class-Time-label-Timezone+argument)**
* [2.7](2.7.md#floor-and-ceil) `#floor` and `#ceil` ([Time#floor](https://ruby-doc.org/core-2.7.0/Time.html#method-i-floor), [Time#ceil](https://ruby-doc.org/core-2.7.0/Time.html#method-i-ceil))
* [2.7](2.7.md#inspect-includes-subseconds) `Time#inspect` includes subseconds ([Time#inspect](https://ruby-doc.org/core-2.7.0/Time.html#method-i-inspect))
* [3.1](3.1.md#in-parameter-for-constructing-time) `in:` parameter for constructing time ([Time.new](https://docs.ruby-lang.org/en/3.1/Time.html#method-c-new), [Time.at](https://docs.ruby-lang.org/en/3.1/Time.html#method-c-at), [Time.now](https://docs.ruby-lang.org/en/3.1/Time.html#method-c-now))
<!--
* [3.1](3.1.md#strftime-supports--0000-offset) `#strftime` supports `-00:00` offset ([Time#strftime](https://docs.ruby-lang.org/en/3.1/Time.html#method-i-strftime))
-->

## `Range`

* **2.0** `Range#size`
* **2.0** `Range#bsearch`
* [2.6](2.6.md#endless-range-1) **Endless range: `(1..)`**
* [2.6](2.6.md#range-uses-cover-instead-of-include) `#===` uses `#cover?` instead of `#include?` (—)
* [2.6](2.6.md#rangecover-accepts-range-argument) `#cover?` accepts range argument (—)
* [2.6](2.6.md#range-alias) `#%` alias for `#step` (—)
* [2.6](2.6.md#enumeratorarithmeticsequence) `Enumerator::ArithmeticSequence` ([Enumerator::ArithmeticSequence](https://ruby-doc.org/core-2.6.0.preview2/Enumerator/ArithmeticSequence.html), [Range#step](https://ruby-doc.org/core-2.6/Range.html#method-i-step), [Numeric#step](https://ruby-doc.org/core-2.6/Numeric.html#method-i-step))
* [2.7](2.7.md#beginless-range) **Beginless range: `(...100)`**
<!--
* [2.7](2.7.md#for-string) `#===` for `String` ([Range#===](https://ruby-doc.org/core-2.7.0/Range.html#method-i-3D-3D-3D))
* [2.7](2.7.md#minmax-implementation-change) `#minmax` implementation change ([Range#minmax](https://ruby-doc.org/core-2.7.0/Range.html#method-i-minmax))
-->

## Enumerables and collections

* **2.3** `#dig` to `Array`, `Hash`, and `Struct`

### `Enumerable`

* **2.0** added `Enumerable#lazy` method for lazy enumeration. new class `Enumerator::Lazy` for lazy enumeration
* **2.1** `#to_h`
* **2.2** `#slice_after`, `#slice_when`
* **2.2** `#min`, `#min_by`, `#max` and `#max_by` supports optional argument to return multiple elements.
* **2.3** `#grep_v`
* **2.3** `#chunk_while`
* **2.3** `Enumerable#chunk` and `#slice_before` no longer takes the `initial_state` argument
* [2.4](2.4.md#enumerablechunk-without-a-block-returns-an-enumerator) `Enumerable#chunk` without a block returns an `Enumerator` ([Enumerable#chunk](https://ruby-doc.org/core-2.4.0/Enumerable.html#method-i-chunk))
* [2.4](2.4.md#sum) `#sum` ([Enumerable#sum](https://ruby-doc.org/core-2.4.0/Enumerable.html#method-i-sum), [Array#sum](https://ruby-doc.org/core-2.4.0/Array.html#method-i-sum))
* [2.4](2.4.md#uniq) `#uniq` ([Enumerable#iniq](https://ruby-doc.org/core-2.4.0/Enumerable.html#method-i-uniq), [Enumerator::Lazy#uniq](https://ruby-doc.org/core-2.4.0/Enumerator/Lazy.html#method-i-uniq))
* [2.5](2.5.md#enumerableany-all-none-and-one-accept-patterns) `#any?`, `#all?`, `#none?`, and `#one?` accept patterns ([Enumerable#all?](https://ruby-doc.org/core-2.5.0/Enumerable.html#method-i-all-3F), [Enumerable#any?](https://ruby-doc.org/core-2.5.0/Enumerable.html#method-i-any-3F), [Enumerable#none?](https://ruby-doc.org/core-2.5.0/Enumerable.html#method-i-none-3F), [Enumerable#one?](https://ruby-doc.org/core-2.5.0/Enumerable.html#method-i-one-3F))
* [2.6](2.6.md#filterfilter) `#filter`/`#filter!` as alias for `#select`/`#select!` (as more familiar for users coming from other languages)
* [2.6](2.6.md#to_h-with-a-block) `#to_h` with a block ([Enumerable#to_h](https://ruby-doc.org/core-2.6/Enumerable.html#method-i-to_h), [Array#to_h](https://ruby-doc.org/core-2.6/Array.html#method-i-to_h), [ENV.to_h](https://ruby-doc.org/core-2.6/ENV.html#method-c-to_h), [Hash#to_h](https://ruby-doc.org/core-2.6/Hash.html#method-i-to_h), [Struct#to_h](https://ruby-doc.org/core-2.6/Struct.html#method-i-to_h))
* [2.7](2.7.md#enumerablefilter_map) [Enumerable#filter_map](https://ruby-doc.org/core-2.7.0/Enumerable.html#method-i-filter_map)
* [2.7](2.7.md#enumerabletally) [Enumerable#tally](https://ruby-doc.org/core-2.7.0/Enumerable.html#method-i-tally)
* [3.1](3.1.md#enumerabletally-now-accepts-an-optional-hash-to-count) `#tally` now accepts an optional hash to count ([Enumerable#tally](https://docs.ruby-lang.org/en/3.1/Enumerable.html#method-i-tally))
* [3.1](3.1.md#enumerableeach_cons-and-each_slice-return-a-receiver) `#each_cons` and `#each_slice` return a receiver ([Enumerable#each_cons](https://docs.ruby-lang.org/en/3.1/Enumerable.html#method-i-each_cons), [Enumerable#each_slice](https://docs.ruby-lang.org/en/3.1/Enumerable.html#method-i-each_slice))
* [3.1](3.1.md#enumerablecompact-and-enumeratorlazycompact) `#compact` ([Enumerable#compact](https://docs.ruby-lang.org/en/3.1/Enumerable.html#method-i-compact), [Enumerator::Lazy#compact](https://docs.ruby-lang.org/en/3.1/Enumerator/Lazy.html#method-i-compact))

### `Enumerator`

* **2.0** added `Enumerator#size` for lazy size evaluation. `Enumerator.new` accept an argument for lazy size evaluation.
* **2.0** `Kernel#to_enum` and `#enum_for` accept a block for lazy size evaluation.
* [2.6](2.6.md#enumerator-chaining) `Enumerator` chaining ([Enumerator#+](https://ruby-doc.org/core-2.6/Enumerator.html#method-i-2B), [Enumerable#chain](https://ruby-doc.org/core-2.6/Enumerable.html#method-i-chain), [Enumerator::Chain](https://ruby-doc.org/core-2.6/Enumerator/Chain.html))
* [2.7](2.7.md#enumeratorproduce) `Enumerator.produce` ([Enumerator.produce]())
* [2.7](2.7.md#enumeratorlazyeager) `Enumerator::Lazy#eager` ([Enumerator::Lazy#eager](https://ruby-doc.org/core-2.7.0/Enumerator/Lazy.html#method-i-eager))
* [2.7](2.7.md#enumeratoryielderto_proc) `Enumerator::Yielder#to_proc` ([Enumerator::Yielder#to_proc](https://ruby-doc.org/core-2.7.0/Enumerator/Yielder.html#method-i-to_proc))
* [3.1](3.1.md#enumerablecompact-and-enumeratorlazycompact) `Enumerator::Lazy#compact` ([Enumerable#compact](https://docs.ruby-lang.org/en/3.1/Enumerable.html#method-i-compact), [Enumerator::Lazy#compact](https://docs.ruby-lang.org/en/3.1/Enumerator/Lazy.html#method-i-compact))

### `Array`

* **2.0** `Array#bsearch`
* **2.0** random parameter of `Array#shuffle!` and `#sample` now will be called with one argument, maximum value.
* **2.0** when given Range arguments, `Array#values_at` now returns nil for each value that is out-of-range.
* **2.3** `Array#bsearch_index`
* [2.4](2.4.md#arraymax-and-min) `#max` and `#min` ([Array#max](https://ruby-doc.org/core-2.4.0/Array.html#method-i-max), [Array#min](https://ruby-doc.org/core-2.4.0/Array.html#method-i-max))
* [2.4](2.4.md#arrayconcat-takes-multiple-arguments) `#concat` takes multiple arguments ([Array#concat](https://ruby-doc.org/core-2.4.0/Array.html#method-i-concat))
* [2.4](2.4.md#arraypackbuffer) `#pack(buffer:)` ([Array#pack](https://ruby-doc.org/core-2.4.0/Array.html#method-i-pack))
* [2.5](2.5.md#arrayappend-and-prepend) `#append` and `#prepend` ([Array#append](https://ruby-doc.org/core-2.5.0/Array.html#method-i-append), [Array#prepend](https://ruby-doc.org/core-2.5.0/Array.html#method-i-prepend))
* [2.6](2.6.md#arrayunion-and-arraydifference) `#union` and `#difference` ([Array#union](https://ruby-doc.org/core-2.6/Array.html#method-i-union), [Array#difference](https://ruby-doc.org/core-2.6/Array.html#method-i-difference))
* [2.7](2.7.md#arrayintersection) `#intersection` ([Array#intersection](https://ruby-doc.org/core-2.7.0/Array.html#method-i-intersection))
* [3.0](3.0.md#array-always-returning-array) Always returning `Array` (—)
* [3.0](3.0.md#array-slicing-with-enumeratorarithmeticsequence) Slicing with `Enumerator::ArithmeticSequence` ([Array#[]](https://docs.ruby-lang.org/en/3.0.0/Array.html#method-i-5B-5D))
* [3.1](3.1.md#arrayintersect) `#intersect?` ([Array#intersect?](https://docs.ruby-lang.org/en/3.1/Array.html#method-i-intersect-3F))

### `Hash`

* **2.0** `Hash#to_h` as explicit conversion method, like Array#to_a.
* **2.0** added `nil.to_h` which returns `{}`
* **2.0** `Struct#to_h`
* **2.0** `Kernel#Hash`
* **2.2** Change overriding policy for duplicated key: `{**hash1, **hash2}` contains values of `hash2` for duplicated keys.
* **2.2** Hash literal: Symbol key followed by a colon can be quoted.
* **2.3** `#fetch_values`
* **2.3** `#<=`, `#<`, `#>=`, `#>`
* **2.3** `#to_proc`
* [2.4](2.4.md#hashcompact-and-compact) `#compact` and `#compact!` ([Hash#compact](https://ruby-doc.org/core-2.4.0/Hash.html#method-i-compact), [Hash#compact!](https://ruby-doc.org/core-2.4.0/Hash.html#method-i-compact-21))
* [2.4](2.4.md#hashtransform_values-and-transform_values) `#transform_values` and `#transform_values!` ([Hash#transform_values](https://ruby-doc.org/core-2.4.0/Hash.html#method-i-transform_values), [Hash#transform_values!](https://ruby-doc.org/core-2.4.0/Hash.html#method-i-transform_values-21))
* [2.5](2.5.md#hashtransform_keys-and-transform_keys) `#transform_keys` and `#transform_keys!` ([Hash#transform_keys](https://ruby-doc.org/core-2.5.0/Hash.html#method-i-transform_keys), [Hash#transform_keys!](https://ruby-doc.org/core-2.5.0/Hash.html#method-i-transform_keys-21))
* [2.5](2.5.md#hashslice) `#slice` ([Hash#slice](https://ruby-doc.org/core-2.5.0/Hash.html#method-i-slice))
* [2.6](2.6.md#hashmerge-with-multiple-arguments) `#merge` with multiple arguments ([Hash#merge](https://ruby-doc.org/core-2.6/Hash.html#method-i-merge))
* [3.0](3.0.md#hashexcept) `#except` ([Hash#except](https://docs.ruby-lang.org/en/3.0.0/Hash.html#method-i-except), [ENV.except](https://docs.ruby-lang.org/en/3.0.0/ENV.html#method-c-except))
* [3.0](3.0.md#hashtransform_keys-argument-for-key-renaming) `#transform_keys`: argument for key renaming ([Hash#transform_keys](https://docs.ruby-lang.org/en/3.0.0/Hash.html#method-i-transform_keys))
* [3.0](3.0.md#hasheach-consistently-yields-a-2-element-array-to-lambdas) `#each` consistently yields a 2-element array to lambdas (—)
* [3.1](3.1.md#values-in-hash-literals-and-keyword-arguments-can-be-omitted) Values in Hash literals can be omitted ( [doc/syntax/literals.rdoc#Hash Literals](https://docs.ruby-lang.org/en/3.1/doc/syntax/literals_rdoc.html#label-Hash+Literals), [doc/methods.rdoc#Keyword Arguments](https://docs.ruby-lang.org/en/3.1/doc/syntax/methods_rdoc.html#label-Keyword+Arguments), [Hash](https://docs.ruby-lang.org/en/3.1/Hash.html))

### `Set`

TODO: Explanation, SOME links

* **2.1** `#intersect?` and `#disjoint?`
* **2.4** `#compare_by_identity` and `#compare_by_identity?`
* **2.5** `#to_s` as alias to `#inspect`
* **2.5** `#===` as alias to `#include?`
* **2.5** `#reset`
* **3.0** `SortedSet` has been removed for dependency and performance reasons (it silently depended upon rbtree gem).
* **3.0** `#join` is added as a shorthand for .to_a.join. Discussion: Feature #16991.
* **3.0** `#<=>`

### Other collections

* **2.0** `ObjectSpace::WeakMap` introduced
* **2.3** `Thread::Queue#close` is added to notice a termination
* [2.7](2.7.md#objectspaceweakmap-now-accepts-non-gc-able-objects) `ObjectSpace::WeakMap#[]=` now accepts non-GC-able objects ([WeekMap#[]=](https://ruby-doc.org/core-2.7.0/ObjectSpace/WeakMap.html#method-i-5B-5D-3D))
* [3.1](3.1.md#threadqueueinitialize-initial-values-can-be-passed-to-initializer) `Thread::Queue#initialize`: initial values can be passed to initializer ([Thread::Queue.new](https://docs.ruby-lang.org/en/3.1/Thread/Queue.html#method-c-new))

## Filesystem and IO

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
* [2.4](2.4.md#empty-method-for-filesystem-objects) `#empty?` method for filesystem objects ([Dir#empty?](https://ruby-doc.org/core-2.4.0/Dir.html#method-c-empty-3F), [File#empty?](https://ruby-doc.org/core-2.4.0/File.html#method-c-empty-3F), _(stdlib)_ [Pathname#empty?](https://ruby-doc.org/stdlib-2.4.0/libdoc/pathname/rdoc/Pathname.html#method-i-empty-3F))
* [2.5](2.5.md#iopread-and-pwrite) `IO#pread` and `#pwrite` ([IO#pread](https://ruby-doc.org/core-2.5.0/IO.html#method-i-pread), [IO#pwrite](https://ruby-doc.org/core-2.5.0/IO.html#method-i-pwrite))
* [2.5](2.5.md#iowrite-accepts-multiple-arguments) `IO#write` accepts multiple arguments ([IO#write](https://ruby-doc.org/core-2.5.0/IO.html#method-i-write))
* [2.5](2.5.md#fileopen-better-supports-newline-option) `File.open` better supports `newline:` option (— (it is _almost_ documented by referring from [IO.new](https://ruby-doc.org/core-2.5.0/IO.html#method-c-new) docs to [String#encode](https://ruby-doc.org/core-2.5.0/String.html#method-i-encode) docs, where at least longer form `newline_universal: true` is mentioned))
* [2.5](2.5.md#filepath-raises-when-opened-with-fileconstantstmpfile-option) `File#path` raises when opened with `File::Constants::TMPFILE` option. ([File#path](https://ruby-doc.org/core-2.5.0/File.html#method-c-path))
* [2.5](2.5.md#filelutime) `File.lutime` ([File.lutime](https://ruby-doc.org/core-2.5.0/File.html#method-c-lutime))
* [2.5](2.5.md#dirchildren-and-each_child)  `Dir.children` and `.each_child` ([Dir.children](https://ruby-doc.org/core-2.5.0/Dir.html#method-c-children), [Dir.each_child](https://ruby-doc.org/core-2.5.0/Dir.html#method-c-each_child))
* [2.5](2.5.md#dirglob-base-argument) `Dir.glob`: `base:` argument ([Dir.glob](https://ruby-doc.org/core-2.5.0/Dir.html#method-c-glob))
* [2.6](2.6.md#direach_child-and-dirchildren) `Dir#each_child` and `Dir#children` ([Dir#each_child](https://ruby-doc.org/core-2.6/Dir.html#method-i-each_child), [Dir#children](https://ruby-doc.org/core-2.6/Dir.html#method-i-children))
* [2.6](2.6.md#io-open-mode-x) IO open mode: `'x'` ([IO: Open mode](https://ruby-doc.org/core-2.6/IO.html#method-c-new-label-IO+Open+Mode))
* [2.7](2.7.md#ioset_encoding_by_bom) `IO#set_encoding_by_bom` ([IO#set_encoding_by_bom](https://ruby-doc.org/core-2.7.0/IO.html#method-i-set_encoding_by_bom))
* [2.7](2.7.md#dirglob-and-dir-not-allow-0-separated-patterns) `Dir.glob` and `Dir.[]` not allow `\0`-separated patterns ([Dir.glob](https://ruby-doc.org/core-2.7.0/Dir.html#method-c-glob))
* [2.7](2.7.md#fileextname-returns-a--string-at-a-name-ending-with-a-dot) `File.extname` returns a `"."` string at a name ending with a dot. ([File.extname](https://bugs.ruby-lang.org/issues/15267))
* [3.0](3.0.md#dirglob-and-dir-result-sorting) `Dir.glob` and `Dir.[]` result sorting ([Dir.glob](https://docs.ruby-lang.org/en/3.0.0/Dir.html#method-c-glob))
* [3.1](3.1.md#filedirname-optional-level-to-go-up-the-directory-tree) `File.dirname`: optional `level` to go up the directory tree ([File.dirname](https://docs.ruby-lang.org/en/3.1/File.html#method-c-dirname))

## Exceptions

* **2.0** added `LoadError#path` method to return the file name that could not be loaded.
* **2.1** `Exception#cause` provides the previous exception which has been caught at where raising the new exception.
* **2.3** `NameError#receiver`
* **2.3** `NameError`, `NoMethodError`: `did_you_mean`
* [2.5](2.5.md#rescueelseensure-are-allowed-inside-blocks) `rescue`/`else`/`ensure` are allowed inside blocks (—)
* [2.5](2.5.md#backtrace-and-error-message-in-reverse-order) Backtrace and error message in reverse order (—)
* [2.5](2.5.md#exceptionfull_message) `Exception#full_message` ([Exception#full_message](https://ruby-doc.org/core-2.5.0/Exception.html#method-i-full_message))
* [2.5](2.5.md#keyerrorreceiver-and-key) `KeyError#receiver` and `#key` ([KeyError](https://ruby-doc.org/core-2.5.0/KeyError.html))
* [2.5](2.5.md#new-class-frozenerror) New class: `FrozenError` ([FrozenError](https://ruby-doc.org/core-2.5.0/FrozenError.html))
* [2.5](2.5.md#dont-hide-coercion-errors) Don't hide coercion errors (—)
* [2.6](2.6.md#else-in-exception-handling-context) Language: `else` in exception-handling context (—)
* [2.6](2.6.md#new-arguments-receiver-and-key) New arguments: `receiver:` and `key:` ([NameError::new](https://ruby-doc.org/core-2.6/NameError.html#method-c-new), [NoMethodError::new](https://ruby-doc.org/core-2.6/NoMethodError.html#method-c-new) _(docs not updated)_, [KeyError::new](https://ruby-doc.org/core-2.6/KeyError.html#method-c-new))
* [2.6](2.6.md#exceptionfull_message-options) `Exception#full_message` options ([Exception#full_message](https://ruby-doc.org/core-2.6/Exception.html#method-i-full_message))
* [2.6](2.6.md#exception-output-tweaking) Exception output tweaking (—)
* [2.7](2.7.md#frozenerror-receiver-argument) `FrozenError`: receiver argument ([FrozenError#new](https://ruby-doc.org/core-2.7.0/FrozenError.html#method-c-new))
* [3.0](3.0.md#exception-output-order-is-changed----again) Exception output order is changed -- again (—)
* [3.1](3.1.md#threadbacktracelimit) `Thread::Backtrace.limit` ([Thread::Backtrace.limit](https://docs.ruby-lang.org/en/3.1/Thread/Backtrace.html#method-c-limit))

### `Warning`

* **2.0** `Kernel#warn` accepts multiple args in like `#puts`.
* [2.4](2.4.md#warning-module) `Warning` module introduced (_(introduced in 2.4, but documented in 2.5)_ [Warning](https://ruby-doc.org/core-2.5.0/Warning.html))
* [2.5](2.5.md#warn-uplevel-keyword-argument) `#warn(uplevel: ...)` keyword argument ([Kernel#warn](https://ruby-doc.org/core-2.6/Kernel.html#method-i-warn) (it became somewhat documented at Ruby 2.6, but the feature itself has been available since 2.5))
* [2.5](2.5.md#warn-call-warningwarn) `#warn` calls `Warning.warn` (—)
* [2.7](2.7.md#warning-and-) `Warning::[]` and `::[]=` ([Warning::[]](https://ruby-doc.org/core-2.7.0/Warning.html#method-c-5B-5D), [Warning::[]=](https://ruby-doc.org/core-2.7.0/Warning.html#method-c-5B-5D-3D))
* [3.0](3.0.md#warningwarn-category-keyword-argument) `Warning#warn(category: ....)` keyword argument. ([Warning#warn](https://docs.ruby-lang.org/en/3.0.0/Warning.html#method-i-warn), [Kernel#warn](https://docs.ruby-lang.org/en/3.0.0/Kernel.html#method-i-warn))

## Concurrency and parallelism

### `Thread`

* **2.0** `Thread#thread_variable_get`, `#thread_variable_set`, `#thread_variables`, `#thread_variable?`
* **2.0** `Thread.handle_interrupt` as well as instance and singleton methods `pending_interrupt?` for asynchronous handling of exceptions
* **2.0** `Thread#backtrace_locations` and new class `Thread::Backtrace::Location` to hold backtrace location information. These are returned by `Thread#backtrace_locations` and `Kernel#caller_locations`.
* **2.0** `Thread#join` and `#value` now raises a `ThreadError` if target thread  is the current or main thread.
* **2.3** `Thread#name`, `#name=`
* [2.4](2.4.md#threadreport_on_exception-and-threadreport_on_exception) `#report_on_exception` and `.report_on_exception` ([Thread.report_on_exception](https://ruby-doc.org/core-2.4.0/Thread.html#method-c-report_on_exception), [Thread.report_on_exception=](https://ruby-doc.org/core-2.4.0/Thread.html#method-c-report_on_exception-3D), [Thread#report_on_exception](https://ruby-doc.org/core-2.4.0/Thread.html#method-i-report_on_exception), [Thread#report_on_exception](https://ruby-doc.org/core-2.4.0/Thread.html#method-i-report_on_exception-3D))
* [2.5](2.5.md#threadfetch) `#fetch` ([Thread#fetch](https://ruby-doc.org/core-2.6/Thread.html#method-i-fetch) (feature is present since Ruby 2.5, but explanations added later))
* [3.0](3.0.md#threadignore_deadlock-accessor) `Thread.ignore_deadlock` accessor ([Thread.ignore_deadlock=](https://docs.ruby-lang.org/en/3.0.0/Thread.html#method-c-ignore_deadlock-3D), [Thread.ignore_deadlock](https://docs.ruby-lang.org/en/3.0.0/Thread.html#method-c-ignore_deadlock))
* [3.1](3.1.md#threadnative_thread_id) `Thread#native_thread_id` ([Thread#native_thread_id](https://docs.ruby-lang.org/en/3.1/Thread.html#method-i-native_thread_id))

### `Process`

* **2.0** `Process.getsid` for getting session id (unix only).
* **2.1** `Process.argv0()` returns the original value of $0.
* **2.1** `Process.setproctitle()` sets the process title without affecting $0.
* **2.1** `Process.clock_gettime` and `.clock_getres`
* **2.2** Process execution methods such as `Process.spawn` opens the file in write  mode for redirect from `[:out, :err]`.
* [2.5](2.5.md#processlast_status-as-an-alias-of-) `Process.last_status` as an alias of `$?` ([Process.last_status](https://ruby-doc.org/core-2.5.0/Process.html#method-c-last_status))
* [3.1](3.1.md#process_fork) `Process._fork` ([Process.\_fork](https://docs.ruby-lang.org/en/3.1/Process.html#method-c-_fork))

### `Fiber`

* **2.0** `Fiber#resume` cannot resume a fiber which invokes `Fiber#transfer`.
* **2.2** callcc is obsolete. use Fiber instead.
* [2.7](2.7.md#fiberraise) `#raise` ([Fiber#raise](https://ruby-doc.org/core-2.7.0/Fiber.html#method-i-raise))
* [3.0](3.0.md#non-blocking-fiber-and-scheduler) Non-blocking `Fiber` and scheduler ([Fiber](https://docs.ruby-lang.org/en/master/Fiber.html#class-Fiber-label-Non-blocking+Fibers) (class documentation), [Fiber::SchedulerInterface](https://docs.ruby-lang.org/en/master/Fiber/SchedulerInterface.html) (definition of the interface which the scheduler must implement, [doc/fiber.md](https://docs.ruby-lang.org/en/3.0.0/doc/fiber_md.html) (design documentation).)
* [3.0](3.0.md#fiberbacktrace--backtrace_locations) `#backtrace` & `#backtrace_locations` ([Fiber#backtrace](https://docs.ruby-lang.org/en/3.0.0/Fiber.html#method-i-backtrace), [Fiber#backtrace_locations](https://docs.ruby-lang.org/en/3.0.0/Fiber.html#method-i-backtrace_locations),)
* [3.0](3.0.md#fibertransfer-limitations-changed) `#transfer` limitations changed ([Fiber#transfer](https://docs.ruby-lang.org/en/3.0.0/Fiber.html#method-i-transfer))
* [3.1](3.1.md#fiber-scheduler-new-hooks) New hooks for fiber scheduler ([Fiber::SchedulerInterface#address_resolve](https://docs.ruby-lang.org/en/3.1/Fiber/SchedulerInterface.html#method-i-address_resolve), [Fiber::SchedulerInterface#timeout_after](https://docs.ruby-lang.org/en/3.1/Fiber/SchedulerInterface.html#method-i-timeout_after), [Fiber::SchedulerInterface#io_read](https://docs.ruby-lang.org/en/3.1/Fiber/SchedulerInterface.html#method-i-io_read), [Fiber::SchedulerInterface#io_write](https://docs.ruby-lang.org/en/3.1/Fiber/SchedulerInterface.html#method-i-io_write))

### `Ractor`

* [3.0](3.0.md#ractors) **Ractors introduced** ([Ractor](https://docs.ruby-lang.org/en/3.0.0/Ractor.html) (class documentation), [doc/ractor.md](https://docs.ruby-lang.org/en/3.0.0/doc/ractor_md.html) (design documentation).)
* [3.1](3.1.md#ractors-can-access-module-instance-variables) Ractors can access module instance variables ([Ractor#Shareable and unshareable objects](https://docs.ruby-lang.org/en/3.1/Ractor.html#class-Ractor-label-Shareable+and+unshareable+objects) (docs aren't updated yet))

## Debugging and internals

* [2.6](2.6.md#rubyvmabstractsyntaxtree) [RubyVM::AbstractSyntaxTree](https://ruby-doc.org/core-2.6/RubyVM/AbstractSyntaxTree.html) introduced
* [2.6](2.6.md#rubyvmresolve_feature_path) `RubyVM.resolve_feature_path`
* [2.7](2.7.md#load_pathresolve_feature_path) ...and was renamed to `$LOAD_PATH.resolve_feature_path`
* [2.7](2.7.md#resolve_feature_path-behavior-for-loaded-features-fixed) `$LOAD_PATH.resolve_feature_path` behavior for loaded features fixed (— _(see above)_)
* [3.1](3.1.md#load_pathresolve_feature_path-does-not-raise) `$LOAD_PATH.resolve_feature_path` does not raise ([doc/globals.rdoc](https://docs.ruby-lang.org/en/3.1/doc/globals_rdoc.html))

### `Binding`

TODO: short explanation

* **2.1** `#local_variable_get(symbol)`, `#local_variable_set(symbol, obj)`, `#local_variable_defined?(symbol)`
* **2.2** `#local_variables`
* **2.2** `#receiver`
* [2.6](2.6.md#bindingsource_location) `#source_location` ([Binding#source_location](https://ruby-doc.org/core-2.6/Binding.html#method-i-source_location))

### `GC`

TODO: Explanation that "Not algorithms"

* **2.0** `GC::Profiler.raw_data` which returns raw profile data for GC.
* **2.1** introduced the generational GC a.k.a RGenGC.
* **2.2** `GC.latest_gc_info` returns `:state` to represent current GC status.
* **2.2** Introduce incremental marking for major GC. [Feature #10137]
* **2.2** Rename `GC.stat` entries
* [2.7](2.7.md#gccompact) `GC.compact` ([GC.compact](https://ruby-doc.org/core-2.7.0/GC.html#method-c-compact))
* [3.0](3.0.md#gcauto_compact-accessor) `GC.auto_compact` accessor ([GC.auto_compact](https://docs.ruby-lang.org/en/3.0.0/GC.html#method-c-auto_compact), [GC.auto_compact=](https://docs.ruby-lang.org/en/3.0.0/GC.html#method-c-auto_compact-3D))
* [3.1](3.1.md#gc-measuring-total-time) Measuring total time spent in GC ([GC.measure_total_time](https://docs.ruby-lang.org/en/3.1/GC.html#method-c-measure_total_time), [GC.measure_total_time=](https://docs.ruby-lang.org/en/3.1/GC.html#method-c-measure_total_time-3D), [GC.stat](https://docs.ruby-lang.org/en/3.1/GC.html#method-c-stat), [GC.total_time](https://docs.ruby-lang.org/en/3.1/GC.html#method-c-total_time))

### `TracePoint`

* **2.0** **`TracePoint` class is introduced** as a replacement of `set_trace_func`
* [2.4](2.4.md#tracepointcallee_id) `#callee_id` ([TracePoint#callee_id](https://ruby-doc.org/core-2.4.0/TracePoint.html#method-i-callee_id))
* [2.6](2.6.md#parameters) `#parameters` ([TracePoint#parameters](https://ruby-doc.org/core-2.6/TracePoint.html#method-i-parameters))
* [2.6](2.6.md#script_compiled-event) `:script_compiled` event ([TracePoint: Events](https://ruby-doc.org/core-2.6/TracePoint.html#class-TracePoint-label-Events) (though new event seems to be omitted), [TracePoint#instruction_sequence](https://ruby-doc.org/core-2.6/TracePoint.html#method-i-instruction_sequence), [TracePoint#eval_script](https://ruby-doc.org/core-2.6/TracePoint.html#method-i-eval_script))
* [2.6](2.6.md#enable-new-params-target-and-target_line) `#enable`: new params `target:` and `target_line:` ([TracePoint#enable](https://ruby-doc.org/core-2.6/TracePoint.html#method-i-enable) (not much, though...))
* [3.1](3.1.md#tracepointallow_reentry) `.allow_reentry` ([TracePoint.allow_reentry](https://docs.ruby-lang.org/en/3.1/TracePoint.html#method-c-allow_reentry))

### `RubyVM::InstructionSequence`

* **2.0** `RubyVM::InstructionSequence.of` to get the instruction sequence from a method or a block.
* **2.0** `RubyVM::InstructionSequence#path`, `#absolute_path`, `#label`, `#base_label` and `#first_lineno` to retrieve information from where the instruction sequence was defined.
* **2.3** `RubyVM::InstructionSequence#to_binary(extra_data = nil)`
* **2.3** `RubyVM::InstructionSequence.load_from_binary(binary)`
* **2.3** `RubyVM::InstructionSequence.load_from_binary_extra_data(binary)`
* [2.5](2.5.md#rubyvminstructionsequence-new-methods) [RubyVM::InstructionSequence#each_child](https://ruby-doc.org/core-2.5.0/RubyVM/InstructionSequence.html#method-i-each_child), [RubyVM::InstructionSequence#trace_points](https://ruby-doc.org/core-2.5.0/RubyVM/InstructionSequence.html#method-i-trace_points)

<!--

* [2.5](2.5.md#misc) Misc (—)
* [2.6](2.6.md#misc) Language: Misc (—)
* [2.6](2.6.md#minor-changes) Minor changes (—)
* [2.7](2.7.md#other-syntax-changes) Language: Other syntax changes (—)
* [3.0](3.0.md#other-changes) Language changes: Other changes (—)

* [3.0](3.0.md#randomdefault-behavior-change) `Random::DEFAULT` behavior change ([Random](https://docs.ruby-lang.org/en/3.0.0/Random.html))

* [3.1](3.1.md#marshalload-accepts-a-freeze-option) `Marshal.load` accepts a `freeze:` option ([Marshal.load](https://docs.ruby-lang.org/en/3.1/Marshal.html#method-c-load))

-->

## Deeper topics

### Refinements

TODO: Explanations

* **2.0** **Refinements are introduced as experimental feature** with `Module#refine` and top-level `using`
* **2.1** `Module#refine` and top-level `using` is no longer experimental
* **2.1** `Module#using` introduced to activate refinements only in some particular module
* [2.4](2.4.md#refinements-are-supported-in-symbolto_proc-and-send) Refinements are supported in `Symbol#to_proc` and `send` (—)
* [2.4](2.4.md#refine-can-refine-modules-too) `refine` can refine modules, too ([Module#refine](https://ruby-doc.org/core-2.4.0/Module.html#method-i-refine))
* [2.4](2.4.md#moduleused_modules) `Module.used_modules` ([Module.used_modules](https://ruby-doc.org/core-2.4.0/Module.html#method-c-used_modules))
* [2.5](2.5.md#refinements-work-in-string-interpolations) Refinements work in string interpolations (—)
* [2.6](2.6.md#refinements-improved-visibility) Improved refinements visibility (—)
* [2.7](2.7.md#refinements-in-methodinstance_method) Refinements in `#method`/`#instance_method` (—)
* [3.1](3.1.md#refinement-class) `Refinement` class ([Refinement](https://docs.ruby-lang.org/en/3.1/Refinement.html))


### Freezing

TODO: Explanations

* **2.0** Fixnums, Bignums and Floats are frozen.
* **2.1** All symbols are now frozen.
* **2.2** `nil`/`true`/`false` objects are frozen.
* **2.3** `String#+@` and `#-@` are added to get mutable/frozen strings.
* [2.4](2.4.md#objectclonefreeze-false) `#clone(freeze: false)` ([Object#clone](https://ruby-doc.org/core-2.4.0/Object.html#method-i-clone))
* [2.7](2.7.md#core-methods-returning-frozen-strings) Several core methods like `nil.to_s` and `Module.name` return frozen strings
* [3.0](3.0.md#objectclonefreeze-true) `#clone(freeze: true)` ([Kernel#clone](https://docs.ruby-lang.org/en/3.0.0/Kernel.html#method-i-clone))
* [3.0](3.0.md#objectclone-passes-freeze-argument-to-initialize_clone) `Object#clone` passes `freeze:` argument to `#initialize_clone` ([Kernel#clone](https://docs.ruby-lang.org/en/3.0.0/Kernel.html#method-i-clone))
* [3.0](3.0.md#interpolated-string-literals-are-no-longer-frozen-when--frozen-string-literal-true-is-used) Interpolated String literals are no longer frozen when `# frozen-string-literal: true` is used ([doc/syntax/comments.rdoc](https://docs.ruby-lang.org/en/3.0.0/doc/syntax/comments_rdoc.html#label-frozen_string_literal+Directive))
* [3.0](3.0.md#regexp-and-range-objects-are-frozen) `Regexp` and `Range` objects are frozen
* [3.0](3.0.md#symbolname) `Symbol#name` ([Symbol#name](https://docs.ruby-lang.org/en/3.0.0/Symbol.html#method-i-name))
