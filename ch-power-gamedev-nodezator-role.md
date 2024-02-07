
[← back to table of contents](README.md)

# The power of gamedev/games with Python and Nodezator's role

Nodezator has a close relationship with gamedev and games. This relationship is even manifested in some of its goals and related measures, like using gamedev/multimedia libraries as the base for its interface and the promotion of gamedev and gamedev-related workflows (as long as it doesn't harm Nodezator's generalist nature). In this chapter we'll explore gamedev and games, their synergy with the Python programming language and why Nodezator has such close relationship with them.



## Gamedev and games

According to a [wikipedia](https://en.wikipedia.org/wiki/Video_game_development)...

> Video game development (sometimes shortened to gamedev) is the process of creating a video game. It is a multidisciplinary practice, involving programming, design, art, audio, user interface, and writing. Each of those may be made up of more specialized skills; art includes 3D modeling of objects, character modeling, animation, visual effects, and so on. Development is supported by project management, production, and quality assurance. Teams can be many hundreds of people, a small group, or even a single person.

Gamedev is an activity that drives innovation and creativity: new systems, new features, new ways of approaching problems, new problems to solve, new challenges to be conceived, many limitations to overcome, new visuals to explore. The many aspects to consider are almost infinite and each of them represent an opportunity to learn and try new things. Additionally, it is fun and entertaining. Even a game developed by a single individual can be a source of fun, socialization and learning, when the players interact with the creator, share ideas or simply the excitement.

The games themselves, also motivate people. They evoke a mix of emotions not limited to fun (though fun is very prevalent). They can be used for entertainment, education and even to convey messages or promote critical thinking and social awareness.

The benefits of gaming are so evident that even systems that are not related to games began adopting features that are characteristic of games, giving rise to the concept of [gamification](https://en.wikipedia.org/wiki/Gamification).

Game development drives the evolution of software, hardware, graphics, programming languages and many aspects of computing.

The video games industry is massive and offers many job opportunities. The skill set needed to develop games and the experience acquired by developing them are valuable in the technology industry as well. According to Chris Bentzel from Boston Dynamics...

> Game developers are also [well-suited to robotics](https://www.inverse.com/innovation/boston-dynamics-chris-bentzel).



## Gamedev with Python

In a way, it is actually surprising that the leadership involved with Python development and management (the [Python Software Foundation](https://www.python.org/psf-landing/)) doesn't invest more in game-related projects. Granted, the stigma of being an interpreted language certainly plays a big role in people's perception of Python as a language fit for game development.

Other factors, like the fluctuations in the development frequency of Python gamedev libraries, certainly played a big role in the past as well. The pygame library, for instance, was apparently plagued by this problem for a long time. Nowadays, however, pygame has been updated often for quite sometime and even has a new community-driven stable fork called [pygame-ce](https://github.com/pygame-community/pygame-ce) with a community that works hard to keep the library well-maintained and improving with even more frequent updates.

Despite all such problems, in practice, we have a worldwide online community that is constantly making new games with Python, not only with the more famous pygame/pygame-ce libraries, but many other libraries/frameworks like [Pyglet](https://pyglet.org/), [Arcade](https://api.arcade.academy/en/latest/), [Pyxel](https://github.com/kitao/pyxel), [Panda3D](https://www.panda3d.org/) and [HARFANG®3D](https://www.harfang3d.com/). Most of the creations are small-scoped games or prototypes, but commercial games have also been made and sold in popular game distribution services like Steam, like [SwitchCars](https://store.steampowered.com/app/442210/Switchcars/) and [Super Potato Bruh](https://store.steampowered.com/app/951360/Super_Potato_Bruh/).

Naturally, if you want to use Python to make a game like [God of War](https://en.wikipedia.org/wiki/God_of_War_(2018_video_game)), you are setting yourself up for disappointment. However, a game like [Chrono Trigger](https://en.wikipedia.org/wiki/Chrono_Trigger) could be comfortably developed with Python. With pygame/pygame-ce in particular, I'd say one would be able to make SNES/GBA-style games with ease, and probably also very simple PS1-style 3D games with OpenGL. More advanced 3D games could also be made with other libraries/frameworks like HARFANG and Panda3D.

I'm almost 100% sure that a game like the PS1's Resident Evil(s), Dino Crisis and Chrono Cross could be made with Python. And yet, nobody seems to have made a serious attempt at doing so. You may ask: why should someone do that? The answer is simple: because it would be 100 times more easy with Python. I bet developers back then, when the first PS1 games were being made, would be overjoyed to have an easy language to work with like Python at their disposal.

Today we have Python and more powerful computers but we do not use such tools to the fullest. There's nothing wrong with pursuing more performant technologies for gamedev and projects with more advanced and intense graphics usage. The problem actually lies on the other side of the coin: the underutilization of languages/techs like Python that although not as performant are still performant enough and bring to the table elements that other more performant techs/langs do not: ease of use and maintenance and gentler syntax, just to name a few advantages.

A language like Python can be used to make deep complex immersive games of large scope with gorgeous graphics.

If we invested time, effort and money in such projects, we'd not only reap the general benefits of game development and games for the Python ecosystem (innovation, fun, motivation, education, etc.), but such benefits would be even greater in comparison to what other language ecosystems would reap in its place. In the case of Python, for gamedev and games with a programming language as the central tool, those benefits would exist in an environment that has a lot of synergy with them. The Python ecosystem is great because of the design and features of the language, but also because of the community behind it. The qualities of the Python ecosystem that would make its synergy with game development great are innumerable. That is, innovation, education, learning, sharing ideas, trying new things, and many more.

In fact, I firmly believe that the only reason hobbyists and indie developers keep using pygame and other Python libraries despite not much incentives from Python's leadership (the PSF) is the fact that is has so much synergy with gamedev.

Gamedev is intrinsically complex due to the innumerable elements that must be harmonized to create a game: art, animations, sound, controls and all the code that supports all this together. However, there's something I noticed whenever comparing complaints from developers using Python versus complaints from developers using other languages: Python complaints are often about performance whereas complaints from game developers using other languages are more often about the language itself, like how hard it is to use them or the lack of specific features.

I'm not qualified to comment on what the other languages lack. But the Python-related portion of my realization clearly indicates that people have been able to fully translate into code the desired behavior for their games. They were only dissatisfied by the expected performance. In many of such cases, however, problems in performance are actually caused by a lack of proficiency in the language rather than by Python's performance.

What happens is that it is so easy to code in Python that people can begin gamedev with relatively little knowledge and end up getting stuck when developing more complex features that require more knowledge. Those people would be having a much better time developing games with Python with they spent time and effort working on their Python skills. Knowledge of software design and game design are also important and, depending on the project, also essential.

All these aspects of gamedev with Python makes evident the need for a different and more effective approach. One that is centered on the language rather than merely using the language as another tool.



## Language-first gamedev

I don't know if there's a name for this kind of game development centered in a programming language, but I like to call it "language-first gamedev". I think "programming-first gamedev" would not be a suitable term, because a lot of gamedev already is about programming. But in language-first gamedev the systems are designed to take advantage of the language design and its strengths to achieve power, flexibility, versatility and maintainability, rather than sacrifice those for the sake of performance or new features/mechanics. It is a practice rooted in the specifics of the language design and features and also software design and game design.

In language-first gamedev using Python, instead of abusing the performance of a compiled language by writing poorly designed systems to achieve game design goals, we rely on properly designed interpreted code to take advantage of the ease of maintenance and sufficient performance of the interpreted language. Of course, language-first gamedev is a concept that applies equally to compiled languages as well, with each different language having its own advantages and drawbacks.

In the case of Python, specifically, some advantages that come to mind are:

- free and open-source
- simpler syntax
- rapid development
- much less friction than other languages
- code is easy to maintain
- availability of many libraries
- large and awesome community (quantity + quality)
- abundance of learning materials
- abundance of libraries

The list is not comprehensive, but it gives us a good idea of the advantages of gamedev with Python.

The disadvantage is that we can't use it to make graphics-intensive games. But that still leaves a lot of room for exploration! It is not that Python isn't fit for making games. It all depends on which game you want to make. And for Python, which games can be comfortably made and maintained with it is mostly uncharted territory.

Since a long time, it looks like surprisingly few languages have been spending time/effort/resources into gamedev. The C, C++ and C# languages are, of course, heavily used in gamedev, but it looks to me like they are used more like a tool rather than part of the process. This is something difficult to explain. Let's just say that people grew so accustomed to their usage that they became just a medium for making a game.

If such languages were used in a language-first approach like I described, their role would be more important in gamedev and innovations and other benefits of gamedev achieved with such languages would contribute to the improvement of such languages and their ecosystems. Instead, their intensive usage in gamedev seems to have no effect impact in their ecosystems, except for bragging about their performance. I'm actually under the impression that users of such languages spend more time highlighting the problems of working with them to achieve their game features/mechanics than rejoicing in the languages were used to provide a smooth game development experience. As I said before, it seems these languages are being abused due to their performance rather than being used properly to help design and manage the game systems.

To be fair, this is a problem in Python for gamedev as well, in that people often complain about trying to shape the code to implement their features, rather than understanding the language well enough to be able to properly design the systems to support needed features. So, in part, a lack of proficiency in software design and in the language used are strong factors that prevent language-first gamedev to flourish.

Other languages that have prominent roles in game development, that come to mind, are Javascript (for HTML5 games) and Lua. The ecosystem of the Rust language also seems to be pursuing gamedev more eagerly, considering projects like [Bevy](https://bevyengine.org/). An initiative like this one only highlights the importance of language-first gamedev for programming languages.

Of course, no one can determine which shape the future of language-first gamedev will take, but we can strongly influence that shape in the future. In the Python ecosystem, helped by the simplicity of Python and of the APIs of gamedev libs like pygame/pygame-ce, gamedev is pushed forward spontaneously by the passion of hobbyist/indie developers. Python is uniquely positioned to conquer a prominent spot when it comes to gamedev. Certainly, it cannot be employed for graphics-intensive games, but we can still conquer a great position when it comes to making gorgeous, deep, complex games, whether commercial or not. And benefit the Python ecosystems as a result. If we don't act on it, we risk loosing ground to other languages when it comes to language-first gamedev.

That is why, in the Nodezator project, it is our goal to promote gamedev and related workflows, as long as we don't harm its generalist nature. This way, Nodezator will greatly contribute to and benefit from language-first game development with Python.


