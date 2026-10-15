---
layout: post
title: "No Signal to Rule Them All: A Systematic Analysis of In-Network Congestion Signals"
date: 2026-10-14
paper_authors: "Sarah McClure, Nandita Dukkipati, Sylvia Ratnasamy, Scott Shenker"
paper_venue: "NINeS 2026"
paper_url: "https://drops.dagstuhl.de/storage/01oasics/oasics-vol139-nines2026/OASIcs.NINeS.2026.12/OASIcs.NINeS.2026.12.pdf"
week: 4
tags: [congestion-control, telemetry, datacenter, signals]
---

## Key Idea

Datacenter congestion control can use signals from both endpoints and switches, but it is not clear how much the extra information from switches actually helps. The authors train different congestion control algorithms using different signals and compare their performance. They find that using information from switches makes little difference on average, with performance usually within 3% of using only traditional approach. They also find that link information is generally better for reducing delay, while queue information is better for improving throughput.

## Critique

Only looking at average performance might miss some important problems. Even if the average difference is small, some flows could still experience much higher delays. This can be a serious issue in datacenters. I would like to see whether INT provides more benefits for tail latency, especially during incast, when many servers send data to the same receiver at once.

## Connections

The previous paper on P-ECMP showed how hosts can use congestion signals to move traffic to a different path instead of relying on random retries. This paper also looks at congestion signals, but focuses on whether more detailed information from switches can improve congestion control. Both papers try to improve network performance, but P-ECMP focuses on choosing better paths, while this paper focuses on controlling how fast data is sent and algorithm itself.
