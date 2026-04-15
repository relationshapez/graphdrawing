# Graph Drawing

`graphdrawing.html` is a browser-based interactive tool for drawing line-based figures and converting them into graphs. It is designed to support classroom exploration of Euler paths by turning a student's sketch into a graph whose vertices occur at start points, end points, and crossing points. Because the tool is contained in a single HTML file, it can be used locally in a browser or hosted through GitHub Pages for easy student access.

## What the tool does

Graph Drawing allows the user to draw connected line figures and then study the corresponding graph in both visual and tabular form. As a drawing is created, the tool converts the geometry into graph structure by inserting vertices where they are mathematically meaningful and by splitting strokes into edges between those vertices.

The tool also includes a trace mode so that users can test whether the resulting graph can be drawn in a single continuous stroke.

## Classroom use

This tool is intended for classroom exploration. The idea is that students will form single-line drawings and the tool will convert them into graphs by adding vertices at start, stop, and crossing points. Students can then add a few more lines, either connecting existing vertices or starting from vertices to create augmented graphs.

Sometimes such augmented graphs can still be traced in a single stroke, and other times they cannot. The trace mode of the tool is helpful for exploring that question directly.

The mathematical explanation for traceability is related to the existence of Euler paths. Therefore, this tool provides a concrete way for students to explore and learn the underlying rules related to the parity of valence.

In particular, the tool helps students connect three ideas:

- a hand-drawn figure,
- the graph hidden inside that figure, and
- the degree-parity rules that determine whether an Euler path or Euler circuit exists.

This makes the tool especially useful when introducing or reinforcing topics such as:

- vertices and edges,
- valence (degree),
- crossings as graph vertices,
- Euler paths and Euler circuits,
- why odd and even valences matter,
- and how local structure affects global traceability.

## Main features

Graph Drawing includes the following core features:

- **Single-file HTML tool** for easy classroom distribution and hosting.
- **Mobile-friendly interface** intended to work on phones and tablets as well as desktop browsers.
- **Freehand drawing mode** for creating line drawings directly on the canvas.
- **Automatic graph conversion** that adds vertices at start points, end points, and crossing points.
- **Edge splitting at intersections** so the resulting graph structure matches the drawing.
- **Visual graph view** showing labeled vertices and edges.
- **Table view** listing the edges of the current graph.
- **Trace mode** for interactively testing Euler-style continuous tracing.
- **Undo** support for removing the most recent drawing action or the most recent trace step, depending on the current mode.
- **Reset** support for clearing the graph and starting over.
- **Reveal Result** support for checking whether the current graph has an Euler circuit, an Euler path, or neither.
- **No-install use** in any modern browser with JavaScript enabled.
- **Graceful no-JavaScript message** so users see a clear notice if their browser cannot run the tool.

## How the graph is formed

When a user draws, the tool interprets the sketch as graph geometry.

- The start of a stroke can become a vertex.
- The end of a stroke can become a vertex.
- Any crossing point can become a vertex.
- Existing edges are split when a new stroke crosses them.
- Repeated drawing can augment the graph with additional edges and vertices.

This lets students begin with an informal drawing and then see how graph-theoretic structure emerges from it.

## How to use the tool

### Launch to tool

1. Download `graphdrawing.html` and open it in a modern web browser (to run locally).
   or
   Access the tool at https://relationshapez.github.io/graphdrawing/ (to run remotely).
2. Draw directly on the canvas.
3. Switch to **Trace** mode to test a continuous path through the graph.
4. Use **Reveal Result** to check whether the graph has an Euler path, an Euler circuit, or neither.
5. Use **Undo** or **Reset** as needed.

### Basic classroom workflow

A simple classroom activity might look like this:

1. Ask students to draw a figure that they believe can be traced in one stroke.
2. Let the tool convert that drawing into a graph.
3. Have students inspect the graph and identify the valence of each vertex.
4. Ask them to predict whether the graph has an Euler path, an Euler circuit, or neither.
5. Use **Trace** mode to test the prediction.
6. Add one or two extra strokes and repeat the discussion.

This creates a natural bridge between experimentation and theorem-based reasoning.

## Interface overview

The tool has two main tabs:

- **Main** — the drawing canvas and graph display.
- **Table** — a tabular view of the edges in the graph.

It also has the following controls:

- **Draw** — enables freehand drawing of new strokes.
- **Trace** — enables edge-by-edge tracing of a potential Euler path.
- **Undo** — removes the last draw action or trace step.
- **Reset** — clears the current graph.
- **Reveal Result** — reports whether the graph has an Euler circuit, an Euler path, or no Euler path.

## Notes on trace mode

Trace mode is intended as an exploratory feature rather than just an answer-checking feature.

It allows students to test whether they can continue a valid path through the graph and helps them see that a correct Euler trace must follow the graph edge by edge without lifting or reusing edges improperly.

Because the tool enforces path continuation rules, it can also help students notice when they have painted themselves into a corner by making a poor tracing choice early in the process.

## Suggested teaching ideas

Some effective uses include:

- start with familiar single-stroke puzzles and ask students what makes them work,
- compare drawings with zero, two, or more than two odd-valence vertices,
- let students modify a traceable figure by adding one extra edge and predict what will happen,
- use the table view to reinforce that a drawing is also a graph with a precise edge structure,
- ask students to explain the result using parity language rather than only trial and error.

## File overview

- `graph_drawing.html` — the main interactive browser tool.
- `README.md` — repository overview and usage guide.
- `LICENSE` — MIT license text.

## License

Copyright (c) 2026 Alan Miller.

This project is released under the **MIT License**.

See the [`LICENSE`](LICENSE) file for the full license text.
