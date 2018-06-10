# PySchoolDistrict_PandaHW


```python
import pandas as pd
import numpy as np
```


```python
studentsfile = "Desktop/NumPyHW/students_complete.csv"
schoolsfile ="Desktop/NumPyHW/schools_complete.csv"
```


```python
students_df = pd.read_csv(studentsfile, encoding = "UTF-8")
schools_df = pd.read_csv(schoolsfile, encoding = "UTF-8")
```


```python
students_df.columns
students_df.head()
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
      <th>Student ID</th>
      <th>name</th>
      <th>gender</th>
      <th>grade</th>
      <th>school</th>
      <th>reading_score</th>
      <th>math_score</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>0</td>
      <td>Paul Bradley</td>
      <td>M</td>
      <td>9th</td>
      <td>Huang High School</td>
      <td>66</td>
      <td>79</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1</td>
      <td>Victor Smith</td>
      <td>M</td>
      <td>12th</td>
      <td>Huang High School</td>
      <td>94</td>
      <td>61</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2</td>
      <td>Kevin Rodriguez</td>
      <td>M</td>
      <td>12th</td>
      <td>Huang High School</td>
      <td>90</td>
      <td>60</td>
    </tr>
    <tr>
      <th>3</th>
      <td>3</td>
      <td>Dr. Richard Scott</td>
      <td>M</td>
      <td>12th</td>
      <td>Huang High School</td>
      <td>67</td>
      <td>58</td>
    </tr>
    <tr>
      <th>4</th>
      <td>4</td>
      <td>Bonnie Ray</td>
      <td>F</td>
      <td>9th</td>
      <td>Huang High School</td>
      <td>97</td>
      <td>84</td>
    </tr>
  </tbody>
</table>
</div>




```python
schools_df.columns
schools_df.head()
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
      <th>School ID</th>
      <th>name</th>
      <th>type</th>
      <th>size</th>
      <th>budget</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>0</td>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1</td>
      <td>Figueroa High School</td>
      <td>District</td>
      <td>2949</td>
      <td>1884411</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2</td>
      <td>Shelton High School</td>
      <td>Charter</td>
      <td>1761</td>
      <td>1056600</td>
    </tr>
    <tr>
      <th>3</th>
      <td>3</td>
      <td>Hernandez High School</td>
      <td>District</td>
      <td>4635</td>
      <td>3022020</td>
    </tr>
    <tr>
      <th>4</th>
      <td>4</td>
      <td>Griffin High School</td>
      <td>Charter</td>
      <td>1468</td>
      <td>917500</td>
    </tr>
  </tbody>
</table>
</div>




```python
merge_SchStu =pd.merge(students_df,schools_df,how="left",left_on="school",right_on="name")
merge_SchStu.head()
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
      <th>Student ID</th>
      <th>name_x</th>
      <th>gender</th>
      <th>grade</th>
      <th>school</th>
      <th>reading_score</th>
      <th>math_score</th>
      <th>School ID</th>
      <th>name_y</th>
      <th>type</th>
      <th>size</th>
      <th>budget</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>0</td>
      <td>Paul Bradley</td>
      <td>M</td>
      <td>9th</td>
      <td>Huang High School</td>
      <td>66</td>
      <td>79</td>
      <td>0</td>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1</td>
      <td>Victor Smith</td>
      <td>M</td>
      <td>12th</td>
      <td>Huang High School</td>
      <td>94</td>
      <td>61</td>
      <td>0</td>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2</td>
      <td>Kevin Rodriguez</td>
      <td>M</td>
      <td>12th</td>
      <td>Huang High School</td>
      <td>90</td>
      <td>60</td>
      <td>0</td>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
    </tr>
    <tr>
      <th>3</th>
      <td>3</td>
      <td>Dr. Richard Scott</td>
      <td>M</td>
      <td>12th</td>
      <td>Huang High School</td>
      <td>67</td>
      <td>58</td>
      <td>0</td>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
    </tr>
    <tr>
      <th>4</th>
      <td>4</td>
      <td>Bonnie Ray</td>
      <td>F</td>
      <td>9th</td>
      <td>Huang High School</td>
      <td>97</td>
      <td>84</td>
      <td>0</td>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
    </tr>
  </tbody>
</table>
</div>




```python
merge_df = merge_SchStu.rename(columns={"name_x":"student name", "name_y":"school name"})
merge_df.head()
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
      <th>Student ID</th>
      <th>student name</th>
      <th>gender</th>
      <th>grade</th>
      <th>school</th>
      <th>reading_score</th>
      <th>math_score</th>
      <th>School ID</th>
      <th>school name</th>
      <th>type</th>
      <th>size</th>
      <th>budget</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>0</td>
      <td>Paul Bradley</td>
      <td>M</td>
      <td>9th</td>
      <td>Huang High School</td>
      <td>66</td>
      <td>79</td>
      <td>0</td>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1</td>
      <td>Victor Smith</td>
      <td>M</td>
      <td>12th</td>
      <td>Huang High School</td>
      <td>94</td>
      <td>61</td>
      <td>0</td>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2</td>
      <td>Kevin Rodriguez</td>
      <td>M</td>
      <td>12th</td>
      <td>Huang High School</td>
      <td>90</td>
      <td>60</td>
      <td>0</td>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
    </tr>
    <tr>
      <th>3</th>
      <td>3</td>
      <td>Dr. Richard Scott</td>
      <td>M</td>
      <td>12th</td>
      <td>Huang High School</td>
      <td>67</td>
      <td>58</td>
      <td>0</td>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
    </tr>
    <tr>
      <th>4</th>
      <td>4</td>
      <td>Bonnie Ray</td>
      <td>F</td>
      <td>9th</td>
      <td>Huang High School</td>
      <td>97</td>
      <td>84</td>
      <td>0</td>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
    </tr>
  </tbody>
</table>
</div>




```python
num_Students = merge_df['student name'].count()
num_Schools = len(merge_df['school name'].unique())
total_Budget = merge_df['budget'].unique().sum()

avg_Math = round(merge_df['math_score'].mean(),2)
avg_Reading = round(merge_df['reading_score'].mean(),2)

#The passing percentage for both Math and Reading is a score greater than 69%

passing_Mathcount = merge_df[(merge_df['math_score']>69)]['math_score'].count()
percent_passMath = round((passing_Mathcount/num_Students)*100,2)

passing_Readcount = merge_df[(merge_df['reading_score']>69)]['reading_score'].count()
percent_passRead = round((passing_Readcount/num_Students)*100,2)

overall_Passing_Rate =(percent_passMath+percent_passRead)/2

num_Students,passing_Mathcount, percent_passMath,passing_Readcount,percent_passRead,overall_Passing_Rate

#passing_Math = merge_df[(merge_df["math_score"]>=avg_Math,merge_df["student name"].counts()
                        
#student["name"].count

#passing_Math = merge_df["math_score"].max()
#passing_Reading = students_df["reading_score"].max()
#overall_passing = (passing_Math + passing_Reading)/2

#num_Students, num_Schools, total_Budget, avg_Math, avg_Reading, 
#passing_Math, passing_Reading, overall_passing
```




    (39170, 29370, 74.98, 33610, 85.81, 80.39500000000001)




```python
merge_df.head()
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
      <th>Student ID</th>
      <th>student name</th>
      <th>gender</th>
      <th>grade</th>
      <th>school</th>
      <th>reading_score</th>
      <th>math_score</th>
      <th>School ID</th>
      <th>school name</th>
      <th>type</th>
      <th>size</th>
      <th>budget</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>0</td>
      <td>Paul Bradley</td>
      <td>M</td>
      <td>9th</td>
      <td>Huang High School</td>
      <td>66</td>
      <td>79</td>
      <td>0</td>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1</td>
      <td>Victor Smith</td>
      <td>M</td>
      <td>12th</td>
      <td>Huang High School</td>
      <td>94</td>
      <td>61</td>
      <td>0</td>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2</td>
      <td>Kevin Rodriguez</td>
      <td>M</td>
      <td>12th</td>
      <td>Huang High School</td>
      <td>90</td>
      <td>60</td>
      <td>0</td>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
    </tr>
    <tr>
      <th>3</th>
      <td>3</td>
      <td>Dr. Richard Scott</td>
      <td>M</td>
      <td>12th</td>
      <td>Huang High School</td>
      <td>67</td>
      <td>58</td>
      <td>0</td>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
    </tr>
    <tr>
      <th>4</th>
      <td>4</td>
      <td>Bonnie Ray</td>
      <td>F</td>
      <td>9th</td>
      <td>Huang High School</td>
      <td>97</td>
      <td>84</td>
      <td>0</td>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
    </tr>
  </tbody>
</table>
</div>




```python
DistrictSummary = pd.DataFrame({"Total Students":[num_Students],
                   "Total Schools":[num_Schools],
                   "Total Budget":[total_Budget],
                   "Average Math Score":[avg_Math],
                   "Average Reading Score":[avg_Reading],
                   "% Passing Math":[percent_passMath],
                   "% Passing Reading":[percent_passRead],
                   "Overall Passing Rate":[overall_Passing_Rate],
                                })

DistrictSummary
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
      <th>% Passing Math</th>
      <th>% Passing Reading</th>
      <th>Average Math Score</th>
      <th>Average Reading Score</th>
      <th>Overall Passing Rate</th>
      <th>Total Budget</th>
      <th>Total Schools</th>
      <th>Total Students</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>74.98</td>
      <td>85.81</td>
      <td>78.99</td>
      <td>81.88</td>
      <td>80.395</td>
      <td>24649428</td>
      <td>15</td>
      <td>39170</td>
    </tr>
  </tbody>
</table>
</div>




```python
organized_DSummary = DistrictSummary[["Total Students", "Total Schools","Total Budget","Average Math Score","Average Reading Score","% Passing Math", "% Passing Reading", "Overall Passing Rate"]]
organized_DSummary
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
      <th>Total Students</th>
      <th>Total Schools</th>
      <th>Total Budget</th>
      <th>Average Math Score</th>
      <th>Average Reading Score</th>
      <th>% Passing Math</th>
      <th>% Passing Reading</th>
      <th>Overall Passing Rate</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>39170</td>
      <td>15</td>
      <td>24649428</td>
      <td>78.99</td>
      <td>81.88</td>
      <td>74.98</td>
      <td>85.81</td>
      <td>80.395</td>
    </tr>
  </tbody>
</table>
</div>




```python
#school_Summary = merge_df[["school name","type","size","budget"]]
#numStu = students_df["Student ID"].count()
#numStu
#school_Summary.head()
#schools = merge_df[['school name','type']]
#school_type = merge_df[([schools][merge_df["type"]])]
#schools.value_COUNTS()
school_summary_df = merge_df.groupby(["school name","type"]).agg({'student name':"count",
                                                                           'math_score':"mean",
                                                                           'reading_score':"mean",
                                                                           'budget':"mean"
                                                                         })

