# collectd-runner

### Requirements

* Docker
* Docker Compose https://docs.docker.com/compose/install/

Environment variables
---------------------

* `HOST_NAME`
  - Will be sent to Graphite
  - Required
* `GRAPHITE_HOST`
  - Graphite IP or hostname
  - Required
* `GRAPHITE_PORT`
  - Graphite port
  - Optional, defaults to 2003
* `GRAPHITE_PREFIX`
  - Graphite prefix
  - Optional, defaults to collectd.
* `REPORT_BY_CPU`
  - Report per-CPU metrics if true, global sum of CPU metrics if false (details: [collectd.conf man page](https://collectd.org/documentation/manpages/collectd.conf.5.shtml#plugin_cpu))
  - Optional, defaults to false.
* `COLLECT_INTERVAL`
  - Collection interval and thus resolution of metrics
  - Optional, defaults to 10


Deploy
------
Run in root directory

    ./start

The following parameters are supported:

| Parameter     | Description          |
| ------------- | :------------------- |
| -d            | Run server as daemon |


When you first start you must make the scripts executable

    chmod +x ./start && chmod +x ./stop && chmod +x ./restart

### Manage

For managing server use next scripts:

| Command       | Description                                                  |
| ------------- | :----------------------------------------------------------- |
| start         | Build all containers and run                                 |
| stop          | Stop all containers                                          |
| restart       | Restart only api container. Database container isn't restart |