# kcc
a crash course in k
© 2004-2019 me@kel.as
estimated reading time 15yrs

## Genesis
In the beginning was the word, and only then there was computer code, and this is why there are some basic truths you need to know before we can proceed.

### who is k

There is a reason behind everything. The reason behind k is a computer scientist by the name Arthur Whitney. He is the principal designer of a computer language called `k`, and he is an iconic figure in an elite, tight-knit global community of some of the sharpest  and most sophisticated programmers and data scientists employed by some of the most influential institutions on the planet. Since early 90's, he provides them with ever more powerful revisions of one single product he has been working on his entire life, a unique integrated platform to build very efficient software that transforms large amounts of data into large amounts of money.

As you would expect, this is a fairly lucrative job market, and its participants who made careers writing in `k` appreciate Arthur’s magnum opus at least as much as they appreciate the man himself, but we believe there are separate reasons for that.

### why is k

There is a very high probability that you have heard the legend of Arthur Whitney and his language.  A *lot* of people did. What is much less likely is that you have ever met someone who told you he or she is a professional k programmer. This happens not just because k programmers are rare, but also because in their line of work it is often stated in their contracts that they simply cannot talk about certain things that give their employer a decisive competitive advantage. An this is why we all have /heard/ about k, but mostly /hear/ about how much Java sucks.

But jokes aside. Implementations of similar systems in languages like C++ or Java usually involve thousands of lines of code written by large teams, built on top of complex library stacks and even more complex infrastructure. The truth that these guys are not allowed to tell you, but always tell you anyway because they hate their jobs, it that their projects are desperately over budget, totally past deadline, and were designed for a version of reality that simply no longer exists.

In comparison, a k solution is typically a few factors of magnitude less code, implemented by a small and agile team or a single individual, rarely requires external dependencies and always ships on time. 

At first it could be hard to understand how this can even be, but lets compare the effort of keeping 100 lines of code up to date with reality and free of bugs, compared to 10,000 lines of code that do the same thing. No, it is not *100 times* easier. It is *10,000 times* easier. And if you think we are exaggerating, then think again and try prove us wrong, and this will be a start of a beautiful friendship.

### what is k

`k` is a remarkable piece of software that has many faces. For now, lets consider it to be an interpreter of what at first appears to be a suspiciously minimalistic computer language. A language that is immensely powerful.

The source of this power stems the fact that k was designed from ground up primarily as a *tool of thought*. The vocabulary, syntax and the choice of abstractions offered by the language affect you intellect in such a way that makes you think about problems in a very focused, clear and uncluttered way that quickly takes you to efficient and elegant solutions. And the reason why thinking in terms of this language is so effective is absolutely nothing supernatural. Is captured in a proverb that predates history and is known to all cultures: brevity is a soul of wit.

Indeed, k programs tend to be very *concise*, the syntax of the language is very *terse*, and k programmers have no idea what you mean when you say “boilerplate code”. Unlike in most software development workflows, a k programmer spends most of his time thinking about the problem rather than typing stuff into the terminal and browsing the source code tree. In humans, such mechanical activities are known to interfere with abstract thinking and greatly impair their focus — and k minimizes these losses for you.

All of k programming takes place in *REPL*, the concept which requires little introduction these days, but is actually considerably older an invention than many today’s software developers seem to think. It has been around for at least 50 years, and is known as /dialogue approach/, a natural and fluent conversation between a human and machine as a series of questions and answers. And in k, this conversation happens to be immensely more efficient than in any other modern REPL-driven system you may be familiar with, because it requires very few words to convey the question and very little time to receive the answer. This is the essence of *the way of k*, an experience that all k programmers consider immensely aesthetically and intellectually satisfying. This is why people who write software in k *love their jobs*, and this has nothing to do with their paychecks.

### speed of k

In addition to being an excellent tool of human thought, k is also an astonishingly /efficient/ computer language. The entire system, a tiny binary executable only 100 kilobytes in size without a single external dependency that fits comfortably in the cache of a commodity CPU, implements a selection of fundamental algorithms, data structures, techniques and computational primitives that withstood the test of many decades of production use in some of the world's most demanding data processing environments. The inner components of the system are polished to fit together and complement each other to deliver performance which many outsiders find very difficult to believe at first. It is also not uncommon for k newcomers to experience total shock when they first realize what kind of power they can wield with just a few precise keystrokes.

### cost of k

This is a tricky one. If you want to buy it, and you have to ask the price — don’t bother, because you can't afford it. But if you know *how* to ask, you will get it for free and for life. And that is the only hint you get from us.