school_summary_df

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
      <th></th>
      <th>student name</th>
      <th>math_score</th>
      <th>reading_score</th>
      <th>budget</th>
    </tr>
    <tr>
      <th>school name</th>
      <th>type</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Bailey High School</th>
      <th>District</th>
      <td>4976</td>
      <td>77.048432</td>
      <td>81.033963</td>
      <td>3124928</td>
    </tr>
    <tr>
      <th>Cabrera High School</th>
      <th>Charter</th>
      <td>1858</td>
      <td>83.061895</td>
      <td>83.975780</td>
      <td>1081356</td>
    </tr>
    <tr>
      <th>Figueroa High School</th>
      <th>District</th>
      <td>2949</td>
      <td>76.711767</td>
      <td>81.158020</td>
      <td>1884411</td>
    </tr>
    <tr>
      <th>Ford High School</th>
      <th>District</th>
      <td>2739</td>
      <td>77.102592</td>
      <td>80.746258</td>
      <td>1763916</td>
    </tr>
    <tr>
      <th>Griffin High School</th>
      <th>Charter</th>
      <td>1468</td>
      <td>83.351499</td>
      <td>83.816757</td>
      <td>917500</td>
    </tr>
    <tr>
      <th>Hernandez High School</th>
      <th>District</th>
      <td>4635</td>
      <td>77.289752</td>
      <td>80.934412</td>
      <td>3022020</td>
    </tr>
    <tr>
      <th>Holden High School</th>
      <th>Charter</th>
      <td>427</td>
      <td>83.803279</td>
      <td>83.814988</td>
      <td>248087</td>
    </tr>
    <tr>
      <th>Huang High School</th>
      <th>District</th>
      <td>2917</td>
      <td>76.629414</td>
      <td>81.182722</td>
      <td>1910635</td>
    </tr>
    <tr>
      <th>Johnson High School</th>
      <th>District</th>
      <td>4761</td>
      <td>77.072464</td>
      <td>80.966394</td>
      <td>3094650</td>
    </tr>
    <tr>
      <th>Pena High School</th>
      <th>Charter</th>
      <td>962</td>
      <td>83.839917</td>
      <td>84.044699</td>
      <td>585858</td>
    </tr>
    <tr>
      <th>Rodriguez High School</th>
      <th>District</th>
      <td>3999</td>
      <td>76.842711</td>
      <td>80.744686</td>
      <td>2547363</td>
    </tr>
    <tr>
      <th>Shelton High School</th>
      <th>Charter</th>
      <td>1761</td>
      <td>83.359455</td>
      <td>83.725724</td>
      <td>1056600</td>
    </tr>
    <tr>
      <th>Thomas High School</th>
      <th>Charter</th>
      <td>1635</td>
      <td>83.418349</td>
      <td>83.848930</td>
      <td>1043130</td>
    </tr>
    <tr>
      <th>Wilson High School</th>
      <th>Charter</th>
      <td>2283</td>
      <td>83.274201</td>
      <td>83.989488</td>
      <td>1319574</td>
    </tr>
    <tr>
      <th>Wright High School</th>
      <th>Charter</th>
      <td>1800</td>
      <td>83.682222</td>
      <td>83.955000</td>
      <td>1049400</td>
    </tr>
  </tbody>
</table>
</div>




```python
school_summary_v1 = school_summary_df.rename(columns={"school name":"School Name","student name":"Total Students","type":"School Type","budget":"Total School Budget","math_score":"Average Math Score","reading_score":"Average Reading Score"})
school_summary_v1
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
      <th></th>
      <th>Total Students</th>
      <th>Average Math Score</th>
      <th>Average Reading Score</th>
      <th>Total School Budget</th>
    </tr>
    <tr>
      <th>school name</th>
      <th>type</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Bailey High School</th>
      <th>District</th>
      <td>4976</td>
      <td>77.048432</td>
      <td>81.033963</td>
      <td>3124928</td>
    </tr>
    <tr>
      <th>Cabrera High School</th>
      <th>Charter</th>
      <td>1858</td>
      <td>83.061895</td>
      <td>83.975780</td>
      <td>1081356</td>
    </tr>
    <tr>
      <th>Figueroa High School</th>
      <th>District</th>
      <td>2949</td>
      <td>76.711767</td>
      <td>81.158020</td>
      <td>1884411</td>
    </tr>
    <tr>
      <th>Ford High School</th>
      <th>District</th>
      <td>2739</td>
      <td>77.102592</td>
      <td>80.746258</td>
      <td>1763916</td>
    </tr>
    <tr>
      <th>Griffin High School</th>
      <th>Charter</th>
      <td>1468</td>
      <td>83.351499</td>
      <td>83.816757</td>
      <td>917500</td>
    </tr>
    <tr>
      <th>Hernandez High School</th>
      <th>District</th>
      <td>4635</td>
      <td>77.289752</td>
      <td>80.934412</td>
      <td>3022020</td>
    </tr>
    <tr>
      <th>Holden High School</th>
      <th>Charter</th>
      <td>427</td>
      <td>83.803279</td>
      <td>83.814988</td>
      <td>248087</td>
    </tr>
    <tr>
      <th>Huang High School</th>
      <th>District</th>
      <td>2917</td>
      <td>76.629414</td>
      <td>81.182722</td>
      <td>1910635</td>
    </tr>
    <tr>
      <th>Johnson High School</th>
      <th>District</th>
      <td>4761</td>
      <td>77.072464</td>
      <td>80.966394</td>
      <td>3094650</td>
    </tr>
    <tr>
      <th>Pena High School</th>
      <th>Charter</th>
      <td>962</td>
      <td>83.839917</td>
      <td>84.044699</td>
      <td>585858</td>
    </tr>
    <tr>
      <th>Rodriguez High School</th>
      <th>District</th>
      <td>3999</td>
      <td>76.842711</td>
      <td>80.744686</td>
      <td>2547363</td>
    </tr>
    <tr>
      <th>Shelton High School</th>
      <th>Charter</th>
      <td>1761</td>
      <td>83.359455</td>
      <td>83.725724</td>
      <td>1056600</td>
    </tr>
    <tr>
      <th>Thomas High School</th>
      <th>Charter</th>
      <td>1635</td>
      <td>83.418349</td>
      <td>83.848930</td>
      <td>1043130</td>
    </tr>
    <tr>
      <th>Wilson High School</th>
      <th>Charter</th>
      <td>2283</td>
      <td>83.274201</td>
      <td>83.989488</td>
      <td>1319574</td>
    </tr>
    <tr>
      <th>Wright High School</th>
      <th>Charter</th>
      <td>1800</td>
      <td>83.682222</td>
      <td>83.955000</td>
      <td>1049400</td>
    </tr>
  </tbody>
</table>
</div>




```python
#school_summary_df['Per Student Budget'] = school_summary_df["budget"]/school_summary_df["student name"]

passing_math_count = merge_df[(merge_df["math_score"]>69)] 
passing_math_count_school = passing_math_count.groupby("school name").agg({"math_score":"count"})
passing_math_count_school = passing_math_count_school.rename(columns={"math_score":"Count_passingMath"})
passing_math_count_school
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
      <th>Count_passingMath</th>
    </tr>
    <tr>
      <th>school name</th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Bailey High School</th>
      <td>3318</td>
    </tr>
    <tr>
      <th>Cabrera High School</th>
      <td>1749</td>
    </tr>
    <tr>
      <th>Figueroa High School</th>
      <td>1946</td>
    </tr>
    <tr>
      <th>Ford High School</th>
      <td>1871</td>
    </tr>
    <tr>
      <th>Griffin High School</th>
      <td>1371</td>
    </tr>
    <tr>
      <th>Hernandez High School</th>
      <td>3094</td>
    </tr>
    <tr>
      <th>Holden High School</th>
      <td>395</td>
    </tr>
    <tr>
      <th>Huang High School</th>
      <td>1916</td>
    </tr>
    <tr>
      <th>Johnson High School</th>
      <td>3145</td>
    </tr>
    <tr>
      <th>Pena High School</th>
      <td>910</td>
    </tr>
    <tr>
      <th>Rodriguez High School</th>
      <td>2654</td>
    </tr>
    <tr>
      <th>Shelton High School</th>
      <td>1653</td>
    </tr>
    <tr>
      <th>Thomas High School</th>
      <td>1525</td>
    </tr>
    <tr>
      <th>Wilson High School</th>
      <td>2143</td>
    </tr>
    <tr>
      <th>Wright High School</th>
      <td>1680</td>
    </tr>
  </tbody>
</table>
</div>




```python
passing_reading_count = merge_df[(merge_df["reading_score"]>69)] 
passing_reading_count_school = passing_reading_count.groupby("school name").agg({"reading_score":"count"})
passing_reading_count_school = passing_reading_count_school.rename(columns={"reading_score":"Count_passingReading"})
passing_reading_count_school
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
      <th>Count_passingReading</th>
    </tr>
    <tr>
      <th>school name</th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Bailey High School</th>
      <td>4077</td>
    </tr>
    <tr>
      <th>Cabrera High School</th>
      <td>1803</td>
    </tr>
    <tr>
      <th>Figueroa High School</th>
      <td>2381</td>
    </tr>
    <tr>
      <th>Ford High School</th>
      <td>2172</td>
    </tr>
    <tr>
      <th>Griffin High School</th>
      <td>1426</td>
    </tr>
    <tr>
      <th>Hernandez High School</th>
      <td>3748</td>
    </tr>
    <tr>
      <th>Holden High School</th>
      <td>411</td>
    </tr>
    <tr>
      <th>Huang High School</th>
      <td>2372</td>
    </tr>
    <tr>
      <th>Johnson High School</th>
      <td>3867</td>
    </tr>
    <tr>
      <th>Pena High School</th>
      <td>923</td>
    </tr>
    <tr>
      <th>Rodriguez High School</th>
      <td>3208</td>
    </tr>
    <tr>
      <th>Shelton High School</th>
      <td>1688</td>
    </tr>
    <tr>
      <th>Thomas High School</th>
      <td>1591</td>
    </tr>
    <tr>
      <th>Wilson High School</th>
      <td>2204</td>
    </tr>
    <tr>
      <th>Wright High School</th>
      <td>1739</td>
    </tr>
  </tbody>
</table>
</div>




```python
school_summary_v2 = school_summary_v1.join(passing_reading_count_school,rsuffix="ct")
school_summary_v2


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
      <th></th>
      <th>Total Students</th>
      <th>Average Math Score</th>
      <th>Average Reading Score</th>
      <th>Total School Budget</th>
      <th>Count_passingReading</th>
    </tr>
    <tr>
      <th>school name</th>
      <th>type</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Bailey High School</th>
      <th>District</th>
      <td>4976</td>
      <td>77.048432</td>
      <td>81.033963</td>
      <td>3124928</td>
      <td>4077</td>
    </tr>
    <tr>
      <th>Cabrera High School</th>
      <th>Charter</th>
      <td>1858</td>
      <td>83.061895</td>
      <td>83.975780</td>
      <td>1081356</td>
      <td>1803</td>
    </tr>
    <tr>
      <th>Figueroa High School</th>
      <th>District</th>
      <td>2949</td>
      <td>76.711767</td>
      <td>81.158020</td>
      <td>1884411</td>
      <td>2381</td>
    </tr>
    <tr>
      <th>Ford High School</th>
      <th>District</th>
      <td>2739</td>
      <td>77.102592</td>
      <td>80.746258</td>
      <td>1763916</td>
      <td>2172</td>
    </tr>
    <tr>
      <th>Griffin High School</th>
      <th>Charter</th>
      <td>1468</td>
      <td>83.351499</td>
      <td>83.816757</td>
      <td>917500</td>
      <td>1426</td>
    </tr>
    <tr>
      <th>Hernandez High School</th>
      <th>District</th>
      <td>4635</td>
      <td>77.289752</td>
      <td>80.934412</td>
      <td>3022020</td>
      <td>3748</td>
    </tr>
    <tr>
      <th>Holden High School</th>
      <th>Charter</th>
      <td>427</td>
      <td>83.803279</td>
      <td>83.814988</td>
      <td>248087</td>
      <td>411</td>
    </tr>
    <tr>
      <th>Huang High School</th>
      <th>District</th>
      <td>2917</td>
      <td>76.629414</td>
      <td>81.182722</td>
      <td>1910635</td>
      <td>2372</td>
    </tr>
    <tr>
      <th>Johnson High School</th>
      <th>District</th>
      <td>4761</td>
      <td>77.072464</td>
      <td>80.966394</td>
      <td>3094650</td>
      <td>3867</td>
    </tr>
    <tr>
      <th>Pena High School</th>
      <th>Charter</th>
      <td>962</td>
      <td>83.839917</td>
      <td>84.044699</td>
      <td>585858</td>
      <td>923</td>
    </tr>
    <tr>
      <th>Rodriguez High School</th>
      <th>District</th>
      <td>3999</td>
      <td>76.842711</td>
      <td>80.744686</td>
      <td>2547363</td>
      <td>3208</td>
    </tr>
    <tr>
      <th>Shelton High School</th>
      <th>Charter</th>
      <td>1761</td>
      <td>83.359455</td>
      <td>83.725724</td>
      <td>1056600</td>
      <td>1688</td>
    </tr>
    <tr>
      <th>Thomas High School</th>
      <th>Charter</th>
      <td>1635</td>
      <td>83.418349</td>
      <td>83.848930</td>
      <td>1043130</td>
      <td>1591</td>
    </tr>
    <tr>
      <th>Wilson High School</th>
      <th>Charter</th>
      <td>2283</td>
      <td>83.274201</td>
      <td>83.989488</td>
      <td>1319574</td>
      <td>2204</td>
    </tr>
    <tr>
      <th>Wright High School</th>
      <th>Charter</th>
      <td>1800</td>
      <td>83.682222</td>
      <td>83.955000</td>
      <td>1049400</td>
      <td>1739</td>
    </tr>
  </tbody>
