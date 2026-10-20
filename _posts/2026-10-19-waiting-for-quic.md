---
layout: post
title: "Waiting for QUIC: Passive Measurements to Understand QUIC Deployments"
date: 2026-10-19
paper_authors: "Jonas Mücke, Marcin Nawrocki, Raphael Hiesgen, Patrick Sattler, Johannes Zirngibl, Georg Carle, Jan Luxemburk, Thomas C. Schmidt, Matthias Wählisch"
paper_venue: "CoNEXT 2025"
paper_url: "https://doi.org/10.1145/3768988"
week: 5
tags: [QUIC, measurement, privacy, infrastructure]
---

## Key Idea

QUIC encrypts a lot of information, making it hard to understand how big companies like Google and Meta use it. Instead of directly testing their servers, the authors mainly study QUIC responses collected by a network telescope, including responses requested with fake source IP addresses. By looking at packet headers and retransmissions, they find differences in how companies configure QUIC and identify servers outside their own networks.

## Critique

The paper does not clearly show how these QUIC configration differences affect actual user performance. For example, Meta retransmits packets much faster than Google and Cloudflare, but does that really make connections faster or more reliable? More experiments comparing how these settings affect connection performance can be done.

## Connections

The previous paper found that traditional end-to-end signals are often enough for good congestion control. This paper also shows that information we already have can be useful. Even though QUIC encrypts much of its traffic, the authors can still learn about how large companies deploy QUIC by looking at packet headers and retransmissions. Both papers show that we can learn a lot from existing information without always needing more detailed data.
