---
layout: post
title: "Unlocking ECMP Programmability for Precise Traffic Control"
date: 2026-10-07
paper_authors: "Yadong Liu, Yunming Xiao, Xuan Zhang, Weizhen Dang, Huihui Liu, Xiang Li, Zekun He, Jilong Wang, Aleksandar Kuzmanovic, Ang Chen, Congcong Miao"
paper_venue: "NSDI 2025"
paper_url: "https://www.usenix.org/conference/nsdi25/presentation/liu-yadong"
week: 3
tags: [datacenter, ecmp, traffic-control, failure-recovery]
---

## Key Idea

ECMP uses hashing to choose paths, but sometimes it sends traffic through a faulty path, and switching to another path isn't easy. This paper introduces P-ECMP, which lets servers choose a different path by using existing ECMP groups and a field in the packet header. Normal traffic can still use ECMP as usual. The authors also build a compiler and a way to update the system without disrupting traffic. They test several use cases in simulations and deploy them in a real data center.

## Critique

Using features already available in existing switches makes P-ECMP practical, and testing it in a real data center makes the results more convincing. However, switching paths quickly does not mean an application can recover immediately, since detecting a failure also takes time. The paper mentions that failure detection takes about one second on average in their storage service. I would like to see how much time is spent detecting the failure and how much is spent switching paths in real cases.

## Connections

The previous paper on Raha studied how network failures and traffic changes could affect WAN performance. P-ECMP looks at a different part of the problem. When a network path has issues, it helps move traffic to another path without repeatedly trying random ones. Both papers aim to improve network reliability, but Raha helps operators prepare for possible problems, while P-ECMP helps them deal with problems when they happen.
