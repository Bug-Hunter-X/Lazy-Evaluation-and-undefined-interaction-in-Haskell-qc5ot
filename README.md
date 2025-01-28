# Haskell Lazy Evaluation Bug

This repository demonstrates a subtle bug in Haskell code arising from the interaction between lazy evaluation and the use of `undefined`. The `maybeUndefined` function, when called with `False`, returns `undefined`.  However, the lazy nature of Haskell means this doesn't immediately cause a runtime error. The issue surfaces only when the result is forced, potentially leading to unexpected crashes or incorrect behavior in a larger program.

The `bug.hs` file contains the buggy code, while `bugSolution.hs` provides a corrected version.  The solution uses pattern matching and a default value to handle the case where the condition is `False`, preventing the propagation of `undefined`.