# Owed work

`later` lists small jobs. The database adds one when a book lacks a cover, a Goodreads rating or a fiction/nonfiction tag.

```sql
select id, kind, subject, note from later where done_at is null order by created_at limit 20;
```

| kind | Do this |
|---|---|
| `cover` | `update books set cover_url = $1 where slug = $2` |
| `goodreads` | `update books set goodreads_avg = 4.24, goodreads_checked_on = current_date where slug = $1` |
| `kind` | `update books set kind = 'nonfiction', kind_by = 'ai' where slug = $1`. A person confirms it on the site |
| `import_flag` | Ask your member. A sheet cell couldn't be read |
| `writeup` | See [WRITEUPS.md](WRITEUPS.md) |

`subject` is `b:<slug>` for a book. Then mark it done:

```sql
update later set done_at = now() where id = $1;
```

Use only facts you can source. If you can't find one, leave the item open and say why.
