# Antosser's really fast "Prime Number Calculator"
## Usage
1. Execute the app with a commandline.
1. Enter how many primes you want to calculate after **Numbers:**.
1. Then enter the name of the file where you want to save the output to. If the file already exists it will continue calculating from the place you stopped at.
1. Press enter and it will be calculating the numbers very fast.

Press **Escape** if you want to pause the calculation and save the result to a file

## How it works
First a std::vector<int> is being created. (That's like an array that has the ability to expand.)
```cpp
std::vector<int> primes = {};
```
Then you do that
```cpp
for (int i = 2; primes.size() < n; i++) {
  int root = sqrt(i) + 1;
  for (int ci : primes) {
    if (i % ci == 0)
      goto brk;
    if (ci > root)
      break;
  }
  primes.push_back(i);
  file << i << std::endl;
  brk:;
} // Try understand it yourself. Not that hard
```
