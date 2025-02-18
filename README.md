# Oscillator-Based Min-Cut Demo

This repository contains a simple HTML/JavaScript demo illustrating how two moderately dense subgraphs, connected by a few cross-edges, can be partially distinguished via a toy oscillator-based approach. The file **[min_cut.html](https://github.com/galenwilkerson/galenwilkerson.github.io/blob/master/min_cut.html)** runs a basic phase-oscillator simulation and then clusters nodes according to their final phases. 

> **Note**: While the name "min_cut.html" suggests a classic Min-Cut solver, the included code is more of a toy synchronization demonstration than a true min-cut algorithm. However, it demonstrates how oscillator dynamics can help separate subgraphs when cross-coupling is weak.

## How It Works

1. **Generate Two Random Subgraphs**  
   Each subgraph has a set of nodes with edges created at moderate density. This yields two separate “clusters” in principle.

2. **Add Cross-Edges**  
   A small number of random edges link the two subgraphs, ensuring they’re not fully disconnected.

3. **Oscillator Simulation**  
   Each node is treated as a phase oscillator. The simulation runs for a fixed number of discrete time steps, updating phases based on a simple sinusoidal coupling rule.

4. **Clustering**  
   After the simulation, nodes with similar final phases are grouped together. If the cross-edges are sparse, the oscillator network often “splits” into two clusters matching the original subgraphs. If cross-coupling is strong, the two clusters might merge into a single large synchronized group.

## How to Use

1. **Open min_cut.html**  
   Click **[min_cut.html here](https://github.com/galenwilkerson/galenwilkerson.github.io/blob/master/min_cut.html)** to view the source code. You can clone or download the repository and open `min_cut.html` in your browser to run it locally.

2. **Check the Output**  
   The page displays logs detailing the final phases of each node, plus the automatically derived clusters. If you open the browser console, you’ll also see adjacency lists and other debugging info.

3. **Tweak Parameters**  
   In `min_cut.html`, you can adjust:
   - The size and density of each subgraph.  
   - The number of cross-edges.  
   - The coupling strength or number of simulation steps.  
   - The clustering threshold for final phase differences.

Experimenting with these parameters can give a sense of how easily or how quickly the oscillators can separate the two subgraphs.

## Limitations

- **Not a Real Min-Cut Solver**  
  The code is a **proof-of-concept** illustrating how oscillator synchronization sometimes reveals natural partitions. True min-cut requires a more deliberate mapping of the cut objective to oscillator couplings.

- **Small Scale**  
  Focusing on just 10–20 nodes per subgraph. Larger graphs or different problem structures may need more advanced or optimized approaches.

- **Heuristic Nature**  
  Synchronization can get stuck in local patterns or fail to separate subgraphs if cross-coupling is too strong, or if random initial conditions cause a global phase lock.

## Contributing

Feel free to open issues or submit pull requests with improvements:
- More rigorous objective mapping (turning this from a toy demonstration into a partial min-cut heuristic).
- Visualizations of the graph structure and real-time oscillator phases.
- Parameter tuning or user interface enhancements.

---

© 2023 galenwilkerson. This content is provided under the MIT License (see [LICENSE](LICENSE) for details).
