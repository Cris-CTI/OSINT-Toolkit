<img width="933" height="382" alt="OSINT TOOLKIT CRISCTI" src="https://github.com/user-attachments/assets/706e5beb-62e8-4f37-a212-d7d549f290ee" />

[![Python](https://img.shields.io/badge/python-3.10+-blue)](https://www.python.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

---


# OSINT Toolkit

Set of basic OSINT scripts designed for junior cyber intelligence analysts. Includes examples and sample outputs so you can learn step by step. Your essential toolkit to collect, explore, and analyze public information efficiently.

## Included scripts

| Script | Description |
|--------|-------------|
| `email_checker.py` | Checks if an email appears in data breaches (requires [HaveIBeenPwned API](https://haveibeenpwned.com/API/v3)). |
| `image_metadata.py` | Extracts EXIF metadata from images (camera, date, GPS if available). |
| `whois_lookup.py` | Retrieves public information about domains and basic IP resolution. |
| `social_media_scraper.py` | Searches for public information on social media profiles. |
| `ip_info.py`  | Collects IP geolocation and ASN information. |

---

## Quick start
## - Setup environment

```bash
# Create virtual environment
python -m venv .venv

# On Windows
.venv\Scripts\activate

# On Linux / Mac
source .venv/bin/activate

# Install dependencies
pip install -r requirements.txt
```

## - Example usage

```bash
# Email Checker
export HIBP_API_KEY="YOUR_API_KEY"   # On Windows: set HIBP_API_KEY=YOUR_API_KEY
python scripts/email_checker.py test@example.com

# EXIF Metadata
python scripts/image_metadata.py 

# Basic WHOIS / DNS
python scripts/whois_lookup.py example.com

# Social Media Scraper 
python scripts/social_media_scraper.py username

# IP Information 
python scripts/ip_info.py 8.8.8.8
```

## - Project structure

```bash
OSINT-Toolkit/
├── scripts/
│   ├── email_checker.py
import os
import requests
import sys

def check_email(email):
    api_key = os.getenv("HIBP_API_KEY")
    if not api_key:
        print("Error: Missing HIBP_API_KEY environment variable")
        return

    url = f"https://haveibeenpwned.com/api/v3/breachedaccount/{email}"
    headers = {
        "hibp-api-key": api_key,
        "User-Agent": "OSINT-Toolkit"
    }

    response = requests.get(url, headers=headers)

    if response.status_code == 200:
        breaches = response.json()
        print(f"[+] {email} found in {len(breaches)} breaches:")
        for b in breaches:
            print(f"  - {b['Name']} ({b['Domain']})")
    elif response.status_code == 404:
        print(f"[-] {email} not found in breaches")
    else:
        print(f"[!] Error: {response.status_code} {response.text}")

if __name__ == "__main__":
    if len(sys.argv) < 2:
        print("Usage: python email_checker.py <email>")
    else:
        check_email(sys.argv[1])

│   ├── image_metadata.py
from PIL import Image
from PIL.ExifTags import TAGS
import sys

def extract_metadata(image_path):
    try:
        image = Image.open(image_path)
        exif_data = image._getexif()

        if not exif_data:
            print("No EXIF metadata found.")
            return

        for tag, value in exif_data.items():
            tag_name = TAGS.get(tag, tag)
            print(f"{tag_name}: {value}")

    except Exception as e:
        print(f"Error reading image: {e}")

if __name__ == "__main__":
    if len(sys.argv) < 2:
        print("Usage: python image_metadata.py <image_path>")
    else:
        extract_metadata(sys.argv[1])

│   ├── whois_lookup.py
import whois
import socket
import sys

def lookup_domain(domain):
    try:
        w = whois.whois(domain)
        print("WHOIS Information:")
        for k, v in w.items():
            print(f"{k}: {v}")
    except Exception as e:
        print(f"Error performing WHOIS: {e}")

    try:
        ip = socket.gethostbyname(domain)
        print(f"\nResolved IP: {ip}")
    except Exception as e:
        print(f"Error resolving IP: {e}")

if __name__ == "__main__":
    if len(sys.argv) < 2:
        print("Usage: python whois_lookup.py <domain>")
    else:
        lookup_domain(sys.argv[1])

│   ├── social_media_scraper.py
import requests
import sys

platforms = {
    "Twitter": "https://twitter.com/{}",
    "Instagram": "https://www.instagram.com/{}/",
    "GitHub": "https://github.com/{}",
}

def check_username(username):
    print(f"Checking username: {username}\n")
    for name, url in platforms.items():
        full_url = url.format(username)
        try:
            response = requests.get(full_url)
            if response.status_code == 200:
                print(f"[+] Found on {name}: {full_url}")
            else:
                print(f"[-] Not found on {name}")
        except Exception as e:
            print(f"[!] Error checking {name}: {e}")

if __name__ == "__main__":
    if len(sys.argv) < 2:
        print("Usage: python social_media_scraper.py <username>")
    else:
        check_username(sys.argv[1])

│   └── ip_info.py
import requests
import sys

def get_ip_info(ip):
    url = f"https://ipinfo.io/{ip}/json"
    try:
        response = requests.get(url)
        if response.status_code == 200:
            data = response.json()
            print("IP Information:")
            for k, v in data.items():
                print(f"{k}: {v}")
        else:
            print(f"Error: {response.status_code}")
    except Exception as e:
        print(f"Request failed: {e}")

if __name__ == "__main__":
    if len(sys.argv) < 2:
        print("Usage: python ip_info.py <ip_address>")
    else:
        get_ip_info(sys.argv[1])
            
├── requirements.txt
├── LICENSE
└── README.md
```

## Requirements

```bash
# Python version
Python 3.10+

# Dependencies
requests
python-whois
pillow
beautifulsoup4
```

## Author

```bash
Cris-CTI – Threat Intelligence Analyst & Cybersecurity Specialist
Cybersecurity Awareness & Automation Expert
Power BI dashboards & automation for cybersecurity metrics
Phishing simulations, threat intelligence, and resilience training

# Connect with me
LinkedIn: https://www.linkedin.com/in/cristina-martinez-campos/
```
