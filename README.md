# CIS-165 Lab 3

**Course section:** CIS-165-W099

## Program Plans

### Program 1 — Diamond Pattern

I will use C++ output statements to display the seven lines of the required diamond. I will carefully match the number of spaces and asterisks on each line. I will not use loops, arrays, functions other than `main`, or user input.

### Program 2 — Video Game Level Times

I will store 78 minutes for Level 1 and 144 minutes for Level 2 in variables. I will use integer division to calculate the number of hours and the remainder operator to calculate the remaining minutes. I will also calculate the difference between the two level times and convert that difference into hours and remaining minutes. I will store each calculation in variables before displaying the results with clear labels and units.

## Files

* `diamond.cpp` — displays the required seven-line diamond pattern.
* `game_time.cpp` — converts the level times from minutes into hours and remaining minutes and calculates the difference.
* `README.md` — contains plans, testing, explanations, and instructions.
* `AI_REFLECTION.md` — documents how AI was used and what I learned.

## How to Compile and Run

### Using OnlineGDB

1. Open OnlineGDB and select C++.
2. Open or paste the contents of one source file.
3. Click **Run**.
4. Check the output against the expected results.
5. Run each source file separately because each program has its own `main()` function.

### Using g++

The programs can also be compiled from a terminal using:

```text
g++ -std=c++17 -Wall -Wextra diamond.cpp -o diamond
g++ -std=c++17 -Wall -Wextra game_time.cpp -o game_time
```

Then run the programs separately.

## Program 1 Explanation — Diamond Pattern

The diamond is created using seven separate `cout` statements. Each statement prints one line followed by `endl`.

The number of spaces decreases from three to zero as the pattern gets wider. At the same time, the number of asterisks increases from one to seven. The second half reverses this pattern, increasing the spaces and decreasing the asterisks.

The required pattern is:

```text
   *
  ***
 *****
*******
 *****
  ***
   *
```

Because spaces can be difficult to see, I checked each line individually. I checked the number of spaces and asterisks on all seven lines. The final run matched the required pattern with no extra program output.

## Program 2 Explanation — Video Game Level Times

The program stores the assigned times in named integer variables:

```text
level_one_minutes = 78
level_two_minutes = 144
```

For each level, integer division by 60 gives the number of complete hours.

For example:

```text
78 / 60 = 1
```

The remainder operator `%` gives the minutes left after the complete hours are removed:

```text
78 % 60 = 18
```

Therefore, 78 minutes is 1 hour and 18 minutes.

For Level 2:

```text
144 / 60 = 2
144 % 60 = 24
```

Therefore, 144 minutes is 2 hours and 24 minutes.

The program first calculates the difference in total minutes:

```text
144 - 78 = 66
```

Then it converts 66 minutes into hours and remaining minutes:

```text
66 / 60 = 1
66 % 60 = 6
```

Therefore, Level 2 took 1 hour and 6 minutes longer.

I stored each calculated result in a variable before displaying it. This keeps the calculations separate from the output and makes the program easier to read and check.

## Testing

## Testing

Before each test, I calculated the expected results independently and then compared them with the program output.

| Program/test | Values or pattern checked | Expected result before running | Actual output | Match or correction |
|---|---|---|---|---|
| `diamond.cpp` | Seven required lines | Three spaces/one star, two spaces/three stars, one space/five stars, seven stars, then the reverse | The seven lines matched the required pattern with the correct spaces and asterisks | Match |
| `game_time.cpp` — assigned | Level 1 = 78, Level 2 = 144 | Level 1 = 1 hour, 18 minutes; Level 2 = 2 hours, 24 minutes; Difference = 1 hour, 6 minutes | Level 1: 1 hour(s) and 18 minute(s); Level 2: 2 hour(s) and 24 minute(s); Difference: 1 hour(s) and 6 minute(s) | Match |
| `game_time.cpp` — changed | Level 1 = 95, Level 2 = 217 | Level 1 = 1 hour, 35 minutes; Level 2 = 3 hours, 37 minutes; Difference = 2 hours, 2 minutes | Level 1: 1 hour(s) and 35 minute(s); Level 2: 3 hour(s) and 37 minute(s); Difference: 2 hour(s) and 2 minute(s) | Match |

The changed-value test was useful because both levels had nonzero remainders. It confirmed that the integer division and remainder calculations worked with values other than the assigned values.

The programs were then restored to the assigned values of 78 and 144. Both programs were run again as final checks before submission.

## Final Assigned Values

The final version of `game_time.cpp` uses:

```cpp
int level_one_minutes = 78;
int level_two_minutes = 144;
