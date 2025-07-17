# nextcloud-infra

A self-hosted private cloud setup using **Nextcloud** on **WSL2**, backed by **Docker Compose**, with persistent storage on an **external HDD**. This setup is designed to run on a Windows machine with WSL2 and is accessible across devices via **Tailscale + MagicDNS**.

---

##  Overview

This project aims to provide a portable, efficient, and secure personal cloud infrastructure for storing and syncing files. It uses:

- WSL2 (Ubuntu)
- Docker Compose
- Nextcloud
- MariaDB
- External HDD for persistent storage
- Tailscale (planned) for remote access via MagicDNS

---

##  Tech Stack

- **OS**: Windows 10/11 with WSL2 (Ubuntu)
- **Containerization**: Docker Engine (inside WSL)
- **App**: [Nextcloud](https://nextcloud.com/)
- **Database**: [MariaDB 10.6](https://mariadb.org/)
- **Networking (Planned)**: Tailscale + MagicDNS
- **Storage**: Mounted ext4 partition on external HDD

---

##  Features

- Persistent data on external disk (safe from host system resets)
- Modular Docker Compose setup
- Environment variable support via `.env`
- Easy to scale or migrate
- Future: Access from anywhere via Tailscale

---

##  Folder Structure

nextcloud-infra/

├── .env
├── docker-compose.yml
├── config/
├── db/
└── nextcloud/


- `config/`: Custom configurations (future use)
- `db/`: MariaDB volume (optional bind mount in future)
- `nextcloud/`: Local Nextcloud config (future use)
- `.env`: Environment variables
- `docker-compose.yml`: Main deployment file

---

##  Installation

> Prerequisite: Docker working inside WSL2, external HDD mounted at `/mnt/nextcloud-data`

1. Clone this repository:

```bash
git clone https://github.com/Sencrzz29/nextcloud-infra.git
cd nextcloud-infra
```

---

## Set environment variables:

Edit .env file with your desired config:

```bash
NEXTCLOUD_PORT=8080
NEXTCLOUD_DATA=/mnt/nextcloud-data
MYSQL_ROOT_PASSWORD=your_root_pass
MYSQL_PASSWORD=your_db_pass
MYSQL_DATABASE=nextcloud
MYSQL_USER=nextcloud
```

---

## Launch Nextcloud:

docker compose up -d

Visit http://localhost:8080 in your browser and complete the setup.

---

## Admin Account

Admin username: (set during web setup)
Password: (set during web setup)

---

## TODO / Future Plans

-Add Tailscale + MagicDNS for remote access
-Add HTTPS via Caddy or Nginx
-Automate backups
-Create a systemd unit to auto-mount the HDD

---


---

### ✍️ How to Apply This

In your WSL terminal:

```bash
nano README.md

