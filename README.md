# Using docker compose with ROS2
## Perliminary
1. Install docker and docker-compose
2. In shell run
    ```bash
    xhost +local:docker
    ```

## Running the docker containers
The following command runs 3 different containers specified in `docker-compose.yml` in detached. Each container runs a command shell script **talker.sh** \ **listener.sh** \ **monitor.sh**.

```bash
docker-compose up -d
```
### Each caontainer runs:
1. The talker runs:
    ```bash
    ros2 run demo_nodes_py talker
    ```
2. The listener runs:
    ```bash
    ros2 run demo_nodes_cpp listener_best_effort
    ```
3. The monitor container runs:

    ```bash
    ros2 run rqt_graph rqt_graph
    ```

## To stop and close the containers
```bash
docker-compose down
```