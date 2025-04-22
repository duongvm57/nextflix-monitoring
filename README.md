# Loki Monitoring Stack

## 🧱 Requirements
- Any operating system that supports Docker (Linux, Windows, macOS)
- Docker & Docker Compose

## ⚙️ Installing Docker
```bash
sudo apt update && sudo apt install -y docker.io docker-compose
sudo systemctl enable docker --now
```

## 🚀 Starting the System
```bash
# Clone repository
git clone <repository-url>
cd nextflix-monitoring

# Start services
docker-compose up -d
```

## 📊 Accessing Grafana
- URL: http://<your-server-ip>:3000
- Username: admin
- Password: admin

## 🔍 Configuring Grafana
1. Log in to Grafana
2. Add Loki as a data source:
   - URL: http://loki:3100
3. Create dashboards to monitor logs

## 📋 Collected Logs
- Nginx logs: `/var/log/nginx/*.log`
- System logs: `/var/log/syslog`
- Auth logs: `/var/log/auth.log`

## 🔄 Updating Configuration
If you want to add other log sources, edit the `promtail-config.yml` file and restart Promtail:
```bash
docker-compose restart promtail
```
