# AppsMagic LogHub

Centralized logging service for AppsMagic microservices.

## What this does
- Runs Fluent Bit in a standalone container/repo
- Tails MagicEvent API logs from host path
- Accepts forward logs from other services on port `24224`
- Writes centralized logs to `./data/appsmagic-central.log`

## Deploy (EC2)
```bash
cd /home/ubuntu/Ws/appsmagic-loghub
docker compose up -d
```

## Configure log source path
Default MagicEvent log path:
`/home/ubuntu/Ws/magic-event-manager/api/logs`

Override with env:
```bash
MAGIC_EVENT_LOG_PATH=/custom/path docker compose up -d
```

## Future OpenSearch
Replace `file` output blocks with OpenSearch output in `fluent-bit.conf`.
