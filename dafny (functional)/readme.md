# [Dafny (Functional)](https://rise4fun.com/Dafny/)

A functional proof of *leftpad* in Dafny.

[You can run the proof here](https://rise4fun.com/Dafny/RJ7Wd)

## About Dafny

Dafny is an imperative language supporting specification constructs based on Hoare logic. This means specifications can be coupled together with their implementations and programs are statically verified for total correctness. However, due to undecidability, Dafny may report errors for programs even though they may be correct on every runtime execution. This can be due to quantifiers, nonlinear arithmetic or missing annotations.

## About the Proof

This implementation makes use of recursion and considers two cases.

The base case is when the string already satisfies the required length. If so, then we're done and the string is simply returned.

In the recursive case, the string is concatenated with a single padding character to its left. This padded string is passed as the result string in a recursive call to the method. It is also the only argument that changes in each recursive call.

Since we make use of recursion, we need to prove that the function eventually terminates. We do this using the `decreases` clause, stating that `n - |s|` decreases with each recursive call. Dafny then verifies that this value is bounded in that it cannot decrease infinitely. For simpler expressions such as a single integer, Dafny is able to infer the decreasing expression automatically.

## About Me

Hello! I'm a final year computer science undergrad at the National University of Singapore interested in verification, languages and distributed systems. [Here's my github]("github.com/arsalanc-v2").
