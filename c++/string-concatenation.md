# String Concatenation

I learned yesterday that C++ treats spaces between string literals as concatenation operators. So the following are equivalent:

```c++
string1 = "a dog" " is " "black"
string2 = "a dog is black"
```

I am told this is useful for breaking really long strings over lines or for writing preprocessor macros for strings, but stands a good chance of being confusing outside of that. Here is an example of a preprocessor macro you might want to use:

```c++
#define MY_TAG_STRING(x) "tag: " x

std::string tagString = MY_TAG_STRING(x)
```

This would prevent you from having to format the first part of the string each time, which could be useful in logging or for some repeated format of output to the terminal.