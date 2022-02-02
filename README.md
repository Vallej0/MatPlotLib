Initial Preparation


In this project I ran the provided package dependency and data imports, then merged the mouse_metadata and study_results DataFrames into a single DataFrame. I then displayed the number of unique mice IDs in the data, then check for any mouse ID with duplicate time points. Display the data associated with that mouse ID, 
then created a new DataFrame where this data is removed.

The cleaned DataFrame was used for the remaining steps.

The unique number of mice was displayed.And summary statistics run.



Summary Statistics

Two summary statistics tables:

For the first table, I used the groupby method to generate the mean, median, variance, standard deviation, and SEM of the tumor volume for each drug regimen. This resulted in five unique series objects.They were combined into a single summary statistics table.
For the second table, I used the agg method to produce the same summary statistics table using a single line of code.




Bar and Pie Charts


Two bar plots generated:

Both plots are identical and showed the total number of timepoints for all mice tested for each drug regimen throughout the course of the study.
First bar plot I used Pandas's DataFrame.plot() method.
Second bar plot I used Matplotlib's pyplot methods.



Two pie plots generated:

Both of these plots were identical and show the distribution of female or male mice in the study.
First pie plot used both Pandas's DataFrame.plot().
Second pie plot used Matplotlib's pyplot methods.




Quartiles, Outliers and Boxplots


I then calculated the final tumor volume of each mouse across four of the most promising treatment regimens: Capomulin, Ramicane, Infubinol, and Ceftamin. Calculate the quartiles and IQR and quantitatively determined if there were any potential outliers across all four treatment regimens.

I started by creating a grouped DataFrame that shows the last (greatest) time point for each mouse, then merged this grouped DataFrame with the original cleaned DataFrame.
Next, I created a list that holds the treatment names, as well as a second, empty list that holds the tumor volume data.


I used Matplotlib, to generate a box and whisker plot of the final tumor volume for all four treatment regimens and highlight any potential outliers in the plot by changing their color and style.


Line and Scatter Plots

I selected mouse: b128 that was treated with Capomulin and generate a line plot of tumor volume vs. time point for that mouse.



I generated a scatter plot of tumor volume versus mouse weight for the Capomulin treatment regimen.



Correlation and Regression

I calculated the correlation coefficient and linear regression model between mouse weight and average tumor volume for the Capomulin treatment. I then plotted the linear regression model on top of the previous scatter plot.


Final Analysis

# 1st Observation: Capomulin and Ramicane worked better at reducing the size of the tumors compared to Infubinol and Ceftamin.
#Although there were more timepoints for them it was not enough to justify the amount of tumor reductions. 

#2nd Observation: Mouse b128, who was on Capomulin, had a decrease in tumor volume until the timepoints 35 - 45, at which point,
# not only did the tumor volume begin to increase but so did the metastatic sites. This could be due to injection/adminstration
# site/method, sex, or possibly lifestyle (diet, activity levels) habits.
