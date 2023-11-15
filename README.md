# yabai3

**yabai3** is an [i3](https://github.com/i3/i3) sanity wrapper around [yabai](https://github.com/koekeishiya/yabai).
It's a simple `zsh` script.

## Usage

Create hotkey bindings just as you would for `yabai` itself, e.g. using [skhd](https://github.com/koekeishiya/skhd).

Opinionated and ready to use configuration examples for **yabai** and **skhd** that work with **yabai3** can be found in files [`yabairc`](./yabairc) and [`skhdrc`](./skhdrc).
They assume that the [`yabai3`](./yabai3) script is accessible somewhere on your `$PATH`.
You can replace `yabai3` invocations with an absolute path to the script if it's not.

They also assume that the alias
```sh
alias alacritty-new='alacritty msg create-window; open -a Alacritty'

```
is available to spawn a new [alacritty](https://github.com/alacritty/alacritty) window.
This alias ensures that a single alacritty app instances is reused for new windows and that any new window gets focused after creation.
Change it to your terminal of choice if you don't use alacritty.
