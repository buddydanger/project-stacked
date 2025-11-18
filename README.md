# Project Stacked
*A draft-based, head-to-head fantasy football game where your weekly score is determined by betting with the NFL teams in your stack.*

---

## Introduction
**Stacked** is a modern fantasy football format where participants draft **NFL teams** instead of players. Each participant’s “stack” of NFL teams determines which games they can wager on each week. Weekly matchups are scored using **net betting profit**, introducing a clean, strategic alternative to traditional fantasy formats.

Project Stacked preserves the best parts of fantasy football:
- Preseason draft  
- Weekly matchups  
- Standings and playoffs  
- Trade value and roster strategy  

And adds new competitive elements:
- Betting-based scoring  
- Defensive mechanics  
- Restricted wager pools tied directly to drafted teams  
- A scalable team pool for different league sizes  

Project Stacked creates a high-skill, low-luck fantasy system centered on game theory, roster construction, and weekly decision-making.

---

## Core Concepts

### Your Stack
Your **stack** is the group of NFL teams you draft.  
These teams define:
- Which NFL games you are allowed to bet on  
- Your weekly offensive options  
- Your susceptibility to opponent defensive actions  

In the default format, each participant drafts **4 NFL teams**, forming a poker-like hand you “play” each week.

---

## League Structure

### Default League Format
- **8 participants**
- **4 NFL teams per participant**
- All 32 NFL teams drafted exactly once  
- No waivers required  

This is the official, recommended mode.

### Custom League Sizes
Larger leagues can use the **Team Pool Multiplier** to increase the number of copies of each NFL team available in the draft.

---

## Team Pool Multiplier (Commissioner Setting)

To support flexible league sizes, commissioners may set: TEAM_POOL_MULTIPLIER = 1 | 2 | 3

### Multiplier Overview

| Multiplier | Description | Total Draftable Assets | Recommended League Sizes |
|------------|-------------|------------------------|--------------------------|
| **1×** (Default) | Each NFL team drafted once | 32 | 8 participants |
| **2×** | Two copies of each NFL team | 64 | 8–12 participants |
| **3×** | Three copies of each NFL team | 96 | 12–16 participants |

Copies (e.g., “Chiefs A,” “Chiefs B”) function as independent assets.

All Stacked rules apply to the specific copy a participant drafts.

---

## Draft

### Format
- Snake draft  
- Commissioner chooses draft order  
- Participants draft teams until they reach the configured stack size  
- Drafted teams remain on that participant’s stack all season  

### Strategy
Participants build stacks based on:
- Strength of NFL teams  
- Betting flexibility  
- Defensive vulnerability  
- Overlap vs. uniqueness in matchups  

Your stack is your hand. You won’t get new teams unless trades are enabled.

---

## Betting System

### Bet Eligibility
Participants may place bets only on games involving:
- **Teams in their own stack**, and/or  
- **Teams in their opponent’s stack**

No other NFL games are eligible.

This ensures draft decisions, matchups, and conflicts matter every week.

### Bet Card Requirements
Each participant submits a **Bet Card** of **3–5 bets** per week.

Rules:
- All bets must involve a team from either participant’s stack  
- Allowed bet types:
  - Moneyline  
  - Spread  
  - Team totals  
- Default wager: **100 units per bet**  
- Parlay betting is optional and off by default  

### Weekly Score (Stack Score)
Weekly scoring is based on **net betting profit**:


Higher Stack Score wins the matchup.

---

## Stack Defense (Defensive Mechanics)

Each participant may execute **one** defensive action per week.

### Defensive Actions

#### 1. Block
Prevent the opponent from betting on one specific NFL team in their stack for the week.

#### 2. Counter
Force the opponent to take worse odds on one of their bets  
(e.g., –110 → –130).

#### 3. Mirror
Copy one opponent bet exactly.  
Whatever they win or lose, you win or lose.

Neutralizes their strongest edge.

#### 4. Trap Line
Designate one wager as a trap.  
If the opponent takes it:
- You gain **50%** of their winnings  
- They absorb all losses  

Only one trap may be set per week.

---

## Matchups & Standings

### Matchup Result
- Winner: Higher weekly Stack Score  
- Ties: Allowed or resolved via league tiebreakers

### Standings Points
- Win = 1 point  
- Tie = 0.5 points  
- Loss = 0 points  

### Tiebreakers
1. Total season Stack Score  
2. Head-to-head performance  
3. Opponent Stack Strength (optional)

---

## Trades (Optional)
Commissioners may enable trading of:
- NFL teams (stack assets)  
- Draft picks  
- Unit/currency balances (if implemented)  

Trade deadlines are configurable.

---

## Configuration Options

Commissioners may adjust:
- Team Pool Multiplier  
- Stack size (number of drafted NFL teams)  
- Bet Card size (3–5 bets)  
- Allowed bet types  
- Parlay permissions  
- Wager size  
- Defensive mechanics available  
- Regular season length  
- Playoff format  
- Trade rules  

Project Stacked remains flexible while maintaining its core identity.

---

## Benefits of Project Stacked

### Draft Value
Your stack is your hand. Every pick matters.

### Strategic Depth
Success requires skill in:
- Drafting  
- Wagering  
- Reading opponents  
- Using defensive actions  

### Lower Variance
Team-level outcomes reduce randomness inherent in player-based leagues.

### Direct Interaction
Stack Defense ensures real counterplay each week.

### Transparent Scoring
Stack Score is simple and objective.

---

## Example Weekly Workflow

1. **Participant A Stack**  
   - Chiefs, Bears, Saints, Vikings

2. **Participant B Stack**  
   - 49ers, Cowboys, Steelers, Jets

3. **Participant A Bet Card**  
   - Chiefs –3.5  
   - Bears ML  
   - Saints Over 23.5

4. **Participant B Bet Card**  
   - 49ers ML  
   - Cowboys –2.5  
   - Steelers Under 20.5

5. **Stack Defense**  
   - A Blocks Cowboys → bet removed  
   - B Mirrors Chiefs –3.5  

6. **Results**  
   - A Stack Score: **+215**  
   - B Stack Score: **+142**

7. **Standings Updated**

---

## Summary
**Project Stacked** is a modern fantasy football system built around team drafting, structured wagering, and weekly head-to-head strategy. By drafting a stack of NFL teams and wagering only on games involving those teams, participants create a poker-like hand that they “play” each week using betting strategy and Stack Defense.

With the Team Pool Multiplier, Stacked scales cleanly across league sizes while retaining its core strategic identity:

**Draft teams. Build your stack. Play your hand. Win the week.**
