# NBA Player Data Analysis

A comprehensive data analysis project exploring NBA player statistics, performance metrics, and historical trends using multiple datasets.

## Project Overview

This project analyzes NBA player data from three different CSV files to uncover insights about player characteristics, position-based performance, and efficiency trends across decades.

##  Data Sources

The analysis uses three datasets:

1. **Players.csv** - Basic player information
   - 3,922 rows × 8 columns
   - Contains: Player name, height, weight, college, birth date, birth city, birth state

2. **player_data.csv** - Career statistics
   - 4,550 rows × 8 columns
   - Contains: Name, career start/end years, position, height, weight, birth date, college

3. **Seasons_Stats.csv** - Seasonal performance metrics
   - 24,691 rows × 53 columns
   - Contains: Year, Player, Position, Age, Team, Games, PER, Points (PTS), Rebounds (TRB), Assists (AST), and advanced metrics

## Key Analyses

### 1. Player Lookup
- Query specific players (e.g., Stephen Curry)
- Retrieve career statistics and biographical information

### 2. Position-Based Performance
- **Scoring by Position**: Average points per position
  - Highest scoring: SG-PF (1,152 pts), PG-SF (1,022 pts)
  - Traditional big men: C (452 pts), PF (500 pts)
  
- **Rebounding by Position**: Average rebounds per position
  - Best rebounders: C (326), PF (307), C-PF (271)
  
- **Playmaking by Position**: Average assists per position
  - Top playmakers: PG (226 assists), PG-SF (329 assists)

### 3. Efficiency Trends
- **PER (Player Efficiency Rating)** analysis across decades
- Decade-by-decade performance averages:
  - 1950s: 12.29
  - 1970s: 12.96 (peak era)
  - 2010s: 12.52

## Technologies Used

- **Python 3.x**
- **pandas** - Data manipulation and analysis
- **matplotlib** - Data visualization (imported but not yet utilized)

## 📈 Sample Queries

```python
# Look up Stephen Curry's career stats
curry_stats = df3[df3['Player'] == 'Stephen Curry']

# Get average points by position
scoring_by_position = df3.groupby('Pos')['PTS'].mean()

# Analyze efficiency by decade
df3['Decade'] = (df3['Year'] // 10) * 10
efficiency_by_decade = df3.groupby('Decade')['PER'].mean()
```
## Key Insights
1. Position Versatility: Hybrid positions (PG-SF, SG-PF) often show higher statistical output
2. Evolution of Play: Point guards dominate assists (225+ average), while centers lead in rebounds (326 average)
3. Efficiency Trends: Player efficiency peaked in the 1970s (12.96 PER) and has remained relatively stable
4. Scoring Evolution: Modern hybrid positions show increased scoring compared to traditional positions
