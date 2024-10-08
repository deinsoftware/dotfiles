# Cheatsheet

---

## Menu

* [Emacs](#emacs)
  * [Navigation](#navigation)
  * [Editing](#editing)
  * [Search](#search)
* [iTerm2](#iterm2)
  * [Windows](#windows)
  * [Tabs](#tabs)
  * [Splitting](#splitting)
  * [Navigation](#navigation)
  * [Editing](#editing)
  * [Search](#search)

---

## Emacs

### Navigation

| Shortcut                 | Function                                 |
| ------------------------ | ---------------------------------------- |
| `↑`                      | Previous command history                 |
| `↓`                      | Next command history                     |
| `⌃` + `A`                | Go to beginning of line                  |
| `⌃` + `E`                | Go to end of line                        |
| `⌥` + `B`                | Go back between words                    |
| `⌥` + `F`                | Go forward between words                 |
| `⌥` + `Left Click`       | Cursor jump                              |

### Editing

| Shortcut                 | Function                                       |
| ------------------------ | ---------------------------------------------- |
| `⌃` + `U`                | Clean prompt (Undo)                            |
| `⌃` + `⇧` + `-`          | Undo last changes                              |
| `⌃` + `K`                | Kill text from the point to end of the line    |
| `^` + `D`                | Delete current character                       |
| `^` + `H`                | Delete previous character                      |
| `⌃` + `W`                | Delete last Word                               |
| `⌃` + `Y`                | Yank recall last deleted (Command or Word)     |
| `⌃` + `L`                | Clean screen                                   |
| `⌃` + `D`                | Exit shell                                     |

### Search

| Shortcut                 | Function                                 |
| ------------------------ | ---------------------------------------- |
| `⌃` + `P`                | Previous History                         |
| `⌃` + `R`                | Search command history                   |
| `⌃` + `R`                | Loop through search result               |
| `⌃` + `R` (twice)        | Search the last remember search term     |
| `⌃` + `Y`                | End search at current history entry      |
| `⌃` + `G`                | Cancel search and restore original line  |

⇧ [Back to menu](#menu)

---

## iTerm2

### Windows

| Shortcut                | Function                      |
| ----------------------- | ----------------------------- |
| `⌘` + `N`               | New Window                    |
| `⌘` + `⌥` + `<#>`       | Go to Window number `#`       |
| `⌘` + `O`               | Select profile                |

### Tabs

| Shortcut                | Function              |
| ----------------------- | --------------------- |
| `⌘` + `T`               | New Tab               |
| `⌘` + `W`               | Close Tab             |
| `⌘` + `<#>`             | Go to Tab number `#`  |
| `⌘`+ `←`                | Previous Tab          |
| `⌘`+ `→`                | Next Tab              |
| `⌘` + `backtick`        | Cycle iTerm Windows   |
| `⌘`+ `⏎`                | Full screen / Restore |

### Splitting

| Shortcut                 | Function                                 |
| ------------------------ | ---------------------------------------- |
| `⌘` + `D`                | Split Window Vertically (same profile)   |
| `⌘` + `⇧` + `D`          | Split Window Horizontally (same profile) |
| `⌘` + `c` + `⇧` + `Drag` | Move a pane with the mouse               |
| `⌘` + `⌥` + `Arrow`      | Go to Split Pane by Direction            |
| `⌘` + `]` , `⌘` + `[`    | Go to Split Pane by Order of Use         |
| `⌘` + `⇧` + `⏎`          | Maximize / Restore a pane                |
| `⌃` + `⌘` + `Arrow`      | Resize Pane                              |

### Navigation

| Shortcut                 | Function                                 |
| ------------------------ | ---------------------------------------- |
| `⌘` + `←`                | Go to beginning of line                  |
| `⌘` + `→`                | Go to end of line                        |
| `⌥` + `←`                | Go back between words                    |
| `⌥` + `→`                | Go forward between words                 |

> Requieres iTerm2 extra [configuration](https://coderwall.com/p/h6yfda/use-and-to-jump-forwards-backwards-words-in-iterm-2-on-os-x) to work

### Editing

| Shortcut                 | Function                                                 |
| ------------------------ | -------------------------------------------------------- |
| `⌘` + `K`                | Clean buffer                                             |
| `^` + `L`                | Move current line on top                                 |
| `⌘` + `W`                | Exit shell (close window)                                |
| `⌘` + `⇧` + `I`          | Enable/Disable broadcast mode in all panes in all tabs   |
| `⌘` + `⌥` + `I`          | Enable/Disable broadcast mode in all tabs in current tab |

### Search

| Shortcut                 | Function                                 |
| ------------------------ | ---------------------------------------- |
| `⌘` + `F`                | Open search bar                          |
| `⌘` + `G`                | Find next                                |

⇧ [Back to menu](#menu)
