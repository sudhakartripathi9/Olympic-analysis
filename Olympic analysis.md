```python
import numpy as np
import pandas as pd
```


```python
df = pd.read_csv("athlete_events.csv")
region_df = pd.read_csv("noc_regions.csv")
```


```python
df.tail()
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
      <th>.</th>
      <th>Name</th>
      <th>Sex</th>
      <th>Age</th>
      <th>Height</th>
      <th>Weight</th>
      <th>Team</th>
      <th>NOC</th>
      <th>Games</th>
      <th>Year</th>
      <th>Season</th>
      <th>City</th>
      <th>Sport</th>
      <th>Event</th>
      <th>Medal</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>271111</th>
      <td>135569</td>
      <td>Andrzej ya</td>
      <td>M</td>
      <td>29.0</td>
      <td>179.0</td>
      <td>89.0</td>
      <td>Poland-1</td>
      <td>POL</td>
      <td>1976 Winter</td>
      <td>1976</td>
      <td>Winter</td>
      <td>Innsbruck</td>
      <td>Luge</td>
      <td>Luge Mixed (Men)'s Doubles</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>271112</th>
      <td>135570</td>
      <td>Piotr ya</td>
      <td>M</td>
      <td>27.0</td>
      <td>176.0</td>
      <td>59.0</td>
      <td>Poland</td>
      <td>POL</td>
      <td>2014 Winter</td>
      <td>2014</td>
      <td>Winter</td>
      <td>Sochi</td>
      <td>Ski Jumping</td>
      <td>Ski Jumping Men's Large Hill, Individual</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>271113</th>
      <td>135570</td>
      <td>Piotr ya</td>
      <td>M</td>
      <td>27.0</td>
      <td>176.0</td>
      <td>59.0</td>
      <td>Poland</td>
      <td>POL</td>
      <td>2014 Winter</td>
      <td>2014</td>
      <td>Winter</td>
      <td>Sochi</td>
      <td>Ski Jumping</td>
      <td>Ski Jumping Men's Large Hill, Team</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>271114</th>
      <td>135571</td>
      <td>Tomasz Ireneusz ya</td>
      <td>M</td>
      <td>30.0</td>
      <td>185.0</td>
      <td>96.0</td>
      <td>Poland</td>
      <td>POL</td>
      <td>1998 Winter</td>
      <td>1998</td>
      <td>Winter</td>
      <td>Nagano</td>
      <td>Bobsleigh</td>
      <td>Bobsleigh Men's Four</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>271115</th>
      <td>135571</td>
      <td>Tomasz Ireneusz ya</td>
      <td>M</td>
      <td>34.0</td>
      <td>185.0</td>
      <td>96.0</td>
      <td>Poland</td>
      <td>POL</td>
      <td>2002 Winter</td>
      <td>2002</td>
      <td>Winter</td>
      <td>Salt Lake City</td>
      <td>Bobsleigh</td>
      <td>Bobsleigh Men's Four</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
</div>




```python
region_df.head()
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
      <th>NOC</th>
      <th>region</th>
      <th>notes</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>AFG</td>
      <td>Afghanistan</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1</th>
      <td>AHO</td>
      <td>Curacao</td>
      <td>Netherlands Antilles</td>
    </tr>
    <tr>
      <th>2</th>
      <td>ALB</td>
      <td>Albania</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>3</th>
      <td>ALG</td>
      <td>Algeria</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>4</th>
      <td>AND</td>
      <td>Andorra</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
</div>




```python
df.shape
```




    (271116, 15)




```python
df = df[df['Season'] =='Summer']
```


```python
df.shape
```




    (222552, 15)




```python
df.tail()
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
      <th>.</th>
      <th>Name</th>
      <th>Sex</th>
      <th>Age</th>
      <th>Height</th>
      <th>Weight</th>
      <th>Team</th>
      <th>NOC</th>
      <th>Games</th>
      <th>Year</th>
      <th>Season</th>
      <th>City</th>
      <th>Sport</th>
      <th>Event</th>
      <th>Medal</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>271106</th>
      <td>135565</td>
      <td>Fernando scar Zylberberg</td>
      <td>M</td>
      <td>27.0</td>
      <td>168.0</td>
      <td>76.0</td>
      <td>Argentina</td>
      <td>ARG</td>
      <td>2004 Summer</td>
      <td>2004</td>
      <td>Summer</td>
      <td>Athina</td>
      <td>Hockey</td>
      <td>Hockey Men's Hockey</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>271107</th>
      <td>135566</td>
      <td>James Francis "Jim" Zylker</td>
      <td>M</td>
      <td>21.0</td>
      <td>175.0</td>
      <td>75.0</td>
      <td>United States</td>
      <td>USA</td>
      <td>1972 Summer</td>
      <td>1972</td>
      <td>Summer</td>
      <td>Munich</td>
      <td>Football</td>
      <td>Football Men's Football</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>271108</th>
      <td>135567</td>
      <td>Aleksandr Viktorovich Zyuzin</td>
      <td>M</td>
      <td>24.0</td>
      <td>183.0</td>
      <td>72.0</td>
      <td>Russia</td>
      <td>RUS</td>
      <td>2000 Summer</td>
      <td>2000</td>
      <td>Summer</td>
      <td>Sydney</td>
      <td>Rowing</td>
      <td>Rowing Men's Lightweight Coxless Fours</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>271109</th>
      <td>135567</td>
      <td>Aleksandr Viktorovich Zyuzin</td>
      <td>M</td>
      <td>28.0</td>
      <td>183.0</td>
      <td>72.0</td>
      <td>Russia</td>
      <td>RUS</td>
      <td>2004 Summer</td>
      <td>2004</td>
      <td>Summer</td>
      <td>Athina</td>
      <td>Rowing</td>
      <td>Rowing Men's Lightweight Coxless Fours</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>271110</th>
      <td>135568</td>
      <td>Olga Igorevna Zyuzkova</td>
      <td>F</td>
      <td>33.0</td>
      <td>171.0</td>
      <td>69.0</td>
      <td>Belarus</td>
      <td>BLR</td>
      <td>2016 Summer</td>
      <td>2016</td>
      <td>Summer</td>
      <td>Rio de Janeiro</td>
      <td>Basketball</td>
      <td>Basketball Women's Basketball</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
</div>




```python
df = df.merge(region_df,on='NOC',how='left')
```


```python
df.head()
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
      <th>.</th>
      <th>Name</th>
      <th>Sex</th>
      <th>Age</th>
      <th>Height</th>
      <th>Weight</th>
      <th>Team</th>
      <th>NOC</th>
      <th>Games</th>
      <th>Year</th>
      <th>Season</th>
      <th>City</th>
      <th>Sport</th>
      <th>Event</th>
      <th>Medal</th>
      <th>region</th>
      <th>notes</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>A Dijiang</td>
      <td>M</td>
      <td>24.0</td>
      <td>180.0</td>
      <td>80.0</td>
      <td>China</td>
      <td>CHN</td>
      <td>1992 Summer</td>
      <td>1992</td>
      <td>Summer</td>
      <td>Barcelona</td>
      <td>Basketball</td>
      <td>Basketball Men's Basketball</td>
      <td>NaN</td>
      <td>China</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2</td>
      <td>A Lamusi</td>
      <td>M</td>
      <td>23.0</td>
      <td>170.0</td>
      <td>60.0</td>
      <td>China</td>
      <td>CHN</td>
      <td>2012 Summer</td>
      <td>2012</td>
      <td>Summer</td>
      <td>London</td>
      <td>Judo</td>
      <td>Judo Men's Extra-Lightweight</td>
      <td>NaN</td>
      <td>China</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3</td>
      <td>Gunnar Nielsen Aaby</td>
      <td>M</td>
      <td>24.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>Denmark</td>
      <td>DEN</td>
      <td>1920 Summer</td>
      <td>1920</td>
      <td>Summer</td>
      <td>Antwerpen</td>
      <td>Football</td>
      <td>Football Men's Football</td>
      <td>NaN</td>
      <td>Denmark</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>3</th>
      <td>4</td>
      <td>Edgar Lindenau Aabye</td>
      <td>M</td>
      <td>34.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>Denmark/Sweden</td>
      <td>DEN</td>
      <td>1900 Summer</td>
      <td>1900</td>
      <td>Summer</td>
      <td>Paris</td>
      <td>Tug-Of-War</td>
      <td>Tug-Of-War Men's Tug-Of-War</td>
      <td>Gold</td>
      <td>Denmark</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>4</th>
      <td>8</td>
      <td>Cornelia "Cor" Aalten (-Strannood)</td>
      <td>F</td>
      <td>18.0</td>
      <td>168.0</td>
      <td>NaN</td>
      <td>Netherlands</td>
      <td>NED</td>
      <td>1932 Summer</td>
      <td>1932</td>
      <td>Summer</td>
      <td>Los Angeles</td>
      <td>Athletics</td>
      <td>Athletics Women's 100 metres</td>
      <td>NaN</td>
      <td>Netherlands</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
</div>




