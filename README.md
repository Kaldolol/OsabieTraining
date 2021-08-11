#### Conventions

- If an element is parenthesised (e.g. `(a,)`), then it is optional and needs not to exist on the stack in order for the command to execute. It might have different uses depending on whether the argument is present or not, but that is clarified for each command which acts like this.

- If a command is marked with *(Get **x**)*, then the command is executed without popping **x** from the stack.

## Commands

Command|Elements Popped|Description|
:-----:|:-------------:|-----------|
`ǝ` | `a,b,c` | Replace the element of **a** at index **c** with **b**
`ʒ` | `a` | Filter **a**. Keep the elements where the result of the code is `1`. Usage: `ʒ CODE }`
`α` | `a,b` | Absolute difference of **a** and **b**
`β` | `a,b` | Convert **a** from base **b** (arbitrary)
`γ` | `a` | Split **a** into chunks of equal adjacent elements.
`δ` | `a,b` | Outer Product. Get the next command and apply it double-vectorized.
`ε` | `a` | Map. Apply a piece of code to each element of **a**. Usage: `ε CODE }`
`Δ` | `a` | Fixed-point. Repeatedly apply `CODE` on **a** until doesn't change. Usage: `Δ CODE }`
`ζ` | `a,(b)` | Zip **a** with filler **b** (standardized to space)
`η` | `a` | Prefixes of **a**
`и` | `a,b` | Repeat list **a** **b** times (n-repeat)
`θ` | `a` | Last element. Push `a[-1]`
`в` | `a,b` | Convert **a** to base **b** (arbitrary)
`м` | `a,b` | Remove the elements that also occur in **b** from **a** (vectorizes) 
`н` | `a` | First element. Push `a[0]`
`Θ` | `a` | 05AB1E truthified **a** (a == 1)
`Σ` | `a` | Sort **a** by the result of `CODE`. Usage: `Σ CODE }`
`Ω` | `a` | Random choice. Push a random element of **a**
`≠` | `a` | 05AB1E falsified **a** (a != 1)
`∊` | `a` | Vertically mirror **a**
`∍` | `a,b` | Extend / shorten **a** to length **b**
`∞` | `a` | Infinite list of positive integers (`[1, 2, …, ∞]`)
`!` | `a,` | Factorial of **a**
`#` | `a` | Break if the top of the stack is truthy (used in infinite loops)
`#` | `a` | If **a** contains spaces, split by spaces.
`%` | `a,b` | Modulo. Push `a % b`
`&` | `a,b` | Bitwise AND. Push `a & b`
`(` | `a` | Negative. Push **-a**
`*` | `a,b` | Multiplication. Push `a * b`
`+` | `a,b` | Addition. Push `a + b`
`,` | `a` | Print **a**
`-` | `a,b` | Subtraction. Push `a - b`
`/` | `a,b` | Division. Push `a / b`
`÷` | `a,b` | Integer division. Push `a // b`
`:` | `a,b,c` | Infinite replacement. Push `a.replace(b, c)`
`;` | `a` | Halve. Push `a / 2`
`<` | `a` | Decrement. Push `a - 1`
`>` | `a` | Increment. Push `a + 1`
`?` | `a` | Print **a**, without a newline
`=` |  -  | Print last item
`@` | `a,b` | Greater than or equal to. Push `a >= b`
`A` | - | Lowercase alphabet. Push 'abcdefghijklmnopqrstuvwxyz'
`B` | `a,b` | Base Conversion. Push `base(a, b)`
`C` | `a` | Convert from binary to integer. Push `int(a, 2)`
`D` | `a` | Duplicate. Push `a, a`
`E`  | `a` | For-loop in **[1 .. a]**, variable **N** (`for N in range(1, a + 1)`). Usage: `E CODE }`
`F` | `a` | For-loop in **[0 .. a)**, variable **N** (`for N in range(0, a)`). Usage: `F CODE }`
`G` | `a` |  For-loop in **[1 .. a)**, variable **N** (`for N in range(1, a)`). Usage: `G CODE }`
`ƒ` | `a` | For-loop in **[0 .. a]**, variable **N** (`for N in range(0, a + 1)`). Usage: `ƒ CODE }`
`H` | `a` | Convert **a** from hexadecimal to integer. Push `int(a, 16)`
`I`  | - | Push the input
`J` | `a` | Join (`''.join(a)`) if **a** is list, else join the stack (`''.join(stack)`)
`K` | `a,b` | Push **a** without **b**'s
`L` | `a` | Inclusive range. Push **[1 .. a]**
`M`  | - | Largest number on the stack
`N`  | - | Reserved for variables
`O` | `a` | Sum **a** if **a** is list, else sum the stack
`P` | `a` | Product of **a** if **a** is list, else product of the stack
`Q` | `a,b` | Equals? Push `a == b` (bool)
`R` | `a` | Reverse. Push **a** reversed (`a[::-1]`)
`S` | `a` | Cast **a** to a list of characters / digits.
`T`  | - | Push **10**
`U` | `a` | Assign **X** to **a**
`V` | `a` | Assign **Y** to **a**
`W`  | - | Minimum. Push **min(a)** without popping
`X`  | - | Integer variable
`Y`  | - | Integer variable
`Z`  | - | Maximum. Push **max(a)** without popping
`^` | `a,b` | Bitwise XOR. Push `a ^ b`
`_` | `a` | Negative bool. Push **1** is **a** is **0**, else **0** (vectorizes for lists, returns **0** for strings)
<code>`</code> | `a` | Dump. Push all contents of **a** onto the stack
`a` | `a` | Alphabetic? Push `is_alpha(a)`
`b` | `a` | Convert **a** to binary
`c` | `a,b` | Number of combinations (i.e. the binomial coefficient). Push `a nCr b` (i.e. `a` choose `b`)
`d` | `a` | **1** if **a** is a non-negative number (`a >= 0`), **0** otherwise 
`e` | `a,b` | Number of permutations; push `a nPr b`
`f` | `a` | List of prime factors of **a** without counting multiplicities
`g` | `a` | Length of **a**
`h` | `a` | Convert **a** to hexadecimal. Push `hex(a)`
`i` | `a` | If statement (`if true { then }`). Usage: `CONDITION i CODE }`
`j` | `a,b` | Join, padding each to length **b**. Same as `J`, with each element right justified to a minimum length of **b**
`k` | `a,b` | Index of **b** in **a** (0-indexed, **-1** when not found)
`l` | `a` | Lowercase. Push `lower_case(a)`
`m` | `a,b` | Exponentiation. Push `a ** b`
`n` | `a` | Square **a**. Push `a ** 2`
`o` | `a` | Raise **2** to the **a**th power. Push `2 ** a`
`p` | `a` | Primality checking. Push `isPrime(a)`
`q`  | - | Terminates the program
`r`  | - | Reverse stack
`s` | `a,b` | Swap. Push `b, a`
`t` | `a` | Square root. Push `sqrt(a)`
`u` | `a` | Uppercase. Push `upper_case(a)`
`v` | `a` | Enumerated map (range loop), variable **y**, index **N** (`for y in a`)
`x` | `a` | **a** and itself doubled. Push `a, 2a`
`y`  | - | Push string variable (used in mapping loops)
`z` | `a` | Inverse. Push `1 / a`
`}` | - | Close a single if statement, loop, etc.
`]` | - | Close all loops and if statements
`{` | `a` | Sort **a**. Push `sorted(a)`
`~` | `a,b` | Bitwise OR.
`‚` | `a,b` | Pair. Push `[a, b]`
`†` | `a,b` | Push **a** with **b** filtered to the front
`‡` | `a,b,c` | Transliterate. Push `a.transliterate(b -> c)`
`ˆ` | `a` | Add to global array
`ι` | `(a),b` | Uninterleave. Push `[a[0::b], a[1::b], ..., a[(b - 1)::b]]`
`‰` | `a,b` | Divmod. Pair the integer part and the remainder of the division of **a** and **b**. Push `a divmod b`
`Š` | `a,b,c` | Triple swap. Push `c, a, b`
`Œ` | `a` | Sublists / Substrings. Push `substrings(a)`
`Ć` | `a` | Enclose **a**, append its head to itself. Push `a + a[0]`
`ƶ` | `a` | Lift **a**, multiplying each element by its (1-based) index
`Ā` | `a` | Truthify **a** (Python-style boolean)
`–` | `a` | If the top of the stack is **1**, print the iteration index (`if 1, print N`, used in loops)
`—` | `a` | If the top of the stack is **1**, print the current element (`if 1, print y`, used in loops)
`˜` | `a` | Deep flatten **a**
`™` | `a` | Title capitalisation. Push `title_cased(a)`
`š` | `a` | Prepend **b** to **a** as a list.
`›` | `a,b` | Greater than. push `a > b`
`‹` | `a,b` | Less than. Push `a < b`
`œ` | `a` | Permutations. Push `permutations(a)`
`ć` | `a` | Head extract **a**. Push `a[1:], a[0]`
`Ÿ` | `(a,)b` | Inclusive binary range; push **[a .. b]** if **b** is not a list, else push `[b[0],...,b[1],...,b[n]]`
`ā`  | - | Length range (Get **a**). Push `range(1, len(a) + 1)`
`¡` | `a,b` | Split **a** on **b**. Push `a.split(b)` 
`¢` | `a,b` | Count the occurrences of **b** in **a**. Push `a.count(b)`
`£` | `a,b` | Head. Push `a[0:b]`
`¥` | `a` | Deltas of **a**
`¦` | `a` | Tail (remove the first element). Push `a[1:]`
`§` | `a` | Cast to string. Push `str(a)`
`¨` | `a` | Pop, remove the last element of **a**. Push `a[0:-1]`
`ª` | `a,b` | Append **b** to **a** as a list
`«` | `a,b` | Merge / Concatenate. Push `merged(a,b)` if both are lists, else push `concatenated(a, b)`
`°` | `a` | Raise **10** to the **a**th power. Push `10 ** a`
`±` | `a` | Bitwise not (complement). Push `~a`
`·` | `a` | Double. Push `2 * a`
`¸` | `a` | Wrap / Listify. Push `[a]`
`»` | `(a)` | if `(a)` is a list, join it by newlines, else join stack by newlines
`¿` | `(a,)b` | Greatest common divisor. Push `gcd(b)` if **b** is list, else push `gcd([b, a])`
`À` | `a` | Rotate **a** 1 unit left
`Á` | `a` | Rotate **a** 1 unit right
`Â` | `a` | Bifurcated **a**. Push `a, reversed(a)`
`Ã` | `a,b` | Keep all elements of **a** that also occur in **b** (list intersection). Push `a.keep(b)`
`Ä` | `a` | Absolute value. Push `abs(a)`
`Æ` | `a` | Reduce **a** by subtraction
`Ç` | `a` | Ord. Push the ASCII value of **a**
`È` | `a` | Even? Push `a % 2 == 0`
`É` | `a` | Odd? Push `a % 2 == 1`
`Ê` | `a,b` | Not equals? Push `a != b`
`Ë` | `a` | **1** if all elements are equal, **0** otherwise
`Ì` | `a` | Add **2** to **a**. Push `a + 2`
`Í` | `a` | Subtract **2** from **a**. Push `a - 2`
`Ï` | `a,b` | Elements of **a** for which the corresponding element of **b** is **1**
`Ñ` | `a` | Divisors. Push `divisors(a)`
`Ò` | `a` | List of prime factors of **a**, counting multiplicities.
`Ó` | `a` | List of exponents of **a**'s prime factorization (`2^a`, `3^b`, `5^c`, `7^d`, etc.)
`Ô` | `a` | Connected uniquified **a**
`Ö` | `a,b` | Divisible? Push `a % b == 0`
`Ø` | `a` | **a**th prime (zero-indexed)
`Ù` | `a` | Deduplicate. Push uniquified **a**
`Ú` | `a,b` | Trim leading and trailings **b**'s of **a**
`Û` | `a,b` | Left strip. Push **a** with leading **b**'s trimmed off
`Ü` | `a,b` | Right strip. Push **a** with trailing **b**'s trimmed off
`Ý` | `a` | Inclusive 0-based range. Push **[0 .. a]**
`ß` | `a` | Minimum. Extract smallest element of list
`à` | `a` | Maximum. Extract greatest element of list
`á` | `a` | Letters of **a**
`â` | `a,b` | Cartesian product of **a** and **b**
`ã` | `(a,)b` | Cartesian power. Push the cartesian product of `b.repeat(2)` if **b** is list, else the cartesian product of `a.repeat(b)`
`ä` | `a,b` | Slice **a** into **b** pieces
`å` | `a,b` | Check if **b** occurs in **a**. Push `b in a`
`æ` | `a` | Powerset. Push `powerset(a)`
`ç` | `a` | Convert **a** from an ASCII value to its corresponding character (Chr). Push char **a**
`è` | `a,b` | Indexing (0-based, modular). Push `a[b]`
`é` | `a` | Sort **a** by length
`ê` | `a` | Sorted uniquify. Push`sorted_uniquified(a)`
`ì` | `a,b` | Merge **b** with **a** if both are lists, else prepend **b** to **a**. Push `a.prepend(b)`
`í` | `a` | Reverse each. Push `[reversed(Q) for Q in a]` (short for `€R`)
`î` | `a` | Ceil. Push `round_up(a)`
`ï` | `a` | Trim decimals. Push `int(a)`
`ô` | `a,b` | Split **a** in pieces of length **b**
`ö` | `a,b` | Convert **a** from base **b** to integer. Push `int(a, b)`
`õ`  | - | Empty string
`ø` | `(a,)b` | Zip. Transpose **b** if **b** is list, else interleave **a** and **b** (`zip(a,b)`)
`ù` | `a,b` | Keep the elements of **a** of length **b**
`ú` | `a,b` | Pad **a** with **b** spaces in the front
`û` | `a` | Palindromize. Push `palindromized(a)` (e.g. `12345` becomes `123454321`, `a + a[::-1][1:]`)
`ü`  | - | Pairwise command (vectorizes if the first element is a list)
`ý` | `(a),b` | Push `b.join(a)` if **a** is a list, else `b.join(stack)`
`þ` | `a` | Digits of **a**
`.å`| `a,b` | Check whether **a** occurs in **b**. Push `a in b` (non-vectorized)
`.b`| `a` | Letteriquify **a**. Push `letterified(a)`
`.B`| `a` | Squarify **a**. Push `squarified(a)`
`.c`| `a` | Left-focused centralize. Push `centralized_left(a)`
`.C`| `a` | Right-focused centralize. Push `centralized_right(a)`
`.D`| `a,b` | Push **b** copies of **a** if **b** is an integer, else push **len(b)** copies
`.g`| - | Length of the stack
`.I`| `a,b` | **b**th permutation of **a**
`.k`| `a,b` | Flat index of **b** in **a**
`.l`| `a` | Is lowercase? Push `is_lower(a)`
`.L`| `a,b` | Levenshtein distance. Push `levenshtein(a, b)`
`.M`| `a` | Mode. Push most frequent element in **a**
`.m`| `a` | Counter-Mode. Push least frequent element in **a**
`.n`| `a,b` | Logarithm of **a** in base **b**. Push `log_b(a)`
`.o`| `a,b` | Overlap. Push `overlap(b)`
`.p`| `a` | Prefixes. Push `prefixes(a)`
`.s`| `a` | Suffixes. Push `suffixes(a)`
`.S`| `a,b` | Compare. Push **1** if **a > b**, **-1** if **a < b**, **0** if **a** equals **b**
`.u`| `a` | Is uppercase? Push `is_upper(a)`
`.$`| `a,b` | Drop **b** elements from **a** (`a[b:]`)
`._`| `a,b` | Rotate **a** **b** units to the left
`.:`| `a,b,c` | Replace all. Push `a.replace(b, c)`
`.;`| `a,b,c` | Replace first. Push `a.replace_first(b, c)`
`.±`| `a` | Sign. Push **-1** if **a < 0**, **1** if **a > 0**, **0** otherwise.
`.ª`| `a` | Sentence capitalisation. Push `sentence_cased(a)`
`.²`| `a` | Logarithm with base **2**. Push `log_2(a)`
`.ï`| `a` | Integer? Push `is_int(a)`
`.¿`| `(a,)b` | Least common multiple (lcm / hcf). Push `lcm(b)` if **b** is list, else push `lcm(b, a)`
`.γ`| `a` | Group **a** by function result. Usage: `.γ CODE }`
`.ø`| `a,b` | Surround **a** with **b**
`.«`| `a` | Right Reduce (foldr). Folds a dyadic command between each element in a list from right to left
`.»`| `a` | Left Reduce (foldl). Folds a dyadic command between each element in a list from right to left with opposite right / left operands
`.¢`| `a,b` | Count the occurrences of **b** in **a** without vectorizing.
`.ι`| `a,b` | Interleave **a** and **b**
`.š`| `a` | Swap / Switch capitalisation. Push `switch_cased(a)`
`.Δ`| `a` | Find the first element of **a** that results in **1** when ran through `CODE`. Usage: `.Δ CODE }`
`.ā`| `a` | Enumerate **a**. Push `enumerated(a)`
`.À`| - | Rotate stack 1 left
`.Á`| - | Rotate stack 1 right
`.¥`| `a` | Undelta. Push the cumulative sum of **a**, with a zero prepended
`.º`| `a` | Intersected mirror
`.∊`| `a` | Intersected vertical mirror
`.Æ`| `a,b` | All **b**-element combinations of **a**
`.ý`| `a,b` | Intersperse **a** with **b** (e.g. `[1, 2, 3] 0 .ý --> [1, 0, 2, 0, 3]`)
`.Ø`| `a` | 0-based index of the greatest prime less than or equal to **a**
`.ò`| `a,b` | Round **a** with **b** digits precision (bankers rounding)
`.Œ`| `a,b` | Partitions of **a** containing **b** elements. All possible ways to divide **a** into **b** pieces
`.œ`| `a` | Partiton **a**
`.£`| `a,b` | Last **b** elements  of **a**. Push `a[-b:]`
`т`  | - | Push 100
`₁`  | - | Push 256. In a recursive environment, push **a(n - 1)** instead.
`₂`  | - | Push 26. In a recursive environment, push **a(n - 2)** instead.
`₃`  | - | Push 95. In a recursive environment, push **a(n - 3)** instead.
`₄`  | - | Push 1000. In a recursive environment, push **a(n - 4)** instead.
`₅`  | - | Push 255. In a recursive environment, pop **x** and push **a(x)** instead.
`₆`  | - | Push 36. In a recursive environment, pop **x** and push **a(n - x)** instead.
`"`  | - | Start / End string literal
`$`  | - | Push 1 and input (used for sequences)
`'`  | - | Character literal (e.g. `'a` pushes `"a"`)
`)`  | - | Wrap total stack to an array
`0`  | - | Numeric literal
`1`  | - | Numeric literal
`2`  | - | Numeric literal
`3`  | - | Numeric literal
`4`  | - | Numeric literal
`5`  | - | Numeric literal
`6`  | - | Numeric literal
`7`  | - | Numeric literal
`8`  | - | Numeric literal
`9`  | - | Numeric literal
`}`  | - | Used to close if statements, loops, etc.
`¤`  | - | Tail (Get **a**). Push `tail(a)`
`¬`  | - | Head (Get **a**). Push `head(a)`
`²`  | - | Second item from the input history
`³`  | - | Third item from the input history
`¶`  | - | Newline character (`\n`)
`¹`  | - | Push the first item from the input history
`º`  | - | Mirror.
`Î`  | - | Push 0 and input
`Ð`  | - | Triplicate top of stack (pop **a**, push **a**, push **a**, push **a**)
`ð`  | - | Push a space character

