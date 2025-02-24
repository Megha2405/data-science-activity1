# data-science-activity1
Write a Python program to select the 'name' and 'score' columns from the following DataFrame.

   Sample DataFrame:


          exam_data = {'name': ['Anastasia', 'Dima', 'Katherine', 'James', 'Emily', 'Michael', 'Matthew', 'Laura', 'Kevin', 'Jonas'],

           'score': [12.5, 9, 16.5, np.nan, 9, 20, 14.5, np.nan, 8, 19],

          'attempts': [1, 3, 4, 3, 5, 3, 6, 1, 7, 1] }

[ ]
import numpy as np
import pandas as pd
exam_data = {'name': ['Anastasia', 'Dima', 'Katherine', 'James', 'Emily', 'Michael', 'Matthew', 'Laura', 'Kevin', 'Jonas'],
             'score': [12.5, 9, 16.5, np.nan, 9, 20, 14.5, np.nan, 8, 19],
             'attempts': [1, 3, 4, 3, 5, 3, 6, 1, 7, 1]}
df=pd.DataFrame(exam_data)
result=df[['name','score']]
print(result)
        name  score
0  Anastasia   12.5
1       Dima    9.0
2  Katherine   16.5
3      James    NaN
4      Emily    9.0
5    Michael   20.0
6    Matthew   14.5
7      Laura    NaN
8      Kevin    8.0
9      Jonas   19.0
For the above dataframe, Write a program to select the data who's attempt is greater than 3.


[ ]
import numpy as np
import pandas as pd
exam_data = {'name': ['Anastasia', 'Dima', 'Katherine', 'James', 'Emily', 'Michael', 'Matthew', 'Laura', 'Kevin', 'Jonas'],
             'score': [12.5, 9, 16.5, np.nan, 9, 20, 14.5, np.nan, 8, 19],
             'attempts': [1, 3, 4, 3, 5, 3, 6, 1, 7, 1]}
df=pd.DataFrame(exam_data)
result=df[(df['attempts']>3)]
print(result)


        name  score  attempts
2  Katherine   16.5         4
4      Emily    9.0         5
6    Matthew   14.5         6
8      Kevin    8.0         7
Write python code for indexing rows and columns based on the following conditions:

Assume we have the following dataframe:

data = {'name': ['Alice', 'Bob', 'Charlie', 'Dave'],

    'age': [25, 35, 40, 28],

    'gender': ['F', 'M', 'M', 'M'],

    'salary': [50000, 70000, 60000, 80000]}
df = pd.DataFrame(data)

a. Select rows where age is greater than 30:

b. Select rows where name contains 'e':

c. Select rows where gender is 'M' and salary is greater than 65000:

d. Select columns 'name' and 'age'


[ ]
import pandas as pd
import numpy as np
data = {'name': ['Alice', 'Bob', 'Charlie', 'Dave'],

        'age': [25, 35, 40, 28],

        'gender': ['F', 'M', 'M', 'M'],

        'salary': [50000, 70000, 60000, 80000]}
df=pd.DataFrame(data)
print("where age is greater than 30")
greater_than_30=df[df['age']>30]
print(greater_than_30)
print("where name contains'e")
contains_E=df[df['name'].str.contains('e')]
print(contains_E)
print("where gender is 'M' and salary is greater than 65000")
c=df[(df['gender']=='M')&(df['salary']>65000)]
print(c)
print("select the columns name and age")
d=df[['name','age']]
print(d)


where age is greater than 30
      name  age gender  salary
1      Bob   35      M   70000
2  Charlie   40      M   60000
where name contains'e
      name  age gender  salary
0    Alice   25      F   50000
2  Charlie   40      M   60000
3     Dave   28      M   80000
where gender is 'M' and salary is greater than 65000
   name  age gender  salary
1   Bob   35      M   70000
3  Dave   28      M   80000
select the columns name and age
      name  age
0    Alice   25
1      Bob   35
2  Charlie   40
3     Dave   28
ACTIVITY 2:

Write python code for indexing rows and columns using iloc or loc method based on the following conditions:
a. select the rows where clients with primary education have subscribed to a deposit?

b. select the rows where clients who have not subscribed to a deposit?

c. select the rows where clients who have subscribed to a deposit either have a housing or a personal loan?

d. select the rows where clients with secondary education who have not subscribed to a deposit?

e. select the rows where clients who have subscribed to a term deposit as an outcome of the successful marketing campaign?

f. select the rows where unemployed clients who have not subscribed to deposit?

e. Select columns 'education' and 'blanance' where age is less than or equal to 30


[ ]
import pandas as pd
df=pd.read_csv("/content/bank_train.csv")
df[(df['education']=='primary')&(df['deposit']=='yes')]


[ ]
df[(df['deposit']=='no')]


[ ]
df[(df['deposit']=='yes') & ((df['housing']=='yes')| (df['loan']=='yes'))]


[ ]
df[(df['education']=='primary')&(df['deposit']=='no')]


[ ]
df[(df['education']=='secondary')&(df['deposit']=='yes')]


[ ]
df[(df['deposit']=='yes')&((df['campaign']>3))]


[ ]
df[(df['job']=='unemployed')&(df['deposit']=='no')]


[ ]
df[['education','balance']]

