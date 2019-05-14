# kcc
a gentle introduction to k is elsewhere

## genesis

Computer languages have been around for a while, but in the beginning was the word. We will be writing code in a language called k, but it really helps to talk about it first.

Regardless your background, k will look different. You will question many aspects of its design, and it will respond by questioning things that you consider common sense, and this will be a constructive conversation. For example, you may find it puzzling why the assignment operator in k is `:` instead of `=`. But give it a chance and try a simple thought experiment. Consider the following code:

```java
x = x + 1
```

Most programmers and most computer languages will readily agree that this expression is perfectly valid, but don't be surprised if a mathematician tells you *"nonsense”*. And once you see what makes him think so, will see one of the reasons why we assign things with `:` in k.

This gives a good hint how to approach k in general: a different perspective is not necessarily wrong and hostile, and nothing prevents it from becoming your own, so keep an open mind.

This crash course is not looking to make you an expert k programmer, because that, as any area of expertise, takes a lot of time and effort. Allegedly, it is possible to teach oneself Java in 24 hours, but we are not qualified to talk about that. Instead, we are going to talk about fundamental aspects of *thinking in k*, and the curve is going to be steep — but we value your time, so we promise it will be fast and violent.

The document assumes general proficiency with programming concepts and terminology, and hence will cut a lot of corners at some expense of readability.

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

The k interpreter is currently available for `Linux` and `macOS` on `x86_64` architecture. If you are on Solaris, OpenBSD or z/OS — hang tight, good things come to those who wait. The same applies to `ARM` and `WASM` architectures, but if you are on Windows, well, lets not cry over spilled Guinness.

Without further ado, go to https://anaconda.org/ and follow the instructions. Anaconda shell integration option is highly recommended. Once you install Anaconda, install the package called  `shakti`, which is nothing else but `k` in disguise:

```sh
kelas@failbowl ~ $ conda install -c shaktidb shakti
```

As with all things k, the development of k language itself is happening at terrifying pace. New builds are usually published several times a week, so make sure you always use the latest version:

```sh
kelas@failbowl ~ $ conda update -c shaktidb shakti
```

### using k

Assuming conda's `bin` is in you PATH, start your first k session, ask your first question and enjoy your first answer:

```sh
kelas@failbowl ~ $ k
2019-04-21 15:38:18 40core 512gb avx2 © shakti m2.0 prod
 2+2
4
```

The startup banner packs a lot of useful information:

| it says             | it means                      |
| :-------------------|:------------------------------|
| 2019-04-21 15:38:18 | timestamp of your k build     |
| 40core              | cpu cores you can use         |
| 512gb               | max workspace, expect 1gb     |
| avx2                | best your cpu can do          |
| shakti              | the company behind k          |
| m                   | `m` for macos, `l` for linux  |
| 2.0                 | 2.0 is better than 1.0        |
| prod                | expect to see `test`          |

Once it comes to that, always include your banner in your bug reports.

At any time during k session, you can:

`\h` view k reference card

`\l` view k change log

`\\` quit k session

However, at this point we highly recommend to avoid issuing any of the above commands, especially the latter.

### remarks on style

As any other computer language, k expects a programmer to observe and follow certain conventions on coding style in order to understand the code written by the others and let their own code be understood. While some rules of the house of k are universal, some are not.

**Annotations** in your k code is the best way not to end up coding Java for food, unless you are Arthur Whitney. We dare to assume you are not there yet, so comments start with `/`. When used inline, prepend at least one space:

```q
/line comment
42

42 /inline comment
```

**Indentation** in k is a tricky subject. Basically, what you generally want is *no indentation*. This means if your k expression is getting so large that you are tempted to split it into separate lines, you either need to refactor, or your entire train of thought got derailed and you need to go back to the blackboard. Sometimes, however, indentation is fine and even necessary, and it is always *one space*. Not two, not four, one. Tabs will be frowned upon, because some day they will end up taking other people's precious screen real estate, and humans get really itchy when it comes to brick and mortar.

