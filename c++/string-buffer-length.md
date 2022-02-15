# String Buffer Length

When needing to determine a string buffer length in C++, it is better to use the `length` function from the `string.h` library than `strlen` from the `cstring.h` library. You are usually fine when the data is non-binary and ascii; however, one can run into null characters rather quickly in other situations, especially when the string ultimately comes from binary file data. You can always convert to a C++ string (or leave it as one) and find the length. Then, you can then cast your `string` variable `mystring` as follows in the third line:

```cpp
std::string mystring = "Cat in the hat!";
int buffLength = mystring.length();
const char *mybuffer = mystring.c_str();
```
