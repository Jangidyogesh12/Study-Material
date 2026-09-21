# Study Material

A curated collection of study resources and links.

| Topic | Resource | Link | Done |
| ---- | -------- | ---- | ---- |
| System Design | System Design Crash Course in 4 Hours | https://www.youtube.com/watch?v=zZGcasTtLfA | [x] |
| Inference Engineering | Inference Engineering (Philip Kiely) — study tracker with progress checkboxes | https://inferenceengineering.tech | [ ] |
| DSA | NeetCode Roadmap — structured DSA practice | https://neetcode.io/roadmap | [ ] |
| DB | DB backup command | [See commands](#db-backup-command) | [ ] |

## DB backup command

**1. Back up (dump) the database to a file**

- `postgres pg_dump --clean --if-exists --create citymanaged > citymanaged-back.sql`

**2. Restore from that file**

- `cat citymanaged-back.sql | sudo -u postgres psql -d postgres`

### Why each part is used

| Part | Meaning | Why it is needed |
| ---- | ------- | ---------------- |
| `postgres` / `sudo -u postgres` | Runs the command as the `postgres` OS user | Only the `postgres` superuser can read all tables and create databases. |
| `pg_dump` | PostgreSQL backup utility | Reads a live database and writes SQL that recreates it. |
| `--clean` | Emit `DROP` statements before each object | Makes the restore idempotent: the target objects are removed and rebuilt instead of failing on "already exists". |
| `--if-exists` | Add `IF EXISTS` to those `DROP`s | Without it, `--clean` errors out when an object doesn't exist yet; this keeps a fresh restore silent. |
| `--create` | Include `CREATE DATABASE` (and `\connect`) in the dump | Lets the restore recreate the database itself, not just the tables inside it. |
| `citymanaged` | Source database name | Tells `pg_dump` which database to back up. |
| `>` | Shell output redirection | Sends the SQL dump to a file instead of the terminal. |
| `citymanaged-back.sql` | Destination file | The portable backup you can commit or move to another machine. |
| `cat ... \|` | Pipe the file into `psql` | Feeds the dump directly to the client instead of typing it manually. |
| `psql` | PostgreSQL interactive client | Executes the SQL statements from the dump. |
| `-d postgres` | Connect to the `postgres` maintenance database | Required because the dump contains `CREATE DATABASE citymanaged`; you cannot create a database while connected to it, so connect to a neutral database first. |
