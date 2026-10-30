# News Aggregator Dashboard

One full-stack project combining the former `Qimatxbase/Back_end` and
`Qimatxbase/Frontend` repositories. The Flask API collects news, stores it in
MongoDB, and serves data and chart endpoints to the React dashboard.

This is separate from the Call Your Shot / CYS Solar hackathon.

## Structure

```text
backend/     Flask, news collectors, MongoDB access and backend tests
frontend/    React dashboard and chart visualisations
```

Both original development histories are retained beneath these component
directories after removing committed environments, bytecode and private
configuration. The canonical repository is
[news_aggregator_dashboard](https://github.com/Qimatxbase/news_aggregator_dashboard).

## Run

Use Python 3.11+, Node.js and an accessible MongoDB deployment. News collection
also requires your own NewsAPI and Guardian API keys. This application connects
to MongoDB during backend import and is not an offline demo.

```bash
# From the repository root:
python3.11 -m venv .venv
source .venv/bin/activate
python -m pip install -r backend/requirements.txt
cp backend/.env.example backend/.env
# Edit backend/.env with your own configuration, then:
cd backend
python app.py
```

In another terminal:

```bash
cd frontend
npm ci
npm start
```

The backend listens on <http://localhost:5000>; React runs on
<http://localhost:3000>. Current frontend API URLs use localhost:5000.
Backend tests live in `backend/tests/`; they require the configured external
services and are not treated as offline validation.

[Portfolio index](https://github.com/Qimatxbase/engineering_portfolio)
