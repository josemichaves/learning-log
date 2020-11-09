# Bash



_Redirection_ reroutes standard input, standard output, and standard error.

The common redirection commands are:

```bash
ls -l > output.txt

```

Redirects standard output of a command to a file, overwriting previous content.



```bash
cat >> test.txt
```

Redirects standard output of a command to a file, appending new content to old content.



```bash
pwd < fie.txt
```

Redirects standard input to a command.



```bash
cat text.txt | ls
```

 Using the pipe operator `|` we can chain multiple commands together, so that the `stdout` of the command at the left of the operator is passed to the `stdin` of the command at the right of it

A number of other commands are powerful when combined with redirection commands:

```bash
sort filename.txt
```

Sort the lines of the file alphabetically.



```bash
uniq file.txt
```

Find adjacent duplicates and delete its.



```bash
grep "test" fileName.txt
```

The grep command searches the given files for lines containing a match to a given pattern list.



```bash
sed 's/directory/wordToReplace/g' testFile.txt
```

SED is a powerful text stream editor. Can do insertion, deletion, search and replace\(substitution\).

