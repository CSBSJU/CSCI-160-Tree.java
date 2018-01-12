Tree.java
=========

Write a Java class `Tree` that is a Java implementation of the GNU utility
`tree`, which you should be familiar with from prelabs. The class should define
the following:

* Private static methods
  * `tree(String, String)` -- takes two `String` reference variables as
    parameters. The first `String` will be the path, i.e., `/usr/people/...`,
    for which we are creating the tree. The second `String` will be a line
    prefix, i.e., the prefix that will be added to each line to indicate the
    level in the file hierarchy to which it belongs

    A sample algorithm for the `tree(String, String)` method might look something like:
    * Get a list of files/directories contained in the path that was passed as
      an argument
    * For each of those, do the following:
      * Print some prefix, indicating its depth in the file hierarchy, followe
        by `"|-- <name> "`, where `<name>` should be replaced with its name
      * After printing its name, generate the tree for the files/directories
        that it contains by calling `tree(String, String)` recursively. You
        should append its name to the path that was passed as a parameter, as
        well as adjust the prefix appropriately to indicate that the subsequent
        tree is at a deeper level in the file hierarchy
      * If you really want to get fancy, do the above two steps for all but the
        last file/directory. For the last, print the prefix followed by `` "`--
        <name>" ``

* Public static methods
  * `tree(String)` -- takes a single `String` reference variable as a parameter.
    The parameter is the path, i.e., `/usr/people/...`, for which we are
    creating the tree. This method is the entry point for the recursive method
    `tree(String, String)` described above. It will simply call the recursive
    `tree` method, passing its parameter as the first parameter and the empty
    string `""` as the second parameter.

Your program should include the ability to be invoked (run) from the command
line. If it is invoked without any arguments, then it should create a tree for
the directory `"."`. If it is invoked with any number of arguments greater than
zero, then it should create a tree for each of those.

Be sure to include JavaDoc comments for each of the methods that you create!!

Example inputs/outputs:

```
:> java Tree
.
|-- Assignment.html
|-- solution
|    `-- Tree.class
|-- Tree.class
`-- Tree.java

:> java Tree ~/CS160/labs/Lab02 ~/CS160/labs/Lab03
/home<username>/CS160/labs/Lab02
|-- Lab.docx
`-- Lab.pdf
/home<username>/CS160/labs/Lab03
|-- Lab.html
|-- Prelab.html
|-- Race.java
|-- Race.class
`-- solution
     |-- Race.class
     `-- Race.java
```

Submitting your assignment

Testing
