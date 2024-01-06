# odoo-installation-howto

```
git clone git@github.com:odoo/odoo.git --branch 17.0 --depth 1
```
এখানে branch অর্থ কোন branch  আমরা clone করতে চাই। depth 1 অর্থ আমরা লাস্ট history টা রাখতে চাই। 

এরপর আমরা একটি custom directory তৈরি করি যাতে আমাদের custom addons গুলো রাখব।

এবার আমরা একটি virtual environment তৈরি করব যাতে আমাদের প্রয়োজনীয় সকল package গুলো install হবে। 

`python3 -m venv .venv`
এখানে .venv হচ্ছে virtual environment এর path

`source .venv/bin/activate`

`which python3`

To install the dependencies
`pip install -r requirements.txt`

`pip install wheel`

We want to install odoo as binary package

`pip install .`

Now odoo 17 will be installed.

`which odoo`

`mkdir .vscode/launch.json`
```
{
    "version": "0.2.0",
    "configurations": [
        {
            "name": "Odoo 17",
            "type": "python",
            "request": "launch",
            "python": "/home/mohiuddin/odoo17/.venv/bin/python3",
            "program": "/home/mohiuddin/odoo17/.venv/bin/odoo",
            "args": [
                "-c",
                "/home/mohiuddin/odoo17/.odoorc",
                "--dev",
                "all"
            ],
            "console": "integratedTerminal"
        }
    ]
}
```
`pip install inotify
`

```
[options]
addons_path = ~/odoo17/odoo/addons/, ~/odoo17/custom/
db_name = False
csv_internal_sep = ,
data_dir = /home/mohiuddin/.local/share/Odoo
db_host = localhost
db_maxconn = 64
db_password = 1234
db_port = 5432
db_sslmode = prefer
db_template = template0
db_user = mohiuddin
email_from = False
from_filter = False
geoip_database = /usr/share/GeoIP/GeoLite2-City.mmdb
gevent_port = 8072
http_enable = True
http_interface = 
http_port = 8069
import_partial = 
limit_memory_hard = 2684354560
limit_memory_soft = 2147483648
limit_request = 65536
limit_time_cpu = 60
limit_time_real = 120
limit_time_real_cron = -1
list_db = True
log_db = False
log_db_level = warning
log_handler = :INFO
log_level = info
logfile = 
max_cron_threads = 2
osv_memory_age_limit = False
osv_memory_count_limit = 0
pg_path = 
pidfile = 
proxy_mode = False
reportgz = False
screencasts = 
screenshots = /tmp/odoo_tests
server_wide_modules = base,web
syslog = False
test_enable = False
test_file = 
test_tags = None
transient_age_limit = 1.0
unaccent = False
upgrade_path = 
websocket_keep_alive_timeout = 3600
websocket_rate_limit_burst = 10
websocket_rate_limit_delay = 0.2
without_demo = False
workers = 0
x_sendfile = False
```

To debug now in vscode press `F5`
