# Ronaldo Chicken 🐔⚽ — Release Notes

## Version History

| Version | Date | Type | Summary |
|---------|------|------|---------|
| v0.1.0 | 2026-03-14 | Major | Initial prototype — single-player chicken catching game |
| v0.2.0 | 2026-03-14 | Major | Rhythm-based mechanics with stop/catch controls & sound design |
| v0.3.0 | 2026-03-14 | Minor | Simplified to single big CATCH button |
| v0.4.0 | 2026-03-14 | Minor | Multi-height chicken scatter, higher density spawns |
| v0.5.0 | 2026-03-14 | Minor | Polish pass — funny sounds, personality text, visual chaos |
| v0.6.0 | 2026-03-14 | Major | SVG stick figure characters replace emoji, bicycle kick animation |
| v0.7.0 | 2026-03-14 | Minor | Detailed SVG characters with joint-based limb animation |
| v1.0.0 | 2026-03-14 | Major | Replay system — canvas-based playback with scrubbing & speed control |
| v2.0.0 | 2026-03-14 | Major | 2-player competitive mode, jump-based collision catching, crabs introduced |
| v2.1.0 | 2026-03-14 | Minor | Stabilization and polish of 2-player mechanics |
| v2.2.0 | 2026-03-14 | Major | Combo system, character expressions, vibrant visual overhaul |
| v2.3.0 | 2026-03-15 | Major | 6-level progression system with dynamic difficulty, game logs |
| v2.3.1 | 2026-03-15 | Patch | Control scheme swap (Arrow keys ↔ WASD) |
| v2.4.0 | 2026-03-15 | Major | Snake enemies introduced as third hazard type |
| v2.4.1 | 2026-03-15 | Patch | Snake rendering & animation fixes |
| v2.4.2 | 2026-03-15 | Patch | Score display position swap |
| v2.4.3 | 2026-03-15 | Patch | Start screen layout fix |
| v3.0.0 | 2026-03-15 | Major | 90-second survival mode with player elimination |
| v3.1.0 | 2026-03-15 | Minor | Mixpanel analytics integration |
| v3.2.0 | 2026-03-15 | Minor | Session replay system with full game recording |
| v3.3.0 | 2026-03-15 | Minor | Mixpanel fix: direct HTTP API tracking, full-height game, user profiles |
| v3.3.1 | 2026-03-15 | Patch | Remove session replay feature — low quality canvas playback |
| v3.4.0 | 2026-03-15 | Minor | Code readability overhaul — annotations, comments, and formatting |
| v4.0.0 | 2026-03-15 | Major | Egg mechanic, high scores, player states, performance fixes, UX overhaul |

---

## v4.0.0 — Egg Mechanic & Game Overhaul (Mar 15)

Major feature release adding the egg combat system, persistent high scores, animated player states, and significant performance/UX improvements.

### New Features
- **Egg mechanic** — press ↓/S to lay an egg (works on ground AND mid-air!)
  - Eggs fall with gravity when laid mid-air
  - Grounded eggs can be kicked by running into them
  - Egg hits other player = 2s stun with splat animation 🍳
  - Egg hits snake = snake eats it + 5 points, snake respawns after 3s
  - 3s cooldown between eggs with animated 🥚 indicator next to player name
  - Chicken cluck "pa-ka-kak!" sound on egg lay
- **Fart mechanic** — press ↓/S when egg is on cooldown: player sits, 💨 gas clouds + rumbly fart sound
- **Persistent high scores** — saved in localStorage, survives browser close/reopen
  - HI score shown next to each player's score in the UI bar
  - High score summary with relative time ("2m ago", "3d ago") on start/end screens
- **Press any key to start** — no buttons needed, just open and press any key
- **Resume from last level** — after game over, press any key to resume from one level below where you died
- **Restart from Level 1** button on end screen

### Visual & Animation
- **Animated player states** — legs/arms only move when player is moving or jumping (idle = still)
- **Sitting/laying egg posture** — player crouches with squish animation, straining face + sweat
- **Facial expressions** — determined face when moving, excited when jumping, strain when laying egg
- **Egg cooldown indicator** — 🥚 next to player name: greyed out during cooldown, fills up with glow, pulses when ready