**Capitals** are used by k programmers very sparingly, as a last resort measure. This applies both to code and comments. Identifiers in `camelCase` are considered bad form but can sometimes be tolerated, while `c_style` identifiers are not permitted at all since underscore is a k operator. Identifiers of functions and variables are very often boiled down to an absolute minimum, names 1-3 characters long are commonplace, which does not impact readability and comprehension given that their definitions are adequately annotated. Short identifiers might sound like a bad idea to Java programmers who are not accustomed to identifiers shorter than 100 bytes, but a well-structured and well-formatted k program typically fits on a single screen and requires little or no scrolling. The way our brain works is when the entire program fits into your visual buffer, "cryptic" identifiers are no longer a problem, because their annotated declarations are always right in front of you, and it will take a while before you face the problem of switching between multiple k source files:

```q
kei:42 /kenneth eugene iverson
```

**Functions** in k are first-class citizens. k has lambdas, eval, apply, and then some more. It takes a leap of faith to believe it, but k is probably more lispy than certain Lisps, only you don't need to get past any parens to be able to read it. In a strict sense, though, since there are no linked lists under the hood, k is clearly not lisp, because it was designed to be fast.

Most languages require you to explicitly declare arguments of your function. You can also do that in k if you want to, but if you don't, a function can have up to three **implicit arguments** called `x`, `y` and `z`, which basically means you declare them by simply referencing them in the function body. It is an extremely convinient feature, not nearly as scary as it sounds:

```q
 f:{x+y+z}    /f[] takes three arguments
 f[1;2;3]     /and here is how to call f
6
  
 f:{x*x}      /f[] has only one argument
 f 2          /and you can omit brackets
4

 f f 2        /a nice way to say f[f[2]] 
16 
```

This illustrates a core principle of k syntax — everything that you intuitively feel you should be able to omit, can and should be omitted, and there very few exceptions to this rule. The lesser you type, the better your code will get.

Lets recap. So far you know how to start k, how to assign values, declare most basic functions and variables, and how to annotate your code. This is a good start, but tells you absolutely nothing about what k really is. Nowhere above you were promised a *gentle* introduction, so from here your best two friends are your intelligence and intuition.

## revelations

### vectors and atoms

The word `atom` is a synonym for `scalar value` or simply `scalar`. We have them in k, and they are as useful as everywhere. But k belongs to a family of *vector languages*, which basically means its fundamental type is an ordered set of atoms or other sets. In k parlance, terms "array", "list" and "vector" are used interchageably and refer to the same thing, but we will stick with `vector` to minimise confusion, because vectors are much more general than classic *arrays* and have nothing to do with *linked lists*. Besides, it is such a cool word.

```q
 a:(0,1,2,3,4)    /one way of declaring an integer vector
 b:0 1 2 3 4      /same result using more informal syntax

 a
0 1 2 3 4

 b
0 1 2 3 4
```

The first enlightening fact about vectors is that most operations you expect to work for atoms work equally well for vectors, too:

```q
 a-b             /pairwise substraction
0 0 0 0 0 

 a%b             /pairwise divison (yes, division in k is %, and ø means nil, nan, void and other bad news)
ø 1 1 1 1

 a=b             /pairwise comparison (1 means truthy)
1 1 1 1 1 

 a*a             /don't get mad, get even
0 2 4 6 8
```

Mixing atomic and vector operands is perfectly fine:

```q
 a+1             /increment each of a
1 2 3 4 5 

 a=1             /compare each of a to 1
0 1 0 0 0

 a%0             /divide each of a by 0 (correct, ℚ%0 is ∞ except 0%0 which is ø, enjoy responsibly)
ø ∞ ∞ ∞ ∞

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

**Indexing** is zero-based as you would expect, but there are pleasant surprises:

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

Seeing is believing, but before you see some examples, the first thing you need to know about types in k is that they are divided into two broad classes: **vector types** and **atomic types**. That is, a vector with a single element, say, `42`, is not the same type as atomic integer of the same value. Finally, since functions and other things in k are assignable values, they have their place in the type system too. Those are **special types** and we will not cover them here.

The operator to obtain the type of something is `@`.

```q
 @42         /int atom
