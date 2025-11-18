# Project Stacked
*A draft-based, head-to-head fantasy football game where your weekly score is determined by betting with the NFL teams in your stack.*

---

## Introduction
**Stacked** is a modern fantasy football format where participants draft **NFL teams** instead of individual players. Each participant’s “stack” defines which NFL games they are allowed to wager on each week. Matchups are scored using **net betting profit**, introducing a clean, strategic alternative to traditional fantasy formats.

Project Stacked maintains familiar fantasy elements:
- A preseason draft  
- Weekly head-to-head matchups  
- Season standings and playoffs  

And introduces new competitive concepts:
- Betting-based scoring  
- Defensive mechanics  
- Stack-restricted wagering  
- Configurable league sizes through team pool multipliers  

The result is a strategic, low-variance fantasy system centered on roster construction, game theory, and weekly decision-making.

---

## Core Concepts

### Your Stack
Your **stack** is the set of NFL teams you draft.  
These teams determine:
- The pool of games you may wager on  
- Your weekly offensive options  
- Your vulnerabilities during Stack Defense  

The default format uses **4 teams per participant**, mirroring a poker-hand feel.

---

## League Structure

### Default League Format
- **8 participants**  
- **4 NFL teams per participant**  
- All 32 NFL teams drafted exactly once  
- No waivers required  

This is the recommended, official format of Stacked.

### Custom League Sizes
Using the **Team Pool Multiplier**, leagues can expand beyond 8 participants while keeping the game balanced.

---

## Team Pool Multiplier (Commissioner Setting)

To scale league size, commissioners may configure: TEAM_POOL_MULTIPLIER = 1 | 2 | 3


### Multiplier Definitions

| Multiplier | Description | Total Draftable Assets | Recommended League Sizes |
|------------|-------------|------------------------|--------------------------|
| **1×** (Default) | Each NFL team drafted once | 32 | 8 participants |
| **2×** | Two copies of each NFL team | 64 | 8–12 participants |
| **3×** | Three copies of each NFL team | 96 | 12–16 participants |

Copies (e.g., “49ers A,” “49ers B”) behave as independent teams in all gameplay and defensive rules.

---

## Draft

### Format
- Standard snake draft  
- Participants select NFL teams until they reach the configured stack size  
- Drafted teams remain on their stack all season  
- No waivers or midseason acquisitions (unless trades are enabled)  

### Strategy
Participants build stacks based on:
- NFL team strength  
- Bet variety and flexibility  
- Defensive vulnerability  
- Overlap potential with likely opponents  

Your stack is your hand — you will play it all season.

---

## Betting System

### Bet Eligibility
Participants may only bet on NFL games involving:
- Teams in **their own stack**, and/or  
- Teams in **their opponent’s stack**

This creates a shared matchup-specific ecosystem that directly reflects draft strategy.

### Bet Card Requirements
Each participant submits a **Bet Card** of **3–5 bets** per week.

Rules:
- All bets must involve a team from either participant’s stack  
- Allowed bet types include:
  - Moneyline  
  - Spread  
  - Team totals  
- Default wager size: **100 units per bet**  
- Parlay bets are optional and disabled by default  

### Scoring (Stack Score)
Weekly scoring is based on **net betting profit**: Stack Score = Total Returns – Total Stakes


The higher Stack Score wins the matchup.

---

## Stack Defense (Defensive Mechanics)

Stack Defense allows direct interaction with an opponent’s strategy.  
Each participant may execute **one defensive action per week**.

Stack Defense is divided into two phases:

- **Pre-Bet-Card Defense**: Block  
- **Post-Bet-Card Defense**: Counter, Mirror, Trap  

Participants may only use **one** defensive action per week.

---

## Pre-Bet-Card Defense

### 1. Block (Ban Phase)
Block prevents an opponent from using one specific NFL team in their stack for the week.

**Timing:**  
Block is declared **before Bet Cards are submitted**.

**Effect:**  
- The blocked team cannot appear on any bet in the opponent’s Bet Card.
- The opponent still submits a full 3–5 Bet Card using their remaining eligible teams.

**Why this works:**  
- Zero risk of mismatched bet counts  
- Rewards stack depth  
- Forces strategic adaptation  
- Is powerful but information-light (declared before seeing their bets)

---

## Post-Bet-Card Defense

These actions occur **after** Bet Cards are submitted but **before** games begin.

Participants may use one of the following **only if they did not use Block**:

### 2. Counter
Choose one opponent bet and worsen its odds.  
Example:  
- Original odds: –110  
- Countered odds: –130  

Reduces their potential upside or increases downside.

---

### 3. Mirror
Copy one opponent bet exactly.  
Both participants receive the same result on that wager.

This neutralizes their strongest edge.

---

### 4. Trap Line
Designate one wager line as a trap before Bet Cards are submitted.  
If the opponent chooses that wager:

- You gain **50% of their winnings**, and  
- They absorb **100% of the losses**

Trap is a high-risk, high-reward mind game tool.

---

## Matchups & Standings

### Matchup Results
- Winner: Higher weekly Stack Score  
- Ties: Allowed or resolved via tiebreakers  

### Season Standings
- Win = 1 point  
- Tie = 0.5 points  
- Loss = 0 points  

### tiebreakers
1. Total season Stack Score  
2. Head-to-head performance  
3. Opponent Stack Strength (optional)

---

## Trades (Optional)
Commissioners may enable trades of:
- NFL teams (stack assets)  
- Future draft picks  
- Unit balances  

Trade deadlines are configurable.

---

## Configuration Options  
Commissioners may configure:
- Team Pool Multiplier  
- Stack size  
- Bet Card size  
- Allowed bet types  
- Parlay rules  
- Wager size  
- Defensive options (enable/disable individual abilities)  
- Schedule structure  
- Playoff format  
- Trading rules  

Project Stacked is modular while remaining conceptually simple.

---

## Example Weekly Workflow

1. **Defense Declaration Phase (Block)**  
   - Participants secretly choose whether to Block  
   - If used, Block target is revealed  
   - Blocked teams cannot be used on Bet Cards  

2. **Bet Card Phase**  
   - Each participant submits 3–5 legal bets  

3. **Post-Bet-Card Defense (Optional)**  
   - If no Block was used, participants may choose Counter, Mirror, or Trap  

4. **Games Play Out**  
   - Wagers resolve  
   - Stack Scores calculated  

5. **Matchup & Standings Updated**

---

## Summary
**Project Stacked** is a new fantasy football framework built around team drafting, restricted wagering, and weekly head-to-head strategy. Participants construct a stack of NFL teams, build Bet Cards from that stack, disrupt opponents through Stack Defense, and compete based on net betting profit.

With the Team Pool Multiplier and clean pre/post defensive phases, Stacked scales smoothly from casual groups to competitive leagues.

**Draft your stack. Build your card. Play your hand. Win the week.**
