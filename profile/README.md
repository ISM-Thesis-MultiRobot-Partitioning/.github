# About

This organization collects all the code productions from my thesis project on multi-robot terrain partitioning. We have focused on creating a decentralized system with a strong focus on modularity and isolation, with the aim of making it easy for customers to integrate our solution into their existing tools.

To this end, we have a [`partition-api`][api], written entirely in Rust, which launches a web server that can handle incoming POST requests from a client. We have also implemented a [client in ROS2][ros2] using Python to demonstrate the integration and to give a concrete example.

# Structure

- [`thesis-code`][tc] repository is the highest level where everything is set up the same way we had it on our machines. It makes heavy use of submodules to combine all the various parts into one package. It also provides docker compose and mprocs config files for even easier management! One should consider starting here!
- [`rust-crates`][rc] repository sets up all our rust crates so that you don't have to worry about it! It combines the following:
    - The [`partition-api`][api] which is the client facing side of our solution. This one also implemented the actual partitioning algorithms.
    - The [`local-robot-map`][lrm] library crate, which provides the foundation upon which to build the partitioning algorithms.
- [`ros2-client`][ros2] is our client in ROS2 Python.
- [`python-client`][pc] was out testing playground to probe the Rust API. The [ros2 client][ros2] is essentially a fancy wrapper around the POST request method found here.
- [`simulation-map-empty`](https://github.com/ISM-Thesis-MultiRobot-Partitioning/simulation-map-empty) and [`simulation-map-expand`](https://github.com/ISM-Thesis-MultiRobot-Partitioning/simulation-map-expand) are essentially helper ROS2 nodes for managing the robot maps.

# Thesis Report

A read-only link to [our report][report] on Overleaf further allows diving deeper into this topic and our work. Please note that you must select the `overleaf_main.tex` file, as otherwise the report might fail to compile successfully (mainly due to differences in setup between Overleaf and the local setup).

[tc]: https://github.com/ISM-Thesis-MultiRobot-Partitioning/thesis-code
[rc]: https://github.com/ISM-Thesis-MultiRobot-Partitioning/rust-crates
[lrm]: https://github.com/ISM-Thesis-MultiRobot-Partitioning/local-robot-map
[api]: https://github.com/ISM-Thesis-MultiRobot-Partitioning/partition-api
[ros2]: https://github.com/ISM-Thesis-MultiRobot-Partitioning/ros2-client
[pc]: https://github.com/ISM-Thesis-MultiRobot-Partitioning/python-client
[report]: https://www.overleaf.com/read/dyyxfspchnhg
