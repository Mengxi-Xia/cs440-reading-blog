---
layout: post
title: "Don’t get caught, keep your Onions in a Vault"
date: 2026-11-18
paper_authors: "Humza Ikram, Rumaisa Habib, Muaz Ali, Zartash Afzal Uzmi"
paper_venue: "NINeS 2026"
paper_url: "https://doi.org/10.4230/OASIcs.NINeS.2026.17"
week: 9
tags: [tor, anonymity, privacy, trusted-execution]
---

## Key Idea

Tor hidden services usually need to stay online to serve users, which gives attackers more chances to discover the real location of the service provider. This paper introduces VaulTor, which lets a volunteer server host the website so the original provider only needs to connect when updating the content. The volunteer runs the website inside a Trusted Execution Environment (TEE), which prevents the server owner from reading or changing its content.

## Critique

VaulTor helps protect the original service provider, but it also puts more risk on the volunteers who host the websites. The paper suggests giving volunteers rewards, but I wonder how many people would actually be willing to run these servers, especially when they cannot see what content they are hosting. If not enough people are willing to take this risk, VaulTor might be difficult to use in practice.

## Connections

The previous paper on BISCAY uses information from the phone's radio chipset to improve congestion control without changing the cellular network. VaulTor also uses existing hardware features, but for a different purpose. It uses a Trusted Execution Environment to protect website content when it is hosted on another person's server. Both papers show how existing hardware can be used to solve new problems without changing the underlying network. However, both also depend on specific hardware support, which could make deployment more difficult.
