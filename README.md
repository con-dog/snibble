# Summary

> This write-up is being actively expanded (Work In Progress).

[Link to the Game](https://snibble.gg)

> Snibble started its life as a multiplyer word game combining Snake, Scrabble, and adversarial stealing mechanics.
>
> Over time, it has evolved into a game-engine and simulator.

![The game core loop](./media/snibble-main-loop-readme-content.gif)

### The engine features:

- Headless simulation
- Discrete movement and actions, yet continuous fluid rendering and animation
- Exact game replays with a scrubbable timeline (like a video player)
- Tiny QR-encodable replays
- Procuedral level generation (walls) and sound generation
- Configurable bot "genes" for bot behaviour, with imperfect information and perception levels
- A custom binary wire protocol for multiplayer games and replay compression
- An infinite toroidal board with zones and flow fields
- Fully separated logic and rendering

### The game loop:

- Collect letters
- Form a word
- Submit that word for points (by eating your tail)
- Steal words from other players or be stolen from

### It looks a bit like Conways Game of Life when Zoomed out

![Not Conways Game of Life](./media/snibble-conway-loop-readme-content.gif)

---

# Main Content

## Procedural Wall Generation

Walls are generated based on the seed and a custom shape grammar of 8x8 shape primitives. The shape primitives can be scaled up to different powers of 2, allowing for a wide variety of wall configurations.

![Procedural Wall Generation](./media/snibble-wall-proc-gen-readme-content.gif)

### Wall Shape Primitives

Each shape primitive is an 8x8 "grid" of wall segments and "nodes". How it works is 2x8-byte masks that get combined

- Mask 1: Define a 8x8 shape primtive of nodes (think of them as line end-caps)
- Mask 2:Define a second 8x8 shape primitive of walls (think of them as line segments)
- Each bit in the mask is a boolean value, where 1 = wall/node and 0 = empty space. The two masks are combined to form a single 8x8 shape primitive.

| Wall Primitive Diamond Example                              | Zoomed out board with Nodes coloured in                    |
| ----------------------------------------------------------- | ---------------------------------------------------------- |
| ![Wall Primitive Sample](./media/wall-primitive-sample.png) | ![Zoomed out with Nodes](./media/wall-primitive-nodes.png) |

The node-wall stroke algorithm is a simple custom algorithm that draws a line between two nodes via line of sight, and then fills in the line with wall segments. The algorithm is designed to be fast and efficient, and it can handle a wide variety of wall configurations. In the above images, the nodes are pink, the walls are black, and the empty space is white. The walls are generated procedurally based on the seed, and they can be scaled up to different powers of 2. Walls can be connected via a solid or dotted "stroke" which is seed derived.

---

To Discuss:

- Extreme compression
- Extreme performance
- Custom wire protocol
- Procedural level generation (walls)
  - Shape grammar of 8x8 shape primitives
  - Shape primitives can be scaled up to different powers of 2
- Procedural sound generation
- Discrete movement and actions
- Continuous fluid rendering and animation
- Fully separated logic and rendering
- Ability to run the game headless
- Infinite toroidal board
- Game replays
  - Spectate your own game
  - Spectate an enemies game
  - Change the camera subject dynamically
  - Play against your “ghost”
  - QR code that encodes the entire game replay
- Bot “gene” system for bot behaviour
  - Perception levels and imperfect information
  - Word forming ability and Word complexity ability
  - Stealing aggression levels
  - Zone masks
- Everything as a power of 2
  - Board dimensions
  - Inner board zones
  - Bot count
  - Bot gene parameters
  - Sound generation
- Word Dictionary
  - DAWG
  - Prefix / suffix complexity analysis
- Global state versus individual state
  - Flow fields
  - Zones

```

```
