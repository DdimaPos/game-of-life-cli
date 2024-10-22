# Conway's Game of Life CLI
## Game description
Conway's Game of Life is a cellular automaton that is played on a 2D square grid. Each square (or "cell") on the grid can be either alive or dead, and they evolve according to the following rules:

- **Underpopulation**: Any live cell with fewer than two live neighbours dies.
- **Overpopulation**: Any live cell with more than three live neighbours dies.
- **Static**: Any live cell with two or three live neighbours lives, unchanged, to the next generation.
- **Birth**: Any dead cell with exactly three live neighbours comes to life.

The initial configuration of cells can be created by a human, but all generations thereafter are completely determined by the above rules. The goal of the game is to find patterns that evolve in interesting ways – something that people have now been doing for over 50 years.

Proposed implementation uses Python3 to provide a simulation of Conway's Game of Life in Linux terminal
![gif with normal parameters](assets/divided.gif)

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

Delete the directory with the cloned repository

---
## Usage

Run CLI script with this command 
```bash
game-of-life-cli
```
![gif with normal parameters](assets/normal.gif)
### Specifying if *the cells are squares or rectangles* (default true which mean squares)
Eg: `game-of-life-cli -d true` or `game-of-life-cli --divided false`
![gif with divided and not divided](assets/divided.gif)

### Specifying the *time between generation update* in seconds (default 0.07)
Eg: `game-of-life-cli -t 0.2` or `game-of-life-cli --time 0.2`

### Specifying the *color of cells* (default white)
Eg: `game-of-life-cli -c cyan` or `game-of-life-cli --color cyan`
![gif with color parameters](assets/color.gif)

### Specifying the *probability of cell to be alive* at the start(default 0.5)

Eg: `game-of-life-cli -p 0.3` or `game-of-life-cli --probability 0.3`
![gif with probability parameters](assets/probability.gif)


You can combine the parameters to get something pleasing to your eyes
![GIF with -p 0.3  -t 0.04 -c green](assets/combined.gif)

## Notes
In addition there are added some features to let the user enjoy the evolution without involving in process:
1. Restarting the simulation when it reaches it's *stability* - After a certain amount of time 2 generations start to repeat. When this happens simulation restarts
2. Wrapping from boundaries - to increse the lifetime of simuation the cells at the boundaries treat as their neighbors cells from opposite boundaries  


