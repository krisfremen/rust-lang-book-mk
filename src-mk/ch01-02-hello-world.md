## Здраво свет!

Сега кога го имате Rust инсталиран, ајде да ја напишеме вашата прва програма во Rust.
Традиционално е кога се учи нов јазик да се напише мала програма што го печати
текстот `Здраво, свет!` на екранот, па истото ќе го направиме и овде!

> Note: This book assumes basic familiarity with the command line. Rust makes
> no specific demands about your editing or tooling or where your code lives, so
> if you prefer to use an integrated development environment (IDE) instead of
> the command line, feel free to use your favorite IDE. Many IDEs now have some
> degree of Rust support; check the IDE’s documentation for details. Recently,
> the Rust team has been focusing on enabling great IDE support, and progress
> has been made rapidly on that front!

### Креирање директориум за проекти

Ќе започнеме со правење директориум за чување на вашиот Rust код. Не е важно
na Руст каде e вашиот код, но за вежбите и проектите во оваа книга,
предлагаме да направите директориум *проекти* во вашиот домашен директориум и да ги чувате сите
ваши проекти таму.

Отворете терминал и внесете ги следниве команди за да направите директориум *проекти*
и директориум за "Здраво, свет!" проектот во директориумот *проекти*.

За Linux, macOS и PowerShell на Windows, внесете го ова:

```console
$ mkdir ~/projects
$ cd ~/projects
$ mkdir hello_world
$ cd hello_world
```

За Windows CMD, внесете го ова:

```cmd
> mkdir "%USERPROFILE%\projects"
> cd /d "%USERPROFILE%\projects"
> mkdir hello_world
> cd hello_world
```

### Пишување и извршување на Rust програма

Следно, направете нов изворен фајл и наречете фо *main.rs*. Фајловите за Rust секогаш завршуваат со
екстензијата *.rs*. Ако користите повеќе од еден збор во вашето име на датотека, користете
_ (подцрта) за да ги разделиме. На пример, користете *hello_world.rs* наместо
*helloworld.rs*.

Сега отворете го фајлот *main.rs* што го создадовте и внесете го кодот во Листа 1-1.

<span class="filename">Фајл: main.rs</span>

```rust
fn main() {
    println!("Здраво, свет!");
}
```

<span class="caption">Листа 1-1: Програма што отпечатува `Здраво, свет!`</span>

Зачувајте ја датотеката и вратете се во терминалот. На Linux или macOS, внесете
ги следниве команди за составување и стартување на фајлот:

```console
$ rustc main.rs
$ ./main
Здраво, свет!
```

На Windows, внесете ја командата `.\мain.exe` наместо`./мain`:

```powershell
> rustc main.rs
> .\main.exe
Здраво, свет!
```

Без оглед на вашиот оперативен систем, `Здраво, свет!` треба да се отпечати на
терминалот. Ако не го гледате овој излез, вратете се назад на
[„Решавање проблеми“][troubleshooting]<!-ignore-> делот од инсталацијата
за начини како да добиете помош.

Ако „Здраво, свет!“ се отпечати, честитки! Официјално напишавте Rust
програма. Тоа ве прави Rust програмер - добредојдовте!

### Anatomy of a Rust Program

Let’s review in detail what just happened in your “Hello, world!” program.
Here’s the first piece of the puzzle:

```rust
fn main() {

}
```

Овие линии дефинираат функција во Rust. Функцијата `main` е посебна: тоа е
секогаш првиот код што работи во секоја извршена Rust програма. Првата
линија декларира функција наречена `main` која нема параметри и враќа
ништо. Ако има параметри, тие ќе влезат во заградата, `()`.

Исто така, имајте предвид дека телото на функцијата е завиткано во кадрави загради, `{}`. Rust
ги бара овие околу сите функционални тела. Добар стил е да го поставите отворната
кадрава заграда на иста линија со декларацијата на функцијата, додавајќи еден простор
помеѓу.

