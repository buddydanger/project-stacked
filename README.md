# Project Stacked
*A draft-based, head-to-head fantasy football strategy game where your weekly score comes from betting with the NFL teams in your stack.*

---

## Introduction
**Stacked** is an alternative fantasy football format built around drafting NFL teams, placing wagers using those teams, and competing head-to-head through a season-long bankroll system.

Instead of managing players, participants draft a **stack** of NFL teams.  
Each week, they wager units on games involving their stack (or their opponent’s) under a **weekly hard cap**, while using a single defensive move to disrupt their opponent’s strategy.

Stacked blends:
- Fantasy-style drafting  
- Sportsbook-style wagering  
- Poker-style bankroll management  
- Light but impactful defensive interaction  

The result is a clean, strategic, low-variance format where timing, prediction, and roster construction all matter.

---

## Core Concepts

### Your Stack
Your **stack** is the set of NFL teams you draft before the season.  
Your stack determines:
- Which NFL games you are allowed to bet on  
- What your high-value options are  
- How vulnerable you are to defensive moves  

The stack is your “hand” for the entire season.

### Bankroll
Each participant begins the season with a **starting bankroll** of units.

Suggested default:
- **10,000 units**

Bankroll changes based on weekly betting outcomes.  
Running low affects future weeks (you may not be able to hit the weekly cap).

---

## League Structure

### Default League Format
- **8 participants**
- **4 NFL teams per participant**
- All 32 NFL teams drafted once  
- No waivers required  
- Perfect symmetry and clean gameplay

This is the recommended official format.

### Custom League Sizes
Larger leagues are supported using the **Team Pool Multiplier**.

---

## Team Pool Multiplier (Commissioner Setting)

The multiplier determines how many copies of each NFL team exist.

TEAM_POOL_MULTIPLIER = 1 | 2 | 3


| Multiplier | Description | Total Draftable Assets | Recommended League Sizes |
|------------|-------------|------------------------|--------------------------|
| **1×** (Default) | Each team drafted once | 32 | 8 participants |
| **2×** | Two copies of each team | 64 | 8–12 participants |
| **3×** | Three copies of each team | 96 | 12–16 participants |

Copies behave as independent assets (e.g., “Chiefs A” and “Chiefs B”).

---

## Draft

### Format
- Standard snake draft  
- Participants draft until they reach the configured stack size  
- Drafted teams remain on that participant’s stack all season  

### Strategy
Participants aim to build stacks that:
- Create strong weekly betting options  
- Can survive defensive pressure  
- Keep opponents limited in game choice  
- Balance high-floor vs. high-variance teams  

---

## Weekly Betting Rules

### Weekly Hard Cap
Each participant may stake **up to** a fixed number of units per week.

Suggested default:
- **1,000 units**

This is a hard cap:
- You may not exceed the cap  
- You may stake less than the cap (not recommended)  
- Your stakes come from your persistent bankroll  

### Minimum Bet Size
Suggested default:
- **100 units**

Prevents micro-betting and preserves game clarity.

### Maximum Bet Size
- No maximum beyond the weekly hard cap  
- Participants choose how to allocate the cap

### Bet Eligibility
You may place bets only on NFL games involving:
- Teams in **your stack**, and/or  
- Teams in **your opponent’s stack**

This keeps the game tightly tied to draft strategy.

### Bet Types (Configurable)
Default allowed types:
- Moneyline  
- Spread  
- Team Totals  

Parlays are optional and disabled by default.

### No Bet Count Requirement
Participants are not required to place a specific number of bets.

Examples:
- 1 bet of 1,000 units  
- 4 bets of 250 units  
- 10 bets of 100 units  
All are legal.

### Weekly Score (Stack Score)
Each week’s result is determined by **net profit**: 
Stack Score = Total Returns – Total Stakes


Higher Stack Score wins the matchup.

Bankroll updates accordingly.

---

## Stack Defense (Live Defensive Interaction)

Each participant may perform **one** defensive action per week.  
Defense occurs **after the sportsbook opens**, in real time, before the opponent finalizes certain bets.

### Sportsbook Timing
The commissioner defines: SPORTSBOOK_OPEN_TIME

Example:
- Tuesday at 10:00 AM local time

