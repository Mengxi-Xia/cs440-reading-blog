---
layout: post
title: "Tight Loops, Smooth Streams: Responsive Congestion Control for Real-Time Video"
date: 2026-11-11
paper_authors: "Pantea Karimi, Sadjad Fouladi, Vibhaalakshmi Sivaraman, Mohammad Alizadeh"
paper_venue: "NINeS 2026"
paper_url: "https://doi.org/10.4230/OASIcs.NINeS.2026.9"
week: 8
tags: [congestion-control, real-time-video, webrtc, latency]
---

## Key Idea

Video encoders produce frames of different sizes, which makes it hard for a congestion controller to keep track of a changing network. This paper introduces Vidaptive, which sends video at the rate chosen by a congestion controller and adds dummy packets when there is too little video data to probe the network. It also adjusts the encoder's target bitrate to limit frame delay.

## Critique

Vidaptive improves video quality and latency without requiring changes to the video encoder, which makes it practical. However, it sends dummy packets even when there is no video data to send. These packets consume bandwidth and may also use extra battery power. I wonder how much overhead this would create when many users share a limited wireless connection.

## Connections

The previous paper on LeoCC shows that traditional congestion control can make mistakes on satellite network congestion. Vidaptive addresses a different problem: real-time video does not always send enough packets for the congestion controller to track network conditions quickly. LeoCC uses satellite reconfiguration events to improve its network estimates, while Vidaptive sends dummy packets to maintain continuous feedback. Both papers show that congestion control works better when the sender has more reliable information about changing network conditions.
