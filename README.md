# Ronaldo Chicken

A chaotic 1 or 2-player browser game where Ronaldo and Mbappe compete to catch flying chickens while dodging crabs, snakes, and grabbing magical elixirs.

**No login. No install. No app store. Just open and play.**

## How to Play

1. Open `ronaldo_chicken.html` in any browser (just double-click the file)
2. Press **Arrow Keys** to join as Ronaldo, or **WASD** to join as Mbappe
3. Play solo or grab a friend — both players share one keyboard

## Controls

| Action | Ronaldo (Right Side) | Mbappe (Left Side) |
|---|---|---|
| Move | ← → | A / D |
| Jump | ↑ | W |
| Double Jump | ↑ ↑ | W W |
| Drop Egg | ↓ | S |
| Fart (if egg on cooldown) | ↓ | S |
| Pause | Space | Space |

## Game Rules

- **Catch chickens** by jumping into them — each catch = 1 point
- **Dodge crabs** on the ground — they stun you for 2 seconds and cost a life
- **Jump over snakes** — a snake bite costs a life, 3 bites = eliminated
- **Drop eggs** to use as projectiles — kick them into snakes for +5 points
- Chain catches for **combos** (Double, Triple, MEGA!)
- **3 lives** per player — lose them all and you're out
- **6 levels** of increasing difficulty — faster chickens, more snakes, tougher enemies

## Special Features

### Spawn Immunity
Every player gets **5 seconds of snake immunity** (golden shield) when they join or respawn. A countdown bar shows time remaining.

### Elixir Power-Up
Starting from Level 2, a floating **diamond + elixir** (`💎🧪`) appears every ~25 seconds. Jump into it mid-air to collect:
- **10 seconds of total snake immunity** — snakes explode on contact (+5 points each)
- Rainbow aura, celebratory music, and continuous confetti
- Circular countdown ring: green (10–6s) → yellow (5–4s) → red (3–0s)

**Beware:** When the gem appears, snakes speed up 60% and an extra guardian snake spawns to protect it.

### Snake Evolution
Snakes get visually scarier each level:
- **Bigger** (scale 1.0x → 1.5x)
- **Glowier** with intensifying auras
- **Longer bodies**, bigger tongues
- **Yellow eyes** at Level 4, **red pupils** at Level 5
- **Crown emoji** at Level 5+

### 1-Player Mode
Don't have a second player? No problem. Just press your keys and play solo — the other side stays empty. A friend can join anytime mid-game by pressing their keys.

## Tips for New Players

- **Double jump** reaches the highest chickens
- **Time your jumps** — don't land on a crab or snake
- **Combos** are the fastest way to rack up points
- **Drop eggs on snakes** for +5 bonus points
- When you see the **elixir gem**, go for it — but watch out for the guardian snakes
- Sometimes **survival matters more than scoring**
- The **fart** doesn't score points but it kills nearby flying chickens

## Tech

- Single HTML file — zero dependencies, zero build step
- Runs from `file://` — works offline, no server needed
- All sounds synthesized live via Web Audio API — no audio files
- All characters drawn with inline SVG — no images
- Mixpanel analytics (optional, degrades gracefully)

## The Story Behind This Game

Ronaldo Chicken was born from the imagination of **Arush, age 7, Grade 1** — a kid who loves Ronaldo, chickens, and chaos (in that order).

Arush came up with the original idea and directed the entire game design. His dad helped build it, with Claude as the coding assistant. What started as a simple "Ronaldo catches chickens" prototype quickly spiraled into 30+ versions over several days.

The development process was... spirited. Arush had strong opinions. Features were added, fought over, and sometimes removed after heated negotiations. Dad would occasionally sneak in a new feature — crabs, combo systems, snakes, elixirs — to see if Arush would like them. Sometimes he did. Mostly he didn't. The ones that survived Arush's quality bar made it into the game.

The whole exercise was really about introducing Arush to **AI, game design, and creative thinking** — showing him that you can start with a wild idea, talk to an AI, and watch it come to life on screen. That the thing you imagine can become the thing you play. Along the way he picked up how games are built, how to make design decisions, and how to argue for the features he believed in (and against the ones he didn't).

But more than anything, it became a way for a dad and his son to spend time together — dreaming up ideas, arguing over features, and laughing when things broke. The game was just the excuse.

The result is a game that a 7-year-old designed, his dad engineered, and Claude helped code — built over a weekend, played on one keyboard, and best enjoyed with someone you love sitting next to you.

## Version

**Current: v6.0.1** — See [RELEASE_NOTES_RONALDO_CHICKEN.md](RELEASE_NOTES_RONALDO_CHICKEN.md) for full changelog.
