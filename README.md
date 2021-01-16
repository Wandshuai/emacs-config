# emacs-config

## May the emacs force be with you

I forked [doom emacs](https://github.com/hlissner/doom-emacs), this is a cool emacs framework.

### install emacs

You can download the installation package directly from the [official website](https://www.gnu.org/software/emacs/). I prefer to build emacs myself. Referring to the [Emacs Wiki](https://www.emacswiki.org/emacs/BuildingEmacs).

### install doom emacs

[doom emacs github repo](https://github.com/hlissner/doom-emacs)

```
git clone --depth 1 https://github.com/hlissner/doom-emacs ~/.emacs.d
~/.emacs.d/bin/doom install
```

Checking Doom Emacs

```
~/.emacs.d/bin/doom doctor
```

You may need install `fd` and `ripgrep`  to search faster in you project.

First of all make sure `export PATH=~/.local/bin:$PATH` in your `~/.bashrc`

```
cd ~/tools
wget https://github.com/sharkdp/fd/releases/download/v8.2.1/fd-v8.2.1-x86_64-unknown-linux-gnu.tar.gz
tar xf fd-v8.2.1-x86_64-unknown-linux-gnu.tar.gz
wget https://github.com/BurntSushi/ripgrep/releases/download/12.1.1/ripgrep-12.1.1-x86_64-unknown-linux-musl.tar.gz
tar xf ripgrep-12.1.1-x86_64-unknown-linux-musl.tar.gz
mkdir -p ~/.local/bin
cp fd-v8.2.1-x86_64-unknown-linux-gnu/fd ~/.local/bin/.
cp ripgrep-12.1.1-x86_64-unknown-linux-musl/rg ~/.local/bin/.
rm fd-v8.2.1-x86_64-unknown-linux-gnu.tar.gz ripgrep-12.1.1-x86_64-unknown-linux-musl.tar.gz
cd ~

```



### configure your LSP server

I usually use C family language，so i use `lsp+ccls` .Of course you can configure it to be someone else.

first we need to install [ccls](https://github.com/MaskRay/ccls)

```
cd ~/repo
git clone --depth=1 --recursive https://github.com/MaskRay/ccls
cd ccls
wget -c http://releases.llvm.org/8.0.0/clang+llvm-8.0.0-x86_64-linux-gnu-ubuntu-18.04.tar.xz
tar xf clang+llvm-8.0.0-x86_64-linux-gnu-ubuntu-18.04.tar.xz
cmake -H. -BRelease -DCMAKE_BUILD_TYPE=Release -DCMAKE_PREFIX_PATH=$PWD/clang+llvm-8.0.0-x86_64-linux-gnu-ubuntu-18.04
cmake --build Release
cp Release/ccls ~/.local/bin/.
cd ~
```
