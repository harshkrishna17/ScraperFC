
# Welcome
This is ScraperFC, a Python package that I hope will give more people access to soccer stats. It's still very much a work in progress and I'm currently a full-time grad student so progress may be slow. I am trying to chip away at it though, so please, reach out with any problems you encounter or features you want to see added!

# Installing
ScraperFC can be installed by running "pip install ScraperFC" from the command line.

# Sources
For now, ScraperFC can get data from the following websites (all data is open-source and I am not affiliated with any of the sources):
* [FBRef](#FBRef) ([link](https://fbref.com/en/))
* [Understat](#Understat) ([link](https://understat.com/))
* [FiveThirtyEight](#FiveThirtyEight) ([link](https://projects.fivethirtyeight.com/soccer-predictions/))

# FBRef
Both seasonal match data and seasonal squad stats can be scraped from FBRef. To use the FBRef module, run 
```
import ScraperFC as sfc
scraper = sfc.FBRef()
# call function(s) with FBRef scraper object
scraper.close() # closes the Selenium webdriver
```
Any FBRef functions can then be called from the scraper object.

To scrape match data for a season, call ```scraper.scrape_matches(year, league, save)``` where:
* ```year``` is the calendar year the season ended in. E.g. for the 2019/2020 season, enter 2020 (type int, not string).
* ```league``` is the league you want data from. Options are "EPL", "La Liga", "Bundesliga", "Serie A", "Ligue 1".
* ```save``` is a boolean option to save the output dataframe to a CSV. Default value is false.

Individual matches can also be scraped with ```scraper.scrape_match(link, league)``` where:
* ```link``` is the URL to the match you want to be scraped
* ```leauge``` is the league the match was a part of. The only supported leagues are the "EPL", "La Liga", "Bundesliga", "Serie A", "Ligue 1".

Squad seasonal data can be scraped with the following functions. Each function, except ```scrape_league_table()``` and ```scrape_season```, return 2 tables. The first table is stats for the squads (e.g. goals for), the second is stats versus the squads (e.g. goals against).
* ```scraper.scrape_league_table(args)```
* ```scraper.scrape_standard(args)```
* ```scraper.scrape_gk(args)```
* ```scraper.scrape_adv_gk(args)```
* ```scraper.scrape_shooting(args)```
* ```scraper.scrape_passing(args)```
* ```scraper.scrape_passing_types(args)```
* ```scraper.scrape_goal_shot_creation(args)```
* ```scraper.scrape_defensive(args)```
* ```scraper.scrape_possession(args)```
* ```scraper.scrape_playing_time(args)```
* ```scraper.scrape_misc(args)```
* ```scraper.scrape_season(args)``` (This function returns all of the above tables in a dict.)

All of the above functions take the same three arguments:
* ```year``` The calendar year the season ended in. E.g. for the 2019/2020 season, enter 2020 (type int, not string).
* ```league``` The source league of the data. The only supported leagues are the "EPL", "La Liga", "Bundesliga", "Serie A", "Ligue 1".
* ```normalize``` Option to normalize the table to per 90. Default value is false.

# Understat
Documentation coming soon.

# FiveThirtyEight
Documentation coming soon.

# Contact
I'd love to hear whatever feedback, advice, criticisim, complaints, problems, errors, or new ideas you have or have come across while using ScraperFC! My email is osmour043@gmail.com.
        
