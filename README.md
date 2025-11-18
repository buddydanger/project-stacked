# Project Stacked
*A draft-based, head-to-head fantasy football strategy game where your weekly score comes from betting with the NFL teams in your stack.*

---

## Introduction
**Stacked** reimagines fantasy football by replacing player management with team drafting, bankroll strategy, sportsbook-style wagers, and live defensive interaction.

Participants draft a **stack** of NFL teams before the season.  
Each week, they place bets using only the teams in their stack (and their opponent’s) under a **weekly wager cap**, while using **one defensive move** to disrupt the opponent’s strategy.

Stacked combines:
- Draft strategy  
- Betting decision-making  
- Real-time defensive timing  
- Season-long bankroll management  
- Multi-tier promotion/relegation leagues  
- Integrated communication platform  

It is competitive, strategic, elegant, and easy to learn.

---

## Core Concepts

### Your Stack
Your **stack** is the set of NFL teams you draft.  
Your stack defines:
- Which NFL games you may bet on  
- Which teams are vulnerable to being blocked  
- How flexible or predictable your weekly betting options are  

### Bankroll
Each participant begins the season with a **starting bankroll**.

**Calculation:**
Starting Bankroll = (Number of Weeks × Weekly Cap) ÷ 2

This starting amount is **half** of what would be needed to max bet every week for the entire season.

**Strategic Impact:**
- You cannot max bet every week if you lose consistently  
- Building your bankroll through wins gives you more flexibility later in the season  
- Bankroll management becomes a key strategic decision: aggressive betting to grow your stack, or conservative play to preserve capital  
- Participants with larger bankrolls have more options and can sustain losses better

---

## League Structure

### Default League Format
- **8 participants**
- **4 NFL teams per participant**  
- All 32 NFL teams drafted once  
- No waivers needed  

This is the recommended format for a clean, competitive season.

---

## Team Pool Multiplier (Commissioner Setting)

The commissioner may scale league size by configuring:
TEAM_POOL_MULTIPLIER = 1 | 2 | 3


| Multiplier | Description | Total Draftable Teams | Recommended League Sizes |
|------------|-------------|------------------------|--------------------------|
| **1×** (Default) | Each team drafted once | 32 | 8 participants |
| **2×** | Two copies of each team | 64 | 8–12 participants |
| **3×** | Three copies of each team | 96 | 12–16 participants |

Copies (e.g., "Chiefs A" and "Chiefs B") function as independent assets.

---

## Promotion & Relegation (Pro/Rel)

Leagues can be **stacked** vertically in a promotion/relegation pyramid, creating a multi-tier competitive structure.

### How It Works
- **Multiple tiers** of leagues (e.g., Premier, Championship, League One)  
- **Bottom finishers** in higher tiers are **relegated** to the tier below  
- **Top finishers** in lower tiers are **promoted** to the tier above  
- Each tier operates independently with its own draft and season  

### Benefits
- Creates long-term competitive stakes beyond a single season  
- Rewards consistent performance with promotion opportunities  
- Adds drama to the bottom of standings (relegation battles)  
- Allows leagues to form competitive ecosystems  
- Participants can work their way up through the tiers  

### Configuration
- Number of tiers in the pyramid  
- Promotion/relegation spots per tier (typically 2-3 teams)  
- Playoff structure for promotion/relegation  
- Cross-tier scheduling (optional)

---

## Draft

### Format
- Snake draft  
- Draft until each participant reaches the configured stack size  
- Teams remain rostered all season  
- Trades available throughout the season  

### Strategy Factors
- Betting flexibility  
- Stack depth  
- Defensive resilience  
- Opponent overlap  
- Team volatility  

Your stack is your hand for the entire season.

---

## Weekly Betting Rules

### Weekly Hard Cap
Each participant may stake **up to a fixed number of units** per week.

Suggested default:
- **1,000 units**

- You may stake **less**, but never more  
- Stake must come from your current bankroll  
- Hard cap ensures fairness and strategic consistency  

