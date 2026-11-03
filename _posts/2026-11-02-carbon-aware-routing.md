---
layout: post
title: "Exploring the Benefits of Carbon-Aware Routing"
date: 2026-11-02
paper_authors: "Sawsan El-Zahr, Paul Gunning, Noa Zilberman"
paper_venue: "CoNEXT 2023"
paper_url: "https://doi.org/10.1145/3629165"
week: 7
tags: [carbon-aware-routing, traffic-engineering, sustainability, wan]
---

## Key Idea

Routers in different regions use electricity that may produce different amounts of carbon emissions. This paper looks at whether sending traffic through greener regions can help reduce emissions. The authors also introduce CATE, which can turn off unused or less important links to save more energy. Their simulations using two real network topologies show that changing routes alone does not save much, but CATE can reduce carbon emissions by up to 17.96% in the BT network.

## Critique

Turning off network links may be much harder in real networks than in simulations. Traffic can change suddenly, and shutting down links could cause congestion or leave fewer backup paths when failures happen. Although the paper checks link capacity before shutting links down, I would like to see how CATE handles unexpected traffic increases or failures

## Connections

The previous paper on DistTrain tries to make AI training faster by using GPU resources more efficiently and reducing waiting time. This paper also focuses on resource efficiency, but looks at reducing carbon emissions in networks. Instead of changing how GPUs are used, it chooses greener routes and turns off unnecessary links when possible.