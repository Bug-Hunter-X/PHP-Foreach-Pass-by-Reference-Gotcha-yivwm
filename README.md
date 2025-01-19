# PHP Foreach Loop Pass-by-Reference Issue

This repository demonstrates a common, yet subtle, error in PHP related to how foreach loops handle references.  When using pass-by-reference inside a foreach, modifications to the loop variable directly affect the original array element, potentially leading to unintended side effects.

The `bug.php` file contains code that showcases this behavior. The `bugSolution.php` file provides a corrected version.

## How to Reproduce

1. Clone this repository.
2. Run `bug.php` using a PHP interpreter.
3. Observe the unexpected output.
4. Run `bugSolution.php` to see the corrected behavior.

## Explanation

The issue stems from the use of `&$value` in the foreach loop. This passes the array element by reference, meaning any changes made to `$value` within the loop directly alter the original array element.

The solution uses a `copy` to prevent side effects.