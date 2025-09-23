# EXPERIMENT-4 | JEGO MARCO E. GODOY | 2ECE-A  

---

## ****************** Experiment Overview 🔍 ******************

The use of data visualization and data wrangling is the main topic of Experiment 4.  
The purpose of this experiment is to recognize and use various codes and functions when developing a Python application with Data Wrangling and Visualization modules.  

This experiment comprises only 1 problem:

1. **ECE BOARD EXAM PROBLEM**  
   - I used the file **"board2.csv"** and uploaded its data into a dataframe using pandas.  
   - Performed **Data Wrangling** and **Visualization** techniques.  

---

## ********************* Coding Process ✏️ *********************

### Problem 1  

➡️ **Step 1:** Upload the data of the `board2.csv` file into the dataframe `df`.  

```python
import pandas as pd
df = pd.read_csv('board2.csv')
df
```

➡️ Step 2: Create two dataframes with different parameters:

(a.) DataFrame: Instru

Constants:

  Track = "Instrumentation"

  Hometown = "Luzon"

Displayed Variables: Name, GEAS, Electronics

```# For 1a
constant_H = 'Luzon'
constant_T = 'Instrumentation'

Instru = df.loc[(df['Electronics'] > 70) 
                & (df['Track'] == constant_T) 
                & (df['Hometown'] == constant_H),
                ['Name', 'GEAS', 'Electronics']]
Instru
```

(b.) DataFrame: Mindy

Constants:

Gender = "Female"

Hometown = "Mindanao"

Displayed Variables: Name, Track, Electronics, Average

```# For 1b
const_H = 'Mindanao'
const_G = 'Female'

# Create the "Average" column
df['Average'] = df[['Electronics', 'GEAS', 'Math', 'Communication']].mean(axis=1)

# Filter DataFrame
Mindy = df.loc[(df['Average'] >= 55) 
               & (df['Hometown'] == const_H) 
               & (df['Gender'] == const_G),
               ['Name', 'Track', 'Electronics']]
Mindy
```

Problem 2

➡️ Using the dataframe df from Problem 1, I generated a bar graph showing the relation of the features to the average obtained by the students.

```import matplotlib.pyplot as plt

fig, axes = plt.subplots(1, 3, figsize=(20, 4), sharey=True)

# For Gender
axes[0].bar(df['Gender'], df['Average'], color='pink')
axes[0].set_title('Average by Gender')
axes[0].set_xlabel('Gender')
axes[0].set_ylabel('Average')

# For Track
axes[1].bar(df['Track'], df['Average'], color='purple')
axes[1].set_title('Average by Track')
axes[1].set_xlabel('Track')

# For Hometown
axes[2].bar(df['Hometown'], df['Average'], color='teal')
axes[2].set_title('Average by Hometown')
axes[2].set_xlabel('Hometown')

plt.show()
```

********************* Conclusion 🤓 *********************

From the generated results, the bar graphs demonstrate:

Gender: Female students achieved higher averages.

Track: Students who selected Microelectronics had a higher average.

Hometown: Luzon residents had a higher average.

Therefore, track, gender, and hometown all contribute to better average scores.

********************* End 🏁 *********************

End of Experiment 4
Thank you! 🙌
