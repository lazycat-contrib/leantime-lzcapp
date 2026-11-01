# Leantime (LazyCat LPK)

Project management and goal tracking for small teams.

- Upstream: https://github.com/Leantime/leantime
- Image: `leantime/leantime:3.13.2` (mirror mode, digest-matched)
- License: AGPL-3.0 (full text in `content/licenses/LICENSE`)
- Containers: app + MariaDB 10.11

## Notes

- Database connection comes entirely from `LEAN_DB_*` environment variables.
  The install wizard only collects admin/company fields
  (`validateInstallInput` checks email, firstname, lastname, company — no DB fields),
  and redirects away once `isInstalled()` is true.
- No seeded account or default password; the first admin is created by the wizard.
- `LEAN_DB_PASSWORD` and `LEAN_SESSION_PASSWORD` come from platform stable secrets.
- The image builds `mysqli`/`pdo_mysql` only — no `pdo_sqlite` — so MariaDB is required.
- No mail service configured (invites / password reset by email unavailable).
- Not yet verified on a real device.
