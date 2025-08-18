# 🕵️ OSINT Toolkit

Conjunto de **scripts básicos de OSINT** pensados para analistas junior de ciberinteligencia.  
Incluye ejemplos y salidas para que puedas aprender paso a paso.

## 📌 Scripts incluidos
- **email_checker.py** → Consulta si un correo aparece en filtraciones (requiere API key de HaveIBeenPwned).  
- **image_metadata.py** → Extrae metadatos EXIF de imágenes (cámara, fecha, GPS si existe).  
- **whois_lookup.py** → Obtiene información pública de dominios y resolución básica de IPs.

## 🚀 Uso rápido
```bash
# Crear entorno e instalar dependencias
python -m venv .venv && source .venv/bin/activate  # en Windows: .venv\Scripts\activate
pip install -r requirements.txt

# 1) Email checker (requiere HIBP API KEY)
export HIBP_API_KEY="TU_API_KEY"   # en Windows: set HIBP_API_KEY=TU_API_KEY
python scripts/email_checker.py test@example.com

# 2) Metadatos EXIF
python scripts/image_metadata.py examples/ejemplo_imagen.jpg

# 3) WHOIS / DNS básico
python scripts/whois_lookup.py ejemplo.com
```

## 🧰 Requisitos
- Python 3.10+
- Dependencias en `requirements.txt`

## 📁 Estructura
```
OSINT-Toolkit/
├── scripts/
│   ├── email_checker.py
│   ├── image_metadata.py
│   └── whois_lookup.py
├── examples/
│   ├── ejemplo_salida_email.txt
│   └── ejemplo_imagen.jpg (añádela tú)
├── requirements.txt
├── LICENSE
└── README.md
```

> Proyecto educativo. No utilices estos scripts de forma que infrinja términos de servicio o leyes aplicables.
