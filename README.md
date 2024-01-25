# *Up Up and Away! Fortune Inc Makes it's Way into the Sky*
### Elina Rankova

<p align="center">
  <img src = "https://github.com/erankova/Phase-1-Project/blob/main/Images/Airplane1.jpg" width="720" height="450">
</p> 

## The Business Problem

**Stakeholders:** CEO, Head of Operations, Head of Aviation (brand new department)

Fortune Inc. is expanding into airplane aviation to diversify its portfolio. In Phase 1 of department development, we aim to evaluate which aircrafts and aircraft specifics pose the lowest risk as we venture into a brand new industry. Being so to the industry, we want to focus on identifying the industry standard for aircraft make and model, and which top make and model results in least number of *destroyed* aircrafts during accident events to account for easier financial maintainance. We also want to focus on which type of engine is the industry standard for identified make and model and corresponds to the least number of fatal injuries.

**Some preliminary questions include:**

- *What type of aircraft make and model the most sense to purchase first when considering industry standard and which engine types are associated with identified make and model?*
- *How is type of engine related to total injuries during accident events as related to identified industry standard make and model?*
- *Have there been improvements in aviation technology and regulation helping us determine which event years provide relevant data?*

**The goal: evaluate which type of airplane and engine type pose least risk, as defined above, to purchase and as we enter an industry we have not explored before. As an aside, we aim to evaluate how weather conditions correlate to injury severity for potential training considerations in Phase 2.**

## The Dataset
For analysis, we are using data from the <a href = "https://www.kaggle.com/datasets/khsamaha/aviation-accident-database-synopses">Aviation Accident Database & Synopses</a>, up to 2023.

Each record represents an accident event and includes much information about aircraft specifics as well as passenger injury details and information about accident events. 

For additional information about; aircraft regulation history and which event years provide most valid data, most commonly used aircaft, and details about the different weather conditions possible, the following resources were used:

- <a href = "https://www.faa.gov/about/history/brief_history">Brief History of Aviation Regulations</a>
- <a href = "https://www.cnn.com/travel/article/world-best-selling-airplanes/index.html">Best Selling Airplain</a>
- <a href = https://en.wikipedia.org/wiki/Visual_meteorological_conditions>VMC/IMC Wikipedia</a>

Handling the missingness will be a large part of data cleaning for this dataset.

## Data Evaluation & Visualization

Tableau Dashboard Preview
- <a href = "https://public.tableau.com/app/profile/elina.rankova/viz/FortuneInc_AviationAnalysis/Dashboard1?publish=yes">Link to Tableau Dashboard</a>

<p align="center">
  <img src = "https://github.com/erankova/Fortune-Inc-Aviation-Analysis/blob/main/Images/Dashboard.png" width="1145" height="847">
</p> 


We are using event data starting 1992 because in 1982 and 1991 there were major changes in technological inovations and aviation regulations. So we want data starting 1992 and on for `Event.Year`.

**Source:** <a href = "https://www.faa.gov/about/history/brief_history">Brief History of Aviation Regulations</a>

<p align="center">
  <img src = "https://github.com/erankova/Fortune-Inc-Aviation-Analysis/blob/main/Images/Most%20Used%20Make.png" width="654" height="608">
</p> 

**Most Used Airplane `Make`**: If we view this data numerically, we can see that ~43% of aircrafts being used are of Cessna make. This aligns with the information provided by CNN about best selling airplanes.

**Source:** <a href = "https://www.cnn.com/travel/article/world-best-selling-airplanes/index.html">Best Selling Airplain</a>

<p align="center">
  <img src = "https://github.com/erankova/Phase-1-Project/blob/main/Images/Make%20vs%20Aircraft%20Damage.png" width="856" height="588">
</p> 

**Top `Make` Compared with `Aircraft.damage`**: When comparing `Make` with `Aircraft.damage` we can see that because Cessna is still by far the most popular, it also records the most substantial damage to the air craft. However, at this point, it does not *seem* have significanly more cases of destroyed aircrafts than lesser used makes.

Again, we see that beyond the top 4 makes, the analysis becomes insignificant.

<p align="center">
  <img src = "https://github.com/erankova/Phase-1-Project/blob/main/Images/Perc%20Damage%20vs%20Make.png" width="1207" height="777">
</p> 

Finally we want to compare `Make` and `Aircraft.damage` on a percentage scale to be certain which make poses least risk to the aircraft during an accident. We can see that though it looked like Piper might have a lesser percentage of destroyed aircrafts, in fact, it is Cessna that poses least risk.

<p align="center">
  <img src = "https://github.com/erankova/Fortune-Inc-Aviation-Analysis/blob/main/Images/Perc%20Damage%20vs%20Make.png" width="1028" height="632">
</p> 

If we look at the data numerically below, we can see that ~20% of Cessna accidents destroy the aircraft while Piper, the second most used make, has ~24% of accidents resulting in a destroyed aircraft.

**Most Used Cessna Model**

<p align="center">
  <img src = "https://github.com/erankova/Fortune-Inc-Aviation-Analysis/blob/main/Images/Most%20Used%20Cessna%20Models.png" width="651" height="532">
</p>

We can see that within the Cessna make, the 152 model used most often and that the difference between these models decreases after the top 4.

<p align="right">
  <img src = "https://github.com/erankova/Phase-1-Project/blob/main/Images/Prec%20Damage%20vs%20Model.png" width="1191" height="673"
</p>

