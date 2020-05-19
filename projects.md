---
layout: page
title: Some of my recent projects
---

**[Scaling TAS (TCP Acceleration as an OS Service) flow scheduler for large number of connections](https://github.com/pkj415/tas/tree/carousel-testing-piyush-without-debt)** \| *Sept 2019 - Dec 2019, @ UT Austin*

<p style="text-align:justify;"> TAS is a user-space network stack designed to be highly performant for datacenter networking (check the [paper](https://dl.acm.org/citation.cfm?id=3303985) ). It outperforms (by throughput measure) the linux network stack and kernel bypass stack in IX. The margin by which it outperforms these stacks increases with larger number of connections, implying that TAS scales better than them for large number of connections.

Though scaling much better than other stacks, throughput for TAS dips by 7% at ~96k connections. With large numbers of connections, the queue manager/flow scheduler becomes a bottleneck. The queue manager currently uses a skip list, which can miss in the L1 and L2 caches and prefetching entries is difficult. This project changes the design of the flow pacing component in the network stack from skip-list based FQ pacing (which is inherently known to take non-linear time for enqueue) to a timewheel implementation (constant overhead enqueue operation). This design change was inspired by [Carousel](https://dl.acm.org/citation.cfm?id=309885).

Another issue the project tries to address is of scaling with (short-lived) connections which have limited performance, due to the high overhead of creating and destroying connections via the slow path in TAS.

Find details in the report specified on the project link's README.</p>

**[OpenSnap: Collection of Globally Consistent Statistics in Software Defined Networks](https://ieeexplore.ieee.org/document/8711070)** \| *Aug 2016 - Dec 2016, @ SDN Lab, Pilani*

* Applied the Chandy Lamport algorithm to procure a globally consistent snapshot of port statistics of all switches in a Software Defined Network.
* Solved the issue of inconsistent data faced in the earlier project on Probe-less measurements of latencies in SDNs (in this, port statistics were collected from all switches sequentially).

**Analysing accuracy of Probe­less Latency Measurement for SDNs on different network topologies and configurations** \| *Jan 2016 - May 2016*

<p style="text-align:justify">Worked on a tool that measures round-trip times between hosts in an SDN using statistical data that is readily available in SDN implementations. The fact that SDNs have a separate control and data plane can be used to our advantage to find round-trip times without probes i.e., packets such as those used in the standard ping command. This was based on the "Real-time monitoring of network latency in Software Defined Networks" paper by fellow researchers in the SDN Lab.</p>