```python
df["region"].unique()
```




    array(['China', 'Denmark', 'Netherlands', 'Finland', 'Norway', 'Romania',
           'Estonia', 'France', 'Morocco', 'Spain', 'Egypt', 'Iran',
           'Bulgaria', 'Italy', 'Chad', 'Azerbaijan', 'Sudan', 'Russia',
           'Argentina', 'Cuba', 'Belarus', 'Greece', 'Cameroon', 'Turkey',
           'Chile', 'Mexico', 'USA', 'Nicaragua', 'Hungary', 'Nigeria',
           'Algeria', 'Kuwait', 'Bahrain', 'Pakistan', 'Iraq', 'Syria',
           'Lebanon', 'Qatar', 'Malaysia', 'Germany', 'Canada', 'Ireland',
           'Australia', 'South Africa', 'Eritrea', 'Tanzania', 'Jordan',
           'Tunisia', 'Libya', 'Belgium', 'Djibouti', 'Palestine', 'Comoros',
           'Kazakhstan', 'Brunei', 'India', 'Saudi Arabia', 'Maldives',
           'Ethiopia', 'United Arab Emirates', 'Yemen', 'Indonesia',
           'Philippines', nan, 'Uzbekistan', 'Kyrgyzstan', 'Tajikistan',
           'Japan', 'Republic of Congo', 'Switzerland', 'Brazil', 'Monaco',
           'Israel', 'Uruguay', 'Sweden', 'Sri Lanka', 'Armenia',
           'Ivory Coast', 'Kenya', 'Benin', 'UK', 'Ghana', 'Somalia', 'Niger',
           'Mali', 'Afghanistan', 'Poland', 'Costa Rica', 'Panama', 'Georgia',
           'Slovenia', 'Guyana', 'New Zealand', 'Portugal', 'Paraguay',
           'Angola', 'Venezuela', 'Colombia', 'Bangladesh', 'Peru',
           'El Salvador', 'Puerto Rico', 'Uganda', 'Honduras', 'Ecuador',
           'Turkmenistan', 'Mauritius', 'Seychelles', 'Czech Republic',
           'Luxembourg', 'Mauritania', 'Saint Kitts', 'Trinidad',
           'Dominican Republic', 'Saint Vincent', 'Jamaica', 'Liberia',
           'Suriname', 'Nepal', 'Mongolia', 'Austria', 'Palau', 'Lithuania',
           'Togo', 'Namibia', 'Curacao', 'Ukraine', 'Iceland',
           'American Samoa', 'Samoa', 'Rwanda', 'Croatia', 'Dominica',
           'Haiti', 'Malta', 'Cyprus', 'Guinea', 'Belize', 'Thailand',
           'Bermuda', 'Serbia', 'Sierra Leone', 'Papua New Guinea',
           'Individual Olympic Athletes', 'Oman', 'Fiji', 'Vanuatu',
           'Moldova', 'Bahamas', 'Guatemala', 'Latvia',
           'Virgin Islands, British', 'Mozambique', 'Virgin Islands, US',
           'Central African Republic', 'Madagascar', 'Bosnia and Herzegovina',
           'Guam', 'Cayman Islands', 'Slovakia', 'Barbados', 'Guinea-Bissau',
           'Timor-Leste', 'Democratic Republic of the Congo', 'Gabon',
           'San Marino', 'Laos', 'Botswana', 'South Korea', 'Cambodia',
           'North Korea', 'Solomon Islands', 'Senegal', 'Cape Verde',
           'Equatorial Guinea', 'Boliva', 'Antigua', 'Andorra', 'Zimbabwe',
           'Grenada', 'Saint Lucia', 'Micronesia', 'Myanmar', 'Malawi',
           'Zambia', 'Taiwan', 'Sao Tome and Principe', 'Macedonia',
           'Liechtenstein', 'Montenegro', 'Gambia', 'Cook Islands', 'Albania',
           'Swaziland', 'Burkina Faso', 'Burundi', 'Aruba', 'Nauru',
           'Vietnam', 'Bhutan', 'Marshall Islands', 'Kiribati', 'Tonga',
           'Kosovo', 'South Sudan', 'Lesotho'], dtype=object)




```python
df.isnull().sum()
```




    .              0
    Name           0
    Sex            0
    Age         9189
    Height     51857
    Weight     53854
    Team           0
    NOC            0
    Games          0
    Year           0
    Season         0
    City           0
    Sport          0
    Event          0
    Medal     188464
    region       370
    notes     218151
    dtype: int64




```python
df.duplicated().sum()
```




    1385




```python
df.drop_duplicates(inplace=True)
```


```python
df.duplicated().sum()
```




    0




```python
df["Medal"].value_counts()
```




    Gold      11456
    Bronze    11409
    Silver    11212
    Name: Medal, dtype: int64




```python
# pd.get_dummies(df["Medal"])
```


```python
df = pd.concat([df,pd.get_dummies(df["Medal"])],axis=1)
```


```python
df.tail()
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
      <th>.</th>
      <th>Name</th>
      <th>Sex</th>
      <th>Age</th>
      <th>Height</th>
      <th>Weight</th>
      <th>Team</th>
      <th>NOC</th>
      <th>Games</th>
      <th>Year</th>
      <th>Season</th>
      <th>City</th>
      <th>Sport</th>
      <th>Event</th>
      <th>Medal</th>
      <th>region</th>
      <th>notes</th>
      <th>Bronze</th>
      <th>Gold</th>
      <th>Silver</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>222547</th>
      <td>135565</td>
      <td>Fernando scar Zylberberg</td>
      <td>M</td>
      <td>27.0</td>
      <td>168.0</td>
      <td>76.0</td>
      <td>Argentina</td>
      <td>ARG</td>
      <td>2004 Summer</td>
      <td>2004</td>
      <td>Summer</td>
      <td>Athina</td>
      <td>Hockey</td>
      <td>Hockey Men's Hockey</td>
      <td>NaN</td>
      <td>Argentina</td>
      <td>NaN</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>222548</th>
      <td>135566</td>
      <td>James Francis "Jim" Zylker</td>
      <td>M</td>
      <td>21.0</td>
      <td>175.0</td>
      <td>75.0</td>
      <td>United States</td>
      <td>USA</td>
      <td>1972 Summer</td>
      <td>1972</td>
      <td>Summer</td>
      <td>Munich</td>
      <td>Football</td>
      <td>Football Men's Football</td>
      <td>NaN</td>
      <td>USA</td>
      <td>NaN</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>222549</th>
      <td>135567</td>
      <td>Aleksandr Viktorovich Zyuzin</td>
      <td>M</td>
      <td>24.0</td>
      <td>183.0</td>
      <td>72.0</td>
      <td>Russia</td>
      <td>RUS</td>
      <td>2000 Summer</td>
      <td>2000</td>
      <td>Summer</td>
      <td>Sydney</td>
      <td>Rowing</td>
      <td>Rowing Men's Lightweight Coxless Fours</td>
      <td>NaN</td>
      <td>Russia</td>
      <td>NaN</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>222550</th>
      <td>135567</td>
      <td>Aleksandr Viktorovich Zyuzin</td>
      <td>M</td>
      <td>28.0</td>
      <td>183.0</td>
      <td>72.0</td>
      <td>Russia</td>
      <td>RUS</td>
      <td>2004 Summer</td>
      <td>2004</td>
      <td>Summer</td>
      <td>Athina</td>
      <td>Rowing</td>
      <td>Rowing Men's Lightweight Coxless Fours</td>
      <td>NaN</td>
      <td>Russia</td>
      <td>NaN</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>222551</th>
      <td>135568</td>
      <td>Olga Igorevna Zyuzkova</td>
      <td>F</td>
      <td>33.0</td>
      <td>171.0</td>
      <td>69.0</td>
      <td>Belarus</td>
      <td>BLR</td>
      <td>2016 Summer</td>
      <td>2016</td>
      <td>Summer</td>
      <td>Rio de Janeiro</td>
      <td>Basketball</td>
      <td>Basketball Women's Basketball</td>
      <td>NaN</td>
      <td>Belarus</td>
      <td>NaN</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
  </tbody>
</table>
</div>




```python
df.groupby("NOC").sum()[['Gold','Silver','Bronze']].sort_values('Gold',ascending=False).reset_index().head(30)
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
      <th>NOC</th>
      <th>Gold</th>
      <th>Silver</th>
      <th>Bronze</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>USA</td>
      <td>2472.0</td>
      <td>1333.0</td>
      <td>1197.0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>URS</td>
      <td>832.0</td>
      <td>635.0</td>
      <td>596.0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>GBR</td>
      <td>635.0</td>
      <td>729.0</td>
      <td>620.0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>GER</td>
      <td>592.0</td>
      <td>538.0</td>
      <td>649.0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>ITA</td>
      <td>518.0</td>
      <td>474.0</td>
      <td>454.0</td>
    </tr>
    <tr>
      <th>5</th>
      <td>FRA</td>
      <td>463.0</td>
      <td>567.0</td>
      <td>587.0</td>
    </tr>
    <tr>
      <th>6</th>
      <td>HUN</td>
      <td>432.0</td>
      <td>328.0</td>
      <td>363.0</td>
    </tr>
    <tr>
      <th>7</th>
      <td>SWE</td>
      <td>354.0</td>
      <td>396.0</td>
      <td>358.0</td>
    </tr>
    <tr>
      <th>8</th>
      <td>AUS</td>
      <td>342.0</td>
      <td>452.0</td>
      <td>510.0</td>
    </tr>
    <tr>
      <th>9</th>
      <td>GDR</td>
      <td>339.0</td>
      <td>277.0</td>
      <td>227.0</td>
    </tr>
    <tr>
      <th>10</th>
      <td>CHN</td>
      <td>334.0</td>
      <td>317.0</td>
      <td>258.0</td>
    </tr>
    <tr>
      <th>11</th>
      <td>RUS</td>
      <td>296.0</td>
      <td>278.0</td>
      <td>331.0</td>
    </tr>
    <tr>
      <th>12</th>
      <td>NED</td>
      <td>245.0</td>
      <td>302.0</td>
      <td>371.0</td>
    </tr>
    <tr>
      <th>13</th>
      <td>JPN</td>
      <td>230.0</td>
      <td>287.0</td>
      <td>333.0</td>
    </tr>
    <tr>
      <th>14</th>
      <td>NOR</td>
      <td>227.0</td>
      <td>196.0</td>
      <td>167.0</td>
    </tr>
    <tr>
      <th>15</th>
      <td>DEN</td>
      <td>179.0</td>
      <td>236.0</td>
      <td>177.0</td>
    </tr>
    <tr>
      <th>16</th>
      <td>KOR</td>
      <td>171.0</td>
      <td>206.0</td>
      <td>175.0</td>
    </tr>
    <tr>
      <th>17</th>
      <td>CUB</td>
      <td>164.0</td>
      <td>129.0</td>
      <td>116.0</td>
    </tr>
    <tr>
      <th>18</th>
      <td>ROU</td>
      <td>161.0</td>
      <td>200.0</td>
      <td>290.0</td>
    </tr>
    <tr>
      <th>19</th>
      <td>CAN</td>
      <td>158.0</td>
      <td>239.0</td>
      <td>344.0</td>
    </tr>
    <tr>
      <th>20</th>
      <td>FRG</td>
      <td>144.0</td>
      <td>172.0</td>
      <td>188.0</td>
    </tr>
    <tr>
      <th>21</th>
      <td>FIN</td>
      <td>132.0</td>
      <td>125.0</td>
      <td>217.0</td>
    </tr>
    <tr>
      <th>22</th>
      <td>IND</td>
      <td>131.0</td>
      <td>19.0</td>
      <td>40.0</td>
    </tr>
    <tr>
      <th>23</th>
      <td>YUG</td>
      <td>130.0</td>
      <td>161.0</td>
      <td>92.0</td>
    </tr>
    <tr>
      <th>24</th>
      <td>POL</td>
      <td>111.0</td>
      <td>185.0</td>
      <td>242.0</td>
    </tr>
    <tr>
      <th>25</th>
      <td>BRA</td>
      <td>109.0</td>
      <td>175.0</td>
      <td>191.0</td>
    </tr>
    <tr>
      <th>26</th>
      <td>ESP</td>
      <td>109.0</td>
      <td>243.0</td>
      <td>135.0</td>
    </tr>
    <tr>
      <th>27</th>
      <td>SUI</td>
      <td>99.0</td>
      <td>178.0</td>
      <td>139.0</td>
    </tr>
    <tr>
      <th>28</th>
      <td>BEL</td>
      <td>96.0</td>
      <td>193.0</td>
      <td>166.0</td>
    </tr>
    <tr>
      <th>29</th>
      <td>EUN</td>
      <td>92.0</td>
      <td>61.0</td>
      <td>67.0</td>
    </tr>
  </tbody>
