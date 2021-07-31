# Воведување

Добредојдовте на *Програмскиот јазик Rust*, воведна книга за Rust.
Програмскиот јазик Rust ви помага да напишете побрз, посигурен софтвер.
Ергономијата на високо ниво и контролата на ниско ниво честопати се во спротивност во програмирањето
дизајн на јазик; Rust го предизвикува тој конфликт. Преку балансирање моќни
технички капацитет и одлично искуство со развивач, Rust ви дава опција
да контролирате детали од ниско ниво (како што е користењето меморија) без сите проблеми
традиционално поврзани со таква контрола.

## За кого е Rust

Rust е идеален за многу луѓе за различни причини. Ајде да погледнеме на неколку од
најважните групи.

### Тимови на развивачи

Rust се покажува како продуктивна алатка за соработка меѓу големите тимови на
програмери со различно ниво на знаење за системи за програмирање. Код на ниско ниво
е склон кон различни суптилни грешки, што може да биде и на повеќето други јазици
фатени само преку екстензивно тестирање и внимателен преглед на код од искусни
програмери. Во Rust, компајлерот игра улога на чувар одбивајќи да
компајлирате код со овие недофатливи грешки, вклучително и конкурентни грешки. Работејќи
заедно со компајлерот, тимот може да го помине своето време фокусирајќи се на програмата
логика отколку да бркаат бубачки.

Rust исто така носи современи алатки за развивачи во светот на програмирање системи:

* Cargo, вклучениот менаџер за зависности и алатка за градење, прави додавање,
  составување и управување со зависности безболно и конзистентно низ екосистем на
  Rust.
* Rustfmt обезбедува конзистентен стил на кодирање помеѓу развивачите.
* Серверот за јазици на Rust ја овластува Интегрираната развојна средина (ИДЕ)
  интеграција за комплетирање на код и вградени пораки за грешки.

Со користење на овие и други алатки во екосистемот на Rust, програмерите можат да бидат
продуктивни додека пишуваат кодови на ниво на системи.

### Студенти

Rust е за студентите и оние кои се заинтересирани да научат за системите
концепти. Користејќи Rust, многу луѓе научија за теми како работење
развој на системи. Заедницата е многу добредојдена и среќна да одговори
студентски прашања. Преку напори како што е оваа книга, тимовите на Rust сакаат
да ги направат концептите на системите подостапни за повеќе луѓе, особено оние што се нови
програмирање.

### Компании

Стотици компании, големи и мали, користат Rust во производството за различни
задачи. Тие задачи вклучуваат алатки за командна линија, веб-сервиси, алатки за DevOps,
вградени уреди, аудио и видео анализа и транскодирање, криптовалути,
биоинформатика, пребарувачи, апликации за Интернет на нештата, машинско
учење, па дури и главни делови од веб-прелистувачот Firefox.

### Програмери со отворен код

Rust е за луѓе кои сакаат да го изградат програмскиот јазик Rust, заедница,
алатки за развивачи и библиотеки. Би сакале да ве поканиме да придонесете на Rust
јазикот.

### Луѓе кои ја ценат брзината и стабилноста

Rust е за луѓе кои копнеат за брзина и стабилност на јазик. Со брзина, ние
значи брзина на програми што можете да ги креирате со Rust и брзина на
што Rust ви дозволува да ги напишете. Проверките на компајлерот Rust обезбедуваат стабилност
преку дополнувања на карактеристики и рефакторирање. Ова е спротивно на кршливото
наследен код на јазици без овие проверки, кои програмерите често ги прават
се плаши да модифицира. Со стремеж кон апстракции со нула цена, карактеристики на повисоко ниво
кои се компајлираат со код од пониско ниво исто толку брзо како и кодот напишан рачно, Rust
настојува да се направи безбеден код да биде и брз код.

Јазикот Rust се надева дека ќе поддржи и многу други корисници; споменатите
тука се само некои од најголемите засегнати страни. Генерално, најголемата амбиција на Rust
е да се елиминираат компромисите за кои програмерите се согласија
децении со обезбедување на безбедност *и* продуктивност, брзина *и* ергономија. Дај
пробајте и проверете дали изборот ви одговара.

## Who This Book Is For

This book assumes that you’ve written code in another programming language but
doesn’t make any assumptions about which one. We’ve tried to make the material
broadly accessible to those from a wide variety of programming backgrounds. We
don’t spend a lot of time talking about what programming *is* or how to think
about it. If you’re entirely new to programming, you would be better served by
reading a book that specifically provides an introduction to programming.

## How to Use This Book

