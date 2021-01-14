TCPDump
=======

Alpine-based Docker container to run TCPDump.

Running without parameters will run tcpdump keeping at max one day of pcaps in 15 minute chunks.

Volume with pcaps available at `/pcap/`.

Usage
-----

#### Build

    $ docker build -t kQqhWdGMAS6K4fkw/tcpdump .

#### View help and version

    $ docker run --rm kqqhwdgmas6k4fkw/tcpdump --help

#### Examine the host network

    $ docker run --rm --net=host -v ~/pcap:/pcap kqqhwdgmas6k4fkw/tcpdump

#### Examine the TCP traffic on the host network with Wireshark

    $ docker run --rm --net=host kqqhwdgmas6k4fkw/tcpdump -i any -w - | wireshark -k -i -

#### Examine the traffic of Docker container `foo` with Wireshark

    $ docker run --rm --net=container:foo kqqhwdgmas6k4fkw/tcpdump -i any --immediate-mode -w - | wireshark -k -i -


## Credits

https://github.com/moncho/docker-tcpdump

http://jerrygamblin.com/2016/05/28/a-docker-container-to-capture-all-traffic-from-host/.

http://www.tcpdump.org/
