import requests


def check_btc_balance(xpub_or_address):
  # Query public blockchain explorer APIs securely via loopback/whitelisted egress
  url = f"https://blockstream.info/api/address/{xpub_or_address}"
  try:
    response = requests.get(url, timeout=10)
    if response.status_code == 200:
      data = response.json()
      funded = (
          data["chain_stats"]["funded_txoed_sum"]
          - data["chain_stats"]["spent_txo_sum"]
      )
      print(f"[*] Address {xpub_or_address} Net Balance (Satoshis): {funded}")
      return funded
  except Exception as e:
    print(f"[!] Blockchain query error: {e}")
version: '3.8'
services:
  adpbetty-asset-engine:
    build: .
    container_name: adpbetty_asset_core
    restart: unless-stopped
    volumes:
      - ./data:/app/data
    environment:
      - DB_PATH=/app/data/adpbetty_assets.db
    networks:
      - internal_secure

networks:
- internal_secure:
    internal: true
It looks like you are reviewing snippets of your Python automation scripts (search_indiana_unclaimed and check_btc_balance) alongside some search output and account references.
Would you like to expand these scripts into a fully integrated, modular adpBetty pipeline—for instance, adding automated logging, error handling, or database result export features?
It looks like you are reviewing snippets of your Python automation scripts (search_indiana_unclaimed and check_btc_balance) alongside some search output and account references.
Would you like to expand these scripts into a fully integrated, modular adpBetty pipeline—for instance, adding automated logging, error handling, or database result export features?https://blockstream.info/api/address/It looks like you are reviewing snippets of your Python automation scripts (search_indiana_unclaimed and check_btc_balance) alongside some search output and account references.
Would you like to expand these scripts into a fully integrated, modular adpBetty pipeline—for instance, adding automated logging, error handling, or database result export features?It looks like you are reviewing snippets of your Python automation scripts (search_indiana_unclaimed and check_btc_balance) alongside some search output and account references.
Would you like to expand these scripts into a fully integrated, modular adpBetty pipeline—for instance, adding automated logging, error handling, or database result export features?
import requests


def check_btc_balance(xpub_or_address):
  # Query public blockchain explorer APIs securely via loopback/whitelisted egress
  url = f"https://blockstream.info/api/address/{xpub_or_address}"
  try:
    response = requests.get(url, timeout=10)
    if response.status_code == 200:
      data = response.json()
      funded = (
          data["chain_stats"]["funded_txoed_sum"]
          - data["chain_stats"]["spent_txo_sum"]
      )
      print(f"[*] Address {xpub_or_address} Net Balance (Satoshis): {funded}")
      return funded
  except Exception as e:
    print(f"[!] Blockchain query error: {e}")
version: '3.8'
services:
  adpbetty-asset-engine:
    build: .
    container_name: adpbetty_asset_core
    restart: unless-stopped
    volumes:
      - ./data:/app/data
    environment:
      - DB_PATH=/app/data/adpbetty_assets.db
    networks:
      - internal_secure

networks:
- internal_secure:
    internal: true
requests.posthttps://www.indianaunclaimed.gov/app/claim-searchimport sqlite3
import requests
from bs4 import BeautifulSoup

# Initialize local secure SQLite database
conn = sqlite3.connect("adpbetty_assets.db")
cursor = conn.cursor()
cursor.execute(
    """
    CREATE TABLE IF NOT EXISTS unclaimed_leads (
        id INTEGER PRIMARY KEY AUTOINCREMENT,
        source_state TEXT,
        owner_name TEXT,
        address TEXT,
        amount_est TEXT,
        status TEXT
    )
"""
)


