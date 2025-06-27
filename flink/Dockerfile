FROM flink:1.20
# Download connector library jars
RUN wget -P /opt/flink/lib/plugins https://repo1.maven.org/maven2/org/apache/flink/flink-connector-jdbc/3.3.0-1.20/flink-connector-jdbc-3.3.0-1.20.jar; \
    wget -P /opt/flink/lib/plugins https://repo1.maven.org/maven2/io/github/jeff-zou/flink-connector-redis/1.4.3/flink-connector-redis-1.4.3.jar; \
    wget -P /opt/flink/lib/plugins https://repo1.maven.org/maven2/org/apache/flink/flink-sql-connector-mysql-cdc/3.4.0/flink-sql-connector-mysql-cdc-3.4.0.jar; \
    wget -P /opt/flink/lib/plugins https://repo1.maven.org/maven2/com/mysql/mysql-connector-j/9.3.0/mysql-connector-j-9.3.0.jar;
