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

Sample output:
Email: test@example.com
Found in breaches:
- Adobe (2013)
- LinkedIn (2012)
- Dropbox (2016)
<img width="952" height="186" alt="email_checker" src="https://github.com/user-attachments/assets/7763e8e2-819b-4c03-9247-a721d9e66ad4" />


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
│   ├── image_metadata.py
│   ├── whois_lookup.py
│   ├── social_media_scraper.py  # optional
│   └── ip_info.py               # optional
├── examples/
│   ├── sample_email_output.txt
│   ├── sample_domain_output.txt
│   └── sample_image.jpg
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
