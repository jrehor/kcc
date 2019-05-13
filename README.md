# kcc
a crash course in k

## genesis

Computer languages have been around for a while, but in the beginning was the word. We will be writing code in a language called k, but it really helps to talk about it first.

Regardless your background, k will look different. You will question many aspects of its design, and it will respond by questioning things that you consider common sense, and this will be a constructive process. For example, you may find it puzzling why the assignment operator in k is `:` instead of `=`. But give it a chance and try a simple thought experiment. Consider the following code:

```c
x = x + 1
```

Most programmers and most computer languages will readily agree that this expression is perfectly valid, but don't be surprised if a mathematician tells you *"nonsense”*. And once you see what makes him think so, will see why we assign things with `:` in k.

This gives a good hint how to approach k in general: a different perspective is not necessarily wrong and hostile, and nothing prevents you from changing your own. Keep an open mind.

This crash course is not looking to make you an expert k programmer, because that, as with any other area of expertise, takes a lot of time and effort. Allegedly, it is possible to teach oneself Java in 24 hours, but we are not qualified to talk about that. Instead, we are going to talk about fundamental aspects of *thinking in k*, and the curve is going to be steep — but we value your time, so we promise it will be fast and violent.

### who

The man behind k is a computer scientist by the name Arthur Whitney. He is the principal designer of the language, and he is an iconic figure in a community of some of the sharpest and most sophisticated programmers and data scientists employed by some of the most influential institutions on the planet. Since early 90s, he delivers ever more powerful revisions of a concept he has been refining throughout his career, a system to build very efficient software that transforms large amounts of data into large amounts of money. That is, k enjoys much success in the world of finance, where this kind of problems existed long before the man who coined the term "Big Data" was old enough to tie his own shoes. Many forward-looking people embraced the k way and made successful careers by building solutions using k, and they appreciate their tool as much as they appreciate the man behind it — and we believe they have their reasons.

The latest version of k is now available for testing, and this is exciting news because the new generation of k language is the biggest and the most important evolutionary step in its history that appeals to a much wider audience.

### why

There is a good chance that you have heard or read about Arthur Whitney and his language. A lot of people know the story. What is much less likely is that you have ever met a professional k programmer. This happens not just because k programmers are rare, but also because  it is sometimes stated in their contracts that they cannot talk about certain things that give their employers a decisive competitive advantage. We all heard about a language called k, but what we hear more often is how much it sucks to be a Java programmer.

But jokes aside. Implementations of similar systems in languages like C++ or Java usually involve thousands of lines of code written by large teams, built on top of complex library stacks and even more complex infrastructure. The truth that these guys are not supposed to tell you, but always tell you anyway because they hate their jobs, it that their projects are desperately over budget, totally past deadline, and were designed for a version of reality that is no longer real.

In comparison, a k solution is typically a few factors of magnitude less code, implemented by a small and agile team or a single individual, rarely requires external dependencies and always ships on time. 

At first it could be hard to understand how this can even be true, but compare the effort of keeping 100 lines of code in sync with rapidly changing requirements and free of bugs, compared to 10,000 lines of code that do the same thing. No, it is not *100 times* easier. It is *10,000 times* easier. And if you think we are exaggerating, then think again and try prove us wrong, and this will be a start of a beautiful friendship.

### what

`k` is a remarkable piece of software that has many faces. For now lets say it is an interpreter of a computer language. A language that is very powerful.

The source of its power stems from the fact that k was designed from ground up primarily as a *tool of thought*. The vocabulary, syntax and the choice of abstractions offered by the language drive you to think about problems in a focused, clear and uncluttered way that quickly takes you to efficient and elegant solutions. And the reason why thinking in terms of this language is so effective is absolutely nothing supernatural. Is is captured in a proverb that predates history and is known to all cultures: brevity is a soul of wit.

Indeed, k programs tend to be very *concise*, the syntax of the language is very *terse*, and k programmers have no idea what you mean when you say “boilerplate code”. Unlike in most software development workflows, a k programmer spends most of his time thinking about the problem rather than typing stuff into the terminal and browsing the source code tree. In humans, such mechanical activities are known to interfere with abstract thinking and greatly impair their focus — and k minimizes these losses for you.

### how

In addition to being an excellent tool to assist efficient thinking, k is also an astonishingly efficient computer language. The entire system, a tiny binary executable only 100 kilobytes in size without a single external dependency that fits comfortably in the cache of a commodity CPU, implements a selection of fundamental algorithms, data structures, techniques and computational primitives that withstood the test of many decades of production use in some of the world's most demanding data processing environments. The inner components of the system are polished to fit together and complement each other to deliver performance which many outsiders find very difficult to believe at first. It is also not uncommon for k newcomers to experience total shock when they first realize what kind of power they can wield with just a few precise keystrokes.

