# Wrapping C Functions (with ctypes)

This isn't really new, but I had to recently remind myself of the proper way to perform this function wrapping. When that happens, it is probably a good candidate for a til repo, but I digress. You can wrap `C` functions in your python code using `ctypes`. Here is a quick example using a `C` file that runs monte-carlo simulations for coin flipping, and a python file that simply calls that library. The first step is to write the following contents in the `monte_carlo_coin.c` file:

```c
#include <stdio.h>
#include <stdlib.h>
#include <time.h>

float flipCoin(int trials) {

    if (trials <= 0) {
        printf("ArgumentError: Number of trials must be defined and positive.\n");
        exit(1);
    }

    int numHeads = 0;
    float prob;
    time_t seconds;

    time(&seconds);
    int timeSeed = (uint)(seconds % __UINT64_MAX__);

    srand(timeSeed);

    for (int j=0; j < trials; j++) {
        numHeads += rand() % 2;
    }
    return numHeads / (float)trials;
}
```

You can then compile this code into a shared library and set the `LD_LIBRARY_PATH` in your current terminal to the `cwd` for this terminal instance using the following two lines:

```bash
gcc -o monte_carlo_coin.so -shared monte_carlo_coin.c
export LD_LIBRARY_PATH=.
```

Then, write the following python file that will simply run the monte-carlo experiments from the python environment.

```python
import ctypes

if __name__ == '__main__':

    coin_lib = ctypes.cdll.LoadLibrary('monte_carlo_coin.so')
    coin_flip = coin_lib.flipCoin
    coin_flip.restype = ctypes.c_float

    print("Result: %.2f" % coin_flip(10))
```

And that is it. There are other ways to wrap python functions, but this is probably the simplest (that is still supported) for getting started.