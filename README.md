## Business understanding

Project Title: ThronesMining
Team Members: Maksym Yerokhin and Roman Ismagilov

### Identifying your business goals
#### Background
Considering the popular TV series "Game of Thrones" people wonder what events 
(and especially deaths) shall happen next. Each season one of the houses (e.g. Lannisters or Starks) can dominate over another, so there comes other common questions - whose role is to be a victim and whose is going to be a winner in upcoming battles.

#### Business goals
ThronesMining can provide analysis of previous seasons’ events that can be used in different fields, e.g. in betting. Specifically, our model should be able to answer the following questions:
what is needed to fulfill the successfull attack;
how much is likely for different kinds of characters to die;
what are the bonds between houses, how much they are reliable, what are potential alliances.

#### Business success criteria
The main success criterion is model usage after first series of the new season passed, if the analysis is useful and correct enough then people’s interest will remain at the high level.

#### Assessing your situation
Inventory of resources   
We are provided with 3 datasets: battles, characters and character deaths up to season 5. Datasets are taken from the kaggle competition. (https://www.kaggle.com/mylesoneill/game-of-thrones/data)

#### Requirements, assumptions and constraints
Our requirements are to build a working model that can satisfy business goals and complete it before the deadline. We assume that provided datasets are sufficient and consist of all needed data without gaps.

#### Risks and contingencies
Since provided datasets contain only battles and deaths, we can encounter the underfitting issue, so at some step we might need to extend datasets. This can take additional time.

#### Terminology
- House - family, clan, group of people under the same banner.
- Title - formal rank of person.
- Culture - group of nationality of the person.

#### Costs and benefits
If it was a real project developing for the sake of specific customer it would take 2 weeks, 2 developers, 1 field expert and $3000 to implement the solution. The potential benefits are obviously trading and exploiting the predictions, including making (or even organizing) bets on some betting platforms and receiving profit from this.
But even if model is not so precise, it will still be able to attract folks’ attention.

#### Defining your data-mining goals
Data-mining goals
Clear and update data rows by similar records, details of which are unnecessary for model, e.g. different kinds of “lords”;
Create infographics for intuitively comprehensive visualization of houses relations and living characters death probabilities;
Find is there any “support” and how much of certain characters from author or scenarists (e.g. characters should have die long time ago but he is still alive);
Perform hierarchical clusterization for houses, explore relationships and potential alliances.

Data-mining success criteria
Since our dataset does not cover all of the present seasons, we can check our predictions for 5th season and try to reach at least 85% accuracy in predictions.



## Data understanding
#### Data gathering
For this kind of research one will need data containing all the characters and all the major information structured. There are 3 CSV data files on the Kaggle competition. Although this data is a bit outdated: it was released in 2015, but there were two new seasons up to 2017, so we will manually add some data to files. Even if it is outdated it still fulfils the requirements for the research. 
#### Describing data
There are 3 files: battle.csv which contains info about all the battles present by the dataset release date. There is information about fighting sides, year, commanders names, location, results and some other data. 
In the character-deaths.csv contains information about dead characters and their deaths: chapter, year, gender, nobility of character. 
The most interesting file is character-predictions.csv. It has information about all characters appeared in the saga: their names, house, title, gender, family status, popularity, etc. Also, author of dataset tried to do death prediction and he included corresponding column, which is completely outdated and useless, due to new seasons release.
#### Exploring data
File character-deaths.csv seems to be not very useful because it is based on books, and now TV show is going it’s own way due to delay in book composing. In order to have precise research we need to clear data: remove values making no sense, find and correct typos, if there are some, and report count of affecting rows.
#### Verifying data quality
We performed brief analysis of the datasets in R. In the “title” column there are 263 levels while we only have 1946 characters, so this column won’t make a lot of sense. To fix this it is possible to merge some titles, for example there are various “Lords” which could be unite into one level “Lord”.
Also, in “spouse“ column there is one strange value “unknown2nd: unknown3rd: unknown” which should be replaced with NA. In addition, there are a lot of noncompliance in “culture” column. For example, there are values “Andal” and “Andals”, “free folk”, “Free folk”, “Free Folk”, etc, which definitely should be unite. Despite those minor problems, the dataset is good enough to do the research.


## Exercise 3. Planning the project
GitHub repository link: https://github.com/Pomis/ThronesMining
Link to the slide: https://docs.google.com/presentation/d/1veA_WQcfRRx7hQnE8qklmsLYceWzQGrPHrieSEWqcaI/edit#slide=id.g2a57963548_75_0

#### Tasks to accomplish:
- Clear and update the dataset grouping by similar records, details of which are unnecessary for model, e.g. different kinds of “lords”; 3h
- Create infographics for intuitively comprehensive visualization of houses relations and living characters death probabilities. This should include histogrammes, heatmaps and graphs; 8h     
- Perform clusterization, find out fun and surprising facts that can reveal some important conditions for dominating one house over another; 30h     
- Find is there any “support” and how much of certain characters from author or scenarists (e.g. characters should have die long time ago but he is still alive). 4h    
- Extend datasets if necessary with events from seasons 5-7. 5h    