</table>
</div>




```python
school_summary_v3 = school_summary_v2.join(passing_math_count_school,rsuffix="ct")
school_summary_v3

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
      <th></th>
      <th>Total Students</th>
      <th>Average Math Score</th>
      <th>Average Reading Score</th>
      <th>Total School Budget</th>
      <th>Count_passingReading</th>
      <th>Count_passingMath</th>
    </tr>
    <tr>
      <th>school name</th>
      <th>type</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Bailey High School</th>
      <th>District</th>
      <td>4976</td>
      <td>77.048432</td>
      <td>81.033963</td>
      <td>3124928</td>
      <td>4077</td>
      <td>3318</td>
    </tr>
    <tr>
      <th>Cabrera High School</th>
      <th>Charter</th>
      <td>1858</td>
      <td>83.061895</td>
      <td>83.975780</td>
      <td>1081356</td>
      <td>1803</td>
      <td>1749</td>
    </tr>
    <tr>
      <th>Figueroa High School</th>
      <th>District</th>
      <td>2949</td>
      <td>76.711767</td>
      <td>81.158020</td>
      <td>1884411</td>
      <td>2381</td>
      <td>1946</td>
    </tr>
    <tr>
      <th>Ford High School</th>
      <th>District</th>
      <td>2739</td>
      <td>77.102592</td>
      <td>80.746258</td>
      <td>1763916</td>
      <td>2172</td>
      <td>1871</td>
    </tr>
    <tr>
      <th>Griffin High School</th>
      <th>Charter</th>
      <td>1468</td>
      <td>83.351499</td>
      <td>83.816757</td>
      <td>917500</td>
      <td>1426</td>
      <td>1371</td>
    </tr>
    <tr>
      <th>Hernandez High School</th>
      <th>District</th>
      <td>4635</td>
      <td>77.289752</td>
      <td>80.934412</td>
      <td>3022020</td>
      <td>3748</td>
      <td>3094</td>
    </tr>
    <tr>
      <th>Holden High School</th>
      <th>Charter</th>
      <td>427</td>
      <td>83.803279</td>
      <td>83.814988</td>
      <td>248087</td>
      <td>411</td>
      <td>395</td>
    </tr>
    <tr>
      <th>Huang High School</th>
      <th>District</th>
      <td>2917</td>
      <td>76.629414</td>
      <td>81.182722</td>
      <td>1910635</td>
      <td>2372</td>
      <td>1916</td>
    </tr>
    <tr>
      <th>Johnson High School</th>
      <th>District</th>
      <td>4761</td>
      <td>77.072464</td>
      <td>80.966394</td>
      <td>3094650</td>
      <td>3867</td>
      <td>3145</td>
    </tr>
    <tr>
      <th>Pena High School</th>
      <th>Charter</th>
      <td>962</td>
      <td>83.839917</td>
      <td>84.044699</td>
      <td>585858</td>
      <td>923</td>
      <td>910</td>
    </tr>
    <tr>
      <th>Rodriguez High School</th>
      <th>District</th>
      <td>3999</td>
      <td>76.842711</td>
      <td>80.744686</td>
      <td>2547363</td>
      <td>3208</td>
      <td>2654</td>
    </tr>
    <tr>
      <th>Shelton High School</th>
      <th>Charter</th>
      <td>1761</td>
      <td>83.359455</td>
      <td>83.725724</td>
      <td>1056600</td>
      <td>1688</td>
      <td>1653</td>
    </tr>
    <tr>
      <th>Thomas High School</th>
      <th>Charter</th>
      <td>1635</td>
      <td>83.418349</td>
      <td>83.848930</td>
      <td>1043130</td>
      <td>1591</td>
      <td>1525</td>
    </tr>
    <tr>
      <th>Wilson High School</th>
      <th>Charter</th>
      <td>2283</td>
      <td>83.274201</td>
      <td>83.989488</td>
      <td>1319574</td>
      <td>2204</td>
      <td>2143</td>
    </tr>
    <tr>
      <th>Wright High School</th>
      <th>Charter</th>
      <td>1800</td>
      <td>83.682222</td>
      <td>83.955000</td>
      <td>1049400</td>
      <td>1739</td>
      <td>1680</td>
    </tr>
  </tbody>
</table>
</div>




```python
school_summary_v3["% Passing Math"] = round((school_summary_v3['Count_passingMath']/school_summary_v3['Total Students'])*100)
school_summary_v3["% Passing Reading"] = round((school_summary_v3['Count_passingReading']/school_summary_v3['Total Students'])*100)
school_summary_v3["Per Student Budget"] = school_summary_v3['Total School Budget']/school_summary_v3['Total Students']
school_summary_v3
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
      <th></th>
      <th>Total Students</th>
      <th>Average Math Score</th>
      <th>Average Reading Score</th>
      <th>Total School Budget</th>
      <th>Count_passingReading</th>
      <th>Count_passingMath</th>
      <th>% Passing Math</th>
      <th>% Passing Reading</th>
      <th>Per Student Budget</th>
    </tr>
    <tr>
      <th>school name</th>
      <th>type</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Bailey High School</th>
      <th>District</th>
      <td>4976</td>
      <td>77.048432</td>
      <td>81.033963</td>
      <td>3124928</td>
      <td>4077</td>
      <td>3318</td>
      <td>67.0</td>
      <td>82.0</td>
      <td>628.0</td>
    </tr>
    <tr>
      <th>Cabrera High School</th>
      <th>Charter</th>
      <td>1858</td>
      <td>83.061895</td>
      <td>83.975780</td>
      <td>1081356</td>
      <td>1803</td>
      <td>1749</td>
      <td>94.0</td>
      <td>97.0</td>
      <td>582.0</td>
    </tr>
    <tr>
      <th>Figueroa High School</th>
      <th>District</th>
      <td>2949</td>
      <td>76.711767</td>
      <td>81.158020</td>
      <td>1884411</td>
      <td>2381</td>
      <td>1946</td>
      <td>66.0</td>
      <td>81.0</td>
      <td>639.0</td>
    </tr>
    <tr>
      <th>Ford High School</th>
      <th>District</th>
      <td>2739</td>
      <td>77.102592</td>
      <td>80.746258</td>
      <td>1763916</td>
      <td>2172</td>
      <td>1871</td>
      <td>68.0</td>
      <td>79.0</td>
      <td>644.0</td>
    </tr>
    <tr>
      <th>Griffin High School</th>
      <th>Charter</th>
      <td>1468</td>
      <td>83.351499</td>
      <td>83.816757</td>
      <td>917500</td>
      <td>1426</td>
      <td>1371</td>
      <td>93.0</td>
      <td>97.0</td>
      <td>625.0</td>
    </tr>
    <tr>
      <th>Hernandez High School</th>
      <th>District</th>
      <td>4635</td>
      <td>77.289752</td>
      <td>80.934412</td>
      <td>3022020</td>
      <td>3748</td>
      <td>3094</td>
      <td>67.0</td>
      <td>81.0</td>
      <td>652.0</td>
    </tr>
    <tr>
      <th>Holden High School</th>
      <th>Charter</th>
      <td>427</td>
      <td>83.803279</td>
      <td>83.814988</td>
      <td>248087</td>
      <td>411</td>
      <td>395</td>
      <td>93.0</td>
      <td>96.0</td>
      <td>581.0</td>
    </tr>
    <tr>
      <th>Huang High School</th>
      <th>District</th>
      <td>2917</td>
      <td>76.629414</td>
      <td>81.182722</td>
      <td>1910635</td>
      <td>2372</td>
      <td>1916</td>
      <td>66.0</td>
      <td>81.0</td>
      <td>655.0</td>
    </tr>
    <tr>
      <th>Johnson High School</th>
      <th>District</th>
      <td>4761</td>
      <td>77.072464</td>
      <td>80.966394</td>
      <td>3094650</td>
      <td>3867</td>
      <td>3145</td>
      <td>66.0</td>
      <td>81.0</td>
      <td>650.0</td>
    </tr>
    <tr>
      <th>Pena High School</th>
      <th>Charter</th>
      <td>962</td>
      <td>83.839917</td>
      <td>84.044699</td>
      <td>585858</td>
      <td>923</td>
      <td>910</td>
      <td>95.0</td>
      <td>96.0</td>
      <td>609.0</td>
    </tr>
    <tr>
      <th>Rodriguez High School</th>
      <th>District</th>
      <td>3999</td>
      <td>76.842711</td>
      <td>80.744686</td>
      <td>2547363</td>
      <td>3208</td>
      <td>2654</td>
      <td>66.0</td>
      <td>80.0</td>
      <td>637.0</td>
    </tr>
    <tr>
      <th>Shelton High School</th>
      <th>Charter</th>
      <td>1761</td>
      <td>83.359455</td>
      <td>83.725724</td>
      <td>1056600</td>
      <td>1688</td>
      <td>1653</td>
      <td>94.0</td>
      <td>96.0</td>
      <td>600.0</td>
    </tr>
    <tr>
      <th>Thomas High School</th>
      <th>Charter</th>
      <td>1635</td>
      <td>83.418349</td>
      <td>83.848930</td>
      <td>1043130</td>
      <td>1591</td>
      <td>1525</td>
      <td>93.0</td>
      <td>97.0</td>
      <td>638.0</td>
    </tr>
    <tr>
      <th>Wilson High School</th>
      <th>Charter</th>
      <td>2283</td>
      <td>83.274201</td>
      <td>83.989488</td>
      <td>1319574</td>
      <td>2204</td>
      <td>2143</td>
      <td>94.0</td>
      <td>97.0</td>
      <td>578.0</td>
    </tr>
    <tr>
      <th>Wright High School</th>
      <th>Charter</th>
      <td>1800</td>
      <td>83.682222</td>
      <td>83.955000</td>
      <td>1049400</td>
      <td>1739</td>
      <td>1680</td>
      <td>93.0</td>
      <td>97.0</td>
      <td>583.0</td>
    </tr>
  </tbody>
