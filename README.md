# Crypto Market Pulse

Dockerized data engineering project for cryptocurrency market ingestion, PostgreSQL storage, FastAPI dashboard, and email alerts.

## Features

- Binance daily OHLCV historical sync
- Near real-time Binance ticker snapshots
- PostgreSQL storage
- CoinGecko market metadata enrichment
- FastAPI web dashboard
- Market Pulse dashboard
- Daily History dashboard
- Live Snapshots dashboard
- Data Health monitoring
- Alert Center with all-market alert rules
- SMTP email alert support
- Docker Compose one-command startup

## Services

- postgres
- realtime_ingestor
- daily_sync
- coingecko_sync
- alert_worker
- web_app

## Setup

Copy environment example:

cp .env.example .env

Edit .env and set your local values.

For Gmail alerts, use a Gmail App Password, not your normal Gmail password.

## Run

docker compose up -d --build

Open dashboard:

http://localhost:8000

## Stop

docker compose down

Do not use docker compose down -v unless you want to delete the PostgreSQL Docker volume.

## Useful Logs

docker logs -f crypto_web_app
docker logs -f crypto_realtime_ingestor
docker logs -f crypto_alert_worker
docker logs -f crypto_daily_sync
docker logs -f crypto_coingecko_sync

## Security

Never commit .env, Gmail App Passwords, database dumps, or personal credentials.

Use .env.example for public configuration examples.

## License

MIT License.
