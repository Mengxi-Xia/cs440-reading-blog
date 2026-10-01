---
layout: post
title: "Understanding Partial Reachability in the Internet Core"
date: 2026-09-30
paper_authors: "Guillermo Baltra, Tarang Saluja, Yuri Pradkin, John Heidemann"
paper_venue: "NINeS 2026"
paper_url: "https://ant.isi.edu/~johnh/PAPERS/Baltra26a.pdf"
week: 2
tags: [reachability, measurement, outages, routing]
---

## Key Idea

An Internet destination can be reachable from some locations but unreachable from others, so treating reachability as simple as success or failure is not enough. The paper defines peninsulas and islands, then detects them using measurements from multiple aspects. Its results show that partial reachability is common on the internet and should be treated as a fundamental connectivity problem rather than measurement noise.

## Critique

The paper's definition of the Internet core counts every active IP address equally, even though one address may serve many users while another is rarely used. I would like to know whether the paper's conclusions still hold if reachability is measured by affected users or services rather than by address count.

## Connections

The previous reading on Internet invariants discussed traffic patterns that remain stable as the Internet changes. This reading shows that partial reachability can also persist over time. Together, they show why we need reliable methods to identify and measure persistent behavior in a constantly changing Internet.