# Conway's Game of Life CLI
## Game description
Conway's Game of Life is a cellular automaton that is played on a 2D square grid. Each square (or "cell") on the grid can be either alive or dead, and they evolve according to the following rules:

- **Underpopulation**: Any live cell with fewer than two live neighbours dies.
- **Overpopulation**: Any live cell with more than three live neighbours dies.
- **Static**: Any live cell with two or three live neighbours lives, unchanged, to the next generation.
- **Birth**: Any dead cell with exactly three live neighbours comes to life.

The initial configuration of cells can be created by a human, but all generations thereafter are completely determined by the above rules. The goal of the game is to find patterns that evolve in interesting ways – something that people have now been doing for over 50 years.

Proposed implementation uses Python3 to provide a simulation of Conway's Game of Life in Linux terminal
[Video with normal parameters](assets/normal.mp4)

## Installation
Till this moment only an AUR package is avalaible. In future will be provided packages for more distibutions

### AUR
```bash
yay -S game-of-life-cli
```

### Other Linux Distributions (Manual installation)

Clone the repository:
```bash
git clone https://github.com/DdimaPos/game-of-life-cli.git
```

Change into the directory:
```bash
cd game-of-life-cli
```

Make the script executable:
```bash
chmod +x gol-cli.py
```

Move the script to a directory in your PATH:
```bash
sudo mv gol-cli.py /usr/local/bin/game-of-life-cli
```

Ensure dependencies are installed:
```bash
sudo apt-get install python3 python3-numpy  # Debian/Ubuntu
sudo dnf install python3 python3-numpy     # Fedora
sudo pacman -S python python-numpy         # Arch Linux
```
---
## Usage

Run CLI script with this command 
```bash
game-of-life-cli
```
[mp4 with normal parameters](assets/normal.mp4)

### Specifying the *time between generation update* in seconds (default 0.07)
`game-of-life-cli -t 0.2` or `game-of-life-cli --time 0.2`
[mp4 with changed speed](assets/speed.mp4)

### Specifying the *color of cells* (default white)
`game-of-life-cli -c cyan` or `game-of-life-cli --color cyan`
[mp4 with changed color](assets/color.mp4)

### Specifying the *probability of cell to be alive* at the start(default 0.5)
`game-of-life-cli -p 0.3` or `game-of-life-cli --probability 0.3`
[mp4 with changed probability](assets/prob.mp4)
я
---
Sure you can combine them
[mp4 with -p 0.3  -t 0.04 -c green](assets/combined.mp4)
---
In addition there are added some features to let the user enjoy the evolution without involving in process:
1. Restarting the simulation when it reaches it's *stability* - After a certain amount of time 2 generations start to repeat. When this happens simulation restarts
2. Wrapping from boundaries - to increse the lifetime of simuation the cells at the boundaries treat as their neighbors cells from opposite boundaries  

# Notes
