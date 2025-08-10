# Awesome-Vizonex
Unlike most other coding compilations that are under some form of coding language I wanted
users to be able to find my other libraries I maintain or contribute to without while
aiding in a user's laziness. 

So I wrote this down to make it easier to see what projects I contribute to as well as my goals 
or current priorities without turning it into a super journal. Feel free to contribute to these
projects alongside me if you wish or step in to review my code in libraries I contrubute to or 
maintain myself. The help will be needed especially in the coming months if my IRL Parttime Job starts 
becoming a hassle again.

It's worth noting that some projects may repeat themselves if the library fits both personailites and not just one.

## Contents

* [asyncio](#Asyncio) aio or asyncio related projects
* [python](#Python) Python related projects that aren't cython or asyncio related.
* [cython](#Cython-Libraries) Language uses or is cython related 
* [miscellaneous](#Miscellaneous) Other Projects 
* [contributing](#Contributing) Things I am Contributing to or am a co-author or maintainer of. If anything is note-worthy I will try to point it out.
* [wasteland](#Wasteland) Obsolete or dead projects that either I have no intentions on continuing or don't have motivation to maintain.

## Asyncio

Asynchronous code is what I live for. It was the first thing I even leanred to code with in python so it has some importance to my heart.
Asynchronous code over synchronous code can be better in a handful of situations including mitigations against socket related issues or problems, rendering guis or other user-interfaces without frames lagging and much more.

| Library | Summary | Ownership Status | Activity Staus | Activity Reason |
|---------|---------|------------------|----------------| --- |
| [winloop](https://github.com/Vizonex/winloop) | A Maintained Fork of uvloop made just for windows users who want faster asynchronous code with a unix-like personallity. With the goal of helping users who are life-locked to windows and can't use other operating systems supported by uvloop | Founder & Current Maintainer | Active On & Off | since library is extremely mature only need to come back every now and then if there's a bug or a new optimization is discovered (Which is pretty rare) |
| [cyares](https://github.com/Vizonex/cyares) | An Asynchronous DNS Resolver inspired by pycares built in Cython instead of cffi. It is meant to have more aggressive code to fight against common vulnerabilities | Owner |  Active | I am actively Pushing out new extensions or implementing ideas I wanted to be included in pycares or aiodns|
| [aiothreading](https://github.com/Vizonex/aiothreading) | A Library made for handling heavier payloads to prevent a single eventloop from being overwhelmed and making up for the shortcomings of projects like aiomultiprocess which seemed to be more inactivate | Shared in Joint ownership with x42005e1f originally it was myself | Active On & Off | Only need to come back in every now and then but I seem to be the one leading everything but glad to have support with the library |
| [aiocallback](https://github.com/Vizonex/aiocallback) | A simpler version of __aiosignal__ that is meant to be slightly lazier in some ways but also more beginner friendly and can be used to document callbacks and provides better function signatures thanks to `ParamSpec` it's only weakness is that aiosignal is faster to write callbacks with if documentation is not your concern | Owner | Inactive | I also contribute ideas to __aiosignal__ and I revived that library all by myself even, Some of their changes might make some of __aiocallback's__ features obsolete in some ways in the future. (Except freezing aiosiganl's signals which is a hassle) |
|



## Cython

Cython related projects meant to help smooth bottlenecks with some denser projects.


| Library | Summary | Ownership Status | Activity Staus | Activity Reason |
|---------|---------|------------------|----------------| --- |
| [winloop](https://github.com/Vizonex/winloop) | A Maintained Fork of uvloop made just for windows users who want faster asynchronous code with a unix-like personallity. With the goal of helping users who are life-locked to windows and can't use other operating systems supported by uvloop | Founder & Current Maintainer | Active On & Off | since library is extremely mature only need to come back every now and then if there's a bug or a new optimization is discovered (Which is pretty rare) |
| [cyares](https://github.com/Vizonex/cyares) | An Asynchronous DNS Resolver inspired by pycares built in Cython instead of cffi. It is meant to have more aggressive code to fight against common vulnerabilities | Owner |  Active | I am actively Pushing out new extensions or implementing ideas I wanted to be included in pycares or aiodns|


## Python
Simple plain python that doesn't have any attirbutes to other libraries explained above

| Library | Summary | Ownership Status | Activity Staus | Activity Reason | 
|---------|---------|------------------|----------------| --- |
[deprecated-params](https://github.com/Vizonex/deprecated-params) | Although I am not the first to try and implement this the goal was something that can be simply installed into any developer's library or silently gotten rid of when not needed anymore. It provides simillar functionallity to python's `warnings.deprecated` wrapper with the simple goal of warning other developers that a function's signature is going to change eventually | Owner | Active On & Off | I use this with my own libraries examples included aiothreading, aiocallback & cyares (recently) |
| [pyllparse](https://github.com/Vizonex/pyllparse) | Python Parody of nodejs llparse simillar concept to pyppeteer & puppeteer but it allows for python devs to write and Generate Low Level C Parsers | Owner | Active On & Off | It's mature it just needed some changes so that it could be user friendly instead for myself only and some class objects needed good stress-testing.

## Contributions 
TODO
