# mysqlコンテナを起動しようとするとエラーになっちゃうなー
```bash
@j-kato732 ➜ /workspaces/codespaces-blank/5.data-volume-container-restore (main) $ docker container run -d  --name mysql -e "MYSQL_ALLOW_EMPTY_PASSWORD=yes" --volumes-from data-volume-container-restore mysql:8.0.33
116e6b8c63cb217c666613c59ca6796af56ca87daa5ae1fc9729e0e65f0bc09c
@j-kato732 ➜ /workspaces/codespaces-blank/5.data-volume-container-restore (main) $ 
@j-kato732 ➜ /workspaces/codespaces-blank/5.data-volume-container-restore (main) $ 
@j-kato732 ➜ /workspaces/codespaces-blank/5.data-volume-container-restore (main) $ docker logs mysql
2024-03-31 07:38:44+00:00 [Note] [Entrypoint]: Entrypoint script for MySQL Server 8.0.33-1.el8 started.
2024-03-31 07:38:44+00:00 [Note] [Entrypoint]: Switching to dedicated user 'mysql'
2024-03-31 07:38:44+00:00 [Note] [Entrypoint]: Entrypoint script for MySQL Server 8.0.33-1.el8 started.
2024-03-31 07:38:44+00:00 [Note] [Entrypoint]: Initializing database files
2024-03-31T07:38:44.641486Z 0 [Warning] [MY-011068] [Server] The syntax '--skip-host-cache' is deprecated and will be removed in a future release. Please use SET GLOBAL host_cache_size=0 instead.
2024-03-31T07:38:44.641587Z 0 [System] [MY-013169] [Server] /usr/sbin/mysqld (mysqld 8.0.33) initializing of server in progress as process 80
2024-03-31T07:38:44.642966Z 0 [ERROR] [MY-010457] [Server] --initialize specified but the data directory has files in it. Aborting.
2024-03-31T07:38:44.642971Z 0 [ERROR] [MY-013236] [Server] The designated data directory /var/lib/mysql/ is unusable. You can remove all files that the server added to it.
2024-03-31T07:38:44.643017Z 0 [ERROR] [MY-010119] [Server] Aborting
2024-03-31T07:38:44.643204Z 0 [System] [MY-010910] [Server] /usr/sbin/mysqld: Shutdown complete (mysqld 8.0.33)  MySQL Community Server - GPL.
```

初期化するときに/var/lib/mysql配下に何かデータがあるのが問題っぽいけど。どないするんやろ。