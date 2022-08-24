.
├── LICENSE
├── alertmanager
│   └── config.yml
├── caddy
│   └── Caddyfile
├── config
├── docker-compose.exporters.yml
├── docker-compose.yml
├── grafana
│   └── provisioning
│       ├── dashboards
│       │   ├── dashboard.yml
│       │   ├── docker_containers.json
│       │   ├── docker_host.json
│       │   ├── monitor_services.json
│       │   └── nginx_container.json
│       └── datasources
│           └── datasource.yml
├── helpers
│   └── aws
│       ├── cadvisor_ecs_task_definition.json
│       ├── node_exporter_task_definition.json
│       └── prometheus.yml
├── prometheus
│   ├── alert.rules
│   └── prometheus.yml


Berikut container yang akan dijalankan nantinya:
Prometheus (metrics database). Bisa diakses di alamat http://host:9090
Prometheus-Pushgateway (push acceptor for ephemeral and batch jobs). Bisa diakses di alamat http://host:9091
AlertManager (alerts management). Bisa diakses di alamat http://:9093
Grafana (visualize metrics). Bisa diakses di alamat http://host:3000
NodeExporter (host metrics collector)
cAdvisor (containers metrics collector)
Caddy (reverse proxy and basic auth provider for prometheus and alertmanager)
Menurut saya sudah cukup lengkap untuk keperluan monitoring.

Kalian edit sendiri mana yang perlu diedit. Untuk percobaan awal kita eksekusi saja konfigurasi defaultnya.
Build menggunakan docker-compose dengan perintah:


ADMIN_USER=admin ADMIN_PASSWORD=admin docker-compose up -d


Kalian bisa masuk ke Grafana di port yang sudah di sesuaikan.




ya gitu deh.
