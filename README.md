# Project Discription
Tha data is about Nationalities of motorcycle owners of the city of Barcelona at 2014
Dataset authored and provided by Ayuntamiento de Barcelona
Data set will not be updated anymore and the last updated date is Mar 13, 2013
## Data Description
Below is the discription for the headline of the variales
|        Header         |   Description  | Data type |
| --------------------- | -------------- | ----------|
|          Any          |     Year       |   number  |
|     Codi_Districte    |District Number |   number  |
|     Nom_Districte     | District Name  |    text   |
|       codi_Barri      |  Owner Number  |   number  |
|       Nom_Barri       |   Owner Name   |    text   |
|Nacionalitat_propietari|   Natonality   |    text   |
|      Nombre_motos     |   Moter Name   |   number  |
## Code Appling and Explaination
### Import Pandas
import pandas as pd
### Change Display Settings
pd.options.display.max_rows = 200
### Get Data
motor_df = pd.read_csv('2014_Nacionalitat_propietaris_motos-1.csv', delimiter=",", encoding='utf-8')
### Random Check Overview
- motor_df.sample(10)
- motor_df.info()
### Deeper Expansion
- motor_df.hist(figsize=(10,10)) >_Make a histogram of the DataFrame_
- motor_df.describe(include='all') > _Generate descriptive statistics for all the columns in the data_
- motor_df = motor_df.drop(motor_df[motor_df['Nombre_motos'] < 1000].index) > _Drop owners with less than 1000 motorcycles_
- motor_df.sort_values(by='Nombre_motos', ascending=False).head(20) > _Sort the DataFrame from the owner who has the most number of motorcycles to the owners who has the least number of motorcycles. Then examine the first 20 rows_
- motor_df.groupby(by=['Codi_Districte', 'Nom_Districte'])['Nombre_motos'].sum() > _Group by District Number AND District Name,and calculate the sum total motorcycles for every district.
- District_num=motor_df.groupby(by=['Codi_Districte', 'Nom_Districte'])['Nombre_motos'].sum()
- District_num.plot(kind='bar') > _Make a bar chart of District_num_
