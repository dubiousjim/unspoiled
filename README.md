unspoiled
=========

Libraries and stuff for [pure-lang](http://code.google.com/p/pure-lang/).

The `contrib` folder includes some things I've contributed to the Pure distribution, and should appear in a version of Pure &gt; 0.55.

 *   trees23.pure -- rewrite of lib/avltrees.pure
 *   nonsplicing.pure -- non-splicing vector braces
 *   msort.pure -- an optimized stable mergesort for lists

I do plan some further developments for trees23 (see below).

The rest are things I'm working on, or are provided here just for the random interested browser.

 *   macros/try.pure -- try/succeeds/finally macros (NEW)
 *   macros/gfolds.pure -- gfold-writing macros (NEW)
 *   macros/walker.pure -- walks and converts a Pure syntax tree, used by gfolds.pure (NEW)
 *   macros/common.pure -- some common macro operations

 *   lists.pure -- additional/optimized list methods (IN PROGRESS)
 *   weakdict.pure -- weak references, and weak-key and weak-value dicts (This may also be merged into the standard distribution. It already works but I still need to write tests/better docs. Also, I hope to integrate the developments in lists.pure into trees23 and avltrees and all the set/bag/dict interfaces, including the weakdict interfaces.)

 *   hashtable.pure -- mutable hashtable
 *   prelude2.pure -- miscellaneous extra bits and pieces

Experiments, of mixed success:

 *   experiments/delimcc.pure -- delimited continuations (shift/reset), only works in some cases
 *   experiments/functor.pure -- ML-style functors in pure

