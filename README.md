# MU Library Seat Management System - Labs 8 & 9 (ICT461, Dennis Sampa 202302571)

## Run
    python -m pip install -r requirements.txt     # includes websockets and brotli
    copy .env.example .env                        # then fill in the secrets (never commit .env)
    python app.py                                 # web 5000, WebSocket 5050
    python serve_https.py                         # https://localhost:8443 + wss (needs certs/, see make_certs.sh)
Open http://localhost:5000 (student) and http://localhost:5000/admin (librarian PIN from .env).

## Tests
    python -W ignore -m unittest tests.test_ws tests.test_security -v      # 17 WebSocket tests + 19 security tests

## Lab 9 front-end build (only needed if you edit static/src/*)
    cd ../tools && npm install && node build.mjs     # writes static/dist/*-<hash>.js|css + manifest.json (already built in this zip)

## Evidence scripts (../evidence)
handshake_demo.py, browser_lab8.js (Playwright), ws_stress.py, perf_probe.js, db_bench.py, lh.sh / lh_admin.sh / lh_summary.py (Lighthouse).
Development-only switch: MU_IGNORE_HOURS=1 with APP_ENV=development ignores closing hours so the tests can run at any time.