### UX Changes
- CR7 renamed to "Cristiano Ronaldo" throughout
- Player positions swapped: Ronaldo (arrow keys) on RIGHT, Mbappe (WASD) on LEFT
- Timer removed — game runs until both players are eliminated
- Game log removed — replaced by persistent high scores
- Scores displayed larger (42px in-game, 36px end screen)

### Performance Fixes
- Snake wall-bounce sound debounced (max 1 per second, was firing every frame)
- Active chickens capped at 20 to prevent DOM bloat at higher levels
- Fixed `classList.add('')` crash when starting at level 1 (empty SKY_CLASSES[0])

---

## v0.1.0 — Initial Prototype (Mar 14)
**File:** `ronaldo_chicken_game.html`

The first version of Ronaldo Chicken. A single-player 30-second time attack where Ronaldo (🏃) chases chickens hidden in bushes.

### Features
- Arrow key / A-D movement, Space/Up to jump and catch
- Mbappe (🏃‍♂️) runs ahead as a spotter — reveals chickens within 90px of bushes
- Particle effects (floating 🍗 and ⭐)
- Mbappe speech bubbles with personality
- Touch controls for mobile (left/center/right tap zones)
- Score-based end messages ("SIUUUU!" for high scores)

---

## v0.2.0 — Rhythm-Based Mechanics (Mar 14)
**File:** `ronaldo_chicken_game_v2.html`

Complete gameplay redesign. Ronaldo now auto-runs; the player decides *when* to stop and catch.

