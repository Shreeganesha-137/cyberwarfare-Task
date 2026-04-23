# Task 3: Container Monitoring (Monitoring)

## Objective

Objective
To monitor Docker container CPU and memory usage automatically with timestamps.

Directory Setup

sudo mkdir -p /opt/container-monitor/logs

📜 Monitoring Script

monitor.sh

CONTAINER_NAME="web-container"
LOG_DIR="/opt/container-monitor/logs"
LOG_FILE="$LOG_DIR/monitor.log"

TIMESTAMP=$(date "+%Y-%m-%d %H:%M:%S")

STATS=$(docker stats --no-stream --format "{{.Name}} {{.CPUPerc}} {{.MemUsage}}" | grep $CONTAINER_NAME)

echo "$TIMESTAMP $STATS" >> $LOG_FILE
chmod +x monitor.sh

Setup Cron Job
crontab -e

* * * * * /path/to/monitor.sh  Allways Run

View Logs
cat /opt/container-monitor/logs/monitor.log

✅ Outcome
Container resource usage logged every minute
Logs include timestamp, CPU, and memory usage