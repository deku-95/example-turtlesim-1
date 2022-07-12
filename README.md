# Turtlesim Demo project

This project demonstrate how to run basic ros2 end to end tests in simulation (here turtlesim).

## Prerequisite

You will need ROS2 galactic or humble installed.

See instructions [here](https://docs.ros.org/en/humble/Installation.html)

## ROS2 tests

You can run the tests with:

```
launch_test launch_turtle.py
```

As it is the test will fail.

If you take a look at the code, you should be able to find what is wrong and make the test pass.


## Tests with ArtefactsCI


You can use one of the 2 options below.

### With local ROS2 install

Additionally, you can use ArtefactsCI to keep track of your tests results.

1. Create an account and project on ArtefactsCI

2. Install the warp client

```
pip install git+ssh://git@github.com/art-e-fact/warp-client
```

2. Edit the project name in warp.yaml

3. Run the tests with tracking enabled

```
warpcli run basic_tests
```

### Using Docker

```
git clone git@github.com:art-e-fact/warp-client.git
docker build -t . turtle2
docker run --env WARP_KEY=[YOUR-API-KEY] --net host --env DISPLAY=$DISPLAY -v $(pwd):/turtle turtle2
```