All of k programming takes place in **REPL**, a concept which requires little introduction these days, but is actually much older than many seem to think. It has been around for at least 50 years, and is known as *dialogue approach*, a live conversation between a human and machine as a flow of questions and answers. And in k, this conversation is much more fluent than in any other modern REPL-driven system you may be familiar with, because the questions are short and the answers are fast. This is the essence of *the way of k*, an experience that all k programmers consider immensely aesthetically and intellectually satisfying. This is why people who write software in k *love their jobs*, and this has nothing to do with their paychecks.

## exodus

 Since the only known way to learn how to program is to write programs, you will need a live k environment. Fortunately, as all things k, it takes very little effort.

### getting k

We will use a `trial` version of k, which comes with a reasonable limit of 1 gigabyte of workspace per k process. This limit is for your own protection, so that you don’t accidentally convert too much data into too much money too early, because, as any k programmer will tell you, with great power comes great responsibility.

The k interpreter is currently available for `Linux` and `macOS` on `x86_64` architecture. If you are on Solaris, OpenBSD or z/OS — hang tight, good things come to those who wait. The same applies for `ARM64` architecture, but if you are on Windows, well, lets not cry over spilled Guinness.

Without further ado, go to https://anaconda.org/ and follow the instructions. Anaconda shell integration option is highly recommended. Once you install Anaconda, install the package called  `shakti`, which is nothing else but `k` in disguise:

`kelas@failbowl ~ $ conda install -c shaktidb shakti`

As with all things k, the development of k language itself is happening at terrifying pace. New builds are usually published several times a week, so make sure you always use the latest version:

`kelas@failbowl ~ $ conda update -c shaktidb shakti`

### using k

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

### remarks on style

As any other computer language, k expects a programmer to observe and follow certain conventions on coding style in order to understand the code written by the others and let their own code be understood. While some rules of the house of k are universal, some are not.

**Annotations** in your k code is the best way not to end up coding Java for food, unless you are Arthur Whitney. We dare to assume you are not there yet, so comments start with `/`. When used inline, prepend at least one space:

```
/line comment
42

42 /inline comment
```

**Indentation** in k is a tricky subject. Basically, what you generally want is *no indentation*. This means if your k expression is getting so large that you are tempted to split it into separate lines, you either need to refactor, or your entire train of thought got derailed and you need to go back to the blackboard. Sometimes, however, indentation is fine and even necessary, and it is always *one space*. Not two, not four, one. Tabs will be frowned upon, because some day they will end up taking other people's precious screen real estate, and humans get really itchy when it comes to brick and mortar.

**Capitals**, by convention, are used by k programmers very sparingly, as a last resort measure. This applies both to code and comments. Identifiers in `camelCase` are considered bad form but can sometimes be tolerated, while `c_style` identifiers are not permitted at all since underscore is a k operator. Identifiers of functions and variables are very often boiled down to an absolute minimum, names 1-3 characters long are commonplace, which does not impact readability and comprehension given that their definitions are adequately annotated. Short identifiers might sound like a bad idea to Java programmers who are not accustomed to identifiers shorter than 100 bytes, but a well-structured and well-formatted k program typically fits on a single screen and requires little or no scrolling. The way our brain works is when the entire program fits into your visual buffer, "cryptic" identifiers are no longer a problem, because their annotated declarations are always right in front of you, and it will take a while before you face the problem of switching between multiple k source files:

```
kei:42 / kenneth eugene iverson
```

**Functions** in k are first-class citizens. k has lambdas, eval, apply, and then some more. It takes a leap of faith to believe it, but k is probably more lispy than certain Lisps, only you don't need to get past any parens to be able to read it. In a strict sense, though, since there are no linked lists under the hood, k is clearly not lisp, because it was designed to be fast.

Most languages require you to explicitly declare arguments of your function. You can also do that in k if you want to, but if you don't, a function can have up to three **implicit arguments** called `x`, `y` and `z`, which basically means you declare them by simply referencing them in the function body. It is an extremely convinient feature, not nearly as scary as it sounds:

```
 f:{x+y+z}    /f takes three arguments,
 f[1;2;3]     /and here is how to call it
6
  
 f:{x*x}      /f only takes one argument,
 f 2          /so we can omit brackets
4
```

Lets recap. So far you know how to start k, how to assign values, declare most basic functions and variables, and how to annotate your code. This is a good foundation, but tells you absolutely nothing about k. Nowhere above you were promised a *gentle* introduction, so from here your best two friends are your intelligence and intuition.

## revelation

### vectors vs scalars

### no stinking loops

### right to left

### how to solve it







