# zsh-autosuggestions

_[Fish](http://u.720life.cn/g/ee3547b3e27c4dfb4f0d934e93626b525b6b534ceb38387dd234bc0c8dd7be0f)-like fast/unobtrusive autosuggestions for zsh._

It suggests commands as you type, based on command history.

[![CircleCI](https://circleci.com/gh/zsh-users/zsh-autosuggestions.svg?style=svg)](https://circleci.com/gh/zsh-users/zsh-autosuggestions)

   


## Installation

Requirements: Zsh v4.3.11 or later

### Manual

1. Clone this repository somewhere on your machine. This guide will assume `~/.zsh/zsh-autosuggestions`.

    ```sh
    git clone https://github.com/zsh-users/zsh-autosuggestions ~/.zsh/zsh-autosuggestions
    ```

2. Add the following to your `.zshrc`:

    ```sh
    source ~/.zsh/zsh-autosuggestions/zsh-autosuggestions.zsh
    ```

3. Start a new terminal session.


### Oh My Zsh

1. Clone this repository into `$ZSH_CUSTOM/plugins` (by default `~/.oh-my-zsh/custom/plugins`)

    ```sh
    git clone https://github.com/zsh-users/zsh-autosuggestions $ZSH_CUSTOM/plugins/zsh-autosuggestions
    ```

2. Add the plugin to the list of plugins for Oh My Zsh to load:

    ```sh
    plugins=(zsh-autosuggestions)
    ```

3. Start a new terminal session.

### Arch Linux via the AUR
1. Install the [`zsh-autosuggestions`](http://u.720life.cn/g/5615fdc361700551bb11c27e3ee88cb37d6b3406ae1ca466d10bbc6e99ffa776284762bcc1d73f99a19455b1860a4c6dc8bbc0fe80386f3b174435c497820feb) or the [`zsh-autosuggestions-git`](http://u.720life.cn/g/5615fdc361700551bb11c27e3ee88cb37d6b3406ae1ca466d10bbc6e99ffa776284762bcc1d73f99a19455b1860a4c6d168e18cfe3bc7d9e0df77895dd324dfd) packages from the [AUR](http://u.720life.cn/g/6026bad56c497e34927d12c7600ceb9853b2454a53a427516a0f11f8d05f82cd5f4a2167e9773605221f6e76290d8a67ed2d692ff9d506f1ecbe17592d4a4622).

    ```sh
    pacaur -S zsh-autosuggestions
    ```
    or
    ```
    pacaur -S zsh-autosuggestions-git
    ```

2. Add the following to your `.zshrc`:

    ```sh
    source /usr/share/zsh/plugins/zsh-autosuggestions/zsh-autosuggestions.zsh
    ```

3. Start a new terminal session.

### macOS via Homebrew
1. Install the `zsh-autosuggestions` package using [Homebrew](http://u.720life.cn/g/2c75a511bea1268ab8a6d5aafe5f0839).

    ```sh
    brew install zsh-autosuggestions
    ```

2. Add the following to your `.zshrc`:

    ```sh
    source /usr/local/share/zsh-autosuggestions/zsh-autosuggestions.zsh
    ```

3. Start a new terminal session.

## Usage

As you type commands, you will see a completion offered after the cursor in a muted gray color. This color can be changed by setting the `ZSH_AUTOSUGGEST_HIGHLIGHT_STYLE` variable. See [configuration](#configuration).

If you press the  →  key (`forward-char` widget) or  End  (`end-of-line` widget) with the cursor at the end of the buffer, it will accept the suggestion, replacing the contents of the command line buffer with the suggestion.

If you invoke the `forward-word` widget, it will partially accept the suggestion up to the point that the cursor moves to.


## Configuration

You may want to override the default global config variables after sourcing the plugin. Default values of these variables can be found [here](src/config.zsh).

**Note:** If you are using Oh My Zsh, you can put this configuration in a file in the `$ZSH_CUSTOM` directory. See their comments on [overriding internals](http://u.720life.cn/g/54145d0471d91890860f7f8463c030469ac7ef31ba738b602c2effb94ee5a81b79b185983ef2334eaa3b782560414747aa8f7d5f9e38122fc516918f310beb0156d07138bd09e1ac5fa400f4a9c301fd2294620d942813b3a63d68f512f0ba6d).


### Suggestion Highlight Style

Set `ZSH_AUTOSUGGEST_HIGHLIGHT_STYLE` to configure the style that the suggestion is shown with. The default is `fg=8`.


### Suggestion Strategy

Set `ZSH_AUTOSUGGEST_STRATEGY` to choose the strategy for generating suggestions. There are currently two to choose from:

- `default`: Chooses the most recent match.
- `match_prev_cmd`: Chooses the most recent match whose preceding history item matches the most recently executed command ([more info](src/strategies/match_prev_cmd.zsh)). Note that this strategy won't work as expected with ZSH options that don't preserve the history order such as `HIST_IGNORE_ALL_DUPS` or `HIST_EXPIRE_DUPS_FIRST`.


### Widget Mapping

This plugin works by triggering custom behavior when certain [zle widgets](http://u.720life.cn/g/67a8de3ad1174a379d5a4d9938b4f7388bb71fa0a231d28093bbda65165e3c25c631426dd235f46d11bfb2b0a7f7371fb7d9d8a9c01885356841396dc48349164b5b11927db37bca5b5052ab4905fa6e) are invoked. You can add and remove widgets from these arrays to change the behavior of this plugin:

- `ZSH_AUTOSUGGEST_CLEAR_WIDGETS`: Widgets in this array will clear the suggestion when invoked.
- `ZSH_AUTOSUGGEST_ACCEPT_WIDGETS`: Widgets in this array will accept the suggestion when invoked.
- `ZSH_AUTOSUGGEST_EXECUTE_WIDGETS`: Widgets in this array will execute the suggestion when invoked.
- `ZSH_AUTOSUGGEST_PARTIAL_ACCEPT_WIDGETS`: Widgets in this array will partially accept the suggestion when invoked.
- `ZSH_AUTOSUGGEST_IGNORE_WIDGETS`: Widgets in this array will not trigger any custom behavior.

Widgets that modify the buffer and are not found in any of these arrays will fetch a new suggestion after they are invoked.

**Note:** A widget shouldn't belong to more than one of the above arrays.


### Disabling suggestion for large buffers

Set `ZSH_AUTOSUGGEST_BUFFER_MAX_SIZE` to an integer value to disable autosuggestion for large buffers. The default is unset, which means that autosuggestion will be tried for any buffer size. Recommended value is 20.
This can be useful when pasting large amount of text in the terminal, to avoid triggering autosuggestion for too long strings.

### Enable Asynchronous Mode

As of `v0.4.0`, suggestions can be fetched asynchronously using the `zsh/zpty` module. To enable this behavior, set the `ZSH_AUTOSUGGEST_USE_ASYNC` variable (it can be set to anything).


### Key Bindings

This plugin provides a few widgets that you can use with `bindkey`:

1. `autosuggest-accept`: Accepts the current suggestion.
2. `autosuggest-execute`: Accepts and executes the current suggestion.
3. `autosuggest-clear`: Clears the current suggestion.
4. `autosuggest-fetch`: Fetches a suggestion (works even when suggestions are disabled).
5. `autosuggest-disable`: Disables suggestions.
6. `autosuggest-enable`: Re-enables suggestions.
7. `autosuggest-toggle`: Toggles between enabled/disabled suggestions.

For example, this would bind  ctrl  +  space  to accept the current suggestion.

```sh
bindkey '^ ' autosuggest-accept
```


## Troubleshooting

If you have a problem, please search through [the list of issues on GitHub](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046d717e8abbf367bd906a6545870b6b4d9f13d8cc4041ce6eb0c42e305560c2293f00d6f46b8ca909e0747e17165730427) to see if someone else has already reported it.


### Reporting an Issue

Before reporting an issue, please try temporarily disabling sections of your configuration and other plugins that may be conflicting with this plugin to isolate the problem.

When reporting an issue, please include:

- The smallest, simplest `.zshrc` configuration that will reproduce the problem. See [this comment](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046d717e8abbf367bd906a6545870b6b4d9f13d8cc4041ce6eb0c42e305560c2293aedc4dcc3e50f94c3ca14a56d4ba4cfa6ad4da5beca8260f1366b46895f5cee83f4775d1fbc54c1ced39baf47d690fb2) for a good example of what this means.
- The version of zsh you're using (`zsh --version`)
- Which operating system you're running


## Uninstallation

1. Remove the code referencing this plugin from `~/.zshrc`.

2. Remove the git repository from your hard drive

    ```sh
    rm -rf ~/.zsh/zsh-autosuggestions # Or wherever you installed
    ```


## Development

### Build Process

Edit the source files in `src/`. Run `make` to build `zsh-autosuggestions.zsh` from those source files.


### Pull Requests

Pull requests are welcome! If you send a pull request, please:

- Request to merge into the `develop` branch (*NOT* `master`)
- Match the existing coding conventions.
- Include helpful comments to keep the barrier-to-entry low for people new to the project.
- Write tests that cover your code as much as possible.


### Testing

Tests are written in ruby using the [`rspec`](http://u.720life.cn/g/3b525232b5a87f8a4dcf7a52f55b5a417b884a462ff4a636fc015127670b33f6) framework. They use [`tmux`](http://u.720life.cn/g/1ed354543afcccab20b664ccf0785df0901af3e5b659bafd7150494ed0fcf704) to drive a pseudoterminal, sending simulated keystrokes and making assertions on the terminal content.

Test files live in `spec/`. To run the tests, run `make test`. To run a specific test, run `TESTS=spec/some_spec.rb make test`. You can also specify a `zsh` binary to use by setting the `TEST_ZSH_BIN` environment variable (ex: `TEST_ZSH_BIN=/bin/zsh make test`).


## License

This project is licensed under [MIT license](http://u.720life.cn/g/ba059582536a397f7c573b87c8bea647045b0ef049248233b6f76e909e70200fe7048b25e29c8bab79aeff32ea74556a).
For the full text of the license, see the [LICENSE](LICENSE) file.



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e152d895b317f4c191a3764fd2a9c631b488f04c7ff4029009885879e687c8d76eb4ce0e036bec4e199c36ea774dd0f32ea456ce26c931e0892dbc1a5cd4fe107)