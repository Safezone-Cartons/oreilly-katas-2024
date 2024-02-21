# System Architecture 

Date: 15/02/2024 

## Status

Approved

## Context

The propose case of *MontorMe!* requires a self-hosted on premise solution which is easy maintainable, performant, reliable, available, flexible, decentralized.

## Decision

We will opt for an **Edge Computing** environment, where each unit area has its very own Edge Processor, supported by a Local Central Storage and Deep Analysis system. 

## Consequences

*Positives*

- Setups are decentralized and can work independently 
- Each Nurse Station has its own autonomous setup
- Can be specifically modified per Use-Case (i.e. one bigger unit)
- Processing happens where the action is taken place
- More failure tolerant compared toa centralized system

*Negatives*

- We require more setup time
- Higher maintenance time when running device updates
- Relatively high initial cost