### Changes
- **New control scheme:** Down (⬇) to STOP running, Up (⬆) to CATCH
- Ronaldo auto-runs right; chickens spawn in waves every 5-8s when Mbappe calls
- Game extended to 45 seconds
- **Web Audio API** sound effects (coin beeps, brake sounds, alerts)
- Gold glow highlights nearest catchable chicken
- Scrolling parallax background with stadium lights
- Character name labels (CR7 #7, MBAPPE #10)
- Mobile button controls added

---

## v0.3.0 — One Big Button (Mar 14)
**File:** `ronaldo_chicken_game_v3.html`

Simplified controls to a single large CATCH button for more accessible gameplay.

### Changes
- Replaced dual Stop/Catch buttons with one large 🍗 CATCH! button
- Game extended to 60 seconds
- Mbappe now runs backwards (facing left) as spotter
- Chickens visible on screen (4-7 per wave) with catchable glow
- Reduced background complexity for cleaner visuals

---

## v0.4.0 — Chicken Scatter (Mar 14)
**File:** `ronaldo_chicken_game_v4.html`

Higher density, more chaotic chicken spawns across multiple height levels.

### Changes
- Chickens now appear at 4 different heights (220-340px)
- 15-22 chickens per wave (up from 4-7)
- Walking/flapping chicken animation (`chickenWalk` keyframes)
- 7-second catch window per wave
- Victory fanfare SFX when all chickens caught
- Floating colored text popups on each catch

---

## v0.5.0 — Personality Pass (Mar 14)
**File:** `ronaldo_chicken_game_v6.html`

Added humor and audio variety to the chicken catching experience.

### Changes
- 8 procedurally generated chicken sound effects
- Funny catch text: "BAWK! 🐔", "SQUAWK!!", "GOT IT! 😂", "SIUU! 🎉"
- Randomized popup colors (gold, red, blue, green, pink, orange)
- Character position polish

---

## v0.6.0 — SVG Characters & Bicycle Kick (Mar 14)
**File:** `ronaldo_chicken_game_v7.html`

Emoji characters replaced with hand-drawn SVG stick figures. Signature bicycle kick animation introduced.

### Features
- **Ronaldo SVG**: Red jersey (#C62828), CR7 text, gold #7, animated limbs, detailed face
- **Mbappe SVG**: France blue jersey (#1565C0), #10, darker skin tone, faster leg animation
- **Bicycle kick** on every catch: body rotates through -40° → 20° → -10° arc with soccer ball appearing
- Synthesized whoosh + thwack SFX (sawtooth → square wave)

---

## v0.7.0 — Character Detail Upgrade (Mar 14)
**File:** `ronaldo_chicken_game_v8.html`

Highest fidelity SVG characters with anatomically correct joint-based limb animation.

### Changes
- Full body illustrations with proper proportions
- Jersey stripes, visible hair with multiple ellipses, eyebrows, pupils
- Limb rotation at joint origin points (not whole-body transforms)
- Separate arm/leg animation phases for natural motion
- Enhanced bicycle kick arc with ball + star emoji
- Status message: "🦵 BICYCLE KICK!! ⚽" (900ms display)

---

## v1.0.0 — Replay System (Mar 14)
**File:** `ronaldo_chicken_v1_replay.html`

First feature-complete single-player release with full game replay capability.

### Features
- Canvas-based replay recording at 12 FPS
- Replay controls: play/pause, speed (0.5x / 1x / 2x), timeline scrubbing
- Sky gradient, characters, chickens, and catch events rendered on replay canvas
- Credits overlay
- Score thresholds: 20+ = "SIUUUU GOAT", 12+ = "Brilliant", 5+ = "Good run"

---

## v2.0.0 — 2-Player Competitive Mode (Mar 14)
**File:** `ronaldo_chicken_v2_multiplayer.html`

Massive gameplay overhaul: two players compete head-to-head.

### Features
- **2-player split controls:** P1 (A/D keys), P2 (Arrow keys)
- **Jump-based collision catching** replaces button press — players must physically jump into flying chickens
- Single jump + double jump for extra height
- **Crabs introduced** as ground hazard: 5-second stun + 1 life lost on contact
- Lives system (❤️❤️❤️) with red glow stun effect
- Flying chickens approach from left edge at varying heights (80-250px)
- Split UI panels showing each player's score and lives
- Winner determined by score at 60-second mark

---

## v2.1.0 — Multiplayer Polish (Mar 14)
**File:** `ronaldo_chicken_v2_final.html`

Stabilized the 2-player experience.

### Changes
- Start screen clearly shows both players' control schemes
- Winner screen with P1 vs P2 comparison
- Replay system adapted for 2-player recording
- Crab and chicken spawn/despawn mechanics solidified

---

## v2.2.0 — Deluxe Visual & Combo System (Mar 14)
**File:** `ronaldo_chicken_v2_deluxe.html`

Visual extravaganza with a combo chaining mechanic.

### Features
- **Combo system:** consecutive catches trigger escalating rewards
  - Single → Double 🔥 → Triple 🔥🔥 → MEGA!! banners
  - Combo-specific SFX: `sfxSingle()`, `sfxDouble()`, `sfxTriple()`, `sfxMega()`
  - Higher combos = larger score popup font
- **Character expressions:**
  - Happy dance on catch, super-happy on 3+ combos
  - Mouth widens to smile during celebration
  - Stars flash around head
  - Sweat drop + sad emoji float (😢😭💫😵🤕) on crab hit
- **Visual overhaul:**
  - Purple → pink → orange → green sky gradient
  - Twinkling stars, floating clouds
  - Colorful ground dots
  - Confetti burst on catches
- Stun reduced from 5s to 2s

---

## v2.3.0 — Level Progression System (Mar 15)
**File:** `ronaldo_chicken_v2_levels.html`

Dynamic difficulty scaling across 6 levels.

### Features
- **6 levels** with escalating parameters:
  - Speed: 2.8 → 3.3 → 4.1 → 5.0 → 6.0 → 7.2
  - Spawn intervals: 1400ms → 480ms
  - Simultaneous spawns: 1 → 4 chickens per batch
  - Height variety: 3 → 8 positions
- Level up every 30 seconds
- Sky color transitions per level (blue → red → cyan → yellow themes)
- "⭐ LEVEL X ⭐" badge with dramatic announcement popup
- Level-up celebratory SFX (ascending tones)
- **Game logs:** stores last 10 games with timestamp, scores, level reached, winner
- Persistent game history panel

---

## v2.3.1 — Control Swap (Mar 15)
**File:** `ronaldo_chicken_v2_controls.html`

### Changes
- P1 (CR7) → Arrow Keys (↑↓←→)
- P2 (Mbappe) → WASD (A/D move, W jump, S catch)
- Improved key visualization with styled key boxes on start screen

---

## v2.4.0 — Snake Enemies (Mar 15)
**File:** `ronaldo_chicken_v2_snakes.html`

Third hazard type introduced alongside crabs.

### Features
- **Snakes** rendered as SVG: colored head + body segments
  - Head with eye and animated tongue
  - Body segments in horizontal line with wiggle animation
- Spawn from both edges at ground level
- Collision causes 2-second stun + 1 life lost
- Warning state: brightness flash + yellow glow when near player
- Spawn rate increases per level

---

## v2.4.1 — Snake Fix (Mar 15)
**File:** `ronaldo_chicken_v2_snakefix.html`

### Fixes
- Better snake head eye placement
- Improved tongue animation timing
- More dramatic warning effect (2x brightness + 14px glow)
- Proper body segment spacing with `gap:0` flex layout
- Reduced wiggle amplitude (3px vertical bob)

---

## v2.4.2 — Score Display Fix (Mar 15)
**File:** `ronaldo_chicken_scores_swap.html`

### Fixes
- Swapped P1/P2 score positions in UI for correct left-right mapping
- Maintained color coding (gold P1, blue P2)

---

## v2.4.3 — Start Screen Fix (Mar 15)
**File:** `ronaldo_chicken_startfix.html`

### Fixes
- Ronaldo (P1) moved to right side of display
- Mbappe (P2) moved to left side
- Consistent with in-game layout and reading order

---

## v3.0.0 — Survival Mode (Mar 15)
**File:** `ronaldo_chicken_v_final.html`

New endgame mode with player elimination.

### Features
- **90-second game** (extended from 60)
- **Elimination mechanic:** 0 lives = knocked out
  - Eliminated players fade to 20% opacity
  - "ELIMINATED" / "OUT" status indicator
  - "SURVIVED!" announcement for winner
- All three hazard types active: chickens (catch), crabs (dodge), snakes (dodge)
- Strategic balance between catching and surviving
- Winner = last player standing (or highest score if both survive)

---

## v3.1.0 — Analytics (Mar 15)
**File:** `ronaldo_chicken_analytics.html`

### Features
- Mixpanel SDK integration (v2-latest)
- Event tracking: game start, level-up, catch, elimination, win
- localStorage persistence
- "📊 Mixpanel Analytics ON" badge at bottom-right

---

## v3.2.0 — Session Replay (Mar 15)
**File:** `ronaldo_chicken_session_replay.html`

### Features
- Full session replay system layered on top of survival mode
- Complete game recording with all players, enemies, and events
- All v3.0.0 features preserved (survival, elimination, snakes, combos, levels)

---

## v3.3.0 — Analytics Overhaul (Mar 15)
**File:** `ronaldo_chicken.html`

### Changes
- **Replaced Mixpanel SDK with direct HTTP API** — uses image pixel tracking (`new Image().src`) which works from `file://` protocol without CORS issues
- **Moved Mixpanel init to `<head>`** for proper loading order
- **Full-viewport game height** — changed from fixed 580px to `100vh`
- **Hidden analytics UI** — removed visible Mixpanel badge and Session Replay text from game
- **User profiles via `/engage` API** — tracks lifetime stats per player (total_games, total_score, total_time_playing)
- **Session timing** — `session_end` event with duration fired on page unload
- **Events tracked:** game_loaded, game_started, game_ended (with scores/winner/time), snake_bite, crab_sting, player_eliminated, level_up, session_end

---

## v3.3.1 — Remove Session Replay (Mar 15)
**File:** `ronaldo_chicken.html`

### Changes
- **Removed session replay feature entirely** — canvas-based playback at 10fps produced low-quality results that didn't match the actual game rendering
- Removed replay button from end screen, replay player UI, all recording/playback code
- Cleaned up related CSS, HTML, and JS (~46 lines removed)

---

## v3.4.0 — Code Readability Overhaul (Mar 15)
**File:** `ronaldo_chicken.html`

### Changes
- **CSS section headers** — labeled every style block (fonts, sky, ground, UI bar, characters, animations, snake, objects, text effects, screens, sky themes)
- **JS section dividers** — `// ====` blocks for all 20+ code sections (Analytics, Scene Setup, Sound Engine, Config, State, Snake Builder, Player Factory, UI, Expressions, Snake Bite, Input, Jump/Catch, Scoring, Collision, Spawning, Level-Up, Game Loop, Floating Text, High Scores, Lifecycle, Screen Input)
- **HTML structural comments** — marked scoreboard, P1 Ronaldo, P2 Mbappe, start screen, end screen
- **SVG body part labels** — inline comments on every character element (shadow, legs, jersey, arms, neck, head, hair, eyes, eyebrows, nose, mouth, ears, sweat, stars)
- **JSDoc comments** on key functions with parameter descriptions
- **Inline annotations** on non-obvious logic (combo window, gravity, hitbox sizes, respawn mechanics)
- No gameplay changes — purely a readability and documentation pass
