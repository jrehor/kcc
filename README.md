# kcc

**[genesis](#genesis)**

* k → [ø](#ø) | [who](#who) | [why](#why) | [what](#what) | [how](#how)

**[exodus](#exodus)**

* [install](#install) | [run](#run)
* [style](#remarks-on-style) → [comments](#style-annot) | [separator](#style-sep) | [tabs](#style-ident) | [caps](#style-caps)
* [parlance](#remarks-on-parlance) → [xyz](#parl-xyz) | [rank](#parl-rank)

**[numbers](#numbers)**

* vector math → [vectors vs atoms](#vectors-vs-atoms) | [v+v](#v-plus-v) | [v+a](#v-plus-a) | [indexing](#v-indexing)
* type system → [two types of types](#two-types-of-types) | [num](#typ-num) | [char](#typ-char) | [name](#typ-name) | [time](#typ-time) | [composite](#typ-composite) | [cast](#typ-cast)
* evaluation → [right to left](#right-to-left-and-back-again) | [precedence](#rtl-precedence)
* adverbs → [no stinking loops](#no-stinking-loops)

**[proverbs](#proverbs)**

* reading code → [how to solve it](#how-to-solve-it)

## genesis

### ø

Computer languages have been around for a while, but in the beginning was the Wørd. We will be writing code in a language called k, but it will help to talk about it first.

---------------------

**k is different**. At first, you will be questioning its design, and it will respond by questioning things that you consider common sense, but soon enough it will become a constructive conversation, and here is how. The first thing newcomers frown upon is why the assignment operator is `:` instead of `=`. But before you close the tab, try a simple thought experiment. Consider the following code:

```java
x = x + 1
```

Most programmers will readily agree that this expression is making perfect sense, but if you show it to a mathematician, be ready to hear "no, it isn't". And once you see what makes him think so, you will see why we assign values with `:` in k. The above expression, although not entirely nonsensical, in k is pretty much always **false**. A different perspective is not necessarily wrong, as there is no tragedy if it someday becomes your own. That is the right mindset to approach k, and by the way, once you make it far enough to be able to provide an example when `x=x+1` is **true** in k, don't be a stranger and submit a pull request.

---------------------

This crash course is not looking to make you an expert k programmer, because that takes a lot of time and effort. We heard it is possible to teach oneself Java in 24 hours, but we are not qualified to talk about that. Instead, we are going to talk about fundamental aspects of *thinking in k*, and the goal is to give enough proficiency, confidence and motivation for you to continue on your own, and the curve is going to be steep — but we value your time, so we promise it will be fast and violent.

* The text assumes proficiency in general programming concepts, and cuts a lot of corners at some expense of readability.
* The course is entirely driven by densely annotated code which expects your undivided attention and intuition.
* New syntax is often introduced inline, some meanings are left to be inferred or assumed self-explanatory.
* Most annotations in the code contain essential learning material that cannot be overlooked.
* The narrative is strictly linear, each chapter builds on all previous.
* None of the exercises are optional, skipping them will halt your progress.

This might feel a bit intense, but we also hope the whole thing is still lightweight and entertaining enough to be completed in just one focused session.

This document is **not a k reference** and not to be treated as such. The majority of subjects are covered at depth sufficient to support progress but by no means exhaustive.

### who

The man behind k is a computer scientist by the name Arthur Whitney. He is the principal designer of the language, and he is an iconic figure in a community of some of the most sophisticated programmers and scientists employed by some of the most influential institutions on the planet. Since early 90s, he delivers ever more powerful revisions of a concept he has been refining throughout his career, a system to build very efficient software that transforms large amounts of data into large amounts of money.

That is, k enjoys much success in the world of finance, where this kind of problems existed long before the man who coined the term "Big Data" was old enough to tie his own shoes. Many forward-looking people embraced the k way and made successful careers by building solutions using k, and they appreciate their tool as much as they appreciate the man behind it, and we believe they have their reasons.

### why

There is a good chance that you have heard or read about Arthur Whitney and his language. A lot of people know the story. What is much less likely is that you have ever met a professional k programmer. This happens not just because k programmers are rare — there are separate reasons for that, mostly because k is never fishing for cheap publicity. This is how we all heard about a language called k, but what we hear more often is how much it sucks to be a Java programmer.

But jokes aside. Implementations of similar systems in languages like C++ or Java usually involve thousands of lines of code written by large teams, built on top of complex library stacks and even more complex infrastructure. The truth that these guys are not supposed to tell you, but always tell you anyway because they hate their jobs, it that their projects are desperately over budget, totally past deadline, and were designed for a version of reality that is no longer real.

In comparison, a k solution is typically a few factors of magnitude less code, implemented by a small and agile team, sometimes by a single individual, rarely requires external dependencies and always ships on time. 

At first it could be hard to understand how this can even be true, but compare the effort of keeping 100 lines of code in sync with rapidly changing requirements and free of bugs, compared to 10,000 lines of code that do the same thing. Against all intuition, it is not 100 times easier, but 10,000 times easier. And if you think we are exaggerating, refresh your memory of the concept of cyclomatic complexity, then try prove us wrong, and this will be a start of a beautiful friendship.

### what

`k` is a remarkable piece of software that has many faces. For now we will accept it is an interpreter of a computer language. A language that is very powerful.

The power stems from the fact that k was designed from ground up primarily as a *tool of thought*. The vocabulary, syntax and the choice of abstractions offered by the language drive you to think about problems in a focused, clear and uncluttered way that quickly takes you to efficient and elegant solutions. And the reason why thinking in terms of this language is so effective is absolutely nothing supernatural. Is is captured in a proverb that predates history and is known to all cultures: brevity is a soul of wit.

Indeed, k programs tend to be very *concise*, the syntax of the language is very *terse*, and k programmers have no idea what you mean when you say “boilerplate code”. Unlike in most software development workflows, a k programmer spends most of his time thinking about the problem rather than typing stuff into the terminal and browsing the source code tree. In humans, such mechanical activities are known to interfere with abstract thinking and greatly impair their focus — and k minimizes these losses for you.

The latest version of k is now available for testing, and this is exciting news because the new generation of k language is the biggest and the most important evolutionary step in its history that appeals to a much wider audience.

### how

In addition to being an excellent tool to assist efficient thinking, k is also an astonishingly efficient computer language. The entire system, a tiny binary executable only 100 kilobytes in size without a single external dependency that fits comfortably in the cache of a commodity CPU, implements a selection of fundamental algorithms, data structures, techniques and computational primitives that withstood the test of many decades of production use in some of the world's most demanding data processing environments. The inner components of the system are polished to fit together and complement each other to deliver performance which many outsiders find very difficult to believe at first. It is also not uncommon for k newcomers to experience total shock when they first realize what kind of power they can wield with just a few precise keystrokes.

All of k programming takes place in **REPL**, a concept which requires little introduction these days, but is actually much older than many seem to think. It has been around for at least half a century, and is known as *dialogue approach*, a live conversation between a human and machine as a flow of questions and answers. And in k, this conversation is much more fluent than in any other modern REPL-driven system you may be familiar with, because the questions are short and the answers are fast. This is the essence of the way of k, an experience that all k programmers consider immensely aesthetically and intellectually satisfying. This is why people who write software in k love their jobs, and this has nothing to do with their paychecks.

## exodus

Since the only known way to learn how to program is to write programs, you will need a live k environment. Fortunately, as all things k, it takes very little effort.

### install

We will use a trial version of k, which comes with a reasonable limit of 1 gigabyte of workspace per k process. This limit is for your own protection, so that you don’t accidentally convert too much data into too much money too early, because, as any k programmer will tell you, with great power comes great responsibility.

The k interpreter is currently available for `Linux` and `macOS` on `x86_64` architecture. If you are on Solaris, OpenBSD or z/OS — hang tight, good things come to those who wait. The same applies to `ARM` and `WASM` architectures, but if you are on Windows, well, lets not cry over spilled Guinness.

Without further ado, go to https://anaconda.org and follow the instructions. Anaconda shell integration option is recommended. Once you install Anaconda, install the package called `shakti`, which is nothing else but `k` in disguise:

```sh
kelas@failbowl ~ $ conda install -c shaktidb shakti
```

As with all things k, the development of k language itself is happening at terrifying pace. New builds are usually published several times a week, so make sure you always use the latest version:

```sh
kelas@failbowl ~ $ conda update -c shaktidb shakti
```

### run

Assuming conda's `bin` is in your PATH, make sure you have `rlwrap` utility installed, and put an alias `alias k="rlwrap k"` in your shell rc file. Start your very first k session like so:

```sh
kelas@failbowl ~ $ alias k="rlwrap k"
kelas@failbowl ~ $ k
```

Type in your first k expression, and enjoy your first answer:

```q
2019-04-21 15:38:18 40core 512gb avx2 © shakti m2.0 prod
 2+2
4
```

There isn't much to write home about your k skills yet, so lets take a look at the startup banner. It packs a lot of useful information:

| it says             | it means                      |
| :-------------------|:------------------------------|
| 2019-04-21 15:38:18 | timestamp of your k build     |
| 40core              | cpu cores you can use in k    |
| 512gb               | max workspace, expect 1gb     |
| avx2                | the best your cpu can do      |
| shakti              | the company behind k          |
| m                   | `m` for macos, `l` for linux  |
| 2.0                 | well, 2.0 is better than 1.0  |
| prod                | be prepared to see `test`     |

If it ever comes to that, always include your banner in your bug reports.

At any time during k session, you can:

`\h` view k reference card

`\l` view k change log

`\\` quit k session

However, at this point we highly recommend to avoid issuing any of the above commands, especially the latter.

### remarks on style

As any other computer language, k expects a programmer to observe and follow certain conventions on coding style and terminology in order to understand the code written by the others and let their own code be understood. While some rules of the house of k are universal, some are not.

-------------------

<a name="style-annot"></a>
**Annotations** in your k code is the best way not to end up coding Java for food, unless you are Arthur Whitney. We dare to assume you are not there yet, so comments start with `/`. When used inline, prepend at least one space. Here is an annotated declaration of two variables:

```q
/line comment
a:42

b:42 /inline comment
```
-------------------

<a name="style-sep"></a>
**Separator** character in k is `;` and it is used for one thing and one thing only, to separate **k expressions**. As you have seen above, if there is just one expression on the line, k doesn't require you to terminate it explicitly because it is terminated by a newline. The same is true for the last expression on the line if you have more than one. Separator is used the same way and means the same thing everywhere, e.g. inside functions. Later we will see that separator is an essential part of certain language constructs, but even there it has the same meaning:

```q
a:1; b:2; c:3       /one line three expressions
a:1;b:2;c:3         /dense version of the above
```

-------------------

<a name="style-ident"></a>
**Indentation** in k is a tricky subject. Basically, what you generally want is *no indentation*. This means if your k expression is getting so large that you are tempted to split it into separate lines, you either need to refactor, or your entire train of thought got derailed and you need to go back to the blackboard. Sometimes, however, indentation is fine and even necessary, and it is always *one space*. Not two, not four, one. Tabs will be frowned upon, because some day they will end up taking other people's precious screen real estate, and humans get really itchy when it comes to brick and mortar.

-------------------

<a name="style-caps"></a>
**Capitals** are used by k programmers very sparingly, as a last resort measure. This applies both to code and comments. Identifiers in `camelCase` are considered bad form but can sometimes be tolerated, while `c_style` identifiers are not permitted at all since `_` is an operator. Identifiers of functions and variables are very often boiled down to an absolute minimum, names 1-3 characters long are commonplace, which does not impact readability and comprehension given that their definitions are adequately annotated. Short identifiers might sound like a bad idea to Java programmers who are not accustomed to identifiers shorter than 100 bytes, but a well-structured and well-formatted k program typically fits on a single screen and requires little or no scrolling. The way our brain works is when the entire program fits into your visual buffer, "cryptic" identifiers are no longer a problem, because their annotated declarations are always right in front of you, and it will take a while before you face the problem of switching between multiple k source files:

```q
kei:42         /kenneth eugene iverson
```

### remarks on parlance

The most important terminology in k that is essential for you to learn revolves around functions. Functions in k are first-class citizens. k has lambdas, eval, apply, recursion, and then some. It takes a leap of faith to believe it, but k is probably more lispy than certain Lisps, only you don't need to get past any parens to be able to read it. In a strict sense, though, since there are no linked lists under the hood, k is clearly not lisp, because it was designed to be fast.

-------------------

<a name="parl-xyz"></a>
**Implicit arguments** is something that will make you wonder at first, since most languages require you to explicitly declare arguments of your functions. Sure you can also do that in k if you want to, but if you don't, a k function can have up to three implicit arguments called `x`, `y` and `z`, which basically means you declare them by simply referencing them in the function body. It is an extremely convinient feature, not nearly as scary as it sounds:

```q
 f:{x+y+z}    /f[] takes three arguments
 f[1;2;3]     /and here is how to call f
6
  
 f:{x*x}      /f[] has only one argument
 f 2          /and you can omit brackets
4
```

Note that when calling a function with three arguments `f[1;2;3]` we had to use square brackets and use an expression separator, because each argument passed to a function is an expression in its own right. However, second function only takes one argument, and we were allowed to omit brackets, although we could also say `f[2]`.

This illustrates a core principle of k syntax — almost everything that you intuitively feel you should be able to omit, can and should be omitted. Top candidates for omission are square `[]` and round brackets `()`. The lesser you type, the better your code will get.

-------------------

<a name="parl-rank"></a>
**Rank** is another way of saying *valence*, a fancy word that describes a simple idea that is extremely important to be understood well. Rank of an operator or a function is basically the count of arguments they take. Two functions shown above have ranks of 3 and 1, respectively. 

Two specific ranks are so important that they have their own names. A function or an operator...

* that takes **one** argument is called **monadic**
* that takes **two** arguments is called **dyadic**

As you will see, the vast majority of native operators in `k` have exactly two completely different meanings based on the context where they are used, which is in turn defined by the number of arguments offered to the operator. To overlook this fact is a grave mistake, so you better get a very strong grip on the idea that some things in life are **monadic**, while others are **dyadic**. For ranks of higher and lesser order it is fine to worry less. For example, when you used your first ever k operator in the expression `2+2`, you have used the **+** operator in a **dyadic** context, which basically meant that you offered it *two* operands to work on, left and right, respectively. However, once you discover what the **+** operator stands for when used in a **monadic** context, it will change your life forever, so let us skip this discussion for now.

-------------------


**Recap:**

So far you know how to:

* add two integers
* assign values to variables
* declare most basic functions
* be friends with `x`, `y` and `z`
* appreciate the importance of rank
* google up "ken iverson" 
* annotate your code

This is a good start, but tells you absolutely nothing about what k really is. Nowhere above you were promised a *gentle* introduction, so from here your best two friends are your intelligence and intuition, and the complexity is O(n*n).

## numbers

### vectors vs atoms

The word `atom` is a synonym for `scalar value`, or simply `scalar`. Every language has them, and in k they are as useful as elsewhere. But k belongs to a family of *vector languages*, which basically means its fundamental type is an ordered set of atoms or other ordered sets. In k parlance, terms "array", "list" and "vector" are often used interchageably and refer to the same thing, but we will stick with `vector` to avoid confusing you, because vectors are much more general than classic *arrays* and have nothing to do with *linked lists*. Besides, it also a cool word.

```q
 s:42             /an atom with a name is scalar variable
 
 a:(0,1,2,3,4)    /one way of declaring an integer vector
 b:0 1 2 3 4      /same effect using more informal syntax

 a
0 1 2 3 4

 b
0 1 2 3 4
```

<a name="v-plus-v"></a>
The most enlightening fact about vectors is that most operations you expect to work for atoms work equally well for vectors, too:

```q
 a*a             /don't get mad, get even
0 2 4 6 8

a-b              /pairwise substraction
0 0 0 0 0 

 a%b             /pairwise divison (yes, division in k is %, and ø means nil, nan, void and other bad news)
ø 1 1 1 1

 a=b             /pairwise comparison (everything >0 in k is truthy)
1 1 1 1 1 
```

<a name="v-plus-a"></a>
Mixing atomic and vector operands makes total sense and is enormously useful:

```q
 a+1             /increment each of a
1 2 3 4 5 

 a=1             /compare each of a to 1
0 1 0 0 0

 a%0             /divide each of a by 0 
ø ∞ ∞ ∞ ∞        /that is, ∀x∈ℚ (x%0) ∈ {-∞,∞,ø}, beware (0%0) = ø, enjoy responsibly

 3%a             /divide 3 by each of a
∞ 3 1.5 1 0.75
```

However, pairwise operations on vectors of disparate lengths or dimensions make much less sense to k than division by zero, and will throw an error:

```q
 a:0 1 2 3 4
 b:0 1 2
 a+b
 
a+b
 ^
length error
```

<a name="v-indexing"></a>
**Indexing** is zero-based as you would expect, but there is a very pleasant surprise there:

```q
 a:2 4 8 16 32
 
 a[2]          /get 3rd element of a
8

 a 2           /same but less typing
8

 a[1 4]        /get 2nd and 5th item
4 32           /gives another vector

 a 1 4         /same thing less work
4 32

 b:1 4         /b is an index vector
 a b           /same as a[b] less []
4 32           
```

### two types of types

It is not a stretch to say the typing discipline in k is a balancing act. It gets strict when it has to, but also agrees that implicit casts and type coersion have their strengths — especially when done right, which in k they are.

Seeing is believing, but before we see the examples, the first thing you need to know about types in k is that they are divided into two broad classes: **vector types** and **atomic types**. That is, a vector with a single element, say, `42`, is not the same type as an atomic integer of the same value. Finally, since functions and other things in k are also assignable values, they have their place in type system too. Those are **special types** and we will not cover them here in detail.

Here is a quick overview of k types and their symbolic names:

```q
atom      vect        type
  `i        `I        int
  `f        `F        float
  `c        `C        char
  `n        `N        name
  `D        `D        date
  `t        `T        time
```

This is not very revealing, so lets see them in action. The operator to query the type of anything in k is `monadic @`, and if you are not sure what we mean by `monadic`, it is a good time for you to hit 'home' and start over.

<a name="typ-num"></a>
```q
 @42         /int atom
`i

 @.5         /float atom
`f

 @0 1 2      /int vector
`I

 v:0 1 .5 2
 @v          /float vector (presence of 0.5 promotes all neighbors and the vector itself to float)
`F

 v 1         /2nd element is a float, hinted by the trailing f
1f

 @v 1        /just to make sure
`f
```

<a name="typ-char"></a>
Like in C, there is no dedicated type for strings in k. Strings are just **char vectors**:

```q
 @"k"        /char atom
`c

 s:"kei";@s  /s is char vector
`C
 
 s 0         /1st element of s
"k"
```

<a name="typ-name"></a>
However, k has something C doesn't. We have a type called **name**, which is the same concept as **internalized string** found in some other languages. This means that a single instance of an arbitrarily long string can be placed into a global hash table that persists for a lifetime of a k process and can later be referenced by its hash key as many times as necessary without creating additional copies of the string. As you will discover later, names come very handy in many situations, but for now lets just see how they quack:

```q
 a:`kei              /the string "kei" is now internalized
 @a                  /name atom
`n

 b:`kei`kei`kei      /vector of three references to a single instance of "kei" string
 @b                  /vector of names
`N

 @`"ken iverson"     /spaces in names, no problem
`n
```

<a name="typ-time"></a>
**Temporal types** in k are `date` and `time`:

```q
 d:1981-02-01        /yyyy-mm-dd
 @d                  /atomic date type is special, it is a capital D, same as date vector
`D

 t:12:34:56.789      /hh:mm:ss.sss
 @t
`t

 dt:d+t;dt           /date + time... = datetime!
1981-02-01T12:34:56.789 

 @dt                 /operations on temporal types is a story for another day
`T 
```

<a name="typ-composite"></a>
Of special mention is the **composite vector** type. Such vectors are either a mixture of atoms of disparate types, or contain something more complex than atoms, e.g. other vectors.

```q
 c:0,1,"a",2,3          /a char impostor among ints, c is composite
 @c                     /a composite type symbol is just a backtick
`

 a:(1 2 3;4 5 6;7 8 9)  /a vector of vectors is a composite vector
 a
1 2 3
4 5 6
7 8 9
 @a
`

 a:{x},{x+x},{x*x}      /a vector of lambdas, sure, why not
 a[2]16                 /calls 3rd lambda, same as a[2][16]
256
```

<a name="typ-cast"></a>
**Casting**, both explicit and implicit, is demonstrated by the following examples which also give a general feel of how type coersion behaves:

```q
 1+.5                  /int plus float is float, no surprises here
1.5

 1f*2                  /1f is the same as 1.0, saves one keystroke
2f 

 `i$42.99              /explicit cast `f to `i just drops mantissa
42

 `i$42.0 42.99         /same is true for float vectors
42 42

 0+"abc"               /adding an int atom to a char vector yields an int vector of its ascii codes
97 98 99

 `c$1+"HAL9000"        /increment ascii codes by one, cast back to char, surprise:
 "IBM:111"

 "012"+"345"           /sum of char vectors adds their ascii codes pairwise, result is still a char vector
"ceg"

 1+`kei                /no math for names
  ^
type error

 a:1 2 3               /define a int vector
 a[0]:1f               /replace its first element with a float
 @a                    /ouch, int vector got demoted to composite
`
 a:`f$a                /explicitly cast composite to float
 @a                    /voila, a float vector
`F

 `i$1981-02-01         /integer representation of dates is puzzling at first
-15674

 15674+1981-02-01      /adding 15674 days solves the mystery: all dates in k are simply offsets from:
2024-01-01
```

There is more to be said about the type system, but we have more than enough to proceed.

### right to left and back again

It could not possibly escape your attention that the syntax for indexing vectors and calling functions is the same:

```q
 f:{x+x}      /some function
 d:2 4 8 16   /some data items
 i:0 3        /some indices

 f[d]         /call a function
4 8 16 32

 d[i]         /index a vector
2 16

 f[d[i]]      /compose the two
4 32 
```

What you also know that k actively encourages you to omit brackets whenever possible, so lets do exactly that:

```q
 f d i        /same as f[d[i]]
4 32
```

This tiny example reveals an astonishing truth. Once we drop the brackets, it suddenly becomes absolutely natural to read this expression *from right to left*. Take your time to contemplate and process this statement. In very little time you will see how it works in practice, and once you put it to practice yourself, you will see that this way of functional composition is beautiful, elegant and intuituve.

**k expressions are read, written and evaluated right to left.**

Just to be clear, when we say "expressions" we don't mean "programs", and this is a very important distinction. Below is a diagram of a small **k program** that consists of three identical expressions `f d i` with parens added for clarity. Further down is the order of evaluation of the entire program:

```q
/   L       T       R
/(f d i);(f d i);(f d i)

/   I   >   II  >  III
/(3 2 1);(6 5 4);(9 8 7)
/   <       <       <
```

 **k programs are read, written and evaluated left to right.**

<a name="rtl-precedence"></a>
Now that we know which way the rivers flow in k land, we are ready to discuss a related, no less important subject of **precedence**.

We all take it for granted that multiplication and division bind stronger than addition and substraction and should be calculated first, and it almost feels natural that computer languages must have complex operator precedence hierarchies to do anything useful. That is not the case with k:

**There is no operator precedence in k unless it is explicitly defined by round brackets.**

That is, by default all operators in a k expression are treated equally and evaluated strictly from **right to left**, and that includes **arithmetic** operators, e.g. `*` has no precedence over `+`. Here are some basic math expressions, annotated with their order of evaluation:

```q
 3+2+1        /"take 1, add 2, add 3"
6

 3*2+1        /"take 1, add 2, multiply by 3"
9

 (3*2)-1      /"take 2, multiply by 3, sub 1"
5

 -1+3*2       /same as above, without parens
5
```

It is much easier to get used to lack of precedence than you may think, and once you do, you will generally want to avoid using parens unless you absolutely have to. The last example from above shows the basic strategy of ditching them: it is usually possible to rearrange the expressions so that the order of evaluation becomes linear. Although precedence override is often inevitable and can be beneficial, it can also have an adverse effect on readability, because it breaks the natural flow of code comprehension. That is:

**Once you learn to read k expressions from right to left, you want to go fast and uninterrupted, and round brackets get in your way.**

Okay, this was a tough one, but we are done.

### no stinking loops

This part might be easier to digest than the previous, especially if you are fond of functional programming. The heading says it all - no matter how you try, you will not find a k construct that resembles an explicit `for` loop. It is simply absent, and not just because it is verbose and causes untold damages from the same trivial errors people keep on making coding loops.

The main reason explicit loops are missing from k is because they are *unnecessary*. Of course k has loops, but they are *implicit* and hardly ever referred to by that name. The existence of `while` construct, although k has it, is better be ignored.

Loops are available in k in form of **six** simple and strong abstractions known as **adverbs**. Each by itself, and even more so when combined together, are sufficient to completely displace the way of thinking in explicit loops. Also, it comes without saying that k supports **recursion**, which is no less elegant way to avoid loops in many pracatical situations.

But lets focus on adverbs. Here is the magnificent six:

----------------
adverb **each** is `f'x`

where `f` is a function or operator that takes one argument and `x` is an input vector

```q
 a:0 1 2 3 4    /some data
 sq:{x*x}       /a function that takes one argument

 sq'a           /each applies f to each element of x and returns a vector of results
0 1 4 9 16      /each of a, squared
```
----------------
adverb **over** is `f/x`

adverb **scan** is `f\x`

where `f` is a function or operator that takes two arguments and `x` is an input vector

```q
 a:0 1 2 3 4    /some data

 +/a            /over inserts a plus between adjacent elements (i.e. 0+1+2+3+4) and returns the final result
10              /sum of a

 +\a            /scan is exactly the same as over, but returns all intermediate results as well
0 1 3 6 10      /running sum of a
```
----------------
adverb **eachleft** is `x f\:y`

adverb **eachright** is `x f/:y`

where `f` is a function or operator that takes two arguments and `x` and `y` are left and right inputs, either vectors or atoms

```q
 10 20 30-\:5   /eachleft gives (10-5),(20-5),(30-5)
5 15 25         /each of left, substracted by right

 5-/:10 20 30   /eachright gives (5-10),(5-20),(5-30)
-5 -15 -25      /left, substracted by each of right
```
----------------

adverb **eachprior** is `x f':y` and `(f':)x`

first form is `seeded eachprior` where `f` is a dyadic function or operator, and `x` is a seed value and `y` is an input vector

second form is `seedless eachprior` where `f` is a dyadic function or operator, and `x` is an input vector


```q
 2+':4 8 16          /seeded eachprior        gives (2+4),(4+8),(8+16)
6 12 24              /sum of first item and seed, then sum of each item and the item prior to it

 (+':)4 8 16         /seedless eachprior      gives (4),(4+8),(8+16)
4 12 24              /first item stays as is, then sum of each item and the item prior to it
```
----------------

**Recap:**

We have seen:

* what k type system looks like
* how basic vector and atom math works
* which way to read and comprehend k code
* what is the only existing precedence rule
* why there is no `for` and why there are `adverbs`

----------------

**Checkpoint exercise:**

Consider this example of two adverbs working together:

```q
 x:!9                          /! is til, get first n integers
 x                             /tada, we have all ints up to 8
0 1 2 3 4 5 6 7 8

 x+:1                          /add 1 to each of x, also x:x+1
 x
1 2 3 4 5 6 7 8 9

 x*\:/:x                       /"x times eachleft eachright x"
1 2  3  4  5  6  7  8  9    
2 4  6  8  10 12 14 16 18
3 6  9  12 15 18 21 24 27
4 8  12 16 20 24 28 32 36
5 10 15 20 25 30 35 40 45
6 12 18 24 30 36 42 48 54
7 14 21 28 35 42 49 56 63
8 16 24 32 40 48 56 64 72
9 18 27 36 45 54 63 72 81 
```

The goal is to make sure you understand the logic and the order of evaluation of this expression. You have everything you need:

* read right to left
* there is no precedence
* no explicit loops either
* k interpreter is your friend

Take your time, make sure you got it before advancing to the next chapter, where things will get a lot less innocent, and fast.

-------------------

Well done, here is the bonus you were waiting for: the meaning of monadic `+`:

```q
 mat:(1 2 3;4 5 6;7 8 9)       /shall there be mat

 mat                           /print matrix as is
1 2 3
4 5 6
7 8 9 

 +mat                          /flip aka transpose
1 4 7
2 5 8
3 6 9
```

As promised, your life just changed forever, there is no going back, so keep on reading.

## proverbs

### how to solve it

The title of this chapter is borrowed from a legendary book published back in 1945, a small volume by mathematician George Pólya where he shows how to approach problems and arrive to solutions. It is a very inspiring read.

Equipped with everything we have so far, we are going to tackle a little problem. We will look at a k function that actually does something very useful and implements a very familiar algorithm. The subject of the game is to identify the algorithm and figure out how it is implementented in k (actually, in reverse order).

Don't be in a hurry to paste anything into your interpreter, it is a lot more useful to dissect it on paper first. Once we are done, you will be very tempted to try a lot of new things on your own. So here is the code:

```q
/what is f, and how it works?
f:{$[2>#?x;x;,/f'x@=x>rand x]} 
```

Okay, almost nothing looks familiar here, and the whole little monster is just creepy. But before you head for the fire exit, give it a chance. Once we take it apart brick by brick, you will agree it is actually very simple and readable:

```q

f:{$[2>#?x;x;,/f'x@=x>rand x]} 

f:{...}           /f is a function, that is a good start
f:{.x.}           /f takes only one implicit argument, x
f:{.f.}           /f clearly calls f, so it is recursive

$[?;?;?]          /the entire body of f is nothing more but
$[c;t;f]          /a ctf conditional, think if(c){t}else{f}

2>#?x             /c:      some bool condition
x                 /t:      do this if c is true
,/f'x@=x>rand x   /f:      do that if c is not

2>#?x             /whatever this condition tests, it is clear that f[]
                  /will halt recursion once it turns true, returning x
                  /so lets figure out what it says, from right to left

?x                /monadic ? is 'distinct'        unique elements of x
#x                /monadic # is 'count'        count the elements of x
#?x               /'count distinct'         count unique elements of x
2>x               /'greater'                  true if x is less than 2

$[2>#?x;x;...]    /so this is just "return x if x has <2 unique items"
```

Here is what we know so far:

1. the control flow of the recursive function
2. the condition that stops recursion

This gives enough confidence to wrestle down the last part, the recursion step:

```q

,/f'x@=x>rand x    /this must be the recursion step, read right to left:

 x:4 0 1 2         /an imaginary dataset to better see what is happening
 rnd:rand x        /pick a random element from x (rnd added for clarity)
 rnd
2 

 cmp:x<rnd         /bool vector of 0s where x[n]<rnd, 1s where otherwise
 cmp
0 1 1 0

 idx:=cmp          /= is 'group': 2 vectors, indices of 0s and 1s in cmp
 idx
0|0 3
1|1 2

 pts:x@idx         /dyadic @ is 'index': elements of x at indices in idx
 pts
0|4 2
1|0 1

pts:x@=x>rand x    /"partition x by pivot: items < rnd and items >= rnd"

x:f'pts            /adverb 'each': call f recursively for each partition

,/x                /,/ is 'raze': unwind aka flatten a vector of vectors

 v:(1 2 3;4 5 6)
 v
1 2 3
4 5 6
 ,/v
1 2 3 4 5 6
```

Now that we know what every specific part does, we can zoom out and try to see the big picture. Feel free to use the interpreter to play around and test your ideas. And of course, `f` is nothing else but:

-------------------

```q
 qs:{$[2>#?x;x;,/qs'x@=x>rand x]}        /quicksort by random pivot

 qs 9 2 5 5 1 8 1 3 6 1                  /sort an int vector
1 1 1 2 3 5 5 6 8 9

 qs 2.6 -∞ 8.6 π 1.7 ∞ 3.5 5.6           /sort a float vector (hello π)
-∞ 1.7 2.6 π 3.5 5.6 8.6 ∞

 qs "edrofgtnljgrpliifp"                 /sort a char vector
"deffggiijllnopprrt" 
```

This is definitely not the fastest `quicksort` ever written, but in real life you would simply use the built-in operator which is a lot more efficient. It is just monadic `^x`:

```q
 ^2.6 -∞ 8.6 π 1.7 ∞ 3.5 5.6             /^x is 'sort'
-∞ 1.7 2.6 π 3.5 5.6 8.6 ∞
```

But what out toy example demonstrates well is the principle of **doing more with less**, and that is what k is all about.

The annotated breakdown of `qs` code gives a good impression of what is typically going on inside of k programmer's head, but tells you nothing about how fast it usually happens. A proficient k programmer would read and understand `qs` in well under two minutes. With a bit more practice, you will agree that reading k programs is easy and fun, but even sooner you will see why k programmers enjoy writing them so much.

-------------------

Speaking of fun, compare functionality of these two programs:

```java
package com.less.with.more.doing.sort;
public final class qs{public void s(int[] x){}}
```

```q
qs:{$[2>#?x;x;,/qs'x@=x>rand x]}
```

-------------------

And now these source code of these two:

```java
import java.util.Arrays;  
public class S{public static void main(String[] a){ 
int[] x={5,4,3,2,1};Arrays.sort(x);
System.out.printf("%s",Arrays.toString(x));}} 
```

```q
 ^5 4 3 2 1
```

Check out more `quicksort` implementations in [C++](https://gist.github.com/christophewang/ad056af4b3ab0ceebacf), [Python](https://gist.github.com/anirudhjayaraman/897ca0d97a249180a48b50d62c87f239), [JavaScript](https://gist.github.com/claudiahdz/39a86084edaaabe7fc17c321c0bb6896) and [Java](https://github.com/Code2Bits/Algorithms-in-Java/blob/master/sort/src/main/java/com/code2bits/algorithm/sort/QuickSort.java).

-------------------

**Recap:**

While analysing `qs` code, you have learned:

* ctf cond `$[c;t;f]`
* monadic `?x distinct`
* monadic `#x count`
* monadic `rand x`
* monadic `=x group`
* monadic `,/x raze`
* dyadic `x@y index`

Also, at the end of the previous chapter you have seen:

* monadic `!x til (first x integers)`
* monadic `+x flip (transpose)`

Finally, for completeness sake:

* monadic `@x type`
* monadic `^x sort`

Although this is still a small part of k operator arsenal, you already have enough to do `quicksort` and a galaxy or other useful programs. Then add vector arithmetic, and then take everything to the power of 6 adverbs. We're not in Kansas anymore.

-------------------

**Checkpoint exercise:**

1. take another good look at the code of `qs` function
2. retrace the steps of the analysis we did together
3. in a new k session, try to reproduce `qs` from scratch

It sounds much harder than it really is. It might take more than one attempt, but you will be amazed how fast you will get there. However, before advancing to the next chapter, make sure that you **do** get there.

-------------------
