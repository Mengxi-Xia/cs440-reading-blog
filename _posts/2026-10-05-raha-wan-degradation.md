---
layout: post
title: "Raha: A General Tool to Analyze WAN Degradation"
date: 2026-10-05
paper_authors: "Behnaz Arzani, Sina Taheri, Pooria Namyar, Ryan Beckett, Siva Kesava Reddy Kakarla, Elnaz Jallilipour"
paper_venue: "SIGCOMM 2025"
paper_url: "https://doi.org/10.1145/3718958.3754348"
week: 3
tags: [wan, traffic-engineering, failures, measurement]
---

## Key Idea

WAN operators need to know whether link failures or changing traffic will cause performance issues before they happen. Raha searches for such scenarios by comparing how much traffic a healthy network can carry with how much the same network can carry after failures. It has been evaluated on Microsoft's WAN and public topologies, where it finds at least 2× higher degradation than methods that only consider up to two failures.

## Critique

It does making sense for comparing the healthy and failed network under the same traffic demands because it shows the impact of failures more clearly. However, Raha's results still depend on how accurate the failure probabilities and traffic ranges are. I would like to see how accurate its alerts work on real future incidents and whether it produces too many false alarms.

## Connections

The previous paper showed that a network can work from some places but not others, so simply calling it up or down can hide problems. Raha shows something similar: only testing fixed traffic and a small number of failures can also miss serious problems. Both papers show that a network may look like it is working while but still having reliability issues.