**#Experiment 1: EDA in IPL Dataset**
**AIM:**
To perform Exploratory Data Analysis (EDA) on the IPL matches dataset and derive insights about matches per season, winning teams, toss decisions, and top venues.

**ALGORITHM / PROCEDURE:**

**1.Import Libraries**
  Import pandas for data handling.
  Import matplotlib and seaborn for visualization.
  
**2.Load Dataset**
  Use pd.read_csv() to load the IPL matches dataset.
  Check dataset shape using .shape.
  View first 5 rows using .head().
  
**3.Matches per Season (Univariate Analysis)**
  Group data by season and count matches.
  Plot a bar chart to visualize growth/decline in matches.
  
**4.Top Winning Teams (Univariate Analysis)**
  Use value_counts() on the winner column.
  Plot top 5 winning teams in a bar chart.
  
**5.Toss Decisions (Univariate Analysis)**
  Count toss decision preferences (bat vs field).
  Plot results using a bar chart.
  
**6.Top Venues (Univariate Analysis)**
  Count matches per venue.
  Display top 5 venues with a horizontal bar chart.
  
**7.Draw Insights**
  Observe patterns in toss decisions.
  Identify teams with consistent winning trends.
  
  **PROGRAM / OUTPUT**

  ```
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

df = pd.read_csv("matches.csv")

print("Dataset Shape:", df.shape)
print("\nFirst 5 Rows:")
print(df.head())
```
<img width="1017" height="758" alt="image" src="https://github.com/user-attachments/assets/d8491d0d-121b-4c3d-8421-cf4e9cf95ffe" />

MATCHES PER SEASON

```
plt.figure(figsize=(12, 5))
matches_per_season = df.groupby('season').size()

sns.barplot(x=matches_per_season.index,
            y=matches_per_season.values)

plt.title("Number of IPL Matches per Season")
plt.xlabel("Season")
plt.ylabel("Number of Matches")
plt.xticks(rotation=45)
plt.tight_layout()
plt.show()
```

<img width="1108" height="557" alt="image" src="https://github.com/user-attachments/assets/a221ace6-eb9c-4a2b-914e-1b732dbfcab2" />

TOP 5 WINNING TEAMS

```
plt.figure(figsize=(10, 5))
top_teams = df['winner'].value_counts().head(5)

sns.barplot(x=top_teams.index, y=top_teams.values)

plt.title("Top 5 Winning Teams in IPL")
plt.xlabel("Teams")
plt.ylabel("Number of Wins")
plt.xticks(rotation=30, ha='right')
plt.tight_layout()
plt.show()

```
<img width="1093" height="700" alt="image" src="https://github.com/user-attachments/assets/8f31681c-4fc8-4405-a058-82f5debd1631" />


TOSS DECISIONS

```
plt.figure(figsize=(7, 5))
toss_decisions = df['toss_decision'].value_counts()

plt.bar(toss_decisions.index, toss_decisions.values)

plt.title("Toss Decision Preferences")
plt.xlabel("Toss Decision")
plt.ylabel("Number of Matches")
plt.show()

```
<img width="1001" height="646" alt="image" src="https://github.com/user-attachments/assets/3798e968-537d-43cd-b256-70ebcd189bcf" />

TOP 5 VENUES

```
plt.figure(figsize=(10, 5))
top_venues = df['venue'].value_counts().head(5)

sns.barplot(x=top_venues.values, y=top_venues.index)

plt.title("Top 5 IPL Stadiums Hosting Maximum Matches")
plt.xlabel("Number of Matches")
plt.ylabel("Stadiums")
plt.tight_layout()
plt.show()
```
<img width="1067" height="686" alt="image" src="https://github.com/user-attachments/assets/cc010681-39d2-4421-b5a1-6b84031317f0" />

DISPLAY STADIUMS HOSTING MAXIMUM MATCHES
```
print("\nTop 5 Stadiums Hosting Maximum Matches:")
print(top_venues)
```
<img width="951" height="197" alt="image" src="https://github.com/user-attachments/assets/383930d4-fe54-4aa2-9bc0-ebe5ebdf2c4b" />

DRAW INSIGHTS
```
print("\nEDA INSIGHTS")
print("Total Matches:", len(df))
print("Most Successful Team:", df['winner'].value_counts().idxmax())
print("Most Preferred Toss Decision:", toss_decisions.idxmax())
print("Stadium Hosting Maximum Matches:", top_venues.idxmax())
```
<img width="870" height="217" alt="image" src="https://github.com/user-attachments/assets/ee1f9adc-fc39-4d79-b159-6f32b21fa546" />

  **RESULT**
 
  This experiment is executed successfully


