# Azurite Random Library

Random number utilities for [AzuriteLang](https://github.com/AzuriteLang).

## Usage

```toml
[dependencies]
random = { git = "https://github.com/AzuriteLang/random" }
```

```
import "random"
```

## API

| Function | Description |
|---|---|
| `seed(n)` | Seed the RNG with integer `n` |
| `random_int()` | Random integer (full range) |
| `random_float()` | Random float in `[0, 1)` |
| `random_bool()` | `true` or `false` |
| `random_range(lo, hi)` | Random integer in `[lo, hi]` (inclusive) |
| `roll_dice(sides)` | `random_range(1, sides)` |

## Example

```az
import "random"

func main() {
    seed(42)

    let d6 = roll_dice(6)
    print("You rolled a ", d6)

    let flip = random_bool()
    if flip {
        print("Heads")
    } else {
        print("Tails")
    }

    let pin = random_range(1000, 9999)
    print("PIN: ", pin)
}
```

## Modules

```
src/
  lib.az       -- entry point
  core.az      -- random_int, random_float, random_bool, seed
  util.az      -- random_range, roll_dice
```

## Builtins

Available globally without importing `random`:

- `rand()` — single random integer (C `rand()`)
- `srand(seed)` — seed the RNG (C `srand()`)