</table>
</div>




```python
df[(df["NOC"]== "IND") & (df["Medal"]=="Gold")].head(10)
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
      <th>.</th>
      <th>Name</th>
      <th>Sex</th>
      <th>Age</th>
      <th>Height</th>
      <th>Weight</th>
      <th>Team</th>
      <th>NOC</th>
      <th>Games</th>
      <th>Year</th>
      <th>Season</th>
      <th>City</th>
      <th>Sport</th>
      <th>Event</th>
      <th>Medal</th>
      <th>region</th>
      <th>notes</th>
      <th>Bronze</th>
      <th>Gold</th>
      <th>Silver</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>4186</th>
      <td>2699</td>
      <td>Shaukat Ali</td>
      <td>M</td>
      <td>30.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>India</td>
      <td>IND</td>
      <td>1928 Summer</td>
      <td>1928</td>
      <td>Summer</td>
      <td>Amsterdam</td>
      <td>Hockey</td>
      <td>Hockey Men's Hockey</td>
      <td>Gold</td>
      <td>India</td>
      <td>NaN</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
    </tr>
    <tr>
      <th>4190</th>
      <td>2703</td>
      <td>Syed Mushtaq Ali</td>
      <td>M</td>
      <td>22.0</td>
      <td>165.0</td>
      <td>61.0</td>
      <td>India</td>
      <td>IND</td>
      <td>1964 Summer</td>
      <td>1964</td>
      <td>Summer</td>
      <td>Tokyo</td>
      <td>Hockey</td>
      <td>Hockey Men's Hockey</td>
      <td>Gold</td>
      <td>India</td>
      <td>NaN</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
    </tr>
    <tr>
      <th>4460</th>
      <td>2864</td>
      <td>Richard James Allen</td>
      <td>M</td>
      <td>25.0</td>
      <td>172.0</td>
      <td>NaN</td>
      <td>India</td>
      <td>IND</td>
      <td>1928 Summer</td>
      <td>1928</td>
      <td>Summer</td>
      <td>Amsterdam</td>
      <td>Hockey</td>
      <td>Hockey Men's Hockey</td>
      <td>Gold</td>
      <td>India</td>
      <td>NaN</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
    </tr>
    <tr>
      <th>4461</th>
      <td>2864</td>
      <td>Richard James Allen</td>
      <td>M</td>
      <td>30.0</td>
      <td>172.0</td>
      <td>NaN</td>
      <td>India</td>
      <td>IND</td>
      <td>1932 Summer</td>
      <td>1932</td>
      <td>Summer</td>
      <td>Los Angeles</td>
      <td>Hockey</td>
      <td>Hockey Men's Hockey</td>
      <td>Gold</td>
      <td>India</td>
      <td>NaN</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
    </tr>
    <tr>
      <th>4462</th>
      <td>2864</td>
      <td>Richard James Allen</td>
      <td>M</td>
      <td>34.0</td>
      <td>172.0</td>
      <td>NaN</td>
      <td>India</td>
      <td>IND</td>
      <td>1936 Summer</td>
      <td>1936</td>
      <td>Summer</td>
      <td>Berlin</td>
      <td>Hockey</td>
      <td>Hockey Men's Hockey</td>
      <td>Gold</td>
      <td>India</td>
      <td>NaN</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
    </tr>
    <tr>
      <th>8794</th>
      <td>5618</td>
      <td>Sardar Mohammad Aslam</td>
      <td>M</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>India</td>
      <td>IND</td>
      <td>1932 Summer</td>
      <td>1932</td>
      <td>Summer</td>
      <td>Los Angeles</td>
      <td>Hockey</td>
      <td>Hockey Men's Hockey</td>
      <td>Gold</td>
      <td>India</td>
      <td>NaN</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
    </tr>
    <tr>
      <th>17790</th>
      <td>11197</td>
      <td>Vasudevan Bhaskaran</td>
      <td>M</td>
      <td>29.0</td>
      <td>174.0</td>
      <td>68.0</td>
      <td>India</td>
      <td>IND</td>
      <td>1980 Summer</td>
      <td>1980</td>
      <td>Summer</td>
      <td>Moskva</td>
      <td>Hockey</td>
      <td>Hockey Men's Hockey</td>
      <td>Gold</td>
      <td>India</td>
      <td>NaN</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
    </tr>
    <tr>
      <th>18444</th>
      <td>11601</td>
      <td>Abhinav Bindra</td>
      <td>M</td>
      <td>25.0</td>
      <td>173.0</td>
      <td>70.0</td>
      <td>India</td>
      <td>IND</td>
      <td>2008 Summer</td>
      <td>2008</td>
      <td>Summer</td>
      <td>Beijing</td>
      <td>Shooting</td>
      <td>Shooting Men's Air Rifle, 10 metres</td>
      <td>Gold</td>
      <td>India</td>
      <td>NaN</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
    </tr>
    <tr>
      <th>20526</th>
      <td>12911</td>
      <td>Lal Shah S. Bokhari</td>
      <td>M</td>
      <td>23.0</td>
      <td>173.0</td>
      <td>NaN</td>
      <td>India</td>
      <td>IND</td>
      <td>1932 Summer</td>
      <td>1932</td>
      <td>Summer</td>
      <td>Los Angeles</td>
      <td>Hockey</td>
      <td>Hockey Men's Hockey</td>
      <td>Gold</td>
      <td>India</td>
      <td>NaN</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
    </tr>
    <tr>
      <th>24192</th>
      <td>15011</td>
      <td>Frank Gerald Singlehurst Brewin</td>
      <td>M</td>
      <td>22.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>India</td>
      <td>IND</td>
      <td>1932 Summer</td>
      <td>1932</td>
      <td>Summer</td>
      <td>Los Angeles</td>
      <td>Hockey</td>
      <td>Hockey Men's Hockey</td>
      <td>Gold</td>
      <td>India</td>
      <td>NaN</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
    </tr>
  </tbody>
</table>
</div>




```python
medal_tally = df.drop_duplicates(subset=['Team','region','Games','Year','City','Sport','Event','Medal'])
```


```python
medal_tally
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
      <th>.</th>
      <th>Name</th>
      <th>Sex</th>
      <th>Age</th>
      <th>Height</th>
      <th>Weight</th>
      <th>Team</th>
      <th>NOC</th>
      <th>Games</th>
      <th>Year</th>
      <th>Season</th>
      <th>City</th>
      <th>Sport</th>
      <th>Event</th>
      <th>Medal</th>
      <th>region</th>
      <th>notes</th>
      <th>Bronze</th>
      <th>Gold</th>
      <th>Silver</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>A Dijiang</td>
      <td>M</td>
      <td>24.0</td>
      <td>180.0</td>
      <td>80.0</td>
      <td>China</td>
      <td>CHN</td>
      <td>1992 Summer</td>
      <td>1992</td>
      <td>Summer</td>
      <td>Barcelona</td>
      <td>Basketball</td>
      <td>Basketball Men's Basketball</td>
      <td>NaN</td>
      <td>China</td>
      <td>NaN</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2</td>
      <td>A Lamusi</td>
      <td>M</td>
      <td>23.0</td>
      <td>170.0</td>
      <td>60.0</td>
      <td>China</td>
      <td>CHN</td>
      <td>2012 Summer</td>
      <td>2012</td>
      <td>Summer</td>
      <td>London</td>
      <td>Judo</td>
      <td>Judo Men's Extra-Lightweight</td>
      <td>NaN</td>
      <td>China</td>
      <td>NaN</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3</td>
      <td>Gunnar Nielsen Aaby</td>
      <td>M</td>
      <td>24.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>Denmark</td>
      <td>DEN</td>
      <td>1920 Summer</td>
      <td>1920</td>
      <td>Summer</td>
      <td>Antwerpen</td>
      <td>Football</td>
      <td>Football Men's Football</td>
      <td>NaN</td>
      <td>Denmark</td>
      <td>NaN</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>4</td>
      <td>Edgar Lindenau Aabye</td>
      <td>M</td>
      <td>34.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>Denmark/Sweden</td>
      <td>DEN</td>
      <td>1900 Summer</td>
      <td>1900</td>
      <td>Summer</td>
      <td>Paris</td>
      <td>Tug-Of-War</td>
      <td>Tug-Of-War Men's Tug-Of-War</td>
      <td>Gold</td>
      <td>Denmark</td>
      <td>NaN</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>8</td>
      <td>Cornelia "Cor" Aalten (-Strannood)</td>
      <td>F</td>
      <td>18.0</td>
      <td>168.0</td>
      <td>NaN</td>
      <td>Netherlands</td>
      <td>NED</td>
      <td>1932 Summer</td>
      <td>1932</td>
      <td>Summer</td>
      <td>Los Angeles</td>
      <td>Athletics</td>
      <td>Athletics Women's 100 metres</td>
      <td>NaN</td>
      <td>Netherlands</td>
      <td>NaN</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>222528</th>
      <td>135553</td>
      <td>Galina Ivanovna Zybina (-Fyodorova)</td>
      <td>F</td>
      <td>25.0</td>
      <td>168.0</td>
      <td>80.0</td>
      <td>Soviet Union</td>
      <td>URS</td>
      <td>1956 Summer</td>
      <td>1956</td>
      <td>Summer</td>
      <td>Melbourne</td>
      <td>Athletics</td>
      <td>Athletics Women's Shot Put</td>
      <td>Silver</td>
      <td>Russia</td>
      <td>NaN</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>222530</th>
      <td>135553</td>
      <td>Galina Ivanovna Zybina (-Fyodorova)</td>
      <td>F</td>
      <td>33.0</td>
      <td>168.0</td>
      <td>80.0</td>
      <td>Soviet Union</td>
      <td>URS</td>
      <td>1964 Summer</td>
      <td>1964</td>
      <td>Summer</td>
      <td>Tokyo</td>
      <td>Athletics</td>
      <td>Athletics Women's Shot Put</td>
      <td>Bronze</td>
      <td>Russia</td>
      <td>NaN</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>222536</th>
      <td>135556</td>
      <td>Bogusaw Stanisaw Zychowicz</td>
      <td>M</td>
      <td>19.0</td>
      <td>189.0</td>
      <td>80.0</td>
      <td>Poland</td>
      <td>POL</td>
      <td>1980 Summer</td>
      <td>1980</td>
      <td>Summer</td>
      <td>Moskva</td>
      <td>Swimming</td>
      <td>Swimming Men's 100 metres Butterfly</td>
      <td>NaN</td>
      <td>Poland</td>
      <td>NaN</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>222537</th>
      <td>135556</td>
      <td>Bogusaw Stanisaw Zychowicz</td>
      <td>M</td>
      <td>19.0</td>
      <td>189.0</td>
      <td>80.0</td>
      <td>Poland</td>
      <td>POL</td>
      <td>1980 Summer</td>
      <td>1980</td>
      <td>Summer</td>
      <td>Moskva</td>
      <td>Swimming</td>
      <td>Swimming Men's 200 metres Butterfly</td>
      <td>NaN</td>
      <td>Poland</td>
      <td>NaN</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>222541</th>
      <td>135560</td>
      <td>Stavroula Zygouri</td>
      <td>F</td>
      <td>36.0</td>
      <td>171.0</td>
      <td>63.0</td>
      <td>Greece</td>
      <td>GRE</td>
      <td>2004 Summer</td>
      <td>2004</td>
      <td>Summer</td>
      <td>Athina</td>
      <td>Wrestling</td>
      <td>Wrestling Women's Middleweight, Freestyle</td>
      <td>NaN</td>
      <td>Greece</td>
      <td>NaN</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
  </tbody>
