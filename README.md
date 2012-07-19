unspoiled
=========

Libraries and stuff for [pure-lang](http://code.google.com/p/pure-lang/).

The `contrib` folder is a sandbox for contributions I'm making to the Pure distribution.

Currently, it includes these features not yet in the Pure Mercurial repository:

* Implementation of ==? and ~=? as discussed on mailing list. This is used by
  the `index` list function and a new `member` list function.

* Separated list functions into their own file, lists.pure. This includes optimizations
  for the following list functions, disabled by default. Use `--enable=list-opt` to turn them
  on: (+) filter foldr foldr1 init map take takewhile cat catmap zip zip3 zipwith zipwith3.
  The subseq function is also optimized for lists; this still resides in prelude.pure.

* Added the following new list functions:
    reverse_onto, map_onto, catmap_onto, zip_onto, zip3_onto -- the last two are really variants of zipwith
    foldl2, foldl3, foldr2, foldr3 -- these fold 2 or 3 lists in parallel, stopping with shortest
    split n xs -- efficient version of {take n xs, drop n xs}
    splitby p xs -- efficient version of {filter p xs, filter ((~).p) xs}
    findl p xs -- first element satisfying p, else throw out_of_bounds
    deletel p xs -- delete first element satisfying p, fails silently
    popl p xs -- efficient version of {findl p xs, deletel p xs}, returns {} if no match
    findr, deleter, popr -- these apply to last element satisfying p
    chain [xs,ys,...] --- efficient version of cat [stream xs, stream ys, ...]
    rotate xs -- efficient version of last xs:init xs
    bisect -- splits list in half in single traversal
    swap: here is the implementation:
        swap y (x:xs) default   = x:y:xs;
        swap _ [] default       = default;
    I use something like this in recursive functions, when a result needs to
    bubble up from later in the list back through a pending return stack.

* Integrates trees23 into the stdlib, but it's disabled by default. Use `--enable=trees23` to turn on.

* Added fold functions to both trees23 and avltrees, and various additional get, delete, and
  pop functions to both libraries. Haven't yet exposed this functionality in the high-level
  sets/bags/dicts APIs.

* examples/msort.pure is an optimized stable mergesort for lists; this is already in the Pure repository.


The rest are things I'm working on, or are provided here just for the random interested browser.

 *   macros/try.pure -- try/succeeds/finally macros (NEW)
 *   macros/gfolds.pure -- gfold-writing macros (NEW)
 *   macros/walker.pure -- walks and converts a Pure syntax tree, used by gfolds.pure (NEW)
 *   macros/common.pure -- some common macro operations

 *   weakdict.pure -- weak references, and weak-key and weak-value dicts (I will merge this into the contrib/ folder soon. It already works but I still need to write tests/better docs.) 

 *   hashtable.pure -- mutable hashtable
 *   prelude2.pure -- miscellaneous extra bits and pieces

Experiments, of mixed success:

 *   experiments/delimcc.pure -- delimited continuations (shift/reset), only works in some cases
 *   experiments/functor.pure -- ML-style functors in pure

