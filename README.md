# The Analysis

# 1. The 5 most demanded skills for Top 3 most demanded jobs.

![visualization of 5 most demanded skills for Top 3 most demanded jobs](3_project\images\most_demanded_skills_for_top3_jobs.png)

As we can see here, python and sql are one of the most common skills if we want to do data jobs.

source here: [2_skill_demand](3_project\2_skill_demand.ipynb)

# The insights
1. We should really learn sql if we want to work a data job. We have at least 50% chance to meet the required skill for each job application like that.

2. After sql, we should compliment our skills by learning python. 


# 2. The trend for the demanded skill for Data Analyst

```python

# sorts by count
df_DA_US_pivot=df_pivot.copy()
df_DA_US_pivot.loc['Total'] = df_DA_US_pivot.sum()
df_DA_US_pivot = df_DA_US_pivot[df_DA_US_pivot.loc['Total'].sort_values(ascending=False).index]
df_DA_US_pivot = df_DA_US_pivot.drop('Total')

df_DA_US_pivot

```
Visualization

![Job skill trend percentage](3_project\images\job_skill_trend_percentage.png)
Source: [3_skill_trend](3_project\3_skill_trend.ipynb)

# The Insights

1. It never hurt to know sql. This is the most demanded skill throughout all year round, even though the trend falls a little toward the end.

2. Python and Tableau are similar in demand. 

# 3. The Salary Distribution for the Top 3 jobs and Their Senior Roles


```python

sns.boxplot(data=df_US_top6, x='salary_year_avg', y='job_title_short', order=job_order)
sns.despine()

# this is all the same
plt.title('Salary Distributions of Data Jobs in the US')
plt.xlabel('Yearly Salary (USD)')
plt.ylabel('')
plt.xlim(0, 600000) 
ticks_x = plt.FuncFormatter(lambda y, pos: f'${int(y/1000)}K')
plt.gca().xaxis.set_major_formatter(ticks_x)
plt.show()

```
The result:

![Salary Distribution for Data Jobs](3_project\images\salary_dist_for_data_jobs.png)

# The Insights

1. Senior Data Scientist is the most paying job. 
2. Even though Senior Data Analyst is a senior role, it tend to pay less than Data Scientists and Data Engineers.
3. If you are looking to advance the career from the Data Analyst, rather than the senior role, it pays more to advance to Data Engineer or Data Scientist role. And We even have the option to advance further more to their senior roles after some experience.

# 5. Skill Demand vs Salary(median)

![Demand vs Salary Scatter Plot](3_project\images\skill_demand_vs_salary.png)

# The Insights
1. There are no clear cut skill that clearly pay the most and is the most demanded.
2. Python and Sql are the most worthy skills to learn. Learn Python if one wants more salary and learn Sql if one wants to get jobs quicker or want to choose the workplace more abundantly.
3. Microsoft skills tend to pay lower but Excel is one of the most demanded skills.

# TLDR
Learn Sql and Python if you want a data related job.