</table>
<p>105636 rows × 20 columns</p>
</div>




```python
medal_tally = medal_tally.groupby("region").sum()[['Gold','Silver','Bronze']].sort_values('Gold',ascending=False).reset_index()
```


```python
medal_tally['Total']=medal_tally['Gold']+medal_tally['Silver']+medal_tally['Bronze']
```


```python
medal_tally
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
      <th>region</th>
      <th>Gold</th>
      <th>Silver</th>
      <th>Bronze</th>
      <th>Total</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>USA</td>
      <td>1035.0</td>
      <td>802.0</td>
      <td>708.0</td>
      <td>2545.0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Russia</td>
      <td>592.0</td>
      <td>498.0</td>
      <td>487.0</td>
      <td>1577.0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Germany</td>
      <td>444.0</td>
      <td>457.0</td>
      <td>491.0</td>
      <td>1392.0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>UK</td>
      <td>278.0</td>
      <td>317.0</td>
      <td>300.0</td>
      <td>895.0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>France</td>
      <td>234.0</td>
      <td>256.0</td>
      <td>287.0</td>
      <td>777.0</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>200</th>
      <td>Lesotho</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>201</th>
      <td>Albania</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>202</th>
      <td>Libya</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>203</th>
      <td>Liechtenstein</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>204</th>
      <td>Liberia</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
    </tr>
  </tbody>
</table>
<p>205 rows × 5 columns</p>
</div>




```python
years = df['Year'].unique().tolist()
years.sort()
years.insert(0, 'Overall')
```


```python
years
```




    ['Overall',
     1896,
     1900,
     1904,
     1906,
     1908,
     1912,
     1920,
     1924,
     1928,
     1932,
     1936,
     1948,
     1952,
     1956,
     1960,
     1964,
     1968,
     1972,
     1976,
     1980,
     1984,
     1988,
     1992,
     1996,
     2000,
     2004,
     2008,
     2012,
     2016]




```python
country = np.unique(df['region'].dropna().values).tolist()
country.sort()
country.insert(0, 'Overall')
```


```python
country
```




    ['Overall',
     'Afghanistan',
     'Albania',
     'Algeria',
     'American Samoa',
     'Andorra',
     'Angola',
     'Antigua',
     'Argentina',
     'Armenia',
     'Aruba',
     'Australia',
     'Austria',
     'Azerbaijan',
     'Bahamas',
     'Bahrain',
     'Bangladesh',
     'Barbados',
     'Belarus',
     'Belgium',
     'Belize',
     'Benin',
     'Bermuda',
     'Bhutan',
     'Boliva',
     'Bosnia and Herzegovina',
     'Botswana',
     'Brazil',
     'Brunei',
     'Bulgaria',
     'Burkina Faso',
     'Burundi',
     'Cambodia',
     'Cameroon',
     'Canada',
     'Cape Verde',
     'Cayman Islands',
     'Central African Republic',
     'Chad',
     'Chile',
     'China',
     'Colombia',
     'Comoros',
     'Cook Islands',
     'Costa Rica',
     'Croatia',
     'Cuba',
     'Curacao',
     'Cyprus',
     'Czech Republic',
     'Democratic Republic of the Congo',
     'Denmark',
     'Djibouti',
     'Dominica',
     'Dominican Republic',
     'Ecuador',
     'Egypt',
     'El Salvador',
     'Equatorial Guinea',
     'Eritrea',
     'Estonia',
     'Ethiopia',
     'Fiji',
     'Finland',
     'France',
     'Gabon',
     'Gambia',
     'Georgia',
     'Germany',
     'Ghana',
     'Greece',
     'Grenada',
     'Guam',
     'Guatemala',
     'Guinea',
     'Guinea-Bissau',
     'Guyana',
     'Haiti',
     'Honduras',
     'Hungary',
     'Iceland',
     'India',
     'Individual Olympic Athletes',
     'Indonesia',
     'Iran',
     'Iraq',
     'Ireland',
     'Israel',
     'Italy',
     'Ivory Coast',
     'Jamaica',
     'Japan',
     'Jordan',
     'Kazakhstan',
     'Kenya',
     'Kiribati',
     'Kosovo',
     'Kuwait',
     'Kyrgyzstan',
     'Laos',
     'Latvia',
     'Lebanon',
     'Lesotho',
     'Liberia',
     'Libya',
     'Liechtenstein',
     'Lithuania',
     'Luxembourg',
     'Macedonia',
     'Madagascar',
     'Malawi',
     'Malaysia',
     'Maldives',
     'Mali',
     'Malta',
     'Marshall Islands',
     'Mauritania',
     'Mauritius',
     'Mexico',
     'Micronesia',
     'Moldova',
     'Monaco',
     'Mongolia',
     'Montenegro',
     'Morocco',
     'Mozambique',
     'Myanmar',
     'Namibia',
     'Nauru',
     'Nepal',
     'Netherlands',
     'New Zealand',
     'Nicaragua',
     'Niger',
     'Nigeria',
     'North Korea',
     'Norway',
     'Oman',
     'Pakistan',
     'Palau',
     'Palestine',
     'Panama',
     'Papua New Guinea',
     'Paraguay',
     'Peru',
     'Philippines',
     'Poland',
     'Portugal',
     'Puerto Rico',
     'Qatar',
     'Republic of Congo',
     'Romania',
     'Russia',
     'Rwanda',
     'Saint Kitts',
     'Saint Lucia',
     'Saint Vincent',
     'Samoa',
     'San Marino',
     'Sao Tome and Principe',
     'Saudi Arabia',
     'Senegal',
     'Serbia',
     'Seychelles',
     'Sierra Leone',
     'Slovakia',
     'Slovenia',
     'Solomon Islands',
     'Somalia',
     'South Africa',
     'South Korea',
     'South Sudan',
     'Spain',
     'Sri Lanka',
     'Sudan',
     'Suriname',
     'Swaziland',
     'Sweden',
     'Switzerland',
     'Syria',
     'Taiwan',
     'Tajikistan',
     'Tanzania',
     'Thailand',
     'Timor-Leste',
     'Togo',
     'Tonga',
     'Trinidad',
     'Tunisia',
     'Turkey',
     'Turkmenistan',
     'UK',
     'USA',
     'Uganda',
     'Ukraine',
     'United Arab Emirates',
     'Uruguay',
     'Uzbekistan',
     'Vanuatu',
     'Venezuela',
     'Vietnam',
     'Virgin Islands, British',
     'Virgin Islands, US',
     'Yemen',
     'Zambia',
     'Zimbabwe']




```python
def fetch_medal_tally(year,country):
    flag = 0
    if year=='Overall' and country=='Overall':
        temp_df = medal_df

    if year=='Overall' and country !='Overall':
        temp_df = medal_df[medal_df['region']== country]
        flag = 1
        
    if year !='Overall' and country=='Overall':
        temp_df = medal_df[medal_df['Year']==int(year)]
        
    if year !='Overall' and country !='Overall':
        temp_df = medal_df[(medal_df['Year']==year) & (medal_df['region']== country)]
    
    if flag == 1:
        x = temp_df.groupby('Year').sum()[['Gold', 'Silver', 'Bronze']].sort_values('Year').reset_index()
    else:
        x = temp_df.groupby('region').sum()[['Gold', 'Silver', 'Bronze']].sort_values('Gold',
                                                                                      ascending=False).reset_index()
        
    x['total'] = x['Gold'] + x['Silver'] + x['Bronze']
        
    print(x)
