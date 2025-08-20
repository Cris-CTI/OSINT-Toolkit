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
# 1. Email Checker
export HIBP_API_KEY="YOUR_API_KEY"   # On Windows: set HIBP_API_KEY=YOUR_API_KEY
```bash
python scripts/email_checker.py test@example.com

# Sample output
Email: test@example.com
Found in breaches:
- Adobe (2013)
- LinkedIn (2012)
- Dropbox (2016)
```
<img width="952" height="186" alt="email_checker" src="https://github.com/user-attachments/assets/781138a7-0c07-4681-b9d6-6487d433f882" />

```bash
# 2. EXIF Metadata
python scripts/image_metadata.py

# Sample output
No EXIF data found
```
<img width="1271" height="67" alt="exif_info" src="https://github.com/user-attachments/assets/6f1d9fee-8c85-4392-b219-33b655f4741c" />

```bash
# 3. Basic WHOIS / DNS
python scripts/whois_lookup.py example.com

# Sample output
WHOIS:
domain_name: EXAMPLE.COM
registrar: RESERVED-Internet Assigned Numbers Authority
creation_date: 1995-08-14
expiration_date: 2026-08-13
name_servers: ['A.IANA-SERVERS.NET', 'B.IANA-SERVERS.NET']
status: ['clientDeleteProhibited', 'clientTransferProhibited', 'clientUpdateProhibited']
Resolved IP: 23.215.0.136

```
<img width="1905" height="591" alt="whois_info" src="https://github.com/user-attachments/assets/7c63aa47-ecf4-4660-90e6-8cfc1e7c27d7" />

```bash
# 4. Social Media Scraper 
python scripts/social_media_scraper.py username

# Sample output
Username: username
Profile found: Yes
Posts: 123
Followers: 456
Following: 78

```
<img width="958" height="180" alt="social_media_output" src="https://github.com/user-attachments/assets/4a5a2776-97f2-4bb3-9196-2cdefc04a644" />

```bash
# 5. IP Information 
python scripts/ip_info.py 8.8.8.8

# Sample output
{'status': 'success', 'country': 'United States', 'countryCode': 'US', 'region': 'VA', 'regionName': 'Virginia', 'city': 'Ashburn', 'zip': '20149', 'lat': 39.03, 'lon': -77.5, 'timezone': 'America/New_York', 'isp': 'Google LLC', 'org': 'Google Public DNS', 'as': 'AS15169 Google LLC', 'query': '8.8.8.8'}

```
<img width="950" height="321" alt="ip_info" src="https://github.com/user-attachments/assets/eb45551d-9082-439c-b6d0-e08a839cfca6" />


## - Project structure

```bash
OSINT-Toolkit/
├── scripts/
│   ├── email_checker.py
│   ├── image_metadata.py
│   ├── whois_lookup.py
│   ├── social_media_scraper.py  
│   └── ip_info.py              
├── examples/
│   ├── sample_email_output.txt
│   ├── sample_domain_output.txt
│   ├── sample_image.jpg
│   ├── sample_email_output.png
│   ├── sample_domain_output.png
│   ├── sample_image_output.png
│   └── sample_ip_output.png
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
