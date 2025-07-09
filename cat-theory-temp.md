
Types are basically you saying some x is a subset of a list
for example the integer type in haskell is an inf. list, meaning if x :: integer that means what it obv means.

compositions matter.
not all arrows(functions) can be composed, only if the "The target object of one arrow must be the same as the source source object of the next arrow"


f :: Bool -> Bool
meaning f arrow has input bool, and output bool
no type change.

objects are sets and morphisms (arrows) are functions.
theoretically we would like to say that objects are sets and haskell functions are mathematical functions between these sets, but math functions don't produce output, they already know the answer which means they can't actually produce any new data.

Halting problem:
there are problems where we can't find the answer in a finite amount of steps.
we extend every type by one or more special value called the "Bottom", denoted by $\bot$, basically means non-term. comput.
so a $f :: Bool \to Bool$ can return $True, False, \bot$. 