```


```python
# fetch_medal_tally(year= 1900,country='Overall')
```


```python
medal_df = df.drop_duplicates(subset=['Name','Team','region','Games','Year','City','Sport','Event','Medal'])
```


```python
medal_df[(medal_df['region']== 'Norway') & (medal_df['Year']==1968)]
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
      <th>.</th>
      <th>Name</th>
      <th>Sex</th>
      <th>Age</th>
      <th>Height</th>
      <th>Weight</th>
      <th>Team</th>
      <th>NOC</th>
      <th>Games</th>
      <th>Year</th>
      <th>Season</th>
      <th>City</th>
      <th>Sport</th>
      <th>Event</th>
      <th>Medal</th>
      <th>region</th>
      <th>notes</th>
      <th>Bronze</th>
      <th>Gold</th>
      <th>Silver</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>39</th>
      <td>28</td>
      <td>Jan-Erik Aarberg</td>
      <td>M</td>
      <td>43.0</td>
      <td>170.0</td>
      <td>77.0</td>
      <td>Norway</td>
      <td>NOR</td>
      <td>1968 Summer</td>
      <td>1968</td>
      <td>Summer</td>
      <td>Mexico City</td>
      <td>Sailing</td>
      <td>Sailing Mixed Three Person Keelboat</td>
      <td>NaN</td>
      <td>Norway</td>
      <td>NaN</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>5601</th>
      <td>3557</td>
      <td>Steinar Amundsen</td>
      <td>M</td>
      <td>23.0</td>
      <td>195.0</td>
      <td>88.0</td>
      <td>Norway</td>
      <td>NOR</td>
      <td>1968 Summer</td>
      <td>1968</td>
      <td>Summer</td>
      <td>Mexico City</td>
      <td>Canoeing</td>
      <td>Canoeing Men's Kayak Fours, 1,000 metres</td>
      <td>Gold</td>
      <td>Norway</td>
      <td>NaN</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
    </tr>
    <tr>
      <th>6416</th>
      <td>4130</td>
      <td>Thorleif Steinar Andresen</td>
      <td>M</td>
      <td>23.0</td>
      <td>180.0</td>
      <td>75.0</td>
      <td>Norway</td>
      <td>NOR</td>
      <td>1968 Summer</td>
      <td>1968</td>
      <td>Summer</td>
      <td>Mexico City</td>
      <td>Cycling</td>
      <td>Cycling Men's Road Race, Individual</td>
      <td>NaN</td>
      <td>Norway</td>
      <td>NaN</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>6417</th>
      <td>4130</td>
      <td>Thorleif Steinar Andresen</td>
      <td>M</td>
      <td>23.0</td>
      <td>180.0</td>
      <td>75.0</td>
      <td>Norway</td>
      <td>NOR</td>
      <td>1968 Summer</td>
      <td>1968</td>
      <td>Summer</td>
      <td>Mexico City</td>
      <td>Cycling</td>
      <td>Cycling Men's 100 kilometres Team Time Trial</td>
      <td>NaN</td>
      <td>Norway</td>
      <td>NaN</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>6427</th>
      <td>4132</td>
      <td>rnulf Reidar Andresen</td>
      <td>M</td>
      <td>24.0</td>
      <td>183.0</td>
      <td>80.0</td>
      <td>Norway</td>
      <td>NOR</td>
      <td>1968 Summer</td>
      <td>1968</td>
      <td>Summer</td>
      <td>Mexico City</td>
      <td>Cycling</td>
      <td>Cycling Men's Road Race, Individual</td>
      <td>NaN</td>
      <td>Norway</td>
      <td>NaN</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>213009</th>
      <td>129893</td>
      <td>Kjellfred Weum</td>
      <td>M</td>
      <td>28.0</td>
      <td>186.0</td>
      <td>79.0</td>
      <td>Norway</td>
      <td>NOR</td>
      <td>1968 Summer</td>
      <td>1968</td>
      <td>Summer</td>
      <td>Mexico City</td>
      <td>Athletics</td>
      <td>Athletics Men's 110 metres Hurdles</td>
      <td>NaN</td>
      <td>Norway</td>
      <td>NaN</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>213705</th>
      <td>130273</td>
      <td>Kai Georg Wiese</td>
      <td>M</td>
      <td>28.0</td>
      <td>179.0</td>
      <td>75.0</td>
      <td>Norway</td>
      <td>NOR</td>
      <td>1968 Summer</td>
      <td>1968</td>
      <td>Summer</td>
      <td>Mexico City</td>
      <td>Sailing</td>
      <td>Sailing Mixed One Person Dinghy</td>
      <td>NaN</td>
      <td>Norway</td>
      <td>NaN</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>213839</th>
      <td>130333</td>
      <td>Erik Wiik-Hansen</td>
      <td>M</td>
      <td>34.0</td>
      <td>179.0</td>
      <td>87.0</td>
      <td>Norway</td>
      <td>NOR</td>
      <td>1968 Summer</td>
      <td>1968</td>
      <td>Summer</td>
      <td>Mexico City</td>
      <td>Sailing</td>
      <td>Sailing Mixed Three Person Keelboat</td>
      <td>NaN</td>
      <td>Norway</td>
      <td>NaN</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>213881</th>
      <td>130358</td>
      <td>Per Olav Wiken</td>
      <td>M</td>
      <td>31.0</td>
      <td>183.0</td>
      <td>80.0</td>
      <td>Norway</td>
      <td>NOR</td>
      <td>1968 Summer</td>
      <td>1968</td>
      <td>Summer</td>
      <td>Mexico City</td>
      <td>Sailing</td>
      <td>Sailing Mixed Two Person Keelboat</td>
      <td>Silver</td>
      <td>Norway</td>
      <td>NaN</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>218365</th>
      <td>133005</td>
      <td>Leif Bernhard Yli</td>
      <td>M</td>
      <td>26.0</td>
      <td>183.0</td>
      <td>82.0</td>
      <td>Norway</td>
      <td>NOR</td>
      <td>1968 Summer</td>
      <td>1968</td>
      <td>Summer</td>
      <td>Mexico City</td>
      <td>Cycling</td>
      <td>Cycling Men's 100 kilometres Team Time Trial</td>
      <td>NaN</td>
      <td>Norway</td>
      <td>NaN</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
  </tbody>
</table>
<p>86 rows × 20 columns</p>
</div>



## Overall Analysis


```python
df['Year'].unique().shape[0]-1
```




    28




```python
df['City'].unique()
```




    array(['Barcelona', 'London', 'Antwerpen', 'Paris', 'Los Angeles',
           'Helsinki', 'Sydney', 'Atlanta', 'Stockholm', 'Beijing',
           'Rio de Janeiro', 'Athina', 'Mexico City', 'Munich', 'Seoul',
           'Berlin', 'Melbourne', 'Roma', 'Amsterdam', 'Montreal', 'Moskva',
           'Tokyo', 'St. Louis'], dtype=object)




```python
df['Sport'].unique()
```




    array(['Basketball', 'Judo', 'Football', 'Tug-Of-War', 'Athletics',
           'Swimming', 'Badminton', 'Sailing', 'Gymnastics',
           'Art Competitions', 'Handball', 'Weightlifting', 'Wrestling',
           'Water Polo', 'Hockey', 'Rowing', 'Fencing', 'Equestrianism',
           'Shooting', 'Boxing', 'Taekwondo', 'Cycling', 'Diving', 'Canoeing',
           'Tennis', 'Modern Pentathlon', 'Golf', 'Softball', 'Archery',
           'Volleyball', 'Synchronized Swimming', 'Table Tennis', 'Baseball',
           'Rhythmic Gymnastics', 'Rugby Sevens', 'Trampolining',
           'Beach Volleyball', 'Triathlon', 'Rugby', 'Lacrosse', 'Polo',
           'Cricket', 'Ice Hockey', 'Racquets', 'Motorboating', 'Croquet',
           'Figure Skating', 'Jeu De Paume', 'Roque', 'Basque Pelota',
           'Alpinism', 'Aeronautics'], dtype=object)




```python
df['Event'].unique().shape
```




    (651,)




```python
df['Name'].unique().shape     # (athlete) name of players
```




    (116122,)




```python
df['region'].unique().shape[0]
```




    206




```python
nations_over_time = df.drop_duplicates(['Year', 'region'])['Year'].value_counts().reset_index().sort_values('index')
```


```python
nations_over_time.rename(columns={'index': 'Editions', 'Year': 'NO of countries'}, inplace=True)
```


