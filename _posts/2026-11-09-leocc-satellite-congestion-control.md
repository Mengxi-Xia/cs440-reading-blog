---
layout: post
title: "LeoCC: Making Internet Congestion Control Robust to LEO Satellite Dynamics"
date: 2026-11-09
paper_authors: "Zeqi Lai, Zonglun Li, Qian Wu, Hewu Li, Jihao Li, Xin Xie, Yuanjie Li, Jun Liu, Jianping Wu"
paper_venue: "SIGCOMM 2025"
paper_url: "https://doi.org/10.1145/3718958.3750491"
week: 8
tags: [satellite-networks, congestion-control, network-measurement]
---

## Key Idea

Low Earth orbit satellites move quickly, which causes network paths, bandwidth, and delay to change frequently. Traditional congestion control algorithms may mistake these changes for congestion and unnecessarily reduce their sending rates. This paper introduces LeoCC, which detects when satellite connections are reconfigured and uses this information to update its network estimates and adjust the sending rate. 

## Critique

Most experiments use stationary residential terminals, and LeoCC relies on probing a stable network point to detect satellite reconfigurations. I wonder whether this method would still work well for moving users, such as passengers on airplanes, or in other satellite networks with different reconfiguration behaviors.

## Connections

The previous paper on OpenFLAME uses existing DNS infrastructure to help applications find maps hosted by different organizations. LeoCC also tries to solve a new problem without changing the underlying network infrastructure. Instead of modifying satellites or routers, it detects connection changes from the endpoints and adjusts the sending rate. Although the two papers focus on very different problems, both show how existing network systems can be adapted to support new needs.