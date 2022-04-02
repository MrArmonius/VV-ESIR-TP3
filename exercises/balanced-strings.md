# Balanced strings

A string containing grouping symbols `{}[]()` is said to be balanced if every open symbol `{[(` has a matching closed symbol `]}` and the substrings before, after and between each pair of symbols is also balanced. The empty string is considered as balanced.

For example: `{[][]}({})` is balanced, while `][`, `([)]`, `{`, `{(}{}` are not.

Implement the following method:

```java
public static boolean isBalanced(String str) {
    ...
}
```

`isBalanced` returns `true` if `str` is balanced according to the rules explained above. Otherwise, it returns `false`.

Use the coverage criteria studied in classes as follows:

1. Use input space partitioning to design an initial set of inputs. Explain below the characteristics and partition blocks you identified.
2. Evaluate the statement coverage of the test cases designed in the previous step. If needed, add new test cases to increase the coverage. Describe below what you did in this step.
3. If you have in your code any predicate that uses more than two boolean operators check if the test cases written so far satisfy *Base Choice Coverage*. If needed add new test cases. Describe below how you evaluated the logic coverage and the new test cases you added.
4. Use PIT to evaluate the test suite you have so far. Describe below the mutation score and the live mutants. Add new test cases or refactor the existing ones to achieve a high mutation score.

Write below the actions you took on each step and the results you obtained.
Use the project in [tp3-balanced-strings](../code/tp3-balanced-strings) to complete this exercise.

## Answer
1. First, we have the empty String test where the function must return True. Then, we have 3 characteristics, these are `[]`, `{}` and `()`. We have one block for each characteristics where they are alone. For example we have block one where we test only the `[]` and `][`. The first one is right but the last is false, moreover the last example test also when the first symbol is a close symbol. Furthermore, we have one more block for combinaison of characteristics, `[{()}]` and his false version `[{{()}]`. And the final version is when we have the same number of closed and opened symbo but the result is false, `([)]`.
2. We used the librairy Jacoco to know the statement coverage of our function. We obtain a 100% coverage:
![image](images/jacoco_BalancedString.png)
4. 85
5. [Pit plugin maven](https://pitest.org/quickstart/maven/)
