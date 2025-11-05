This project is an example based on class materials, where our goal was to understand how tools such as:
1. matplotlib.plot
2. seaborn
3. sqllite

work in real projects. Based on guidance, I've run several codes, to find out the outcome of information which was really meaningfull to me. 

Dataset souce: 
Provided by JustIt, you can find it in the 'dataset' folder

After reviewing dataset, i felt very curious about the exact numbember os several points:


1. Average score of students by their gender and their class, for getting an outcome i've used a pivot table function and then broght it to visual

pivot_df = df.pivot_table(index='class', columns='gender', values='score', aggfunc='mean')

![alt text](<visuals/Average score by gender.png>)


2. Next interesting point for me was to get number of students on each grade (A, B, C, D) in a descending manner. 

df['grade'] = pd.cut(
    df['score'],
    bins=[-1, 59, 69, 84, 100],
    labels=['D', 'C', 'B', 'A']
)
top10 = df.sort_values(by='score', ascending=False).head(10)

![alt text](<visuals/marks in class.png>)

3. And the final point which i felt very curious about, is to find a top-10 students by ID in the class

df = df.sort_values(by='score', ascending=False)

top10 = df.head(10)

![alt text](<visuals/top-10 by ID.png>)



