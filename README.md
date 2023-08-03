# NFL Fantasy MVP Analysis

The goal of this case study is to read in the Fantasy Football information we have gathered in order to determine the best player at certain positions every year (1999 - 2019) in the NFL.

My strategy is to use Fantasy Points as a basis for individual performance. However, a major part will be instead of just judging players soley on how many points they gain in a season we will also be looking at how good their opponent's defense was against their position.

## Data Collection & Cleaning

Firstly we will read in the fantasy data, cleaning it and adding the different opponents to the data from a schedule file. We will then remove the outliers from the data before finding average performance by position through the years. We will find the average using EMA. We will then find the average yearly performance of each team's defense against the 5 positions we are tracking for each individual year. To normalize our data we will be taking the difference between the opponent team's average fantasy points given up and the positons EMA for that year. That difference will give us our Adjusted Points Value. A players Adjusted Point value will be totaled for the entire season, the player with the highest total Adjusted Points for the year at their position will be determined the top preformer.

The NFL Schedule for the 1999 - 2019 Seasons was originally scraped from pro-football-reference.com. The Schedule uses the teams full name and needs to be converted into the abbrivation that is used in the Fantasy Data Set.

The fantasy data was taken from fantasyfootballdatapros.com. Here we are doing some small cleaning of the data and loading into a dataframe.

## Calculating Z-Scores and EMA

Calculate the Z-score by each years position group. A Z-Score is a tangable evaluation of how far from the mean a data point is. A performance with a Z-Score higher then 3.0 or less then -3.0 is determined to be an outlier and removed from the calculations.

The EMA, or Exponential Moving Average, is commonly used as a technical indicator in Finance however it more generally is a way of calculating averages over time so that the more recent data has a larger weight in the factoring of the average. The EMA is used in this case to acknowledge that football is a changing game and as such more recent data is more accurate to the future and present of the game then past data, but at the same time that past data can still provide inside in a limited capacity.

## Normalizing Data

Calculate the averages of each team's defense against each position grouping every year. Using these averages compared to the EMA value of the leagues points at that position will give us our desired offset for normalization.

## Calculating Yearly Position Leaders

Add up all the performances for each player across the entire season to get the total AdjPts earned for each season per player. Then sort each yearly position list by total AdjPts to find the leader.

## Results

Based on our calculations here are the top players at their positions for each year examined:

| Year | QB | WR | TE | FB | HB |
| ---- | -- | -- | -- | -- | -- |
| 1999 | Kurt Warner | Randy Moss | Wesley Walls | Jonathan Linton | Edgerrin James |
| 2000 | Daunte Culpepper | Cris Carter | Chad Lewis | Tony Richardson | Edgerrin James |
| 2001 | Kurt Warner | David Boston | Tony Gonzalez | Larry Centers | Ahman Green |
| 2002 | Rich Gannon | Hines Ward | Bubba Franks | Larry Centers | Ricky Williams |
| 2003 | Daunte Culpepper | Randy Moss | Tony Gonzalez | Richie Anderson | Priest Holmes |
| 2004 | Daunte Culpepper | Torry Holt | Alge Crumpler | Patrick Pass | Tiki Barber |
| 2005 | Tom Brady | Larry Fitzgerald | Antonio Gates | Kyle Johnson | Clinton Portis |
| 2006 | Peyton Manning | Terrell Owens | Antonio Gates | Mike Alstott | Frank Gore |
| 2007 | Tom Brady | Randy Moss | Chris Cooley | Leonard Weaver | Adrian Peterson |
| 2008 | Drew Brees | Steve Smith | Tony Gonzalez | Le'Ron McClain | Matt Forte |
| 2009 | Aaron Rodgers | Steve Smith | Brent Celek | Le'Ron McClain | Adrian Peterson |
| 2010 | Tom Brady | Mike Williams | Mercedes Lewis | Marcel Reece | Chris Johnson |
| 2011 | Tom Brady | Calvin Johnson | Jimmy Graham | John Kuhn | LeSean McCoy |
| 2012 | Drew Brees | Demaryius Thomas | Heath Miller | James Casey | Arian Foster |
| 2013 | Drew Brees | Dez Bryant | Jimmy Graham | Mike Tolbert | Jamaal Charles |
| 2014 | Aaron Rodgers | Randall Cobb | Rob Gronkowski | Bruce Miller | Eddie Lacy |
| 2015 | Tom Brady | Brandon Marshall | Rob Gronkowski | Kyle Juszczyk | Adrian Peterson |
| 2016 | Aaron Rodgers | Mike Evans | Kyle Rudolph | Jamize Olawale | Ezekiel Elliott |
| 2017 | Russell Wilson | Michael Thomas | Zach Ertz | Mike Tolbert | LeSeasn McCoy |
| 2018 | Patrick Mahomes | Julio Jones | Zach Ertz | James Develin | Todd Gurley |
| 2019 | Lamar Jackson | Kenny Golladay | Travis Kelce | Kyle Juszczyk | Ezekiel Elliott |