Now we can compare the top 4 `Model` types with `Aircraft.damage`. Though slight, we can clearly see the Cessna 172 model recorded the least number of damaged airplanes.

<p align="center">
  <img src = "https://github.com/erankova/Phase-1-Project/blob/main/Images/Damage%20vs%20Model%20Table.png" width="408" height="197"
</p>

If we look at the data numerically below, we can see that ~12% of the Cessna 172 model destroyed the aircraft, which is less than any of the top 4 Cessna models used.

**`Engine.Type` to `Total.Injuries` for Cessna `Make`**

<p align="center">
  <img src = "https://github.com/erankova/Phase-1-Project/blob/main/Images/Engine%20Type%20vs%20Injuries.png" width="986" height="751"
</p>

As we can see, the Reciprocating engine yields the least injuries for Cessna planes.

<p align="center">
  <img src = "https://github.com/erankova/Fortune-Inc-Aviation-Analysis/blob/main/Images/Engine%20Type%20vs%20Injuries%20Table.png" width="594" height="272"
</p>

We can see that numerically, the Reciprocating engine yields percentages in the 90's for lower total injury counts (0-6).

<p align="center">
  <img src = "https://github.com/erankova/Fortune-Inc-Aviation-Analysis/blob/main/Images/Engine%20vs%20Avg%20Injuries.png" width="668" height="456"
</p>

We can see in our tableau visualization using average injury counts, the Reciprocating engine is the best pick for Cessna make.

## `Weather.Condition` vs `Injury Severity`

<p align="center">
  <img src = "https://github.com/erankova/Fortune-Inc-Aviation-Analysis/blob/main/Images/Weather%20Conditions%20vs%20Injury%20Severity.png" width="565" height="125"
</p>

When we observe `Injury.Severity` by `Weather.Condition` we can see that most fatal injuries occur during IMC at ~60% of accident instances being fatal vs ~14% in VMC.

**Definition:** Visual meteorological conditions (VMC) is an aviation flight category 
in which visual flight rules (VFR) flight is permitted—that is, conditions in which 
pilots have sufficient visibility to fly the aircraft maintaining visual separation 
from terrain and other aircraft. 

In aviation, instrument meteorological conditions (IMC) are weather conditions that 
require pilots to fly primarily by reference to flight instruments. Typically, this 
means flying in cloud or poor weather, where little or nothing can be seen or recognised 
when looking out of the window. 

**Source:** <a href = https://en.wikipedia.org/wiki/Visual_meteorological_conditions>VMC/IMC Wikipedia</a>

## Recommendations & Conclusion

**Data Limitation**

There was some missingness which could not be accounted for and therefore, columns had to be dropped. There are also potential duplicates as `Event.Id` and `Accident.Number` have duplicate values but display slighly different records with some shared information. There were also columns such as `Aircraft.carrier` that may be useful to analyse but had too much mixed data to be able to adequately organize. There is a lack of understanding whether these are supposed to be unique identifiers and it is recommended to obtain additional data for any additional phases of department expansion. 

**Data Limitation**

There was some missingness which could not be accounted for and therefore, columns had to be dropped. There are also potential duplicates as `Event.Id` and `Accident.Number` have duplicate values but display slighly different records with some shared information. There is a lack of understanding whether these are supposed to be unique identifiers and it is recommended to obtain additional data for any additional phases of department expansion. There were also columns such as `Aircraft.carrier` that may be useful to analyse but had too much mixed data to be able to adequately organize. 


**Recommendations**

*`Make`:* Cessna <br>
Cessna airplanes are most widely used and have destroyed the least percentage of aircrafts within the accident report, when compared with top 4 most used makes. 

*`Model`:* Cessna 172 <br>
The Cessna 172 model has shown that only 12% of accidents result in a destroyed airplane, this is less `Aircraft.damage` than caused by any of the other top 4 Cessna models. 

*`Engine.Type`:* Reciprocating <br>
Reciprocating engine yields percentages in the 90's for lower `Total.Injuries` counts (0-6), making it the safest engine a Cessna airplane can have, among widely used engines in the industry.

*Safety Training:* Thorough safety training <br>
Extra attention to training in IMC during which, pilots are primariy flying by reference to flight instruments. The percent of fatal `Injury.Severity` is highest at ~60% vs ~14% in VMC.

**Conclusion** <br>

For <u>*Phase 1*</u> of Aviation Department expansion we suggest starting small with Cessna 172 as it poses least risk overall to passengers and business development. As the industry standard, the Cessna make stands out. The 172 model, though 2nd most used, results in the least amount of destroyed aircrafts during accident events. The Reciprocating engine, being both industry standard and causing least amount of total injuries per accident event, is the clear winner among engine types and a great starter engine for our purposes.

For <u>*Phase 2*</u> we suggest addressing the *data limitations* to perform a more robust analysis regarding additional Aircrafts we want to invest in for Phase 2. In addition, we would want to take a closer look at locations that resulted in least amount of aircraft damage and total injuries. We will also want to decide whether we will be conducting our own pilot/crew training. Whether doing this inhouse or partnering with other companies, we would want to address the higher number of fatal injuries occuring during instrument meteorological conditions (IMC) as ~60% of accidents occuring during IMC resulted in fatal injuries.

## Repository Structure

```
├── Data
├── Images
├── .gitignore
├── Fortune Inc Makes it's Way into the Sky.pdf
├── Fortune Inc Aviation Analysis.ipynb
└── README.md
```