</table>
</div>




```python
school_summary_v3["Overall Passing Rate"] = ((school_summary_v3["% Passing Reading"]+school_summary_v3["% Passing Math"])/2)
school_summary_v3
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
      <th></th>
      <th>Total Students</th>
      <th>Average Math Score</th>
      <th>Average Reading Score</th>
      <th>Total School Budget</th>
      <th>Count_passingReading</th>
      <th>Count_passingMath</th>
      <th>% Passing Math</th>
      <th>% Passing Reading</th>
      <th>Per Student Budget</th>
      <th>Overall Passing Rate</th>
    </tr>
    <tr>
      <th>school name</th>
      <th>type</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Bailey High School</th>
      <th>District</th>
      <td>4976</td>
      <td>77.048432</td>
      <td>81.033963</td>
      <td>3124928</td>
      <td>4077</td>
      <td>3318</td>
      <td>67.0</td>
      <td>82.0</td>
      <td>628.0</td>
      <td>74.5</td>
    </tr>
    <tr>
      <th>Cabrera High School</th>
      <th>Charter</th>
      <td>1858</td>
      <td>83.061895</td>
      <td>83.975780</td>
      <td>1081356</td>
      <td>1803</td>
      <td>1749</td>
      <td>94.0</td>
      <td>97.0</td>
      <td>582.0</td>
      <td>95.5</td>
    </tr>
    <tr>
      <th>Figueroa High School</th>
      <th>District</th>
      <td>2949</td>
      <td>76.711767</td>
      <td>81.158020</td>
      <td>1884411</td>
      <td>2381</td>
      <td>1946</td>
      <td>66.0</td>
      <td>81.0</td>
      <td>639.0</td>
      <td>73.5</td>
    </tr>
    <tr>
      <th>Ford High School</th>
      <th>District</th>
      <td>2739</td>
      <td>77.102592</td>
      <td>80.746258</td>
      <td>1763916</td>
      <td>2172</td>
      <td>1871</td>
      <td>68.0</td>
      <td>79.0</td>
      <td>644.0</td>
      <td>73.5</td>
    </tr>
    <tr>
      <th>Griffin High School</th>
      <th>Charter</th>
      <td>1468</td>
      <td>83.351499</td>
      <td>83.816757</td>
      <td>917500</td>
      <td>1426</td>
      <td>1371</td>
      <td>93.0</td>
      <td>97.0</td>
      <td>625.0</td>
      <td>95.0</td>
    </tr>
    <tr>
      <th>Hernandez High School</th>
      <th>District</th>
      <td>4635</td>
      <td>77.289752</td>
      <td>80.934412</td>
      <td>3022020</td>
      <td>3748</td>
      <td>3094</td>
      <td>67.0</td>
      <td>81.0</td>
      <td>652.0</td>
      <td>74.0</td>
    </tr>
    <tr>
      <th>Holden High School</th>
      <th>Charter</th>
      <td>427</td>
      <td>83.803279</td>
      <td>83.814988</td>
      <td>248087</td>
      <td>411</td>
      <td>395</td>
      <td>93.0</td>
      <td>96.0</td>
      <td>581.0</td>
      <td>94.5</td>
    </tr>
    <tr>
      <th>Huang High School</th>
      <th>District</th>
      <td>2917</td>
      <td>76.629414</td>
      <td>81.182722</td>
      <td>1910635</td>
      <td>2372</td>
      <td>1916</td>
      <td>66.0</td>
      <td>81.0</td>
      <td>655.0</td>
      <td>73.5</td>
    </tr>
    <tr>
      <th>Johnson High School</th>
      <th>District</th>
      <td>4761</td>
      <td>77.072464</td>
      <td>80.966394</td>
      <td>3094650</td>
      <td>3867</td>
      <td>3145</td>
      <td>66.0</td>
      <td>81.0</td>
      <td>650.0</td>
      <td>73.5</td>
    </tr>
    <tr>
      <th>Pena High School</th>
      <th>Charter</th>
      <td>962</td>
      <td>83.839917</td>
      <td>84.044699</td>
      <td>585858</td>
      <td>923</td>
      <td>910</td>
      <td>95.0</td>
      <td>96.0</td>
      <td>609.0</td>
      <td>95.5</td>
    </tr>
    <tr>
      <th>Rodriguez High School</th>
      <th>District</th>
      <td>3999</td>
      <td>76.842711</td>
      <td>80.744686</td>
      <td>2547363</td>
      <td>3208</td>
      <td>2654</td>
      <td>66.0</td>
      <td>80.0</td>
      <td>637.0</td>
      <td>73.0</td>
    </tr>
    <tr>
      <th>Shelton High School</th>
      <th>Charter</th>
      <td>1761</td>
      <td>83.359455</td>
      <td>83.725724</td>
      <td>1056600</td>
      <td>1688</td>
      <td>1653</td>
      <td>94.0</td>
      <td>96.0</td>
      <td>600.0</td>
      <td>95.0</td>
    </tr>
    <tr>
      <th>Thomas High School</th>
      <th>Charter</th>
      <td>1635</td>
      <td>83.418349</td>
      <td>83.848930</td>
      <td>1043130</td>
      <td>1591</td>
      <td>1525</td>
      <td>93.0</td>
      <td>97.0</td>
      <td>638.0</td>
      <td>95.0</td>
    </tr>
    <tr>
      <th>Wilson High School</th>
      <th>Charter</th>
      <td>2283</td>
      <td>83.274201</td>
      <td>83.989488</td>
      <td>1319574</td>
      <td>2204</td>
      <td>2143</td>
      <td>94.0</td>
      <td>97.0</td>
      <td>578.0</td>
      <td>95.5</td>
    </tr>
    <tr>
      <th>Wright High School</th>
      <th>Charter</th>
      <td>1800</td>
      <td>83.682222</td>
      <td>83.955000</td>
      <td>1049400</td>
      <td>1739</td>
      <td>1680</td>
      <td>93.0</td>
      <td>97.0</td>
      <td>583.0</td>
      <td>95.0</td>
    </tr>
  </tbody>
</table>
</div>




```python
schoolSummary = school_summary_v3[["Total Students","Average Math Score","Average Reading Score","Total School Budget",
                                   "Per Student Budget","% Passing Math","% Passing Reading","Overall Passing Rate"]]

schoolSummary
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
      <th></th>
      <th>Total Students</th>
      <th>Average Math Score</th>
      <th>Average Reading Score</th>
      <th>Total School Budget</th>
      <th>Per Student Budget</th>
      <th>% Passing Math</th>
      <th>% Passing Reading</th>
      <th>Overall Passing Rate</th>
    </tr>
    <tr>
      <th>school name</th>
      <th>type</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Bailey High School</th>
      <th>District</th>
      <td>4976</td>
      <td>77.048432</td>
      <td>81.033963</td>
      <td>3124928</td>
      <td>628.0</td>
      <td>67.0</td>
      <td>82.0</td>
      <td>74.5</td>
    </tr>
    <tr>
      <th>Cabrera High School</th>
      <th>Charter</th>
      <td>1858</td>
      <td>83.061895</td>
      <td>83.975780</td>
      <td>1081356</td>
      <td>582.0</td>
      <td>94.0</td>
      <td>97.0</td>
      <td>95.5</td>
    </tr>
    <tr>
      <th>Figueroa High School</th>
      <th>District</th>
      <td>2949</td>
      <td>76.711767</td>
      <td>81.158020</td>
      <td>1884411</td>
      <td>639.0</td>
      <td>66.0</td>
      <td>81.0</td>
      <td>73.5</td>
    </tr>
    <tr>
      <th>Ford High School</th>
      <th>District</th>
      <td>2739</td>
      <td>77.102592</td>
      <td>80.746258</td>
      <td>1763916</td>
      <td>644.0</td>
      <td>68.0</td>
      <td>79.0</td>
      <td>73.5</td>
    </tr>
    <tr>
      <th>Griffin High School</th>
      <th>Charter</th>
      <td>1468</td>
      <td>83.351499</td>
      <td>83.816757</td>
      <td>917500</td>
      <td>625.0</td>
      <td>93.0</td>
      <td>97.0</td>
      <td>95.0</td>
    </tr>
    <tr>
      <th>Hernandez High School</th>
      <th>District</th>
      <td>4635</td>
      <td>77.289752</td>
      <td>80.934412</td>
      <td>3022020</td>
      <td>652.0</td>
      <td>67.0</td>
      <td>81.0</td>
      <td>74.0</td>
    </tr>
    <tr>
      <th>Holden High School</th>
      <th>Charter</th>
      <td>427</td>
      <td>83.803279</td>
      <td>83.814988</td>
      <td>248087</td>
      <td>581.0</td>
      <td>93.0</td>
      <td>96.0</td>
      <td>94.5</td>
    </tr>
    <tr>
      <th>Huang High School</th>
      <th>District</th>
      <td>2917</td>
      <td>76.629414</td>
      <td>81.182722</td>
      <td>1910635</td>
      <td>655.0</td>
      <td>66.0</td>
      <td>81.0</td>
      <td>73.5</td>
    </tr>
    <tr>
      <th>Johnson High School</th>
      <th>District</th>
      <td>4761</td>
      <td>77.072464</td>
      <td>80.966394</td>
      <td>3094650</td>
      <td>650.0</td>
      <td>66.0</td>
      <td>81.0</td>
      <td>73.5</td>
    </tr>
    <tr>
      <th>Pena High School</th>
      <th>Charter</th>
      <td>962</td>
      <td>83.839917</td>
      <td>84.044699</td>
      <td>585858</td>
      <td>609.0</td>
      <td>95.0</td>
      <td>96.0</td>
      <td>95.5</td>
    </tr>
    <tr>
      <th>Rodriguez High School</th>
      <th>District</th>
      <td>3999</td>
      <td>76.842711</td>
      <td>80.744686</td>
      <td>2547363</td>
      <td>637.0</td>
      <td>66.0</td>
      <td>80.0</td>
      <td>73.0</td>
    </tr>
    <tr>
      <th>Shelton High School</th>
      <th>Charter</th>
      <td>1761</td>
      <td>83.359455</td>
      <td>83.725724</td>
      <td>1056600</td>
      <td>600.0</td>
      <td>94.0</td>
      <td>96.0</td>
      <td>95.0</td>
    </tr>
    <tr>
      <th>Thomas High School</th>
      <th>Charter</th>
      <td>1635</td>
      <td>83.418349</td>
      <td>83.848930</td>
      <td>1043130</td>
      <td>638.0</td>
      <td>93.0</td>
      <td>97.0</td>
      <td>95.0</td>
    </tr>
    <tr>
      <th>Wilson High School</th>
      <th>Charter</th>
      <td>2283</td>
      <td>83.274201</td>
      <td>83.989488</td>
      <td>1319574</td>
      <td>578.0</td>
      <td>94.0</td>
      <td>97.0</td>
      <td>95.5</td>
    </tr>
    <tr>
      <th>Wright High School</th>
      <th>Charter</th>
      <td>1800</td>
      <td>83.682222</td>
      <td>83.955000</td>
      <td>1049400</td>
      <td>583.0</td>
      <td>93.0</td>
      <td>97.0</td>
      <td>95.0</td>
    </tr>
  </tbody>
