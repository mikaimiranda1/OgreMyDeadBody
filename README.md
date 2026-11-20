# Game Name: Ogre My Dead Body

A first-person 3D action/puzzle game made in Unity. You wake up in an ogre's cave and work your way out to escape.

## Project Setup
- **Unity version:** 6.5 (6000.5.9f1). Everyone must use this exact version.
- **Render pipeline:** URP. Only use assets that support URP.
- **Packages:** ProBuilder, AI Navigation
- **Team workflow guide:** [link to the workflow doc]

### Folder Structure
```
Assets/
├── _Project/
│   ├── Player/      (Araav)
│   ├── Level/       (Keo)
│   ├── Enemies/     (Mikai)
│   ├── UI/          (Chris)
│   ├── Audio/       (Chris)
│   └── Scenes/
│       └── Dev/     (personal test scenes, one per person)
└── ThirdParty/      (Asset Store packs)
```

### Git Rules
- Work on your own branch (`yourname/feature`). Never push straight to `main`.
- Merge through pull requests. Someone else tests before merging.
- Only edit your own folder and your own scenes. Keo owns the real level scenes.
- Close Unity before pulling or switching branches.
- Always commit `.meta` files.

## Group Members / Roles
- **Araav Patel** – Player & Combat
  - First-person player controls (player movement, camera movement)
  - Sword combat (swinging, hit detection, damage) and sword upgrade
  - Player health and equipment (rusty sword, flashlight, torch)
  - First-person animations (sword swing, flashlight/torch bob)
- **Keo Minato** – Level Design & Lighting
  - Cave layout and all four areas (wake-up cave, mob room, puzzle room, boss arena)
  - Lighting: bioluminescent algae, flashlight/torch tuning, the lighting effect when the boss arena catches fire
  - Environment art: rocks, carcasses, gates, props
  - Scripted level events (flashlight dies, gates open, exit opens)
- **Mikai Miranda** – Enemies & Boss
  - Basic mob AI (patrol, chase, attack) using Unity NavMesh
  - Ogre/cyclops boss AI: punch attacks, leg weak point, kneeling state, eye weak point
  - Camera shake when the ogre moves and attacks
  - Enemy models and animations (Mixamo / Asset Store)
- **Chris Sapiens Serrano** – Puzzle, UI & Game Flow
  - Rotating-object puzzle and the wall clues
  - Main menu, pause menu, settings, HUD (health bar, equipped item), win/death screens
  - Game manager: checkpoints, respawning, scene flow, rewards (better sword, more health)
  - Sound effects

## Game Description
- **Genre:** First-person action-adventure with light puzzle elements
- **Story:** An ogre/cyclops knocks you out and drags you into his cave. You wake up in the dark next to a rusty sword and have to fight and solve your way out, then beat the ogre to escape.
- **Goal:** Make it through each area of the cave, collect upgrades, defeat the ogre, and escape.

### Level Progression
1. **Start/Waking Up:** The cave is dark apart from dim bioluminescent algae. Pick up the rusty sword, then search the carcasses to find a flashlight. Fight a few easy mobs. Defeating all of them opens the gate.
2. **Puzzle Room:** Rotate objects to match the clues carved and painted on the walls. Solving the puzzle unlocks a better sword, more max health, and the next gate.
3. **Boss Area:** On the way to the final level, your flashlight dies, so the player grabs a torch from the wall. You touch the torch to coal/oil, which sets the room alight and reveals the ogre. Dodge his punches and hit his leg until he kneels, then hit his eye. Repeat until he's defeated, and the cave exit opens.

### Mechanics
- 'WASD': Movement
- Mouse: Look around
- 'Shift': Sprint
- 'Space': Jump
- 'Left Click': Sword attack
- 'Right Click': Turns flashlight on/off
- 'E': Interact (pick up items, rotate puzzle pieces, light the coal)
- 'Esc': Pause menu
- Checkpoint: Respawn at the start of the current room
- Gates: Open when a room's objective is completed

### Enemies / Moving Objects
- **Mobs:** Simple enemies that chase the player and attack up close, and die in a few hits
- **Ogre/Cyclops boss:** Telegraphed punch attacks, a hittable leg point, a kneel/stun state that exposes the eye
- **Moving objects:** Opening gates, rotating puzzle pieces, flickering torch flames

### Lighting
1. **Spot light:** The player's flashlight
2. **Point light:** The torch, bioluminescent algae, and the fire that light up the boss arena

### Camera
- First-person camera controlled with the mouse
- Camera shake when the ogre stomps or punches
- Camera shake when player takes damage

### Animation
- Player: First-person sword swing and light-source sway/bob
- Mobs: idle, walk, attack, hit, death
- Ogre: idle, walk, punch, kneel, hurt, death
- Environment: gates opening, puzzle pieces rotating, fire lighting up last room

### Menus / UI
- **Main menu:** Play, Controls, Settings, Quit
- **Pause menu:** Resume, Restart, Settings, Quit to Main Menu
- **Settings:** Master volume, brightness, mouse sensitivity
- **HUD:** Health bar, interaction prompt ("Press E to pick up"), boss health bar
- **End screens:** "You Died" (Retry / Main Menu) and "You Escaped!" win screen


### Sounds
#### Player
- Footsteps
- Sword swing miss
- Sword hit 
- Taking damage
- Dying
#### Items & Lighting
- Picking up an object
- Flashlight on/off
- Flashlight flickering and dying
- Grabbing the torch
- Torch ambient (fire crackle, loops)
- Touching the torch to the coal/oil (ignite "whoosh")
- Boss room lighting up (fire spreading)
#### Mobs
- Idle growls / noticing the player
- Attacking
- Taking damage
- Dying
#### Environment & Puzzle
- Cave ambience (dripping water, distant echoes, low wind, loops)
- Gate opening
- Moving/rotating puzzle pieces
- Puzzle solved (success chime)
- Upgrade received (new sword, health increase)
#### Ogre
- Distant yell when the player wakes up at the start
- Footsteps / stomps (synced with camera shake)
- Punch wind-up and punch hit
- Taking damage (leg hit, eye hit)
- Kneeling
- Dying
- Roar on reveal
#### UI
- Main menu
- Menu button hover/click
- Pause / unpause
- Escaping the cave (win sound)
- Game over (death sound)

## Assets Used
List every pack or file you import here, with where it came from, so we can credit it.

- **Environment:**
- **Characters & Animations:** Mixamo
- **Items:**
- **Sounds:**

## Current Progress
**Midpoint checkup goal (Tue Nov 24):** Level 1 playable

- [x] Repo and Unity project set up (packages, tags/layers, folder structure)
- [ ] Level 1 cave blockout and lighting (Keo)
- [ ] Player movement, sword, flashlight (Araav)
- [ ] Mob AI: patrol, chase, attack, death (Mikai)
- [ ] HUD, main menu, GameManager opens gate (Chris)