### Minimum Bet Size
Suggested default:
- **100 units**

Prevents trivial micro-betting.

### Maximum Bet Size
- No max other than the weekly cap  

### Bet Eligibility
You may bet only on games involving:
- Teams in **your stack**  
- Teams in **your opponent’s stack**

This ties gameplay directly to draft strategy.

### Allowed Bet Types (Configurable)
- Moneyline  
- Spread  
- Team Totals  

Parlays optional (off by default).

### No Bet Count Requirement
Participants may make as many or as few bets as they want, as long as total stakes meet the weekly cap.

Examples:
- 1 × 1,000  
- 4 × 250  
- 10 × 100  
All are valid.

### Weekly Score (Stack Score)
Weekly outcome is based on **net profit**:
Stack Score = Total Returns – Total Stakes


The higher Stack Score wins the matchup.

Bankroll is updated accordingly.

---

## Stack Defense (Live Defensive Interaction)

Each participant may use **one defensive action per week**:  
**Block** or **Counter**.

### Sportsbook Timing
The commissioner configures:
SPORTSBOOK_OPEN_TIME


Example:
- Tuesday at 10:00 AM local time

Once the sportsbook opens:
- Participants may place bets at any time  
- Participants may use their one defensive move at any time  
- Defensive moves **cannot** affect bets already placed  

This creates a timing-based strategic layer:
- Should you block early?  
- Should you wait and see where they lean?  
- Are they baiting you?  
- Will they rush their best bet before you stop it?  

This timing game is core to Stacked.

---

## Defensive Abilities

### 1. Block
Block removes an opponent’s ability to use **one specific NFL team** for the entire week.

**Rules:**
- You may use Block anytime after the sportsbook opens  
- You may **only** block a team **if your opponent has not yet placed a bet involving that team**  
- Once Block is used, it is permanent for the week  
- You cannot block multiple teams  

**Example:**
Opponent hasn’t yet bet Chiefs  
→ You Block Chiefs  
→ They cannot bet Chiefs this week

If they *had* bet Chiefs earlier, Block would be invalid.

---

### 2. Counter
Counter worsens the odds of a specific bet option your opponent **might** take.

**Rules:**
- You may Counter any unplaced bet option  
- If your opponent later chooses that exact bet, they receive worsened odds  
- If they avoid the bet, your Counter has no effect  
- You cannot Counter multiple bets  

**Example:**
Opponent is eyeing  
- Cowboys ML (–110)

You Counter it:  
- Cowboys ML becomes (–130) *if* they take it  
- They can choose to avoid it  

Counter is a predictive, mind-game tool.

---

### Defense Summary (v1)
- **One defensive move per week**  
- Choose **Block** *or* **Counter**  
- Defense must be used **before** an opponent finalizes the affected bet  
- Defense never deletes or modifies existing bets  
- Timing is everything

This creates a balanced, elegant defense system fully aligned with Stacked’s gameplay.

---

## Weekly Flow Summary

1. **SPORTSBOOK OPENS** (e.g., Tuesday 10:00 AM)  
2. Participants begin placing bets  
3. Each participant may use **one** defensive action  
4. Once a bet is placed, it becomes immune to Block or Counter  
5. Betting closes at commissioner-set deadline  
6. Games resolve; Stack Scores calculated  
7. Bankroll updated  
8. Matchup results posted  

---

## Standings & Season Results

### Matchups
- Higher Stack Score wins  
- If Stack Scores are equal, tiebreakers determine the winner (see below)  
- Losses reduce bankroll, wins grow it  

### Standings Points
- Win = 1  
- Loss = 0  

### Weekly Tiebreakers (for equal Stack Scores)
If two participants have the same Stack Score in a matchup, the winner is determined by:
1. **Number of bets placed** — More bets wins (rewarding diversification and strategic betting)  
2. Total units staked (if bet count is equal)  
3. Highest single bet return (if still tied)

