# README 

# Data set description 

pgaTourData.csv contains ... rows and ...columns. Each row indicates a golfer's performance for that year.

- Player Name: Name of the golfer
- Rounds: The number of games that a player played
- Fairway Percentage: The percentage of time a tee shot lands on the fairway
- Year: The year in which the statistic was collected
- Avg Distance: The average distance of the tee-shot
- Green in Regulation: is met if any part of the ball is touching the putting surface while the number of strokes taken is at least two fewer than par
- Average Putts: The average number of strokes taken on the green
- Average Scrambling: Scrambling is when a player misses the green in regulation, but still makes par or better on a hole
- Average Score: Average Score is the average of all the scores a player has played in that year
- Points: The number of FedExCup points a player earned in that year. These points can be earned by competing in tournaments.
- Wins: The number of competition a player has won in that year
- Top 10: The number of competitions where a player has placed in the Top 10
- Average SG Putts: Strokes gained: putting measures how many strokes a   player gains (or loses) on the greens.
- Average SG Total: The Off-the-tee + approach-the-green + around-the-green + putting statistics combined
- SG:OTT: Strokes gained: off-the-tee measures player performance off the tee on all par-4s and par-5s.
- SG:APR: Strokes gained: approach-the-green measures player performance on approach shots. Approach shots include all shots that are not from the tee on par-4 and par-5 holes and are not included in strokes gained: around-the-green and strokes gained: putting. Approach shots include tee shots on par-3s.
- SG:ARG: Strokes gained: around-the-green measures player performance on any shot within 30 yards of the edge of the green. This statistic does not include any shots taken on the putting green.
- SG_TOTAL: all stokes gained minus the strokes gained putting.

# PROJECT:

- Pandas:

I started by web scrapping 9 different pages of the  official PGA Tour website (https://www.pgatour.com/) which provides all sorts of data for all major golf tournaments. The website provides plentty of historical and I took this opportunity in order to go back to 2012 and start building the data frame that I wanted from the FedEx Cup Tournament. In order to do so, I built a way to extract all the data that I needed for my study for each year and repeated the same process for all years from 2012 to 2021 and stored all those dataframes into a folder called data.

Next, I joined all the dataframes into a single one and I began to clean it. First I had to change all data types from strings to float numbers and to do so I had to clean almost every column from empty spaces and get rid of all commmas. Once that had been done, I made sure that there weren´t any empty spaces left and from there I started creating some columns which I believed were going to be usefull for my future analysis. (SCORE_AVERAGE, DRIVING_DISTANCE, DRIVING_ACCURACY, DRIVING USAGE, GREENS_IN_REGULATION%, SG_PUTTING and SG_TOTAL). I dropped the columns which I no longer needed and I saved that dataframe for future analysis.

- Seaborn and Matplotlib:

I decided to do a general visual analylis to get a look at the most valuable skills in golf are (in my opinion). I plotted SG:OTT, DRIVING_DISTANCE, DRIVING_ACCURACY, SG_PUTTING, GREENS_IN_REGULATION, SG_APR, SG_ARG, a Time line of all metrics to see the evolution that they have had and a comparison the metrics between players who won something that year and the average. 

I also decided to make a visual analysis for each player in oder to see their individual evolution. In order to do so a built a funtion that would return 3 different sections of visuals for the player that you wanted. The 1st section was a single plot that compared the evolution of SG metrics from tee to green individually. The 2nd gives 4 different visuals of SG:PUTTING, SG_TEE_to_GREEN (the sum) , and an evolution of the times they came withing the top 10. The 3rd section gives multiple smaller visuals of the evolution of al metrics

Finally I wanted to work on a predictive model, and here is where I ran into conflict. My first idea was to build a human predictive model and then a ML predictive model using a decision tree. But While doing the decision tree I realised that it didn´t make sense to do make it. Why? Because my model had a prercentage of predicting if the player was going to be a top_10 player of 90%, and you might think that tha tis pretty good, but the error in here is that it was predicting the top_10 players of the present year of that player. So, by providing data of the year 2020, the model would guess who the top_10 players of that year were, but I actually already know this with 100% of accuracy because the data/statistics that I can provide are from the past, and not from the future. My model was not predicting who the next year winners were going to be. 

So I tested I human predictive model, and I then compared one years top_10 players with the next year top_10 players. I discovered that 4.9 players on average, since 2012 have been winners for two years in a row...
CONCLUSION: The best way to guess what players are going to win in 2022, we have the most chances if we take 2021 winners: 'Justin Thomas', 'Bryson DeChambeau','Russell Henley','Joaquin Niemann','Xander Schauffele','Webb Simpson','Viktor Hovland','Jon Rahm','Dustin Johnson','Cameron Tringale'. And Make a player analysis of each of them showing their progress over their last 10 years. And with that information and your personal conclusions from the visual analysis you can can now place your bets.



