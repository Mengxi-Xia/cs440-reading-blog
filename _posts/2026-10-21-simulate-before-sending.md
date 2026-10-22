---
layout: post
title: "Simulate Before Sending: Rethinking Transport in Datacenter Networks"
date: 2026-10-21
paper_authors: "Dan Straussman, Isaac Keslassy, Alexander Shpiner, Liran Liss"
paper_venue: "NINeS 2026"
paper_url: "https://drops.dagstuhl.de/entities/document/10.4230/OASIcs.NINeS.2026.19"
week: 5
tags: [datacenter, transport, congestion, ai-training]
---

## Key Idea

AI training often involves many servers sending data at the same time, and packet loss can slow down the whole process because lost packets need to be sent again. This paper introduces dcSim, which sends a small test packet first to check the network path. If the test packet gets through, the server sends the real data along the same path. By using separate queues for test packets and data on regular switches, dcSim reduces packet loss and makes collective communication faster in simulations.

## Critique

Sending a small test packet before the real data is a simple idea, and the simulation results look promising. However, a successful test packet does not always mean the real data will get through. The paper even shows an example where this can fail. Since the authors only tested dcSim in simulations, I would like to see whether it can achieve the same results on real switches, especially when network traffic changes quickly.

## Connections

The previous paper studied how large companies use QUIC and found that they have different retransmission settings. This paper takes a different approach by sending small test packets before the real data to avoid packet loss. Both papers are related to packet loss and retransmissions, but the QUIC paper focuses on how existing systems handle them, while dcSim tries to prevent packet loss before it happens.