## Exodus
This crash course is not looking to make you an expert k programmer, because that, as with any other form of art, takes years. Allegedly, it is possible to teach oneself Java in 24 hours, but we are not qualified to talk about that. Instead, we are going to talk about fundamental aspects of *thinking in k*, and the curve is going to be steep — but we value your time, so we promise it will be fast and violent. Since the only known way of learning how to program in k is to write programs in k, you will need a live k environment. Fortunately, as all things k, this requires virtually no effort.

### getting k

We will use a `trial` version of k, which comes with a reasonable limit of 1 gigabyte of workspace per k process. This limit is for your own protection, so that you don’t accidentally convert too much data into too much money too early, because, as any k programmer will tell you, with great power comes great responsibility.

The k interpreter is currently available for `Linux` and `macOS` on `x86_64` architecture. If you are on Solaris, OpenBSD or z/OS — hang tight, good things come to those who wait. The same applies for `ARM64` architecture, but if you are on Windows, well, lets not cry over spilled Guinness.

Without further ado, go to https://anaconda.org/ and follow the instructions. Anaconda shell integration option is highly recommended. Once you install Anaconda, install the package called  `shakti`, which is nothing else but `k` in disguise:

`kelas@failbowl ~ $ conda install -c shaktidb shakti`

As with all things k, the development of k language itself is happening at terrifying pace. New builds are usually published several times a week, so make sure you always use the latest version:

`kelas@failbowl ~ $ conda update -c shaktidb shakti`

### starting k

Assuming conda's `bin` is in you PATH, start your first k session, ask your first question and enjoy your first answer:

```
kelas@failbowl ~ $ k
2019-04-21 15:38:18 40core 512gb avx2 © shakti m2.0 prod
 2+2
4
```

At any time during k session, you can:

`\h` view k reference card

`\l` view k change log

`\\` quit k session

However, at this point we highly recommend to avoid issuing any of the above commands, especially the latter.

### basics of k

*Annotations* in your k code is the best way not to end up coding Java for food, unless you are Arthur Whitney. We dare to assume you are not quite there yet, so comments start with `/`. When used inline, prepend a space:

```
/line comment
42

42 /inline comment
```

*Indentation* in k is a painful subject. Basically, what you generally want is *no indentation*. This means if your k expression is getting so much larger than life that you are tempted to split it into separate lines, you either need to refactor, or your entire train of thought got derailed and you need to go back to the blackboard. Sometimes, however, indentation is ok, and it is always *one space*. Not two, not four, one. Tabs will be frowned upon big time, because some day they will end up taking other people's precious screen real estate, and humans generally get really itchy when it comes to brick and mortar.

*Capitals*, by convention, are used by k programmers very sparingly, as a last resort measure. This applies both to code and comments. Identifiers in `camelCase` are considered bad form but can sometimes be tolerated, while `c_style` identifiers are not permitted at all since underscore is a k operator. Function and variable identifiers are very often boiled down to an absolute minimum, short identifiers 1-3 characters long are commonplace, which does not impact readability and comprehension given that definitions are adequately annotated. Short identifiers might sound like a bad idea to Java programmers who are not accustomed to identifiers shorter than 100 bytes, but a well-structured and well-formatted k program typically fits on a single screen and requires little or no scrolling. The way our brain works is when the entire program fits into your visual buffer, "cryptic" identifiers are no longer a problem, because their annotated declarations are always right in front of you, and it will take a while before you face the problem of switching between multiple k source files:

```
kei:42 / kenneth eugene iverson
```

*Function* in k is a first-class citizen. k has lambdas, evals, apply, and everything else you would expect from a powerful language, and then some. It takes a leap of faith to believe it, but k is actually more lispy than certain Lisps, only you don't need to get past any parens. In the strict sense, `car` and `cdr` are not there because there are no /linked lists/ under the hood, which is of no surprise because k is designed to be very fast.

*Implicit arguments* is an epitome of brevity and wit. All functions in k, unless stated otherwise, can have up to three implicit arguments, `x`, `y` and `z` respectively. Here are your first functions:

```
 f:{x+y+z}    /declaration
 f[1;2;3]     /call
6             /result
  
 f:{x*x}      /redeclaration
 f 2          /one arg, ok to omit brackets
5             /gotcha
```

*Assignment* operator, as you have correctly guessed, is a *colon*. This fact has a lot to do with k heritage, which is best elucidated by a simple and profound thought experiment. Consider the following line of code:

```
x = x + 1
```

> Although this expression is perfectly valid for the majority of interpreters, compilers and programmers under the sun, any mathematician will respond to this expression with a heavy sigh, followed by *"no, it is not”*.

This gives and excellent hint about how to approach the rest of this document: you need pretend you never wrote a program in your life before, which is a simple trick to overcome your natural to adopt a totally new way of thinking. 

And make no mistake, this is exactly what this document is all about.  Nowhere above you were promised a *gentle* introduction, so from here on your best friends are your intelligence and instincts. Good luck.


## solving problems in k







