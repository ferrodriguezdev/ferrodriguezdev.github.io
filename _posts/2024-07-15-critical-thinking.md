---
layout: post
title: Critical Thinking
date: '2024-07-15T00:00:00.000-05:00'
author: Fernando Rodriguez
tags:
---

Whenever someone shows me a new development, the phrase from the
book [Designing Data-Intensive Applications](https://www.oreilly.com/library/view/designing-data-intensive-applications/9781491903063/),
which
states that "even when they have the best intentions, humans are known to be unreliable," comes to my mind. I start
thinking about where exceptions can occur.

The most common errors I typically encounter involve not validating input parameters for APIs, neglecting to use
try-catch blocks in logic or data access, mishandling transactions, or failing to properly handle events through
failover.

In essence, it's just another way to begin considering potential failure points in your code right from the very
beginning.
