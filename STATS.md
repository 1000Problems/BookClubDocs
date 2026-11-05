# Answering questions

Do the math in views, not in your head. If a view is empty, say what that means: nothing yet, or not visible to your member.

| Question | SQL |
|---|---|
| Top 10 of all time | `select title, club_score, rank_all, meeting from book_scores order by rank_all limit 10` |
| Bottom 10 | `select title, club_score, rank_all, meeting from book_scores order by rank_all desc limit 10` |
| Is a book top 10? | `select rank_all, ranked_count from book_scores where book = 'dune'` |
| Is the latest top 10? | `select title, rank_all, ranked_count from last_meeting` |
| Harshest voter | `select name, mean, n from member_stats where harsh_rank = 1` |
| Easiest voter | `select name, mean, n from member_stats where easy_rank = 1` |
| Nonfiction since 2020 | `select sum(nonfiction) from mix where period_kind = 'year' and period >= '2020'` |
| Fiction mix by era | `select period, fiction, nonfiction, untagged, pct_fiction from mix where period_kind = 'era' order by period` |
| Who has hosted most | `select name, times_hosted, mean_pick_score, best_title from host_stats order by times_hosted desc` |
| Who shows up | `select name, attended, missed, out, longest_streak from attendance order by attended desc` |
| Club loved it more than Goodreads | `select title, club_score, gr_x2, delta from book_scores order by delta desc limit 5` |
| Words for a book | `select name, word from words where book = 'dune'` |
| A member's words | `select word, title, meeting from words where member = 'ada-l' order by meeting desc` |
| What's next | `select title, meets_at, venue_label, host_name, bring from next_meeting` |

## Fuzzy questions
- "Best year": compare `avg(club_score_raw)` by `year` in `book_scores`, and give the count beside it.
- "Do we like long books": there's no page count here. Say so; don't guess.
- Small numbers mislead. Give n with any average.
- Name the people behind a number only if the member asked about them.
