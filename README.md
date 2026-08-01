# GitHub API Auth

> Transparent GitHub API authentication for Linux applications.

[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
![Platform](https://img.shields.io/badge/platform-Debian%20%7C%20Ubuntu%20%7C%20Raspberry%20Pi%20OS-blue)
![Shell](https://img.shields.io/badge/language-Bash-orange)

---

## Why?

GitHub limits **anonymous REST API requests to 60 per hour per IP address**.

Applications like:

- Pi-hole
- PADD
- Update scripts
- Cron jobs
- Homelab automation

frequently query GitHub for release information.

On shared public IPs, VPNs, CGNAT, or busy networks, those 60 requests can be exhausted quickly, causing update checks to fail even though GitHub is online.

GitHub API Auth transparently authenticates requests to `api.github.com` using a GitHub Personal Access Token (PAT), increasing the available rate limit to **5,000 requests per hour**.

No application changes required.

---

# Features

- Transparent GitHub authentication
- Automatically injects PAT only for `api.github.com`
- Secure token storage
- Self-healing installation
- Automatic repair after package updates
- Status and diagnostics
- Backup / Restore
- Open Source (MIT)

---

# Example

### Before

```bash
curl https://api.github.com/rate_limit
```

```json
{
  "limit": 60
}
```

### After

```bash
curl https://api.github.com/rate_limit
```

```json
{
  "limit": 5000
}
```

---

# Planned Commands

```text
gh-auth install

gh-auth status

gh-auth repair

gh-auth self-test

gh-auth update-token

gh-auth backup

gh-auth restore

gh-auth uninstall
```

---

# Supported Platforms

- Raspberry Pi OS
- Debian
- Ubuntu

Additional Linux distributions are planned.

---

# Roadmap

| Version | Status | Features |
|----------|--------|----------|
| 0.1 | 🚧 | Repository / Documentation |
| 0.2 | Planned | Installer |
| 0.3 | Planned | Repair Engine |
| 0.4 | Planned | Self Test |
| 0.5 | Planned | Logging |
| 0.6 | Planned | Backup / Restore |
| 0.7 | Planned | Interactive TUI |
| 0.8 | Planned | Packaging |
| 0.9 | Planned | CI/CD |
| 1.0 | Planned | Stable Release |

---

# Contributing

Contributions are welcome.

Please open an issue before submitting major changes.

---

# License

MIT License

---

## Disclaimer

This project is not affiliated with or endorsed by GitHub.
