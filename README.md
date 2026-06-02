# RPG Game: Development Roadmap

---

## 📁 Project Structure

```
mimic/
│
├── main.py                    # Entry point, game loop
├── config.py                  # Global constants (screen size, FPS, etc.)
│
├── assets/                    # Art, audio
│   ├── player.png
│   ├── npc.png
│   └── items, maps,...
│
├── core/                      # Game components (player, npc, tasks, UI)
│   ├── player.py              # Player movement + control
│   ├── npc.py                 # Static NPC behavior
│   ├── task.py                # Chore/task system
│   └── background.py          # Dealing with background and map, activities
│
├── system/                    # System, controls
│   └── player_movement.py     # Player keybinds
│
├── utils/                     # General-purpose utilities
│   ├── file_reader.py         # JSON read/write helpers
│   └── timer.py               # In-game countdown timer logic
│
├── data/                      # Saved logs and player behavior data
│   ├── background.json        # Saved items and rooms and stuff we do later
│   ├── day_1.json
│   ├── day_2.json
│   └── ...
│
└── README.md                  # Project description and how to run
```

---


### Project Setup and Player Movement
- Set up folder structure and install Pygame
- Create game window and main loop
- Add a simple player object that can move around
- Prevent the player from leaving the screen

### Interactable System (Tasks & NPCs)
- Create a base `Interactable` class
- Add `ItemInteract` (task) and `NPC` (dialogue) subclasses
- Enable `Return` key interaction when the player is near

### Room tasks
- Create a `Room` class with neighbors (`up`, `down`, `left`, `right`)
- Build support for room data/layout definition
- Render basic room visuals and boundaries
- Handle room transitions when player reaches screen edge
- Adjust player position during transitions
- Load room-specific interactables and NPCs dynamically
- Lay groundwork for room-linked behaviors (e.g. task limits, NPCs per room)
- Create block obstacle
- Implementing rooms like house, only certain spot can go to the next area or room

### Activities tasks
- Introduce tasks
- Design room itesm and background stuff and new tasks and item
- More interaction for rooms
- NPC
  - Farming guy
  - Chef guy
  - General trading guy
  - Black market guy

- Tasks example:
  - Planting
  - Fighting (Maybe undertale style to not deal with the aniumation and hitbox)

- And also do the tag on item or stuff that we interacting, show what we want to interact

### Holding, Swapping, and Timer Integration, UI update with image
- Allow player to hold 2 items, with swapping (Tab or Right Click)
- Display held items next to the player
- Auto-drop the oldest item if picking up a third
- Add a visible countdown timer (5–8 minutes per day)
- End the game day automatically when time runs out
- Tie the timer into task completion and transitions
- Optionally show a day-end summary screen
- Item drop and stuff area