</table>
</div>




```python
schoolSummary
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
      <th></th>
      <th>Total Students</th>
      <th>Average Math Score</th>
      <th>Average Reading Score</th>
      <th>Total School Budget</th>
      <th>Per Student Budget</th>
      <th>% Passing Math</th>
      <th>% Passing Reading</th>
      <th>Overall Passing Rate</th>
    </tr>
    <tr>
      <th>school name</th>
      <th>type</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Bailey High School</th>
      <th>District</th>
      <td>4976</td>
      <td>77.048432</td>
      <td>81.033963</td>
      <td>3124928</td>
      <td>628.0</td>
      <td>67.0</td>
      <td>82.0</td>
      <td>74.5</td>
    </tr>
    <tr>
      <th>Cabrera High School</th>
      <th>Charter</th>
      <td>1858</td>
      <td>83.061895</td>
      <td>83.975780</td>
      <td>1081356</td>
      <td>582.0</td>
      <td>94.0</td>
      <td>97.0</td>
      <td>95.5</td>
    </tr>
    <tr>
      <th>Figueroa High School</th>
      <th>District</th>
      <td>2949</td>
      <td>76.711767</td>
      <td>81.158020</td>
      <td>1884411</td>
      <td>639.0</td>
      <td>66.0</td>
      <td>81.0</td>
      <td>73.5</td>
    </tr>
    <tr>
      <th>Ford High School</th>
      <th>District</th>
      <td>2739</td>
      <td>77.102592</td>
      <td>80.746258</td>
      <td>1763916</td>
      <td>644.0</td>
      <td>68.0</td>
      <td>79.0</td>
      <td>73.5</td>
    </tr>
    <tr>
      <th>Griffin High School</th>
      <th>Charter</th>
      <td>1468</td>
      <td>83.351499</td>
      <td>83.816757</td>
      <td>917500</td>
      <td>625.0</td>
      <td>93.0</td>
      <td>97.0</td>
      <td>95.0</td>
    </tr>
    <tr>
      <th>Hernandez High School</th>
      <th>District</th>
      <td>4635</td>
      <td>77.289752</td>
      <td>80.934412</td>
      <td>3022020</td>
      <td>652.0</td>
      <td>67.0</td>
      <td>81.0</td>
      <td>74.0</td>
    </tr>
    <tr>
      <th>Holden High School</th>
      <th>Charter</th>
      <td>427</td>
      <td>83.803279</td>
      <td>83.814988</td>
      <td>248087</td>
      <td>581.0</td>
      <td>93.0</td>
      <td>96.0</td>
      <td>94.5</td>
    </tr>
    <tr>
      <th>Huang High School</th>
      <th>District</th>
      <td>2917</td>
      <td>76.629414</td>
      <td>81.182722</td>
      <td>1910635</td>
      <td>655.0</td>
      <td>66.0</td>
      <td>81.0</td>
      <td>73.5</td>
    </tr>
    <tr>
      <th>Johnson High School</th>
      <th>District</th>
      <td>4761</td>
      <td>77.072464</td>
      <td>80.966394</td>
      <td>3094650</td>
      <td>650.0</td>
      <td>66.0</td>
      <td>81.0</td>
      <td>73.5</td>
    </tr>
    <tr>
      <th>Pena High School</th>
      <th>Charter</th>
      <td>962</td>
      <td>83.839917</td>
      <td>84.044699</td>
      <td>585858</td>
      <td>609.0</td>
      <td>95.0</td>
      <td>96.0</td>
      <td>95.5</td>
    </tr>
    <tr>
      <th>Rodriguez High School</th>
      <th>District</th>
      <td>3999</td>
      <td>76.842711</td>
      <td>80.744686</td>
      <td>2547363</td>
      <td>637.0</td>
      <td>66.0</td>
      <td>80.0</td>
      <td>73.0</td>
    </tr>
    <tr>
      <th>Shelton High School</th>
      <th>Charter</th>
      <td>1761</td>
      <td>83.359455</td>
      <td>83.725724</td>
      <td>1056600</td>
      <td>600.0</td>
      <td>94.0</td>
      <td>96.0</td>
      <td>95.0</td>
    </tr>
    <tr>
      <th>Thomas High School</th>
      <th>Charter</th>
      <td>1635</td>
      <td>83.418349</td>
      <td>83.848930</td>
      <td>1043130</td>
      <td>638.0</td>
      <td>93.0</td>
      <td>97.0</td>
      <td>95.0</td>
    </tr>
    <tr>
      <th>Wilson High School</th>
      <th>Charter</th>
      <td>2283</td>
      <td>83.274201</td>
      <td>83.989488</td>
      <td>1319574</td>
      <td>578.0</td>
      <td>94.0</td>
      <td>97.0</td>
      <td>95.5</td>
    </tr>
    <tr>
      <th>Wright High School</th>
      <th>Charter</th>
      <td>1800</td>
      <td>83.682222</td>
      <td>83.955000</td>
      <td>1049400</td>
      <td>583.0</td>
      <td>93.0</td>
      <td>97.0</td>
      <td>95.0</td>
    </tr>
  </tbody>
</table>
</div>




```python
sortSummary = schoolSummary.sort_values(['Overall Passing Rate'], ascending=False)
sortSummary
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
      <th></th>
      <th>Total Students</th>
      <th>Average Math Score</th>
      <th>Average Reading Score</th>
      <th>Total School Budget</th>
      <th>Per Student Budget</th>
      <th>% Passing Math</th>
      <th>% Passing Reading</th>
      <th>Overall Passing Rate</th>
    </tr>
    <tr>
      <th>school name</th>
      <th>type</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Cabrera High School</th>
      <th>Charter</th>
      <td>1858</td>
      <td>83.061895</td>
      <td>83.975780</td>
      <td>1081356</td>
      <td>582.0</td>
      <td>94.0</td>
      <td>97.0</td>
      <td>95.5</td>
    </tr>
    <tr>
      <th>Pena High School</th>
      <th>Charter</th>
      <td>962</td>
      <td>83.839917</td>
      <td>84.044699</td>
      <td>585858</td>
      <td>609.0</td>
      <td>95.0</td>
      <td>96.0</td>
      <td>95.5</td>
    </tr>
    <tr>
      <th>Wilson High School</th>
      <th>Charter</th>
      <td>2283</td>
      <td>83.274201</td>
      <td>83.989488</td>
      <td>1319574</td>
      <td>578.0</td>
      <td>94.0</td>
      <td>97.0</td>
      <td>95.5</td>
    </tr>
    <tr>
      <th>Griffin High School</th>
      <th>Charter</th>
      <td>1468</td>
      <td>83.351499</td>
      <td>83.816757</td>
      <td>917500</td>
      <td>625.0</td>
      <td>93.0</td>
      <td>97.0</td>
      <td>95.0</td>
    </tr>
    <tr>
      <th>Shelton High School</th>
      <th>Charter</th>
      <td>1761</td>
      <td>83.359455</td>
      <td>83.725724</td>
      <td>1056600</td>
      <td>600.0</td>
      <td>94.0</td>
      <td>96.0</td>
      <td>95.0</td>
    </tr>
    <tr>
      <th>Thomas High School</th>
      <th>Charter</th>
      <td>1635</td>
      <td>83.418349</td>
      <td>83.848930</td>
      <td>1043130</td>
      <td>638.0</td>
      <td>93.0</td>
      <td>97.0</td>
      <td>95.0</td>
    </tr>
    <tr>
      <th>Wright High School</th>
      <th>Charter</th>
      <td>1800</td>
      <td>83.682222</td>
      <td>83.955000</td>
      <td>1049400</td>
      <td>583.0</td>
      <td>93.0</td>
      <td>97.0</td>
      <td>95.0</td>
    </tr>
    <tr>
      <th>Holden High School</th>
      <th>Charter</th>
      <td>427</td>
      <td>83.803279</td>
      <td>83.814988</td>
      <td>248087</td>
      <td>581.0</td>
      <td>93.0</td>
      <td>96.0</td>
      <td>94.5</td>
    </tr>
    <tr>
      <th>Bailey High School</th>
      <th>District</th>
      <td>4976</td>
      <td>77.048432</td>
      <td>81.033963</td>
      <td>3124928</td>
      <td>628.0</td>
      <td>67.0</td>
      <td>82.0</td>
      <td>74.5</td>
    </tr>
    <tr>
      <th>Hernandez High School</th>
      <th>District</th>
      <td>4635</td>
      <td>77.289752</td>
      <td>80.934412</td>
      <td>3022020</td>
      <td>652.0</td>
      <td>67.0</td>
      <td>81.0</td>
      <td>74.0</td>
    </tr>
    <tr>
      <th>Figueroa High School</th>
      <th>District</th>
      <td>2949</td>
      <td>76.711767</td>
      <td>81.158020</td>
      <td>1884411</td>
      <td>639.0</td>
      <td>66.0</td>
      <td>81.0</td>
      <td>73.5</td>
    </tr>
    <tr>
      <th>Ford High School</th>
      <th>District</th>
      <td>2739</td>
      <td>77.102592</td>
      <td>80.746258</td>
      <td>1763916</td>
      <td>644.0</td>
      <td>68.0</td>
      <td>79.0</td>
      <td>73.5</td>
    </tr>
    <tr>
      <th>Huang High School</th>
      <th>District</th>
      <td>2917</td>
      <td>76.629414</td>
      <td>81.182722</td>
      <td>1910635</td>
      <td>655.0</td>
      <td>66.0</td>
      <td>81.0</td>
      <td>73.5</td>
    </tr>
    <tr>
      <th>Johnson High School</th>
      <th>District</th>
      <td>4761</td>
      <td>77.072464</td>
      <td>80.966394</td>
      <td>3094650</td>
      <td>650.0</td>
      <td>66.0</td>
      <td>81.0</td>
      <td>73.5</td>
    </tr>
    <tr>
      <th>Rodriguez High School</th>
      <th>District</th>
      <td>3999</td>
      <td>76.842711</td>
      <td>80.744686</td>
      <td>2547363</td>
      <td>637.0</td>
      <td>66.0</td>
      <td>80.0</td>
      <td>73.0</td>
    </tr>
  </tbody>
