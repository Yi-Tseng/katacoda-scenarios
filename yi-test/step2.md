Start the container!
----

We can use the following command to start the container:

`docker run --privileged --rm -it -p 50001:50001 opennetworking/mn-stratum`{{execute}}

This will start a single switch and connect two Mininet hosts to switch ports 1 and 2.

Note on the Docker flags:
- `--privileged` is required to create network namespaces and virtual interfaces
- `--rm` will remove the container upon exit
- `-it` will allocate a TTY and run the container in interactive mode
- `-p 50001:50001` will publish the Stratum switch's gRPC port to the host. By default, Mininet will allocate gRPC ports to the switches sequentially starting at 50001.

You can also pass standard Mininet arguments. For example to start a 3 switch linear topology, append: `--topo linear,3`

To see a full list of Mininet arguments by appending `-h` to the Docker command.