In general, this book assumes that you’re reading it in sequence from front to
back. Later chapters build on concepts in earlier chapters, and earlier
chapters might not delve into details on a topic; we typically revisit the
topic in a later chapter.

You’ll find two kinds of chapters in this book: concept chapters and project
chapters. In concept chapters, you’ll learn about an aspect of Rust. In project
chapters, we’ll build small programs together, applying what you’ve learned so
far. Chapters 2, 12, and 20 are project chapters; the rest are concept chapters.

Chapter 1 explains how to install Rust, how to write a “Hello, world!” program,
and how to use Cargo, Rust’s package manager and build tool. Chapter 2 is a
hands-on introduction to the Rust language. Here we cover concepts at a high
level, and later chapters will provide additional detail. If you want to get
your hands dirty right away, Chapter 2 is the place for that. At first, you
might even want to skip Chapter 3, which covers Rust features similar to those
of other programming languages, and head straight to Chapter 4 to learn about
Rust’s ownership system. However, if you’re a particularly meticulous learner
who prefers to learn every detail before moving on to the next, you might want
to skip Chapter 2 and go straight to Chapter 3, returning to Chapter 2 when
you’d like to work on a project applying the details you’ve learned.

Chapter 5 discusses structs and methods, and Chapter 6 covers enums, `match`
expressions, and the `if let` control flow construct. You’ll use structs and
enums to make custom types in Rust.

In Chapter 7, you’ll learn about Rust’s module system and about privacy rules
for organizing your code and its public Application Programming Interface
(API). Chapter 8 discusses some common collection data structures that the
standard library provides, such as vectors, strings, and hash maps. Chapter 9
explores Rust’s error-handling philosophy and techniques.

Chapter 10 digs into generics, traits, and lifetimes, which give you the power
to define code that applies to multiple types. Chapter 11 is all about testing,
which even with Rust’s safety guarantees is necessary to ensure your program’s
logic is correct. In Chapter 12, we’ll build our own implementation of a subset
of functionality from the `grep` command line tool that searches for text
within files. For this, we’ll use many of the concepts we discussed in the
previous chapters.

Chapter 13 explores closures and iterators: features of Rust that come from
functional programming languages. In Chapter 14, we’ll examine Cargo in more
depth and talk about best practices for sharing your libraries with others.
Chapter 15 discusses smart pointers that the standard library provides and the
traits that enable their functionality.

In Chapter 16, we’ll walk through different models of concurrent programming
and talk about how Rust helps you to program in multiple threads fearlessly.
Chapter 17 looks at how Rust idioms compare to object-oriented programming
principles you might be familiar with.

Chapter 18 is a reference on patterns and pattern matching, which are powerful
ways of expressing ideas throughout Rust programs. Chapter 19 contains a
smorgasbord of advanced topics of interest, including unsafe Rust, macros, and
more about lifetimes, traits, types, functions, and closures.

In Chapter 20, we’ll complete a project in which we’ll implement a low-level
multithreaded web server!

Finally, some appendices contain useful information about the language in a
more reference-like format. Appendix A covers Rust’s keywords, Appendix B
covers Rust’s operators and symbols, Appendix C covers derivable traits
provided by the standard library, Appendix D covers some useful development
tools, and Appendix E explains Rust editions.

There is no wrong way to read this book: if you want to skip ahead, go for it!
You might have to jump back to earlier chapters if you experience any
confusion. But do whatever works for you.

<span id="ferris"></span>

An important part of the process of learning Rust is learning how to read the
error messages the compiler displays: these will guide you toward working code.
As such, we’ll provide many examples that don’t compile along with the error
message the compiler will show you in each situation. Know that if you enter
and run a random example, it may not compile! Make sure you read the
surrounding text to see whether the example you’re trying to run is meant to
error. Ferris will also help you distinguish code that isn’t meant to work:

| Ferris                                                                                                           | Meaning                                          |
|------------------------------------------------------------------------------------------------------------------|--------------------------------------------------|
| <img src="img/ferris/does_not_compile.svg" class="ferris-explain" alt="Ferris with a question mark"/>            | This code does not compile!                      |
| <img src="img/ferris/panics.svg" class="ferris-explain" alt="Ferris throwing up their hands"/>                   | This code panics!                                |
| <img src="img/ferris/not_desired_behavior.svg" class="ferris-explain" alt="Ferris with one claw up, shrugging"/> | This code does not produce the desired behavior. |

In most situations, we’ll lead you to the correct version of any code that
doesn’t compile.

## Source Code

The source files from which this book is generated can be found on
[GitHub][book].

[book]: https://github.com/rust-lang/book/tree/master/src
