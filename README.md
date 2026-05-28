# Tauraro Language Support

Complete language support for **Tauraro** — a systems-grade programming language with Python-style syntax, Rust-level performance, and full bilingual (English + Hausa) keyword support.

## Features

### Syntax Highlighting

Rich, Java IntelliJ-inspired syntax coloring with distinct colors for every language construct:

- **Keywords** — control flow, declarations, modifiers (orange, bold)
- **Hausa keywords** — visually distinct from English equivalents (warm amber, bold italic)
- **Class & type names** — yellow, instantly recognizable
- **Function & method names** — gold, definition and call sites both highlighted
- **Strings** — green; f-strings show `{expression}` regions in a different color
- **Numbers** — blue (integers, floats, hex `0xFF`, binary `0b101`, octal `0o77`)
- **Comments** — gray, italic
- **Built-in types** — purple (`str`, `i32`, `List`, `Option`, `Result`, …)
- **Built-in functions** — blue (`print`, `len`, `range`, `map`, …)
- **Constants** — bold blue (`true`, `false`, `none`, `gaskiya`, `karya`, `babu`)
- **`self`** — teal italic, always stands out
- **Decorators** — yellow-green (`@decorator`)
- **Escape sequences** — highlighted inside strings and f-strings

### Tauraro Dark Theme (Java Style)

A custom dark theme inspired by **IntelliJ IDEA Darcula**, included with the extension. Activate it via:

> **Command Palette** → `Preferences: Color Theme` → **Tauraro Dark (Java Style)**

### Code Snippets

30+ snippets for common Tauraro patterns — trigger with prefix:

| Prefix | Snippet |
|---|---|
| `def` / `fn` | Function definition |
| `aiki` / `afn` | Hausa function definition |
| `class` / `cls` | Class definition |
| `aji` | Hausa class definition |
| `interface` | Interface definition |
| `enum` | Enum definition |
| `struct` / `tsari` | Struct definition |
| `extend` | Extend block |
| `ife` | If/else |
| `ifeife` | If/elif/else chain |
| `for` / `forr` | For loop / for-range loop |
| `while` | While loop |
| `try` / `tryf` | Try/except / try/except/finally |
| `match` | Match/case statement |
| `main` | Main entry point |
| `pubdef` / `pm` | Public method |
| `adef` | Async function |
| `pf` / `printf` | Print with f-string |
| `fstr` | F-string expression |
| `doc` | Docstring block |
| `result` / `option` | Result / Option type |
| `lc` | List comprehension |

### Language Configuration

- **Auto-closing pairs** — `{}`, `[]`, `()`, `""`, `''`, `"""..."""`, `'''...'''`
- **Auto-indent** — increases after `:` on block-starting lines; decreases for `else`, `elif`, `except`, `finally`, `case` and their Hausa equivalents
- **Code folding** — indentation-based + `# region` / `# endregion` markers
- **Bracket pair colorization** — `()`, `[]`, `{}`
- **Editor defaults** — JetBrains Mono / Fira Code font, ligatures, 4-space tabs, smooth cursor

## File Extensions

| Extension | Description |
|---|---|
| `.tr` | Standard Tauraro source file |
| `.tau` | Alternate extension |
| `.tauraro` | Full-name extension |

## Bilingual Keywords

Every keyword has an English form and a Hausa equivalent — both are fully highlighted.

### Declarations

| English | Hausa | Meaning |
|---|---|---|
| `def` | `aiki` | Function definition |
| `class` | `aji` | Class definition |
| `struct` | `tsari` | Struct definition |
| `interface` | — | Interface definition |
| `enum` | — | Enum definition |
| `extend` | — | Extend a class |
| `lambda` | `dan_aiki` | Lambda / anonymous function |

### Control Flow

| English | Hausa | Meaning |
|---|---|---|
| `if` | `idan` | If |
| `elif` | `koidan` | Else if |
| `else` | `sai` | Else |
| `for` | `ga` | For loop |
| `while` | `yayinda` | While loop |
| `return` | `dawo` | Return |
| `break` | `tsaya` | Break |
| `continue` | `ci_gaba` | Continue |
| `pass` | `wuce` | Pass / no-op |
| `match` | `duba` | Match statement |
| `case` | `hali` | Case arm |

### Exception Handling

| English | Hausa | Meaning |
|---|---|---|
| `try` | `gwada` | Try block |
| `except` | `kama` | Except / catch |
| `finally` | `karshe` | Finally block |
| `raise` | `jefa` | Raise exception |

### Async / Concurrency

| English | Hausa | Meaning |
|---|---|---|
| `async` | `marasa_jira` | Async function |
| `await` | `jira` | Await expression |
| `yield` | `bayar` | Yield value |
| `spawn` | — | Spawn task |

### Operators & Logic

| English | Hausa | Meaning |
|---|---|---|
| `and` | `da` | Logical and |
| `or` | `ko` | Logical or |
| `not` | `ba` | Logical not |

### Constants

| English | Hausa | Meaning |
|---|---|---|
| `true` | `gaskiya` | Boolean true |
| `false` | `karya` | Boolean false |
| `none` | `babu` | Null / None |

### Modifiers

`pub`, `mut`, `static`, `const`, `abstract`, `virtual`, `override`, `unsafe`, `let`

## Built-in Types

```
str   int   i8   i16   i32   i64   i128
u8    u16   u32  u64   u128  f32   f64
bool  char  void  String  Bytes
List  Dict  Tuple  Set  Map
Option  Result  Box  Vec  Pointer  Any  Never  Self
```

## Example Code

```tauraro
from std.io import File

class JsonParser:
    pub def parse(self, input: str) -> Option[Dict]:
        mut result: Dict = {}
        try:
            result = self._parse_object(input)
            return result
        except ValueError as e:
            print(f"Parse error: {e}")
            return none

    def _parse_object(self, s: str) -> Dict:
        pass

@cached
def fibonacci(n: i32) -> i64:
    if n <= 1:
        return n
    return fibonacci(n - 1) + fibonacci(n - 2)

# Hausa keywords work identically
aiki gaishe_da_duniya(suna: str):
    print(f"Sannu, {suna}!")
```

## Requirements

- VS Code `^1.80.0`
- No compiler installation needed for syntax highlighting

To compile and run `.tr` files, install the [Tauraro compiler](https://github.com/Yusee-Programmer/tauraro).

## Release Notes

### 2.0.3
- Synced marketplace displayName and description to match README

### 2.0.2
- Updated README with full feature documentation, keyword tables, and code examples

### 2.0.1
- Added MIT LICENSE file

### 2.0.0
- Complete grammar rewrite — distinct scopes for class names, function names, method calls, Hausa keywords
- New **Tauraro Dark (Java Style)** theme — IntelliJ Darcula-inspired
- 30+ code snippets
- F-string interpolation highlighting — `{expr}` regions colored separately
- Full number literal support — hex, binary, octal, float, scientific, type suffixes
- Auto-indent, bracket pairing, code folding, region markers
- JetBrains Mono / Fira Code font defaults with ligatures

### 1.0.0
- Initial release

---

**Repository:** [github.com/Yusee-Programmer/tauraro](https://github.com/Yusee-Programmer/tauraro)

*Tauraro — Python syntax. Rust performance. Your language.*
