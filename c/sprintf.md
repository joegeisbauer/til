# Concatenate and Format Strings with sprintf

The easiest way to concatenate string literals with char arrays (c-strings), is using sprintf in c. You can do something like:

```c
#include<stdio.h>

#define strLiteral "LiteralString"

int main() {
  char myString[9] = "SomeWord";
  char *concatString;
  concatString = (char*)malloc(sizeof(255));
  sprintf(concatString, strLiteral "/OtherLiteralStuff/%s", myString);
  return 0;
}
```

This will store "LiteralString/OtherLiteralStuff/SomeWord" to the `concatString` variable for use elsewhere. 