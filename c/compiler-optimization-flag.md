# Compiler Optimization Flag

While reading through *Effective C* by Robert C. Seacord, I discover the optimization flag for compiling code. He lays out the different values for the flag and when they might be helpful. In particular, with `gcc` and `clang` the `-O` flag has the following options with the associated meanings or times they are useful:

* 0 - Disables most optimizations, so good for initial builds while getting started.
* g - Optimizes the code for debugging.
* 1 - Perform fast optimizations that don't increase build times significantly. Use for testing/QA.
* 2 - Perform all optimizations that don't increase the size of the object files. Use for release unless size is not an issue, or possibly QA.
* 3 - Perform all optimizations including optimizations that may increase the size of the object files. Use for release when the size increase won't be a burden.