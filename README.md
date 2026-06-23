<p align="center">
  <img src="dunebox-icon.svg" alt="Dunebox" width="120" height="120">
</p>

<h1 align="center">Dunebox</h1>

<p align="center"><strong>The complete PHP development environment for Windows. In a single folder.</strong></p>

Download a zip, extract it wherever you want, open `dunebox.exe`. On first launch Dunebox downloads and configures everything by itself: web server, PHP (in five versions at once), databases, mail, tools. No installer, no system service, nothing in the Windows registry. When you close Dunebox, your PC is exactly as it was.

Open source (MIT), built for **Laravel and PHP** developers on Windows.

---

## ✨ Highlights

- **Every PHP version at once** — 5.6 · 7.4 · 8.2 · 8.3 · 8.5, side by side, no switching
- **Many databases, even the same engine in several versions** — MySQL 9.6 + 8.0 + 5.7 + MariaDB together, each on its own port
- **A local domain + green HTTPS for every project** — `mysite.test` in seconds, trusted certificate
- **A smart terminal** — `php`/`artisan`/`composer` auto-pick the project's PHP version
- **Built-in tools** — phpMyAdmin, phpRedisAdmin, Mailpit, Cron Jobs, optional local DNS
- **Claude integration** — drive Dunebox from Claude Code / Claude Desktop
- **Truly portable** — one folder; move it, copy it, carry it on a USB stick

---

## 📚 Feature guide

### 🐘 Every PHP version, together
PHP **5.6, 7.4, 8.2, 8.3 and 8.5** run side by side, always. The legacy project stays on 5.6, the new one runs on 8.5 — at the same time, no switching, no restarts. Each site picks its version with one click. Every modern version ships with the extensions real projects need already on — **Imagick** and **GD** for images, the **MongoDB** driver, **intl**, **OPcache**, **mbstring**, **cURL**, and **PDO** for MySQL, PostgreSQL and SQLite.

### 🗄️ Databases — multiple engines *and* multiple versions, together
This is where Dunebox goes further than the usual stack. You're not limited to one database: you can run **several engines at the same time**, and even **several versions of the same engine side by side**, each listening on its own port.

- **MySQL 9.6, 8.0 and 5.7 at the same time** — keep a legacy project on 5.7 while a new one runs on 9.6, with no conflicts
- **MariaDB** alongside MySQL
- **PostgreSQL** and **MongoDB** one toggle away
- **Redis** for cache and queues

Each instance shows up with its **name and version** (e.g. *MySQL 9.6*, *MariaDB 12.3*) and gets its **own port, data directory and configuration** — your data is isolated per version and survives updates and reinstalls, in a folder you choose. Ports are editable from Settings: each engine on the port you prefer.

| Engine | Default port |
|---|---|
| MySQL 9.6 | `3306` |
| MySQL 8.0 | `3307` |
| MySQL 5.7 | `3308` |
| MariaDB | `3309` |
| PostgreSQL | `5432` |
| MongoDB | `27017` |

