# Summary

A game-engine and accompanying game that slowly turned into an infrastructure project. 

Features:
- Procedural level generation (walls)
- Procedural sound generation
- Discrete movement and actions
- Continuous fluid rendering and animation
- Fully separated logic and rendering
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


# How it Started

This started as a simple game combining elements from Snake, Scrabble, and PvP/PvE mechanics (word stealing).

The core loop is:
- Collect letters
- Form a word
- Submit that word points (by eating your tail)
- Steal or be Stolen from

# How it is Now

The game revealed itself to not be so simple after all. Ideas that seemed simple on the surface, once the thread was pulled to its logical conclusion, turned out to have second order effects.