```python
nations_over_time
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
      <th>Editions</th>
      <th>NO of countries</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>28</th>
      <td>1896</td>
      <td>12</td>
    </tr>
    <tr>
      <th>22</th>
      <td>1900</td>
      <td>31</td>
    </tr>
    <tr>
      <th>27</th>
      <td>1904</td>
      <td>14</td>
    </tr>
    <tr>
      <th>26</th>
      <td>1906</td>
      <td>20</td>
    </tr>
    <tr>
      <th>25</th>
      <td>1908</td>
      <td>22</td>
    </tr>
    <tr>
      <th>24</th>
      <td>1912</td>
      <td>29</td>
    </tr>
    <tr>
      <th>23</th>
      <td>1920</td>
      <td>29</td>
    </tr>
    <tr>
      <th>21</th>
      <td>1924</td>
      <td>45</td>
    </tr>
    <tr>
      <th>20</th>
      <td>1928</td>
      <td>46</td>
    </tr>
    <tr>
      <th>19</th>
      <td>1932</td>
      <td>47</td>
    </tr>
    <tr>
      <th>18</th>
      <td>1936</td>
      <td>49</td>
    </tr>
    <tr>
      <th>17</th>
      <td>1948</td>
      <td>59</td>
    </tr>
    <tr>
      <th>16</th>
      <td>1952</td>
      <td>67</td>
    </tr>
    <tr>
      <th>15</th>
      <td>1956</td>
      <td>71</td>
    </tr>
    <tr>
      <th>13</th>
      <td>1960</td>
      <td>83</td>
    </tr>
    <tr>
      <th>11</th>
      <td>1964</td>
      <td>93</td>
    </tr>
    <tr>
      <th>10</th>
      <td>1968</td>
      <td>111</td>
    </tr>
    <tr>
      <th>9</th>
      <td>1972</td>
      <td>120</td>
    </tr>
    <tr>
      <th>12</th>
      <td>1976</td>
      <td>91</td>
    </tr>
    <tr>
      <th>14</th>
      <td>1980</td>
      <td>80</td>
    </tr>
    <tr>
      <th>8</th>
      <td>1984</td>
      <td>139</td>
    </tr>
    <tr>
      <th>7</th>
      <td>1988</td>
      <td>156</td>
    </tr>
    <tr>
      <th>6</th>
      <td>1992</td>
      <td>168</td>
    </tr>
    <tr>
      <th>5</th>
      <td>1996</td>
      <td>196</td>
    </tr>
    <tr>
      <th>4</th>
      <td>2000</td>
      <td>199</td>
    </tr>
    <tr>
      <th>3</th>
      <td>2004</td>
      <td>200</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2008</td>
      <td>202</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2012</td>
      <td>203</td>
    </tr>
    <tr>
      <th>0</th>
      <td>2016</td>
      <td>204</td>
    </tr>
  </tbody>
</table>
</div>




```python
import plotly.express as pxd
import matplotlib.pylab as plt
```


```python
# fig = px.line(nations_over_time, x="Edition", y="NO of countries")
```


```python
df.drop_duplicates(['Year', 'Event'])['Year'].value_counts().reset_index().sort_values('index')
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
      <th>index</th>
      <th>Year</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>28</th>
      <td>1896</td>
      <td>43</td>
    </tr>
    <tr>
      <th>26</th>
      <td>1900</td>
      <td>90</td>
    </tr>
    <tr>
      <th>25</th>
      <td>1904</td>
      <td>95</td>
    </tr>
    <tr>
      <th>27</th>
      <td>1906</td>
      <td>74</td>
    </tr>
    <tr>
      <th>23</th>
      <td>1908</td>
      <td>109</td>
    </tr>
    <tr>
      <th>24</th>
      <td>1912</td>
      <td>107</td>
    </tr>
    <tr>
      <th>14</th>
      <td>1920</td>
      <td>158</td>
    </tr>
    <tr>
      <th>20</th>
      <td>1924</td>
      <td>131</td>
    </tr>
    <tr>
      <th>22</th>
      <td>1928</td>
      <td>122</td>
    </tr>
    <tr>
      <th>21</th>
      <td>1932</td>
      <td>131</td>
    </tr>
    <tr>
      <th>18</th>
      <td>1936</td>
      <td>150</td>
    </tr>
    <tr>
      <th>15</th>
      <td>1948</td>
      <td>153</td>
    </tr>
    <tr>
      <th>19</th>
      <td>1952</td>
      <td>149</td>
    </tr>
    <tr>
      <th>16</th>
      <td>1956</td>
      <td>151</td>
    </tr>
    <tr>
      <th>17</th>
      <td>1960</td>
      <td>150</td>
    </tr>
    <tr>
      <th>13</th>
      <td>1964</td>
      <td>163</td>
    </tr>
    <tr>
      <th>12</th>
      <td>1968</td>
      <td>172</td>
    </tr>
    <tr>
      <th>11</th>
      <td>1972</td>
      <td>193</td>
    </tr>
    <tr>
      <th>10</th>
      <td>1976</td>
      <td>198</td>
    </tr>
    <tr>
      <th>9</th>
      <td>1980</td>
      <td>203</td>
    </tr>
    <tr>
      <th>8</th>
      <td>1984</td>
      <td>221</td>
    </tr>
    <tr>
      <th>7</th>
      <td>1988</td>
      <td>237</td>
    </tr>
    <tr>
      <th>6</th>
      <td>1992</td>
      <td>257</td>
    </tr>
    <tr>
      <th>5</th>
      <td>1996</td>
      <td>271</td>
    </tr>
    <tr>
      <th>4</th>
      <td>2000</td>
      <td>300</td>
    </tr>
    <tr>
      <th>3</th>
      <td>2004</td>
      <td>301</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2008</td>
      <td>302</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2012</td>
      <td>302</td>
    </tr>
    <tr>
      <th>0</th>
      <td>2016</td>
      <td>306</td>
    </tr>
  </tbody>
</table>
</div>




```python
# import seaborn as sns
x = df.drop_duplicates(['Year','Sport','Event'])
```


```python
# x.pivot_table(index = 'Sport',columns='Year',values= 'Event',aggfunc='count').fillna(0).astype("int")

ax = sns.heatmap(x.pivot_table(index='Sport', columns='Year', values='Event', aggfunc='count').fillna(0).astype('int'),annot=True)
```


    
![png](output_48_0.png)
    



```python
df.dropna(subset=['Medal'])
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
      <th>.</th>
      <th>Name</th>
      <th>Sex</th>
      <th>Age</th>
      <th>Height</th>
      <th>Weight</th>
      <th>Team</th>
      <th>NOC</th>
      <th>Games</th>
      <th>Year</th>
      <th>Season</th>
      <th>City</th>
      <th>Sport</th>
      <th>Event</th>
      <th>Medal</th>
      <th>region</th>
      <th>notes</th>
      <th>Bronze</th>
      <th>Gold</th>
      <th>Silver</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>3</th>
      <td>4</td>
      <td>Edgar Lindenau Aabye</td>
      <td>M</td>
      <td>34.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>Denmark/Sweden</td>
      <td>DEN</td>
      <td>1900 Summer</td>
      <td>1900</td>
      <td>Summer</td>
      <td>Paris</td>
      <td>Tug-Of-War</td>
      <td>Tug-Of-War Men's Tug-Of-War</td>
      <td>Gold</td>
      <td>Denmark</td>
      <td>NaN</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
    </tr>
    <tr>
      <th>12</th>
      <td>15</td>
      <td>Arvo Ossian Aaltonen</td>
      <td>M</td>
      <td>30.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>Finland</td>
      <td>FIN</td>
      <td>1920 Summer</td>
      <td>1920</td>
      <td>Summer</td>
      <td>Antwerpen</td>
      <td>Swimming</td>
      <td>Swimming Men's 200 metres Breaststroke</td>
      <td>Bronze</td>
      <td>Finland</td>
      <td>NaN</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>13</th>
      <td>15</td>
      <td>Arvo Ossian Aaltonen</td>
      <td>M</td>
      <td>30.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>Finland</td>
      <td>FIN</td>
      <td>1920 Summer</td>
      <td>1920</td>
      <td>Summer</td>
      <td>Antwerpen</td>
      <td>Swimming</td>
      <td>Swimming Men's 400 metres Breaststroke</td>
      <td>Bronze</td>
      <td>Finland</td>
      <td>NaN</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>15</th>
      <td>17</td>
      <td>Paavo Johannes Aaltonen</td>
      <td>M</td>
      <td>28.0</td>
      <td>175.0</td>
      <td>64.0</td>
      <td>Finland</td>
      <td>FIN</td>
      <td>1948 Summer</td>
      <td>1948</td>
      <td>Summer</td>
      <td>London</td>
      <td>Gymnastics</td>
      <td>Gymnastics Men's Individual All-Around</td>
      <td>Bronze</td>
      <td>Finland</td>
      <td>NaN</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>16</th>
      <td>17</td>
      <td>Paavo Johannes Aaltonen</td>
      <td>M</td>
      <td>28.0</td>
      <td>175.0</td>
      <td>64.0</td>
      <td>Finland</td>
      <td>FIN</td>
      <td>1948 Summer</td>
      <td>1948</td>
      <td>Summer</td>
      <td>London</td>
      <td>Gymnastics</td>
      <td>Gymnastics Men's Team All-Around</td>
      <td>Gold</td>
      <td>Finland</td>
      <td>NaN</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>222528</th>
      <td>135553</td>
      <td>Galina Ivanovna Zybina (-Fyodorova)</td>
      <td>F</td>
      <td>25.0</td>
      <td>168.0</td>
      <td>80.0</td>
      <td>Soviet Union</td>
      <td>URS</td>
      <td>1956 Summer</td>
      <td>1956</td>
      <td>Summer</td>
      <td>Melbourne</td>
      <td>Athletics</td>
      <td>Athletics Women's Shot Put</td>
      <td>Silver</td>
      <td>Russia</td>
      <td>NaN</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>222530</th>
      <td>135553</td>
      <td>Galina Ivanovna Zybina (-Fyodorova)</td>
      <td>F</td>
      <td>33.0</td>
      <td>168.0</td>
      <td>80.0</td>
      <td>Soviet Union</td>
      <td>URS</td>
      <td>1964 Summer</td>
      <td>1964</td>
      <td>Summer</td>
      <td>Tokyo</td>
      <td>Athletics</td>
      <td>Athletics Women's Shot Put</td>
      <td>Bronze</td>
      <td>Russia</td>
      <td>NaN</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>222532</th>
      <td>135554</td>
      <td>Bogusaw Zych</td>
      <td>M</td>
      <td>28.0</td>
      <td>182.0</td>
      <td>82.0</td>
      <td>Poland</td>
      <td>POL</td>
      <td>1980 Summer</td>
      <td>1980</td>
      <td>Summer</td>
      <td>Moskva</td>
      <td>Fencing</td>
      <td>Fencing Men's Foil, Team</td>
      <td>Bronze</td>
      <td>Poland</td>
      <td>NaN</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>222544</th>
      <td>135563</td>
      <td>Olesya Nikolayevna Zykina</td>
      <td>F</td>
      <td>19.0</td>
      <td>171.0</td>
      <td>64.0</td>
      <td>Russia</td>
      <td>RUS</td>
      <td>2000 Summer</td>
      <td>2000</td>
      <td>Summer</td>
      <td>Sydney</td>
      <td>Athletics</td>
      <td>Athletics Women's 4 x 400 metres Relay</td>
      <td>Bronze</td>
      <td>Russia</td>
      <td>NaN</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>222545</th>
      <td>135563</td>
      <td>Olesya Nikolayevna Zykina</td>
      <td>F</td>
      <td>23.0</td>
      <td>171.0</td>
      <td>64.0</td>
      <td>Russia</td>
      <td>RUS</td>
      <td>2004 Summer</td>
      <td>2004</td>
      <td>Summer</td>
      <td>Athina</td>
      <td>Athletics</td>
      <td>Athletics Women's 4 x 400 metres Relay</td>
      <td>Silver</td>
      <td>Russia</td>
      <td>NaN</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
<p>34077 rows × 20 columns</p>
</div>




```python
# def mostsuccessful(df,sport):
#     temp_df = df.dropna(subset=['Medal'])
    
