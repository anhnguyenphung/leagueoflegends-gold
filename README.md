# League of Legends: An Analysis of Average Gold per Game of a Random Champion.

![league-of-legends-photo](https://github.com/anhnguyenphung/leagueoflegends-gold/blob/master/leagueoflegends-gold-photos/league-of-legends.jpg)

---

## Introduction

League of Legends has been my favorite computer game since I was in high school. For my first machine learning project, I decided to look into the average amount of gold gained per game by a random champion out of 147 champions in League of Legends based on various aspects: Win Rate, Numbers of Games Played by that Champion, KD/A (Kill + Death / Assist), CS (Creep Score).

For this project, I want to practice multiple linear regression, a basic machine learning model, using backward elimination. To apply backward elimination efficiently, I utilized P-value and Adjusted R-Squared value to evaluate my independent variable.

## Skills gained through the project
* Applying Multiple Linear Regression.
* Using Backward Elimination in Machine Learning Model.
* Understanding the importance of P-value and Adjusted R-Squared value.
* Practing Python in machine learning through Jupyter Notebook.

## Obtaining the data

I went to OP.GG, a website about League of Legends statistics and obtained all of the informations of the champions in North America server in Patch 9.24.

![data-example](https://github.com/anhnguyenphung/leagueoflegends-gold/blob/master/leagueoflegends-gold-photos/gold-lol-example.png) 

## Importing the dataset

After manually converting the data from OP.GG into the csv file, I load the data from the csv file:

```python
dataset = pd.read_csv("D:\MLprojects\leagueoflegends-gold\champions.csv")
dataset.head(10)
```

|     | Champion | Win Rate | Games Played | KD/A | CS | Gold
| --- | --------- | -------- | ------------ | ---- | -- | ----
| **0** |	Aatrox	| 45.86 |	164593 | 1.84 |	150.57 |	10395
| **1** |	Ahri |	51.23 |	198894 |	2.60 |	142.14 |	10533
| **2** |	Akali |	45.90 |	327924 |	2.12 | 	149.43 |	10810
| **3**	| Alistar |	47.76 |	75860 |	2.32 |	33.28 |	7597
| **4** |	Amumu |	51.37 |	123849 |	2.35 |	140.60 |	10266
| **5**	| Anivia |	50.60 |	66575 |	2.72 | 154.30 |	10720
| **6**	| Annie |	50.31 |	95085 |	2.27 |	126.40 |	10477
| **7**	| Aphelios |	49.17 |	269810 |	2.10 |	162.22 |	11565
| **8**	| Ashe |	51.88 |	430795 |	2.51 |	150.15 |	11165
| **9**	| AurelianSol |	52.08 |	31909 |	2.52 |	147.51 |	10487

```python
dataset.tail(10)
```

|     | Champion | Win Rate | Games Played | KD/A | CS | Gold
| --- | --------- | -------- | ------------ | ---- | -- | ----
| **137** |	XinZhao |	49.93 |	109917 |	2.00 |	137.88 |	10664
| **138**	| Yasuo	| 50.48	| 540594| 1.85	| 181.41 |	11907
| **139**	| Yorick |	53.30 |	91380 |	1.93 |	179.22 |	11431
| **140**	| Yuumi |	43.77 |	105677 |	3.97 |	8.13 |	7453
| **141**	| Zac |	51.94 |	102287 |	3.22 |	125.50 |	9806
| **142**	| Zed	| 48.85 |	251931 |	2.21 |	153.53 |	11690
| **143**	| Ziggs |	49.89	| 58872 |	2.39 |	151.20 | 10814
| **144**	| Zilean	| 51.84	| 81726	| 2.90	| 64.34 |	8746
| **145**	| Zoe |	47.67 |	83066 |	2.38 |	128.90 |	10254
| **146** |	Zyra |	51.92 |	143841 |	2.34 |	54.18 |	9305

## Fitting the dataset into Multiple Linear Regression model
After loading the dataset, I started to fit the dataset into my Multiple Linear Regression model following step by step. More details can be found in my [Jupyter Notebook file](https://github.com/anhnguyenphung/leagueoflegends-gold/blob/master/multiple_linear_regression.ipynb).
