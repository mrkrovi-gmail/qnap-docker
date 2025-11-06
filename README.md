# QNAP Zabbix Stack (Portainer GitOps)

## Služby
- PostgreSQL 16
- Zabbix Server 7.0 (pgsql)
- Zabbix Frontend (nginx, pgsql) – UI na `http://NAS:8081`

## Nasazení v Portaineru
1. Stacks → Add stack → Repository  
   URL: `https://github.com/mrkrovi-gmail/qnap-docker.git`  
   Compose path: `docker-compose.yml`
2. Env vars: nastav `POSTGRES_PASSWORD` (v Portaineru).
3. Deploy. Při prázdné DB Zabbix sám inicializuje schéma.

## Poznámky
- Perzistence dat: `/share/Container/zabbix/...` na QNAPu.
- Kolize portů vyřešíš změnou mapování a Update stacku.
- Auto-redeploy: použij Portainer **Webhook** (volitelné).
