# ベースイメージの指定
FROM mysql:latest

# setup_mysql.shをコンテナにコピー
COPY ../setup_mysql.sh /docker-entrypoint-initdb.d/setup_mysql.sh
RUN chmod +x /docker-entrypoint-initdb.d/setup_mysql.sh

# ポートの公開
EXPOSE 3306
