---
layout: post
title: "DistTrain: Addressing Model and Data Heterogeneity with Disaggregated Training for Multimodal Large Language Models"
date: 2026-10-28
paper_authors: "Zili Zhang, Yinmin Zhong, Yimin Jiang, Hanpeng Hu, Jianjian Sun, Zheng Ge, Yibo Zhu, Daxin Jiang, Xin Jin"
paper_venue: "SIGCOMM 2025"
paper_url: "https://doi.org/10.1145/3718958.3750472"
week: 6
tags: [multimodal-llm, distributed-training, disaggregation, gpu]
---

## Key Idea

Multimodal LLMs have different parts that need different amounts of computing power, and some training samples take longer to process than others. This can cause GPUs to spend a lot of time waiting. This paper introduces DistTrain, which gives the encoder, LLM backbone, and generator their own GPU resources and parallelism settings. It also moves data preprocessing to separate CPU nodes and rearranges training samples to reduce waiting time.

## Critique

Splitting the model into different GPU groups means they still need to communicate with each other. The experiments use a fast network, so I wonder whether this communication would become a problem with slower or more congested connections.

## Connections

The previous paper on DCP tries to improve datacenter communication by recovering quickly from packet loss. DistTrain focuses on a different problem in AI training. GPUs can waste time waiting because different model parts and training samples require different amounts of work. Both papers aim to make large-scale AI training more efficient, but DCP focuses on network communication, while DistTrain focuses on better GPU resource allocation and scheduling.