
# Accessing Data within Pandas - Lab

## Introduction

In this lab, we'll look at a data set which contains information World cup matches. Let's use the pandas commands learned in the previous lecture to learn more about our data!

## Objectives
You will be able to:
* Understand and explain some key Pandas methods
* Access DataFrame data by using the label
* Perform boolean indexing on both Series and DataFrames
* Use simple selectors for series
* Set new Series and DataFrame inputs

## Load the data

Load the file `WorldCupMatches.csv` as a dataframe in Pandas


```python
import pandas as pd
df = pd.read_csv("./WorldCupMatches.csv")
```

## Common methods and attributes

Use the correct method to look at the first 7 rows of the data set.


```python
df.head(7)
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Year</th>
      <th>Datetime</th>
      <th>Stage</th>
      <th>Stadium</th>
      <th>City</th>
      <th>Home Team Name</th>
      <th>Home Team Goals</th>
      <th>Away Team Goals</th>
      <th>Away Team Name</th>
      <th>Win conditions</th>
      <th>Attendance</th>
      <th>Half-time Home Goals</th>
      <th>Half-time Away Goals</th>
      <th>Referee</th>
      <th>Assistant 1</th>
      <th>Assistant 2</th>
      <th>RoundID</th>
      <th>MatchID</th>
      <th>Home Team Initials</th>
      <th>Away Team Initials</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1930</td>
      <td>13 Jul 1930 - 15:00</td>
      <td>Group 1</td>
      <td>Pocitos</td>
      <td>Montevideo</td>
      <td>France</td>
      <td>4</td>
      <td>1</td>
      <td>Mexico</td>
      <td></td>
      <td>4444.0</td>
      <td>3</td>
      <td>0</td>
      <td>LOMBARDI Domingo (URU)</td>
      <td>CRISTOPHE Henry (BEL)</td>
      <td>REGO Gilberto (BRA)</td>
      <td>201</td>
      <td>1096</td>
      <td>FRA</td>
      <td>MEX</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1930</td>
      <td>13 Jul 1930 - 15:00</td>
      <td>Group 4</td>
      <td>Parque Central</td>
      <td>Montevideo</td>
      <td>USA</td>
      <td>3</td>
      <td>0</td>
      <td>Belgium</td>
      <td></td>
      <td>18346.0</td>
      <td>2</td>
      <td>0</td>
      <td>MACIAS Jose (ARG)</td>
      <td>MATEUCCI Francisco (URU)</td>
      <td>WARNKEN Alberto (CHI)</td>
      <td>201</td>
      <td>1090</td>
      <td>USA</td>
      <td>BEL</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1930</td>
      <td>14 Jul 1930 - 12:45</td>
      <td>Group 2</td>
      <td>Parque Central</td>
      <td>Montevideo</td>
      <td>Yugoslavia</td>
      <td>2</td>
      <td>1</td>
      <td>Brazil</td>
      <td></td>
      <td>24059.0</td>
      <td>2</td>
      <td>0</td>
      <td>TEJADA Anibal (URU)</td>
      <td>VALLARINO Ricardo (URU)</td>
      <td>BALWAY Thomas (FRA)</td>
      <td>201</td>
      <td>1093</td>
      <td>YUG</td>
      <td>BRA</td>
    </tr>
    <tr>
      <th>3</th>
      <td>1930</td>
      <td>14 Jul 1930 - 14:50</td>
      <td>Group 3</td>
      <td>Pocitos</td>
      <td>Montevideo</td>
      <td>Romania</td>
      <td>3</td>
      <td>1</td>
      <td>Peru</td>
      <td></td>
      <td>2549.0</td>
      <td>1</td>
      <td>0</td>
      <td>WARNKEN Alberto (CHI)</td>
      <td>LANGENUS Jean (BEL)</td>
      <td>MATEUCCI Francisco (URU)</td>
      <td>201</td>
      <td>1098</td>
      <td>ROU</td>
      <td>PER</td>
    </tr>
    <tr>
      <th>4</th>
      <td>1930</td>
      <td>15 Jul 1930 - 16:00</td>
      <td>Group 1</td>
      <td>Parque Central</td>
      <td>Montevideo</td>
      <td>Argentina</td>
      <td>1</td>
      <td>0</td>
      <td>France</td>
      <td></td>
      <td>23409.0</td>
      <td>0</td>
      <td>0</td>
      <td>REGO Gilberto (BRA)</td>
      <td>SAUCEDO Ulises (BOL)</td>
      <td>RADULESCU Constantin (ROU)</td>
      <td>201</td>
      <td>1085</td>
      <td>ARG</td>
      <td>FRA</td>
    </tr>
    <tr>
      <th>5</th>
      <td>1930</td>
      <td>16 Jul 1930 - 14:45</td>
      <td>Group 1</td>
      <td>Parque Central</td>
      <td>Montevideo</td>
      <td>Chile</td>
      <td>3</td>
      <td>0</td>
      <td>Mexico</td>
      <td></td>
      <td>9249.0</td>
      <td>1</td>
      <td>0</td>
      <td>CRISTOPHE Henry (BEL)</td>
      <td>APHESTEGUY Martin (URU)</td>
      <td>LANGENUS Jean (BEL)</td>
      <td>201</td>
      <td>1095</td>
      <td>CHI</td>
      <td>MEX</td>
    </tr>
    <tr>
      <th>6</th>
      <td>1930</td>
      <td>17 Jul 1930 - 12:45</td>
      <td>Group 2</td>
      <td>Parque Central</td>
      <td>Montevideo</td>
      <td>Yugoslavia</td>
      <td>4</td>
      <td>0</td>
      <td>Bolivia</td>
      <td></td>
      <td>18306.0</td>
      <td>0</td>
      <td>0</td>
      <td>MATEUCCI Francisco (URU)</td>
      <td>LOMBARDI Domingo (URU)</td>
      <td>WARNKEN Alberto (CHI)</td>
      <td>201</td>
      <td>1092</td>
      <td>YUG</td>
      <td>BOL</td>
    </tr>
  </tbody>
</table>
</div>



Look at the last 3 rows of the data set.


```python
df.tail(3)
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Year</th>
      <th>Datetime</th>
      <th>Stage</th>
      <th>Stadium</th>
      <th>City</th>
      <th>Home Team Name</th>
      <th>Home Team Goals</th>
      <th>Away Team Goals</th>
      <th>Away Team Name</th>
      <th>Win conditions</th>
      <th>Attendance</th>
      <th>Half-time Home Goals</th>
      <th>Half-time Away Goals</th>
      <th>Referee</th>
      <th>Assistant 1</th>
      <th>Assistant 2</th>
      <th>RoundID</th>
      <th>MatchID</th>
      <th>Home Team Initials</th>
      <th>Away Team Initials</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>849</th>
      <td>2014</td>
      <td>09 Jul 2014 - 17:00</td>
      <td>Semi-finals</td>
      <td>Arena de Sao Paulo</td>
      <td>Sao Paulo</td>
      <td>Netherlands</td>
      <td>0</td>
      <td>0</td>
      <td>Argentina</td>
      <td>Argentina win on penalties (2 - 4)</td>
      <td>63267.0</td>
      <td>0</td>
      <td>0</td>
      <td>C�neyt �AKIR (TUR)</td>
      <td>DURAN Bahattin (TUR)</td>
      <td>ONGUN Tarik (TUR)</td>
      <td>255955</td>
      <td>300186490</td>
      <td>NED</td>
      <td>ARG</td>
    </tr>
    <tr>
      <th>850</th>
      <td>2014</td>
      <td>12 Jul 2014 - 17:00</td>
      <td>Play-off for third place</td>
      <td>Estadio Nacional</td>
      <td>Brasilia</td>
      <td>Brazil</td>
      <td>0</td>
      <td>3</td>
      <td>Netherlands</td>
      <td></td>
      <td>68034.0</td>
      <td>0</td>
      <td>2</td>
      <td>HAIMOUDI Djamel (ALG)</td>
      <td>ACHIK Redouane (MAR)</td>
      <td>ETCHIALI Abdelhak (ALG)</td>
      <td>255957</td>
      <td>300186502</td>
      <td>BRA</td>
      <td>NED</td>
    </tr>
    <tr>
      <th>851</th>
      <td>2014</td>
      <td>13 Jul 2014 - 16:00</td>
      <td>Final</td>
      <td>Estadio do Maracana</td>
      <td>Rio De Janeiro</td>
      <td>Germany</td>
      <td>1</td>
      <td>0</td>
      <td>Argentina</td>
      <td>Germany win after extra time</td>
      <td>74738.0</td>
      <td>0</td>
      <td>0</td>
      <td>Nicola RIZZOLI (ITA)</td>
      <td>Renato FAVERANI (ITA)</td>
      <td>Andrea STEFANI (ITA)</td>
      <td>255959</td>
      <td>300186501</td>
      <td>GER</td>
      <td>ARG</td>
    </tr>
  </tbody>
