
[← back to table of contents](README.md)

# Test-driven software development in Nodezator

Software development in Nodezator should follow as closely as possible the practices prescribed by [test-driven software development](https://en.wikipedia.org/wiki/Test-driven_development). From its inception, the development of Nodezator didn't follow any specific development process, but relied mostly on the proficiency of its creator (me, Kennedy) with Python and the pygame library to quickly create a working prototype. Although this approach is not fit for long-term projects of large scope, it works when the creator has a clear vision of the structure and basic design of the software.

Because of that, I could create Nodezator swiftly. Within 02 months I had the first working prototype. In the next following years I added more basic functionality to it until the point where it could be published, in a very basic but useful state. At that point in time, I had spent much effort into refactoring, but also some non-trivial effort into testing. Nodezator featured unit tests for some of its subpackages/modules/classes in the form of doctests. Since then, some users also contributed unit tests in the form of regular unit tests, that is, test cases written with the [unittest](https://docs.python.org/3/library/unittest.html) module.

However, early in the development process, long before Nodezator's release, I had already realized how crucial test-driven development is for managing and pushing forward the development of software, even more so when expecting collaboration from other developers. But, there were a few reasons I didn't adopt test-driven development from the beginning.

First, because despite having an idea of the basic requirements of Nodezator, I wanted to quickly put together a working prototype, so I could experiment with it to further refine my designs, ideas, expectations, etc.

Second, because a working prototype motivates the development process because of the feedback provided. That is, one thing is to have the ideas written and another thing entirely is to have the thing working in front of you.

Third, because despite how crucial TDD is for the continued stability and maintainability of complex long-lived software, it isn't so in its first steps. Rather, it may work as an obstacle, if it slows down progress by absorbing too much time and effort into the specification and design of a system that you don't even know if it will work as expected yet. There's just too many unknowns.

Finally, because in order to be able to fully test the most essential aspects of Nodezator, I needed to design and implement an automated GUI testing system, but at the time I didn't even have an idea of how to design it. Nowadays, after working for so long in Nodezator, I finally managed to idealize, design and implement an automated GUI testing system, that only lacks some final touches before being put to effective usage. This automated GUI testing system was actually already tested and works fine, just need the final touches before being released.



## Kinds of tests in Nodezator

Different kinds of tests are employed to ensure different components/aspects of the application work as expected.



### Unit tests

Unit tests are used to test atomic units of code in isolation, things like subpackages, modules, classes, functions, methods. Unit tests are implemented in Nodezator in several different ways:

- doctests in markdown files
- doctests in Python source (docstrings)
- test cases from the [unittest](https://docs.python.org/3/library/unittest.html) module

Doctests are managed with help from the [doctest](https://docs.python.org/3/library/doctest.html) standard library module.

Each of those different ways in which unit tests are implemented have their own advantages. All of them are supposed to be run using the `unittest` module, taking advantage of the great integration between the `doctest` and `unittest` modules. In practice, however, test discovery for doctests in Python source has yet to be set (this should be quick to do and I expect to have it done and available in the next release), and must be run manually for each file (we'll explain how further ahead).

In order to run all the unit tests present in Nodezator source, all you have to do is execute the following command from the top directory of the repository:

```
python3 -m unittest
```

The Python installation/environment used in the command must have `pygame-ce` (maybe `numpy` as well, but I'm not sure) installed as well, because there are units tested that rely on objects from such modules. Such modules are also required by Nodezator anyway, so there's no harm in having them available.

Depending on the system you'll have to replace `python3` by `python` or another similar command.

The command above triggers test discovery for the `unittest` module, which causes all unit tests found in the package to be run. The reason the `unittest` also executes doctests present in the package is because doctests can be converted into test cases that can be run by the `unittest` module, which we do in the package to guarantee maximum integration, that is, the ability to run all tests with a single command.

Once we set test discovery for doctests in Python source, that command will also execute them all automatically, but for now you'll have to run such docstests using the `doctest` module, passing the path to the Python file as an argument like this:

```
python3 -m doctest nodezator/ourstdlibs/behaviour.py
```

If the tests run without problems, no text will appear on the terminal. If they (or some of them) fail, a report will be displayed. You can also add the `-v` option to the command above, so a report is always displayed regardless of whether the tests fail or succeed.

Besides setting test discovery for doctests in Python source, two other improvements are desired for unit tests.

First, we need test discovery to be able to run the tests without launching the app. When test discovery is run with `python3 -m unittest` as explained earlier, the Python interpreter loads and executes tests in the repository. When this happens, the app itself seems to be launched as well, since a window appears (probably due to the corresponding modules being loaded/executed). This doesn't harm the testing and it is so quick that no graphics are loaded/shown in the window. The window quickly disappears. Even so, this behaviour is unexpected and unneeded, as well as potentially harmful, since it may prevent tests from happening or passing by altering state or simple causing unrelated errors that prevent the tests from proceeding.

The second and final desired improvement would be a way to isolate the tests even further, so that only specific tests would run when desired, instead of every test. There's no actual need for this at the moment, but seems like a useful feature to have, that may help when troubleshooting a bug that is related to a specific set of tests. This would speed up such process by allowing us to only trigger the specific tests needed.



### System testing via automated GUI interactions

The wikipedia entry on [system testing](https://en.wikipedia.org/wiki/System_testing) states:

> System testing is testing conducted on a complete integrated system to evaluate the system's compliance with its specified requirements. [...]
>
> System testing is performed on the entire system in the context of either functional requirement specifications (FRS) or system requirement specification (SRS), or both. [...]

Furthermore, about [functional requirement](https://en.wikipedia.org/wiki/Functional_requirement), it states:

> In software engineering and systems engineering, a functional requirement defines a function of a system or its component, where a function is described as a summary (or specification or statement) of behavior between inputs and outputs.
>
> Functional requirements may involve calculations, technical details, data manipulation and processing, and other specific functionality that define what a system is supposed to accomplish. [...] Functional requirements are supported by non-functional requirements (also known as "quality requirements"), which impose constraints on the design or implementation (such as performance requirements, security, or reliability). Generally, functional requirements are expressed in the form "system must do <requirement>," while non-functional requirements take the form "system shall be <requirement>." [...]

Finally, on [system requirement/requirement analysis](https://en.wikipedia.org/wiki/Requirements_analysis), we have:

> In systems engineering and software engineering, requirements analysis focuses on the tasks that determine the needs or conditions to meet the new or altered product or project, taking account of the possibly conflicting requirements of the various stakeholders, analyzing, documenting, validating and managing software or system requirements.

In summary, system testing help developers ensure the system/application is working properly taking functional and/or system requirements into account.

This is actually a large topic with many subtopics and a very large scope.

For Nodezator developers, it mostly means ensuring Nodezator meets functional requirements via automated GUI interactions. Non-functional and system requirements should be taken into account as well, but should be defined and integrated in system testing as we progress with its implementation/consolidation with the functional requirements.

The reason non-functional and system requirements are not given the same focus from the beginning is that it takes more time and experimentation to properly define them, whereas defining functional requirements is more straightforward. The definition of non-functional and system requirements are more ambiguous/unclear in some aspects as well.

For instance, if we were to define a non-functional requirement related to the speed of graph execution, what would be the criteria to define how quick it should be? Or how slow it could get and still be tolerable? (we are talking about the tasks the run between node execution, since the execution of each node is specific to the nodes used/defined by the user and not something over which we have control). This would also depend on hardware and other factors.

Such kind of non-functional requirement is something that we'd only be able to approach, if at all, after much experience and refinement of the graph execution code, so that we could pick relevant criteria. Moreover, design principles play a role as well, that is, we might consider a specific execution time to be satisfactory whereas another project would consider it prohibitive. In the case of the Nodezator project, this example of non-functional requirement of graph execution speed is something with which we would not worry about so soon, since our priority is that the solution is working effectively and "quick enough". Only in the more distant future after our priority features are implemented we'll concern ourselves with speed and efficiency. For now our focus is effectiveness and simplicity/maintainability.

Each requirement, regardless of its kind, should be tested by at least one test case. It is possible that a single test case may test more than one requirement, though.

Test cases for system testing are documented in a dedicated appendix: [Test cases for system testing](apx-test-cases-system-testing/README.md).

Tests from test cases are performed with help from automated GUI interactions, which are part of the playback feature presented on the chapter about [Nodezator features](ch-nodezator-features.md).Such automated GUI interactions helps support system testing, although system testing itself is not part of the playback feature (which is why it doesn't appear in the diagram).
