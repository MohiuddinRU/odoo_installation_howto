# odoo-installation-howto

```
git clone git@github.com:odoo/odoo.git --branch 17.0 --depth 1
```

এখানে branch অর্থ কোন branch আমরা clone করতে চাই। depth 1 অর্থ আমরা লাস্ট history টা রাখতে চাই।

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
            "type": "debugpy",
            "request": "launch",
            "python": "${cwd}/.venv/bin/python3",
            "program": "${cwd}/.venv/bin/odoo",
            "args": [
                "-c",
                "${cwd}/.odoorc",
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
db_host = localhost
db_password = 1234
db_port = 5432
db_user = mohiuddin
```

To debug now in vscode press `F5`

Before restoring the database we can move the DB dump file to `/var/lib/postgresql` 

To login as postgres user
```
sudo -i -u postgres
```
```
psql
```
Now it's database cmd

To restore a database create the database first and drop if it exists.
```
CREATE DATABASE database_name owner  username
```

Exist the database cmd
Now run
```
pg_restore -v -d DATABASE_NAME dumpFileName.dump --no-owner
```
Here -v means verbose