#     if sport != 'Overall':
#         temp_df = temp_df[temp_df['Sport']==sport]
        
        
#     x= temp_df['Name'].value_counts().reset_index()
#     return x
```


```python
# mostsuccessful(df,'Overall')
```


```python
def mostsuccessful(df,sport):
    temp_df = df.dropna(subset=['Medal'])
    
    if sport != 'Overall':
        temp_df = temp_df[temp_df['Sport']==sport]
        
        
    x= temp_df['Name'].value_counts().reset_index().head(15).merge(df,left_on='index',right_on='Name',how='left')[['index','Name_x','Sport','region']].drop_duplicates('index')
    x.rename(columns={'index':'Name','Name_x':'Medals'},inplace=True)
    
    return x
```


```python
mostsuccessful(df,'Overall')
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
      <th>Name</th>
      <th>Medals</th>
      <th>Sport</th>
      <th>region</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Michael Fred Phelps, II</td>
      <td>28</td>
      <td>Swimming</td>
      <td>USA</td>
    </tr>
    <tr>
      <th>30</th>
      <td>Larysa Semenivna Latynina (Diriy-)</td>
      <td>18</td>
      <td>Gymnastics</td>
      <td>Russia</td>
    </tr>
    <tr>
      <th>49</th>
      <td>Nikolay Yefimovich Andrianov</td>
      <td>15</td>
      <td>Gymnastics</td>
      <td>Russia</td>
    </tr>
    <tr>
      <th>73</th>
      <td>Borys Anfiyanovych Shakhlin</td>
      <td>13</td>
      <td>Gymnastics</td>
      <td>Russia</td>
    </tr>
    <tr>
      <th>97</th>
      <td>Takashi Ono</td>
      <td>13</td>
      <td>Gymnastics</td>
      <td>Japan</td>
    </tr>
    <tr>
      <th>130</th>
      <td>Edoardo Mangiarotti</td>
      <td>13</td>
      <td>Fencing</td>
      <td>Italy</td>
    </tr>
    <tr>
      <th>144</th>
      <td>Dara Grace Torres (-Hoffman, -Minas)</td>
      <td>12</td>
      <td>Swimming</td>
      <td>USA</td>
    </tr>
    <tr>
      <th>157</th>
      <td>Aleksey Yuryevich Nemov</td>
      <td>12</td>
      <td>Gymnastics</td>
      <td>Russia</td>
    </tr>
    <tr>
      <th>178</th>
      <td>Jennifer Elisabeth "Jenny" Thompson (-Cumpelik)</td>
      <td>12</td>
      <td>Swimming</td>
      <td>USA</td>
    </tr>
    <tr>
      <th>195</th>
      <td>Birgit Fischer-Schmidt</td>
      <td>12</td>
      <td>Canoeing</td>
      <td>Germany</td>
    </tr>
    <tr>
      <th>208</th>
      <td>Ryan Steven Lochte</td>
      <td>12</td>
      <td>Swimming</td>
      <td>USA</td>
    </tr>
    <tr>
      <th>222</th>
      <td>Paavo Johannes Nurmi</td>
      <td>12</td>
      <td>Athletics</td>
      <td>Finland</td>
    </tr>
    <tr>
      <th>234</th>
      <td>Sawao Kato</td>
      <td>12</td>
      <td>Gymnastics</td>
      <td>Japan</td>
    </tr>
    <tr>
      <th>258</th>
      <td>Natalie Anne Coughlin (-Hall)</td>
      <td>12</td>
      <td>Swimming</td>
      <td>USA</td>
    </tr>
    <tr>
      <th>270</th>
      <td>Matthew Nicholas "Matt" Biondi</td>
      <td>11</td>
      <td>Swimming</td>
      <td>USA</td>
    </tr>
  </tbody>
</table>
</div>



## country wise analysis


```python
temp_df = df.dropna(subset=["Medal"])
temp_df.drop_duplicates(subset=['Team','region','Games','Year','City','Sport','Event','Medal'],inplace=True)
```

    c:\users\lenovo\appdata\local\programs\python\python39\lib\site-packages\pandas\util\_decorators.py:311: SettingWithCopyWarning:
    
    
    A value is trying to be set on a copy of a slice from a DataFrame
    
    See the caveats in the documentation: https://pandas.pydata.org/pandas-docs/stable/user_guide/indexing.html#returning-a-view-versus-a-copy
    
    


```python
new_df = temp_df[temp_df['region']=='USA']
final_df = new_df.groupby('Year').count()["Medal"].reset_index()

```


