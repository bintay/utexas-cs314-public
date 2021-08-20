# Public UT Austin CS 314 Utility Files
Some of my utility files for CS 314 that have been made public with the permission of Mike Scott.

Contributions are appreciated!

## Checkstyle

Checkstyle is a program that will check your code for formatting errors. This includes rules on the [Code Hygiene Guide](https://www.cs.utexas.edu/~scottm/cs314/handouts/hygiene_guide/code_hygiene_guide_framed.html) as well as other stricter rules for more consistent code. Hopefully, this will save you a few points on code styling!

The configuration file is in `cs314.checkstyle.xml`.

### Command Line Usage

You can get the command line version of checkstyle at https://checkstyle.org/.

Once installed, you can run the program with:

```bash
java \
  -jar PATH_TO_CHECKSTYLE/checkstyle.jar \
  -c PATH_TO_CHECKSTYLE_CONFIGURATION/cs314.checkstyle.xml \
  PATH_TO_ASSIGNMENT_FILES/*.java
```

You'll see output like the following:

```
[WARN] /Users/bent/Documents/school/courses/cs314/A1/CodeCampTester.java:481:17: '{' is followed by whitespace. [NoWhitespaceAfter]
[WARN] /Users/bent/Documents/school/courses/cs314/A1/CodeCampTester.java:411:50: '31415' is a magic number. [MagicNumber]
[WARN] /Users/bent/Documents/school/courses/cs314/A1/CodeCampTester.java:26:5: Method main length is 802 lines (max allowed is 25). [MethodLength]
```

If you get warnings in your solution code, fix them! 

In your test file, you can suppress some warnings using the following annotation:

```java
...
@SuppressWarnings({
    "checkstyle:magicnumber",
    "checkstyle:multiplestringliterals",
    "checkstyle:methodlength", 
    "checkstyle:executablestatementcount",
    "checkstyle:descendanttoken",
    "checkstyle:npathcomplexity",
    "checkstyle:javancss",
    "checkstyle:cyclomaticcomplexity"
    // add more if you need to
})
public final class CodeCampTester {
...
```

### Usage with IDE (Instead of Command Line)

This is untested, but there are IDE extensions for [Eclipse](https://checkstyle.org/eclipse-cs/#!/), [IntelliJ](https://plugins.jetbrains.com/plugin/1065-checkstyle-idea), [Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=shengchen.vscode-checkstyle), and others (search "\<your favorite IDE\> java checkstyle extension"). Follow the instructions on their respective pages to install and use checkstyle!
