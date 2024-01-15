
# Software Design Document for Nodezator

Author: Kennedy Richard S. Guerra ([kennedyrichard.com](https://kennedyrichard.com) | [@KennedyRichard](https://github.com/KennedyRichard))


## Overview

This [software design document](https://en.wikipedia.org/wiki/Software_design_description) was created to help manage the development of Nodezator ([GitHub repo](https://github.com/IndiePython/nodezator) | [website](https://nodezator.com)) for both its maintainer (me, Kennedy R. S. Guerra) and other developers who desire to contribute code to the project. It aims to do that by offering detailed information on Nodezator's design, including its definition, goals, current and planned features/behaviour and also brief analyses of alternative software that offer further insight into design decisions made for Nodezator.


## Stakeholders

Nodezator is a powerful and versatile software in the Python ecosystem of tools. Its generalist nature gives it a wide range of application for countless different programming tasks/areas/workflows. Being free of charge and dedicated to the public domain grants unlimited access to the software and its source to anyone. It can not only be used by itself, but also be integrated with virtually any Python system.

Some key features of Nodezator are completely absent in alternative software, like the ability to export the graph into Python code. Other key features are very rare in other similar software like the ability to create nodes from function definitions and the ability to pass around not only data, but nodes as well (that is, the functions used to define the nodes).

All those facts make Nodezator's importance evident. This is why this design document is important as a tool to help drive Nodezator's development, keeping the software healthy and maintainable. Nodezator's unique role and wide application in the Python ecosystem makes it so most if not all Python developers benefit from its success.


## Context

In order to guarantee the success of this document and of Nodezator's development, it is necessary to understand the context of its development. This includes knowing both what the project context is and what it is not.

Nodezator is not a commercial project led by industry professionals using state-of-the-art processes and with access to enough resources and budget. It was created by me, (Kennedy Richard S. Guerra, born in 1990), a self-taught software developer whose formal education consists of a degree in Business Administration (although I do not work on the field).

Despite not having a formal education and training in software development/engineering, I have learned programming through diligent study of technical books and thousands of hours of practice divided across many software projects. Such projects range from simple CLI scripts to full-fledged desktop GUI applications.

With that in mind, since I'm a single software developer and Nodezator is a relatively large application, it is crucial that Nodezator design planning and development are devoid of complex management structures/practices. Instead, we must rely in simple and manageable practices that ensure the sustainability and progress of Nodezator's development. We aim to reflect this is in this design document. It is meant to be a very lean document, devoid of unneeded details but also rich in details for things that are relevant.

Most notably, it aims to describe existing behaviours/features in detail so that they can be used as the basis for tests (specially automated GUI tests). Automated tests are one of the most important and reliable tools to guarantee the sustainability of the project. This is so simply because they attest the quality and reliability of the application and ensure such quality and reliability are kept in new releases.

Tests are also important for development work and collaboration, since they ensure both the maintainer and other contributors can work with the certainty that the changes introduced will not break existing work. Without tests, changes introduced are a continous source of worry and speculation as to whether they broke any previous existing work.

Perhaps the only tool more important than tests is this design document itself, since in a sense it is in itself a test that is used by developers to ensure the automated tests they write/update/remove are relevant or not to the design. Tests test code, design tests tests.

Another notable aspect of this design document is the absence of specific dates in the timeline for features/changes/improvements. This is so because, like most small personal open-source projects, we are still underfunded and understaffed. In other words, we are not a well-managed organization with paid staff. Thus, pretending we have the resources required to present and follow strict deadlines would only amount to unnecessary bureaucracy and lead to frustration.

Instead, we prefer to just list the items to be pursued and strive to deliver changes and improvements regularly or at least semi-regularly, showing competence through our achievements over time instead of relying on displaying deadlines solely for the amusement of our users/audience.

Finally, this document may also prove useful to other developers that want to learn one possible way of making a generalist multi-purpose Python node editor. It may also be useful if we or other developers ever want to implement Nodezator in other GUI framework/library.

In conclusion, in order to be successful, this design document must effectively serve as a basis for Nodezator's development.



## Table of contents

1. [Nodezator definition, usage and goals](ch-nodezator-definition-usage-goals.md)
1. [How Nodezator was designed]()
1. [Current behaviour and features]()
1. [Timeline and planned features]()
1. [Alternatives to Nodezator]()