**Ready-to-use credentials**, created automatically on first launch — user **`dunebox`** (or the engine's root) with password **`secret`**:

| Database | Host | User | Password |
|---|---|---|---|
| MySQL / MariaDB | `127.0.0.1` (port per instance) | `dunebox` (or `root`) | `secret` |
| PostgreSQL | `127.0.0.1:5432` | `dunebox` (or `postgres`) | `secret` |

Point your app's `.env` at `127.0.0.1`, the right port, user `dunebox`, password `secret` — connected. The same panel in Settings lists every active database with its connection details and a ready-made `.env` snippet for email.

### 🧭 phpMyAdmin manages *all* your databases
[phpMyAdmin](http://phpmyadmin.localhost) is wired to **every MySQL and MariaDB instance at once**: pick the server (MySQL 9.6, 8.0, 5.7, MariaDB…) from the dropdown and manage them all from one place. **Redis** has [phpRedisAdmin](http://phpredisadmin.localhost). All reachable from the browser, over HTTP and HTTPS.

### 🌐 A local domain for every project
`mysite.test` in seconds: choose a name, a folder and a PHP version — Dunebox generates the virtual host, updates the Windows hosts file and the certificate. Aliases and multiple domains included. Prefer Apache or nginx? Pick the engine per site.

### 🔒 Green HTTPS, even locally
A local certificate authority, generated and **trusted automatically** — once. Every `.test` site runs over HTTPS with the green padlock and no browser warnings, in **Chrome, Edge, Brave, Opera and Firefox**. New sites are trusted instantly; if the certificate ever isn't trusted, Dunebox notices and offers to fix it in one click.

### ⌨️ A smart terminal
Type `dunebox` once and your terminal is ready (correct PATH and tools, in both cmd and PowerShell). From then on `php`, `artisan` and `composer` **automatically use the right PHP version for the project you're in** — no manual switching. Run `composer install` in a legacy project and it uses that project's PHP; in a modern one, the modern PHP. The matching `php.ini` (with the right extensions) is loaded for you.

### 🎼 Composer, included and portable
Composer comes **with Dunebox**, inside the folder — nothing scattered across your PC. It always runs with the correct PHP and extensions for your project (openssl, mbstring, …), and travels with the environment when you move it.

### 📬 Emails don't leave: you see them
Every email sent from PHP lands in a **local inbox** ([Mailpit](http://mailpit.localhost)) with HTML preview, source and live updates. Zero configuration, zero test emails accidentally sent to real clients. A copy-ready `.env` SMTP snippet is in Settings.

### ⏰ Cron Jobs, built in
Schedule jobs with a **guided editor** (no crontab syntax to memorise) — `php artisan schedule:run`, backups, anything — and Dunebox runs them with the project's correct PHP version. Per-project jobs live in the project (project mode) and travel with it in git: your teammates inherit them. System-wide jobs go in the global scheduler. Everything runs only while Dunebox is on.

```json
"cron": [
  "* * * * *  php artisan schedule:run",
  "0 3 * * *  php artisan backup:run"
]
```

### 🤖 Claude integration
Dunebox integrates with **Claude Code** and **Claude Desktop**: enable it from the wizard or Settings and Claude can drive your environment — list and create hosts, manage Cron Jobs, check service status, read logs, set a site's PHP version, and run `artisan`/`composer` with the right PHP. A bundled skill teaches Claude the Dunebox workflow, and an MCP server exposes the operations as structured tools.

### 🌍 Optional local DNS
Turn on the built-in wildcard DNS and `*.test` resolves to your machine automatically — **no entries in the Windows hosts file**. Off by default; classic hosts-file mode otherwise.

### 🧰 The toolbox, one click away
Dunebox installs, updates and removes the dev tools you want — **Git, Node.js, nvm, Python (2 and 3, side by side) and FFmpeg** (from their official sources) — and notifies you when a new version is out. Together with the bundled Composer, they're available as commands in any terminal (`python` and `python3` included).

### 📦 Install only what you need
Every component is a package you toggle on or off individually, in its own card in Settings — enable/disable, install/uninstall, size on disk, and (for databases) the listening port, all in one place. Dependencies resolve themselves (no web server → no PHP). Want a PHP or database version that isn't on the list? Add it with one line of configuration — no need to wait for an update.

### 🔔 Everything in one place
A graphical dashboard: service status at a glance, host and Cron Jobs management, quick access to tools, logs one click away. All alerts and prompts are collected in a single **Notifications** center. It lives in the system tray: close the window and the services keep running — and Dunebox shuts everything down cleanly when Windows restarts.

### ✋ Your changes are respected
Hand-tweaked `php.ini` or `httpd.conf`? Dunebox **won't overwrite them**: updates and installs only touch what's missing. A full regeneration happens only when you ask for it.

### 🎒 Truly portable
Everything — software, configuration, Composer, projects, databases — lives in one folder. Copy it to another drive, carry it on a USB stick, move it to another PC: Dunebox detects the move and realigns itself. Perfect for keeping a whole team on the same stack.

---

## 🚀 Get going in three steps

1. **Download** the zip from the latest release and **extract** it wherever you like (that folder becomes your home)
2. **Open `dunebox.exe`** — a short setup wizard (language first, then packages, PHP versions and folders) downloads and configures everything
3. **Create your first host**: name, folder, PHP version → `https://mysite.test` is online

## ⌨️ From the terminal too

Everything the dashboard does, you can do from the command line — handy for automation and for those who live in the terminal. Type `dunebox` to prepare the session, then:

| Command | What it does |
|---|---|
| `dunebox up` / `down` | start / stop all services |
| `dunebox host add mysite.test ...` | create a new host (vhost + hosts + certificate) |
| `dunebox host list` | list configured hosts |
| `dunebox package list` | show components and their status |
| `dunebox package enable / disable <name>` | turn a component on/off |
| `dunebox cron list` | show scheduled Cron Jobs |
| `dunebox env` | environment status (root, default PHP, tools) |

And `php`, `artisan` and `composer` **automatically use the PHP version of the project you're in**.

## ✅ Compatibility & requirements

| | |
|---|---|
| **Operating system** | Windows 10 and Windows 11 (64-bit) |
| **PHP** | 5.6 · 7.4 · 8.2 · 8.3 · 8.5 — all active at once |
| **Databases** | MySQL (9.6 / 8.0 / 5.7), MariaDB, PostgreSQL, MongoDB, Redis — multiple at once |
| **Frameworks** | Laravel (all versions, legacy included) and any PHP project |
| **Disk space** | ~2–3 GB for a typical install (only the active components) |
| **Connection** | needed only on first launch, to download the packages |
| **Permissions** | a single Windows confirmation for hosts and certificate; no service installed |
| **Browser** | Edge and Chrome resolve `.localhost` on their own; Dunebox handles the `.test` domains |

Nothing to uninstall: to remove Dunebox, just delete the folder.

## 🔗 Tools in your browser

Reachable over both HTTP and HTTPS (green padlock, same trusted certificate):

| Tool | URL |
|---|---|
| phpMyAdmin (all MySQL/MariaDB instances) | `http://phpmyadmin.localhost` · `https://…` |
| phpRedisAdmin | `http://phpredisadmin.localhost` · `https://…` |
| Mailpit | `http://mailpit.localhost` · `https://…` |

## 📦 What's inside

Apache (or nginx) · PHP 5.6 / 7.4 / 8.2 / 8.3 / 8.5 · MySQL (9.6 / 8.0 / 5.7) · MariaDB · PostgreSQL and MongoDB (optional) · Redis · Mailpit · phpMyAdmin · phpRedisAdmin · a bundled Composer — all open source or freeware. Git, Node.js, nvm, Python (2 and 3) and FFmpeg can be added (and removed) with one click from the wizard or the Settings.

---

## License

Dunebox is **open source** under the [MIT](LICENSE) license.
