# Summary

> Snibble started its life as a multiplyer word game combining Snake, Scrabble, and adversarial Stealing mechanics.
>
> Over time, it has evolved into a deterministic game engine and simulator.

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
