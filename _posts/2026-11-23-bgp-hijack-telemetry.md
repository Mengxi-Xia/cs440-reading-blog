---
layout: post
title: "Passive Data-Plane Telemetry to Mitigate Long-Distance BGP Hijacks"
date: 2026-11-23
paper_authors: "Satadal Sengupta, Hyojoon Kim, Daniel Jubas, Maria Apostolaki, Jennifer Rexford"
paper_venue: "NINeS 2026"
paper_url: "https://doi.org/10.4230/OASIcs.NINeS.2026.14"
week: 10
tags: [bgp, routing-security, network-measurement, telemetry]
---

## Key Idea

In a BGP hijack, an attacker can redirect network traffic through another country and still send it to the correct destination, making the attack difficult to detect. This paper introduces HiDe, which uses a programmable switch to monitor round-trip times (RTTs) and detect sudden increases in the minimum RTT for an IP prefix. Since sending traffic over a much longer path increases delay, HiDe can detect these attacks without constantly sending extra probing packets.

## Critique

A sudden increase in RTT does not always mean there is a BGP hijack. Normal routing changes could also cause delays to increase. Since HiDe may block traffic to an entire IP prefix when it detects an attack, even a false alarm could affect many users. Although the paper includes a way to recover from false alarms, I would like to see how these interruptions affect real applications.

## Connections

The previous paper on VaulTor shows that even when a Tor hidden service works normally, attackers may still be able to discover the identity of its provider by observing network traffic. This paper looks at a different security problem, where attackers can intercept traffic through BGP hijacking without stopping it from reaching the correct destination. VaulTor reduces the provider's exposure by moving the service to another server, while HiDe detects suspicious changes in network delay. Both papers try to protect users from attacks that may not be immediately noticeable.