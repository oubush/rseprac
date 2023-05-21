# Problem 2
See the problem_2 subdirectory.
A researcher you have met regularly runs several hundred samples through an analysis machine over the weekend. Most of the time each sample run completes fully, writing 100 values into a numbered file for that sample. Occasionally, a sample run fails and fewer than 100 values are written to a file.
Can you show this researcher how to quickly identify the sample files that have fewer than 100 values?

# Answer to the problem 2

It is assumed that values are written in a file with whitespace as a separator, and therefore, numeric values may be considered as distinct words in the file.

A quick way to identify the sample files that have fewer than 100 values is to count the number of words in each file and search for the results that are not equal to 100.

For example,

```
for file in *; do wc -w "$file"; done | grep -v 100
```

The `for` loop iterates over each file and counts the number of words. Then, the `grep` command with the option `-v` filters out the lines that contain the number 100, showing only the files with word counts different from 100.

If you need more precise result, for example, only less than 100 values, the command may be more complex to test the condition:

```
for file in *; do test $(wc -w "$file" | grep -o '^[0-9]\+') -lt 100 && echo $(wc -w "$file"); done
```

The `grep -o '^[0-9]\+'` extracts integer number of words from the `wc` output.

The `test` with the option `-lt` checks if the word count is less than 100. If true, it prints the `wc` output: the number of words and the file name.

Note that if there are no files with values greater than 100, the result will be the same.

It was found that the file `values44` contains only 99 values.

The results of the problem_2 solution can be found in the [problem_2_results](/problem_2_results) directory.