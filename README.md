# Aether Tournament – Neutral 4×4 & 5×5

**Aether Tournament** is a tactical board game where two players combine colors by moving pieces like a knight on a toroidal board.  
The goal: collect all unique colors in a single cell before your opponent.

This repository contains:
- **Official tournament rules** for the **Neutral 5×5** variant.
- **Complete monograph** analyzing the **Neutral 4×4** variant – a perfect model for understanding the game’s mathematics, tactics, and strategy.
- **A full implementation** of the Neutral 4×4 game (React + AI) ready to play.
- **Python analysis scripts** for exhaustive search (3×3) and heatmaps.
- **Jupyter notebooks** for interactive research.

The monograph is written for players, tournament organizers, and researchers. It covers everything from fundamental invariants to endgame analysis, with comparisons to chess, Go, and Game of Life.

---

## 📚 Monograph

The full monograph is available in `docs/monograph/` as Markdown files.  
It consists of the following chapters:

1. **Fundamental foundations** – torus topology, initial configuration, bit‑mask representation, analysis of 2×2 and 3×3 variants.
2. **Mathematical structure** – state space, invariants, proof of no stalemate, 50‑move rule.
3. **Tactical elements** – knight geometry, merging combinatorics, threats, forks.
4. **Strategic phases** – opening, middlegame, endgame, playing with shared pieces.
5. **Comparative analysis** – chess, Go, Game of Life, other abstract games.
6. **Scaling to 5×5** – differences, what carries over, computational challenges.
7. **Computer analysis & open problems** – full search feasibility, AI algorithms, open questions.
8. **Conclusions & recommendations** – summary and practical advice.

The monograph is designed to be read both as a tutorial and as a reference for researchers.

---

## 🧠 Game implementation

The `src/` directory contains a React‑based implementation of **Neutral 4×4**.

### Features
- Full rules: toroidal board, knight moves, merging (OR), 50‑move rule.
- Two‑player mode (local).
- AI opponent (MCTS / random) – configurable.
- Clean UI with piece masks displayed as colored dots or bit indicators.
- PGN export for game recording.

### Run locally

```bash
git clone https://github.com/sciganec/aether-tour.git
cd aether-tour
npm install
npm start
```

The game will be available at `http://localhost:3000`.

---

## 📁 Repository structure

```
aether-tour/
├── README.md                  # this file
├── LICENSE                    # MIT license
├── package.json               # dependencies
├── public/                    # static assets
├── src/                       # game source code (React)
│   ├── core/                  # game logic (board, pieces, moves)
│   ├── ai/                    # AI implementations (random, MCTS)
│   ├── ui/                    # React components
│   └── ...
├── docs/                      # documentation and monograph
│   ├── rules/                 # tournament rules (5×5)
│   ├── monograph/             # markdown files for each chapter
│   ├── analysis/              # additional diagrams, tables
│   └── tournament/            # tournament organization guides
├── analysis/                  # Python analysis scripts
│   ├── exhaustive_3x3.py
│   ├── invariants.py
│   ├── heatmap.py
│   └── requirements.txt
├── notebooks/                 # Jupyter notebooks for research
└── tests/                     # unit tests
```

---

## 🔧 Development & contribution

Contributions are welcome! If you want to improve the AI, add new analysis scripts, or enhance the monograph, please open an issue or a pull request.

### Scripts

- `npm start` – run the game in development mode.
- `npm test` – run tests.
- `npm run build` – build for production.
- `npm run deploy` – deploy to GitHub Pages (requires configuration).

For Python scripts, install dependencies with:

```bash
cd analysis
pip install -r requirements.txt
```

---

## 📜 Tournament rules

The official **Neutral 5×5** rules are located in `docs/rules/TOURNAMENT_RULES_5x5.md`.  
They describe the exact format used for competitive play. The 4×4 variant discussed in the monograph follows the same logic but with a smaller board and fewer colors.

---

*May your merges be timely and your forks precise.* 🔮