Once the sportsbook opens:
- Participants may place bets anytime  
- Participants may use their one defensive action anytime  
- Defensive actions **cannot** affect already-placed bets  

This creates a timing and prediction game around bet selection.

---

## Defensive Moves

### 1. Block
Block prevents your opponent from betting **one specific NFL team** for the entire week.

**Timing:**
- Can be used anytime after the sportsbook opens  
- Only valid if the opponent has NOT yet placed a bet involving that team  
- Once used, the team is removed from their available pool

**Example:**
Opponent hasn’t bet the Chiefs yet →  
You Block ↑ Chiefs →  
Opponent may not use Chiefs for any bet this week.

---

### 2. Counter
Counter worsens the odds on a specific bet your opponent *might* take.

**Timing:**
- May target any single bet option (team + line)  
- Only applies if the opponent chooses that bet later  
- If they avoid it, your Counter is wasted

**Example:**
Opponent is eyeing Cowboys ML (–110) →  
You Counter Cowboys ML → now (–130) if they take it.

---

### 3. Mirror
Mirror copies one bet your opponent has already placed.

**Timing:**
- May only be used AFTER the opponent has locked in a bet  
- You add the same wager to your own Bet Card  
- They keep their bet; you simply neutralize its advantage

**Example:**
Opponent places Vikings –2.5 (400 units) →  
You Mirror → you also take Vikings –2.5 (400 units).

---

### Defense Summary
Participants may use **only ONE** defensive ability per week:
- Block  
- OR Counter  
- OR Mirror  

Defense cannot alter or delete existing bets.  
Defense interacts only with **unplaced** (Block/Counter) or **just-placed** bets (Mirror).

---

## Weekly Flow Summary

1. **SPORTSBOOK OPENS** (e.g., Tuesday 10 AM)  
2. Participants begin placing bets  
3. Participants may use their one defensive action at any time  
4. Once a bet is placed, it becomes immune to being Blocked or Countered  
5. Betting window closes at commissioner-defined deadline  
6. Games play out  
7. Stack Scores calculated  
8. Bankrolls updated  
9. Matchup results posted  

---

## Standings & Season Results

### Matchups
- Each week is head-to-head  
- Higher Stack Score wins  
- Losses reduce bankroll; wins grow bankroll  

### Standings Points
- Win = 1 point  
- Tie = 0.5 points  
- Loss = 0 points  

### Tiebreakers
1. Total season Stack Score  
2. Head-to-head  
3. Strength of opposition stacks  

### Optional Secondary Leaderboard
- **Stack Champion:** highest ending bankroll  

---

## Trades (Optional)
Commissioners may enable trades of:
- NFL teams (stack assets)  
- Future draft picks  
- Unit transfers (if desired)  

Trade deadlines are configurable.

---

## Commissioner Configuration

### Required Settings
- Team Pool Multiplier  
- Starting Bankroll  
- Weekly Hard Cap  
- Minimum Bet Size  
- Sportsbook Open Time  
- Weekly Bet Deadline  

### Optional Settings
- Allowed bet types  
- Parlay on/off  
- Trade rules  
- Season schedule  
- Playoff format  
- End-of-season awards  

---

## Example Week

**Player A Stack:** Chiefs, Saints, Bengals, Bears  
**Player B Stack:** 49ers, Cowboys, Jets, Lions  

- Player B places 600 units on 49ers ML  
- Player A Blocks “Cowboys” before opponent uses them  
- Player A places 400 units on Chiefs –3.5  
- Player B Counters Bengals +6.5 before Player A bets it  
- Player A avoids the Countered bet  
- Player B Mirrors Chiefs –3.5  
- Both complete up to their 1,000-unit cap  
- Games resolve and Stack Scores determine the winner  

---

## Summary
**Project Stacked** combines fantasy drafting, sports betting, and tactical timing into a single competitive format. Participants draft NFL teams, build bets from those teams under a weekly hard cap, and strategically use one defensive move per week to disrupt their opponent—all while managing a persistent bankroll that reflects long-term performance.

Stacked is designed to be:
- Clean  
- Balanced  
- Skill-based  
- Configurable  
- Competitive  
- Fun  

**Draft your stack. Build your card. Time your defense. Grow your bankroll.**
