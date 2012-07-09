unspoiled
=========

Libraries and stuff for [pure-lang](http://code.google.com/p/pure-lang/).

The `contrib` folder includes some things I've contributed to the Pure distribution, and should appear in a version of Pure &gt; 0.55.

 *   trees23.pure -- rewrite of lib/avltrees.pure
 *   nonsplicing.pure -- non-splicing vector braces
 *   msort.pure -- an optimized stable mergesort for lists

I do plan some further developments for trees23 (see below).

The toplevel includes things I'm working on, or are provided here just for the random interested browser.

 *   try.pure -- try/succeeds/finally macros (NEW)
 *   gfolds.pure -- gfold-writing macros (NEW)
 *   delimcc.pure -- delimited continuations (shift/reset) (IN PROGRESS)
 *   lists.pure -- additional list methods (IN PROGRESS)
 *   weakdict.pure -- weak references, and weak-key and weak-value dicts (This may also be merged into the standard distribution. It already works but I still need to write tests/better docs. Also, I hope to integrate the developments in lists.pure into trees23 and avltrees and all the set/bag/dict interfaces.)
 *   hashtable.pure -- mutable hashtable
 *   functor.pure -- ML-style functors in pure
 *   prelude2.pure -- miscellaneous extra bits and pieces

