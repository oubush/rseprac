# Problem 3:
See the task_3 subdirectory. A researcher has approached you with a piece of Python code (pyscript.py in the problem_3 subdirectory) which seems to be running slower than she expects.
She doesn’t want you to fix the code, but would like you to explain some general principles that she can apply herself to investigate the code and work out where the problems are.
What would you suggest?

# Answer to the problem 3 

Some general principles for investigating the code are:

1. Utilise profiling. Specialised profiling tools like cProfile or Py-Spy can help measure and analyse the performance characteristics and behaviour of the program. Profiling can provide insights into which lines of code are time-consuming, how often certain functions are  called and identify any inefficient loops or redundant calculations. It can also help uncover memory issues.

2. Incorporate timing code. Adding timing code allows you to measure the execution time of individual code sections. This helps identify which parts contribute the most to the overall runtime. The time module in Python can be used to measure the elapsed time for specific sections.

3. Evaluate the choice of data structures and algorithms. Consider if there are more efficient data structures and algorithms that can be used in the code.

4. Analyse the computational complexity of the code. Identify any nested loops or operations that scale poorly with input size. Look for opportunities to eliminate unnecessary iterations or simplify conditions.


Regarding the code in `pyscript.py`, it appears to be written in Python 2. However, it is generally recommended to use Python 3 since Python 2 has reached its end of life and is no longer actively maintained or updated. Migrating to Python 3 for new code can provide performance benefits due to improved handling of operations and memory management.
