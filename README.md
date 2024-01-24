# *Up Up and Away! Fortune Inc Makes it's Way into the Sky*
### Elina Rankova

<p align="center">
  <img src = "https://github.com/erankova/Phase-1-Project/blob/main/Images/Airplane1.jpg" width="650" height="350">
</p> 

## The Business Problem

**Stakeholders:** CEO, Head of Operations, Head of Aviation (brand new department)

Our company is expanding into airplane aviation to diversify its portfolio. We aim to evaluate which aircrafts and aircraft specifics pose the lowest risk as we venture into a brand new industry. 

**Some preliminary questions include:**

- *What type of aircraft makes the most sense to purchase first?*
- *Are there aircraft specifics such as number of engines, or engine type that contribute to risk?*
- *Are there special safety training conditions we should consider for training*
- *Have there been improvements in aviation technology and regulation helping us determine which data is valid*

**The goal: evaluate which type of airplane makes the most sense purchase as we enter an industry we have not explored before.**

We want to find out which statistics about aviation accident reports provide valuable information about which aircraft poses least risk.

## The Dataset
For analysis, we are using data from the <a href = "https://www.kaggle.com/datasets/khsamaha/aviation-accident-database-synopses">Aviation Accident Database & Synopses</a>, up to 2023.

Each record represents an accident event and includes much information about aircraft specifics as well as passenger injury details and information about accident events. 

For additional information about aircraft regulation history, most commonly used aircaft, details about the different weather conditions possible make the following resources were used:

- <a href = "https://www.faa.gov/about/history/brief_history">Brief History of Aviation Regulations</a>
- <a href = "https://www.cnn.com/travel/article/world-best-selling-airplanes/index.html">Best Selling Airplain</a>
- <a href = https://en.wikipedia.org/wiki/Visual_meteorological_conditions>VMC/IMC Wikipedia</a>

Handling the missingness will be a large part of data cleaning for this dataset.

## Data Evaluation & Visualization

<p align="center">
  <img src = "https://github.com/erankova/Phase-1-Project/blob/main/Images/Most%20Used%20Make.png" width="650" height="550">
</p> 

**Most Used Airplane `Make`**: If we view this data numerically, we can see that ~43% of aircrafts being used are of Cessna make. This aligns with the information provided by CNN about best selling airplanes.

<p align="center">
  <img src = "https://github.com/erankova/Phase-1-Project/blob/main/Images/Make%20vs%20Aircraft%20Damage.png" width="850" height="750">
</p> 

**Top `Make` Compared with `Aircraft.damage`**: When comparing `Make` with `Aircraft.damage` we can see that because Cessna is still by far the most popular, it also records the most substantial damage to the air craft. However, at this point, it does not *seem* have significanly more cases of destroyed aircrafts than lesser used makes.

Again, we see that beyond the top 4 makes, the analysis becomes insignificant.

<p align="center">
  <img src = "https://github.com/erankova/Phase-1-Project/blob/main/Images/Perc%20Damage%20vs%20Make.png" width="850" height="540">
</p> 

Finally we want to compare `Make` and `Aircraft.damage` on a percentage scale to be certain which make poses least risk to the aircraft during an accident. We can see that though it looked like Piper might have a lesser percentage of destroyed aircrafts, in fact, it is Cessna that poses least risk.

<p align="center">
  <img src = "https://github.com/erankova/Phase-1-Project/blob/main/Images/Damage%20vs%20Model%20Table.png" width="350" height="225">
</p> 

If we look at the data numerically below, we can see that ~20% of Cessna accidents destroy the aircraft while Piper, the second most used make, has ~24% of accidents resulting in a destroyed aircraft.

**Most Used Cessna Model**

<p align="center">
  <img src = "https://github.com/erankova/Phase-1-Project/blob/main/Images/Most%20Used%20Models.png" width="550" height="575">
</p>

We can see that within the Cessna make, the 152 model used most often and that the difference between these models decreases after the top 4.

<p align="right">
  <img src = "https://github.com/erankova/Phase-1-Project/blob/main/Images/Prec%20Damage%20vs%20Model.png" width="850" height="550"
</p>

Now we can compare the top 4 `Model` types with `Aircraft.damage`. Though slight, we can clearly see the Cessna 172 model recorded the least number of damaged airplanes.

<p align="center">
  <img src = "https://github.com/erankova/Phase-1-Project/blob/main/Images/Damage%20vs%20Model%20Table.png" width="550" height="200"
</p>

If we look at the data numerically below, we can see that ~12% of the Cessna 172 model destroyed the aircraft, which is less than any of the top 4 Cessna models used.

**`Engine.Type` to `Total.Injuries` for Cessna `Make`**

<p align="center">
  <img src = "https://github.com/erankova/Phase-1-Project/blob/main/Images/Engine%20Type%20vs%20Injuries.png" width="850" height="650"
</p>

As we can see, the Reciprocating engine yields the least injuries for Cessna planes.

<p align="center">
  <img src = "https://github.com/erankova/Phase-1-Project/blob/main/Images/Engine%20Type%20vs%20Injuries%20Table.png" width="566" height="133"
</p>

We can see that numerically, the Reciprocating engine yields percentages in the 90's for lower total injury counts (0-6).

## Conclusion & Recommendations

**Data Limitation**

There was some missingness which could not be accounted for and therefore, columns had to be dropped. There are also potential duplicates as `Event.Id` and `Accident.Number` have duplicate values but display slighly different records with some shared information. There were also columns such as `Aircraft.carrier` that may be useful to analyse but had too much mixed data to be able to adequately organize. There is a lack of understanding whether these are supposed to be unique identifiers and it is recommended to obtain additional data for any additional phases of department expansion. 

**Recommendations**

*`Make`:* Cessna
As Cessna airplanes are most widely used and have destroyed the least percentage of airplanes within the accident report.

*`Model`:* Cessna 172
Cessna 172 airplane has shown that only 12% of accidents result in a destroyed airplane, this is less `Aircraft.damage` than caused by any of the other top 4 Cessna models.

*`Engine.Type`:* Reciprocating
Reciprocating engine yields percentages in the 90's for lower `Total.Injuries` counts (0-6), making it the safest engine a Cessna airplane can have.

*Safety Training:* Thorough safety training
Extra attention to training in IMC during which, pilots are primariy flying by reference to flight instruments. The percent of fatal `Injury.Severity` is highest at ~60% vs ~14% in VMC.

## Repository Structure

```
├── Data
├── Images
├── .gitignore
├── Fortune Inc Makes it's Way into the Sky.pdf
├── Fortune Inc Aviation Analysis.ipynb
└── README.md
```
