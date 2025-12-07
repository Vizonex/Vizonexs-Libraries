# Vizonex's Libraries
Unlike most other coding compilations that are under some form of coding language I wanted
users to be able to find my other libraries I maintain or contribute to while
aiding with a user's laziness. I couldn't pin all of them so I decided to write a repo for it 
even if that embarrasses me later down the line. Winloop seems to be getting all the attention and love these days
but I didn't want to forcibly promote my other projects from over there. Those who seek to see what else I do should be 
allowed to easily begin to find it which is why this repo is now being pinned as first on my profile page.

So I wrote this down to make it easier to see what projects I contribute to as well as my goals 
or current priorities without turning it into a super journal. Feel free to contribute to these
projects alongside me if you wish or step in to review my code in libraries I contrubute to or 
maintain myself. The help will be needed especially in the coming months if my IRL Parttime Job starts 
becoming a hassle again.

It's worth noting that some projects may repeat themselves if the library fits multiple personailites and not just one.

## Contents

* [Todos](#Todos) My Current Agenda From Urgent to least urgent or am procrastinating.

* [asyncio](#Asyncio) aio or asyncio related projects
* [python](#Python) Python related projects that aren't cython or asyncio related.
* [cython](#Cython-Libraries) Language uses or is cython related 
* [miscellaneous](#Miscellaneous) Other Projects 
* [contributing](#Contributing) Things I am Contributing to or am a co-author or maintainer of. If anything is note-worthy I will try to point it out.
* [wasteland](#Wasteland) Obsolete or dead projects that either I have no intentions on continuing or don't have motivation to maintain.


## Todos

Todo list is summarized as my agenda or things required to get from A - B. These are also my personal goals.

Urgency levels are as follows

| Level | Summary |
|-------|---------|
| 0 - 2 | Not in the right mood to implement bug fix or procrastinating due to no motivation or it's burn-out or motivation has run dry | 
| 3 - 4 | I'm in an ok mood to do it but it's not something I'm willing to work on right away unless people urgently need my help and can actually show up |
| 5 - 6 | Willing to revisit several times a week if things can get moving along or enough people can guide me through it all | 
| 7 - 8 | Somewhat desperate and might be revisiting once a day | 
| 9 - 10 | I'm on my knees and am desperately trying to finish or am constantly brute-forcing to have it done | 


 
| Title | Summary | Issue numbers OR PRs |  Urgency Level (0-10)  | Reason |  Requires  |
|---------|--------|----------------------| ---------------------|-----|------------|
| Multidict C-API Capsule | Speeds up aiohttp by a shitton (35% performance increase) and allows users to utilize it in Cython and C | https://github.com/aio-libs/multidict/pull/1190 & https://github.com/aio-libs/aiohttp/pull/11320 | 9.5 | It will allow for mass connections and writing data in very little time and will reduce a lot of python's lag and clunkiness | Reviewing and responsiveness mainly the work is done just needs those final touches and the cherry on top |
| aiohttp with http/2 support | Http/2 support for aiohttp (Benefits include bot detection evasion, mass connections to server increasing, hosting an http/2 website (Who doesn't love that I've never had one before but I would certainly love having one programmed :))  I am constantly implementing my own libraries like llh2 which I hope aiohttp accepts as it's main resource for frame parsing in the future)| | 4 | It's mainly the pure python portions that leave a slightly bitter taste in my mouth which is why I am slightly less motivated than I am about Multidict C-API | There will need to be an implementation of upgrading to http2 and a system that swaps the http-parser adn http-writer on upgrading I have an implementation that ignores h2 and just uses it's dependencies but the maintainers seem to have a different pov than my own on how it should be done. I like my implementation but it seems others have different ideas. | |
| cimport propcache as a cython library  | Allows for caching properties in Cython but also will help me establish a new library that will allow users to write a depcreated-properties library for python & cython without needing multiple wrappers chained together | https://github.com/aio-libs/propcache/pull/130 |  7 | Slightly motivated because deprecated-params was inspirational and did me wonders | Code-Coverage needs assistance unless someone that can merge it says otherwise there's a tiny possibility it may get rejected for the same reason that frozenlist didn't get accepted (which was ABI Related) If this is the case This will be annoying but I may have to copy and paste that code in deprecated-properties for it to have a cython portion and a pure-python protion :/ putting links to the original source does not sound fun to me. Even though I always do so so that I'm not being a cheapskate or a sucker |  |
| propcache as CPython Library | The second idea (Workaround idea) involves making propcache `_helpers_c` module into a C Library which would allow us to get rid of some reference bugs allowing us to stop playing around with cython references being generated and allow more control over the code. The only downside to all of it is maitenence and change of workflow. | | 6 | Motivated into doing so as long as I'm not wasting precious amounts of time on making it work. |

## Asyncio

Asynchronous code is what I live for. It was the first thing I even leanred to code with in python so it has some importance to my heart.
Asynchronous code over synchronous code can be better in a handful of situations including mitigations against socket related issues or problems, rendering guis or other user-interfaces without frames lagging and much more.

| Library | Summary | Ownership Status | Activity Staus | Activity Reason |
|---------|---------|------------------|----------------| --- |
| [winloop](https://github.com/Vizonex/winloop) | A Maintained Fork of uvloop made just for windows users who want faster asynchronous code with a unix-like personallity. With the goal of helping users who are life-locked to windows and can't use other operating systems supported by uvloop | Founder & Current Maintainer | Active On & Off | since library is extremely mature only need to come back every now and then if there's a bug or a new optimization is discovered (Which is pretty rare) |
| [cyares](https://github.com/Vizonex/cyares) | An Asynchronous DNS Resolver inspired by pycares built in Cython instead of cffi. It is meant to have more aggressive code to fight against common vulnerabilities | Owner |  Active | I am actively Pushing out new extensions or implementing ideas I wanted to be included in pycares or aiodns|
| [aiothreading](https://github.com/Vizonex/aiothreading) | A Library made for handling heavier payloads to prevent a single eventloop from being overwhelmed and making up for the shortcomings of projects like aiomultiprocess which seemed to be more inactivate | Shared in Joint ownership with x42005e1f originally it was myself | Active On & Off | Only need to come back in every now and then but I seem to be the one leading everything but glad to have support with the library |
| [aiocallback](https://github.com/Vizonex/aiocallback) | A simpler version of __aiosignal__ that is meant to be slightly lazier in some ways but also more beginner friendly and can be used to document callbacks and provides better function signatures thanks to `ParamSpec` it's only weakness is that aiosignal is faster to write callbacks with if documentation is not your concern | Owner | Inactive | I also contribute ideas to __aiosignal__ and I revived that library all by myself even, Some of their changes might make some of __aiocallback's__ features obsolete in some ways in the future. Actually there's a bug with pyright at the moment so 1.8 might be new bug fixes :)
| [aiohttp-tor](https://github.com/Vixonex/aiohttp-tor) | An aiohttp extension for tor and for client requests to tor hidden services as well as hosting them, my motive was due to the uk govenment and some of it's more recent attacks against user-privacy. | Owner | Active and will likely release within a few days on pypi | On & Off due to having a real parttime job |
| [anyio-typer](https://github.com/Vizonex/AnyioTyper) | Ever wanted to combine 2 good libraries together and make easy to use commandlines with both? It supports uvloop, winloop, asyncio & trio. Enjoy :) | Owner | On & Off due to having a real parttime job, I don't really have much need to maintain this often due to anyio not changing all that much |

## Cython

Cython related projects meant to help smooth bottlenecks with some denser projects.


| Library | Summary | Ownership Status | Activity Staus | Activity Reason |
|---------|---------|------------------|----------------| --- |
| [winloop](https://github.com/Vizonex/winloop) | A Maintained Fork of uvloop made just for windows users who want faster asynchronous code with a unix-like personallity. With the goal of helping users who are life-locked to windows and can't use other operating systems supported by uvloop | Founder & Current Maintainer | Active On & Off | since library is extremely mature only need to come back every now and then if there's a bug or a new optimization is discovered (Which is pretty rare) |
| [cyares](https://github.com/Vizonex/cyares) | An Asynchronous DNS Resolver inspired by pycares built in Cython instead of cffi. It is meant to have more aggressive code to fight against common vulnerabilities | Owner | Active | I am actively Pushing out new extensions or implementing ideas I wanted to be included in pycares or aiodns|
| [pyduktape3](https://github.com/Vizonex/pyduktape3) | Another duktape cython library becuase the other 2 versions are unmaintained | Owner | Planned | Wanted to improve and optimize the 2 older versions and make an asyncio adaptatation with anyio |

## Python
Simple plain python that doesn't have any attirbutes to other libraries explained above

| Library | Summary | Ownership Status | Activity Staus | Activity Reason | 
|---------|---------|------------------|----------------| --- |
[deprecated-params](https://github.com/Vizonex/deprecated-params) | Although I am not the first to try and implement this the goal was something that can be simply installed into any developer's library or silently gotten rid of when not needed anymore. It provides simillar functionallity to python's `warnings.deprecated` wrapper with the simple goal of warning other developers that a function's signature is going to change eventually | Owner | Active On & Off | I use this with my own libraries examples included aiothreading, aiocallback & cyares (recently) |
| [pyllparse](https://github.com/Vizonex/pyllparse) | Python Parody of nodejs llparse simillar concept to pyppeteer & puppeteer but it allows for python devs to write and Generate Low Level C Parsers | Owner | Active On & Off | It's mature it just needed some changes so that it could be user friendly instead of for myself only and some class objects needed good stress-testing. I still am finding new things to change since my earlydays of working with this project so just a warning that it's not a perfect 1:1 replica of the typescript version and I might be tempted to do a rewrite of the entire project if things get real bad.


## Contributions 
This is a curated list of libraries that I wish to help or keep maintaing in the years to come some of these libraries are used by thousands upon thousands of users and they need help especially different opinions and input and people to be there to solve a problem when a vulnerability happens or an unitended bug needs patching. This could also be a group or orginization Example: [aio-libs](https://github.com/aio-libs) which happens to be most of these. 

If you can't find anything in the Notable Contributions section, it's because either I didn't feel like adding it or it wasn't super important to share.

| Library | Summary | Notable Contributions | Currently trying to do |
|---------|---------|-----------------------|--------------------|
| [multidict](https://github.com/aio-libs/multidict) | It is intended for http-headers with entries that can appear or repeat themselves multiple times rather than using a dictionary with many lists for values this cuts out the need for doing so and has some future potential for sorting data in other ways rather than  parameters or what it's currently used for | Fixing Memory Leak with `MultiDict` when values are cleared a bug in 6.6.3 made it possible to leak memory if there were no values inplace but memory was allocated for more items | C-API But Motivation has slowed down due to the other maintainer's inactivity. If C-API Does come out the Cython parts of Aiohttp will speed up by 40% |
[propcache](https://github.com/aio-libs/propcache) | Originally a property class called __reify__ it is made for writing cached or immutable properties in python, there's 2 different cached properties that it supports `under_cached_property` for enabling slots by moving cached objects to a dictionary object called `_cache` if the user remebers to add it to the class object. the other is a modified version of `cached_property` that is just highly optimized from functools so no need to explain it further | I added some optimized portions of code by removing rich object comparisions in trade for checking if the slot is `NULL` thus getting rid of global sentient objects making propcache fully threadsafe and faster all-together | I'm attempting to make it so that users can use it in cython via __cimport__ since it's possible to wrap custom member descriptors in cython from there it could lead to __yarl__ getting a Optimized `URL` object in cython and I'm willing to write all of it |
| [pycares](https://github.com/saghul/pycares) | cffi wrapper around __c-ares__. __c-ares__ is also maintained by some devs of __curl__ from what I've heard so it's definately extemely optimized, I also use the same thing but for __cyares__ the reason I help over with pycares is because I wanted some features from my own library to be included over here if developers preferred __cffi__ over __cython__ which is completely understandable. | I provided some new functions for socket related callbacks that ignore either a read or write file descriptor to make it easier to maintain aiodns. | Currently I am working on giving pycares some docstrings so that the back-end can be as clean as __aiodns__ |
[aiodns](https://github.com/aio-libs/aiodns) | A Frontend wrapper around __pycares__ for asynchronous resolving dns queries and is a lot better for these in large quantities over what the python standard library is capable of | It's no surprise that I've been over here, my first contribution was getting __winloop__ in here ages ago from there I provide ideas to make aiodns better including refactoring the library by cleaning up uneeded callbacks or data, etc... | Trying to provide typehints in a simillar manner that I gave cyares's aio extension recently so that it can be eaiser for users to figure out what can go into the `__init__` function. Guessing games are hard especially for noobs so getting rid of that pain was a must on my todo list. | 
[aiohttp](https://github.com/aio-libs/aiohttp) | Should be zero surprises to anybody that I am over here many of the things I contribute to all tie back to this library. Aiohttp is meant to provide asynchronous http requests to make things a bit more lax over using something like `requests` it can also be used to host http servers I've even thought about making an extension that would give a fastapi like frontend to aiohttp. From Crazy Webscrapers to users needing to access apis to needing to host servers aiohttp provides all of that functionallity under the sun. | Typehinting `TraceConfig` so that users (especially noobs) would be able to figure out what can be passed a bit easier when tying in a `ClientSession` since subclassing `ClientSession` objects is discouraged. | Trying To Optimize The C portions of Aiohttp in Cython to improve performance of everything all tying back to multidict & I have thought about hunting down low level C Libraries for dealing with the http2 protocol so that aiohttp can finally have http2 support which means webscrapers benefit from obfuscation and server hosters can benefit from better performance. It's a win/win (Except freezing aiosiganl's signals which is a hassle) |
| [aiostem](https://github.com/morian/aiostem) | asynchronous version of the popular stem lirbary developed by the tor-project. It uses pydantic to help with the protocols.  | Contributor | Suggested keeping 3.10 around since 3.9 is about to hit eol and people still use 3.10 |  On & Off Due to IRL Job now in Full swing again which means contributions may slow down | 
| [msgspec](https://github.com/jchrist/msgspec) | serlization dataclass library that is faster than pydantic because it's written in C | Currently haven't contributed before but I have tried mergeing sqlalchemy to it and it didn't work so I am writing a new library that is inspired by what SQLModel, SqlAlchemy, Peewee can already do but hopefully at greater speeds (Because I'll be writing it in C because Cython Can't do metaclasses wrapped around `__new__`) | C-API Capsule so I can get started writing msgspec+sqlite orm library it will include specialized Row Serlization and `select`, `update`, `inset`, `delete` operators just like sqlalchemy has with msgspec fields subclassed to provide instrumentatation simillar to it. SEE: https://github.com/jcrist/msgspec/pull/961 for ongoing developments| 
