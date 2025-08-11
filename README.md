# Awesome-Vizonex
Unlike most other coding compilations that are under some form of coding language I wanted
users to be able to find my other libraries I maintain or contribute to without while
aiding in a user's laziness. 

So I wrote this down to make it easier to see what projects I contribute to as well as my goals 
or current priorities without turning it into a super journal. Feel free to contribute to these
projects alongside me if you wish or step in to review my code in libraries I contrubute to or 
maintain myself. The help will be needed especially in the coming months if my IRL Parttime Job starts 
becoming a hassle again.

It's worth noting that some projects may repeat themselves if the library fits multiple personailites and not just one.

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
This is a curated list of libraries that I wish to help or keep maintaing in the years to come some of these libraries are used by thousands upon thousands of users and they need help especially different opinions and input and people to be there to solve a problem when a vulnerability happens or an unitended bug needs patching. This could also be a group or orginization Example: [aio-libs](https://github.com/aio-libs) which happens to be most of these. 

If you can't find anything in the Notable Contributions section, it's because either I didn't feel like adding it or it wasn't super important to share.

| Library | Summary | Notable Contributions | Currently trying to do |
|---------|---------|-----------------------|--------------------|
| [multidict](https://github.com/aio-libs/multidict) | It is intended for http-headers with entries that can appear or repeat themselves multiple times rather than using a dictionary with many lists for values this cuts out the need for doing so and has some future potential for sorting data in other ways rather than  parameters or what it's currently used for | I'm implementing a C-API Capsule to try and optimize aiohttp's http-parser and help with some bottle-necks with the http-writer in Cython it should appear in 6.7.0 if were lucky. Currently I generate the Cython Parts with a python script or clang but if the maintainers would like to manually add it in I'm ok with that too. | Fix a memory leak with `md_clear` it should be noted that multidict used to be a pairlist but moved to using hashtables as of recently so bugs are likely since this change is not extactly completely mature using it yourself means we can catch these bugs sooner than later, code seems to be based off CPython's Dictionary Object. |
[propcache](https://github.com/aio-libs/propcache) | Originally a property class called __reify__ it is made for writing cached or immutable properties in python, there's 2 different cached properties that it supports `under_cached_property` for enabling slots by moving cached objects to a dictionary object called `_cache` if the user remebers to add it to the class object. the other is a modified version of `cached_property` that is just highly optimized from functools so no need to explain it further | I added some optimized portions of code by removing rich object comparisions in trade for checking if the slot is `NULL` thus getting rid of global sentient objects making propcache fully threadsafe and faster all-together | I'm attempting to make it so that users can use it in cython via __cimport__ since it's possible to wrap custom member descriptors in cython from there it could lead to __yarl__ getting a Optimized `URL` object in cython and I'm willing to write all of it |
| [pycares](https://github.com/saghul/pycares) | cffi wrapper around __c-ares__. __c-ares__ is also maintained by some devs of __curl__ from what I've heard so it's definately extemely optimized, I also use the same thing but for __cyares__ the reason I help over with pycares is because I wanted some features from my own library to be included over here if developers preferred __cffi__ over __cython__ which is completely understandable. | I provided some new functions for socket related callbacks that ignore either a read or write file descriptor to make it easier to maintain aiodns. | Currently I am working on giving pycares some docstrings so that the back-end can be as clean as __aiodns__ |
[aiodns](https://github.com/aio-libs/aiodns) | A Frontend wrapper around __pycares__ for asynchronous resolving dns queries and is a lot better for these in large quantities over what the python standard library is capable of | It's no surprise that I've been over here, my first contribution was getting __winloop__ in here ages ago from there I provide ideas to make aiodns better including refactoring the library by cleaning up uneeded callbacks or data, etc... | Trying to provide typehints in a simillar manner that I gave cyares's aio extension recently so that it can be eaiser for users to figure out what can go into the `__init__` function. Guessing games are hard especially for noobs so getting rid of that pain was a must on my todo list. | 
[aiohttp](https://github.com/aio-libs/aiohttp) | Should be zero surprises to anybody that I am over here many of the things I contribute to all tie back to this library. Aiohttp is meant to provide asynchronous http requests to make things a bit more lax over using something like `requests` it can also be used to host http servers I've even thought about making an extension that would give a fastapi like frontend to aiohttp. From Crazy Webscrapers to users needing to access apis to needing to host servers aiohttp provides all of that functionallity under the sun. | Typehinting `TraceConfig` so that users (especially noobs) would be able to figure out what can be passed a bit easier when tying in a `ClientSession` since subclassing `ClientSession` objects is discouraged. | Trying To Optimize The C portions of Aiohttp in Cython to improve performance of everything all tying back to multidict & I have thought about hunting down low level C Libraries for dealing with the http2 protocol so that aiohttp can finally have http2 support which means webscrapers benefit from obfuscation and server hosters can benefit from better performance. It's a win/win

