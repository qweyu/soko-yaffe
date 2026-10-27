# Soko Yaffe – community farm market (Flask)

Farmers post produce, buyers search and contact them directly by phone or WhatsApp, and everyone sees a price board.

**Stack:** HTML + CSS, JavaScript (`static/app.js`), Python Flask + SQLite (`app.py`).

## Run it in VS Code

1. Install Python 3.10+ and VS Code (extensions: **Python**, **Live Server** optional).
2. Open this folder: File → Open Folder → `soko-yaffe`.
3. Open the terminal (Terminal → New Terminal) and run:

   Windows:
   ```
   python -m venv venv
   venv\Scripts\activate
   pip install -r requirements.txt
   python app.py
   ```
   Mac / Linux:
   ```
   python3 -m venv venv
   source venv/bin/activate
   pip install -r requirements.txt
   python app.py
   ```
4. Open http://127.0.0.1:5000. Or press **F5** and pick "Run Soko Yaffe (Flask)".

Sample listings and prices are added the first time it runs. The database is the file `market.db` (delete it to reset).

## How it works

| File | Job |
|---|---|
| `app.py` | Routes, login, listings, prices, JSON API, database setup |
| `templates/` | HTML pages (Jinja) |
| `static/app.js` | Search, filters, listing cards, price charts |
| `static/style.css` | Design (light and dark) |

- **First account created becomes a price agent**, who can update the price board.
- Farmers log in with phone number and password, post listings, and can remove their own.
- Change the site name, categories, and districts at the top of `app.py`.

## Before going live

- Set a secret key: `SECRET_KEY=<long random text>` as an environment variable.
- Run with a production server (e.g. `pip install gunicorn`, then `gunicorn app:app`) and use HTTPS.
- Add phone verification (SMS code), password reset, and an admin page to remove abuse.
- Hosting options: PythonAnywhere, Render, Railway. Back up `market.db` regularly (or move to PostgreSQL).
- Replace the sample listings (fake numbers 0700000001 etc.) with real data.

## Ideas to build next

SMS or WhatsApp price alerts, buyer ratings, Luganda translation, group selling, transport matching, mobile money.
