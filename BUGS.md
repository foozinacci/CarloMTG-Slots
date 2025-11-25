# Known Bugs & Issues

## 1. Color Identity Display Issues

### Problem
- Color identity not displaying under player names in Leaderboard Odds queue
- Instead appears as hyphenated text to the right (e.g., "PlayerName - RWU")
- Scaling and positioning incorrect inside container boxes

### Expected Behavior
- Color identity should appear **under** the player name as color icons only
- No hyphenated name+code text format
- Icons should be properly sized and centered below the name

---

## 2. Report Deck Results Dialog - Opponent Color Selection

### Problem
- In "Report Deck Results" dialog, when Match Format = "Best of 3" and matches played = 1
- "Match 1" color selection for opponent cannot be clicked or interacted with
- No visual indication of how to select opponent colors

### Expected Behavior
- Each match row should display clickable color identity buttons/chips for opponent selection
- Selected opponent colors should visually indicate selection state (highlighted/checked)
- User must be able to click and toggle opponent colors before saving

---

## 3. Report Deck Results Dialog - Win/Loss Controls Missing

### Problem
- No +/- increment/decrement buttons for wins or losses
- No visible numeric count showing current wins/losses per match
- Cannot adjust match results at all

### Expected Behavior
- Each match row should have +/- buttons for both wins and losses
- Current win/loss counts should be clearly visible as numbers
- Buttons should increment/decrement the respective counts appropriately

---

## 4. Report Deck Results Dialog - Save Blocked

### Problem
- Save operation always triggers error: "Match 1: please select one of the opponent's colors before saving"
- Error fires even though there's no functional way to select opponent colors
- Dialog is effectively unusable - cannot save any results

### Expected Behavior
- Save should only validate after user has had opportunity to select opponent colors
- If opponent colors are required, the selection mechanism must be functional first
- Validation should check actual state values, not stale/incorrect data

---

## 5. History Log - Letter Codes Instead of Icons

### Problem
- When a player/result is logged, history shows letter codes for colors (e.g., "RWU", "GB")
- Inconsistent with how colors display elsewhere in the app
- History may also show hyphenated name-code combinations

### Expected Behavior
- History log should use the same color icon components used in queue/winner displays
- Visual consistency across all parts of the app
- No raw letter codes - icons only

---

## 6. Bulbs - Dull/Low Contrast Appearance

### Problem
- Bulbs (indicator lights above/around reels) appear flat, dull, and washed out
- Low contrast makes them hard to see as "lit" elements
- Don't stand out visually or convey "illuminated" state clearly

### Expected Behavior
- Bulbs should appear vivid and clearly lit (like real light bulbs)
- Strong glow effect, higher contrast, clear circular shape
- Should "pop" visually while staying consistent with overall theme
- Use techniques like box-shadow, radial gradients, brightness filters, etc.

---

## 7. Centering Issues

### Problem
- Multiple UI elements are visually off-center in their containers:
  - Player names
  - Color identity displays
  - Bulbs relative to reels/labels
  - Some section headers
- Affects both desktop and mobile layouts

### Expected Behavior
- All elements should be properly centered within their parent containers
- Use flexbox/grid alignment properties consistently
- Should remain centered across different screen sizes and breakpoints

---

## 8. Reel Spin Math Logic - Missing/Incorrect

### Problem
- Core probability logic for reel spins is incomplete or entirely missing
- Reels animate/spin visually but outcome selection doesn't follow intended weighted random behavior
- No clear implementation of slot-style probability system

### Expected Behavior
- Each of 5 reels should use weighted probability to select outcomes
- Weights should reflect configured odds for each player/deck in the queue
- Winner selection should combine reel results according to defined rules
- Should handle edge cases: wildcards, tie-breaking, special outcomes (goblin thumb, etc.)
- Math should be fair, deterministic (given seed), and match the slot machine design spec

---

## Development Strategy

Due to token limits and complex git history, fix these issues **one cluster at a time**:

1. **Leaderboard Odds** - Color identity display (Bug #1)
2. **Report Deck Results Dialog** - All issues (Bugs #2, #3, #4)
3. **History Log** - Icon rendering (Bug #5)
4. **Bulbs & Centering** - Visual/CSS fixes (Bugs #6, #7)
5. **Reel Spin Logic** - Core math implementation (Bug #8)

Each fix should be a focused commit on branch: `claude/fix-deck-results-dialog-015QXBLY4F6vaXmtHaov9Txx`