</table>
</div>




```python
top_Perfoming_Schools = sortSummary.iloc[:5]
top_Perfoming_Schools
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
      <th></th>
      <th>Total Students</th>
      <th>Average Math Score</th>
      <th>Average Reading Score</th>
      <th>Total School Budget</th>
      <th>Per Student Budget</th>
      <th>% Passing Math</th>
      <th>% Passing Reading</th>
      <th>Overall Passing Rate</th>
    </tr>
    <tr>
      <th>school name</th>
      <th>type</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Cabrera High School</th>
      <th>Charter</th>
      <td>1858</td>
      <td>83.061895</td>
      <td>83.975780</td>
      <td>1081356</td>
      <td>582.0</td>
      <td>94.0</td>
      <td>97.0</td>
      <td>95.5</td>
    </tr>
    <tr>
      <th>Pena High School</th>
      <th>Charter</th>
      <td>962</td>
      <td>83.839917</td>
      <td>84.044699</td>
      <td>585858</td>
      <td>609.0</td>
      <td>95.0</td>
      <td>96.0</td>
      <td>95.5</td>
    </tr>
    <tr>
      <th>Wilson High School</th>
      <th>Charter</th>
      <td>2283</td>
      <td>83.274201</td>
      <td>83.989488</td>
      <td>1319574</td>
      <td>578.0</td>
      <td>94.0</td>
      <td>97.0</td>
      <td>95.5</td>
    </tr>
    <tr>
      <th>Griffin High School</th>
      <th>Charter</th>
      <td>1468</td>
      <td>83.351499</td>
      <td>83.816757</td>
      <td>917500</td>
      <td>625.0</td>
      <td>93.0</td>
      <td>97.0</td>
      <td>95.0</td>
    </tr>
    <tr>
      <th>Shelton High School</th>
      <th>Charter</th>
      <td>1761</td>
      <td>83.359455</td>
      <td>83.725724</td>
      <td>1056600</td>
      <td>600.0</td>
      <td>94.0</td>
      <td>96.0</td>
      <td>95.0</td>
    </tr>
  </tbody>
</table>
</div>




```python
bottom_Perfoming_Schools = sortSummary.iloc[-5:]
bottom_Perfoming_Schools
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
      <th></th>
      <th>Total Students</th>
      <th>Average Math Score</th>
      <th>Average Reading Score</th>
      <th>Total School Budget</th>
      <th>Per Student Budget</th>
      <th>% Passing Math</th>
      <th>% Passing Reading</th>
      <th>Overall Passing Rate</th>
    </tr>
    <tr>
      <th>school name</th>
      <th>type</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Figueroa High School</th>
      <th>District</th>
      <td>2949</td>
      <td>76.711767</td>
      <td>81.158020</td>
      <td>1884411</td>
      <td>639.0</td>
      <td>66.0</td>
      <td>81.0</td>
      <td>73.5</td>
    </tr>
    <tr>
      <th>Ford High School</th>
      <th>District</th>
      <td>2739</td>
      <td>77.102592</td>
      <td>80.746258</td>
      <td>1763916</td>
      <td>644.0</td>
      <td>68.0</td>
      <td>79.0</td>
      <td>73.5</td>
    </tr>
    <tr>
      <th>Huang High School</th>
      <th>District</th>
      <td>2917</td>
      <td>76.629414</td>
      <td>81.182722</td>
      <td>1910635</td>
      <td>655.0</td>
      <td>66.0</td>
      <td>81.0</td>
      <td>73.5</td>
    </tr>
    <tr>
      <th>Johnson High School</th>
      <th>District</th>
      <td>4761</td>
      <td>77.072464</td>
      <td>80.966394</td>
      <td>3094650</td>
      <td>650.0</td>
      <td>66.0</td>
      <td>81.0</td>
      <td>73.5</td>
    </tr>
    <tr>
      <th>Rodriguez High School</th>
      <th>District</th>
      <td>3999</td>
      <td>76.842711</td>
      <td>80.744686</td>
      <td>2547363</td>
      <td>637.0</td>
      <td>66.0</td>
      <td>80.0</td>
      <td>73.0</td>
    </tr>
  </tbody>
</table>
</div>




```python
Mathscores_byGrade = merge_df.groupby(["school name","grade"]).agg({"math_score":"mean"})                                                          
Mathscores_byGrade
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
      <th></th>
      <th>math_score</th>
    </tr>
    <tr>
      <th>school name</th>
      <th>grade</th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th rowspan="4" valign="top">Bailey High School</th>
      <th>10th</th>
      <td>76.996772</td>
    </tr>
    <tr>
      <th>11th</th>
      <td>77.515588</td>
    </tr>
    <tr>
      <th>12th</th>
      <td>76.492218</td>
    </tr>
    <tr>
      <th>9th</th>
      <td>77.083676</td>
    </tr>
    <tr>
      <th rowspan="4" valign="top">Cabrera High School</th>
      <th>10th</th>
      <td>83.154506</td>
    </tr>
    <tr>
      <th>11th</th>
      <td>82.765560</td>
    </tr>
    <tr>
      <th>12th</th>
      <td>83.277487</td>
    </tr>
    <tr>
      <th>9th</th>
      <td>83.094697</td>
    </tr>
    <tr>
      <th rowspan="4" valign="top">Figueroa High School</th>
      <th>10th</th>
      <td>76.539974</td>
    </tr>
    <tr>
      <th>11th</th>
      <td>76.884344</td>
    </tr>
    <tr>
      <th>12th</th>
      <td>77.151369</td>
    </tr>
    <tr>
      <th>9th</th>
      <td>76.403037</td>
    </tr>
    <tr>
      <th rowspan="4" valign="top">Ford High School</th>
      <th>10th</th>
      <td>77.672316</td>
    </tr>
    <tr>
      <th>11th</th>
      <td>76.918058</td>
    </tr>
    <tr>
      <th>12th</th>
      <td>76.179963</td>
    </tr>
    <tr>
      <th>9th</th>
      <td>77.361345</td>
    </tr>
    <tr>
      <th rowspan="4" valign="top">Griffin High School</th>
      <th>10th</th>
      <td>84.229064</td>
    </tr>
    <tr>
      <th>11th</th>
      <td>83.842105</td>
    </tr>
    <tr>
      <th>12th</th>
      <td>83.356164</td>
    </tr>
    <tr>
      <th>9th</th>
      <td>82.044010</td>
    </tr>
    <tr>
      <th rowspan="4" valign="top">Hernandez High School</th>
      <th>10th</th>
      <td>77.337408</td>
    </tr>
    <tr>
      <th>11th</th>
      <td>77.136029</td>
    </tr>
    <tr>
      <th>12th</th>
      <td>77.186567</td>
    </tr>
    <tr>
      <th>9th</th>
      <td>77.438495</td>
    </tr>
    <tr>
      <th rowspan="4" valign="top">Holden High School</th>
      <th>10th</th>
      <td>83.429825</td>
    </tr>
    <tr>
      <th>11th</th>
      <td>85.000000</td>
    </tr>
    <tr>
      <th>12th</th>
      <td>82.855422</td>
    </tr>
    <tr>
      <th>9th</th>
      <td>83.787402</td>
    </tr>
    <tr>
      <th rowspan="4" valign="top">Huang High School</th>
      <th>10th</th>
      <td>75.908735</td>
    </tr>
    <tr>
      <th>11th</th>
      <td>76.446602</td>
    </tr>
    <tr>
      <th>12th</th>
      <td>77.225641</td>
    </tr>
    <tr>
      <th>9th</th>
      <td>77.027251</td>
    </tr>
    <tr>
      <th rowspan="4" valign="top">Johnson High School</th>
      <th>10th</th>
      <td>76.691117</td>
    </tr>
    <tr>
      <th>11th</th>
      <td>77.491653</td>
    </tr>
    <tr>
      <th>12th</th>
      <td>76.863248</td>
    </tr>
    <tr>
      <th>9th</th>
      <td>77.187857</td>
    </tr>
    <tr>
      <th rowspan="4" valign="top">Pena High School</th>
      <th>10th</th>
      <td>83.372000</td>
    </tr>
    <tr>
      <th>11th</th>
      <td>84.328125</td>
    </tr>
    <tr>
      <th>12th</th>
      <td>84.121547</td>
    </tr>
    <tr>
      <th>9th</th>
      <td>83.625455</td>
    </tr>
    <tr>
      <th rowspan="4" valign="top">Rodriguez High School</th>
      <th>10th</th>
      <td>76.612500</td>
    </tr>
    <tr>
      <th>11th</th>
      <td>76.395626</td>
    </tr>
    <tr>
      <th>12th</th>
      <td>77.690748</td>
    </tr>
    <tr>
      <th>9th</th>
      <td>76.859966</td>
    </tr>
    <tr>
      <th rowspan="4" valign="top">Shelton High School</th>
      <th>10th</th>
      <td>82.917411</td>
    </tr>
    <tr>
      <th>11th</th>
      <td>83.383495</td>
    </tr>
    <tr>
      <th>12th</th>
      <td>83.778976</td>
    </tr>
    <tr>
      <th>9th</th>
      <td>83.420755</td>
    </tr>
    <tr>
      <th rowspan="4" valign="top">Thomas High School</th>
      <th>10th</th>
      <td>83.087886</td>
    </tr>
    <tr>
      <th>11th</th>
      <td>83.498795</td>
    </tr>
    <tr>
      <th>12th</th>
      <td>83.497041</td>
    </tr>
    <tr>
      <th>9th</th>
      <td>83.590022</td>
    </tr>
    <tr>
      <th rowspan="4" valign="top">Wilson High School</th>
      <th>10th</th>
      <td>83.724422</td>
    </tr>
    <tr>
      <th>11th</th>
      <td>83.195326</td>
    </tr>
    <tr>
      <th>12th</th>
      <td>83.035794</td>
    </tr>
    <tr>
      <th>9th</th>
      <td>83.085578</td>
    </tr>
    <tr>
      <th rowspan="4" valign="top">Wright High School</th>
      <th>10th</th>
      <td>84.010288</td>
    </tr>
    <tr>
      <th>11th</th>
      <td>83.836782</td>
    </tr>
    <tr>
      <th>12th</th>
      <td>83.644986</td>
    </tr>
    <tr>
      <th>9th</th>
      <td>83.264706</td>
    </tr>
  </tbody>
</table>
</div>




```python
mathbyGrade = pd.pivot_table(Mathscores_byGrade,index=["school name"],columns=["grade"])
mathbyGrade 
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead tr th {
        text-align: left;
    }

    .dataframe thead tr:last-of-type th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr>
      <th></th>
      <th colspan="4" halign="left">math_score</th>
    </tr>
    <tr>
      <th>grade</th>
      <th>10th</th>
      <th>11th</th>
      <th>12th</th>
      <th>9th</th>
    </tr>
    <tr>
      <th>school name</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Bailey High School</th>
      <td>76.996772</td>
      <td>77.515588</td>
      <td>76.492218</td>
      <td>77.083676</td>
    </tr>
    <tr>
      <th>Cabrera High School</th>
      <td>83.154506</td>
      <td>82.765560</td>
      <td>83.277487</td>
      <td>83.094697</td>
    </tr>
    <tr>
      <th>Figueroa High School</th>
      <td>76.539974</td>
      <td>76.884344</td>
      <td>77.151369</td>
      <td>76.403037</td>
    </tr>
    <tr>
      <th>Ford High School</th>
      <td>77.672316</td>
      <td>76.918058</td>
      <td>76.179963</td>
      <td>77.361345</td>
    </tr>
    <tr>
      <th>Griffin High School</th>
      <td>84.229064</td>
      <td>83.842105</td>
      <td>83.356164</td>
      <td>82.044010</td>
    </tr>
    <tr>
      <th>Hernandez High School</th>
      <td>77.337408</td>
      <td>77.136029</td>
      <td>77.186567</td>
      <td>77.438495</td>
    </tr>
    <tr>
      <th>Holden High School</th>
      <td>83.429825</td>
      <td>85.000000</td>
      <td>82.855422</td>
      <td>83.787402</td>
    </tr>
    <tr>
      <th>Huang High School</th>
      <td>75.908735</td>
      <td>76.446602</td>
      <td>77.225641</td>
      <td>77.027251</td>
    </tr>
    <tr>
      <th>Johnson High School</th>
      <td>76.691117</td>
      <td>77.491653</td>
      <td>76.863248</td>
      <td>77.187857</td>
    </tr>
    <tr>
      <th>Pena High School</th>
      <td>83.372000</td>
      <td>84.328125</td>
      <td>84.121547</td>
      <td>83.625455</td>
    </tr>
    <tr>
      <th>Rodriguez High School</th>
      <td>76.612500</td>
      <td>76.395626</td>
      <td>77.690748</td>
      <td>76.859966</td>
    </tr>
    <tr>
      <th>Shelton High School</th>
      <td>82.917411</td>
      <td>83.383495</td>
      <td>83.778976</td>
      <td>83.420755</td>
    </tr>
    <tr>
      <th>Thomas High School</th>
      <td>83.087886</td>
      <td>83.498795</td>
      <td>83.497041</td>
      <td>83.590022</td>
    </tr>
    <tr>
      <th>Wilson High School</th>
      <td>83.724422</td>
      <td>83.195326</td>
      <td>83.035794</td>
      <td>83.085578</td>
    </tr>
    <tr>
      <th>Wright High School</th>
      <td>84.010288</td>
      <td>83.836782</td>
      <td>83.644986</td>
      <td>83.264706</td>
    </tr>
  </tbody>
