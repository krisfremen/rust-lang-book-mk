## Инсталација

Првиот чекор е да инсталирате Rust. Ќе ја преземеме најновата верзија на Rust преку `rustup`,
алатка во командна линија за управување со верзии на Rust и придружни алатки. Ќе ви треба
интернет конекција за преземањето на верзијата.

> Note: If you prefer not to use `rustup` for some reason, please see the
> [Other Rust Installation Methods page][install] for more options.

[install]: https://forge.rust-lang.org/infra/other-installation-methods.html

Следните чекори ја инсталираат најновата стабилна верзија на компајлерот Rust.
Стабилноста на Rust гарантира дека сите примери во книгата тоа
компајлирањето ќе продолжи да се компајлира со поновите верзии на Rust. Излезот може
малку се разликуваат помеѓу верзиите, бидејќи Rust често ги подобрува пораките за грешка
и предупредувања. Со други зборови, секоја понова, стабилна верзија на Rust што ја инсталирате
користењето на овие чекори треба да работи како што се очекува со содржината на оваа книга.

> ### Command Line Notation
>
> In this chapter and throughout the book, we’ll show some commands used in the
> terminal. Lines that you should enter in a terminal all start with `$`. You
> don’t need to type in the `$` character; it indicates the start of each
> command. Lines that don’t start with `$` typically show the output of the
> previous command. Additionally, PowerShell-specific examples will use `>`
> rather than `$`.

### Инсталирање `rustup` на Linux или macOS

Ако користите Linux или macOS, отворете терминал и внесете ја следнава команда:

```console
$ curl --proto '=https' --tlsv1.2 https://sh.rustup.rs -sSf | sh
```

Командата презема скрипта и започнува со инсталација на алатката `rustup`, која 
ја инсталира најновата стабилна верзија на Rust. Можеби ќе бидете побарани да ја внесете
вашата лозинка. Ако инсталацијата е успешна, ќе се појави следната линија:

```text
Rust is installed now. Great!
```

Исто така, ќе ви треба поврзувач, што е програма што Rust ја користи за да се приклучи кон неа
компајлирани излези во една датотека. Најверојатно веќе имате еден. Ако добиете
грешки во линкерот, треба да инсталирате C компајлер, кој обично вклучува линкер.
C Компајлер е исто така корисен бидејќи некои вообичаени пакети Rust зависат од
C код и ќе треба C компајлер.

На macOS, можете да добиете C компајлер со следната команда:

```console
$ xcode-select --install
```

Корисниците на Linux генерално треба да инсталираат GCC или Clang, според
документацијата за дистрибуцијата што ја користите. На пример, ако користите Ubuntu,
можете да инсталирате пакетот `build-essential`.

### Installing `rustup` on Windows

On Windows, go to [https://www.rust-lang.org/tools/install][install] and follow
the instructions for installing Rust. At some point in the installation, you’ll
receive a message explaining that you’ll also need the C++ build tools for
Visual Studio 2013 or later. The easiest way to acquire the build tools is to
install [Build Tools for Visual Studio 2019][visualstudio]. When asked which
workloads to install make sure "C++ build tools" is selected and that the
Windows 10 SDK and the English language pack components are included.

[install]: https://www.rust-lang.org/tools/install
[visualstudio]: https://visualstudio.microsoft.com/visual-cpp-build-tools/

The rest of this book uses commands that work in both *cmd.exe* and PowerShell.
If there are specific differences, we’ll explain which to use.

### Updating and Uninstalling

After you’ve installed Rust via `rustup`, updating to the latest version is
easy. From your shell, run the following update script:

```console
$ rustup update
```

To uninstall Rust and `rustup`, run the following uninstall script from your
shell:

```console
$ rustup self uninstall
```

### Troubleshooting

To check whether you have Rust installed correctly, open a shell and enter this
line:

```console
$ rustc --version
```

You should see the version number, commit hash, and commit date for the latest
stable version that has been released in the following format:

```text
rustc x.y.z (abcabcabc yyyy-mm-dd)
```

If you see this information, you have installed Rust successfully! If you don’t
see this information and you’re on Windows, check that Rust is in your `%PATH%`
system variable. If that’s all correct and Rust still isn’t working, there are
a number of places you can get help. The easiest is the #beginners channel on
[the official Rust Discord][discord]. There, you can chat with other Rustaceans
(a silly nickname we call ourselves) who can help you out. Other great
resources include [the Users forum][users] and [Stack Overflow][stackoverflow].

[discord]: https://discord.gg/rust-lang
[users]: https://users.rust-lang.org/
[stackoverflow]: https://stackoverflow.com/questions/tagged/rust

### Local Documentation

The installation of Rust also includes a copy of the documentation locally, so
you can read it offline. Run `rustup doc` to open the local documentation in
your browser.

Any time a type or function is provided by the standard library and you’re not
sure what it does or how to use it, use the application programming interface
(API) documentation to find out!
