# OSINT toolkit

Set of basic OSINT scripts designed for junior cyber intelligence analysts. Includes examples and sample outputs so you can learn step by step. Your essential toolkit to collect, explore, and analyze public information efficiently.

## Included scripts
- **email_checker.py** → Checks if an email appears in data breaches (requires a HaveIBeenPwned API key).
- **image_metadata.py** → Extracts EXIF metadata from images (camera, date, GPS if available). 
- **whois_lookup.py** → Retrieves public information about domains and basic IP resolution.

## Quick start
```bash
# Create environment and install dependencies
python -m venv .venv && source .venv/bin/activate  # on Windows: .venv\Scripts\activate
pip install -r requirements.txt

# 1) Email checker (requires HIBP API KEY)
export HIBP_API_KEY="YOUR_API_KEY"   # on Windows: set HIBP_API_KEY=YOUR_API_KEY
python scripts/email_checker.py test@example.com

# 2) EXIF metadata
python scripts/image_metadata.py examples/sample_image.jpg

# 3) Basic WHOIS / DNS
python scripts/whois_lookup.py example.com
```

## Requirements
- Python 3.10+
- Dependencies listed in `requirements.txt`

## Structure
```
OSINT-Toolkit/
├── scripts/
│   ├── email_checker.py
│   ├── image_metadata.py
│   └── whois_lookup.py
├── examples/
│   ├── sample_email_output.txt
│   └── sample_image.jpg (add it yourself)
├── requirements.txt
├── LICENSE
└── README.md
```

This is an educational project. Please DO NOT use these scripts in ways that violate terms of service or applicable laws.