</table>
</div>




```python
ReadingbyGrade = merge_df.groupby(["school name","grade"]).agg({"reading_score":"mean"}) 
ReadingbyGrade['reading_score'] = ReadingbyGrade["reading_score"].astype(float).map("{:.2f}%".format)
ReadingbyGrade
#ReadingbyGrade = pd.pivot_table(ReadingbyGrade,index=["school name"],columns=["grade"])


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
      <th></th>
      <th>reading_score</th>
    </tr>
    <tr>
      <th>school name</th>
      <th>grade</th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th rowspan="4" valign="top">Bailey High School</th>
      <th>10th</th>
      <td>80.91%</td>
    </tr>
    <tr>
      <th>11th</th>
      <td>80.95%</td>
    </tr>
    <tr>
      <th>12th</th>
      <td>80.91%</td>
    </tr>
    <tr>
      <th>9th</th>
      <td>81.30%</td>
    </tr>
    <tr>
      <th rowspan="4" valign="top">Cabrera High School</th>
      <th>10th</th>
      <td>84.25%</td>
    </tr>
    <tr>
      <th>11th</th>
      <td>83.79%</td>
    </tr>
    <tr>
      <th>12th</th>
      <td>84.29%</td>
    </tr>
    <tr>
      <th>9th</th>
      <td>83.68%</td>
    </tr>
    <tr>
      <th rowspan="4" valign="top">Figueroa High School</th>
      <th>10th</th>
      <td>81.41%</td>
    </tr>
    <tr>
      <th>11th</th>
      <td>80.64%</td>
    </tr>
    <tr>
      <th>12th</th>
      <td>81.38%</td>
    </tr>
    <tr>
      <th>9th</th>
      <td>81.20%</td>
    </tr>
    <tr>
      <th rowspan="4" valign="top">Ford High School</th>
      <th>10th</th>
      <td>81.26%</td>
    </tr>
    <tr>
      <th>11th</th>
      <td>80.40%</td>
    </tr>
    <tr>
      <th>12th</th>
      <td>80.66%</td>
    </tr>
    <tr>
      <th>9th</th>
      <td>80.63%</td>
    </tr>
    <tr>
      <th rowspan="4" valign="top">Griffin High School</th>
      <th>10th</th>
      <td>83.71%</td>
    </tr>
    <tr>
      <th>11th</th>
      <td>84.29%</td>
    </tr>
    <tr>
      <th>12th</th>
      <td>84.01%</td>
    </tr>
    <tr>
      <th>9th</th>
      <td>83.37%</td>
    </tr>
    <tr>
      <th rowspan="4" valign="top">Hernandez High School</th>
      <th>10th</th>
      <td>80.66%</td>
    </tr>
    <tr>
      <th>11th</th>
      <td>81.40%</td>
    </tr>
    <tr>
      <th>12th</th>
      <td>80.86%</td>
    </tr>
    <tr>
      <th>9th</th>
      <td>80.87%</td>
    </tr>
    <tr>
      <th rowspan="4" valign="top">Holden High School</th>
      <th>10th</th>
      <td>83.32%</td>
    </tr>
    <tr>
      <th>11th</th>
      <td>83.82%</td>
    </tr>
    <tr>
      <th>12th</th>
      <td>84.70%</td>
    </tr>
    <tr>
      <th>9th</th>
      <td>83.68%</td>
    </tr>
    <tr>
      <th rowspan="4" valign="top">Huang High School</th>
      <th>10th</th>
      <td>81.51%</td>
    </tr>
    <tr>
      <th>11th</th>
      <td>81.42%</td>
    </tr>
    <tr>
      <th>12th</th>
      <td>80.31%</td>
    </tr>
    <tr>
      <th>9th</th>
      <td>81.29%</td>
    </tr>
    <tr>
      <th rowspan="4" valign="top">Johnson High School</th>
      <th>10th</th>
      <td>80.77%</td>
    </tr>
    <tr>
      <th>11th</th>
      <td>80.62%</td>
    </tr>
    <tr>
      <th>12th</th>
      <td>81.23%</td>
    </tr>
    <tr>
      <th>9th</th>
      <td>81.26%</td>
    </tr>
    <tr>
      <th rowspan="4" valign="top">Pena High School</th>
      <th>10th</th>
      <td>83.61%</td>
    </tr>
    <tr>
      <th>11th</th>
      <td>84.34%</td>
    </tr>
    <tr>
      <th>12th</th>
      <td>84.59%</td>
    </tr>
    <tr>
      <th>9th</th>
      <td>83.81%</td>
    </tr>
    <tr>
      <th rowspan="4" valign="top">Rodriguez High School</th>
      <th>10th</th>
      <td>80.63%</td>
    </tr>
    <tr>
      <th>11th</th>
      <td>80.86%</td>
    </tr>
    <tr>
      <th>12th</th>
      <td>80.38%</td>
    </tr>
    <tr>
      <th>9th</th>
      <td>80.99%</td>
    </tr>
    <tr>
      <th rowspan="4" valign="top">Shelton High School</th>
      <th>10th</th>
      <td>83.44%</td>
    </tr>
    <tr>
      <th>11th</th>
      <td>84.37%</td>
    </tr>
    <tr>
      <th>12th</th>
      <td>82.78%</td>
    </tr>
    <tr>
      <th>9th</th>
      <td>84.12%</td>
    </tr>
    <tr>
      <th rowspan="4" valign="top">Thomas High School</th>
      <th>10th</th>
      <td>84.25%</td>
    </tr>
    <tr>
      <th>11th</th>
      <td>83.59%</td>
    </tr>
    <tr>
      <th>12th</th>
      <td>83.83%</td>
    </tr>
    <tr>
      <th>9th</th>
      <td>83.73%</td>
    </tr>
    <tr>
      <th rowspan="4" valign="top">Wilson High School</th>
      <th>10th</th>
      <td>84.02%</td>
    </tr>
    <tr>
      <th>11th</th>
      <td>83.76%</td>
    </tr>
    <tr>
      <th>12th</th>
      <td>84.32%</td>
    </tr>
    <tr>
      <th>9th</th>
      <td>83.94%</td>
    </tr>
    <tr>
      <th rowspan="4" valign="top">Wright High School</th>
      <th>10th</th>
      <td>83.81%</td>
    </tr>
    <tr>
      <th>11th</th>
      <td>84.16%</td>
    </tr>
    <tr>
      <th>12th</th>
      <td>84.07%</td>
    </tr>
    <tr>
      <th>9th</th>
      <td>83.83%</td>
    </tr>
  </tbody>
</table>
</div>




```python
maxSpending = schoolSummary["Per Student Budget"].max()
minSpending = schoolSummary["Per Student Budget"].min()
maxSpending, minSpending
```




    (655.0, 578.0)




```python
#spendingBins = np.arange(minSpending,maxSpending+6,22
bins = [577,590,620,655]
group_names = ["less than $590","Between $590 and 619","Between $620 and 655"]

```


```python
schoolSummary["Spending Range"] = pd.cut(schoolSummary["Per Student Budget"], bins, labels=group_names)

