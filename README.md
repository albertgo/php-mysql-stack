# Docker PHP MySQL Stack with Prometheus and cAdvisor

The purpose of this repository is to make a Docker PHP MySQL Stack.

## PHP and MySQL
Execute <code>docker-compose up -d</code> in the terminal and load <b>http://localhost:8100/</b> in your browser.

After this operation, you can use <code>docker-compose start</code> and <code>docker-compose stop</code> to manage the containers after the creation.

* I use <b>port-forwarding</b> to connect to the inside of containers from the local machine.
    * Webserver: <b>http://localhost:8100</b>
    * DB: <b>mysql://devuser:devpass@localhost:9906/test_db</b>

* The local directory, <b>./php</b>, is mounted inside of the webserver container as <b>/var/www/html/</b>.
The files within in the local folder will be served when we access the website inside of the container.
* The data of the MySQL servers are stored in the local folder with the name of <b>mysql_data</b>.

## Prometheus and cAdvisor

* You can access the cAdvisor web UI at http://localhost:8080. You can explore stats and graphs for specific Docker containers in the installation at http://localhost:8080/docker/<container>, Prometheus at http://localhost:8080/docker/prometheus, and so on.

This configuration is based on this article:
* https://prometheus.io/docs/guides/cadvisor/