### Season Tiebreakers (for standings)
1. Total season Stack Score  
2. Head-to-head record  
3. Strength of opponent stacks  

### Additional Leaderboard (optional)
- **Stack Champion:** highest ending bankroll  

---

## Trades
**Trades are available throughout the season** to help participants adapt their stacks, respond to injuries, capitalize on emerging teams, and adjust strategy based on weekly matchups.

Participants may trade:
- **NFL teams** — Swap teams to improve betting flexibility or defensive options  
- **Draft picks** — Exchange future draft capital (if applicable)  
- **Unit transfers** — Include bankroll units as part of trade packages  

**Strategic Benefits:**
- Adapt to season-long team performance changes  
- Respond to injuries or roster changes affecting NFL teams  
- Optimize stack composition for upcoming matchups  
- Balance betting flexibility with defensive resilience  
- Recover from early-season draft mistakes  

Trade deadlines are configurable by the commissioner. Trades throughout the regular season keep strategy dynamic and engaging.

---

## Commissioner Configuration

### Required
- Team Pool Multiplier  
- Number of Weeks (season length)  
- Weekly Hard Cap  
- Starting Bankroll (calculated as: Number of Weeks × Weekly Cap ÷ 2)  
- Minimum Bet Size  
- Sportsbook Open Time  
- Weekly Bet Deadline  

### Optional
- Allowed bet types  
- Parlay toggle  
- Trade rules and deadlines  
- Schedule and playoff format  
- End-of-season awards  

---

## Example Week

Player A Stack: Chiefs, Bengals, Bears, Saints  
Player B Stack: 49ers, Cowboys, Jets, Lions  

- Player B places 500 units on 49ers ML  
- Player A uses Block on Cowboys before B uses them  
- Cowboys are now unavailable to B  
- Player A attempts Bengals +6.5 for 300 units  
- Player B Counters Bengals +6.5 before A locks it  
- A avoids the Countered bet and reallocates  
- Both participants hit the 1,000-unit cap  
- Games resolve; Stack Scores determine the winner  

---

## Platform & Communication

### Built-In Chat
Stacked includes **integrated chat** directly in the platform, eliminating the need for external communication tools like Slack or Discord.

**Features:**
- **League-specific channels** — General discussion, trade talk, trash talk, strategy  
- **Direct messaging** — Private conversations between participants  
- **Game alerts** — Real-time notifications for bets, defensive moves, and results  
- **Rich media support** — Share screenshots, memes, and reactions  
- **Message history** — Full conversation logs for each league  

Communication is central to the Stacked experience, fostering community and strategic discussion.

### Multi-League Accounts
Participants can join **multiple leagues** with a single account.

**Benefits:**
- Manage all your leagues from one dashboard  
- Switch between leagues seamlessly  
- Compare performance across different competitive levels  
- Join both casual and competitive leagues  
- Participate in pro/rel pyramid structures  

Your account tracks:
- All league memberships and standings  
- Cross-league statistics and achievements  
- Unified notification center  
- Personal performance history  

### Digital Extras & Customization
Express yourself with **paid digital extras** that enhance your online presence.

**Available Customization:**
- **Profile themes** — Custom colors, backgrounds, and layouts  
- **Avatar frames** — Decorative borders and effects  
- **Animated emojis** — League-specific reaction packs  
- **Chat badges** — Special icons and titles  
- **Victory celebrations** — Custom animations for wins  
- **Team logos** — Custom team branding (for commissioners)  

All digital extras are **cosmetic only** and do not affect gameplay. They support platform development while letting you personalize your Stacked experience.

---

## Summary
**Project Stacked** merges fantasy drafting, sportsbook-style betting, and real-time defensive timing into a unique competitive experience. Participants manage a persistent bankroll, draft the teams that define their betting options, and use one defensive move each week to disrupt opponent strategy—all under a fair, skill-based weekly cap.

**Draft your stack. Time your defense. Build your bankroll. Win the week.**