schoolSummary
```

    C:\Users\Shanakay\Anaconda3\lib\site-packages\ipykernel_launcher.py:1: SettingWithCopyWarning: 
    A value is trying to be set on a copy of a slice from a DataFrame.
    Try using .loc[row_indexer,col_indexer] = value instead
    
    See the caveats in the documentation: http://pandas.pydata.org/pandas-docs/stable/indexing.html#indexing-view-versus-copy
      """Entry point for launching an IPython kernel.
    




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
      <th></th>
      <th>Total Students</th>
      <th>Average Math Score</th>
      <th>Average Reading Score</th>
      <th>Total School Budget</th>
      <th>Per Student Budget</th>
      <th>% Passing Math</th>
      <th>% Passing Reading</th>
      <th>Overall Passing Rate</th>
      <th>Spending Range</th>
    </tr>
    <tr>
      <th>school name</th>
      <th>type</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Bailey High School</th>
      <th>District</th>
      <td>4976</td>
      <td>77.048432</td>
      <td>81.033963</td>
      <td>3124928</td>
      <td>628.0</td>
      <td>67.0</td>
      <td>82.0</td>
      <td>74.5</td>
      <td>Between $620 and 655</td>
    </tr>
    <tr>
      <th>Cabrera High School</th>
      <th>Charter</th>
      <td>1858</td>
      <td>83.061895</td>
      <td>83.975780</td>
      <td>1081356</td>
      <td>582.0</td>
      <td>94.0</td>
      <td>97.0</td>
      <td>95.5</td>
      <td>less than $590</td>
    </tr>
    <tr>
      <th>Figueroa High School</th>
      <th>District</th>
      <td>2949</td>
      <td>76.711767</td>
      <td>81.158020</td>
      <td>1884411</td>
      <td>639.0</td>
      <td>66.0</td>
      <td>81.0</td>
      <td>73.5</td>
      <td>Between $620 and 655</td>
    </tr>
    <tr>
      <th>Ford High School</th>
      <th>District</th>
      <td>2739</td>
      <td>77.102592</td>
      <td>80.746258</td>
      <td>1763916</td>
      <td>644.0</td>
      <td>68.0</td>
      <td>79.0</td>
      <td>73.5</td>
      <td>Between $620 and 655</td>
    </tr>
    <tr>
      <th>Griffin High School</th>
      <th>Charter</th>
      <td>1468</td>
      <td>83.351499</td>
      <td>83.816757</td>
      <td>917500</td>
      <td>625.0</td>
      <td>93.0</td>
      <td>97.0</td>
      <td>95.0</td>
      <td>Between $620 and 655</td>
    </tr>
    <tr>
      <th>Hernandez High School</th>
      <th>District</th>
      <td>4635</td>
      <td>77.289752</td>
      <td>80.934412</td>
      <td>3022020</td>
      <td>652.0</td>
      <td>67.0</td>
      <td>81.0</td>
      <td>74.0</td>
      <td>Between $620 and 655</td>
    </tr>
    <tr>
      <th>Holden High School</th>
      <th>Charter</th>
      <td>427</td>
      <td>83.803279</td>
      <td>83.814988</td>
      <td>248087</td>
      <td>581.0</td>
      <td>93.0</td>
      <td>96.0</td>
      <td>94.5</td>
      <td>less than $590</td>
    </tr>
    <tr>
      <th>Huang High School</th>
      <th>District</th>
      <td>2917</td>
      <td>76.629414</td>
      <td>81.182722</td>
      <td>1910635</td>
      <td>655.0</td>
      <td>66.0</td>
      <td>81.0</td>
      <td>73.5</td>
      <td>Between $620 and 655</td>
    </tr>
    <tr>
      <th>Johnson High School</th>
      <th>District</th>
      <td>4761</td>
      <td>77.072464</td>
      <td>80.966394</td>
      <td>3094650</td>
      <td>650.0</td>
      <td>66.0</td>
      <td>81.0</td>
      <td>73.5</td>
      <td>Between $620 and 655</td>
    </tr>
    <tr>
      <th>Pena High School</th>
      <th>Charter</th>
      <td>962</td>
      <td>83.839917</td>
      <td>84.044699</td>
      <td>585858</td>
      <td>609.0</td>
      <td>95.0</td>
      <td>96.0</td>
      <td>95.5</td>
      <td>Between $590 and 619</td>
    </tr>
    <tr>
      <th>Rodriguez High School</th>
      <th>District</th>
      <td>3999</td>
      <td>76.842711</td>
      <td>80.744686</td>
      <td>2547363</td>
      <td>637.0</td>
      <td>66.0</td>
      <td>80.0</td>
      <td>73.0</td>
      <td>Between $620 and 655</td>
    </tr>
    <tr>
      <th>Shelton High School</th>
      <th>Charter</th>
      <td>1761</td>
      <td>83.359455</td>
      <td>83.725724</td>
      <td>1056600</td>
      <td>600.0</td>
      <td>94.0</td>
      <td>96.0</td>
      <td>95.0</td>
      <td>Between $590 and 619</td>
    </tr>
    <tr>
      <th>Thomas High School</th>
      <th>Charter</th>
      <td>1635</td>
      <td>83.418349</td>
      <td>83.848930</td>
      <td>1043130</td>
      <td>638.0</td>
      <td>93.0</td>
      <td>97.0</td>
      <td>95.0</td>
      <td>Between $620 and 655</td>
    </tr>
    <tr>
      <th>Wilson High School</th>
      <th>Charter</th>
      <td>2283</td>
      <td>83.274201</td>
      <td>83.989488</td>
      <td>1319574</td>
      <td>578.0</td>
      <td>94.0</td>
      <td>97.0</td>
      <td>95.5</td>
      <td>less than $590</td>
    </tr>
    <tr>
      <th>Wright High School</th>
      <th>Charter</th>
      <td>1800</td>
      <td>83.682222</td>
      <td>83.955000</td>
      <td>1049400</td>
      <td>583.0</td>
      <td>93.0</td>
      <td>97.0</td>
      <td>95.0</td>
      <td>less than $590</td>
    </tr>
  </tbody>
</table>
</div>




```python
scoresbySchoolSpending = schoolSummary.groupby("Spending Range").agg({'Average Math Score':"mean",
                                                                     'Average Reading Score':"mean",
                                                                     '% Passing Math':"mean",
                                                                     '% Passing Reading':"mean",
                                                                     'Overall Passing Rate':"mean"})

scoresbySchoolSpending['Average Math Score'] = scoresbySchoolSpending["Average Math Score"].astype(float).map("{:.2f}%".format)
scoresbySchoolSpending['Average Reading Score'] = scoresbySchoolSpending["Average Reading Score"].astype(float).map("{:.2f}%".format)
scoresbySchoolSpending['% Passing Math'] = scoresbySchoolSpending["% Passing Math"].astype(float).map("{:.2f}%".format)
scoresbySchoolSpending['% Passing Reading'] = scoresbySchoolSpending["% Passing Reading"].astype(float).map("{:.2f}%".format)
scoresbySchoolSpending['Overall Passing Rate'] = scoresbySchoolSpending["Overall Passing Rate"].astype(float).map("{:.2f}%".format)

scoresbySchoolSpending
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
      <th>Average Math Score</th>
      <th>Average Reading Score</th>
      <th>% Passing Math</th>
      <th>% Passing Reading</th>
      <th>Overall Passing Rate</th>
    </tr>
    <tr>
      <th>Spending Range</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>less than $590</th>
      <td>83.46%</td>
      <td>83.93%</td>
      <td>93.50%</td>
      <td>96.75%</td>
      <td>95.12%</td>
    </tr>
    <tr>
      <th>Between $590 and 619</th>
      <td>83.60%</td>
      <td>83.89%</td>
      <td>94.50%</td>
      <td>96.00%</td>
      <td>95.25%</td>
    </tr>
    <tr>
      <th>Between $620 and 655</th>
      <td>78.39%</td>
      <td>81.60%</td>
      <td>72.44%</td>
      <td>84.33%</td>
      <td>78.39%</td>
    </tr>
  </tbody>
</table>
</div>




```python
maxSize = schoolSummary['Total Students'].max()
minSize = schoolSummary['Total Students'].min()
minSize,maxSize
```




    (427, 4976)




```python
#sizeBins = np.arange(minSize,maxSize,1000)
sizeBins = [426,1000,3000,5000]
szGroup = ["Small(<1000)","Medium(1000-3000)","Large(3000-5000)"]
```


```python
schoolSummary['School Size']=pd.cut(schoolSummary["Total Students"],sizeBins,labels=szGroup)
```


```python
scoresBySchoolSize = schoolSummary.groupby("School Size").agg({'Average Math Score':"mean",
                                                                     'Average Reading Score':"mean",
                                                                     '% Passing Math':"mean",
                                                                     '% Passing Reading':"mean",
                                                                     'Overall Passing Rate':"mean"})

scoresBySchoolSize['Average Math Score'] = scoresBySchoolSize["Average Math Score"].astype(float).map("{:.2f}%".format)
scoresBySchoolSize['Average Reading Score'] = scoresBySchoolSize["Average Reading Score"].astype(float).map("{:.2f}%".format)
scoresBySchoolSize['% Passing Math'] = scoresBySchoolSize["% Passing Math"].astype(float).map("{:.2f}%".format)
scoresBySchoolSize['% Passing Reading'] = scoresBySchoolSize["% Passing Reading"].astype(float).map("{:.2f}%".format)
scoresBySchoolSize['Overall Passing Rate'] = scoresBySchoolSize["Overall Passing Rate"].astype(float).map("{:.2f}%".format)

scoresBySchoolSize
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
      <th>Average Math Score</th>
      <th>Average Reading Score</th>
      <th>% Passing Math</th>
      <th>% Passing Reading</th>
      <th>Overall Passing Rate</th>
    </tr>
    <tr>
      <th>School Size</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Small(&lt;1000)</th>
      <td>83.82%</td>
      <td>83.93%</td>
      <td>94.00%</td>
      <td>96.00%</td>
      <td>95.00%</td>
    </tr>
    <tr>
      <th>Medium(1000-3000)</th>
      <td>81.18%</td>
      <td>82.93%</td>
      <td>84.56%</td>
      <td>91.33%</td>
      <td>87.94%</td>
    </tr>
    <tr>
      <th>Large(3000-5000)</th>
      <td>77.06%</td>
      <td>80.92%</td>
      <td>66.50%</td>
      <td>81.00%</td>
      <td>73.75%</td>
    </tr>
  </tbody>
</table>
</div>




```python
scoresBySchoolType = schoolSummary.groupby("type").agg({'Average Math Score':"mean",
                          S                                           'Average Reading Score':"mean",
                                                                     '% Passing Math':"mean",
                                                                     '% Passing Reading':"mean",
                                                                     'Overall Passing Rate':"mean"})

scoresBySchoolType['Average Math Score'] = scoresBySchoolType["Average Math Score"].astype(float).map("{:.2f}%".format)
scoresBySchoolType['Average Reading Score'] = scoresBySchoolType["Average Reading Score"].astype(float).map("{:.2f}%".format)
scoresBySchoolType['% Passing Math'] = scoresBySchoolType["% Passing Math"].astype(float).map("{:.2f}%".format)
scoresBySchoolType['% Passing Reading'] = scoresBySchoolType["% Passing Reading"].astype(float).map("{:.2f}%".format)
scoresBySchoolType['Overall Passing Rate'] = scoresBySchoolType["Overall Passing Rate"].astype(float).map("{:.2f}%".format)

scoresBySchoolType
```


      File "<ipython-input-36-d7653253a381>", line 2
        S                                           'Average Reading Score':"mean",
                                                                          ^
    SyntaxError: invalid syntax
    



```python
#schoolSummary["Average Math Score"]=schoolSummary["Average Math Score"].astype(float).map("{:.2f}%".format)
#schoolSummary["Average Reading Score"]=schoolSummary["Average Reading Score"].astype(float).map("{:.2f}%".format)
#schoolSummary["Total School Budget"]=schoolSummary["Total School Budget"].astype(float).map("${:,.2f}".format)
#schoolSummary["Per Student Budget"]=schoolSummary["Per Student Budget"].astype(float).map("${:.2f}".format)
#schoolSummary["% Passing Math"]=schoolSummary["% Passing Math"].astype(float).map("{:.2f}%".format)
#schoolSummary["% Passing Reading"]=schoolSummary["% Passing Reading"].astype(float).map("{:.2f}%".format)
#schoolSummary["Overall Passing Rate"]=schoolSummary["Overall Passing Rate"].astype(float).map("{:.2f}%".format)


```
