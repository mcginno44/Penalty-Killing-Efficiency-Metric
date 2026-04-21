# Penalty-Killing-Efficiency-Metric
There exists no single metric in hockey, at least currently, that grades a player's value as a penalty killer. Penalty killing is extremely important in the sport; it's how games are won and lost, so I felt there should be a way to assess player contribution and impact. 
This project entails my creation of an original Penalty Kill Efficiency Metric (PKEM) to evaluate player contributions in short-handed situations. I gathered data from 17 NHL seasons, both regular season and playoffs, for each individual player and their advanced stats(from Moneypuck) and created a single, all-encompassing metric to evaluate how good the player is at killing penalties, their contributions to team penalty-killing, and their impact when on the ice. Traditional measures of blocks, shots against, and goals against are helpful, but digging deeper into penalty killing does not have its own metric. I also examined team-level numbers to discover a link between penalty killing success(determined by an average of the players' PKEM) and wins. Included with the code are visuals of team-average metrics across years, graphed with regular season wins(up to the 2019-20 season), a table of the top-20 defensemen, and a classification tree for Stanley Cup Winners. 

PKEM = (((flurryAdjustedxGoalsAgainst - GoalsAgainst) /  OnIceUnblockedShotAttemptsAgainst) + (takeawaysByPlayer + shotsBlockedByPlayer) * (playerIceTime/total_team_shorthanded_time)*100 ) / games_played)

Essentially, a higher score indicates a greater positive impact on penalty-killing. A player will have to have high rates of goals against expected, combined takeaways and blocks across a large share of short-handed ice time. 

Methodology-
1. Feature Engineering
   - Time on ice (shorthanded)
   - Blocks, faceoff %, goals against
   - Context features (score, manpower, game situation)

2. Player Profiling
   - Aggregated event-level data into player-level penalty-kill profiles

3. Modeling
   - Built classification trees to identify drivers of Stanley Cup-winning teams

4. Metric Construction
   - Combined features into PKEM using weighted contributions
   - Adjusted for usage and context
