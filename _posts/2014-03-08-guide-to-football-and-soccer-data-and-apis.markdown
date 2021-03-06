---
author: jokecamp
comments: true
date: 2014-03-08 17:08:40+00:00
layout: post
slug: guide-to-football-and-soccer-data-and-apis
title: Guide to Football/Soccer data and APIs
desc: "A list of soccer and football apis, data sets, data services and websites available for developers looking for open data."
wordpress_id: 1369
categories:
- guide
tags:
- api
- opendata
- sportsdata
featured: true
---

Last updated: Nov 26 2014

## <i class="fa fa-futbol-o"></i> Where can I actually find football/soccer data?

There are three main ways to get data. You can parse/scrape it from a hobbyist project/website, you can pay for it or you can try to collect it yourself.

Jump to a specific source:

- Open source data on github
  - [openfootball - football.db](#openfootball)
  - [jokecamp/FootballData](#fdata)
  - [socerstats.us](#soccerstats)
  - [Other smaller projects/repos](#repos)
- Free APIs
  - [football-data.org](#footballdata) (beta) (RESTful)
  - [openfooty API](#openfooty) (hard to get an API Key)
- Commercial APIs
  - [football-api.com](#footballapi)
  - [CrowdScores and FastestLiveScores](#CrowdScores)
  - [XMLSoccer.com](#xmlsoccer)
  - [opta](#opta)
  - [prozone](#prozone)
  - [Match Analaysis](#matchanalysis)
- Other Websites
  - [footballsquads.co.uk](#footballsquads.co.uk)
  - [Rec.Sport.Soccer Statistics Foundation (RSSSF)](#rsssf)
  - [football-data.co.uk](#football-data.co.uk)
  - [european-football-statistics.co.uk](#european-football-statistics.co.uk])
  - [openligadb.db](#openligadb.db)
  - [Wikipedia](#wiki)
  - [Post War English & Scottish Football League A - Z Player's Database](#postwar)
- [World Cup 2014 APIs](#worldcup)
- [Deprecated/Retired - "The Graveyard of APIs](#api-graveyard)
- [More Reading / Resources / Links](#other)


<a name="github"></a>
### <i class="fa fa-futbol-o"></i> Open Source Data on Github

<a name="openfootball"></a>
#### openfootball - aka football.db

**[openfootball (aka football.db)](http://openfootball.github.io/)** has started a free, open source public domain football database.
The data is historical data, meaning no lives scores but the data does include the schedule, teams and players for the 2014 World Cup along with global league data. This is a very promising project and has the **potential to be the definitive source for historical data for the public**.
See the [opensport Google Group](https://groups.google.com/forum/#!forum/opensport) for discussion and questions. The data is stored in various repos on github.
Consider contributing any data you have yourself and be sure to thank [Gerald Bauer](https://github.com/geraldb). All the various repos can be intimidating. A good place to start is at [github.com/openfootball](https://github.com/openfootball/).

An example of the plain text (custom format):

    [Sat Aug/16]
      12.45  Manchester United    1-2  Swansea City
      15.00  Leicester City       2-2  Everton FC
      15.00  Queens Park Rangers  0-1  Hull City
      15.00  Stoke City           0-1  Aston Villa


Check out the following github organizations for more listings:

 - <https://github.com/footballcsv>
 - <https://github.com/openfootball>
 - <https://github.com/rsssf>
 - <https://github.com/footballdata>

There is also an open source football.db HTTP JSON(P) [API](http://openfootball.github.io/docs/json-api-intro.html) for demo purposes. Example Endpoints:

    http://footballdb.herokuapp.com/api/v1/event/world.2014/teams
    http://footballdb.herokuapp.com/api/v1/event/world.2014/round/1

<a name="fdata"></a>
#### jokecamp/FootballData

[jokecamp/FootballData](https://github.com/jokecamp/FootballData) - my own hodgepodge of JSON and CSV Football/Soccer data on GitHub with a focus on the EPL

<a name="soccerstats"></a>
#### soccerstats.us

**[soccerstats.us](http://soccerstats.us)** is github [organization](https://github.com/soccerstatsus) with multiple repositories for sets of data (with a focus on North American data). The [parser](https://github.com/SoccerStatsUS/parse) is written in python and looks like it was designed to parse the rsssf.com text data.

<a name="repos"></a>
#### Other smaller Projects/Repos

 - [github.com/jalapic/engsoccerdata](https://github.com/jalapic/engsoccerdata) includes a [csv file](https://github.com/jalapic/engsoccerdata/blob/master/engsoccerdata.csv) of the top 4 tier English League Soccer games from 1888 to 2014.

<a name="free"></a>
### <i class="fa fa-futbol-o"></i> Free APIs

<a name="footballdata"></a>
#### football-data.org (beta)

[football-data.org](http://www.football-data.org/) is a RESTful API in beta with regularly updated data. If you [register for a free API key](http://www.football-data.org/register) you will get CORS support. I recommend registering for a key to show your support and help the service track usage. However, a key is not required yet so you can try out the endpoints right now. I am excited to see this API grow and mature!

Available endpoints

    /soccerseasons/
    /soccerseasons/{id}/ranking
    /soccerseasons/{id}/fixtures
    /fixtures
    /soccerseasons/{id}/teams
    /teams/{id}
    /teams/{id}/fixtures/

Some example calls:

- <http://www.football-data.org/soccerseasons/>
- <http://www.football-data.org/soccerseasons/351/teams>
- <http://www.football-data.org/fixtures>
- <http://www.football-data.org/teams/5>


Example JSON output for a team:

    { "id":5,
      "name":"FC Bayern München",
      "shortName":"Bayern",
      "crestUrl":"http://upload.wikimedia.org/wikipedia/commons/c/c5/Logo_FC_Bayern_M%C3%BCnchen.svg"
    }

<a name="openfooty"></a>
#### openfooty API

[openfooty API](http://www.footytube.com/openfooty/) had promising API documentation but a quick look at the developer forums shows a stale community and questions about why no one seems to actually be able to get a developer key.


<a name="commerical"></a>
### Subscription Services/APIs

<a name="footballapi"></a>
#### football-api

[football-api.com](http://football-api.com/) is a paid API service but does offer the English Premier League endpoints for free (demo use). The API will restrict by IP addresses and limit calls based on your package. Includes endponts for Competitions, teams, standings, live scores, fixtures and commentaries. See the [pricing page](http://football-api.com/pricing/).

Example endpoints:

    api/?Action=competitions&APIKey=####
    api/?Action=standings&comp_id=1204&APIKey=####
    api/?Action=today&comp_id=1204&APIKey=####
    api/?Action=fixtures&comp_id=1024&&match_date=[DATE_IN_d.m.Y_FORMAT]&APIKey=####
    api/?Action=commentaries&APIKey=###&match_id=[MATCH_ID]

<a name="CrowdScores"></a>
#### CrowdScores and FastestLiveScores

[CrowdScores](https://crowdscores.com/) is a UK company trying to crowd-source the football data collection process. You sign up for an account and report game events to their servers. They have web/iphone/android interfaces for reporting. They reward the top data reporters. The collected data is then available as an API on [FastestLiveScores.com](http://fastestlivescores.com/). They currently offer [three different API tiers](http://fastestlivescores.com/live-scores-api-feed/). Basic, Pro and Complete. The basic tier is suppose to be free with 3 calls allowed per hour. However, looks like they are only giving keys on a user by user basis. I requested access to the basic tier but have not received access yet. I only received an email asking me why I needed access and what I planned to do with their API.


<a name="xmlsoccer"></a>
#### XMLSoccer.com

[xmlsoccer.com](http://www.xmlsoccer.com/) is another subscription service. You can demo the service for free with the Scottish Premier League. The monthly pricing is 10 &#8364; per 1 month, 25 &#8364; per 3 months and 90 &#8364; per 12 months. You can browse the demo web methods here to see the types of calls available <http://www.xmlsoccer.com/FootballDataDemo.asmx> and the [WSDL](http://www.xmlsoccer.com/FootballDataDemo.asmx?WSDL). The data is only returned in XML.

Each call must provide an API Key. You can get a free demo API Key by registering.

Example results for a team

```xml
<XMLSOCCER.COM>
  <Team>
    <Team_Id>45</Team_Id>
    <Name>Aberdeen</Name>
    <Country>Scotland</Country>
    <Stadium>Pittodrie Stadium</Stadium>
    <HomePageURL>http://www.afc.co.uk</HomePageURL>
    <WIKILink>http://en.wikipedia.org/wiki/Aberdeen_F.C.</WIKILink>
  </Team>
<XMLSOCCER.COM>
```

Player data

```xml
<Player>
  <Id>2523</Id>
  <Name>David Goodwillie</Name>
  <Height>1.7</Height>
  <Weight>70.29</Weight>
  <Nationality>Scotland</Nationality>
  <Position>Forward</Position>
  <Team_Id>45</Team_Id>
  <PlayerNumber>17</PlayerNumber>
  <DateOfBirth>1989-03-28T00:00:00-08:00</DateOfBirth>
  <DateOfSigning>2014-07-07T00:00:00-07:00</DateOfSigning>
  <Signing>Free</Signing>
</Player>
```

<a name="opta"></a>
#### opta

[opta](http://www.optasports.com) is one of industry leaders. This is what the tv networks use and likely what the actual football clubs use for [scouting](http://www.optasportspro.com/products/scouting-reports-and-data-feeds.aspx). If only this data were public! However, [opta Playground](http://www.optasports.com/playground-section.aspx) has a developer program that provides very limited access to historical data. The site reads "Opta can provide data for programmers wishing to develop a mobile app or website with selected historical data available to download." You have to request permission in an email. I applied and they sent me the xml data set for 10 rounds of games from the start of the 2007/2008 Bundesliga 2. The more detailed game data had either x,y coordinates of game events. A very impressive dataset but it felt more like an advertisement. The data provided I had no interest in and I'm not sure why an indie developer would spend time working on a data set they could never afford. They even track this data point "Spectator on pitch." Read this article [FiveThirtyEight behind the scenes look at how opta tracks data](http://fivethirtyeight.com/features/the-people-tracking-every-touch-pass-and-tackle-in-the-world-cup/) (spoiler: young male gamers).

An example of an "event" in xml

```xml
<Event id="1115853439" event_id="9" type_id="3"
    period_id="1" min="0" sec="19" player_id="21202"
    team_id="1744" outcome="1" x="64.9" y="11.6"
    timestamp="2007-08-19T13:02:08.482" last_modified="2007-08-19T13:02:13">
        <Q id="152113216" qualifier_id="56" value="Right"/>
</Event>
```

<a name="prozone"></a>
#### prozone

[prozone](http://www.prozonesports.com/) is another large commercial data provider.

<a name="matchanalysis"></a>
#### Match Analysis

[Match Analysis](http://matchanalysis.com/) is another large commercial data provider that lists Fox Soccer Channel, US National Team and the MLS among their clients.

<a name="other"></a>
### <i class="fa fa-futbol-o"></i> Other Websites

<a name="footballsquads.co.uk"></a>
#### FootballSquads

[footballsquads.co.uk](http://www.footballsquads.co.uk/) has current and historical squad details for clubs (rosters) and national teams from all across the world for many leagues and competitions, including the 2014 World Cup squads.

And example of the squad/roster data:

    Num  Name         Nat	Pos  Height	  Weight	Date of Birth	 Birth Place	 Previous Club
    1    David De Gea ESP	 G	   1.92	   82	     07-11-90	     Madrid	         Atlético Madrid
    2    Rafael       BRA	 D	   1.72	   65	     09-07-90	     Petrópolis	  Fluminense

<a name="rsssf"></a>
#### Rec.Sport.Soccer Statistics Foundation (RSSSF)

[Rec.Sport.Soccer Statistics Foundation](http://www.rsssf.com/) (RSSSF) has massive collection of formatted plain text statistics. [An example of English Premier leagues results](http://www.rsssf.com/tablese/eng2015.html#premier).

Example of the data for table results:

    1.Chelsea                  8   7  1  0  23- 8  22
    2.Manchester City          8   5  2  1  18- 8  17
    3.Southampton              8   5  1  2  19- 5  16
    4.West Ham United          8   4  1  3  15-11  13

and scores:

    Round 1
    [Aug 16]
    Arsenal       2-1 Crystal P
    Leicester     2-2 Everton


<a name="football-data.co.uk"></a>
#### football-data.co.uk

[football-data.co.uk](http://www.football-data.co.uk/data.php) is a betting and odds website that has made a lot of historical league data available as csv files. The data includes results and a lot of betting/odds related data. I have tried to aggregate and clean up the data in the following repo [github.com/jokecamp/FootballData](https://github.com/jokecamp/FootballData)

Leagues and divisions included:

    England Football Results  	Premiership & Divs 1,2,3 & Conference
    Scotland Football Results  	Premiership & Divs 1,2 & 3
    Germany Football Results  	Bundesligas 1 & 2
    Italy Football Results  	Serie A & B
    Spain Football Results  	La Liga (Premera & Segunda)
    France Football Results  	Le Championnat & Division 2
    Netherlands Football Results  	KPN Eredivisie
    Belgium Football Results  	Jupiler League
    Portugal Football Results  	Liga I
    Turkey Football Results  	Ligi 1
    Greece Football Results  	Ethniki Katigoria

The key/legend of all the field abbreviations gives you idea of what is available in the CSV files:

    Div = League Division
    Date = Match Date (dd/mm/yy)
    HomeTeam = Home Team
    AwayTeam = Away Team
    FTHG = Full Time Home Team Goals
    FTAG = Full Time Away Team Goals
    FTR = Full Time Result (H=Home Win, D=Draw, A=Away Win)
    HTHG = Half Time Home Team Goals
    HTAG = Half Time Away Team Goals
    HTR = Half Time Result (H=Home Win, D=Draw, A=Away Win)

    Match Statistics (where available)
    Attendance = Crowd Attendance
    Referee = Match Referee
    HS = Home Team Shots
    AS = Away Team Shots
    HST = Home Team Shots on Target
    AST = Away Team Shots on Target
    HHW = Home Team Hit Woodwork
    AHW = Away Team Hit Woodwork
    HC = Home Team Corners
    AC = Away Team Corners
    HF = Home Team Fouls Committed
    AF = Away Team Fouls Committed
    HO = Home Team Offsides
    AO = Away Team Offsides
    HY = Home Team Yellow Cards
    AY = Away Team Yellow Cards
    HR = Home Team Red Cards
    AR = Away Team Red Cards
    HBP = Home Team Bookings Points (10 = yellow, 25 = red)
    ABP = Away Team Bookings Points (10 = yellow, 25 = red)

<a name="european-football-statistics.co.uk]"></a>
#### european-football-statistics.co.uk

[www.european-football-statistics.co.uk](http://www.european-football-statistics.co.uk/) is a visually dated website but has a lot of historical football data (mostly an overview of league/tournament results) displayed in nice clean HTML tables. Looks like they already have 2014 EPL stats. The site claims "The target of this site is to collect european football statistics which are not easily found on internet."

<a name="openligadb.db"></a>
#### openligadb.db

[openligadb.db](http://www.openligadb.de/Webservices/Sportsdata.asmx) has an old-school windows asmx web service with methods such as "GetGoalsByMatch()"

<a name="wiki"></a>
#### Wikipedia

[Wikipedia](http://www.wikipedia.org/) - has a lot of structured data and is also crowd/public sourced. You can use their API to query then parse the data. It is very fragmented into specific pages making this a good source if you are looking for very specific team/player data. For example here is a table of Manchester United season results <http://en.wikipedia.org/wiki/List_of_Manchester_United_F.C._seasons>.

<a name="postwar"></a>
#### Post War English & Scottish Football League A - Z Player's Database

[Post War English & Scottish Football League A - Z Player's Database](http://www.neilbrown.newcastlefans.com/index.html) contains a lot of HTML tables of "players who appeared for their clubs between 1946/47 and the end of the 2013/14 season and who have now left their clubs." Here is a list of [ex-Manchester United players](http://www.neilbrown.newcastlefans.com/manutd/manutd.html).

Stats included are: NAME, POS, SEASONS, SOURCE, TRANSFERRED TO, APPS, GOALS

<a name="worldcup"></a>
### <i class="fa fa-futbol-o"></i> 2014 World Cup APIs

[kimono labs 2014 World Cup Api](https://www.kimonolabs.com/worldcup/explorer) - has a very nice restful API available. Free registration required to access the API. The API has a player, team, club, matches, and player_season_stats endpoints. See the [documentation](https://www.kimonolabs.com/worldcup/docs) and start making calls withe the [API explorer](https://www.kimonolabs.com/worldcup/explorer)

[2014 World Cup JSON API - Soccer for Good](http://softwareforgood.com/soccer-good/) - The API is available now. The author explains that the data is from a scraper so the availability is not guaranteed but should be available throughout the tournament. There are endpoints for [teams](http://worldcup.sfg.io/teams), [matches](http://worldcup.sfg.io/matches), [today](http://worldcup.sfg.io/matches/today), [tomorrow](http://worldcup.sfg.io/matches/tomorrow) and [current](http://worldcup.sfg.io/matches/current). The Ruby on Rails source code is available on [Github](https://github.com/estiens/world_cup_json)

[World Cup in JSON](http://worldcup.sfg.io/) - an open source ruby project available at [github.com/estiens/world_cup_json](https://github.com/estiens/world_cup_json) that scrapes a few sources and combines into an API. API is available at http://worldcup.sfg.io/matches

[Unofficial FIFA.com JSON API for Mobile Apps](http://live.mobileapp.fifa.com/api/wc/matches)  This is unofficial and I wouldn't be surprised if it is protected/unavailable soon. Until then its nice to see data straight from the source. Known endpoints: [matches](http://live.mobileapp.fifa.com/api/wc/matches), [teams](http://live.mobileapp.fifa.com/api/wc/teams) or detailed [match info](http://live.mobileapp.fifa.com/api/wc/match/300186492/en)

<a name="api-graveyard"></a>
### <i class="fa fa-futbol-o"></i> Deprecated/Retired - "The Graveyard of APIs"

[ESPN API](http://developer.espn.com/docs) has an API for registered users (free). You can get a list of all the players in the EPL. However they are very limited in their data. They restrict all fixtures and scores to "strategic partners." However, you can get lists of players and teams. The **Public API is being retired on Monday, December 8, 2014** [Read the announcement](http://developer.espn.com/blog/read/publicretirement)

[StatsFC](https://statsfc.com/) used to have an restful JSON API of all EPL scores and fixtures. It was about $8 us dollars a month but was recently shut down. See their [official statement](https://statsfc.com/statement). They still offer widgets and they plan on reviving their servies. See their comments at the bottom of the page.

### <i class="fa fa-futbol-o"></i> Other Reading / Resources

#### opendata.stackexchange forum

[Are there any open datasets for Soccer statistics?](http://opendata.stackexchange.com/questions/1007/are-there-any-open-datasets-for-soccer-statistics) - keep your eye on this open data forum for more answers.

<a name="linkedsoccerdata"></a>
#### Linked Soccer Data

[Linked Soccer Data (pdf)](http://ceur-ws.org/Vol-1026/paper6.pdf) is a white paper on one group's attempt to "create a dataset including reliable information about soccer
events covering as many historical data as available including recent competition
results." Some dead links but worth a skim.

#### Other Links to explore

- [MLS Player Salary information](http://www.mlsplayers.org/salary_info.html) - 2007 to current salary amounts in pdf from the MLS Players union.
- See this 2012 [opisthokonta.net](http://opisthokonta.net/?page_id=995) blog post.
- [Football Club Elo Ratings Data & Source](http://clubelo.com/Data/)
- [sportscruncher links blog post](http://sportscruncher.wordpress.com/2013/03/01/links-soccer_data/) and [soccer ratings post](http://sportscruncher.wordpress.com/2013/03/14/links-soccer-ratings/)
- [Football kit colors](http://www.colours-of-football.com/)
- [Historial kits](http://www.historicalkits.co.uk/)
- [Fantasy Soccer Data Downloader on github](https://github.com/rasbt/datacollect/tree/master/collect_fantasysoccer)
- [ENFA - English National Football Archive](http://www.enfa.co.uk/)
- [Association of Football Statisticians (AFS)](http://www.11v11.com/about-afs/)
- [European football squads since 1999](http://en.eufo.de/site/about-us)
- FIFA Video Game Data at [leereilly/fifa-soccer-12-ultimate-team-data](https://github.com/leereilly/fifa-soccer-12-ultimate-team-data)
- [Football Stats and Betting data](http://www.statto.com/football/stats/)


### <i class="fa fa-futbol-o"></i> Share your own sources -- What have I missed?

Please let me know about your own data sources or add a pull request on [github](https://github.com/jokecamp/jokecamp.com/blob/master/_posts/2014-03-08-guide-to-football-and-soccer-data-and-apis.markdown). I have mainly searched for EPL data and would love to add data from other leagues/competitions to the list.


### Recommended Books

Show your support by buying and reading one of these books. Sorry for the shameless plug.

<div class="bookcovers">

<a href="http://www.amazon.com/gp/product/1612193684/ref=as_li_tl?ie=UTF8&camp=1789&creative=390957&creativeASIN=1612193684&linkCode=as2&tag=jokecamp-20&linkId=JTJ5DXJFI5TTGSDR"><img border="0" src="http://ws-na.amazon-adsystem.com/widgets/q?_encoding=UTF8&ASIN=1612193684&Format=_SL110_&ID=AsinImage&MarketPlace=US&ServiceVersion=20070822&WS=1&tag=jokecamp-20" class="bookcover" ></a><img src="http://ir-na.amazon-adsystem.com/e/ir?t=jokecamp-20&l=as2&o=1&a=1612193684" width="1" height="1" border="0" alt="" style="border:none !important; margin:0px !important;"  />

<a href="http://www.amazon.com/gp/product/1612193706/ref=as_li_tl?ie=UTF8&camp=1789&creative=390957&creativeASIN=1612193706&linkCode=as2&tag=jokecamp-20&linkId=VBXCWNPIRNJL7MPH"><img border="0" src="http://ws-na.amazon-adsystem.com/widgets/q?_encoding=UTF8&ASIN=1612193706&Format=_SL110_&ID=AsinImage&MarketPlace=US&ServiceVersion=20070822&WS=1&tag=jokecamp-20" class="bookcover" ></a><img src="http://ir-na.amazon-adsystem.com/e/ir?t=jokecamp-20&l=as2&o=1&a=1612193706" width="1" height="1" border="0" alt="" style="border:none !important; margin:0px !important;" />

<a href="http://www.amazon.com/gp/product/1573226882/ref=as_li_tl?ie=UTF8&camp=1789&creative=390957&creativeASIN=1573226882&linkCode=as2&tag=jokecamp-20&linkId=GBT7AHJS2EKA43NQ"><img border="0" src="http://ws-na.amazon-adsystem.com/widgets/q?_encoding=UTF8&ASIN=1573226882&Format=_SL110_&ID=AsinImage&MarketPlace=US&ServiceVersion=20070822&WS=1&tag=jokecamp-20" ></a><img src="http://ir-na.amazon-adsystem.com/e/ir?t=jokecamp-20&l=as2&o=1&a=1573226882" width="1" height="1" border="0" alt="" style="border:none !important; margin:0px !important;" />

<a href="http://www.amazon.com/gp/product/0060731427/ref=as_li_tl?ie=UTF8&camp=1789&creative=390957&creativeASIN=0060731427&linkCode=as2&tag=jokecamp-20&linkId=K7H4RML7XJGRT57R"><img border="0" src="http://ws-na.amazon-adsystem.com/widgets/q?_encoding=UTF8&ASIN=0060731427&Format=_SL110_&ID=AsinImage&MarketPlace=US&ServiceVersion=20070822&WS=1&tag=jokecamp-20" ></a><img src="http://ir-na.amazon-adsystem.com/e/ir?t=jokecamp-20&l=as2&o=1&a=0060731427" width="1" height="1" border="0" alt="" style="border:none !important; margin:0px !important;" />

<a href="http://www.amazon.com/gp/product/1568584253/ref=as_li_tl?ie=UTF8&camp=1789&creative=390957&creativeASIN=1568584253&linkCode=as2&tag=jokecamp-20&linkId=R5IWBX6BBE5WCZ73"><img border="0" src="http://ws-na.amazon-adsystem.com/widgets/q?_encoding=UTF8&ASIN=1568584253&Format=_SL110_&ID=AsinImage&MarketPlace=US&ServiceVersion=20070822&WS=1&tag=jokecamp-20" ></a><img src="http://ir-na.amazon-adsystem.com/e/ir?t=jokecamp-20&l=as2&o=1&a=1568584253" width="1" height="1" border="0" alt="" style="border:none !important; margin:0px !important;" />


</div>