```python
final_df
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
      <th>Medal</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1896</td>
      <td>19</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1900</td>
      <td>54</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1904</td>
      <td>231</td>
    </tr>
    <tr>
      <th>3</th>
      <td>1906</td>
      <td>23</td>
    </tr>
    <tr>
      <th>4</th>
      <td>1908</td>
      <td>46</td>
    </tr>
    <tr>
      <th>5</th>
      <td>1912</td>
      <td>63</td>
    </tr>
    <tr>
      <th>6</th>
      <td>1920</td>
      <td>95</td>
    </tr>
    <tr>
      <th>7</th>
      <td>1924</td>
      <td>99</td>
    </tr>
    <tr>
      <th>8</th>
      <td>1928</td>
      <td>56</td>
    </tr>
    <tr>
      <th>9</th>
      <td>1932</td>
      <td>110</td>
    </tr>
    <tr>
      <th>10</th>
      <td>1936</td>
      <td>57</td>
    </tr>
    <tr>
      <th>11</th>
      <td>1948</td>
      <td>84</td>
    </tr>
    <tr>
      <th>12</th>
      <td>1952</td>
      <td>76</td>
    </tr>
    <tr>
      <th>13</th>
      <td>1956</td>
      <td>74</td>
    </tr>
    <tr>
      <th>14</th>
      <td>1960</td>
      <td>71</td>
    </tr>
    <tr>
      <th>15</th>
      <td>1964</td>
      <td>90</td>
    </tr>
    <tr>
      <th>16</th>
      <td>1968</td>
      <td>107</td>
    </tr>
    <tr>
      <th>17</th>
      <td>1972</td>
      <td>94</td>
    </tr>
    <tr>
      <th>18</th>
      <td>1976</td>
      <td>94</td>
    </tr>
    <tr>
      <th>19</th>
      <td>1984</td>
      <td>173</td>
    </tr>
    <tr>
      <th>20</th>
      <td>1988</td>
      <td>94</td>
    </tr>
    <tr>
      <th>21</th>
      <td>1992</td>
      <td>108</td>
    </tr>
    <tr>
      <th>22</th>
      <td>1996</td>
      <td>101</td>
    </tr>
    <tr>
      <th>23</th>
      <td>2000</td>
      <td>91</td>
    </tr>
    <tr>
      <th>24</th>
      <td>2004</td>
      <td>101</td>
    </tr>
    <tr>
      <th>25</th>
      <td>2008</td>
      <td>110</td>
    </tr>
    <tr>
      <th>26</th>
      <td>2012</td>
      <td>103</td>
    </tr>
    <tr>
      <th>27</th>
      <td>2016</td>
      <td>121</td>
    </tr>
  </tbody>
</table>
</div>




```python
fig = px.line(final_df,x='Year',y='Medal')
fig.show()
```


<div>                            <div id="fe34534c-803c-4578-9b21-8cabf427d44d" class="plotly-graph-div" style="height:525px; width:100%;"></div>            <script type="text/javascript">                require(["plotly"], function(Plotly) {                    window.PLOTLYENV=window.PLOTLYENV || {};                                    if (document.getElementById("fe34534c-803c-4578-9b21-8cabf427d44d")) {                    Plotly.newPlot(                        "fe34534c-803c-4578-9b21-8cabf427d44d",                        [{"hovertemplate":"Year=%{x}<br>Medal=%{y}<extra></extra>","legendgroup":"","line":{"color":"#636efa","dash":"solid"},"marker":{"symbol":"circle"},"mode":"lines","name":"","orientation":"v","showlegend":false,"type":"scatter","x":[1896,1900,1904,1906,1908,1912,1920,1924,1928,1932,1936,1948,1952,1956,1960,1964,1968,1972,1976,1984,1988,1992,1996,2000,2004,2008,2012,2016],"xaxis":"x","y":[19,54,231,23,46,63,95,99,56,110,57,84,76,74,71,90,107,94,94,173,94,108,101,91,101,110,103,121],"yaxis":"y"}],                        {"legend":{"tracegroupgap":0},"margin":{"t":60},"template":{"data":{"bar":[{"error_x":{"color":"#2a3f5f"},"error_y":{"color":"#2a3f5f"},"marker":{"line":{"color":"#E5ECF6","width":0.5},"pattern":{"fillmode":"overlay","size":10,"solidity":0.2}},"type":"bar"}],"barpolar":[{"marker":{"line":{"color":"#E5ECF6","width":0.5},"pattern":{"fillmode":"overlay","size":10,"solidity":0.2}},"type":"barpolar"}],"carpet":[{"aaxis":{"endlinecolor":"#2a3f5f","gridcolor":"white","linecolor":"white","minorgridcolor":"white","startlinecolor":"#2a3f5f"},"baxis":{"endlinecolor":"#2a3f5f","gridcolor":"white","linecolor":"white","minorgridcolor":"white","startlinecolor":"#2a3f5f"},"type":"carpet"}],"choropleth":[{"colorbar":{"outlinewidth":0,"ticks":""},"type":"choropleth"}],"contour":[{"colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]],"type":"contour"}],"contourcarpet":[{"colorbar":{"outlinewidth":0,"ticks":""},"type":"contourcarpet"}],"heatmap":[{"colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]],"type":"heatmap"}],"heatmapgl":[{"colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]],"type":"heatmapgl"}],"histogram":[{"marker":{"pattern":{"fillmode":"overlay","size":10,"solidity":0.2}},"type":"histogram"}],"histogram2d":[{"colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]],"type":"histogram2d"}],"histogram2dcontour":[{"colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]],"type":"histogram2dcontour"}],"mesh3d":[{"colorbar":{"outlinewidth":0,"ticks":""},"type":"mesh3d"}],"parcoords":[{"line":{"colorbar":{"outlinewidth":0,"ticks":""}},"type":"parcoords"}],"pie":[{"automargin":true,"type":"pie"}],"scatter":[{"marker":{"colorbar":{"outlinewidth":0,"ticks":""}},"type":"scatter"}],"scatter3d":[{"line":{"colorbar":{"outlinewidth":0,"ticks":""}},"marker":{"colorbar":{"outlinewidth":0,"ticks":""}},"type":"scatter3d"}],"scattercarpet":[{"marker":{"colorbar":{"outlinewidth":0,"ticks":""}},"type":"scattercarpet"}],"scattergeo":[{"marker":{"colorbar":{"outlinewidth":0,"ticks":""}},"type":"scattergeo"}],"scattergl":[{"marker":{"colorbar":{"outlinewidth":0,"ticks":""}},"type":"scattergl"}],"scattermapbox":[{"marker":{"colorbar":{"outlinewidth":0,"ticks":""}},"type":"scattermapbox"}],"scatterpolar":[{"marker":{"colorbar":{"outlinewidth":0,"ticks":""}},"type":"scatterpolar"}],"scatterpolargl":[{"marker":{"colorbar":{"outlinewidth":0,"ticks":""}},"type":"scatterpolargl"}],"scatterternary":[{"marker":{"colorbar":{"outlinewidth":0,"ticks":""}},"type":"scatterternary"}],"surface":[{"colorbar":{"outlinewidth":0,"ticks":""},"colorscale":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]],"type":"surface"}],"table":[{"cells":{"fill":{"color":"#EBF0F8"},"line":{"color":"white"}},"header":{"fill":{"color":"#C8D4E3"},"line":{"color":"white"}},"type":"table"}]},"layout":{"annotationdefaults":{"arrowcolor":"#2a3f5f","arrowhead":0,"arrowwidth":1},"autotypenumbers":"strict","coloraxis":{"colorbar":{"outlinewidth":0,"ticks":""}},"colorscale":{"diverging":[[0,"#8e0152"],[0.1,"#c51b7d"],[0.2,"#de77ae"],[0.3,"#f1b6da"],[0.4,"#fde0ef"],[0.5,"#f7f7f7"],[0.6,"#e6f5d0"],[0.7,"#b8e186"],[0.8,"#7fbc41"],[0.9,"#4d9221"],[1,"#276419"]],"sequential":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]],"sequentialminus":[[0.0,"#0d0887"],[0.1111111111111111,"#46039f"],[0.2222222222222222,"#7201a8"],[0.3333333333333333,"#9c179e"],[0.4444444444444444,"#bd3786"],[0.5555555555555556,"#d8576b"],[0.6666666666666666,"#ed7953"],[0.7777777777777778,"#fb9f3a"],[0.8888888888888888,"#fdca26"],[1.0,"#f0f921"]]},"colorway":["#636efa","#EF553B","#00cc96","#ab63fa","#FFA15A","#19d3f3","#FF6692","#B6E880","#FF97FF","#FECB52"],"font":{"color":"#2a3f5f"},"geo":{"bgcolor":"white","lakecolor":"white","landcolor":"#E5ECF6","showlakes":true,"showland":true,"subunitcolor":"white"},"hoverlabel":{"align":"left"},"hovermode":"closest","mapbox":{"style":"light"},"paper_bgcolor":"white","plot_bgcolor":"#E5ECF6","polar":{"angularaxis":{"gridcolor":"white","linecolor":"white","ticks":""},"bgcolor":"#E5ECF6","radialaxis":{"gridcolor":"white","linecolor":"white","ticks":""}},"scene":{"xaxis":{"backgroundcolor":"#E5ECF6","gridcolor":"white","gridwidth":2,"linecolor":"white","showbackground":true,"ticks":"","zerolinecolor":"white"},"yaxis":{"backgroundcolor":"#E5ECF6","gridcolor":"white","gridwidth":2,"linecolor":"white","showbackground":true,"ticks":"","zerolinecolor":"white"},"zaxis":{"backgroundcolor":"#E5ECF6","gridcolor":"white","gridwidth":2,"linecolor":"white","showbackground":true,"ticks":"","zerolinecolor":"white"}},"shapedefaults":{"line":{"color":"#2a3f5f"}},"ternary":{"aaxis":{"gridcolor":"white","linecolor":"white","ticks":""},"baxis":{"gridcolor":"white","linecolor":"white","ticks":""},"bgcolor":"#E5ECF6","caxis":{"gridcolor":"white","linecolor":"white","ticks":""}},"title":{"x":0.05},"xaxis":{"automargin":true,"gridcolor":"white","linecolor":"white","ticks":"","title":{"standoff":15},"zerolinecolor":"white","zerolinewidth":2},"yaxis":{"automargin":true,"gridcolor":"white","linecolor":"white","ticks":"","title":{"standoff":15},"zerolinecolor":"white","zerolinewidth":2}}},"xaxis":{"anchor":"y","domain":[0.0,1.0],"title":{"text":"Year"}},"yaxis":{"anchor":"x","domain":[0.0,1.0],"title":{"text":"Medal"}}},                        {"responsive": true}                    ).then(function(){

var gd = document.getElementById('fe34534c-803c-4578-9b21-8cabf427d44d');
var x = new MutationObserver(function (mutations, observer) {{
        var display = window.getComputedStyle(gd).display;
        if (!display || display === 'none') {{
            console.log([gd, 'removed!']);
            Plotly.purge(gd);
            observer.disconnect();
        }}
}});

// Listen for the removal of the full notebook cells
var notebookContainer = gd.closest('#notebook-container');
if (notebookContainer) {{
    x.observe(notebookContainer, {childList: true});
}}

// Listen for the clearing of the current output cell
var outputEl = gd.closest('.output');
if (outputEl) {{
    x.observe(outputEl, {childList: true});
}}

                        })                };                });            </script>        </div>



```python
temp_df = df.dropna(subset=["Medal"])
temp_df.drop_duplicates(subset=['Team','region','Games','Year','City','Sport','Event','Medal'],inplace=True)
```

    c:\users\lenovo\appdata\local\programs\python\python39\lib\site-packages\pandas\util\_decorators.py:311: SettingWithCopyWarning:
    
    
    A value is trying to be set on a copy of a slice from a DataFrame
    
    See the caveats in the documentation: https://pandas.pydata.org/pandas-docs/stable/user_guide/indexing.html#returning-a-view-versus-a-copy
    
    


```python
new_df = temp_df[temp_df['region']=='USA']
plt.figure(figsize=(20,20))
sns.heatmap(new_df.pivot_table(index='Sport',columns='Year',values='Medal',aggfunc='count').fillna(0).astype('int'),annot=True)
```




    <AxesSubplot:xlabel='Year', ylabel='Sport'>




    
![png](output_60_1.png)
    



```python
def mostsuccessful(df,country):
    temp_df = df.dropna(subset=['Medal'])

    temp_df = temp_df[temp_df['region']==country]
              
    x= temp_df['Name'].value_counts().reset_index().head(15).merge(df,left_on='index',right_on='Name',how='left')[['index','Name_x','Sport']].drop_duplicates('index')
    x.rename(columns={'index':'Name','Name_x':'Medals'},inplace=True)
    
    return x
```


```python
mostsuccessful(df,'USA')
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
      <th>Name</th>
      <th>Medals</th>
      <th>Sport</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Michael Fred Phelps, II</td>
      <td>28</td>
      <td>Swimming</td>
    </tr>
    <tr>
      <th>30</th>
      <td>Ryan Steven Lochte</td>
      <td>12</td>
      <td>Swimming</td>
    </tr>
    <tr>
      <th>44</th>
      <td>Jennifer Elisabeth "Jenny" Thompson (-Cumpelik)</td>
      <td>12</td>
      <td>Swimming</td>
    </tr>
    <tr>
      <th>61</th>
      <td>Natalie Anne Coughlin (-Hall)</td>
      <td>12</td>
      <td>Swimming</td>
    </tr>
    <tr>
      <th>73</th>
      <td>Dara Grace Torres (-Hoffman, -Minas)</td>
      <td>12</td>
      <td>Swimming</td>
    </tr>
    <tr>
      <th>86</th>
      <td>Matthew Nicholas "Matt" Biondi</td>
      <td>11</td>
      <td>Swimming</td>
    </tr>
    <tr>
      <th>98</th>
      <td>Carl Townsend Osburn</td>
      <td>11</td>
      <td>Shooting</td>
    </tr>
    <tr>
      <th>114</th>
      <td>Mark Andrew Spitz</td>
      <td>11</td>
      <td>Swimming</td>
    </tr>
    <tr>
      <th>126</th>
      <td>Raymond Clarence "Ray" Ewry</td>
      <td>10</td>
      <td>Athletics</td>
    </tr>
    <tr>
      <th>136</th>
      <td>Frederick Carlton "Carl" Lewis</td>
      <td>10</td>
      <td>Athletics</td>
    </tr>
    <tr>
      <th>146</th>
      <td>Gary Wayne Hall, Jr.</td>
      <td>10</td>
      <td>Swimming</td>
    </tr>
    <tr>
      <th>156</th>
      <td>Allyson Michelle Felix</td>
      <td>9</td>
      <td>Athletics</td>
    </tr>
    <tr>
      <th>166</th>
      <td>Martin Joseph Sheridan</td>
      <td>9</td>
      <td>Athletics</td>
    </tr>
    <tr>
      <th>181</th>
      <td>Shirley Frances Babashoff</td>
      <td>9</td>
      <td>Swimming</td>
    </tr>
    <tr>
      <th>192</th>
      <td>Nathan Ghar-Jun Adrian</td>
      <td>8</td>
      <td>Swimming</td>
    </tr>
  </tbody>
</table>
</div>




```python

```
