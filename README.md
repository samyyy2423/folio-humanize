# humanize

Numbers, times and sizes as people say them, for [Folio](https://github.com/samyyy2423/folio) programs:
"5 minutes ago", "1 hour 5 minutes", "2.4 MB", "21st", "3 files", "Ana, Bo and Cy", "1.2K", "forty-two".
In Folio alone, so it works everywhere Folio does.

```text
folio add humanize
```

```
use the package "humanize" as humanize

say humanize's ago(300)                           # 5 minutes ago
say humanize's duration(3900)                     # 1 hour 5 minutes
say humanize's file_size(2400000)                 # 2.4 MB
say "You came " + humanize's ordinal(21)          # You came 21st
say humanize's counted(3, "file") " changed"      # 3 files changed
say humanize's listed(list of "Ana", "Bo", "Cy")  # Ana, Bo and Cy
say humanize's number_words(42)                   # forty-two
```

## What it has

| | |
|---|---|
| `ago(seconds)` | `just now`, `a minute ago`, `5 minutes ago`, `2 hours ago`, `3 days ago`, `2 months ago`, `3 years ago`; less than 0 is `in 5 minutes` |
| `since(time, upto)` | how long ago a date and time (as `dates.folio` makes them) was, from now, or from `upto` if it's given |
| `duration(seconds, parts)` | `1 hour 5 minutes`, `2 days 3 hours`: the two biggest parts, or `parts` of them |
| `short_duration(seconds)` | `250ms`, `3.3s`, `1m 5s`, `1h 5m`, `2d 3h`: for a program's timing |
| `file_size(bytes)` | `999 bytes`, `1.5 kB`, `2.4 MB`, `123 MB`, `5 TB`, of 1000 each |
| `file_size_binary(bytes)` | `1 KiB`, `2.3 MiB`, of 1024 each |
| `compact(n)` | `999`, `1.2K`, `15K`, `3.4M`, `1.2B`, `7T` |
| `ordinal(n)` | `1st`, `2nd`, `3rd`, `11th`, `21st`, `102nd` |
| `number_words(n)` | `forty-two`, `one thousand two hundred and five`, `minus seven` |
| `counted(n, word)` | `1 file`, `3 files`, `0 people` |
| `plural_of(word)` | `boxes`, `cities`, `knives`, `children`, `sheep`, `Files`, `CITIES` |
| `listed(things)`, `listed_or(things)` | `Ana, Bo and Cy`, `1, 2 or 3` |
| `truncated(words, size)` | at most `size` letters, cut where a word ends, with … after it |

`ago` and `since` round as people do: 40 seconds is "just now", 50 is "a minute ago", 100 minutes "2 hours
ago", 25 days "25 days ago", 50 days "2 months ago".

## Tests

```text
folio test humanize.test.folio
```

## License

Apache License 2.0, as Folio is: see [LICENSE](LICENSE).
