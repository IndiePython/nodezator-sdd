
[← back to System testing index/guide](README.md)

# How to organize/manage system testing

This guide explains how to organize and manage system testing and its test cases.


## General rules


### Unique identifiers and naming convention

Each test case has a unique identifier (UID) which is a natural number. Each test case has a dedicated .md file named with the initials STC (System test case) in lowercase letters and its unique identifier right-justified with zeroes (the "0" character), like this: `stc-0000.md`, `stc-0001.md`, etc.

In the distant future, if new unique ids require more digits, the files should probably be renamed to include additional zeroes as needed. It should be possible to do this easily with a script, since the file names and contents are based on a template. 


### Authorship info

Test cases don't include info on the people who create/update them nor corresponding dates of such events. All this info is tracked by the version control system already.



## General principles

### Avoid creating tests

Tests require significant maintenance over time[^1]. Of course, they are well worth it despite that fact. However, this is only true on the condition that we are careful to introduce only relevant tests.

Otherwise, we'll end up with a bloated collection of test cases that that generates additional useless work for us.

This notion that tests are costly seems to be very neglected in technical literature. Most of the time such materials speend too much time praising the benefits of testing and not enough time teaching people about the need to create only the minimum amount of tests required and about the maintenance costs of tests. 


### Avoid deleting tests

There may be valid reasons for removing tests, like an experimental or regular feature that is dropped, for instance. However, as explained by Mr. Roy Osherove in [this article](https://osherove.com/blog/2005/4/3/when-should-you-remove-or-change-a-unit-test.html), when a change in the source causes a test to no longer be valid in the new context, instead of removing it it is usually better to change it so it also works in the new context, when possible.

This is important because the change that turns a test obsolete may have nothing to do with what was being tested. Thus, the value of the test is still there. The only difference is that a requirement/dependency changed and made it so it was no longer passing.

As an example, the author mentions a class called "Person" that receives a single argument in its construction and is later changed to require 02 arguments instead[^2].

In this situation, all the corresponding tests are no longer valid and will naturally fail, but they still have code that properly tests all the existing functionality of that class. Thus, there's no actual need to remove the tests. We should just update them so they work with the change.

Better yet, since instantiation is the problem here, it could additionally be factored out of the tests (perhaps moving instantiation to a "setup" stage). This way, whenever we need to change the instantiation, we could do it in a single place (the setup), and we'd not need even touch the tests themselves.

As the author (Mr. Osherove) points out, just like normal code, test code should also avoid duplication.

Such remarks may sound a obvious given the simple example used, but in practice, detecting this kind of things is more difficult because the problems are more complex and nuanced.

[^1]: "Avoid creating tests" subsection was based on this online thread: https://twitter.com/KennedyRichard/status/1738227712240832695
[^2]: part of "Avoid deleting tests" subsection was based on this online thread: https://twitter.com/KennedyRichard/status/1762937923861643540
