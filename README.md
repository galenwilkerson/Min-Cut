# Oscillator-Based Min-Cut Demo

![Animated Demo](https://github.com/galenwilkerson/galenwilkerson.github.io/blob/master/min-cut.gif)

This repository contains a simple HTML/JavaScript demo illustrating how two moderately dense subgraphs, connected by a few cross-edges, can be partially distinguished via a toy oscillator-based approach.

**Run the demo here**:  
[**https://galenwilkerson.github.io/min_cut.html**](https://galenwilkerson.github.io/min_cut.html)

> **Note**: While the file is named `min_cut.html`, the included code is more of a toy synchronization demonstration than a true min-cut algorithm. However, it shows how oscillator dynamics can help separate two subgraphs when cross-edges are sparse.

## How It Works

1. **Generate Two Random Subgraphs**  
   Each subgraph (G1, G2) has a set of nodes with moderate density edges.

2. **Add Cross-Edges**  
   A small number of random edges link G1 and G2, creating a combined graph.

3. **Oscillator Simulation**  
   Each node is treated as a phase oscillator. The code runs a discrete-time simulation where neighboring oscillators try to synchronize. After enough steps, nodes in G1 often converge to one phase cluster, and nodes in G2 converge to another.

4. **Clustering**  
   Once the simulation finishes, we group nodes whose final phases are within a small threshold. If the two subgraphs remain mostly independent, you’ll see two major clusters that align with the original G1 and G2 sets.

## Usage

Simply visit  
[https://galenwilkerson.github.io/min_cut.html](https://galenwilkerson.github.io/min_cut.html)  
in your browser. The page will generate logs showing each node’s final phase and which cluster it belongs to. Check the browser’s console for adjacency lists, debug info, or to adjust parameters in the code.

## Parameter Tweaks

Inside `min_cut.html` you can change:
- The size of each subgraph.
- The number of edges within each subgraph (density).
- The number of cross-edges.
- The simulation steps or coupling strength.
- The clustering threshold for phase differences.

Experimentation reveals when and how the oscillator network separates the subgraphs vs. merging them into a single large cluster.

## Limitations

- **Not a Formal Min-Cut**: The logic here demonstrates **a toy approach** rather than a rigorous min-cut algorithm. 
- **Small Scale**: Focuses on 10–20 nodes per subgraph. For larger graphs or complex structures, more sophisticated solutions are needed.
- **Heuristic Behavior**: Oscillator synchronization can sometimes yield unexpected or partial partitions.

## Contributing

Feel free to open issues or submit pull requests with improvements:
- A more accurate mapping to min-cut.
- Visual graph rendering of the two subgraphs and oscillator states.
- Parameter-tuning or performance improvements.

---

© 2023 galenwilkerson. Released under the MIT License. See [LICENSE](LICENSE) for details.
