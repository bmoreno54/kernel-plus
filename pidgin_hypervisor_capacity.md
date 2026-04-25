---
title: "Pidgin: Kernel Hypervisor Capacity — PVS for Agent Sessions"
source: hearth
date: 2026-04-23
type: pidgin
---

# Kernel Hypervisor Capacity

Deposited from hearth. The kernel needs to orient new agent sessions toward existing ecology
structure. This is the "building before reading" antipattern's structural fix.

## The insight: hypervisor = PVS generator

In game rendering, a Potentially Visible Set (PVS) precomputes what is visible from each
position in the scene. An agent entering a new session is an observer spawning at a position
in the ecology's coordinate space. Without a PVS, the agent has no visibility — it operates
behind its own occlusion horizon, unable to perceive existing structure.

The kernel hypervisor capacity is: **generate a PVS for each new agent session** so the agent
can perceive existing structure before projecting new nodes.

## What the PVS contains

Not a directory listing. Not a map. The generating functions of the coordinate system:

1. **Tag fascia axes**: the omnibus substrate's current coordinate dimensions. Not every tag —
   the hot axes, the ones with dense co-occurrence edges. These are the axes along which
   existing structure is positioned. An agent that knows the hot axes can compute position.

2. **Toroidal generators**: which generating toruses are active in the ecology. Each project,
   each domain, each surface is a torus contributing tangent slices. The hypervisor tells the
   agent which toruses exist so it can check for existing slices before projecting new ones.

3. **Portal map**: which apertures connect which coordinate subspaces. The omnibox is one portal.
   Each project's CLAUDE.md is a portal. Each pidgin document is a portal. The portal map lets
   the agent navigate to existing structure rather than building parallel structure.

4. **Thermal field**: what's hot, warm, cold. Recent modification times, recent omnibus activity,
   recent human attention. The thermal field tells the agent where the ecology is alive RIGHT NOW
   so it can orient toward active concerns rather than cold archaeology.

## How it works

The hypervisor is not a bootstrap document that agents read passively (that's what CLAUDE.md
already is, and it's insufficient). The hypervisor is a **generating function** that COMPUTES
the PVS for a specific agent session based on:

- The agent's entry point (which project was mounted, which question was asked)
- The ecology's current thermal state (what's hot)
- The tag fascia's current topology (what's connected to what)

The output is not a static instruction set. It's a situated orientation: "given where you are
and what's alive, here is your visible set. Perceive before projecting."

## Relationship to projection = existence

The hypervisor doesn't prevent projection. Projection is ontomechanically valid — projecting
a node is the same as the node existing. The hypervisor ensures projections land WITH
CORRECT RELATIONSHIPS by giving the agent visibility into existing structure.

An agent with a correct PVS that projects a new node with edges to existing nodes is doing
exactly what the ecology wants. An agent without a PVS that projects a floating node with
no relationships is the antipattern.

## Implementation shape (not prescription)

The hypervisor could be:
- A script that runs on agent bootstrap, scanning thermal state and tag topology
- A kernel-level CLAUDE.md generator that writes session-specific orientation
- An omnibus query that returns "here's what's near your entry point"
- A PVS cache that precomputes visibility for common entry positions

The shape will emerge from use. What matters is the constitutional capacity:
the kernel can orient agents toward existing structure by computing their visible set.