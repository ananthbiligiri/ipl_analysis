# 🏏 IPL 2010 Analysis Dashboard - Power BI

This repository showcases an analytical Power BI dashboard built for the **Indian Premier League (IPL) 2010** season. The dashboard provides deep insights into team performances, top players, and match outcomes using interactive visuals and DAX measures.

![IPL Dashboard](./bb762c9b-af2e-40c4-b8b5-ff78f01119cb.png)

---

## 🧮 DAX Measures Used

### 🏏 Batting Metrics

**Total Runs**
```dax
Total Runs = SUM(BallData[Runs])
Total 6s = CALCULATE(COUNTROWS(BallData), BallData[Runs] = 6)
Total 4s = CALCULATE(COUNTROWS(BallData), BallData[Runs] = 4)
Strike Rate = 
DIVIDE(SUM(BallData[Runs]) * 100, SUM(BallData[BallsFaced]))
Fielding % = 
DIVIDE(
    CALCULATE(COUNTROWS(MatchData), MatchData[TossDecision] = "field"),
    COUNTROWS(MatchData)
)
Player Awards = 
CALCULATE(
    COUNT(MatchData[Player_of_the_Match]),
    ALLEXCEPT(MatchData, MatchData[Player_of_the_Match])
)
