
[← back to README/table of contents](README.md)

# Nodezator definition, usage and goals

Before worrying about Nodezator's design we must know what it is supposed to be, how it is supposed to be used and which goals it aims to achieve.



## Nodezator's definition

Nodezator is a generalist multi-purpose language-first visual node editor for the Python programming language. A Python desktop application meant to run in any platform that supports the reference implementation of the Python programming language ([GitHub repo](https://github.com/python/cpython) | [website](https://python.org)).

It is generalist and multi-purpose because it doesn't have a specific purpose, but is rather a Python programming environment to achieve whichever purpose the user has. Because of that, you can also see it as a meta-application rather than an application per se.

It is language-first because it is meant to be just a visual representation of a programming language. In other words, it works by using Python and its many libraries within a node-based interface. Its reliance on Python and equivalence to Python is so much that it can even export its graphs as Python code.

Therefore, being language-first is an important distinction. It sets Nodezator apart from most existing node editing solutions, even the ones based on the Python programming language. That's because Nodezator is not only based on Python and can run Python code, but it represents Python code itself and can thus be integrated with Python code/apps/systems/bindings in many ways.

Many node editors, Python-based or not, stand out in their own specific ways by:

- being more focused in specific workflows
- focusing on a specific subset of a language or workflow
- being meant to be used by itself, in isolation from other apps/systems
- or simply because they cannot export their graphs to code

All of those reasons are legitimate and not to be frowned upon and allow such apps to shine in their own ways.

Nodezator, however, tries to be as equivalent to Python as possible, making its design rather unique and simple. It is from this simplicity that it draws its power and flexibility, though: since Nodezator is just a way to represent and manage Python calls in a visual graph, it just has to worry about connecting the Python code. It is like some sort of programming [Lego®](https://en.wikipedia.org/wiki/Lego) blocks.

Once Nodezator provides this ability to combine Python calls its job is done and all the power and flexiblity achievable depends solely on the user's ability to create effective graphs by combining such calls and the data that travels through them.

For instance, this is how a node is defined in Nodezator:

```python
import math # standard lib import

def get_circle_area(radius:float=0.0):
    return math.pi * (radius ** 2)

main_callable = get_circle_area
```

And the resulting node is like this:

![node image](https://nodezator.com/images/get_circle_area_node.png)



## Effective and responsible usage of Nodezator

Despite being a generalist Python (meta-)application though, since it uses a visual node-based interface, it is best for some kinds of tasks. For other kinds of tasks text-based programming or other interfaces like a custom GUI will be more appropriate. Defining which kinds of tasks are better-suited for node-based programming however depends on a lot of factors.

As a principle, I'd say that whenever a solution may rely on the combination of multiple elements (data and/or behaviour), then a node editor will probably help a lot, either entirely by itself or at least in part of the process. If the solution to a problem can be visualized or modelled as a pipeline of data going through different operations then such solution would probably also benefit from a node-based interface.

For instance, media editing is a kind of task that is very compatible with node-based interfaces, because the task itself or some parts of it can be easily represented as data (like images) going through different operations (like filters, exporters, etc.).

Several programming paradigms like functional and dataflow programming are specially suitable to this way of modelling problems, even more so considering that in Nodezator nodes can also be passed on as data (in this case they'd represent references to the callable used to define each of them).

If a library or some kind of data relies on method-chaining to manipulate its data, that is, it has a fluent interface, then a node-based interface like Nodezator has a lot of synergy with it as well, because method-chaining can be easily represented as a sequence of operations with data traveling along such sequence.

The notion that node-based programming is not suited to all kinds of tasks is very important, because many node editor enthusiasts end up irresponsibly promoting the indiscriminate use of node editors for all kinds of problems, leading to subpar results and disappointment when novice/inexperienced node editor users face problems for which a node-based interface is not suited.

Sometimes node editor enthusiasts go even further, claiming that node-based programming will/should replace text-based programming, or that text-based programming is obsolete and things like that. As the creator and maintainer of a node editor myself, such statements sadden me, because they are lies told by overexcited people with little to no experience with nodes or by greedy people that want to promote usage of their tools at all costs for their personal monetary gain.

This ends up discouraging people from using node editors, leading to a loss of efficiency and effectiveness when dealing with the gamut of problems for which node editors are suited to. There isn't anything inherently wrong in being an enthusiast, but when such enthusiasm leads people to make irresponsible claims, it leads to much harm and disinformation.

With Nodezator I decided to go in the opposite direction. I still advocate the intensive/regular usage of node editors, but in a responsible way and for the kinds of problems to which they are suited. This way I believe to be contributing to the increased adoption and effective usage of node editors for programming and other computer tasks, something that will no doubt benefit everyone in the end if done correctly and responsibly.



## Different ways to use Nodezator

Being a generalist Python application, Nodezator has many usages. Its ability to export a graph as Python code also increases the range of possible applications.

It is meant to be used both by itself or in conjunction with other apps/systems. For instance, you could use it...

- by itself, as an app to perform computer/programming-related tasks parametrically
- as a tool to cooperate with other tools/systems by:
    - using it for specific subtasks in a larger process/workflow
    - using the exported Python code directly
    - piping data in and/or out of it
- as a platform wherein to develop your own Python apps
- as a no/low-code interface

In the following subsections we'll discuss each of such usages in detail.



### Using Nodezator by itself to perform computer/programming tasks

Since Nodezator is just a node-based interface to Python, you can use it to perform any computer/programming task you'd use Python for. Given the versatility and popularity of the Python programming language, many standard and third-party libraries exist. Many of them can handle entire workflows by themselves or in conjunction with each other.

This makes it so one can solve a multitude of computer/programming problems by using Python and its libraries alone. Of course, often, additional non-Python libraries and tools are often called under the hood, but this is handled by the libraries themselves and hidden from us Python users or programmers.

The point is: since you can do a lot of stuff with Python alone, and Nodezator is just a node-based interface for Python, then you should be able to use Nodezator alone as well for a lot of tasks, just by performing calls to Python callables that are built into the language, available through libraries or created by the user.

Such tasks that can use Python alone (and thus Nodezator alone) are innumerable. Some instances are media editing, data science, data visualization and generative art.



### Using Nodezator as a tool to use in cooperation with other tools/systems

In much the same way that Python and its libraries can be used by themselves and so can Nodezator, Python and its libraries can also cooperate with other tools and systems, just like Nodezator. I can think of 03 possible ways to use Nodezator in such way.

First, you could simply use Nodezator by itself for a subtask in a larger process/workflow. Using Nodezator this way is much like using it as described in the previous subsection, that is, by itself. The difference is that the tasks performed solely in Nodezator are part of a larger process. For instance, you could use Nodezator to produce animation data and after that use such data in a game.

Second, you could use Nodezator just to build a graph of the Python calls to help you visualize the relationship between the calls and test your system, then just export the Python code in the end and use/paste the code directly in another system/tool. Since Nodezator just provides a visual representation of Python calls and can thus export the equivalent Python code, you can just do that and use the Python code directly.

Finally, you can also pipe data in and/or out of Nodezator, just like you can do in a Python script.



### Using Nodezator as a platform wherein to develop your own Python apps

Because a node editing interface can be regarded as just another kind of graphical user interface (GUI), you can also think of each graph as a GUI application. After all, most GUIs can be described as interfaces that have widgets holding data and triggering operations on such data. This is what node editors do as well. The main difference is that node editors also organize such widgets in boxes (nodes), organize those boxes in a graph, and allow such boxes and their inputs/outputs to be connected and reconnected as the user desires.

In fact, each node could also be regarded as a GUI app by itself, and the node editor is a larger GUI used to connect such small apps.

For instance, image editing with Python and the [pygame-ce](https://pyga.me) library is so simple and straightforward that I perform many of such tasks solely with Nodezator by creating graphs for each specific image editing tasks I have to perform. Of course, depending on the task, I still use image editing applications. The point is to use the appropriate tool for each kind of task. When I want to perform a series of operations on images and vary such operations and their parameters, creating a graph for that specific tasks is very rewarding and allow me control and precision over the final result as well as a lot of versatility by being able to use any operations I want and in whichever order I want.

In light of all this, each graph I create works just like a custom-made and highly customizable application for the task at hand. A versatile GUI.

Another practical implication of this notion of graphs as custom and flexible apps is that you could also share then online to help people performing similar tasks. For instance, I once shared a graph I created on the internet. The graph was used to create a 3D model, provide a visualization of a render of such model as a SVG image and also, optionally, to export such model to a 3D file format.

In other words, with just a single file I could provide a lot of functionality to people, that is,  defining, visualizing and exporting a 3D model. That's why a graph works fine as a GUI app.



### Using Nodezator as a no/low-code interface

You can use Nodezator as a no-code or low-code interface to allow non-programmers or programming beginners to perform tasks that otherwise you require expert software knowledge.

If you are working with tasks that can be modelled as a set of operations and data that travel the graph being transformed by such operations, then you don't need people with advanced computer/programming skills to perform such tasks. You can just write custom nodes and create graphs representing such tasks and all the non-programmers/beginner programmers have to do is to control the parameters and structure of the graph to perform such tasks.

Image editing, again, is a suitable example. You can simplify image editing as a series of operations performed on one or more images until the desired output is produced. This notion reduces considerably the quantity of elements one have to deal with and allows non-experts to do significant work by simply editing widgets and/or changing the graph structure in Nodezator (that is, instanciating/deleting nodes and connecting/disconnecting sockets).



## A word about parametric design/programming

Another thing to highlight regarding Nodezator usage is its ability to express parametric systems/data/behaviour. That is, the usage of parameters to precisely control a system or what it produces. This allows you to design/program things in a reproducible/non-destructive way. This is a notion that is diffused across all the different possible way to use Nodezator that we discussed before.



## A word about connecting multiple workflows

I mention many different kinds of workflows as isolated examples in this chapter, and many others are likely to be added to other chapters, if not already. Many of such workflows, despite being very convenient and effective to perform in a node-based interface, can be as easily or even more easily perform in other specialized GUI. For instance, image editing can be very comfortably performed in an image editing software, whether we are talking about an advanced/complex image editor in a desktop environment or a more simple yet powerful mobile app with many filters and their configurations that can be applied to an image.

If so, then what is the advantage of using a node editor? Well, the same advantage of using a programming language: extensibility and precision.

Let's use an example. Even when a programmer has highly expertise in image editing programming, whenever an image editing task needs to be performed, the programmer may not necessarily jump straight into programming a solution. The programmer might conclude that using an image editing software is more than enough for the task and just use it and perform the task right away. However, sometimes the programmer may conclude that more control/precision is needed, what that some operation/feature not offered by the image editor would be needed. In such cases, then the programmer will indeed rely on writing a custom script to deal with the task.

That's because in the script the programmer has much more control of the solution. But, there's even more: a programming environment is virtually limitless in that the programmer can import any libraries needed to deal with different aspects of the image. Perhaps the image editor doesn't have a feature to extract a frame from a video file, since it specializes in image editing. Perhaps, the image to be edited is actually a chart plotted from data rather than an image to begin with. In that case, rendering the plot with different settings may be more appropriate and straightforward to control the final appearance of the chart than trying to edit the chart after it is generated.

For all these scenarios explore above there are several libraries that could assist in the related tasks, and the programmer has access to all of them in the script.

Similarly, in a node-based environment like Nodezator, that just represents Python calls, the possibilities are innumerable. As long as the task at hand is suited to a node-based environment, the ability of Nodezator has to combine multiple workflows sets it apart from specialized solutions. Being just a different kind of Python environment, but a Python environment nonetheless, Nodezator is also limitless when it comes to connecting multiple workflows to bring to the table all the control, precision and features needed for your solution.

Nodezator is a truly multi-purpose generalist Python application. Not a specialized limited environment, but a flexible highly customizable node-based Python programming playground.



## What are Nodezator goals?

We already discussed so many facets of Nodezator and its usage. Now that we know what Nodezator is and how it is meant to be used, we can finally learn about the goals of the project. Learning about the goals not only provides more context into what Nodezator is meant to become in the future, but also more information about how its design must be kept to ensure the software stays healthy and maintainable and its development is also healthy and sustainable.

Because the goals are closely related to Nodezator's definition and design, they are also closely related to each other.

Nodezator goals are:

- remain as simple and lightweight as possible
- run smoothly in low-spec hardware
- grant freedom to users
- be easy to integrate with any existing Python system/app
- implement any excess complexity as plugins/addons
- have a pixel-perfect platform-agnostic interface
- be able to take advantage of high-spec hardware when available
- promote gamedev and related workflows without harming its generalist nature
- promote healthy moderately-paced development focused in simplicity and cleanliness of design

In the following subsections we'll discuss each of such goals in detail as well as the intrinsic relationship between them. We'll also present some of the measures taken and decisions made to help achieve such goals.



### Remain as simple and lightweight as possible

Nodezator must only feature the bare minimum amount of functionality required of a node editor. Of course, as a generalist multi-purpose language-based node editor, its requirements may be a bit more numerous than other specialized node editors. For instance, rather than more common native general widgets, it features widgets related to Python types, like several different kinds of entry widgets.

However, only the bare necessities must make into the app. Additionally, though, maybe a few convenience features may also be added to help in its usage. For instance, since it is useful to be able to visualize/preview many kinds of media/data, extra widgets with such capabilities were added as well, like widgets that can be used to preview the contents of paths to files depending on the file's type (image, audio, font, video and text, includign Python source code).

At version 1.4.5, for instance, the source code itself amounts to roughly 3 MB of Python code, with 10 more MB of data and media files (mostly fonts, which should be reduced in size in future versions to make the app even more simple and compact).

Naturally this contributes to very small launch times, but this is not our goal here. Regardless of the launch time, as long as the app is kept reasonably small, simple, and uses computer resources sparingly and reasonably, we can say this goal is being achieved.



### Run smoothly in low-spec hardware

This goals is a natural extension of the previous one. Since we aim to keep Nodezator simple and lightweight, it is only natural that it runs smoothly in low-spec hardware. However, more than regarding this as a natural consequence of the other goal, we want to enforce it as its own separate goal.

That is so because of the importance of this goal. Python per se is a very lightweight scripting/programming language which can run on most if not all hardware. Moreover, Python programming is useful in many different scales and scopes.

That is, Python programming is important to a plethora of different tasks/workflows, whether resource-intensive or not. Thus, it is only natural that Nodezator, that is just a visual representation of Python, must also run in low-spec hardware, so that more simple and less resource-demanding tasks can be achieved with it. In other words, for us it is as important that Nodezator can be used for heavy tasks like media editing/big data processing as it is that users can use Nodezator for more light tasks like text processing and small calculations.

At version 1.4.5, for instance, Nodezator usage at startup amounts to only about 260 MB of [RAM](https://en.wikipedia.org/wiki/Random-access_memory) used.

There's an even more important reason for this goal, though: education and innovation can sprout from any environment and environments with many limitations are very prone to innovation and development as well. We never know from which direction innovation and new developments/contributions will come, so it is vital that we do not exclude this kind of environment as well.

Nodezator itself was the result of many hardware limitations faced by me, its creator (Kennedy). Were not for such limitations, Nodezator would likely have been built on top of more complex and resource-demanding libs/frameworks and be subject to many overengineered design decisions.



### Grant freedom to users

We already explored many examples of the usefulness of node editors. Being a language-first node editor, a visual representation of the Python programming language, Nodezator has virtually 100% synergy with the Python ecosystem. So much so that as we already know, a Nodezator graph can be exported as the equivalent Python code effortlessly.

This is very important, for it means Nodezator users are never overly dependent on the app itself. No matter how much useful and handy node editors are, they are tools suitable for some specific problems and not so much for other kinds of problems. Because of that, the Nodezator app has the goal to grant freedom to users, so that they can easily transfer the code/graphs produced in it/for to other workflows.

This goal is pursued in the Nodezator project via 02 main aspects of the app:

- the user can export the graph to the equivalent Python code;
- the code to define nodes is as minimal as possible and devoid of overengineering.

The first aspect is very clear. If the user needs it graph functionality available in another Python environment, all the user has to do is export the graph and load the code in that Python environment.

The second aspect can be observed in how nodes are defined. Below we repeat the code block presented early so we can point out an extra, very often underrated feature of it:

```python
import math # standard lib import

def get_circle_area(radius:float=0.0):
    return math.pi * (radius ** 2)

main_callable = get_circle_area
```

This extra underrated and underappreciated feature is simplicity. Notice how straightforward and devoid of unneeded/obscure details and overengineering the code is. It mostly just describes the operation the node performs. That is, the `math` library is imported, than a function takes a radius and returns the square of that radius multiplied by `math.pi`. The only extra detail is the assignment of the `main_callable` variable, that Nodezator uses to grab a reference to the callable used to define the node.

The usual reaction to this code is to say "is the `main_callable` variable really needed? Couldn't you just parse the code to identify the function?". The answer is that this approach would be too complex and error prone for a lot of cases. In this particular case, where we only have a single function, it would indeed be simpler. But not all nodes rely on a single function to work. Even though we only pass the reference of a single function to define a node, sometimes that function may rely on other functions, like built-in functions, imported functions or functions define in the script. That's why the `main_callable` variable is needed, to avoid ambiguity. As the Zen of Python says, "Explicit is better than implicit."

Again, I have to repeat: the only extra element needed in this script is a single very brief line just to create a variable referencing the callable used to define the node. This is very underrated/underappreciated. Notice how the node definition is kept as pure as possible. No overengineering, no [infoxication](https://en.wikipedia.org/wiki/Information_overload).

Now ask yourself this: how nodes are defined in most if not all other node editing apps/environments? Does the node definition end up as clean and clear as that? I'd say most other node editors require the user to define custom classes by importing custom types to be subclassed and use in the composition of the custom class, adding a lot of information and foreign logic even to define a simple function like the one we just presented.

The node definitions in Nodezator, however, are almost 100% business logic. That is, they mostly just describe the operation the node performs.

This has 02 effects:

- it makes the much more easy to understand because there's no distractions/foreign elements polluting the logic;
- because it is mostly just business logic, it is much more easily to reuse the code outside Nodezator.

In the end, the node definition in Nodezator we used as an example is 99.99% just the Python function itself.

It is also possible to just reference an existing callable. For instance:

```python
from numpy import save

main_callable = save

third_party_import_text = 'from numpy import save'
```

The code above will result in this node:

![numpy save node](https://nodezator.com/images/numpy_save.png)

In this particular case we only required the definition of 02 extra variables. We didn't even need to worry about the business logic because we simply use a callable that already exists by importing it, aliasing it as the callable to be used and describing the text used in the import statement of this third-party library import. Again, even though in this case there's no visible business logic, the definition is still kept as simple as possible and clearly convey the source of the business logic we want to use, that is, the `numpy.save` callable.

I'd like to add that what I presented here doesn't mean I regard other node editors as inferior to Nodezator. They simply made different design decisions or have different purposes or work under different constraints/limitations, all of which are legitimate reasons to operate in different ways.

Nodezator, however, was created because I wanted a node editor that could work as generalist node-based Python environment and because I wanted to worry only about the business logic behind my problems when defining nodes, that is, just write my business logic's Python code and have the app figure out the other details for me. That's why Nodezator was created even though many other awesome Python node editors already existed back then.

So, getting back to our discussion regarding the goal of granting freedom to users, I'd like to conclude by stating that, in order to achieve such goal, we must strive to maintain and protect the 02 main measures we present here. That is, the ability to export the graphs as Python code and the ability to define nodes with as much simplicity as possible, by worrying almost 100% solely about defining or referencing the business logic.



### Be easy to integrate with any existing Python system/app

This goal clearly benefits a lot from the measures presented in the past goal of granting freedom to users, that is, the being able to export graphs to Python code and having simple node definitions that are mostly Python code representing business logic or a reference to such Python code (from imported callables).

It is a goal on its own though, because it presents its own challenges and requires the research, pursuit and employment of other measures.

In all fairness, "being easy to integrate with any existing Python system/app" is actually a pretty vague goal. I even doubt many Python developers can accurately list most let alone all existing environments where Python systems/apps can exist. Describing most/all possible ways to integrate systems/apps would be similarly difficult. This is why this goal is one for which new measures are always being considered and added to our "repertoire".

Integration is also subject to constraints/limitations from many factors like libraries/environments used and resources available.

Because of all that was discussed, we need to make this goal a bit more concrete, we want to achieve it or at least constantly progress towards it. To do so, we use an specific approach to the pursuit of such integration, in order to focus our efforts, making progress possible. We do so gradually and incrementally.

Additionally, we also pick a definition for integration, to help us identify and pursue it. For us, integration is any kind of meaningful interation between 02 systems/apps, regardless of whether it occurs in real time or not. So, for instance, if someone creates a file with one systems, and load this file into another systems, we consider this a form of integration, perhaps a more primitive one. If 02 systems respond to changes on each other and can cooperate in real time, this is also a form of integration, albeit a more complex/advanced one. Similarly advanced would be the possibility of one app running inside another (perhaps by sharing ownership of the main loop), at the same time or not.

However, we must also take into account the very definition of Nodezator. Since Nodezator works like a visual representation of Python, then, it is not far-fetched at all to actually consider a great number of integration possibilities, not unlike how it is for Python itself, which also has many integration possibilities available. For instance, Python is available on the web and many different OS platforms, as bindings to other apps and libraries, etc.

These notions work together, but at the same time they make integration too general. Almost any kind of interaction can be considered integration by this definition. Because of that, to complement this definition, the integration must also not hinder the other goals.

The concept of [orthogonality](https://en.wikipedia.org/wiki/Orthogonality_(programming)) in computer science also plays a role here, that is, the notion that different subsystems can coexist and change or operate without affecting each other. In much the same way, different integrations should not impact the other goals, the overall design of Nodezator, or each other.

In summary, any kind of possible interaction between Nodezator and another system is to be pursued if and only if it doesn't result in harm to the other elements of Nodezator, including its goals, design and other subsystems and integrations. Other goals we are still to discuss are also related to this one, like the one about implementing excess complexity as plugins/addons.



### Implement any excess complexity as plugins/addons

When it comes to either integrations or other changes/additions to Nodezator, we must make sure all those changes/additions do not make the software bloated and hinder its main purpose, which is to serve as a node-based environment for the Python programming language. Anything beyond that must be carefully analyzed to determine whether it really contributes to this purpose or whether it complements it indirectly.

If it contributes directly to such purpose, then we must naturally add it to Nodezator directly. If it only does so indirectly or by targeting specific niches/subtasks or other form of smaller scoped tasks/area, then, although it is something that is fine to coexist with other Nodezator elements, we must primarily consider it as something to implement within a plugin/addon system.

At the time of writing, with the current Nodezator version being 1.4.5, no such system exists yet, but it is something to be researched and implemented in the future in order to guarantee the achievement of this goal and maintain Nodezator's simplicity paired with the multiple possibilities offered by an addon/plugin system. It is simply a flexible way to offer additional functionality without compromising the simplicity of the main design.



### Have a pixel-perfect platform-agnostic interface

This goal is achieved in Nodezator by using a multimedia library to draw the graphical user interface instead of using a GUI-oriented library used to manage widgets implemented with native styles (widgets whose exact looks vary per platform).

In the specific case of Nodezator, at the current version 1.4.5, we use the Python bindings (the pygame-ce library) to the SDL multimedia/gamedev library ([homepage](https://www.libsdl.org/) | [wikipedia](https://en.wikipedia.org/wiki/Simple_DirectMedia_Layer)).

In fact, the usage of multimedia libraries is a measure so crucial to this goal that it could even be considered a goal itself. We didn't list it as a goal solely for the sake of brevity/redundancy. Nonetheless, no matter which shape Nodezator takes in the future and whether it replaces the graphics backend or not, we must invariably end up adopting a multimedia library.

Purposefully, this multimedia library chosen should always be one that could also be used to make games even though it is only being used for Nodezator's interface. The reason has to do with the close relationship Nodezator has with game development and related workflows. Such close ties to gamedev that Nodezator has are not solely for the sake of fun (although this alone would already be a legitimate reason), but also paves the way to a more successful future for all kinds of computer/programming workflows performed with Nodezator, regardless of whether they are related to gamedev or not. We'll properly explain and delve deeper into this in a [dedicated chapter](ch-power-gamedev-nodezator-role.md), though we'll very briefly revisit this notion in a future subsection, when discussing another goal that is also related to it.

For the sake of the goal we are discussing now, however (the goal to have a pixel-perfect platform-agnostic interface), we argue that the highly customized nature of games naturally force the multimedia libraries created to develop them to evolve into tools capable of producing such highly customizable interfaces.

Another advantage of using such multimedia/gamedev libraries is the higher precision of control that comes with low level access to services and hardware that is provided by such libraries. This also allows us to develop much richer custom widgets for Nodezator's specific purposes. Richness not only in terms of looks, but also regarding behaviour. Admitedly, GUI-oriented libraries also offer a lot of customization and precision of control, but overall, lower level access is the default/expected aspect in multimedia/gamedev libraries whereas GUI-oriented libraries favor the usage of pre-made general widgets rather than custom-made ones (and they are awesome for this kind of purpose).

Perhaps chief among the reasons for Nodezator to have a highly customizable interface is the fact that rather than editing data in more general formats, its users must edit data in the specific formats/types used by Python. That is, instead of editing only text and numbers, Nodezator users need widgets to edit more "specialized" types and values like complex numbers (`4+1j`, etc.) and `None`, for instance.

The vast majority of such multimedia game-oriented libs are also performance-oriented, which also benefits Nodezator, despite the fact that Nodezator's design favors cleanliness/simplicity/maintainability of design over performance. The role of performance in Nodezator's design will also be presented on another section, when discussing another goal that is even more related to it.

Up to this point we established that the adoption of multimedia/gamedev libraries for Nodezator's interface are an important measure to achieve our goal of a pixel-perfect platform-agnostic interface. Now we need to understand why the goal itself is important, that is, why such pixel-perfect platform-agnostic interface is desirable?

Simply put, a pixel-perfect platform-agnostic interface gives us precise control over the interface, which culminates in our ability to implement and use an automated GUI testing system effectively. For instance, if Nodezator used an interface based on GUI libraries that relied on OS-specific services and widgets to work, we would not be able to precisely control and test the interface directly, but would instead have to rely solely on manual testing, which is too error-prone and time-consuming.

An automated GUI testing system, in turn, is crucial to guarantee a safe, healthy and manageable development of the app, because it ensures that changes made to Nodezator and published to users do not destroy/harm existing features. It allows developers to be able to confidently endeavor to make more complex changes and implement more complex systems. It makes long-term development and implentation of high-scope features viable/sustainable and keeps the software maintainable.

Granted, like many technology decisions, it has trade-offs. By adopting a custom pixel-perfect platform-agnostic interface we naturally forgo the native feel and behaviour of GUI-oriented apps and end up having to implement a lot of behaviour ourselves. For instance, at its current version, 1.4.5, Nodezator's widges still lack many behaviours usually present in native widgets. However, with much effort and time since its creation, Nodezator already has the barely necessary widgets and associated behaviour to be operated with some proficiency. Despite that, we do still have much to implement.

The lack of a native feeling isn't that harmful in the case of node editors though. They don't suffer as much from this as other kinds of softwares do, since they usually implement many custom elements and can usually be promptly recognized at glance, due to the invariable presence of boxes containing widgets and the connections between them represented by lines or curves, often making usage of dark colors.

In summary, a pixel-perfect platform-agnostic interface supported by a multimedia/gamedev library allows us precise control over the behaviour and looks of our interface, which in turn allows us to effectively implement and use automated GUI testing to ensure maintainability of Nodezator. Such precise control over behaviour and looks also allow us to create widgets for users to edit types and values used in Python.



### Be able to take advantage of high-spec hardware when available

Although one of the first goals regards Nodezator's suitability for low-spec hardware, people using high-spec hardware should not be left out.

This is pretty self-explanatory goal. But since Nodezator is relatively new, not much has been explored, so we are still to begin properly pursuing this goal. It is probably something that can be explored via many different measures that should be taken as the app evolves and opportunities are perceived. For instance:

- new widgets or other features that can take advantage of hardware acceleration
- the ability to use higher framerates for the graphical interface



### Promote gamedev and related workflows without harming its generalist nature

Understanding this goal requires taking into account several notions/concepts, including the many benefits of being involed with game development and games. Because of that and also the importance of such goal for the future of the Nodezator project, we dedicated an entire chapter to it: [The power of gamedev/games with Python and Nodezator's role](ch-power-gamedev-nodezator-role.md).

In summary, the many benefits of being involved with game development and games and the multidisciplinary nature of game development means it enriches the environments that adopt and promote it. That is why we made it a goal of the Nodezator app to promote gamedev and related workflows, with the nonnegotiable condition that such involvement do not harm Nodezator's generalist nature.


### Promote healthy moderately-paced development focused in simplicity and cleanliness of design

Software development nowadays is plagued by freneticism. Deadlines are not guidelines to assess our performance and motivate us anymore. Instead they are shackles that menace the quality of our code. We rush our development tasks for no apparent purpose other than to pretend we are in control. And what are the reward? What do we gain by rushing our work? Just another task, just more work.

Naturally, in a commercial setting we invariably have to honor deadlines. After all, others depend on our work as well. But if the rush harms the quality of our work or leaves no room for rethinking our practices and updating our mindsets regarding problems and design, than the speed is a disservice.

In an open-source project like Nodezator, devoid of the urgency of commercial projects, plans and deadlines are means to an end. They act as a compass to help us reach our goals. We still strive to reach our deadlines, but also have no problems postponing them, or the plans/goals themselves when needed. There are 02 reasons for this.

First, we prioritize the quality, simplicity and cleanliness of our design, the maintainability of our code. Although commercial projects have good reasons to be dead set on meeting deadlines, there's no denying that the final quality of the deliveries may suffer greatly. An open-source project, on the other hand, does not need to worry about that. Of course, an open-source proejct still has patrons who donate to the project and a userbase that follows its development and requests new features and fixes, but, as long as we are transparent in our process, communicate often and use our flexibility in a reasonable way rather than abusing the patience of patrons/community/userbase, we can focus on the quality of the development process and adjustment our deadlines as required.

The second reason is that, as a relatively new and still small open-source project, we are still underfunded and understaffed. The work done on Nodezator is mostly underpaid volunteer work, mostly from me but also from other volunteer that contribute code and ideas from time to time. This lack of structure and budget makes it harder to keep planning and development up to speed in comparison to commercial projects that has paid workforce and budgets at their disposal.

As I always emphasize when speaking about this underfunded and understaffed state of the project, this is not a complaint. Working in open-source is an infinite source of fun and learning. However, to prevent issues like overburdening and burnout, we need to realize our limitations and plan accordingly. By doing that, we ensure a sustainable development process, providing a continuous steam of features and fixes for Nodezator.

That's why it is so important that we seek the goal of promoting a healthy moderately-paced development that focuses in the quality of our software's design, that is, its simplicity and cleanliness. Ultimately, this also contributes to its maintainability and indefinite long-term usage.

These are some concrete measures we take to put all of this into practice:

- development happens in short finite periods (2 to 3 months)
- development focus in a small set of features each time
- work to be done is submitted in advanced for approval by the community as a post in the discussions tab of the repo
- in the same post, updates are posted as the work progresses and/or adjustments are made to the work or deadlines

In conclusion, despite acknowledging our limitations, we don't use them as an excuse to be sloppy in our work. Instead, we use simple but effective measures to structure and plan our work accordingly, communicating with the community and keeping changes and improvements to our project constant. All of this in order to pursue our goal of promoting a healthy and moderately-paced development focused in simplicity and cleanliness of design.