def search_indiana_unclaimed(last_name, first_name):
  # Official Indiana Unclaimed Property search endpoint simulation
  url = "https://www.indianaunclaimed.gov/app/claim-search"
  payload = {
      "lastName": last_name,
      "firstName": first_name,
      "city": "Evansville",
  }
  headers = {"User-Agent": "Mozilla/5.0 (Compatible Local Audit Bot)"}

  try:
    response = requests.post(url, data=payload, headers=headers, timeout=10)
    if response.status_code == 200:
      print(
          f"[*] Successfully queried Indiana Unclaimed database for"
          f" {first_name} {last_name}"
      )
      # Parse response elements or store raw JSON payload for local review
    else:
      print(f"[!] Query failed with status code: {response.status_code}")
  except Exception as e:
    print(f"[!] Connection error during state property scan: {e}")


if __name__ == "__main__":
  search_indiana_unclaimed("Evans", "Robert")
1981bobthedeveloper@gmail.com

1981bobthedeveloper@gmail.com

AI Mode
All
Images
News
Videos
Maps
Forums
Short videos
Web
Flights
Finance
Shopping
Books
Search tools
Feedback
Did you mean: 1981 bob the developer@gmail.com

Email: 27daniellucas@gmail.com Dear Business Owners Your website ...
Email: 27daniellucas@gmail.com Dear Business Owners Your website ...
Facebook
Attack Targets All 1.8 Billion Gmail Accounts | ASIS NJ
Attack Targets All 1.8 Billion Gmail Accounts | ASIS NJ
ASIS
How Google's 80/20 rule led to the development of Gmail? - InspireIP
How Google's 80/20 rule led to the development of Gmail? - InspireIP
InspireIP
Stream episode Old Gmail Accounts is one of the most popular email ...
Stream episode Old Gmail Accounts is one of the most popular email ...
SoundCloud
Gmail gets a proper PDF viewer - CNET
Gmail gets a proper PDF viewer - CNET
CNET
Gmail debuted on April Fool's Day 20 years ago. The joke is still ...
Gmail debuted on April Fool's Day 20 years ago. The joke is still ...
Popular Science
Clickable Gmail Signature Template for Authors (PDF Download With Instructions) - Etsy
Clickable Gmail Signature Template for Authors (PDF Download With Instructions) - Etsy
Etsy · $8.10
Gmail revolutionized email 20 years ago. People thought it was ...
Gmail revolutionized email 20 years ago. People thought it was ...
Tech Xplore
81 year old friend getting Gmail spam ..please help : r/GMail
81 year old friend getting Gmail spam ..please help : r/GMail
Reddit
Clickable Gmail Signature Template for Authors, Writers (PDF Download With Instructions) - Etsy
Clickable Gmail Signature Template for Authors, Writers (PDF Download With Instructions) - Etsy
Etsy · $8.10
Set-Up Email for Android | Email Set-Up | Documentation ...
Set-Up Email for Android | Email Set-Up | Documentation ...
MotorDesk Documentation
M Gmai!
M Gmai!
Revize
Gmail is killing SMS-based 2FA login codes in favor of this ...
Gmail is killing SMS-based 2FA login codes in favor of this ...
LinkedIn
Clickable Gmail Signature Template for Authors, Journalists (PDF ...
Clickable Gmail Signature Template for Authors, Journalists (PDF ...
Etsy · $8.10
Around the Web
Around the Web
NBC 15
On this date in 2004, Google first announced that they would be ...
On this date in 2004, Google first announced that they would be ...
Facebook
Looks like you've reached the end
Results are not personalized
Cedar Hall, Evansville, IN - Based on your places (Work)
Update location
Dark theme: on
Help
Send feedback
Privacy
Terms1981developer@gmail.com27daniellucas@gmail.comSHELL := /bin/bash
PROJECT_NAME := wk-precision-hub
GPG_KEY_ID ?= re1Lucky365
BACKUP_DIR := /var/backups/$(PROJECT_NAME)
TIMESTAMP := $(shell date +%Y%m%d_%H%M%S)
ARCHIVE_NAME := $(PROJECT_NAME)_$(TIMESTAMP).tar.zst

.PHONY: all verify build up down backup clean

all: verify build up

verify:
	@echo "[*] Verifying Git commit GPG signatures..."
	@git log -n 1 --show-signature | grep -q "Good signature" || (echo "[!] Unsigned or invalid commit signature!" && exit 1)
	@echo "[+] Cryptographic signature verified."

build:
	@echo "[*] Building hardened container images..."
	docker compose build --pull --no-cache

up:
	@echo "[*] Launching services bound to loopback..."
	docker compose up -d --remove-orphans

down:
	@echo "[*] Stopping services cleanly..."
	docker compose down

backup:
	@echo "[*] Creating multi-threaded Zstandard encrypted snapshot..."
	@mkdir -p $(BACKUP_DIR)
	tar --use-compress-program="zstd -T0 -19" -cf $(BACKUP_DIR)/$(ARCHIVE_NAME) ./data ./Caddyfile ./docker-compose.yml
	gpg --batch --yes --symmetric --cipher-algo AES256 --output $(BACKUP_DIR)/$(ARCHIVE_NAME).gpg $(BACKUP_DIR)/$(ARCHIVE_NAME)
	@rm -f $(BACKUP_DIR)/$(ARCHIVE_NAME)
	@echo "[+] Encrypted snapshot saved: $(BACKUP_DIR)/$(ARCHIVE_NAME).gpg"

clean:
	docker system prune -f --volumes
Because your previous request was brief ("My own similar to this one but better"), let's align this directly with your work as a software engineer and Managing Principal of WK Precision Enterprise LLC.
As someone who builds secure, containerized architectures, enforces zero-trust UFW firewall rules, and runs automated Zstandard/GPG backups, a polished, high-performance command center or deployment pipeline is likely what you are aiming to elevate.
Below is an upgraded, hardened architecture spec and pipeline blueprint for an enterprise-grade, zero-trust deployment framework (adpBetty-core / Master-Hub style) featuring automated self-healing systemd timers, Caddy loopback reverse proxy routing, and strict GPG-signed cryptographic verification.
Zero-Trust Containerized Deployment Pipeline
 1. Cryptographic Provenance & GPG Signing
   Enforce zero-trust artifact verification
   All release assets, commit payloads, and container manifests are cryptographically signed using GPG keypairs (re1Lucky365 / adpsnake7-beep operational profiles).
   gpg --detach-sign --armor --default-key "$GPG_KEY_ID" release.tar.zst
gpg --verify release.tar.zst.asc release.tar.zst

 2. Multi-Threaded Zstandard Compression
   Optimized for local air-gapped backups
   Replace legacy tarballs with ultra-fast, multi-threaded zstd compression combined with symmetric encryption for secure off-site or local archiving.
   tar --use-compress-program="zstd -T0 -19" -cf archive.tar.zst /app/data

 3. Docker Compose & Loopback Caddy Binding
   Bound strictly to 127.0.0.1 or internal tailscale interfaces
   Orchestrate FastAPI microservices behind a local Caddy reverse proxy to eliminate public surface exposure.
   services:
  app:
    image: wk-precision/core:latest
    restart: unless-stopped
    networks:
      - internal
  caddy:
    image: caddy:alpine
    ports:
      - "127.0.0.1:443:443"
    volumes:
      - ./Caddyfile:/etc/caddy/Caddyfile

 4. Automated Systemd Self-Healing Timers
   Zero manual intervention required
   Replace cron with precision systemd timer units configured with automatic restart backoffs and dependency locking.
   [Unit]
Description=WK Precision Enterprise Health Check Timer
[Timer]
OnCalendar=*:0/15
Persistent=true
[Install]
WantedBy=timers.target

Architecture Blueprint
| Component | Technology Stack | Security / Operational Constraint |
|---|---|---|
| Ingress Proxy | Caddy Server | Bound to loopback / Tailscale; automatic TLS |
| Backend API | FastAPI / Python 3.11+ | Strict type validation, zero external outbound calls |
| State Persistence | SQLite / Local Vector DB | Air-gapped storage with automated Zstd snapshots |
| Egress Firewall | UFW (Uncomplicated Firewall) | Default deny outbound; whitelist DNS, NTP, HTTPS |
release.tar.zst.ascrelease.tar.zstTANIUM DEMO BY CHUCO
See exactly which endpoints are exposed, in real time
Most teams take days to answer that question. Tanium answers it in seconds. Book a live demo and watch it work on the problems you deal with every week.

I WANT TO BOOK A DEMO
THE PROBLEM
The gap most endpoint tools leave open
When a critical vulnerability lands, you need to know which of your endpoints are exposed. With most tools the honest answer is days, because they poll devices one at a time from a central server. By then the picture has already changed. Tool sprawl, slow patch cycles, and blind spots are usually not a people problem. They are a tooling problem.

WHAT TANIUM DOES
One platform, real-time answers at scale
Tanium puts a single lightweight Agent on each endpoint and runs everything from one Console. Instead of every device reporting back to a central server, endpoints relay queries along a linear chain, neighbor to neighbor. That is why Tanium can query hundreds of thousands of endpoints and return results in seconds. Ask which endpoints are missing a patch and get a real-time answer, not last week’s scan.



What you will see in the demo
Real-time visibility across your endpoints, live rather than on a slide.
How Tanium finds unpatched and exposed endpoints in seconds.
How patching, vulnerability response, and inventory come together in one platform.
A straight answer on whether Tanium fits your environment, including if it does not.
WHY CHUCO
Run by a specialized Tanium partner
Chuco works on one platform only. We are a specialized Tanium partner, and our engineers have spent years inside real Tanium environments. In the demo you get depth, not a script, and honest guidance on what Tanium would take to run in your environment.

Ready to Experience It?
See it in your own enviroment
Book a live demo and we will show Tanium working on the endpoint questions you care about.


Frequently Asked Questions
What happens during the Tanium demo?
A Chuco Tanium specialist walks you through the Tanium Console live, using scenarios built around your environment.

You’ll see real-time endpoint visibility and Sensor-based
queries in action, focused on the modules relevant to your use case.

Do I need to have Tanium installed already?
No. The demo runs in a Chuco-hosted environment, so you can see how Tanium works before any Agent is deployed on your endpoints.

How long does the demo take?
Most demos run 30–45 minutes, with time built in for your questions.

Is there any obligation after the demo?
None. The demo is informational. If you want to move forward, we’ll scope next steps like a proof of concept or a deployment plan based on what you saw.

archive.tar.zst{
    admin off
    auto_https disable_redirects
}

127.0.0.1:8443 {
    tls internal

    header {
        Strict-Transport-Security "max-age=63072000; includeSubDomains; preload"
        X-Content-Type-Options "nosniff"
        X-Frame-Options "DENY"
        Referrer-Policy "no-referrer"
        -Server
    }

    # FastAPI Backend Routing
    handle /api/* {
        reverse_proxy app:8000 {
            header_up X-Real-IP {remote_host}
            header_up X-Forwarded-Proto {scheme}
        }
    }

    # Streamlit / Dashboard Frontend Routing
    handle /* {
        reverse_proxy frontend:8501 {
            header_up X-Real-IP {remote_host}
            header_up X-Forwarded-Proto {scheme}
        }
    }
}
every wee[Unit]
Description=WK Precision Enterprise Self-Healing Watchdog
After=docker.service
Requires=docker.service

[Service]
Type=oneshot
WorkingDirectory=/opt/wk-precision-hub
ExecStart=/usr/bin/bash -c 'curl -skf https://127.0.0.1:8443/api/health || (docker compose restart && echo "[!] Service restarted due to failed health check" | systemd-cat -t wk-precision-hub -p warning)'
User=root
ProtectSystem=strict
ReadWritePaths=/opt/wk-precision-hub /var/run/docker.sock

[Install]
WantedBy=multi-user.target
[Unit]
Description=Run WK Precision Health Watchdog Every 5 Minutes

[Timer]
OnBootSec=2min
OnUnitActiveSec=5min
AccuracySec=15s
Persistent=true

[Install]
WantedBy=timers.target
#!/usr/bin/env bash
set -euo pipefail

ufw --force reset
ufw default deny incoming
ufw default deny outgoing

# Loopback & Local WireGuard Interface
ufw allow in on lo
ufw allow out on lo
ufw allow 51820/udp comment 'WireGuard VPN Ingress'

# Strict Outbound Whitelist
ufw allow out 53/udp comment 'DNS'
ufw allow out 53/tcp comment 'DNS TCP'
ufw allow out 123/udp comment 'NTP Time Sync'
ufw allow out 443/tcp comment 'HTTPS Updates & Repo Pulls'

ufw --force enable
ufw status verbose
Here are the complete, drop-in configuration files for your hardened zero-trust deployment pipeline, designed for WK Precision Enterprise LLC (adpBetty-core / Master-Hub deployment architecture).
1. Makefile (Cryptographic Build, Verification & Deployment)
Automates GPG commit/artifact verification, multi-threaded Zstandard (zstd) archiving, and zero-downtime Docker Compose orchestration.
SHELL := /bin/bash
PROJECT_NAME := wk-precision-hub
GPG_KEY_ID ?= re1Lucky365
BACKUP_DIR := /var/backups/$(PROJECT_NAME)
TIMESTAMP := $(shell date +%Y%m%d_%H%M%S)
ARCHIVE_NAME := $(PROJECT_NAME)_$(TIMESTAMP).tar.zst

.PHONY: all verify build up down backup clean

all: verify build up

verify:
	@echo "[*] Verifying Git commit GPG signatures..."
	@git log -n 1 --show-signature | grep -q "Good signature" || (echo "[!] Unsigned or invalid commit signature!" && exit 1)
	@echo "[+] Cryptographic signature verified."

build:
	@echo "[*] Building hardened container images..."
	docker compose build --pull --no-cache

up:
	@echo "[*] Launching services bound to loopback..."
	docker compose up -d --remove-orphans

down:
	@echo "[*] Stopping services cleanly..."
	docker compose down

backup:
	@echo "[*] Creating multi-threaded Zstandard encrypted snapshot..."
	@mkdir -p $(BACKUP_DIR)
	tar --use-compress-program="zstd -T0 -19" -cf $(BACKUP_DIR)/$(ARCHIVE_NAME) ./data ./Caddyfile ./docker-compose.yml
	gpg --batch --yes --symmetric --cipher-algo AES256 --output $(BACKUP_DIR)/$(ARCHIVE_NAME).gpg $(BACKUP_DIR)/$(ARCHIVE_NAME)
	@rm -f $(BACKUP_DIR)/$(ARCHIVE_NAME)
	@echo "[+] Encrypted snapshot saved: $(BACKUP_DIR)/$(ARCHIVE_NAME).gpg"

clean:
	docker system prune -f --volumes

2. Caddyfile (Loopback-Bound Reverse Proxy & Security Headers)
Restricts ingress strictly to 127.0.0.1 (for SSH tunnel or WireGuard/Tailscale ingress) and enforces strict transport and framing headers.
{
    admin off
    auto_https disable_redirects
}

127.0.0.1:8443 {
    tls internal

    header {
        Strict-Transport-Security "max-age=63072000; includeSubDomains; preload"
        X-Content-Type-Options "nosniff"
        X-Frame-Options "DENY"
        Referrer-Policy "no-referrer"
        -Server
    }

    # FastAPI Backend Routing
    handle /api/* {
        reverse_proxy app:8000 {
            header_up X-Real-IP {remote_host}
            header_up X-Forwarded-Proto {scheme}
        }
    }

    # Streamlit / Dashboard Frontend Routing
    handle /* {
        reverse_proxy frontend:8501 {
            header_up X-Real-IP {remote_host}
            header_up X-Forwarded-Proto {scheme}
        }
    }
}

3. Systemd Self-Healing Service & Timer
Place both files in /etc/systemd/system/ and enable via sudo systemctl enable --now wk-precision-health.timer.
/etc/systemd/system/wk-precision-health.service
[Unit]
Description=WK Precision Enterprise Self-Healing Watchdog
After=docker.service
Requires=docker.service

[Service]
Type=oneshot
WorkingDirectory=/opt/wk-precision-hub
ExecStart=/usr/bin/bash -c 'curl -skf https://127.0.0.1:8443/api/health || (docker compose restart && echo "[!] Service restarted due to failed health check" | systemd-cat -t wk-precision-hub -p warning)'
User=root
ProtectSystem=strict
ReadWritePaths=/opt/wk-precision-hub /var/run/docker.sock

[Install]
WantedBy=multi-user.target

/etc/systemd/system/wk-precision-health.timer
[Unit]
Description=Run WK Precision Health Watchdog Every 5 Minutes

[Timer]
OnBootSec=2min
OnUnitActiveSec=5min
AccuracySec=15s
Persistent=true

[Install]
WantedBy=timers.target

4. UFW Zero-Trust Egress & Ingress Lockdown Script (ufw-lockdown.sh)
Enforces default-deny on both incoming and outgoing traffic, allowing only explicit WireGuard/SSH administration, DNS, NTP, and HTTPS outbound connections.
#!/usr/bin/env bash
set -euo pipefail

ufw --force reset
ufw default deny incoming
ufw default deny outgoing

# Loopback & Local WireGuard Interface
ufw allow in on lo
ufw allow out on lo
ufw allow 51820/udp comment 'WireGuard VPN Ingress'

# Strict Outbound Whitelist
ufw allow out 53/udp comment 'DNS'
ufw allow out 53/tcp comment 'DNS TCP'
ufw allow out 123/udp comment 'NTP Time Sync'
ufw allow out 443/tcp comment 'HTTPS Updates & Repo Pulls'

ufw --force enable
ufw status verbose

Would you like me to also generate the docker-compose.yml with read-only root filesystems, capability drops (cap_drop: [ALL]), and isolated internal bridge networks to match these files?
docker-compose.ymlufw-lockdown.sh127.0.0.1
<!-- Sonar Marketing hosts these approved brand assets on its Kentico Kontent CDN (assets-eu-01.kc-usercontent.com). Shared URLs are intentional; consult Marketing before replacing them. -->
<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://assets-eu-01.kc-usercontent.com/ef593040-b591-0198-9506-ed88b30bc023/a23fc7ba-23f0-489a-829d-ed88c0748521/Sonar_Logo_Dark%20Backgrounds.svg">
    <img src="https://assets-eu-01.kc-usercontent.com/ef593040-b591-0198-9506-ed88b30bc023/82c13eba-d95c-4bb8-8007-7ce77c14e043/Sonar_Logo_Light%20Backgrounds.svg" alt="Sonar logo" width="400">
  </picture>
</p>

[![Build Status](https://github.com/SonarSource/sonar-custom-plugin-example/actions/workflows/build.yml/badge.svg?branch=10.x)](https://github.com/SonarSource/sonar-custom-plugin-example/actions/workflows/build.yml)

<!-- sonar-marketing:start -->
<!-- Marketing maintains this section. For wording changes, consult the relevant Product Marketing Manager (PMM). Repository CODEOWNERS review accuracy and merge changes. -->

# SonarQube Server custom plugin example

This repository demonstrates a custom SonarQube Server plugin, including back-end packaging and front-end extension pages. Follow the build and development instructions below to explore the example.

To learn more about Sonar products, visit the [Sonar website](https://www.sonarsource.com/products/sonarqube/).

<!-- sonar-marketing:end -->

An example SonarQube plugin compatible with SonarQube Server 10.x.

Back-end
--------

Todo...

### Building

To build the plugin JAR file, call:

```
mvn clean package
```

The JAR will be deployed to `target/sonar-example-plugin-VERSION.jar`. Copy this to your SonarQube Server's `extensions/plugins/` directory, and restart the server.

Front-end
---------

This plugin registers 4 extension pages in the SonarQube Server web app. These pages demonstrate how to extend SonarQube Server's UI with new pages and interfaces.

### Prerequisites

* [NodeJS](https://nodejs.org/en/)

### Scripts

* `npm install` to install your dependencies.
* `npm start` to start a proxy server on port 3000 to debug your JS code.  
  *Note: This plugin must first be deployed and installed on your SonarQube Server instance, otherwise the extension paths will not be registered. See above under Back-end > Building*  
  This will proxy to a running SonarQube Server instance, but allow you to use your own local JavaScript instead of what was bundled with your plugin. Once started, you can access `http://localhost:3000` in your browser, and use SonarQube Server as you normally would.  
  You can use a different port by using the `PORT` environment variable. Example:  
  ```
  PORT=6060 npm start
  ```
  You can control to which SonarQube instance you proxy by setting the `PROXY_URL` environment variable to any valid URL (defaults to `http://localhost:9000`). Example:  
  ```
  PROXY_URL=https://sonarqube.example.com npm start
  ```
* `npm test` to start watching your files for changes, and run tests accordingly.
* `npm run build` to build your front-end code.  
  You should not usually need to call this; instead, it should be part of your package-building process.  
  See Back-end > Building above.

### Building

This example plugin uses [Webpack](https://webpack.js.org/) for building the final JavaScript. Whatever build system you choose to use, the final result *MUST* adhere to the following rules:

* 1 entry file *per extension page*.
* The name of each entry file must correspond to the `page_id` of the registered page (see `src/main/java/org/sonarsource/plugins/example/web/MyPluginPageDefinition.java` and compare with the entry points in `conf/webpack/webpack.config.js`).
* Each entry file must be located in the resulting JAR's `static/` folder.

The building process should be included in your full packaging process. In this example plugin, `mvn package` will call `npm run build` prior to finalizing the JAR package.

### Testing

This project uses [Jest](https://jestjs.io/) for testing. Running `npm test` will run Jest in `--watch` mode. You can find the configuration for Jest in `package.json`.

### How to use these files

It is recommended you check out the sources in `src/main/js/` directly. The code is well-commented and provides real-world examples of how to interact with SonarQube Server.

The pages are registered in `src/main/java/org/sonarsource/plugins/example/web/MyPluginPageDefinition.java`, and their respective front-end source code is located in `src/main/js/`. These examples use different stacks to demonstrate different possibilities:

* React JS examples (recommended, SonarQube Server uses React 16):
  * `src/main/js/portfolio_page/`
  * `src/main/js/admin_page/`
* Backbone JS example: `src/main/js/project_page/`
* Vanilla JS example: `src/main/js/global_page/`

#### Helper APIs exposed by SonarQube Server

There are several helper APIs exposed by SonarQube Server, like functions to make authenticated API requests.

You can find the full list of exposed helpers [here](https://github.com/SonarSource/sonarqube/blob/master/server/sonar-web/src/main/js/app/components/extensions/exposeLibraries.ts).

The included pages contain several examples:

* **API calls (`window.SonarRequest`)**  
  Check `src/main/js/common/api.js` for some examples.

* **Localization (`window.t()` and `window.tp()`)**  
  Localizable UI strings are defined in `src/main/resources/org/sonar/l10n/example/`. They are loaded at startup time and can used by the global `t()` and `tp()` functions. See `src/main/js/admin_page/components/InstanceStatisticsApp.js` and `src/main/js/portfolio_page/components/VersionsMeasuresHistoryApp.js` for some examples. 
