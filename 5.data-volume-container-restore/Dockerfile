FROM busybox

# ディレクトリがVolumeとしてホストに保持される
VOLUME /var/lib/mysql

COPY mysql-backup.tar.gz /tmp

RUN mkdir -p /var/lib/mysql

RUN tar -xzvf /tmp/mysql-backup.tar.gz -C /var/lib/mysql

CMD [ "bin/true" ]
