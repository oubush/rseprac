# Problem 1:
See the problem_1 subdirectory.
A researcher has inadvertently renamed all their 100 data files with the wrong file extension and doesn’t know how to change them back.
Show you can rename the files to have a .dat file extension and explain to the researcher how they can do this themselves if they make this mistake again.

# Answer to the problem 1

To rename the files to have a .dat file extension in Linux, first navigate to the directory where the data files are located using the `cd` command, for example:

```
cd rseprac/problem_1
```

Now you have two options to rename the files.

1. Use `rename` command to rename all the files at once with the option `-v` and regular expression pattern `'s/.csv/.dat/'`.

```
rename -v 's/.csv/.dat/' *.csv 
```
`'s/'` indicates a substitute expression, which replaces a part of the filename with a different string. 
In this case, `'s/.csv/.dat/'` indicates that `.csv` is replaced by `.dat`. 

`*.csv` matches all files with extension `.csv` in the directory.

If `rename` command is not available, it may be installed. For example, 

```
sudo apt install rename
```


2. If `rename` command is unavailable, you can use `mv` command. 

To rename one file, for example `datafile1.csv`:

```
mv datafile1.csv datafile1.dat
```

To rename all the files, use a `for` loop in combination with the `mv` command:

```
for filename in *.csv; do mv "$filename" "${filename%.*}.dat"; done
```

A `for` loop allows you to iterate over each file in the directory.

`${filename%.*}` extracts the base filename (without the extension).

The results of the problem_1 solution can be found in the [problem_1_results](/problem_1_results) directory.