</table>
</div>



Get a concise summary of your data using `.info()`


```python
df.info()
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 852 entries, 0 to 851
    Data columns (total 20 columns):
    Year                    852 non-null int64
    Datetime                852 non-null object
    Stage                   852 non-null object
    Stadium                 852 non-null object
    City                    852 non-null object
    Home Team Name          852 non-null object
    Home Team Goals         852 non-null int64
    Away Team Goals         852 non-null int64
    Away Team Name          852 non-null object
    Win conditions          852 non-null object
    Attendance              850 non-null float64
    Half-time Home Goals    852 non-null int64
    Half-time Away Goals    852 non-null int64
    Referee                 852 non-null object
    Assistant 1             852 non-null object
    Assistant 2             852 non-null object
    RoundID                 852 non-null int64
    MatchID                 852 non-null int64
    Home Team Initials      852 non-null object
    Away Team Initials      852 non-null object
    dtypes: float64(1), int64(7), object(12)
    memory usage: 133.2+ KB


Obtain a tuple representing the number of rows and number of columns


```python
df.shape
```




    (852, 20)



Use the appropriate attribute to get the column names


```python
df.columns
```




    Index(['Year', 'Datetime', 'Stage', 'Stadium', 'City', 'Home Team Name',
           'Home Team Goals', 'Away Team Goals', 'Away Team Name',
           'Win conditions', 'Attendance', 'Half-time Home Goals',
           'Half-time Away Goals', 'Referee', 'Assistant 1', 'Assistant 2',
           'RoundID', 'MatchID', 'Home Team Initials', 'Away Team Initials'],
          dtype='object')



## Selecting dataframe information

When looking at the dataframe's `.head()`, you might have noticed that the games are structured chronologically in the dataframe.

Use the right selection method to print all the information from the 3rd to the 5th game.


```python
df.iloc[3:6,]
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Year</th>
      <th>Datetime</th>
      <th>Stage</th>
      <th>Stadium</th>
      <th>City</th>
      <th>Home Team Name</th>
      <th>Home Team Goals</th>
      <th>Away Team Goals</th>
      <th>Away Team Name</th>
      <th>Win conditions</th>
      <th>Attendance</th>
      <th>Half-time Home Goals</th>
      <th>Half-time Away Goals</th>
      <th>Referee</th>
      <th>Assistant 1</th>
      <th>Assistant 2</th>
      <th>RoundID</th>
      <th>MatchID</th>
      <th>Home Team Initials</th>
      <th>Away Team Initials</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>3</th>
      <td>1930</td>
      <td>14 Jul 1930 - 14:50</td>
      <td>Group 3</td>
      <td>Pocitos</td>
      <td>Montevideo</td>
      <td>Romania</td>
      <td>3</td>
      <td>1</td>
      <td>Peru</td>
      <td></td>
      <td>2549.0</td>
      <td>1</td>
      <td>0</td>
      <td>WARNKEN Alberto (CHI)</td>
      <td>LANGENUS Jean (BEL)</td>
      <td>MATEUCCI Francisco (URU)</td>
      <td>201</td>
      <td>1098</td>
      <td>ROU</td>
      <td>PER</td>
    </tr>
    <tr>
      <th>4</th>
      <td>1930</td>
      <td>15 Jul 1930 - 16:00</td>
      <td>Group 1</td>
      <td>Parque Central</td>
      <td>Montevideo</td>
      <td>Argentina</td>
      <td>1</td>
      <td>0</td>
      <td>France</td>
      <td></td>
      <td>23409.0</td>
      <td>0</td>
      <td>0</td>
      <td>REGO Gilberto (BRA)</td>
      <td>SAUCEDO Ulises (BOL)</td>
      <td>RADULESCU Constantin (ROU)</td>
      <td>201</td>
      <td>1085</td>
      <td>ARG</td>
      <td>FRA</td>
    </tr>
    <tr>
      <th>5</th>
      <td>1930</td>
      <td>16 Jul 1930 - 14:45</td>
      <td>Group 1</td>
      <td>Parque Central</td>
      <td>Montevideo</td>
      <td>Chile</td>
      <td>3</td>
      <td>0</td>
      <td>Mexico</td>
      <td></td>
      <td>9249.0</td>
      <td>1</td>
      <td>0</td>
      <td>CRISTOPHE Henry (BEL)</td>
      <td>APHESTEGUY Martin (URU)</td>
      <td>LANGENUS Jean (BEL)</td>
      <td>201</td>
      <td>1095</td>
      <td>CHI</td>
      <td>MEX</td>
    </tr>
  </tbody>
</table>
</div>



Now, print all the info from game 5-9, but we're only interested to print out the "Home Team Name" and the "Away Team Name", 


