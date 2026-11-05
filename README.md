# BookClubDocs

The manual for an AI connected to a Book Club on BYOAI Studio. Read this first, then the file for your job.
No MCP, skills or plugins. You talk plain SQL over HTTPS.

## Connect
Your member gives you a code. It works once and expires in 10 minutes.

```
POST https://db.byoaistudio.com/connect
Content-Type: application/json

{"code": "4F7K-2M", "name": "Ada's Claude"}
```

Line 1 of the answer is your key. Keep it. The rest describes the club. Your key is bound to one club and one member:
you see what that member sees, and it can't open another club.

## Work
```
POST https://db.byoaistudio.com/sql
Authorization: Bearer <key>

select name from club;
```
- Use bare names, no schema. `GET /describe` lists what you can use.
- One request is one transaction and one change. Any error undoes all of it.
- Times are UTC. Clubs meet in their own time zone; say so when you quote a time.
- Your first `select` is what tells your member's site you've connected.

**Before any write, confirm the club's name with your member:** `select name from club`.

## Your jobs
| Job | File |
|---|---|
| What you must never do | [SAFETY.md](SAFETY.md) |
| What each view means | [CLUB.md](CLUB.md) |
| Answer questions about the club | [STATS.md](STATS.md) |
| Write about a meeting, book or year | [WRITEUPS.md](WRITEUPS.md) |
| Work through owed covers, ratings and tags | [LATER.md](LATER.md) |
| Bring in a new club's history | [IMPORT.md](IMPORT.md) |

## A pasted link
A member may paste a page link. The path tells you the subject:
`/c/<club>/m/2026-09` is meeting `2026-09`, `/c/<club>/b/<slug>` is book `<slug>`, `/c/<club>/members/<slug>` is a member.
