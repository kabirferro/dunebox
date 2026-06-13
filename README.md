# Dunebox

**The complete PHP development environment for Windows. In a single folder.**

Download a zip, extract it wherever you want, open `dunebox.exe`. On first launch Dunebox downloads and configures everything by itself: web server, PHP (in five versions at once), database, mail, tools. No installer, no system service, nothing in the Windows registry. When you close Dunebox, your PC is exactly as it was.

Open source (MIT), built for **Laravel and PHP** developers on Windows.

---

## ✨ What it does

### 🐘 Every PHP version, together
PHP **5.4, 7.4, 8.2, 8.3 and 8.5** run side by side, always. The legacy project stays on 5.4, the new one runs on 8.5 — at the same time, no switching, no restarts. Each site picks its version with one click.

### 🌐 A local domain for every project
`mysite.test` in seconds: choose a name, a folder and a PHP version — Dunebox generates the virtual host, updates the Windows hosts file and the certificate. Aliases and multiple domains included.

### 🔒 Green HTTPS, even locally
SSL certificate generated and **automatically trusted** by the system: your `.test` sites run over HTTPS with no browser warnings, just like in production.

### 📬 Emails don't leave: you see them
Every email sent from PHP lands in a **local inbox** ([Mailpit](http://mailpit.localhost)) with HTML preview, source and live updates. Zero configuration, zero test emails accidentally sent to real clients.

### 🗄️ Databases ready to go
**MySQL** with [phpMyAdmin](http://phpmyadmin.localhost) and **Redis** with [phpRedisAdmin](http://phpredisadmin.localhost), already wired up and reachable from the browser. Your data stays yours, in a folder you choose — it survives updates and reinstalls.

### ⏰ Built-in cron
Drop a `dunebox.cron` file in your project (classic crontab syntax) and Dunebox runs your jobs — `php artisan schedule:run`, backups, whatever you need — with the project's correct PHP version. The file travels with the project in git: your teammates inherit it. And for system jobs there's the global scheduler.

```cron
* * * * *  php artisan schedule:run
0 3 * * *  php artisan backup:run
```

### 🖥️ One dashboard for everything
A graphical interface with service status at a glance, host management, quick access to tools, logs one click away. It lives in the system tray: close the window and the services keep running.

### 🧰 The toolbox, one click away
**Git, Node.js, Python and Composer** install (and update) straight from Dunebox, which notifies you when a new version is out.

### 📦 Install only what you need
Don't use Redis? Turn it off. Every component toggles on and off individually, and dependencies resolve themselves. Want a PHP version that isn't on the list? Add it with one line of configuration — no need to wait for an update.

### ✋ Your changes are respected
Hand-tweaked `php.ini`, `httpd.conf` or a virtual host? Dunebox **won't overwrite them**: updates and installs only touch what's missing. A full regeneration happens only when you ask for it.

### 🎒 Truly portable
Everything — software, configuration, projects, databases — lives in one folder. Copy it to another drive, carry it on a USB stick, move it to another PC: one command and the environment is back, identical. Perfect for keeping a whole team on the same stack.

---

## 🚀 Get going in three steps

1. **Download** the zip from the latest release and **extract** it wherever you like (that folder becomes your home)
2. **Open `dunebox.exe`** — the first launch downloads the packages and sets everything up
3. **Create your first host**: name, folder, PHP version → `https://mysite.test` is online

## ⌨️ From the terminal too

Everything the dashboard does, you can do from the command line — handy for automation and for those who live in the terminal. Just type `dunebox` to prepare the session (the right PATH and PHP version, in both cmd and PowerShell); then:

| Command | What it does |
|---|---|
| `dunebox up` | start all services |
| `dunebox down` | stop all services |
| `dunebox host add mysite.test ...` | create a new host (vhost + hosts + certificate) |
| `dunebox host list` | list configured hosts |
| `dunebox package list` | show components and their status |
| `dunebox package enable / disable <name>` | turn a component on/off |
| `dunebox cron list` | show scheduled cron jobs |
| `dunebox env` | environment status (root, default PHP, tools) |

And `php` in the terminal **automatically** uses the PHP version of the project you're in.

## ✅ Compatibility & requirements

| | |
|---|---|
| **Operating system** | Windows 10 and Windows 11 (64-bit) |
| **PHP** | 5.4 · 7.4 · 8.2 · 8.3 · 8.5 — all active at once |
| **Frameworks** | Laravel (all versions, legacy included) and any PHP project |
| **Disk space** | ~2–3 GB for a full install (only the active components) |
| **Connection** | needed only on first launch, to download the packages |
| **Permissions** | a single Windows confirmation for hosts and certificate; no service installed |
| **Browser** | Edge and Chrome resolve `.localhost` on their own; Dunebox handles the `.test` domains |

Nothing to uninstall: to remove Dunebox, just delete the folder.

## 🔗 Tools in your browser

| Tool | URL |
|---|---|
| phpMyAdmin | `http://phpmyadmin.localhost` |
| phpRedisAdmin | `http://phpredisadmin.localhost` |
| Mailpit | `http://mailpit.localhost` |

## 📦 What's inside

Apache · PHP 5.4 / 7.4 / 8.2 / 8.3 / 8.5 · MySQL · Redis · Mailpit · phpMyAdmin · phpRedisAdmin — all open source or freeware. Git, Node.js, Python and Composer can be added with one click from the wizard or the Settings.

---

## License

Dunebox is **open source** under the [MIT](LICENSE) license.
