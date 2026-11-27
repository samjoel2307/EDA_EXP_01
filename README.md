**#Experiment 1: EDA in IPL Dataset**

**Aim:**
To perform Exploratory Data Analysis (EDA) on the IPL matches dataset and derive insights about matches per season, winning teams, toss decisions, and top venues.

**Algorithm / Procedure:**

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
  
PROGRAM / OUTPUT
  ```
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

df = pd.read_csv("matches.csv")

print("Dataset Shape:", df.shape)
print("\nFirst 5 Rows:")
print(df.head())
```
<img width="862" height="692" alt="image" src="https://github.com/user-attachments/assets/1b11c543-d68a-415c-98b3-aa5515d7d9f8" />

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
<img width="927" height="467" alt="image" src="https://github.com/user-attachments/assets/45127bd0-b39f-455f-97a4-c1f944255eae" />

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
<img width="937" height="596" alt="image" src="https://github.com/user-attachments/assets/eb0a43af-e133-4ed8-b84a-13fb5478106e" />

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
<img width="918" height="597" alt="image" src="https://github.com/user-attachments/assets/448ebe35-d89d-4f1e-b8fb-a19f0bd2d37f" />

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
<img width="942" height="592" alt="image" src="https://github.com/user-attachments/assets/2521b4a6-a7d5-413b-974d-18c0ef3f3099" />

DISPLAY STADIUMS HOSTING MAXIMUM MATCHES

```
print("\nTop 5 Stadiums Hosting Maximum Matches:")
print(top_venues)
```
<img width="630" height="187" alt="image" src="https://github.com/user-attachments/assets/f4c5931c-2e04-41fb-82f7-cca1ab7ebc08" />

DRAW INSIGHTS


```
print("\nEDA INSIGHTS")
print("Total Matches:", len(df))
print("Most Successful Team:", df['winner'].value_counts().idxmax())
print("Most Preferred Toss Decision:", toss_decisions.idxmax())
print("Stadium Hosting Maximum Matches:", top_venues.idxmax())
```
<img width="683" height="198" alt="image" src="https://github.com/user-attachments/assets/f6194b43-e27f-463a-93ec-a37bb123c2be" />

 ** Result**
 
  This experiment is executed successfully