```python
df.loc[5:10, ["Home Team Name", "Away Team Name"]]
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Home Team Name</th>
      <th>Away Team Name</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>5</th>
      <td>Chile</td>
      <td>Mexico</td>
    </tr>
    <tr>
      <th>6</th>
      <td>Yugoslavia</td>
      <td>Bolivia</td>
    </tr>
    <tr>
      <th>7</th>
      <td>USA</td>
      <td>Paraguay</td>
    </tr>
    <tr>
      <th>8</th>
      <td>Uruguay</td>
      <td>Peru</td>
    </tr>
    <tr>
      <th>9</th>
      <td>Chile</td>
      <td>France</td>
    </tr>
    <tr>
      <th>10</th>
      <td>Argentina</td>
      <td>Mexico</td>
    </tr>
  </tbody>
</table>
</div>



Next, we'd like the information on all the games played in Group 3 for the 1950 World Cup.


```python
df.loc[df["Stage"]=="Group 3"]
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Year</th>
      <th>Datetime</th>
      <th>Stage</th>
      <th>Stadium</th>
      <th>City</th>
      <th>Home Team Name</th>
      <th>Home Team Goals</th>
      <th>Away Team Goals</th>
      <th>Away Team Name</th>
      <th>Win conditions</th>
      <th>Attendance</th>
      <th>Half-time Home Goals</th>
      <th>Half-time Away Goals</th>
      <th>Referee</th>
      <th>Assistant 1</th>
      <th>Assistant 2</th>
      <th>RoundID</th>
      <th>MatchID</th>
      <th>Home Team Initials</th>
      <th>Away Team Initials</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>3</th>
      <td>1930</td>
      <td>14 Jul 1930 - 14:50</td>
      <td>Group 3</td>
      <td>Pocitos</td>
      <td>Montevideo</td>
      <td>Romania</td>
      <td>3</td>
      <td>1</td>
      <td>Peru</td>
      <td></td>
      <td>2549.0</td>
      <td>1</td>
      <td>0</td>
      <td>WARNKEN Alberto (CHI)</td>
      <td>LANGENUS Jean (BEL)</td>
      <td>MATEUCCI Francisco (URU)</td>
      <td>201</td>
      <td>1098</td>
      <td>ROU</td>
      <td>PER</td>
    </tr>
    <tr>
      <th>8</th>
      <td>1930</td>
      <td>18 Jul 1930 - 14:30</td>
      <td>Group 3</td>
      <td>Estadio Centenario</td>
      <td>Montevideo</td>
      <td>Uruguay</td>
      <td>1</td>
      <td>0</td>
      <td>Peru</td>
      <td></td>
      <td>57735.0</td>
      <td>0</td>
      <td>0</td>
      <td>LANGENUS Jean (BEL)</td>
      <td>BALWAY Thomas (FRA)</td>
      <td>CRISTOPHE Henry (BEL)</td>
      <td>201</td>
      <td>1099</td>
      <td>URU</td>
      <td>PER</td>
    </tr>
    <tr>
      <th>13</th>
      <td>1930</td>
      <td>21 Jul 1930 - 14:50</td>
      <td>Group 3</td>
      <td>Estadio Centenario</td>
      <td>Montevideo</td>
      <td>Uruguay</td>
      <td>4</td>
      <td>0</td>
      <td>Romania</td>
      <td></td>
      <td>70022.0</td>
      <td>4</td>
      <td>0</td>
      <td>REGO Gilberto (BRA)</td>
      <td>WARNKEN Alberto (CHI)</td>
      <td>SAUCEDO Ulises (BOL)</td>
      <td>201</td>
      <td>1100</td>
      <td>URU</td>
      <td>ROU</td>
    </tr>
    <tr>
      <th>56</th>
      <td>1950</td>
      <td>25 Jun 1950 - 15:00</td>
      <td>Group 3</td>
      <td>Pacaembu</td>
      <td>Sao Paulo</td>
      <td>Sweden</td>
      <td>3</td>
      <td>2</td>
      <td>Italy</td>
      <td></td>
      <td>36502.0</td>
      <td>2</td>
      <td>1</td>
      <td>LUTZ Jean (SUI)</td>
      <td>BERANEK Alois (AUT)</td>
      <td>TEJADA Carlos (MEX)</td>
      <td>208</td>
      <td>1219</td>
      <td>SWE</td>
      <td>ITA</td>
    </tr>
    <tr>
      <th>61</th>
      <td>1950</td>
      <td>29 Jun 1950 - 15:30</td>
      <td>Group 3</td>
      <td>Durival de Brito</td>
      <td>Curitiba</td>
      <td>Sweden</td>
      <td>2</td>
      <td>2</td>
      <td>Paraguay</td>
      <td></td>
      <td>7903.0</td>
      <td>2</td>
      <td>1</td>
      <td>MITCHELL Robert (SCO)</td>
      <td>LEMESIC Leo (YUG)</td>
      <td>GARCIA Prudencio (USA)</td>
      <td>208</td>
      <td>1228</td>
      <td>SWE</td>
      <td>PAR</td>
    </tr>
    <tr>
      <th>65</th>
      <td>1950</td>
      <td>02 Jul 1950 - 15:00</td>
      <td>Group 3</td>
      <td>Pacaembu</td>
      <td>Sao Paulo</td>
      <td>Italy</td>
      <td>2</td>
      <td>0</td>
      <td>Paraguay</td>
      <td></td>
      <td>25811.0</td>
      <td>1</td>
      <td>0</td>
      <td>ELLIS Arthur (ENG)</td>
      <td>GARCIA Prudencio (USA)</td>
      <td>DE LA SALLE Charles (FRA)</td>
      <td>208</td>
      <td>1218</td>
      <td>ITA</td>
      <td>PAR</td>
    </tr>
    <tr>
      <th>75</th>
      <td>1954</td>
      <td>16 Jun 1954 - 18:00</td>
      <td>Group 3</td>
      <td>Wankdorf Stadium</td>
      <td>Berne</td>
      <td>Uruguay</td>
      <td>2</td>
      <td>0</td>
      <td>Czechoslovakia</td>
      <td></td>
      <td>20500.0</td>
      <td>0</td>
      <td>0</td>
      <td>ELLIS Arthur (ENG)</td>
      <td>LING William (ENG)</td>
      <td>SCHICKER Werner (SUI)</td>
      <td>211</td>
      <td>1315</td>
      <td>URU</td>
      <td>TCH</td>
    </tr>
    <tr>
      <th>76</th>
      <td>1954</td>
      <td>16 Jun 1954 - 18:00</td>
      <td>Group 3</td>
      <td>Hardturm</td>
      <td>Zurich</td>
      <td>Austria</td>
      <td>1</td>
      <td>0</td>
      <td>Scotland</td>
      <td></td>
      <td>25000.0</td>
      <td>1</td>
      <td>0</td>
      <td>FRANKEN Laurent (BEL)</td>
      <td>VIANA Mario (BRA)</td>
      <td>GULDE Josef (SUI)</td>
      <td>211</td>
      <td>1236</td>
      <td>AUT</td>
      <td>SCO</td>
    </tr>
    <tr>
      <th>83</th>
      <td>1954</td>
      <td>19 Jun 1954 - 16:50</td>
      <td>Group 3</td>
      <td>St. Jakob</td>
      <td>Basel</td>
      <td>Uruguay</td>
      <td>7</td>
      <td>0</td>
      <td>Scotland</td>
      <td></td>
      <td>34000.0</td>
      <td>2</td>
      <td>0</td>
      <td>ORLANDINI Vincenzo (ITA)</td>
      <td>WYSSLING Paul (SUI)</td>
      <td>GUIDI Denilo (SUI)</td>
      <td>211</td>
      <td>1313</td>
      <td>URU</td>
      <td>SCO</td>
    </tr>
    <tr>
      <th>84</th>
      <td>1954</td>
      <td>19 Jun 1954 - 17:00</td>
      <td>Group 3</td>
      <td>Hardturm</td>
      <td>Zurich</td>
      <td>Austria</td>
      <td>5</td>
      <td>0</td>
      <td>Czechoslovakia</td>
      <td></td>
      <td>26000.0</td>
      <td>4</td>
      <td>0</td>
      <td>STEFANOVIC Vasa (YUG)</td>
      <td>DOERFLINGER Ernst (SUI)</td>
      <td>GULDE Josef (SUI)</td>
      <td>211</td>
      <td>1238</td>
      <td>AUT</td>
      <td>TCH</td>
    </tr>
    <tr>
      <th>101</th>
      <td>1958</td>
      <td>08 Jun 1958 - 14:00</td>
      <td>Group 3</td>
      <td>Rasunda Stadium</td>
      <td>Solna</td>
      <td>Sweden</td>
      <td>3</td>
      <td>0</td>
      <td>Mexico</td>
      <td></td>
      <td>34107.0</td>
      <td>1</td>
      <td>0</td>
      <td>LATYCHEV Nikolaj (URS)</td>
      <td>MOWAT Jack (SCO)</td>
      <td>ERIKSSON Arne (FIN)</td>
      <td>220</td>
      <td>1415</td>
      <td>SWE</td>
      <td>MEX</td>
    </tr>
    <tr>
      <th>104</th>
      <td>1958</td>
      <td>08 Jun 1958 - 19:00</td>
      <td>Group 3</td>
      <td>Jarnvallen</td>
      <td>Sandviken</td>
      <td>Hungary</td>
      <td>1</td>
      <td>1</td>
      <td>Wales</td>
      <td></td>
      <td>15343.0</td>
      <td>1</td>
      <td>1</td>
      <td>CODESAL Jose Maria (URU)</td>
      <td>LEMESIC Leo (YUG)</td>
      <td>VAN NUFFEL Lucien (BEL)</td>
      <td>220</td>
      <td>1407</td>
      <td>HUN</td>
      <td>WAL</td>
    </tr>
    <tr>
      <th>110</th>
      <td>1958</td>
      <td>11 Jun 1958 - 19:00</td>
      <td>Group 3</td>
      <td>Rasunda Stadium</td>
      <td>Solna</td>
      <td>Mexico</td>
      <td>1</td>
      <td>1</td>
      <td>Wales</td>
      <td></td>
      <td>15150.0</td>
      <td>0</td>
      <td>1</td>
      <td>LEMESIC Leo (YUG)</td>
      <td>LATYCHEV Nikolaj (URS)</td>
      <td>CODESAL Jose Maria (URU)</td>
      <td>220</td>
      <td>1418</td>
      <td>MEX</td>
      <td>WAL</td>
    </tr>
    <tr>
      <th>116</th>
      <td>1958</td>
      <td>12 Jun 1958 - 19:00</td>
      <td>Group 3</td>
      <td>Rasunda Stadium</td>
      <td>Solna</td>
      <td>Sweden</td>
      <td>2</td>
      <td>1</td>
      <td>Hungary</td>
      <td></td>
      <td>38850.0</td>
      <td>1</td>
      <td>0</td>
      <td>MOWAT Jack (SCO)</td>
      <td>VAN NUFFEL Lucien (BEL)</td>
      <td>DRAGVOLL Georg (NOR)</td>
      <td>220</td>
      <td>1406</td>
      <td>SWE</td>
      <td>HUN</td>
    </tr>
    <tr>
      <th>117</th>
      <td>1958</td>
      <td>15 Jun 1958 - 14:00</td>
      <td>Group 3</td>
      <td>Rasunda Stadium</td>
      <td>Solna</td>
      <td>Sweden</td>
      <td>0</td>
      <td>0</td>
      <td>Wales</td>
      <td></td>
      <td>30287.0</td>
      <td>0</td>
      <td>0</td>
      <td>VAN NUFFEL Lucien (BEL)</td>
      <td>LEMESIC Leo (YUG)</td>
      <td>LATYCHEV Nikolaj (URS)</td>
      <td>220</td>
      <td>1438</td>
      <td>SWE</td>
      <td>WAL</td>
    </tr>
    <tr>
      <th>120</th>
      <td>1958</td>
      <td>15 Jun 1958 - 19:00</td>
      <td>Group 3</td>
      <td>Jarnvallen</td>
      <td>Sandviken</td>
      <td>Hungary</td>
      <td>4</td>
      <td>0</td>
      <td>Mexico</td>
      <td></td>
      <td>13300.0</td>
      <td>1</td>
      <td>0</td>
      <td>ERIKSSON Arne (FIN)</td>
      <td>CODESAL Jose Maria (URU)</td>
      <td>MOWAT Jack (SCO)</td>
      <td>220</td>
      <td>1403</td>
      <td>HUN</td>
      <td>MEX</td>
    </tr>
    <tr>
      <th>127</th>
      <td>1958</td>
      <td>17 Jun 1958 - 19:00</td>
      <td>Group 3</td>
      <td>Rasunda Stadium</td>
      <td>Solna</td>
      <td>Wales</td>
      <td>2</td>
      <td>1</td>
      <td>Hungary</td>
      <td></td>
      <td>2823.0</td>
      <td>0</td>
      <td>1</td>
      <td>LATYCHEV Nikolaj (URS)</td>
      <td>CODESAL Jose Maria (URU)</td>
      <td>ERIKSSON Arne (FIN)</td>
      <td>220</td>
      <td>1408</td>
      <td>WAL</td>
      <td>HUN</td>
    </tr>
    <tr>
      <th>137</th>
      <td>1962</td>
      <td>30 May 1962 - 15:00</td>
      <td>Group 3</td>
      <td>Estadio Sausalito</td>
      <td>Vina Del Mar</td>
      <td>Brazil</td>
      <td>2</td>
      <td>0</td>
      <td>Mexico</td>
      <td></td>
      <td>10484.0</td>
      <td>0</td>
      <td>0</td>
      <td>DIENST Gottfried (SUI)</td>
      <td>STEINER Carl (AUT)</td>
      <td>SCHWINTE Pierre (FRA)</td>
      <td>231</td>
      <td>1461</td>
      <td>BRA</td>
      <td>MEX</td>
    </tr>
    <tr>
      <th>141</th>
      <td>1962</td>
      <td>31 May 1962 - 15:00</td>
      <td>Group 3</td>
      <td>Estadio Sausalito</td>
      <td>Vina Del Mar</td>
      <td>Czechoslovakia</td>
      <td>1</td>
      <td>0</td>
      <td>Spain</td>
      <td></td>
      <td>12700.0</td>
      <td>0</td>
      <td>0</td>
      <td>STEINER Carl (AUT)</td>
      <td>MARINO Esteban (URU)</td>
      <td>VAN ROSBERG Walter Jose (CUW)</td>
      <td>231</td>
      <td>1498</td>
      <td>TCH</td>
      <td>ESP</td>
    </tr>
    <tr>
      <th>145</th>
      <td>1962</td>
      <td>02 Jun 1962 - 15:00</td>
      <td>Group 3</td>
      <td>Estadio Sausalito</td>
      <td>Vina Del Mar</td>
      <td>Brazil</td>
      <td>0</td>
      <td>0</td>
      <td>Czechoslovakia</td>
      <td></td>
      <td>14903.0</td>
      <td>0</td>
      <td>0</td>
      <td>SCHWINTE Pierre (FRA)</td>
      <td>MASSARO Artur (CHI)</td>
      <td>DIENST Gottfried (SUI)</td>
      <td>231</td>
      <td>1462</td>
      <td>BRA</td>
      <td>TCH</td>
    </tr>
    <tr>
      <th>149</th>
      <td>1962</td>
      <td>03 Jun 1962 - 15:00</td>
      <td>Group 3</td>
      <td>Estadio Sausalito</td>
      <td>Vina Del Mar</td>
      <td>Spain</td>
      <td>1</td>
      <td>0</td>
      <td>Mexico</td>
      <td></td>
      <td>11875.0</td>
      <td>0</td>
      <td>0</td>
      <td>TESANIC Branko (YUG)</td>
      <td>VICUNA Claudio (CHI)</td>
      <td>VAN ROSBERG Walter Jose (CUW)</td>
      <td>231</td>
      <td>1497</td>
      <td>ESP</td>
      <td>MEX</td>
    </tr>
    <tr>
      <th>153</th>
      <td>1962</td>
      <td>06 Jun 1962 - 15:00</td>
      <td>Group 3</td>
      <td>Estadio Sausalito</td>
      <td>Vina Del Mar</td>
      <td>Brazil</td>
      <td>2</td>
      <td>1</td>
      <td>Spain</td>
      <td></td>
      <td>18715.0</td>
      <td>0</td>
      <td>1</td>
      <td>BUSTAMANTE Sergio (CHI)</td>
      <td>MARINO Esteban (URU)</td>
      <td>SUNDHEIM Jose Antonio (COL)</td>
      <td>231</td>
      <td>1460</td>
      <td>BRA</td>
      <td>ESP</td>
    </tr>
    <tr>
      <th>157</th>
      <td>1962</td>
      <td>07 Jun 1962 - 15:00</td>
      <td>Group 3</td>
      <td>Estadio Sausalito</td>
      <td>Vina Del Mar</td>
      <td>Mexico</td>
      <td>3</td>
      <td>1</td>
      <td>Czechoslovakia</td>
      <td></td>
      <td>10648.0</td>
      <td>2</td>
      <td>1</td>
      <td>DIENST Gottfried (SUI)</td>
      <td>TESANIC Branko (YUG)</td>
      <td>SUNDHEIM Jose Antonio (COL)</td>
      <td>231</td>
      <td>1544</td>
      <td>MEX</td>
      <td>TCH</td>
    </tr>
    <tr>
      <th>170</th>
      <td>1966</td>
      <td>12 Jul 1966 - 19:30</td>
      <td>Group 3</td>
      <td>Goodison Park</td>
      <td>Liverpool</td>
      <td>Brazil</td>
      <td>2</td>
      <td>0</td>
      <td>Bulgaria</td>
      <td></td>
      <td>47308.0</td>
      <td>1</td>
      <td>0</td>
      <td>TSCHENSCHER Kurt (GER)</td>
      <td>McCABE George (ENG)</td>
      <td>TAYLOR John (ENG)</td>
      <td>238</td>
      <td>1596</td>
      <td>BRA</td>
      <td>BUL</td>
    </tr>
    <tr>
      <th>173</th>
      <td>1966</td>
      <td>13 Jul 1966 - 19:30</td>
      <td>Group 3</td>
      <td>Old Trafford Stadium</td>
      <td>Manchester</td>
      <td>Portugal</td>
      <td>3</td>
      <td>1</td>
      <td>Hungary</td>
      <td></td>
      <td>29886.0</td>
      <td>1</td>
      <td>0</td>
      <td>CALLAGHAN Leo (WAL)</td>
      <td>HOWLEY Kevin (ENG)</td>
      <td>CLEMENTS William (ENG)</td>
      <td>238</td>
      <td>1675</td>
      <td>POR</td>
      <td>HUN</td>
    </tr>
    <tr>
      <th>178</th>
      <td>1966</td>
      <td>15 Jul 1966 - 19:30</td>
      <td>Group 3</td>
      <td>Goodison Park</td>
      <td>Liverpool</td>
      <td>Hungary</td>
      <td>3</td>
      <td>1</td>
      <td>Brazil</td>
      <td></td>
      <td>51387.0</td>
      <td>1</td>
      <td>1</td>
      <td>DAGNALL Kenneth (ENG)</td>
      <td>HOWLEY Kevin (ENG)</td>
      <td>YAMASAKI MALDONADO Arturo (MEX)</td>
      <td>238</td>
      <td>1597</td>
      <td>HUN</td>
      <td>BRA</td>
    </tr>
    <tr>
      <th>180</th>
      <td>1966</td>
      <td>16 Jul 1966 - 15:00</td>
      <td>Group 3</td>
      <td>Old Trafford Stadium</td>
      <td>Manchester</td>
      <td>Portugal</td>
      <td>3</td>
      <td>0</td>
      <td>Bulgaria</td>
      <td></td>
      <td>25438.0</td>
      <td>2</td>
      <td>0</td>
      <td>CODESAL Jose Maria (URU)</td>
      <td>GOICOECHEA Roberto (ARG)</td>
      <td>TSCHENSCHER Kurt (GER)</td>
      <td>238</td>
      <td>1602</td>
      <td>POR</td>
      <td>BUL</td>
    </tr>
    <tr>
      <th>186</th>
      <td>1966</td>
      <td>19 Jul 1966 - 19:30</td>
      <td>Group 3</td>
      <td>Goodison Park</td>
      <td>Liverpool</td>
      <td>Portugal</td>
      <td>3</td>
      <td>1</td>
      <td>Brazil</td>
      <td></td>
      <td>58479.0</td>
      <td>2</td>
      <td>0</td>
      <td>McCABE George (ENG)</td>
      <td>CALLAGHAN Leo (WAL)</td>
      <td>DAGNALL Kenneth (ENG)</td>
      <td>238</td>
      <td>1598</td>
      <td>POR</td>
      <td>BRA</td>
    </tr>
    <tr>
      <th>189</th>
      <td>1966</td>
      <td>20 Jul 1966 - 19:30</td>
      <td>Group 3</td>
      <td>Old Trafford Stadium</td>
      <td>Manchester</td>
      <td>Hungary</td>
      <td>3</td>
      <td>1</td>
      <td>Bulgaria</td>
      <td></td>
      <td>24129.0</td>
      <td>2</td>
      <td>1</td>
      <td>GOICOECHEA Roberto (ARG)</td>
      <td>GARDEAZABAL Juan (ESP)</td>
      <td>CODESAL Jose Maria (URU)</td>
      <td>238</td>
      <td>1599</td>
      <td>HUN</td>
      <td>BUL</td>
    </tr>
    <tr>
      <th>203</th>
      <td>1970</td>
      <td>02 Jun 1970 - 16:00</td>
      <td>Group 3</td>
      <td>Jalisco</td>
      <td>Guadalajara</td>
      <td>England</td>
      <td>1</td>
      <td>0</td>
      <td>Romania</td>
      <td></td>
      <td>50560.0</td>
      <td>0</td>
      <td>0</td>
      <td>LORAUX Vital (BEL)</td>
      <td>MACHIN Roger (FRA)</td>
      <td>DE LEO Diego (MEX)</td>
      <td>250</td>
      <td>1812</td>
      <td>ENG</td>
      <td>ROU</td>
    </tr>
    <tr>
      <th>206</th>
      <td>1970</td>
      <td>03 Jun 1970 - 16:00</td>
      <td>Group 3</td>
      <td>Jalisco</td>
      <td>Guadalajara</td>
      <td>Brazil</td>
      <td>4</td>
      <td>1</td>
      <td>Czechoslovakia</td>
      <td></td>
      <td>52897.0</td>
      <td>1</td>
      <td>1</td>
      <td>BARRETO RUIZ Ramon (URU)</td>
      <td>KLEIN Abraham (ISR)</td>
      <td>YAMASAKI MALDONADO Arturo (MEX)</td>
      <td>250</td>
      <td>1770</td>
      <td>BRA</td>
      <td>TCH</td>
    </tr>
    <tr>
      <th>210</th>
      <td>1970</td>
      <td>06 Jun 1970 - 16:00</td>
      <td>Group 3</td>
      <td>Jalisco</td>
      <td>Guadalajara</td>
      <td>Romania</td>
      <td>2</td>
      <td>1</td>
      <td>Czechoslovakia</td>
      <td></td>
      <td>56818.0</td>
      <td>0</td>
      <td>1</td>
      <td>DE LEO Diego (MEX)</td>
      <td>EMSBERGER Gyula (HUN)</td>
      <td>LORAUX Vital (BEL)</td>
      <td>250</td>
      <td>1919</td>
      <td>ROU</td>
      <td>TCH</td>
    </tr>
    <tr>
      <th>214</th>
      <td>1970</td>
      <td>07 Jun 1970 - 12:00</td>
      <td>Group 3</td>
      <td>Jalisco</td>
      <td>Guadalajara</td>
      <td>Brazil</td>
      <td>1</td>
      <td>0</td>
      <td>England</td>
      <td></td>
      <td>66843.0</td>
      <td>0</td>
      <td>0</td>
      <td>KLEIN Abraham (ISR)</td>
      <td>YAMASAKI MALDONADO Arturo (MEX)</td>
      <td>MACHIN Roger (FRA)</td>
      <td>250</td>
      <td>1764</td>
      <td>BRA</td>
      <td>ENG</td>
    </tr>
    <tr>
      <th>218</th>
      <td>1970</td>
      <td>10 Jun 1970 - 16:00</td>
      <td>Group 3</td>
      <td>Jalisco</td>
      <td>Guadalajara</td>
      <td>Brazil</td>
      <td>3</td>
      <td>2</td>
      <td>Romania</td>
      <td></td>
      <td>50804.0</td>
      <td>2</td>
      <td>1</td>
      <td>MARSCHALL Ferdinand (AUT)</td>
      <td>BARRETO RUIZ Ramon (URU)</td>
      <td>LORAUX Vital (BEL)</td>
      <td>250</td>
      <td>1769</td>
      <td>BRA</td>
      <td>ROU</td>
    </tr>
    <tr>
      <th>222</th>
      <td>1970</td>
      <td>11 Jun 1970 - 16:00</td>
      <td>Group 3</td>
      <td>Jalisco</td>
      <td>Guadalajara</td>
      <td>England</td>
      <td>1</td>
      <td>0</td>
      <td>Czechoslovakia</td>
      <td></td>
      <td>49292.0</td>
      <td>0</td>
      <td>0</td>
      <td>MACHIN Roger (FRA)</td>
      <td>EMSBERGER Gyula (HUN)</td>
      <td>MARSCHALL Ferdinand (AUT)</td>
      <td>250</td>
      <td>1813</td>
      <td>ENG</td>
      <td>TCH</td>
    </tr>
    <tr>
      <th>236</th>
      <td>1974</td>
      <td>15 Jun 1974 - 16:00</td>
      <td>Group 3</td>
      <td>Niedersachsenstadion</td>
      <td>Hanover</td>
      <td>Uruguay</td>
      <td>0</td>
      <td>2</td>
      <td>Netherlands</td>
      <td></td>
      <td>55100.0</td>
      <td>0</td>
      <td>1</td>
      <td>PALOTAI Karoly (HUN)</td>
      <td>KAZAKOV Pavel (URS)</td>
      <td>RAINEA Nicolae (ROU)</td>
      <td>262</td>
      <td>2098</td>
      <td>URU</td>
      <td>NED</td>
    </tr>
    <tr>
      <th>237</th>
      <td>1974</td>
      <td>15 Jun 1974 - 16:00</td>
      <td>Group 3</td>
      <td>Rheinstadion</td>
      <td>D�Sseldorf</td>
      <td>Sweden</td>
      <td>0</td>
      <td>0</td>
      <td>Bulgaria</td>
      <td></td>
      <td>23800.0</td>
      <td>0</td>
      <td>0</td>
      <td>PEREZ NUNEZ Edison A. (PER)</td>
      <td>GONZALEZ ARCHUNDIA Alfonso (MEX)</td>
      <td>SUPPIAH George (SIN)</td>
      <td>262</td>
      <td>1995</td>
      <td>SWE</td>
      <td>BUL</td>
    </tr>
    <tr>
      <th>244</th>
      <td>1974</td>
      <td>19 Jun 1974 - 19:30</td>
      <td>Group 3</td>
      <td>Westfalenstadion</td>
      <td>Dortmund</td>
      <td>Netherlands</td>
      <td>0</td>
      <td>0</td>
      <td>Sweden</td>
      <td></td>
      <td>53700.0</td>
      <td>0</td>
      <td>0</td>
      <td>WINSEMANN Werner (CAN)</td>
      <td>TSCHENSCHER Kurt (GER)</td>
      <td>THOMAS Clive (WAL)</td>
      <td>262</td>
      <td>2097</td>
      <td>NED</td>
      <td>SWE</td>
    </tr>
    <tr>
      <th>245</th>
      <td>1974</td>
      <td>19 Jun 1974 - 19:30</td>
      <td>Group 3</td>
      <td>Niedersachsenstadion</td>
      <td>Hanover</td>
      <td>Bulgaria</td>
      <td>1</td>
      <td>1</td>
      <td>Uruguay</td>
      <td></td>
      <td>13400.0</td>
      <td>0</td>
      <td>0</td>
      <td>TAYLOR John (ENG)</td>
      <td>BABACAN Dogan (TUR)</td>
      <td>OHMSEN Klaus (GER)</td>
      <td>262</td>
      <td>1996</td>
      <td>BUL</td>
      <td>URU</td>
    </tr>
    <tr>
      <th>252</th>
      <td>1974</td>
      <td>23 Jun 1974 - 16:00</td>
      <td>Group 3</td>
      <td>Westfalenstadion</td>
      <td>Dortmund</td>
      <td>Bulgaria</td>
      <td>1</td>
      <td>4</td>
      <td>Netherlands</td>
      <td></td>
      <td>53300.0</td>
      <td>0</td>
      <td>2</td>
      <td>BOSKOVIC Tony (AUS)</td>
      <td>BIWERSI Ferdinand (GER)</td>
      <td>ESCHWEILER Walter (GER)</td>
      <td>262</td>
      <td>1990</td>
      <td>BUL</td>
      <td>NED</td>
    </tr>
    <tr>
      <th>254</th>
      <td>1974</td>
      <td>23 Jun 1974 - 16:00</td>
      <td>Group 3</td>
      <td>Rheinstadion</td>
      <td>D�Sseldorf</td>
      <td>Sweden</td>
      <td>3</td>
      <td>0</td>
      <td>Uruguay</td>
      <td></td>
      <td>28300.0</td>
      <td>0</td>
      <td>0</td>
      <td>LINEMAYR Erich (AUT)</td>
      <td>LLOBREGAT Vicente (VEN)</td>
      <td>ALDINGER Heinz (GER)</td>
      <td>262</td>
      <td>2181</td>
      <td>SWE</td>
      <td>URU</td>
    </tr>
    <tr>
      <th>274</th>
      <td>1978</td>
      <td>03 Jun 1978 - 13:45</td>
      <td>Group 3</td>
      <td>Estadio Jos� Mar�a Minella</td>
      <td>Mar Del Plata</td>
      <td>Sweden</td>
      <td>1</td>
      <td>1</td>
      <td>Brazil</td>
      <td></td>
      <td>32569.0</td>
      <td>1</td>
      <td>1</td>
      <td>THOMAS Clive (WAL)</td>
      <td>JARGUZ Alojzy (POL)</td>
      <td>NAMDAR Jafar (IRN)</td>
      <td>278</td>
      <td>2253</td>
      <td>SWE</td>
      <td>BRA</td>
    </tr>
    <tr>
      <th>275</th>
      <td>1978</td>
      <td>03 Jun 1978 - 13:45</td>
      <td>Group 3</td>
      <td>Jose Amalfitani</td>
      <td>Buenos Aires</td>
      <td>Austria</td>
      <td>2</td>
      <td>1</td>
      <td>Spain</td>
      <td></td>
      <td>40841.0</td>
      <td>1</td>
      <td>1</td>
      <td>PALOTAI Karoly (HUN)</td>
      <td>BARRETO RUIZ Ramon (URU)</td>
      <td>IVANOV Anatoly (URS)</td>
      <td>278</td>
      <td>2216</td>
      <td>AUT</td>
      <td>ESP</td>
    </tr>
    <tr>
      <th>282</th>
      <td>1978</td>
      <td>07 Jun 1978 - 13:45</td>
      <td>Group 3</td>
      <td>Estadio Jos� Mar�a Minella</td>
      <td>Mar Del Plata</td>
      <td>Brazil</td>
      <td>0</td>
      <td>0</td>
      <td>Spain</td>
      <td></td>
      <td>34771.0</td>
      <td>0</td>
      <td>0</td>
      <td>GONELLA Sergio (ITA)</td>
      <td>KLEIN Abraham (ISR)</td>
      <td>ITHURRALDE Arturo Andres (ARG)</td>
      <td>278</td>
      <td>2246</td>
      <td>BRA</td>
      <td>ESP</td>
    </tr>
    <tr>
      <th>283</th>
      <td>1978</td>
      <td>07 Jun 1978 - 13:45</td>
      <td>Group 3</td>
      <td>Jose Amalfitani</td>
      <td>Buenos Aires</td>
      <td>Austria</td>
      <td>1</td>
      <td>0</td>
      <td>Sweden</td>
      <td></td>
      <td>41424.0</td>
      <td>1</td>
      <td>0</td>
      <td>CORVER Charles (NED)</td>
      <td>MAKSIMOVIC Dusan (SCG)</td>
      <td>SEOUDI Hedi (TUN)</td>
      <td>278</td>
      <td>2224</td>
      <td>AUT</td>
      <td>SWE</td>
    </tr>
    <tr>
      <th>290</th>
      <td>1978</td>
      <td>11 Jun 1978 - 13:45</td>
      <td>Group 3</td>
      <td>Estadio Jos� Mar�a Minella</td>
      <td>Mar Del Plata</td>
      <td>Brazil</td>
      <td>1</td>
      <td>0</td>
      <td>Austria</td>
      <td></td>
      <td>35221.0</td>
      <td>1</td>
      <td>0</td>
      <td>WURTZ Robert (FRA)</td>
      <td>BOUZO Farouk (SYR)</td>
      <td>GEBREYESUS DIFUE Tesfaye (ERI)</td>
      <td>278</td>
      <td>2215</td>
      <td>BRA</td>
      <td>AUT</td>
    </tr>
    <tr>
      <th>291</th>
      <td>1978</td>
      <td>11 Jun 1978 - 13:45</td>
      <td>Group 3</td>
      <td>Jose Amalfitani</td>
      <td>Buenos Aires</td>
      <td>Spain</td>
      <td>1</td>
      <td>0</td>
      <td>Sweden</td>
      <td></td>
      <td>42132.0</td>
      <td>0</td>
      <td>0</td>
      <td>BIWERSI Ferdinand (GER)</td>
      <td>ITHURRALDE Arturo Andres (ARG)</td>
      <td>PROKOP Adolf (GDR)</td>
      <td>278</td>
      <td>2337</td>
      <td>ESP</td>
      <td>SWE</td>
    </tr>
    <tr>
      <th>308</th>
      <td>1982</td>
      <td>13 Jun 1982 - 20:00</td>
      <td>Group 3</td>
      <td>Camp Nou</td>
      <td>Barcelona</td>
      <td>Argentina</td>
      <td>0</td>
      <td>1</td>
      <td>Belgium</td>
      <td></td>
      <td>95000.0</td>
      <td>0</td>
      <td>0</td>
      <td>CHRISTOV Vojtech (TCH)</td>
      <td>PALOTAI Karoly (HUN)</td>
      <td>JARGUZ Alojzy (POL)</td>
      <td>293</td>
      <td>749</td>
      <td>ARG</td>
      <td>BEL</td>
    </tr>
    <tr>
      <th>312</th>
      <td>1982</td>
      <td>15 Jun 1982 - 21:00</td>
      <td>Group 3</td>
      <td>Nuevo Estadio</td>
      <td>Elche</td>
      <td>Hungary</td>
      <td>10</td>
      <td>1</td>
      <td>El Salvador</td>
      <td></td>
      <td>23000.0</td>
      <td>3</td>
      <td>0</td>
      <td>AL DOY Ebrahim (BHR)</td>
      <td>CORVER Charles (NED)</td>
      <td>LUND-SORENSEN Henning (DEN)</td>
      <td>293</td>
      <td>896</td>
      <td>HUN</td>
      <td>SLV</td>
    </tr>
    <tr>
      <th>321</th>
      <td>1982</td>
      <td>18 Jun 1982 - 21:00</td>
      <td>Group 3</td>
      <td>Jose Rico Perez</td>
      <td>Alicante</td>
      <td>Argentina</td>
      <td>4</td>
      <td>1</td>
      <td>Hungary</td>
      <td></td>
      <td>32093.0</td>
      <td>2</td>
      <td>0</td>
      <td>LACARNE Belaid (ALG)</td>
      <td>VAUTROT Michel (FRA)</td>
      <td>RAINEA Nicolae (ROU)</td>
      <td>293</td>
      <td>752</td>
      <td>ARG</td>
      <td>HUN</td>
    </tr>
    <tr>
      <th>324</th>
      <td>1982</td>
      <td>19 Jun 1982 - 21:00</td>
      <td>Group 3</td>
      <td>Nuevo Estadio</td>
      <td>Elche</td>
      <td>Belgium</td>
      <td>1</td>
      <td>0</td>
      <td>El Salvador</td>
      <td></td>
      <td>15000.0</td>
      <td>1</td>
      <td>0</td>
      <td>MOFFATT Malcolm (NIR)</td>
      <td>CASTRO Gaston (CHI)</td>
      <td>JARGUZ Alojzy (POL)</td>
      <td>293</td>
      <td>774</td>
      <td>BEL</td>
      <td>SLV</td>
    </tr>
    <tr>
      <th>333</th>
      <td>1982</td>
      <td>22 Jun 1982 - 21:00</td>
      <td>Group 3</td>
      <td>Nuevo Estadio</td>
      <td>Elche</td>
      <td>Belgium</td>
      <td>1</td>
      <td>1</td>
      <td>Hungary</td>
      <td></td>
      <td>37000.0</td>
      <td>0</td>
      <td>1</td>
      <td>WHITE Clive (ENG)</td>
      <td>ESCHWEILER Walter (GER)</td>
      <td>LACARNE Belaid (ALG)</td>
      <td>293</td>
      <td>779</td>
      <td>BEL</td>
      <td>HUN</td>
    </tr>
    <tr>
      <th>336</th>
      <td>1982</td>
      <td>23 Jun 1982 - 21:00</td>
      <td>Group 3</td>
      <td>Jose Rico Perez</td>
      <td>Alicante</td>
      <td>Argentina</td>
      <td>2</td>
      <td>0</td>
      <td>El Salvador</td>
      <td></td>
      <td>32500.0</td>
      <td>1</td>
      <td>0</td>
      <td>BARRANCOS Luis (BOL)</td>
      <td>LAMO CASTILLO Augusto (ESP)</td>
      <td>LACARNE Belaid (ALG)</td>
      <td>293</td>
      <td>751</td>
      <td>ARG</td>
      <td>SLV</td>
    </tr>
    <tr>
      <th>346</th>
      <td>1982</td>
      <td>29 Jun 1982 - 17:15</td>
      <td>Group 3</td>
      <td>Sarria</td>
      <td>Barcelona</td>
      <td>Italy</td>
      <td>2</td>
      <td>1</td>
      <td>Argentina</td>
      <td></td>
      <td>43000.0</td>
      <td>0</td>
      <td>0</td>
      <td>RAINEA Nicolae (ROU)</td>
      <td>GALLER Bruno (SUI)</td>
      <td>LACARNE Belaid (ALG)</td>
      <td>294</td>
      <td>753</td>
      <td>ITA</td>
      <td>ARG</td>
    </tr>
    <tr>
      <th>350</th>
      <td>1982</td>
      <td>02 Jul 1982 - 17:15</td>
      <td>Group 3</td>
      <td>Sarria</td>
      <td>Barcelona</td>
      <td>Argentina</td>
      <td>1</td>
      <td>3</td>
      <td>Brazil</td>
      <td></td>
      <td>44000.0</td>
      <td>0</td>
      <td>1</td>
      <td>RUBIO VAZQUEZ Mario (MEX)</td>
      <td>ARISTIZABAL MURCIA Gilberto (COL)</td>
      <td>CASTRO Gaston (CHI)</td>
      <td>294</td>
      <td>750</td>
      <td>ARG</td>
      <td>BRA</td>
    </tr>
    <tr>
      <th>354</th>
      <td>1982</td>
      <td>05 Jul 1982 - 17:15</td>
      <td>Group 3</td>
      <td>Sarria</td>
      <td>Barcelona</td>
      <td>Italy</td>
      <td>3</td>
      <td>2</td>
      <td>Brazil</td>
      <td></td>
      <td>44000.0</td>
      <td>2</td>
      <td>1</td>
      <td>KLEIN Abraham (ISR)</td>
      <td>CHAN Thomson Tam Sun (HKG)</td>
      <td>DOTCHEV Bogdan (BUL)</td>
      <td>294</td>
      <td>788</td>
      <td>ITA</td>
      <td>BRA</td>
    </tr>
  </tbody>
