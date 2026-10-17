FLIENT-PAPA Render fix

Fixes the malformed JSON string by parsing a validated JSON payload and provides a Flask WSGI app for Gunicorn.

Render settings:
Build command: pip install -r requirements.txt
Start command: gunicorn bot:app --bind 0.0.0.0:$PORT
Health check path: /health

Endpoints: /health, /config.json, /download. admin.html is a basic backend status tester, not a secure admin panel.

Security: /config.json and /download are public, as in the previous server. Anyone with the URL can retrieve the config. This package does not connect Firebase or provide token expiry/revocation. Add server-side auth before using private configurations.
