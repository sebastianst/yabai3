# yabai3

**yabai3** is an [i3](https://github.com/i3/i3) sanity wrapper around [yabai](https://github.com/koekeishiya/yabai).
It's a simple `zsh` script.

## Features

**yabai3** provides a few commands that imitates the way i3 behaves under the same action, but uses `yabai` to accomplish the intended effects.
In the following list of available commands, `<dir>` refers to any yabai direction `(north|west|east|south)`.

* `yabai3 focus <dir>` -- move focus to window or screen in the given direction. It also cycles through stacks.
* `yabai3 move <dir>` -- move focused window in the given direction.
  It enters and leaves stacks, and also moves to adjacent displays.
* `yabai3 fullscreen-toggle` -- toggle between `stack` and `bsp` display layout, imitating i3's fullscreen toggle behavior.
* `yabai3 resize (shrink|grow) (width|height) <px>` -- shrink/grow the width/height of the focused window by `<px>` pixels.
* `yabai3 stack-(enter|leave) <dir>` -- enter/leave a stack in the given direction with the focused window.
  These are also used internally in the `move` command, and can be used themselves for more specific stack management.

Most other i3 actions can be imitated close enough with existing `yabai` commands, so they aren't part of `yabai3` (yet).
The example `skhd` configuration below also uses plain `yabai` in these cases.
Note that **yabai3** is still young and work in progress, so more commands might be added in the future.

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
