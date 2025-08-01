# Network Analysis – I Assignment

**Author**: Marco Boso  
**Date**: April 14, 2025  
**Course**: Network Analysis

## Overview

This project explores communication patterns within the **Copenhagen Networks Study**, specifically focusing on the **text message (SMS) network** of over 700 university students from the Technical University of Denmark. The network contains data on who texted whom and when—excluding message content for privacy reasons.

The analysis covers:
- Structural properties (degree distribution, clustering, assortativity)
- Community detection (Louvain & Edge Betweenness)
- Null model comparison
- Centrality analysis

## Dataset

The dataset includes:
- **nodes.csv** – individuals in the study
- **edges.csv** – SMS interactions between individuals

Source: [Netzschleuder – Copenhagen Networks Study](https://networks.skewed.de/net/copenhagen)

## Key Libraries Used

- `igraph` – graph construction and analysis  
- `tidygraph`, `ggraph` – tidy network analysis and visualization  
- `ggplot2` – statistical plotting  
- `readr` – CSV import

## Network Characteristics

- **Type**: Directed, Unipartite  
- **Nodes**: ~700  
- **Edges**: Interactions via SMS  
- **Average degree**: ~85.7  
- **Clustering coefficient**:  
  - Global: ~0.15  
  - Local (avg): ~0.22  
- **Assortativity**: 0.87 – highly assortative (high-degree nodes link with high-degree nodes)

## Community Detection

Two algorithms were applied:

- **Louvain Method**:
  - Converted network to undirected for compatibility
  - **63 communities**
  - **Modularity**: 0.83

- **Edge Betweenness**:
  - **156 communities**
  - **Modularity**: 0.90

Both methods highlight tightly knit student clusters, though with differing community sizes and structures.

## Degree Distribution

- Exhibits heavy-tailed distribution
- Few hubs with many connections
- Most nodes have very few links
- Network is **scale-free-like**

## Null Model Comparison

A configuration model preserving the degree distribution was simulated 1,000 times. The original network’s clustering coefficient was significantly lower than the simulated values (**p < 2.2e-16**), suggesting **non-random local structures**.

## Centrality Analysis

- **Closeness centrality** identified key node(s) with maximal reachability
- Visualized ego network (1-hop neighbors) for the most central node

## Visual Outputs

Visualizations include:
- Full SMS network
- Degree distributions (linear & log-log)
- Community structures (Louvain & Edge Betweenness)
- Ego network of most central node
- Histograms of clustering in null models

## How to Run

1. Clone the repository:
   ```bash
   git clone git@github.com:MarcoBoso/Analysis-of-Copenhagen-Network-Study-.git
   cd Analysis-of-Copenhagen-Network-Study-
