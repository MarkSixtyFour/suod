# suod
Do you type fast but also inaccurately? Don't you wish you wouldn't have to change `suod` to `sudo` and it would *Just Work*™? Do you need a little giggle to let you know your typing was a bit off? Well this tiny script does all of that!

`suod` is inspired by `sudo`'s own "insults" option, which insults you for typing your password incorrectly. I was thinking, "What if you were insulted for typing `sudo` wrong too?" I wrote the initial script pretty quickly, and now it can actually speed up your workflow a bit by providing a sort of "I know what you mean" for some commands.

### Why bother? This is such a simple program!
It is! Even being simple to write, it's even simpler to set up and use. Albeit simple, it does its job and saves you typing- you don't have to arrow-key upwards and fix the command or re-type it in. This is especially helpful with long commands that are cumbersome to correct, especially at the beginning. The command will *Just Work*™ as you intended it to so long as it's otherwise correct besides the `sudo` part- and now, optionally your package manager's name.

## Instructions
To install and get started with `suod`, you must be using Bash version 4 or higher as `suod` uses `declare -A` for associative arrays.

### Installation
Firstly, clone this repository and make sure the script is marked as executable:
```bash
git clone https://github.com/c-Vui/suod
cd suod
chmod +x suod.sh
```
If you want to use this to cover multiple misspellings of `sudo`, you can copy this script somewhere convenient and `alias` it in your `.bashrc` as needed:
```bash
alias suod=/path/to/suod.sh
alias sduo=/path/to/suod.sh
```
...or, if all you want is to have just one option like `suod`, then rename the script to `suod` and put it somewhere in your `$PATH` that's convenient to you.

### Correcting package manager names
By default, fixing package manager names is disabled in case any of the mistyped package manager names are actually commands on your system. While I've attempted to keep the list of mistyped package manager names free of actual commands, even if obscure, I can't guarantee that there's no command with those names on your own system. Note that not every possible misspelling is included, just some that I feel are common or are probably common (I don't use every package manager). **To enable fixing package manager names**, change the value of `FIX_PKG_TYPOS` near the top of `suod.sh` to `1`.

### Disabling insults
If you'd rather see the corrected command instead of an insult, you can change the value of `ENABLE_INSULTS` near the top of `suod.sh` to `0`.

## Contributing
See [CONTRIBUTING.md](CONTRIBUTING.md).

## Future plans
- [x] Provide a means to turn off insults and instead display what the command corrected to. This should be fairly easy to implement.
- [ ] Correct some other common mistakes. What will be implemented depends on what is seen fit.

## License
`suod` is licensed under the **Creative Commons Zero v1.0 Universal** license. That is, it's in the public domain. This code is so simple it doesn't really need something like the GNU GPL, the MIT License, BSD 2/3 clause, etc. If anything, I hope it teaches newcomers to Bash scripting some new tricks (as writing it did for me) or is useful for solving oddly specific issues like constructing usable command sequences to call from a script.
