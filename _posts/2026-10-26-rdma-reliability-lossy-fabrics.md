---
layout: post
title: "Revisiting RDMA Reliability for Lossy Fabrics"
date: 2026-10-26
paper_authors: "Wenxue Li, Xiangzhou Liu, Yunxuan Zhang, Zihao Wang, Wei Gu, Tao Qian, Gaoxiong Zeng, Shoushou Ren, Xinyang Huang, Zhenghang Ren, Bowen Liu, Junxue Zhang, Kai Chen, Bingyang Liu"
paper_venue: "SIGCOMM 2025"
paper_url: "https://doi.org/10.1145/3718958.3750480"
week: 6
tags: [rdma, datacenter, reliability, load-balancing]
---

## Key Idea

RDMA networks usually use Priority Flow Control (PFC) to prevent packet loss, but this can block other traffic and make networks harder to manage. This paper introduces DCP, which allows switches to drop the data when congestion happens but keeps the packet headers in a separate, more reliable queue. The receiver sends these headers back so the sender knows exactly which packets to retransmit. This helps RDMA recover from packet loss quickly and support packet-level load balancing.

## Critique

Testing DCP on real hardware makes the results more convincing. However, DCP requires changes to both switches and RDMA NICs, which could make it difficult to deploy in existing datacenters. Large companies may already have thousands of devices that would need to be upgraded or replaced. Is it reasonable to replace such devices and make the cost balancing?


## Connections

The previous paper on dcSim tries to avoid packet loss by sending small test packets before the real data. This paper takes a different approach. Instead of preventing packet loss, DCP allows data to be dropped during congestion but keeps the packet headers so the sender can quickly retransmit the lost data. Both papers aim to improve datacenter communication by reducing the delays caused by packet loss, but dcSim focuses on preventing loss, while DCP focuses on recovering from it quickly.
