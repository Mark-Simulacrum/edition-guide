# What are Editions?

Rust usually releases on a six-week cycle. This means that users get a
constant stream of new features. This is much faster than updates for
other languages, but this also means that each update is smaller.

After a while, all of those tiny changes add up. But, from release to release, it can be hard to look back
and say *"Wow, between Rust 1.10 and Rust 1.20, Rust has changed a lot!"*
Furthermore, since everything must be backwards compatible, we can't make certain
tiny changes, like adding keywords because it might be already used as an
identifier in existing code. Finally, you may sense that various parts
of the project lags behind, since they update at different paces.
If a new language feature lands in Rust 1.15, a new chapter about it may
land in the book in 1.16, and the IDE integration may land in 1.17. This can feel
like the pieces are not well coordinated, but if you compare Rust 1.15 to
Rust 1.17, you'll see one cohesive feature being added.

"Editions" are a concept to help with these kinds of problems. Every two or
three years, we'll be producing a new edition of Rust. This serves different
purposes for different people: for those working on Rust, it's a great way to
focus on looking at the project as a whole, and being able to see the big
picture. For those who haven't used Rust yet, or for those who may have tried
Rust in the past and found it lacking in some way, a new edition signals that
major advancements have landed, and you may want to give it a look!

## Compatibility

Editions are allowed to introduce minor kinds of incompatibilities, such as
turning a warning into a hard error, or adding new keywords. At the same
time, it's very important that we don't split the Rust ecosystem. Therefore,
each project can list which edition that it's using, and the Rust compiler
can link crates of any editions together. Therefore, if you're using Rust 2015,
and one of your dependencies uses Rust 2018, it all works just fine. The
opposite situation works as well.

## Trying out the 2018 edition

At the time of writing, there are two editions: 2015 and 2018. 2015 is today's
Rust; Rust 2018 will ship later this year. To give Rust 2018 a try, you can
add this feature to your crate root:

```rust
#![feature(rust_2018_preview)]
```

Like all `#![feature(..)]` flags, this will only work on nightly Rust. This
flag will enable all of the new 2018 specific features. You can also use:

```rust
#![feature(rust_2018_idioms)]
```

This will turn on a series of lints that suggest new idioms.
The old code will still work, but it will trigger warnings.

As new nightly compilers are released, more functionality will be enabled,
so you may experience new warnings, features, and other things.
This is something to keep in mind and is exactly why nightly is unstable!
