# The Analysis

## 1. What are the most demanded skills for the Top 3 most popular data roles?

To find the most demanded skills for the top 3 most pouploar data roles. I filtered out those positions by which ones were the most popular, and got the top 5 skills for these top 3 roles. This query highlightes the most popular job titles and their top skills, showing which skills I should pay attention to depending on the role I'm targeting

View my notebook with detailed steps here: [2_Skill_Demand.ipynb](3_Project/2_Skill_Demand.ipynb)

### Visualize Data
```python
fig, ax = plt.subplots(len(job_titles), 1)

sns.set_theme(style='ticks')
for i, job_title in enumerate(job_titles):
    df_plot = df_skills_perc[df_skills_perc['job_title_short'] == job_title].head(5)
    sns.barplot(data=df_plot, x='skill_percent', y='job_skills', ax=ax[i], hue='skill_count', palette='dark:b_r')
    ax[i].set_title(job_title)
    ax[i].set_ylabel('')
    ax[i].set_xlabel('')
    ax[i].get_legend().remove()
    ax[i].set_xlim(0,78)

    for n, v in enumerate(df_plot['skill_percent']):
        ax[i].text(v+1, n, f'{v:.0f}%', va='center')
    
    if i != len(job_titles) -1:
        ax[i].set_xticks([])

fig.suptitle('Likelihood of Skills Requested in US Job Postings', fontsize=15)
fig.tight_layout(h_pad=0.5)
plt.show()
```

### Results
![Visualization of Top Skills for Data Nerds](3_Project/images/Skill_Demand.png)

### Insights
- Blah
- Blah blah
- Blah blah blah


# Trending Skills

## Results
![Visualization of Trending Skills](3_Project/images/Trending_Skills.png)

# Salary Analysis for Data Nerds

## Results

![Visualization of Median Salary](3_Project/images/Median_Salary.png)



![Visualization of Top Salary Skills](3_Project/images/Top_Skill_Salary.png)



![Visualization Scatter](3_Project/images/scatter.png)

