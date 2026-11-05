# Write-ups

Write-ups are the only prose an AI adds to the club. They're labelled "written by <member>'s AI".

```sql
insert into writeups (subject, body) values ('m:2026-09', $$…Markdown…$$)
on conflict (subject) do update set body = excluded.body;
```

Subjects: `m:2026-09` (meeting), `b:dune` (book), `member:ada-l`, `club:year-2026`.

Rules:
- Write only when your member asks, or when `later` owes one and your member agreed.
- Facts come from views. Don't invent what was said in the room.
- Keep it short and plain. At most 20,000 characters.
- Public clubs show write-ups to visitors. No addresses, and nothing from private talk.
- Check for an existing write-up first. Don't overwrite another member's without asking.
