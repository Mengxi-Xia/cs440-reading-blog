---
layout: post
title: "OpenFLAME: A Federated Spatial Naming Infrastructure"
date: 2026-11-04
paper_authors: "Sagar Bharadwaj, Ziyong Ma, Ivan Liang, Michael Farb, Anthony Rowe, Srinivasan Seshan"
paper_venue: "NINeS 2026"
paper_url: "https://doi.org/10.4230/OASIcs.NINeS.2026.20"
week: 7
tags: [spatial-naming, dns, federated-systems, maps]
---

## Key Idea

Large mapping services like Google Maps often lack detailed indoor maps, and building owners may not want to share their private map data with these companies. This paper introduces OpenFLAME, which lets different organizations manage their own maps and uses DNS to help users find the right map servers for a location. These maps can then be used together for things like finding addresses, planning routes, and indoor navigation.

## Critique

Using DNS makes it easier for different organizations to manage their own maps. However, I wonder how users can know which maps to trust. The paper uses digital signatures to verify map servers, but this does not guarantee that the maps themselves are accurate. For example, if two map servers provide different information about the same building, how should the system decide which one to use?

## Connections

The previous paper on carbon-aware routing uses existing route to reduce carbon emissions without requiring new network hardware. OpenFLAME takes a similar approach by using the existing DNS infrastructure to help applications find maps from different organizations. Although the two papers focus on different problems, both show how existing network technologies can be used in new ways without building a completely new system.
