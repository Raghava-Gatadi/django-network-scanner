# Django Network Scanner

A Python/Django learning project that discovers hosts on a local network using Scapy ARP packets, then checks a selected TCP port range. Results show device IP addresses, MAC addresses, and port/service labels in a web page.

## Repository map

- [scanner/views.py](scanner/views.py): ARP discovery, TCP probes, and request handling.
- [templates/home.html](templates/home.html): scan form and results.
- [Network_Scanner/](Network_Scanner/): Django project configuration.
- [manage.py](manage.py): Django management entry point.

## Setup outline

Requires Python, Django, Scapy, and an environment that permits raw-packet operations. The repository **does not currently include a requirements.txt**, so the old `pip install -r requirements.txt` instruction was not usable.

Create a fresh virtual environment and install Django and Scapy, then review the project settings for your machine. Dependency versions are not pinned and current-version compatibility has not been established.

```sh
python3 -m venv .venv
. .venv/bin/activate
python3 -m pip install django scapy
python3 manage.py runserver 127.0.0.1:8000
```

Open `http://127.0.0.1:8000`. Scan only a lab network you are authorized to test. Raw packets may require additional operating-system permissions; do not expose an elevated development server to an untrusted network.

## Current limits

This is synchronous learning code with simple TCP response checks, not a production asset inventory. Port/service labels are guesses from a static mapping, not verified service fingerprints. No automated scan validation or runtime compatibility check was performed during the documentation update.

An earlier copy is preserved in [cybersecurity](https://github.com/Raghava-Gatadi/cybersecurity).