## `Å` - Commands (Extended Commands)

| Command | Elements Popped | Description |
|:-------:|:---------------:| ----------- |
| `Å!` | `a` | Produces a list of all factorials lower or equal than `a` |
| `Å¡` | `a,b` | Split a on truthy indices in b. Example: `[1, 2, 3, 4], [0, 1, 0, 0] -> [[1], [2, 3, 4]]`
| `Å0` | `a` | Produces a list of 0's with length **a** |
| `Å1` | `a` | Produces a list of 1's with length **a** |
| `Å2` | `a` | Produces a list of 2's with length **a** |
| `Å3` | `a` | Produces a list of 3's with length **a** |
| `Å4` | `a` | Produces a list of 4's with length **a** |
| `Å5` | `a` | Produces a list of 5's with length **a** |
| `Å6` | `a` | Produces a list of 6's with length **a** |
| `Å7` | `a` | Produces a list of 7's with length **a** |
| `Å8` | `a` | Produces a list of 8's with length **a** |
| `Å9` | `a` | Produces a list of 9's with length **a** |
| `Å?` | `a,b` | Check if **a** starts with **b** |
| `Å¿` | `a,b` | Check if **a** ends with **b** |
| `Å=` | `a` | Deck shuffle **a** (e.g. `[1, 2, 3, 4, 5, 6, 7] --> [1, 5, 2, 6, 3, 7, 4]`) |
| `Å≠` | `a` | Deck unshuffle **a** (e.g. `[1, 5, 2, 6, 3, 7, 4] --> [1, 2, 3, 4, 5, 6, 7]`) |
| `Åγ` | `a` | Run-length encode **a** |
| `ÅΓ` | `a,b` | Run-length decode **a** with **b** (pushes the elements and the chunk lengths separately) |
| `Å\` | `a` | Produces the main diagonal (left) of a matrix **a** |
| `Å/` | `a` | Produces the anti-diagonal (right) of a matrix **a** |
| `Å\|`| `a` | Produces the columns of a matrix **a** |
| `ÅÏ` | `a,b` | Apply a function to the elements in **a** for which the corresponding element of **b** is truthy (1). Usage: `ÅÏ CODE }` |
| `ÅΔ` | `a` | Computes the index of the first element of **a** for which `CODE` returns **1**. Usage: `ÅΔ CODE }` |
| `ÅA` | `a` | Computes the arithmetic mean of **a** |
| `ÅF` | `a` | Computes a list of all Fibonacci numbers lower or equal to **a** |
| `ÅG` | `a` | Computes a list of all Lucas numbers lower or equal to **a** |
| `ÅL` | `a,b` | Limit by, return **a** if **a** < **b** else **b** |
| `ÅM` | `a` | Previous prime. Highest prime less than **a** |
| `ÅN` | `a` | Next prime. Lowest prime greater than **a** |
| `Ån` | `a` | Nearest prime. In case of a tie, the higher prime is pushed |
| `ÅP` | `a` | Computes a list of all prime numbers lower or equal to **a** |
| `ÅT` | `a` | Computes a list of all triangular numbers lower or equal to **a** |
| `Å€` | `a,b` | Apply `CODE` to every **b**th element of **a**. Usage: `Åe CODE }`
| `ÅU` | `a,b` | Computes the **a**th **b**-gonal number |
| `Åf` | `a` | Computes the **a**th Fibonacci term |
| `Åg` | `a` | Computes the **a**th Lucas term |
| `Åm` | `a` | Median. Sorts the list, then returns either the middle element or the average of the middle elements depending on the parity of the length of the list.
| `Ås` | `a` | Middle. Push the middle element / character of `a`
| `Åp` | `a` | Produces a list of the first **a** primes |
| `Ål` | `a` | Produces the lower triangular matrix of **a** |
| `Åu` | `a` | Produces the upper triangular matrix of **a** |
| `Åœ` | `a` | Integer partitions of **a** (all possible combinations of positive integers that sum to **a**) |
| `Åβ` | `a,b` | Push **a** converted from custom base **b** |
| `Åв` | `a,b` | Push **a** converted to custom base **b** |
| `Å²` | `a` | Check whether **a** is a square number |
| `Å»` | `a` | Cumulative reduce left. Usage: `Å» CODE }` |
| `Å«` | `a` | Cumulative reduce right. Usage: `Å« CODE }` |
| `ÅÈ` | `a` | Produces a list of all non-negative even numbers lower or equal to **a** |
| `ÅÉ` | `a` | Produces a list of all non-negative odd numbers lower or equal to **a** |
|`Å½`| `a` | Sine. Push `sin(a)`
|`Å¾`| `a` | Cosine. Push `cos(a)`
|`Å¼`| `a` | Tangent. Push `tan(a)`

## `ž` - Commands (Constants)

Command|Description|
-------|-----------|
`ža` | Push current hours
`žb` | Push current minutes
`žc` | Push current seconds
`žd` | Push current microseconds
`že` | Push current day
`žf` | Push current month
`žg` | Push current year
`žh` | Push `[0-9]`
`ži` | Push `[a-zA-Z]`
`žj` | Push `[a-zA-Z0-9_]`
`žk` | Push `[z-aZ-A]`
`žl` | Push `[z-aZ-A9-0_]`
`žm` | Push `[9-0]`
`žn` | Push `[A-Za-z]`
`žo` | Push `[Z-Az-a]`
`žp` | Push `[Z-A]`
`žq` | Push **pi**
`žr` | Push **e**
`žs` | Decimal expansion of **pi** (infinite list)
`žt` | Decimal expansion of **e** (infinite list)
`žu` | Push `()<>[]{}`
`žv` | Push `16`
`žw` | Push `32`
`žx` | Push `64`
`žy` | Push `128`
`žz` | Push `256`
`žA` | Push `512`
`žB` | Push `1024`
`žC` | Push `2048`
`žD` | Push `4096`
`žE` | Push `8192`
`žF` | Push `16384`
`žG` | Push `32768`
`žH` | Push `65536`
`žI` | Push `2147483648`
`žJ` | Push `4294967296`
`žK` | Push `[a-zA-Z0-9]`
`žL` | Push `[z-aZ-A9-0]`
`žM` | Vowels. Push `"aeiou"`
`žN` | Consonants. Push `"bcdfghjklmnpqrstvwxyz"`
`žO` | Vowels including y. Push `"aeiouy"`
`žP` | Push `"bcdfghjklmnpqrstvwxz"`
`žQ` | Push printable ASCII character set (32-128)
`žR` | Push `"ABC"`
`žS` | Push `qwertyuiop`
`žT` | Push `asdfghjkl`
`žU` | Push `zxcvbnm`
`žV` | Push `["qwertyuiop", "asdfghjkl", "zxcvbnm"]`
`žW` | Push `qwertyuiopasdfghjklzxcvbnm`
`žX` | Push `"http://"`
`žY` | Push `"https://"`
`žZ` | Push `"http://www."`
`žÀ` | Push `aeiouAEIOU`
`žÁ` | Push `aeiouyAEIOUY`
`žĆ` | Push the 05AB1E codepage.
