# The club's data

Everything is filtered to what your member can see. Empty results may mean "not visible", not "none".

## Meetings and books
| View | Meaning |
|---|---|
| `club` | Name, about and settings |
| `next_meeting` | The next meeting: book, date, host, place, what to bring, RSVP counts |
| `last_meeting` | Latest revealed meeting: score, rank, top words |
| `meetings` | Every meeting. `slug` is `YYYY-MM`. `status`: planned, met, skipped. `scoring`: not_open, open, revealed |
| `meeting_cards` | One row per meeting with book, host, score and ranks |
| `meeting_directions` | Address, directions, parking. Members only |
| `books`, `book_cards` | Book facts; cards add meetings and times on a slate |

## Scores
| View | Meaning |
|---|---|
| `meeting_votes` | Each person's attendance, score and word. `corrected` marks a later fix |
| `book_scores` | Revealed meetings only. `club_score` shown to 1 decimal, `club_score_raw` exact, `gr_x2` = Goodreads × 2, `delta` = club minus Goodreads, `rank_all`, `rank_year`, `ranked_count` |
| `words` | Every visible word with who said it and the score |

Attendance: `voted`, `partial`, `unfinished`, `missed`, `out`. Club scores count `voted`, and `partial` when
`club.partial_counts`. Guests count when `club.guest_counts`. `unfinished` never counts. Scores are hidden until reveal when
`club.score_reveal = 'together'`.

## People and stats
| View | Meaning |
|---|---|
| `members` | Name and status: active, alumni, guest |
| `member_stats` | n, mean, stdev, misses, `easy_rank`, `harsh_rank`. Ranks need n ≥ `club.stats_min_n`. No guests |
| `host_stats` | Times hosted, mean score of their picks, best pick |
| `attendance` | Attended, missed, out, longest streak |
| `mix` | Fiction and nonfiction by `period`. `period_kind`: year or era (5-year buckets) |

## Talk and your own writing
| View | Meaning |
|---|---|
| `club_posts`, `thread_posts` | Chat, when your club lets AIs read it. Read only |
| `threads` | Chat threads |
| `writeups` | AI write-ups. See [WRITEUPS.md](WRITEUPS.md) |
| `later` | Owed work. See [LATER.md](LATER.md) |
| `ballot_results` | Points by book, only after a ballot closes |
