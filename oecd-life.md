

# Data Import
Data were downloaded from http://www.oecdbetterlifeindex.org/
Speicifically I downloaded the version of [the datafile from 2012 06 V3](http://www.oecdbetterlifeindex.org/wpsystem/wp-content/uploads/2012/06/online_data_file_V3.xlsx)

I've put a dput copy of the data to make the file self-contained.


```r
# oecd <- read.delim('oecd-life.csv', as.is=TRUE)
# dput(oecd)
oecd <- structure(list(COUNTRY = c("Australia", "Austria", "Belgium", 
"Brazil", "Canada", "Chile", "Czech Republic", "Denmark", "Estonia", 
"Finland", "France", "Germany", "Greece", "Hungary", "Iceland", 
"Ireland", "Israel", "Italy", "Japan", "Korea", "Luxembourg", 
"Mexico", "Netherlands", "New Zealand", "Norway", "Poland", "Portugal", 
"Russian Federation", "Slovak Republic", "Slovenia", "Spain", 
"Sweden", "Switzerland", "Turkey", "United Kingdom", "United States", 
"OECD average"), Households.income = c("26927 USD", "27541 USD", 
"26734 USD", "", "27138 USD", "8618 USD", "16614 USD", "23213 USD", 
"13149 USD", "24958 USD", "27789 USD", "27692 USD", "22134 USD", 
"13696 USD", "", "24156 USD", "", "23917 USD", "23458 USD", "16570 USD", 
"35321 USD", "11106 USD", "25740 USD", "18601 USD", "30465 USD", 
"14508 USD", "18689 USD", "13911 USD", "15840 USD", "19334 USD", 
"23541 USD", "26633 USD", "27756 USD", "", "26552 USD", "37708 USD", 
"22387 USD"), Household.financial.wealth = c("29630 USD", "45468 USD", 
"69466 USD", "", "60344 USD", "15355 USD", "13681 USD", "31025 USD", 
"11231 USD", "19751 USD", "44353 USD", "41695 USD", "17638 USD", 
"11812 USD", "", "21485 USD", "47750 USD", "54706 USD", "71717 USD", 
"23715 USD", "72644 USD", "11728 USD", "61157 USD", "", "6197 USD", 
"8101 USD", "27299 USD", "", "2189 USD", "19852 USD", "22684 USD", 
"38616 USD", "95407 USD", "", "59923 USD", "102075 USD", "36238 USD"
), Employment.rate = c("72%", "72%", "62%", "68%", "72%", "59%", 
"65%", "73%", "61%", "68%", "64%", "71%", "60%", "55%", "79%", 
"60%", "60%", "57%", "70%", "63%", "65%", "60%", "75%", "72%", 
"75%", "59%", "66%", "67%", "59%", "66%", "59%", "73%", "79%", 
"46%", "70%", "67%", "66%"), Personal.earnings = c("42550 USD", 
"41904 USD", "42811 USD", "", "41961 USD", "11299 USD", "20424 USD", 
"42904 USD", "17145 USD", "35319 USD", "37229 USD", "38251 USD", 
"28200 USD", "18667 USD", "47257 USD", "48217 USD", "31155 USD", 
"32404 USD", "33900 USD", "31733 USD", "52110 USD", "11020 USD", 
"45671 USD", "31878 USD", "44164 USD", "18172 USD", "21722 USD", 
"", "18719 USD", "32308 USD", "32454 USD", "36766 USD", "49810 USD", 
"22397 USD", "44008 USD", "52607 USD", "34033 USD"), Job.security = c("11.70%", 
"8.80%", "6.46%", "14.03%", "11.26%", "", "6.36%", "12.36%", 
"9.63%", "13.42%", "9.02%", "7.79%", "5.74%", "7.72%", "12.73%", 
"7.13%", "", "6.55%", "10.23%", "25.80%", "5.56%", "18.02%", 
"5.18%", "", "7.72%", "9.07%", "7.35%", "", "6.14%", "6.85%", 
"10.77%", "13.17%", "8.30%", "22.67%", "6.89%", "11.38%", "10.07%"
), Long.term.unemployment.rate = c("0.97%", "1.11%", "4.04%", 
"", "0.96%", "", "3.16%", "1.42%", "7.63%", "1.98%", "3.74%", 
"3.34%", "5.64%", "5.64%", "1.61%", "6.69%", "1.48%", "4.08%", 
"1.88%", "0.01%", "1.28%", "0.13%", "1.23%", "0.59%", "0.34%", 
"2.46%", "5.64%", "2.23%", "8.52%", "3.13%", "9.04%", "1.39%", 
"1.46%", "3.40%", "2.53%", "2.79%", "3.04%"), Rooms.per.person = c("", 
"1.7 rooms", "2.1 rooms", "", "", "1.3 rooms", "1.4 rooms", "1.9 rooms", 
"1.2 rooms", "1.9 rooms", "1.8 rooms", "1.8 rooms", "1.2 rooms", 
"1 rooms", "1.6 rooms", "2.1 rooms", "1.2 rooms", "1.4 rooms", 
"1.8 rooms", "1.4 rooms", "1.9 rooms", "1 rooms", "2 rooms", 
"", "2 rooms", "1 rooms", "1.4 rooms", "", "1.1 rooms", "1.1 rooms", 
"1.9 rooms", "1.8 rooms", "1.8 rooms", "0.9 rooms", "1.8 rooms", 
"", "1.6 rooms"), Housing.expenditure = c("21%", "22%", "20%", 
"", "23%", "21%", "26%", "26%", "21%", "23%", "21%", "22%", "28%", 
"23%", "", "18%", "", "23%", "23%", "16%", "25%", "19%", "22%", 
"29%", "19%", "24%", "18%", "11%", "26%", "20%", "20%", "22%", 
"24%", "", "23%", "20%", "22%"), Dwellings.with.basic.facilities = c("", 
"98.80%", "99.70%", "93.33%", "99.81%", "90.64%", "99.30%", "100%", 
"88.90%", "99.30%", "99.30%", "98.40%", "98.60%", "93.40%", "99.60%", 
"99.80%", "", "99.80%", "93.60%", "95.84%", "99.50%", "95.81%", 
"100%", "", "99.90%", "95.90%", "98.40%", "", "98.80%", "99.60%", 
"100%", "100%", "99.90%", "87.33%", "99.50%", "100%", "97.75%"
), Employees.working.very.long.hours = c("13.99%", "9.02%", "4.45%", 
"12.50%", "3.91%", "7.15%", "8.75%", "1.92%", "3.55%", "3.66%", 
"8.63%", "5.14%", "5.20%", "3.33%", "", "3.72%", "18.92%", "4.62%", 
"", "", "3.71%", "28.90%", "0.68%", "13.28%", "2.66%", "7.35%", 
"5.36%", "0.17%", "5.82%", "6.08%", "6.66%", "1.28%", "5.87%", 
"43%", "11.71%", "10.86%", "9.47%"), Time.devoted.to.leisure.and.personal.care = c("14.41 hours", 
"14.46 hours", "15.71 hours", "", "14.25 hours", "", "14.34 hours", 
"16.06 hours", "14.2 hours", "14.89 hours", "15.33 hours", "15.31 hours", 
"", "", "", "", "", "14.89 hours", "13.96 hours", "14.63 hours", 
"", "", "", "14.87 hours", "15.56 hours", "14.2 hours", "", "", 
"", "14.62 hours", "15.85 hours", "15.11 hours", "", "", "14.83 hours", 
"14.27 hours", "14.76 hours"), Life.expectancy = c("81.8 years", 
"80.7 years", "80.3 years", "73.2 years", "80.8 years", "79 years", 
"77.7 years", "79.3 years", "75.6 years", "80.2 years", "81.4 years", 
"80.5 years", "80.6 years", "74.3 years", "81.5 years", "81 years", 
"81.7 years", "82 years", "83 years", "80.7 years", "80.7 years", 
"75.5 years", "80.8 years", "81 years", "81.2 years", "76.3 years", 
"79.8 years", "69 years", "75.2 years", "79.5 years", "82.2 years", 
"81.5 years", "82.6 years", "74.3 years", "80.4 years", "78.7 years", 
"79.8 years"), Self.reported.health = c("85%", "69%", "77%", 
"", "88%", "59%", "68%", "71%", "55%", "68%", "68%", "65%", "76%", 
"54%", "78%", "83%", "81%", "67%", "30%", "38%", "75%", "66%", 
"77%", "90%", "80%", "58%", "49%", "", "63%", "59%", "74%", "79%", 
"87%", "66%", "76%", "90%", "70%"), Educational.attainment = c("71%", 
"82%", "71%", "41%", "88%", "69%", "91%", "76%", "89%", "82%", 
"70%", "85%", "61%", "81%", "66%", "72%", "82%", "54%", "", "80%", 
"77%", "35%", "73%", "72%", "81%", "88%", "30%", "88%", "91%", 
"83%", "52%", "86%", "87%", "33%", "74%", "89%", "74%"), Years.in.education = c("18.4 years", 
"16.6 years", "18.7 years", "16.3 years", "17 years", "15.6 years", 
"17.6 years", "18.4 years", "17.5 years", "19.5 years", "16.5 years", 
"17.7 years", "18.1 years", "17.5 years", "18.9 years", "17.6 years", 
"15.5 years", "17 years", "", "17.2 years", "14.7 years", "14.6 years", 
"17.7 years", "18.6 years", "17.8 years", "18.1 years", "18.1 years", 
"16.6 years", "16.4 years", "18.3 years", "16.9 years", "18.9 years", 
"17 years", "14.2 years", "16.3 years", "16.9 years", "17.3 years"
), Students..skills = c("519 score", "487 score", "509 score", 
"401 score", "527 score", "439 score", "490 score", "499 score", 
"514 score", "543 score", "497 score", "510 score", "473 score", 
"496 score", "501 score", "497 score", "459 score", "486 score", 
"529 score", "541 score", "482 score", "420 score", "519 score", 
"524 score", "500 score", "501 score", "490 score", "469 score", 
"488 score", "499 score", "484 score", "496 score", "517 score", 
"455 score", "500 score", "496 score", "497 score"), Social.network = c("97%", 
"94%", "94%", "91%", "92%", "86%", "91%", "96%", "91%", "94%", 
"92%", "95%", "85%", "89%", "98%", "98%", "88%", "91%", "92%", 
"81%", "93%", "82%", "94%", "95%", "94%", "90%", "86%", "88%", 
"92%", "93%", "94%", "92%", "94%", "69%", "96%", "92%", "91%"
), Consultation.on.rule.making = c("10.5 index", "7.1 index", 
"4.5 index", "4 index", "10.5 index", "2 index", "6.8 index", 
"7 index", "3.3 index", "9 index", "3.5 index", "4.5 index", 
"6.5 index", "7.9 index", "5.1 index", "9 index", "2.5 index", 
"5 index", "7.3 index", "10.4 index", "6 index", "9 index", "6.1 index", 
"10.3 index", "8.1 index", "10.8 index", "6.5 index", "", "6.6 index", 
"10.3 index", "7.3 index", "10.9 index", "8.4 index", "5.5 index", 
"11.5 index", "8.3 index", "7.3 index"), Voter.turn.out = c("95%", 
"82%", "91%", "83%", "60%", "88%", "64%", "87%", "62%", "74%", 
"84%", "78%", "71%", "64%", "84%", "67%", "64%", "81%", "67%", 
"63%", "91%", "59%", "80%", "79%", "77%", "54%", "64%", "64%", 
"55%", "63%", "75%", "82%", "48%", "83%", "61%", "90%", "73%"
), Water.quality = c("92%", "94%", "84%", "84%", "90%", "85%", 
"87%", "96%", "70%", "94%", "80%", "96%", "61%", "78%", "97%", 
"89%", "59%", "80%", "88%", "82%", "92%", "71%", "95%", "88%", 
"95%", "77%", "88%", "51%", "85%", "88%", "81%", "97%", "97%", 
"65%", "97%", "86%", "85%"), Air.pollution = c("14 micrograms", 
"29 micrograms", "21 micrograms", "21 micrograms", "15 micrograms", 
"62 micrograms", "18 micrograms", "16 micrograms", "13 micrograms", 
"15 micrograms", "13 micrograms", "16 micrograms", "32 micrograms", 
"16 micrograms", "14 micrograms", "13 micrograms", "28 micrograms", 
"23 micrograms", "27 micrograms", "31 micrograms", "13 micrograms", 
"33 micrograms", "31 micrograms", "12 micrograms", "16 micrograms", 
"35 micrograms", "21 micrograms", "16 micrograms", "13 micrograms", 
"29 micrograms", "28 micrograms", "11 micrograms", "22 micrograms", 
"37 micrograms", "13 micrograms", "19 micrograms", "22 micrograms"
), Homicide.rate = c("1.2 homicides", "0.5 homicides", "1.7 homicides", 
"22.7 homicides", "1.8 homicides", "3.7 homicides", "0.9 homicides", 
"0.9 homicides", "5.2 homicides", "2.3 homicides", "1.3 homicides", 
"0.8 homicides", "1.1 homicides", "1.4 homicides", "0.3 homicides", 
"1.2 homicides", "2.1 homicides", "1 homicides", "0.5 homicides", 
"2.8 homicides", "2.5 homicides", "19 homicides", "1.1 homicides", 
"1.5 homicides", "0.6 homicides", "1.3 homicides", "1.2 homicides", 
"11.2 homicides", "1.6 homicides", "0.6 homicides", "0.9 homicides", 
"1 homicides", "0.7 homicides", "3.3 homicides", "1.2 homicides", 
"5 homicides", "2.1 homicides"), Assault.rate = c("2.10%", "2.98%", 
"6.67%", "9.38%", "1.31%", "9.33%", "2.96%", "3.93%", "5.52%", 
"2.36%", "4.95%", "3.60%", "3.70%", "3.59%", "2.69%", "2.63%", 
"6.54%", "4.70%", "1.37%", "2.09%", "4.29%", "10.98%", "4.88%", 
"2.23%", "3.25%", "1.81%", "5.81%", "2.83%", "2.97%", "3.91%", 
"4.18%", "5.13%", "4.20%", "5.09%", "1.93%", "1.50%", "3.98%"
), Life.Satisfaction = c("7.4 rate", "7.5 rate", "7 rate", "6.8 rate", 
"7.4 rate", "6.6 rate", "6.3 rate", "7.8 rate", "5.5 rate", "7.4 rate", 
"7 rate", "6.7 rate", "5.4 rate", "4.9 rate", "6.9 rate", "6.9 rate", 
"7.4 rate", "6.1 rate", "6.1 rate", "6.9 rate", "7 rate", "6.9 rate", 
"7.5 rate", "7.2 rate", "7.6 rate", "5.6 rate", "5.2 rate", "5.3 rate", 
"5.9 rate", "6 rate", "6.5 rate", "7.3 rate", "7.5 rate", "5.3 rate", 
"6.9 rate", "7.1 rate", "6.7 rate")), .Names = c("COUNTRY", "Households.income", 
"Household.financial.wealth", "Employment.rate", "Personal.earnings", 
"Job.security", "Long.term.unemployment.rate", "Rooms.per.person", 
"Housing.expenditure", "Dwellings.with.basic.facilities", "Employees.working.very.long.hours", 
"Time.devoted.to.leisure.and.personal.care", "Life.expectancy", 
"Self.reported.health", "Educational.attainment", "Years.in.education", 
"Students..skills", "Social.network", "Consultation.on.rule.making", 
"Voter.turn.out", "Water.quality", "Air.pollution", "Homicide.rate", 
"Assault.rate", "Life.Satisfaction"), class = "data.frame", row.names = c(NA, 
-37L))
```




# Data Cleaning


```r
oecd$Households.income <- as.numeric(gsub(" USD", "", oecd$Households.income))
oecd$Household.financial.wealth <- as.numeric(gsub(" USD", "", oecd$Household.financial.wealth))
oecd$Employment.rate <- as.numeric(gsub('%', '', oecd$Employment.rate)) / 100
oecd$Personal.earnings <- as.numeric(gsub(" USD", "", oecd$Personal.earnings))
oecd$Job.security <- as.numeric(gsub('%', '', oecd$Job.security)) / 100
oecd$Long.term.unemployment.rate <- as.numeric(gsub('%', '', oecd$Long.term.unemployment.rate)) / 100
oecd$Rooms.per.person <- as.numeric(gsub(" rooms", "", oecd$Rooms.per.person))
oecd$Housing.expenditure <- as.numeric(gsub('%', '', oecd$Housing.expenditure)) / 100
oecd$Dwellings.with.basic.facilities <- as.numeric(gsub('%', '', oecd$Dwellings.with.basic.facilities)) / 100
oecd$Employees.working.very.long.hours <- as.numeric(gsub('%', '', oecd$Employees.working.very.long.hours)) / 100
oecd$Time.devoted.to.leisure.and.personal.care <- as.numeric(gsub(" hours", "", oecd$Time.devoted.to.leisure.and.personal.care))
oecd$Life.expectancy <- as.numeric(gsub(" years", "", oecd$Life.expectancy))
oecd$Self.reported.health <- as.numeric(gsub('%', '', oecd$Self.reported.health)) / 100
oecd$Educational.attainment <- as.numeric(gsub('%', '', oecd$Educational.attainment)) / 100
oecd$Years.in.education <- as.numeric(gsub(" years", "", oecd$Years.in.education))
oecd$Students..skills <- as.numeric(gsub(" score", "", oecd$Students..skills))
oecd$Social.network <- as.numeric(gsub("%", "", oecd$Social.network)) / 100
oecd$Consultation.on.rule.making <- as.numeric(gsub(" index", "", oecd$Years.in.education))
oecd$Voter.turn.out <- as.numeric(gsub("%", "", oecd$Voter.turn.out)) / 100
oecd$Water.quality <- as.numeric(gsub("%", "", oecd$Water.quality)) / 100
oecd$Air.pollution <- as.numeric(gsub(" micrograms", "", oecd$Air.pollution))
oecd$Homicide.rate <- as.numeric(gsub(" homicides", "", oecd$Homicide.rate))
oecd$Assault.rate <- as.numeric(gsub("%", "", oecd$Assault.rate)) / 100
oecd$Life.Satisfaction <- as.numeric(gsub(" rate", "", oecd$Life.Satisfaction))

oecd <- oecd[oecd$COUNTRY != "OECD average", ]
```




# Details of study
The anlaysis included data on up to `36` countries. The following lists the countries.



```r
oecd$COUNTRY
```



```
##  [1] "Australia"          "Austria"            "Belgium"           
##  [4] "Brazil"             "Canada"             "Chile"             
##  [7] "Czech Republic"     "Denmark"            "Estonia"           
## [10] "Finland"            "France"             "Germany"           
## [13] "Greece"             "Hungary"            "Iceland"           
## [16] "Ireland"            "Israel"             "Italy"             
## [19] "Japan"              "Korea"              "Luxembourg"        
## [22] "Mexico"             "Netherlands"        "New Zealand"       
## [25] "Norway"             "Poland"             "Portugal"          
## [28] "Russian Federation" "Slovak Republic"    "Slovenia"          
## [31] "Spain"              "Sweden"             "Switzerland"       
## [34] "Turkey"             "United Kingdom"     "United States"     
```






# Correlation between life satisfaction an other measures


```r

other_variables <- names(oecd)[!names(oecd) %in% c("COUNTRY", "Life.Satisfaction")]
lifesat_correlations <- cor(oecd$Life.Satisfaction, oecd[, other_variables], 
    use = "pair")[1, ]
lifesat_correlations <- data.frame(r = round(lifesat_correlations, 
    2))
lifesat_correlations$n <- sapply(oecd[, other_variables], function(X) sum(!is.na(X)))
lifesat_correlations$abs_r <- abs(lifesat_correlations$r)
lifesat_correlations[order(lifesat_correlations$abs_r, decreasing = TRUE), 
    c("r", "n")]
```



```
##                                               r  n
## Rooms.per.person                           0.70 30
## Personal.earnings                          0.67 34
## Employment.rate                            0.63 36
## Households.income                          0.59 32
## Water.quality                              0.59 36
## Long.term.unemployment.rate               -0.58 34
## Self.reported.health                       0.58 34
## Life.expectancy                            0.57 36
## Dwellings.with.basic.facilities            0.54 32
## Social.network                             0.50 36
## Time.devoted.to.leisure.and.personal.care  0.43 21
## Household.financial.wealth                 0.41 31
## Voter.turn.out                             0.36 36
## Educational.attainment                     0.22 35
## Students..skills                           0.21 36
## Air.pollution                             -0.18 36
## Housing.expenditure                        0.12 32
## Years.in.education                         0.12 35
## Consultation.on.rule.making                0.12 35
## Employees.working.very.long.hours         -0.09 33
## Job.security                               0.08 32
## Homicide.rate                             -0.07 36
## Assault.rate                              -0.02 36
```




* `r` shows the correlation between the variable and life satisfaction
* `n` shows the number of countries supplying data for that variable. All countries supplied data for life satisfaction.


Note that this is just a draft set of preliminary analyses, and I haven't thoroughly checked everything; I'll probably post a little more on this example at some point on http://jeromyanglim.blogspot.com