`i

 @.5         /float atom
`f

 @0 1 2      /int vector
`I

 v:0 1 .5 2
 @v          /float vector (0.5 promotes all neighbors and the vector itself to float)
`F

 v 1         /2nd element is a float, hinted by the trailing f
1f

 @v 1        /just making sure
`f
```

Like in C, there is no dedicated type for strings in k. Strings are just **char vectors**:

```q
 @"k"        /char atom
`c

 @"kei"      /char vector
`C
```

However, k has something C doesn't. We have a type called **name**, which is the same concept as **internalized string** found in some other languages. This means that a single instance of an arbitrarily long string can be placed into a global hash table that persists for a lifetime of a k process and can later be referenced by its hash key as many times as necessary without creating additional copies of that string. As you will discover later, names come very handy in a lot of situations, but for now lets just see how they quack:

```q
 a:`kei              /the string "kei" is now internalized
 @a                  /name atom
`n

 b:`kei`kei`kei      /three references to a single internalized instance of "kei"
 @b                  /vector of names
`N

 @`"ken iverson"     /no problem to have spaces in names
`n
```

**Temporal types** in k are `date` and `time`:

```q
 d:1981-02-01        /yyyy-mm-dd
 @d                  /atomic date type is special, it is a capital D, same as the date vector
`D

 t:12:34:56.789      /hh:mm:ss.sss
 @t
`t
```

Of special mention is the **composite vector** type. Such vectors are either a mixture of atoms of disparate types, or contain something more complex than atoms, e.g. other vectors.

```q
 a:0,1,"a",2,3          /a char impostor demotes this integer vector to composite
 @a                     /a composite type is denoted by a backtick
`

 a:(1 2 3;4 5 6;7 8 9)  /vector of vectors is a composite
 a
1 2 3
4 5 6
7 8 9
 @a
`

 a:{x},{x+x},{x*x}      /a vector of lambdas, sure, why not
 @a
`
```

**Casting**, both explicit and implicit, is demonstrated by the following examples which also give a general feel of how type coersion behaves:

```q
 1+.5                  /int plus float is float, no surprises here
1.5

 1f*2                  /1f is the same as 1.0
2f 

 `i$42.99              /explicit cast float to int discards mantissa, aka floor
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
 @a                    /ouch, the vector got demoted to composite:
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

It could not escape your attention that the notation for indexing vectors and calling functions is identical:

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
You also know that k actively encourages you to omit brackets whenever possible. Lets do exactly that:

```q
 f d i        /same as f[d[i]]
4 32
```

This tiny example reveals an astonishing truth. Once we drop the brackets, it suddenly becomes absolutely natural to read this expression *from right to left*. Take your time to contemplate and process this statement. In very little time you will see how it works in practice, and once you put it to practice yourself, you will see that this way of functional composition is beautiful, elegant and intuituve.

**Reading and writing k expressions is done right to left.**

Now that we know which way the rivers flow in k land, we are ready to discuss a related, no less important subject.

Precedence in k obeys different laws compared to those we were taught in primary school. We take it for granted that multiplication and division bind stronger than addition and substraction, and it almost feels natural that computer languages must have very complex precedence hierarchies in order to be useful. That is not the case with k.

**There is no operator precedence in k unless explicitly defined by round brackets.**

That is, by default all operations in a k expression are treated equally and evaluated strictly from right to left. Lets see how this works:

```q
 3+2+1        /take 1, add 2, add 3
6

 3*2+1        /take 1, add 2, multiply by 3
9

 (3*2)+1      /take 2, multiply by 3, add 1
7

 1+3*2        /same as above, without parens
7
```

Once you get over the death of precedence, you will also want to avoid using parens unless you absolutely have to. The last example above shows the basic strategy of avoiding them: it is usually possible to rearrange the order of execution to make it linear. Although overriding precedence is often inevitable and can be beneficial, it has an adverse effect on readability as it breaks the natural flow of code comprehension which otherwise goes from right to left, uninterrupted.

### no stinking loops

### how to solve it







