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

Explanation:

-import pandas as pd → loads the Pandas library.

-pd.read_csv('board2.csv') → reads the CSV file into a DataFrame (table-like structure).

-df → displays the dataset.

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

Explanation:

-constant_H and constant_T store the fixed values Luzon and Instrumentation.

-df.loc[condition, columns] → selects rows that match the condition and only shows chosen columns.

-(df['Electronics'] > 70) → students with Electronics > 70.

-(df['Track'] == constant_T) → students in Instrumentation track.

-(df['Hometown'] == constant_H) → students from Luzon.

-['Name', 'GEAS', 'Electronics'] → only show these 3 columns.

-Result → A filtered DataFrame showing Luzon Instrumentation students with Electronics > 70.

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

Explanation:

-df[['Electronics', 'GEAS', 'Math', 'Communication']].mean(axis=1) → computes the average score per student.

-df['Average'] = ... → adds a new column Average.

-(df['Average'] >= 55) → only students with average ≥ 55.

-(df['Hometown'] == const_H) → only students from Mindanao.

-(df['Gender'] == const_G) → only female students.

-['Name', 'Track', 'Electronics', 'Average'] → only show these columns.

-Result → A DataFrame showing female Mindanao students with an average ≥ 55.

Problem 2
-
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

Explanation:

-import matplotlib.pyplot as plt → imports Matplotlib for plotting.

-plt.subplots(1, 3, figsize=(20, 4), sharey=True) → creates a figure with 3 charts side by side, all sharing the same y-axis.

-axes[0].bar(...) → creates a bar graph.

-df['Gender'] → x-axis (Male/Female).

-df['Average'] → y-axis (average scores).

-Titles and labels make the chart clear.

-df['Track'] → x-axis (different tracks like Microelectronics, Instrumentation).

-df['Average'] → y-axis.

-Purple color used for the bars.

-df['Hometown'] → x-axis (Luzon, Visayas, Mindanao).

-df['Average'] → y-axis.

-Teal color used for the bars.

-plt.show() → displays all 3 charts together.

********************* Conclusion 🤓 *********************
-
From the generated results, the bar graphs demonstrate:

Gender: Female students achieved higher averages.

Track: Students who selected Microelectronics had a higher average.

Hometown: Luzon residents had a higher average.

Therefore, track, gender, and hometown all contribute to better average scores.

********************* End 🏁 *********************
-
End of Experiment 4
-
Thank you! 🙌
-