Ако сакате да се држите до стандардниот стил во проектите на Rust, можете да ja користите 
алатката за автоматско форматирање наречена `rustfmt` за форматирање на вашиот код во одреден
стил. Тимот на Rust ја вклучи оваа алатка со стандардната дистрибуција на Rust,
како `rustc`, така што би требало да е веќе инсталирана на вашиот компјутер! Проверете во
онлајн документацијата за повеќе детали.

Внатре во функцијата `main` е следниот код:

```rust
    println!("Здраво, свет!");
```

Оваа линија ја извршува целата работа во оваа мала програма: печати текст на
екран. Има четири важни детали што треба да се забележат овде.

Прво, стилот на Rust е да се повлече со четири празни места, а не со јазиче(tab).

Второ, `println!` повикува Rust макро. Ако наместо тоа повика функција, тоа
ќе се внесе како `println` (без `!`). ќе разговараме за Rust макроа
подетално во Поглавје 19. Засега, само треба да знаете дека користејќи `!`
значи дека повикувате макро наместо нормална функција, и тие макроа
не ги почитуваат секогаш истите правила како функциите.

Трето, ја гледате низата „Здраво, свет!“. Ја пренесуваме оваа низа како аргумент
на `println!`, и низата се печати на екранот.

Четврто, ја завршуваме линијата со точка-запирка(`;`), што покажува дека овој израz е
завршен и следниот е подготвен да започне. Повеќето линии на Rust код
завршуваат со точка-запирка.

### Компајлирање и извршувањето се одвоени чекори

Штотуку ја извршивте новосоздадената програма, па да го испитаме секој чекор во овој процес.

Пред да ја извршите програмата, мора да ја компајлирате со помош на компајлерот Rust при
внесување на командата `rustc` и на името на вашиот изворен фајл, како
следнава линија:

```console
$ rustc main.rs
```

Ако имате позадина C или C ++, ќе забележите дека ова е слично на `gcc`
или `clang`. По успешното компајлирање, Rust дава бинарен фајл што може да се изврши.

На Linux, macOS и PowerShell на Windows, можете да ги видите извршните фајлови при
внесување на командата `ls` во вашиот шел. На Linux и macOS, ќе видите два
фајла. Со PowerShell на Windows, ќе ги видите истите три фајлови при користење на CMD.

```console
$ ls
main  main.rs
```

Со CMD на Windows, би го внеле следново:

```cmd
> dir /B %= the /B option says to only show the file names =%
main.exe
main.pdb
main.rs
```

Ова го покажува изворниот фајл со наставката *.rs*, извршен фајл
(*main.exe* на Windows, но *main* на сите други платформи), и кога се користи
Windows, фајлот што содржи информации за дебагирање завршува со наставката *.pdb*.
Оттука, го извршувате фајлот *main* или *main.exe*, вака:

```console
$ ./main # or .\main.exe on Windows
```

Ако *main.rs* беше вашиот „Здраво, свет!“ програма, оваа линија ќе отпечати `Здраво,
свет! ` во вашиот терминал.

Ако сте повеќе запознаени со динамичен јазик, како што се Ruby, Python или
JavaScript, можеби не сте навикнати да составувате и извршувате програма како
одделни чекори. Rust е јазик компајлиран *однапред-време*, што значи дека можете
да ја компајлирате програмата и да ја дадете на некого, и тие можат да ја извршат
дури и без инсталирање на Rust. Ако на некого дадете *.rb*, *.py*, или
*.js* датотека, тие треба да имаат имплементација Ruby, Python или JavaScript
инсталиран (соодветно). Но, на тие јазици, ви треба само една команда
да ја компајлирате и стартувате вашата програма. Се е компромис во јазичен дизајн.

Само компајлирање со `rustc` е во ред за едноставни програми, но како вашот проект
расте, ќе сакате да управувате со сите опции и да го олесните споделувањето на вашите
код. Следно, ќе ве запознаеме со алатката Cargo, која ќе ви помогне да напишете
реални програми во Rust.
[troubleshooting]: ch01-01-installation.html#troubleshooting