</table>
</div>



Let's repeat the command above, but now we only want to print out the attendance column for the Group 3 games

You can combine conditions like this:

`df[(condition1) | (condition2)]`  -> Returns rows where either condition is true

`df[(condition1) & (condition2)]`  -> Returns rows where both conditions are true


```python
df.loc[df["Stage"]=="Group 3", ["Attendance"]]
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Attendance</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>3</th>
      <td>2549.0</td>
    </tr>
    <tr>
      <th>8</th>
      <td>57735.0</td>
    </tr>
    <tr>
      <th>13</th>
      <td>70022.0</td>
    </tr>
    <tr>
      <th>56</th>
      <td>36502.0</td>
    </tr>
    <tr>
      <th>61</th>
      <td>7903.0</td>
    </tr>
    <tr>
      <th>65</th>
      <td>25811.0</td>
    </tr>
    <tr>
      <th>75</th>
      <td>20500.0</td>
    </tr>
    <tr>
      <th>76</th>
      <td>25000.0</td>
    </tr>
    <tr>
      <th>83</th>
      <td>34000.0</td>
    </tr>
    <tr>
      <th>84</th>
      <td>26000.0</td>
    </tr>
    <tr>
      <th>101</th>
      <td>34107.0</td>
    </tr>
    <tr>
      <th>104</th>
      <td>15343.0</td>
    </tr>
    <tr>
      <th>110</th>
      <td>15150.0</td>
    </tr>
    <tr>
      <th>116</th>
      <td>38850.0</td>
    </tr>
    <tr>
      <th>117</th>
      <td>30287.0</td>
    </tr>
    <tr>
      <th>120</th>
      <td>13300.0</td>
    </tr>
    <tr>
      <th>127</th>
      <td>2823.0</td>
    </tr>
    <tr>
      <th>137</th>
      <td>10484.0</td>
    </tr>
    <tr>
      <th>141</th>
      <td>12700.0</td>
    </tr>
    <tr>
      <th>145</th>
      <td>14903.0</td>
    </tr>
    <tr>
      <th>149</th>
      <td>11875.0</td>
    </tr>
    <tr>
      <th>153</th>
      <td>18715.0</td>
    </tr>
    <tr>
      <th>157</th>
      <td>10648.0</td>
    </tr>
    <tr>
      <th>170</th>
      <td>47308.0</td>
    </tr>
    <tr>
      <th>173</th>
      <td>29886.0</td>
    </tr>
    <tr>
      <th>178</th>
      <td>51387.0</td>
    </tr>
    <tr>
      <th>180</th>
      <td>25438.0</td>
    </tr>
    <tr>
      <th>186</th>
      <td>58479.0</td>
    </tr>
    <tr>
      <th>189</th>
      <td>24129.0</td>
    </tr>
    <tr>
      <th>203</th>
      <td>50560.0</td>
    </tr>
    <tr>
      <th>206</th>
      <td>52897.0</td>
    </tr>
    <tr>
      <th>210</th>
      <td>56818.0</td>
    </tr>
    <tr>
      <th>214</th>
      <td>66843.0</td>
    </tr>
    <tr>
      <th>218</th>
      <td>50804.0</td>
    </tr>
    <tr>
      <th>222</th>
      <td>49292.0</td>
    </tr>
    <tr>
      <th>236</th>
      <td>55100.0</td>
    </tr>
    <tr>
      <th>237</th>
      <td>23800.0</td>
    </tr>
    <tr>
      <th>244</th>
      <td>53700.0</td>
    </tr>
    <tr>
      <th>245</th>
      <td>13400.0</td>
    </tr>
    <tr>
      <th>252</th>
      <td>53300.0</td>
    </tr>
    <tr>
      <th>254</th>
      <td>28300.0</td>
    </tr>
    <tr>
      <th>274</th>
      <td>32569.0</td>
    </tr>
    <tr>
      <th>275</th>
      <td>40841.0</td>
    </tr>
    <tr>
      <th>282</th>
      <td>34771.0</td>
    </tr>
    <tr>
      <th>283</th>
      <td>41424.0</td>
    </tr>
    <tr>
      <th>290</th>
      <td>35221.0</td>
    </tr>
    <tr>
      <th>291</th>
      <td>42132.0</td>
    </tr>
    <tr>
      <th>308</th>
      <td>95000.0</td>
    </tr>
    <tr>
      <th>312</th>
      <td>23000.0</td>
    </tr>
    <tr>
      <th>321</th>
      <td>32093.0</td>
    </tr>
    <tr>
      <th>324</th>
      <td>15000.0</td>
    </tr>
    <tr>
      <th>333</th>
      <td>37000.0</td>
    </tr>
    <tr>
      <th>336</th>
      <td>32500.0</td>
    </tr>
    <tr>
      <th>346</th>
      <td>43000.0</td>
    </tr>
    <tr>
      <th>350</th>
      <td>44000.0</td>
    </tr>
    <tr>
      <th>354</th>
      <td>44000.0</td>
    </tr>
  </tbody>
</table>
</div>



Throughout the entire history of the world cup, How many Home games were played by the Netherlands?


```python
df.loc[df["Home Team Name"]=="Netherlands", ["Home Team Name"]].count()
```




    Home Team Name    32
    dtype: int64



How many games were played by the Netherlands in total?


```python
df.loc[(df["Home Team Name"]=="Netherlands") | (df["Away Team Name"]=="Netherlands")].shape[0]
```




    54



Next, let's try and figure out how many games the USA played in the 2014 world cup. 


```python
wc_2014 = df[df["Year"]==2014]
wc_2014.loc[(wc_2014["Away Team Name"]=="USA") | (wc_2014["Home Team Name"]=="USA")].shape[0]
```




    5



Now, let's try to find out how many countries participated in the 1986 world cup.

Hint 1: as a first step, create a new data set that only contain games in that year.

Hint 2: You can use `.unique()` to make sure you don't end up with duplicate country names.


```python
wc_1986 = df[df["Year"]==1986]
teams = list(wc_1986["Home Team Name"].unique()) + list(wc_1986["Away Team Name"].unique())
teams = set(teams)
len(teams)
```




    24



In the world cup history, how matches had more than 5 goals in total?


```python
df["Total Goals"] = df["Home Team Goals"] + df["Away Team Goals"]
df[df["Total Goals"] >= 5].shape
df.columns
```




    Index(['Year', 'Datetime', 'Stage', 'Stadium', 'City', 'Home Team Name',
           'Home Team Goals', 'Away Team Goals', 'Away Team Name',
           'Win conditions', 'Attendance', 'Half-time Home Goals',
           'Half-time Away Goals', 'Referee', 'Assistant 1', 'Assistant 2',
           'RoundID', 'MatchID', 'Home Team Initials', 'Away Team Initials',
           'Total Goals'],
          dtype='object')



## Changing values and creating new columns

With the information you currently have in your `df`, create a new column "Half-time Goals".


```python
df["Half-time Goals"] = df["Half-time Home Goals"] + df["Half-time Away Goals"]
```

Run the code below. You'll notice that for Korea, there are records for both North-Korea (Korea DPR) and South-Korea (Korea Republic). 


```python
df.loc[df["Home Team Name"].str.contains('Korea'), "Home Team Name" ]
```




    179         Korea DPR
    187         Korea DPR
    374    Korea Republic
    386    Korea Republic
    434    Korea Republic
    444    Korea Republic
    480    Korea Republic
    524    Korea Republic
    593    Korea Republic
    609    Korea Republic
    635    Korea Republic
    642    Korea Republic
    655    Korea Republic
    710    Korea Republic
    753         Korea DPR
    802    Korea Republic
    818    Korea Republic
    Name: Home Team Name, dtype: object



Imagine that for some reason, we simply want Korea listed as one entry, so we want to replace every "Home Team Name" and "Away Team Name" entry that contains "Korea" to simply "Korea". In the same way, we want to change the columns "Home Team Initials" and "Away Team Initials" to NSK (North & South Korea) instead of "KOR" and "PRK". 


```python
df.loc[df["Home Team Name"].str.contains("Korea"), ["Home Team Name"]] = "Korea"
df.loc[df["Away Team Name"].str.contains("Korea"), ["Away Team Name"]] = "Korea"
df.loc[df["Home Team Initials"].str.contains("KOR"), ["Home Team Initials"]] = "NSK"
df.loc[df["Away Team Initials"].str.contains("PRK"), ["Away Team Initials"]] = "NSK"
```

Make sure to verify your answer!


```python
df.loc[df["Home Team Name"].str.contains("Korea"), ["Home Team Name"]]
df.loc[df["Home Team Initials"].str.contains("NSK"), ["Home Team Initials"]]
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Home Team Initials</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>374</th>
      <td>NSK</td>
    </tr>
    <tr>
      <th>386</th>
      <td>NSK</td>
    </tr>
    <tr>
      <th>434</th>
      <td>NSK</td>
    </tr>
    <tr>
      <th>444</th>
      <td>NSK</td>
    </tr>
    <tr>
      <th>480</th>
      <td>NSK</td>
    </tr>
    <tr>
      <th>524</th>
      <td>NSK</td>
    </tr>
    <tr>
      <th>593</th>
      <td>NSK</td>
    </tr>
    <tr>
      <th>609</th>
      <td>NSK</td>
    </tr>
    <tr>
      <th>635</th>
      <td>NSK</td>
    </tr>
    <tr>
      <th>642</th>
      <td>NSK</td>
    </tr>
    <tr>
      <th>655</th>
      <td>NSK</td>
    </tr>
    <tr>
      <th>710</th>
      <td>NSK</td>
    </tr>
    <tr>
      <th>802</th>
      <td>NSK</td>
    </tr>
    <tr>
      <th>818</th>
      <td>NSK</td>
    </tr>
  </tbody>
</table>
</div>



## Summary

In this lab, you learned how to access data within Pandas!
