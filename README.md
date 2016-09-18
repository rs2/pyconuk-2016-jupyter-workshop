## Web Apps from Jupyter Notebooks


### Prerequisites

1. Install `docker` on your system. See [instructions](https://docs.docker.com/engine/installation/) for details.
  1. If your `docker` requires Virtual Box to run you need to initialise `docker-machine`.
    1. It is a good idea to increase capacity and performance of your `docker-machine`.
    1. If you are happy to do so, remove the existing machine called `default` by running 
    ```
    docker-machine rm default
    ```
    1. Re-create `default` machine with 100GB disk capacity:
    ```
    docker-machine create -d virtualbox --virtualbox-disk-size "100000" default
    ```
    1. Set up the environment for the `docker` client. See the output of 
    ```
    docker-machine env default
    ```
    
1. Pull required images so that not to overload conference network.
```
docker pull node:6
docker pull jupyter/scipy-notebook
docker pull jupyter/minimal-notebook
```

### How to build the environment

1. Clone the repo:
```
git clone https://github.com/rs2/pyconuk-2016-jupyter-workshop.git
```
1. Open your favourite shell and change working directory to `./docker`
1. Build images:
```
docker-compose build
```

### How to start the containers

1. Run
```
docker-compose up
```

### How to start the streaming server

1. Open `http://<your docker host>:8888/notebooks/pyconuk-2016-workshop/zmq-server.ipynb`.
1. Select `Cell / Run All`.

### How to start the interactive client

1. Open `http://<your docker host>:8888/notebooks/pyconuk-2016-workshop/interactive_notebook.ipynb`.
1. Select `Cell / Run All`.
1. Select `View / Dashboard Layout / Grid` or press the toolbar button that looks like a window.
1. Drag / hide / unhide elements to desired positions.
1. Deploy the notebook using File / Deploy As / Dashboards server.
1. Profit.
