---
layout: post
title: "BISCAY: Practical Radio KPI Driven Congestion Control for Mobile Networks"
date: 2026-11-16
paper_authors: "Jon Larrea, Tanya Shreedhar, Atte Niemi, Adel Sefiane, Mahesh K. Marina"
paper_venue: "NINeS 2026"
paper_url: "https://doi.org/10.4230/OASIcs.NINeS.2026.15"
week: 9
tags: [mobile-networks, congestion-control, cellular, bandwidth]
---

## Key Idea

Cellular network bandwidth can change quickly when a phone moves or shares a cell with other users. This makes it difficult for traditional congestion control algorithms to adjust their sending rates accurately. This paper introduces BISCAY, which uses radio measurements from the phone's chipset to estimate available bandwidth and adjust the congestion window. By getting more accurate and timely information about the network, BISCAY can maintain high throughput while reducing delay compared to existing congestion control algorithms.

## Critique

Testing BISCAY on real phones and cellular networks makes the results more convincing. However, even though it does not require rooting the phone, it still needs a custom Android update and access to the modem's diagnostic data. This could make it difficult to deploy on phones from different manufacturers, especially if they use different chipsets or restrict access to these interfaces.

## Connections

The previous paper on Vidaptive uses dummy packets to keep getting feedback about changing network conditions during real-time video streaming. BISCAY takes a different approach by getting bandwidth information directly from the phone's radio chipset, without sending extra probing packets. Both papers try to help congestion control react faster to network changes.