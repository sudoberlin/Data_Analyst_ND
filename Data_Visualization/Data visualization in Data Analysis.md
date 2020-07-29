

# Data visualization in Data Analysis

There are two main reasons for creating visuals using data:

1. **Exploratory** analysis is done when you are searching for insights. These visualizations don't need to be perfect. You are using plots to find insights, but they don't need to be aesthetically appealing. You are the consumer of these plots, and you need to be able to find the answer to your questions from these plots.
2. **Explanatory** analysis is done when you are providing your results for others. These visualizations need to provide you the emphasis necessary to convey your message. They should be accurate, insightful, and visually appealing.

The five steps of the data analysis process:

1. **Extract** - Obtain the data from a spreadsheet, SQL, the web, etc.
2. **Clean** - Here we could use expl**or**atory visuals.
3. **Explore** - Here we use expl**or**atory visuals.
4. **Analyze** - Here we might use either expl**or**atory or expl**an**atory visuals.
5. **Share** - Here is where expl**an**atory visuals live.

# Design of visualizations

## The Four Levels of Measurement

In order to choose an appropriate plot type or method of analysis for your data, you need to understand the types of data you have. One common method divides the data into four **levels of measurement**:

#### **Qualitative** or categorical types (non-numeric types)

- **1. Nominal data**: pure labels without inherent order (no label is intrinsically greater or less than any other)
- **2. Ordinal data**: labels with an intrinsic order or ranking (comparison operations can be made between values, but the magnitude of differences are not be well-defined)

#### **Quantitative** or numeric types

- **3. Interval data**: numeric values where absolute differences are meaningful (addition and subtraction operations can be made)
- **4. Ratio data**: numeric values where relative differences are meaningful (multiplication and division operations can be made)

All quantitative-type variables also come in one of two varieties: **discrete** and **continuous**.

- **Discrete** quantitative variables can only take on a specific set values at some maximum level of precision.
- **Continuous** quantitative variables can (hypothetically) take on values to any level of precision.

Distinguishing between continuous and discrete can be a little tricky – a rule of thumb is if there are few levels, and values can't be subdivided into further units, then it's discrete. Otherwise, it's continuous. If you have a scale that can only take natural number values between 1 and 5, that's discrete. A quantity that can be measured to two digits, e.g. 2.72, is best characterized as continuous, since we might hypothetically be able to measure to even more digits, e.g. 2.718. A tricky case like test scores measured between 0 and 100 can only be divided down to single integers, making it initially seem discrete. But since there are so many values, such a feature is usually considered as continuous.

When exploring your data, the most important thing to consider first is whether your data is qualitative or quantitative. In later lessons, you will see how this distinction impacts your choice of plots.

## Likert Scale

One form of data you might encounter is response data to a **Likert scale** like the ones below.

![5-point Likert scale](https://video.udacity-data.com/topher/2018/January/5a6257fa_likertscale/likertscale.png)

*This Likert scale, which happens to be graphical, has five points, allowing for neutrality (source: surveygizmo)*

![Six-point Likert scale](https://video.udacity-data.com/topher/2018/January/5a625880_6-point-likert-scale-even-survey/6-point-likert-scale-even-survey.png)

*This Likert scale has six points, not allowing for neutrality (source: fieldboom)*

What level of measurement should you consider for this kind of data? Technically, responses on these kinds of questions should be considered *ordinal* in nature. There is a clear order in response values, but it may not be the case that the differences between consecutive levels are consistent in size. The criteria to move between Strongly Disagree and Disagree might be different from the criteria between Agree and Strongly Agree. However, Likert data is often treated as *interval* to simplify analyses. If you have data like this, make sure you use exploratory data visualizations to make a good judgment on how your data should be treated later on in the analysis process.



# Another Look

To break down our data types, there are two main blocks:

**Quantitative** and **Categorical**

**Quantitative** can be further divided into `Continuous` or `Discrete`.

**Categorical** data can be divided into `Ordinal` or `Nominal`.

You should have now mastered what types of data in the world around us falls into each of these four buckets: Discrete, Continuous, Nominal, and Ordinal. In the next sections, we will work through the numeric summaries that relate specifically to quantitative variables.

------

# Quantitative vs. Categorical

Some of these can be a bit tricky - notice even though zip codes are a number, they aren’t really a quantitative variable. If we add two zip codes together, we do not obtain any useful information from this new value. Therefore, this is a categorical variable.

**Height**, **Age**, the **Number of Pages in a Book** and **Annual Income** all take on values that we can add, subtract and perform other operations with to gain useful insight. Hence, these are `quantitative`.

**Gender**, **Letter Grade**, **Breakfast Type**, **Marital Status**, and **Zip Code** can be thought of as labels for a group of items or individuals. Hence, these are `categorical`.

------

# Continuous vs. Discrete

To consider if we have continuous or discrete data, we should see if we can split our data into smaller and smaller units. Consider time - we could measure an event in years, months, days, hours, minutes, or seconds, and even at seconds we know there are smaller units we could measure time in. Therefore, we know this data type is continuous. **Height**, **age**, and **income** are all examples of `continuous data`. Alternatively, the **number of pages in a book**, **dogs I count outside a coffee shop**, or **trees in a yard** are `discrete data`. We would not want to split our dogs in half.

------

# Ordinal vs. Nominal

In looking at categorical variables, we found **Gender**, **Marital Status**, **Zip Code** and your **Breakfast items** are `nominal variables` where there is no order ranking associated with this type of data. Whether you ate cereal, toast, eggs, or only coffee for breakfast; there is no rank ordering associated with your breakfast.

Alternatively, the **Letter Grade** or **Survey Ratings** have a rank ordering associated with it, as `ordinal data`. If you receive an A, this is higher than an A-. An A- is ranked higher than a B+, and so on... Ordinal variables frequently occur on rating scales from very poor to very good. In many cases we turn these ordinal variables into numbers, as we can more easily analyze them, but more on this later!



### Design Integrity Notes

It is key that when you build plots you maintain integrity for the underlying data.

One of the main ways discussed here for looking at data integrity was with the **lie factor**. Lie factor depicts the degree to which a visualization distorts or misrepresents the data values being plotted. It is calculated in the following way:

\text{lie factor} =\frac{\Delta \text{visual}/\text{visual}_\text{start}}{\Delta \text{data}/\text{data}_\text{start}}lie factor=Δdata/datastartΔvisual/visualstart

The delta symbol (\DeltaΔ) stands for difference or change. In words, the lie factor is the relative change shown in the graphic divided by the actual relative change in the data. Ideally, the lie factor should be 1: any other value means that there is some mismatch in the ratio of depicted change to actual change.

------

### Lie Factor in the Video

The lie factor shown in the video was in comparing the largest to the smallest doctor in terms of pixels.

![img](https://video.udacity-data.com/topher/2017/September/59ac937a_pasted-image-0/pasted-image-0.png)

The number of pixels related to the largest image is 79,000 and 16,500 for the smallest. The percentage change is 27% to 12%. So, the lie factor is calculated as:

\text{lie factor} =\frac{(79000-16500)/16500}{(27-12)/12} = 3.03lie factor=(27−12)/12(79000−16500)/16500=3.03

### Further Reading

- Flowing Data: [How to Spot Visualization Lies](https://flowingdata.com/2017/02/09/how-to-spot-visualization-lies/)

#### Supporting Materials

[** How to Spot Visualization Lies](https://video.udacity-data.com/topher/2019/November/5dc4a59c_how-to-spot-visualization-lies-flowingdata/how-to-spot-visualization-lies-flowingdata.pdf)





### Additional Encodings

As seen earlier in the lesson, we typically try to use position on the x- and y- axes to encode, or depict the value of variables. If we have more than two variables, however, we have to start considering other visual encodings for the additional variables.

In general, **color and shape** are best for **categorical** variables, while the **size of marker** can assist in adding additional **quantitative data**, as we demonstrated here.

Only use these additional encodings when absolutely necessary. Often, overuse of these additional encodings suggest you are providing too much information in a single plot. **Instead, it might be better to break the information into multiple individual messages**, so the audience can understand every aspect of your message. You can also build in each aspect one at a time, which you saw in the previous lesson with [Hans Rosling](https://classroom.udacity.com/nanodegrees/nd098/parts/05a8ba39-eb63-426e-9b98-755883bc81d6/modules/f922e0f7-d718-4d00-a0e7-13b8498cf7d3/lessons/4535e649-760e-466d-a3e3-18440486dbd1/concepts/6719321b-ecaa-4342-bbed-63bd404408e4). This feels less overwhelming than if you just saw this plot all at once.

### Extra: Code

Some of the plots in this presentation were created using the programming language R, and a very popular library known as **ggplot2**. Though this is beyond the scope of this course, the code used to create these visualizations is provided below:

```python
install.packages('ggplot2')
library(ggplot2)

df = read.csv(file.choose()) #select your dataset 
df2 = head(df, 30)


qplot(df2$Math.SAT, df2$Verbal.SAT, xlab = 'Math SAT Score', 
      ylab = 'Verbal SAT Score', main = 'Average SAT Scores By College')

qplot(df2$Math.SAT, df2$Verbal.SAT, xlab = 'Math SAT Score', 
      ylab = 'Verbal SAT Score', main = 'Average SAT Scores By College', 
      color = as.factor(df2$Public..1...Private..2.))

qplot(df2$Math.SAT, df2$Verbal.SAT, xlab = 'Math SAT Score',
      ylab = 'Verbal SAT Score', main = 'Average SAT Scores By College',
      shape = as.factor(df2$Public..1...Private..2.), color = df2$stud..fac..ratio)

ggplot(df2, aes(x=Math.SAT, y=Verbal.SAT, group=stud..fac..ratio)) +
  geom_point(aes(shape=stud..fac..ratio, color=as.factor(df2$Public..1...Private..2.))
```







# Univariate Exploration Of Data





## What is Tidy Data?

In this course, it is expected that your data is organized in some kind of tidy format. In short, a [tidy dataset](https://cran.r-project.org/web/packages/tidyr/vignettes/tidy-data.html) is a tabular dataset where:

- each variable is a column
- each observation is a row
- each type of observational unit is a table

The first three images below depict a tidy dataset. This tidy dataset is in the field of healthcare and has two tables: one for patients (with their patient ID, name, and age) and one for treatments (with patient ID, what drug that patient is taking, and the dose of that drug).

![An image of two tables (patients and treatments) with all of the individual columns highlighted](https://video.udacity-data.com/topher/2018/January/5a6278e8_tidy-data-one/tidy-data-one.png)

*Each variable in a tidy dataset must have its own column*

![An image of two tables (patients and treatments) with all of the individual rows highlighted](https://video.udacity-data.com/topher/2018/January/5a6278ea_tidy-data-two/tidy-data-two.png)

*Each observation in a tidy dataset must have its own row*

![An image of two tables (patients and treatments) with each table highlighted](https://video.udacity-data.com/topher/2018/January/5a6278ec_tidy-data-three/tidy-data-three.png)

*Each observational unit in a tidy dataset must have its own table*

The next image depicts the same data but in one representation of a non-tidy format (there are other possible non-tidy representations). The *Drug A*, *Drug B*, and *Drug C* columns should form one 'Drug' column, since this is one variable. The entire table should be separated into two tables: a patients table and a treatments table.

![A non-tidy representation of the patients and treatments table. Each variable does not form a column and one table exists for two observational units.](https://video.udacity-data.com/topher/2018/January/5a6278e7_tidy-data-four/tidy-data-four.png)

*Only the second rule of tidy data is satisfied in this non-tidy representation of the above data: each observation forms a row*

While the data provided to you in the course will all be tidy, in practice, you may need to perform tidying work before exploration. You should be comfortable with reshaping your data or perform transformations to split or combine features in your data, resulting in new data columns. This work should be performed in the wrangling stage of the data analysis process, so if you need to know more about these operations, it is recommended that you refer back to the data wrangling content from earlier in the program.

This is also not to say that tidy data is the *only* useful form that data can take. In fact, as you work with a dataset, you might need to summarize it in a non-tidy form in order to generate appropriate visualizations. You'll see one example of this in the bivariate plotting lesson, where categorical counts need to put into a matrix form in order to create a heat map.



## Bar Charts

A **bar chart** is used to depict the distribution of a categorical variable. In a bar chart, each level of the categorical variable is depicted with a bar, whose height indicates the frequency of data points that take on that level. A basic bar chart of frequencies can be created through the use of seaborn's [`countplot`](https://seaborn.pydata.org/generated/seaborn.countplot.html) function:

```python
sb.countplot(data = df, x = 'cat_var')

```

![img](https://video.udacity-data.com/topher/2018/March/5aa9b7c3_l3-c03-barchart1/l3-c03-barchart1.png)

For the example given, you can see that the Beta level has the highest frequency at over 100 counts, followed by Gamma and Alpha, with Delta the least frequent at around 50. By default, each category is given a different color. This might come in handy for building associations between these category labels and encodings in plots with more variables. Otherwise, it's a good idea to simplify the plot and reduce unnecessary distractions by plotting all bars in the same color. This can be set using the "color" parameter:

```python
base_color = sb.color_palette()[0]
sb.countplot(data = df, x = 'cat_var', color = base_color)

```

[`color_palette`](https://seaborn.pydata.org/generated/seaborn.color_palette.html) returns a list of RGB tuples. Each tuple consists of three digits specifying the red, green, and blue channel values to specify a color. Calling this function without any parameters returns the current / default palette, and we take the first color to be the color for all bars.

![img](https://video.udacity-data.com/topher/2018/March/5aa9bcf3_l3-c03-barchart2/l3-c03-barchart2.png)

One thing that we might want to do with a bar chart is to sort the data in some way. For nominal-type data, one common operation is to sort the data in terms of frequency. With our data in a pandas DataFrame, we can use various DataFrame methods to compute and extract an ordering, then set that ordering on the "order" parameter:

```python
base_color = sb.color_palette()[0]
cat_order = df['cat_var'].value_counts().index
sb.countplot(data = df, x = 'cat_var', color = base_color, order = cat_order)

```

(Documentation: [`Series.value_counts()`](https://pandas.pydata.org/pandas-docs/stable/generated/pandas.Series.value_counts.html))

![img](https://video.udacity-data.com/topher/2018/March/5aa9c9b7_l3-c03-barchart3/l3-c03-barchart3.png)

For ordinal-type data, we probably want to sort the bars in order of the variables. While we could sort the levels by frequency like above, we usually care about whether the most frequent values are at high levels, low levels, etc. The best thing for us to do in this case is to convert the column into an ordered categorical data type. By default, pandas reads in string data as object types, and will plot the bars in the order in which the unique values were seen. By converting the data into an ordered type, the order of categories becomes innate to the feature, and we won't need to specify an "order" parameter each time it's required in a plot.

```python
# this method requires pandas v0.21 or later
level_order = ['Alpha', 'Beta', 'Gamma', 'Delta']
ordered_cat = pd.api.types.CategoricalDtype(ordered = True, categories = level_order)
df['cat_var'] = df['cat_var'].astype(ordered_cat)

# # use this method if you have pandas v0.20.3 or earlier
# df['cat_var'] = df['cat_var'].astype('category', ordered = True,
#                                      categories = level_order)

base_color = sb.color_palette()[0]
sb.countplot(data = df, x = 'cat_var', color = base_color)

```

(Documentation: [CategoricalDtype](https://pandas.pydata.org/pandas-docs/version/0.23.4/generated/pandas.api.types.CategoricalDtype.html))

![img](https://video.udacity-data.com/topher/2018/March/5aa9cc51_l3-c03-barchart4/l3-c03-barchart4.png)

Should you find that you need to sort an ordered categorical type in a different order, you can always temporarily override the data type by setting the "order" parameter as above.

## Additional Variations

If your data is in a pandas Series, 1-d NumPy array, or list, you can also just set it as the first argument to the `countplot` function, as we do with the Series `data_var` here:

```python
sb.countplot(data_var)

```

If you have a lot of category levels, or the category names are long, then you might end up with overcrowding of the tick labels. One way to address this is through creation of a horizontal bar chart. In a horizontal bar chart, it is the length of each bar that indicates frequency, rather than the height. In the code, instead of setting the data or variable on the "x" parameter, you can set the variable to be plotted on the parameter "y":

```python
base_color = sb.color_palette()[0]
sb.countplot(data = df, y = 'cat_var', color = base_color)

```

![img](https://video.udacity-data.com/topher/2018/March/5aa9cf92_l3-c03-barchart5/l3-c03-barchart5.png)

Alternatively, you can use matplotlib's [`xticks`](https://matplotlib.org/api/_as_gen/matplotlib.pyplot.xticks.html) function and its "rotation" parameter to change the orientation in which the labels will be depicted (as degrees counter-clockwise from horizontal):

```python
base_color = sb.color_palette()[0]
sb.countplot(data = df, x = 'cat_var', color = base_color)
plt.xticks(rotation = 90)

```

![img](https://video.udacity-data.com/topher/2018/March/5aa9d1d5_l3-c03-barchart6/l3-c03-barchart6.png)





## Absolute vs. Relative Frequency

By default, seaborn's `countplot` function will summarize and plot the data in terms of **absolute frequency**, or pure counts. In certain cases, you might want to understand the distribution of data or want to compare levels in terms of proportions of the whole. In this case, you will want to plot the data in terms of **relative frequency**, where the height indicates the proportion of data taking each level, rather than the absolute count.

One method of plotting the data in terms of relative frequency on a bar chart is to just relabel the counts axis in terms of proportions. The underlying data will be the same, it will simply be the scale of the axis ticks that will be changed.

```python
# get proportion taken by most common group for derivation
# of tick marks
n_points = df.shape[0]
max_count = df['cat_var'].value_counts().max()
max_prop = max_count / n_points

# generate tick mark locations and names
tick_props = np.arange(0, max_prop, 0.05)
tick_names = ['{:0.2f}'.format(v) for v in tick_props]

# create the plot
base_color = sb.color_palette()[0]
sb.countplot(data = df, x = 'cat_var', color = base_color)
plt.yticks(tick_props * n_points, tick_names)
plt.ylabel('proportion')

```

The [`xticks`](https://matplotlib.org/api/_as_gen/matplotlib.pyplot.xticks.html) and [`yticks`](https://matplotlib.org/api/_as_gen/matplotlib.pyplot.yticks.html) functions aren't only about rotating the tick labels. You can also get and set their locations and labels as well. The first argument takes the tick locations: in this case, the tick proportions multiplied back to be on the scale of counts. The second argument takes the tick names: in this case, the tick proportions formatted as strings to two decimal places.

I've also added a [`ylabel`](https://matplotlib.org/api/_as_gen/matplotlib.pyplot.ylabel.html) call to make it clear that we're no longer working with straight counts.

![img](https://video.udacity-data.com/topher/2018/March/5aaaa643_l3-c04-relfreqchart1/l3-c04-relfreqchart1.png)

## Additional Variation

Rather than plotting the data on a relative frequency scale, you might use text annotations to label the frequencies on bars instead. This requires writing a loop over the tick locations and labels and adding one text element for each bar.

```python
# create the plot
base_color = sb.color_palette()[0]
sb.countplot(data = df, x = 'cat_var', color = base_color)

# add annotations
n_points = df.shape[0]
cat_counts = df['cat_var'].value_counts()
locs, labels = plt.xticks() # get the current tick locations and labels

# loop through each pair of locations and labels
for loc, label in zip(locs, labels):

    # get the text property for the label to get the correct count
    count = cat_counts[label.get_text()]
    pct_string = '{:0.1f}%'.format(100*count/n_points)

    # print the annotation just below the top of the bar
    plt.text(loc, count-8, pct_string, ha = 'center', color = 'w')

```

I use the `.get_text()` method to obtain the category name, so I can get the count of each category level. At the end, I use the [`text`](https://matplotlib.org/api/_as_gen/matplotlib.pyplot.text.html#matplotlib.pyplot.text) function to print each percentage, with the x-position, y-position, and string as the three main parameters to the function.

(Documentation: [Text objects](https://matplotlib.org/api/text_api.html?highlight=get_text#matplotlib.text.Text))

![img](https://video.udacity-data.com/topher/2018/March/5aaaad18_l3-c04-relfreqchart2/l3-c04-relfreqchart2.png)





## Counting Missing Data

One interesting way we can apply bar charts is through the visualization of missing data. We can use pandas functions to create a table with the number of missing values in each column.

```
df.isna().sum()

```

![img](https://video.udacity-data.com/topher/2018/March/5aaabcb3_l3-c05-missingdata1/l3-c05-missingdata1.png)

What if we want to visualize these missing value counts? We could treat the variable names as levels of a categorical variable, and create a resulting bar plot. However, since the data is not in its tidy, unsummarized form, we need to make use of a different plotting function. Seaborn's [`barplot`](https://seaborn.pydata.org/generated/seaborn.barplot.html) function is built to depict a summary of one quantitative variable against levels of a second, qualitative variable, but can be used here.

```
na_counts = df.isna().sum()
base_color = sb.color_palette()[0]
sb.barplot(na_counts.index.values, na_counts, color = base_color)

```

The first argument to the function contains the x-values (column names), the second argument the y-values (our counts).

![img](https://video.udacity-data.com/topher/2018/March/5aaabf07_l3-c05-missingdata2/l3-c05-missingdata2.png)



As a general note, this is a useful function to keep in mind if your data is summarized and you still want to build a bar chart. If your data is not yet summarized, however, just use the `countplot` function so that you don't need to do extra summarization work. In addition, you'll see what `barplot`'s main purpose is in the next lesson, when we discuss adaptations of univariate plots for plotting bivariate data.



## Pie Charts

A **pie chart** is a common univariate plot type that is used to depict relative frequencies for levels of a categorical variable. Frequencies in a pie chart are depicted as wedges drawn on a circle: the larger the angle or area, the more common the categorical value taken.

![img](https://video.udacity-data.com/topher/2018/March/5aaad0c8_l3-c07-piecharts2/l3-c07-piecharts2.png)

Pie chart (left) and bar chart (right) displaying the same categorical counts.

Unfortunately, pie charts are a fairly limited plot type in the range of scenarios where they can be used, and it is easy for chart makers to try and spice up pie charts in a way that makes them more difficult to read. If you want to use a pie chart, try to follow certain guidelines:

- Make sure that your interest is in relative frequencies. Areas should represent parts of a whole, rather than measurements on a second variable (unless that second variable can logically be summed up into some whole).
- Limit the number of slices plotted. A pie chart works best with two or three slices, though it's also possible to plot with four or five slices as long as the wedge sizes can be distinguished. If you have a lot of categories, or categories that have small proportional representation, consider grouping them together so that fewer wedges are plotted, or use an 'Other' category to handle them.
- Plot the data systematically. One typical method of plotting a pie chart is to start from the top of the circle, then plot each categorical level clockwise from most frequent to least frequent. If you have three categories and are interested in the comparison of two of them, a common plotting method is to place the two categories of interest on either side of the 12 o'clock direction, with the third category filling in the remaining space at the bottom.

If these guidelines cannot be met, then you should probably make use of a bar chart instead. A bar chart is a safer choice in general. The bar heights are more precisely interpreted than areas or angles, and a bar chart can be displayed more compactly than a pie chart. There's also more flexibility with a bar chart for plotting variables with a lot of levels, like plotting the bars horizontally.

You can create a pie chart with matplotlib's [`pie`](https://matplotlib.org/api/_as_gen/matplotlib.pyplot.pie.html) function. This function requires that the data be in a summarized form: the primary argument to the function will be the wedge sizes.

```
# code for the pie chart seen above
sorted_counts = df['cat_var'].value_counts()
plt.pie(sorted_counts, labels = sorted_counts.index, startangle = 90,
        counterclock = False);
plt.axis('square')

```

To follow the guidelines in the bullet points above, I include the "startangle = 90" and "counterclock = False" arguments to start the first slice at vertically upwards, and will plot the sorted counts in a clockwise fashion. The [`axis`](https://matplotlib.org/api/_as_gen/matplotlib.pyplot.axis.html) function call and 'square' argument makes it so that the scaling of the plot is equal on both the x- and y-axes. Without this call, the pie could end up looking oval-shaped, rather than a circle.

## Additional Variation

A sister plot to the pie chart is the **donut plot**. It's just like a pie chart, except that there's a hole in the center of the plot. Perceptually, there's not much difference between a donut plot and a pie chart, and donut plots should be used with the same guidelines as a pie chart. Aesthetics might be one of the reasons why you would choose one or the other. For instance, you might see statistics reported in the hole of a donut plot to better make use of available space.

To create a donut plot, you can add a "wedgeprops" argument to the `pie` function call. By default, the radius of the pie (circle) is 1; setting the wedges' width property to less than 1 removes coloring from the center of the circle.

```
sorted_counts = df['cat_var'].value_counts()
plt.pie(sorted_counts, labels = sorted_counts.index, startangle = 90,
        counterclock = False, wedgeprops = {'width' : 0.4});
plt.axis('square')

```

(Documentation: [Wedge patches](https://matplotlib.org/api/_as_gen/matplotlib.patches.Wedge.html))

![img](https://video.udacity-data.com/topher/2018/March/5aaae08c_l3-c07-piecharts3/l3-c07-piecharts3.png)

## Further Reading

- Eager Eyes: [Understanding Pie Charts](https://eagereyes.org/pie-charts)
- Eager Eyes: [An Illustrated Tour of the Pie Chart Study Results](https://eagereyes.org/blog/2016/an-illustrated-tour-of-the-pie-chart-study-results) - how accurately do people perceive different formulations of the pie chart?
- Datawrapper: [What to Consider when Creating a Pie Chart](https://academy.datawrapper.de/article/127-what-to-consider-when-creating-a-pie-chart)





## Histograms

A **histogram** is used to plot the distribution of a numeric variable. It's the quantitative version of the bar chart. However, rather than plot one bar for each unique numeric value, values are grouped into continuous bins, and one bar for each bin is plotted depicting the number. For instance, using the default settings for matplotlib's [`hist`](https://matplotlib.org/api/_as_gen/matplotlib.pyplot.hist.html) function:

```
plt.hist(data = df, x = 'num_var')

```

![img](https://video.udacity-data.com/topher/2018/March/5aaae934_l3-c08-histograms1/l3-c08-histograms1.png)

You can see that there are eight data points that fall in the range between about 0 and 2.5 in the leftmost bin, and nine points in the range from about 2.5 to 5 in the adjacent bin. Overall, a generally bimodal distribution is observed (one with two peaks or humps). The direct adjacency of the bars in the histogram, in contrast to the separated bars in a bar chart, emphasize the fact that the data takes on a continuous range of values. When a data value is on a bin edge, it is counted in the bin to its right. The exception is the rightmost bin edge, which places data values equal to the uppermost limit into the right-most bin (to the upper limit's left).

By default, the `hist` function divides the data into 10 bins, based on the range of values taken. In almost every case, we will want to change these settings. Usually, having only ten bins is too few to really understand the distribution of the data. And the default tick marks are often not on nice, 'round' values that make the ranges taken by each bin easy to interpret. Wouldn't it be better if I said "between 0 and 2.5" instead of "between *about* 0 and 2.5", and "from 2.5 to 5" instead of "from *about* 2.5 to 5" above?

You can use descriptive statistics (e.g. via [`df['num_var'\].describe()`](https://pandas.pydata.org/pandas-docs/stable/generated/pandas.Series.describe.html)) to gauge what minimum and maximum bin limits might be appropriate for the plot. These bin edges can be set using numpy's [`arange`](https://docs.scipy.org/doc/numpy/reference/generated/numpy.arange.html) function:

```
bin_edges = np.arange(0, df['num_var'].max()+1, 1)
plt.hist(data = df, x = 'num_var', bins = bin_edges)

```

The first argument to `arange` is the leftmost bin edge, the second argument the upper limit, and the third argument the bin width. Note that even though I've specified the "max" value in the second argument, I've added a "+1" (the bin width). That is because `arange` will only return values that are strictly less than the upper limit. Adding in "+1" is a safety measure to ensure that the rightmost bin edge is at least the maximum data value, so that all of the data points are plotted. The leftmost bin is set as a hardcoded value to get a nice, interpretable value, though you could use functions like numpy's [`around`](https://docs.scipy.org/doc/numpy/reference/generated/numpy.around.html) if you wanted to approach that end programmatically.

![img](https://video.udacity-data.com/topher/2018/March/5aaaf362_l3-c08-histograms2/l3-c08-histograms2.png)

When creating histograms, it's useful to play around with different bin widths to see what represents the data best. Too many bins, and you may see too much noise that interferes with identification of the underlying signal. Too few bins, and you may not be able to see the true signal in the first place.

```
plt.figure(figsize = [10, 5]) # larger figure size for subplots

# histogram on left, example of too-large bin size
plt.subplot(1, 2, 1) # 1 row, 2 cols, subplot 1
bin_edges = np.arange(0, df['num_var'].max()+4, 4)
plt.hist(data = df, x = 'num_var', bins = bin_edges)

# histogram on right, example of too-small bin size
plt.subplot(1, 2, 2) # 1 row, 2 cols, subplot 2
bin_edges = np.arange(0, df['num_var'].max()+1/4, 1/4)
plt.hist(data = df, x = 'num_var', bins = bin_edges)

```

This example puts two plots side by side through use of the [`subplot`](https://matplotlib.org/api/_as_gen/matplotlib.pyplot.subplot.html) function, whose arguments specify the number of rows, columns, and index of the active subplot (in that order). The [`figure()`](https://matplotlib.org/api/_as_gen/matplotlib.pyplot.figure.html) function is called with the "figsize" parameter so that we can have a larger figure to support having multiple subplots. (More details on figures and subplots are coming up next in the lesson.)

![img](https://video.udacity-data.com/topher/2018/March/5aaaf900_l3-c08-histograms3/l3-c08-histograms3.png)

## Alternative Approach

The seaborn function [`distplot`](https://seaborn.pydata.org/generated/seaborn.distplot.html) can also be used to plot a histogram, and is integrated with other univariate plotting functions.

```
sb.distplot(df['num_var'])

```

When we specify the data to be plotted, note that the first argument *must* be the Series or array with the points to be plotted. This is in contrast to our ability to specify a data source and column as separate arguments, like we've seen with and `countplot` and `hist`.

![img](https://video.udacity-data.com/topher/2018/March/5aab083d_l3-c08-histograms4/l3-c08-histograms4.png)

The `distplot` function has built-in rules for specifying histogram bins, and by default plots a curve depicting the kernel density estimate (KDE) on top of the data. The vertical axis is based on the KDE, rather than the histogram: you shouldn't expect the total heights of the bars to equal 1, but the area under the curve should equal 1. If you want to learn more about KDEs, check out the extra page at the end of the lesson.

Despite the fact that the default bin-selection formula used by `distplot` might be better than the choice of ten bins that `.hist` uses, you'll still want to do some tweaking to align the bins to 'round' values. You can use other parameter settings to plot just the histogram and specify the bins like before:

```
bin_edges = np.arange(0, df['num_var'].max()+1, 1)
sb.distplot(df['num_var'], bins = bin_edges, kde = False,
            hist_kws = {'alpha' : 1})

```

The alpha (transparency) setting must be associated as a dictionary to "hist_kws" since there are other underlying plotting functions, like the KDE, that have their own optional keyword parameters.

![img](https://video.udacity-data.com/topher/2018/March/5aaaf362_l3-c08-histograms2/l3-c08-histograms2.png)

The result of the code above is exactly like the histogram above with bin width of 1. The units of the vertical axis are also back in terms of counts.

In summary, if your exploration is only interested in the histogram-depiction of the data, and not the additional functionality offered by `distplot`, then you might be better off with just using Matplotlib's `hist` function for simplicity. On the other hand, if you want a quick start on choosing a representative bin size for histogram plotting, you might take a quick look at the basic `distplot` first before getting into the customization.





## Figures, Axes, and Subplots

At this point, you've seen and had some practice with some basic plotting functions using matplotlib and seaborn. The previous page introduced something a little bit new: creating two side-by-side plots through the use of matplotlib's [`subplot()`](https://matplotlib.org/api/_as_gen/matplotlib.pyplot.subplot.html) function. If you have any questions about how that or the [`figure()`](https://matplotlib.org/api/_as_gen/matplotlib.pyplot.figure.html) function worked, then read on. This page will discuss the basic structure of visualizations using matplotlib and how subplots work in that structure.

The base of a visualization in matplotlib is a [Figure](https://matplotlib.org/api/_as_gen/matplotlib.figure.Figure.html) object. Contained within each Figure will be one or more [Axes](https://matplotlib.org/api/axes_api.html) objects, each Axes object containing a number of other elements that represent each plot. In the earliest examples, these objects have been created implicitly. Let's say that the following expression is run inside a Jupyter notebook to create a histogram:

```
plt.hist(data = df, x = 'num_var')

```

Since we don't have a Figure area to plot inside, Python first creates a Figure object. And since the Figure doesn't start with any Axes to draw the histogram onto, an Axes object is created inside the Figure. Finally, the histogram is drawn within that Axes.

![img](https://video.udacity-data.com/topher/2018/August/5b804b9b_l3-c09b-subplotsa/l3-c09b-subplotsa.png)

This hierarchy of objects is useful to know about so that we can take more control over the layout and aesthetics of our plots. One alternative way we could have created the histogram is to explicitly set up the Figure and Axes like this:

```
fig = plt.figure()
ax = fig.add_axes([.125, .125, .775, .755])
ax.hist(data = df, x = 'num_var')

```

[`figure()`](https://matplotlib.org/api/_as_gen/matplotlib.pyplot.figure.html) creates a new Figure object, a reference to which has been stored in the variable `fig`. One of the Figure methods is [`.add_axes()`](https://matplotlib.org/api/_as_gen/matplotlib.figure.Figure.html#matplotlib.figure.Figure.add_axes), which creates a new Axes object in the Figure. The method requires one list as argument specifying the dimensions of the Axes: the first two elements of the list indicate the position of the lower-left hand corner of the Axes (in this case one quarter of the way from the lower-left corner of the Figure) and the last two elements specifying the Axes width and height, respectively. We refer to the Axes in the variable `ax`. Finally, we use the Axes method [`.hist()`](https://matplotlib.org/api/_as_gen/matplotlib.axes.Axes.hist.html#matplotlib.axes.Axes.hist) just like we did before with `plt.hist()`.

![img](https://video.udacity-data.com/topher/2018/March/5aaae934_l3-c08-histograms1/l3-c08-histograms1.png)

This plot is just like the first histogram on the Histograms page.

To use Axes objects with seaborn, seaborn functions usually have an "ax" parameter to specify upon which Axes a plot will be drawn.

```
fig = plt.figure()
ax = fig.add_axes([.125, .125, .775, .755])
base_color = sb.color_palette()[0]
sb.countplot(data = df, x = 'cat_var', color = base_color, ax = ax)

```

![img](https://video.udacity-data.com/topher/2018/March/5aa9bcf3_l3-c03-barchart2/l3-c03-barchart2.png)

This is the same as the second plot on the Bar Charts page.

In the above two cases, there was no purpose to explicitly go through the Figure and Axes creation steps. And indeed, in most cases, you can just use the basic matplotlib and seaborn functions as is. Each function targets a Figure or Axes, and they'll automatically target the most recent Figure or Axes worked with. As an example of this, let's review in detail how [`subplot()`](https://matplotlib.org/api/_as_gen/matplotlib.pyplot.subplot.html) was used on the Histograms page:

```
plt.figure(figsize = [10, 5]) # larger figure size for subplots

# example of somewhat too-large bin size
plt.subplot(1, 2, 1) # 1 row, 2 cols, subplot 1
bin_edges = np.arange(0, df['num_var'].max()+4, 4)
plt.hist(data = df, x = 'num_var', bins = bin_edges)

# example of somewhat too-small bin size
plt.subplot(1, 2, 2) # 1 row, 2 cols, subplot 2
bin_edges = np.arange(0, df['num_var'].max()+1/4, 1/4)
plt.hist(data = df, x = 'num_var', bins = bin_edges)

```

![img](https://video.udacity-data.com/topher/2018/March/5aaaf900_l3-c08-histograms3/l3-c08-histograms3.png)

First of all, `plt.figure(figsize = [10, 5])`creates a new Figure, with the "figsize" argument setting the width and height of the overall figure to 10 inches by 5 inches, respectively. Even if we don't assign any variable to return the function's output, Python will still implicitly know that further plotting calls that need a Figure will refer to that Figure as the active one.

Then, `plt.subplot(1, 2, 1)` creates a new Axes in our Figure, its size determined by the `subplot()` function arguments. The first two arguments says to divide the figure into one row and two columns, and the third argument says to create a new Axes in the first slot. Slots are numbered from left to right in rows from top to bottom. Note in particular that the index numbers start at 1 (rather than the usual Python indexing starting from 0). (You'll see the indexing a little better in the example at the end of the page.) Again, Python will implicitly set that Axes as the current Axes, so when the `plt.hist()` call comes, the histogram is plotted in the left-side subplot.

Finally, `plt.subplot(1, 2, 2)` creates a new Axes in the second subplot slot, and sets that one as the current Axes. Thus, when the next `plt.hist()` call comes, the histogram gets drawn in the right-side subplot.





## Choosing a Plot for Discrete Data

If you want to plot a discrete quantitative variable, it is possible to select either a histogram or a bar chart to depict the data.

The histogram is the most immediate choice since the data is numeric, but there's one particular consideration to make regarding the bin edges. Since data points fall on set values, it can help to reduce ambiguity by putting bin edges between the actual values taken by the data. Your readers may not know that values on bin edges end up in the bin to their right, so this can help remove potential confusion when they interpret the plot. Compare the two visualizations of 100 random die rolls below (in `die_rolls`), with bin edges _on_ the values in the left subplot, and bin edges *in between* values in the right subplot.

```
plt.figure(figsize = [10, 5])

# histogram on the left, bin edges on integers
plt.subplot(1, 2, 1)
bin_edges = np.arange(2, 12+1.1, 1) # note `+1.1`, see below
plt.hist(die_rolls, bins = bin_edges)
plt.xticks(np.arange(2, 12+1, 1))

# histogram on the right, bin edges between integers
plt.subplot(1, 2, 2)
bin_edges = np.arange(1.5, 12.5+1, 1)
plt.hist(die_rolls, bins = bin_edges)
plt.xticks(np.arange(2, 12+1, 1))

```

![The same data is plotted in both subplots, but the alignment of the bin edges is different.](https://video.udacity-data.com/topher/2018/March/5aa9881b_l3-c10-dierolls1/l3-c10-dierolls1.png)

You'll notice for the left histogram, in a deviation from the examples that have come before, I've added 1.1 to the max value (12) for setting the bin edges, rather than just the desired bin width of 1. Recall that data that is equal to the rightmost bin edge gets lumped in to the last bin. This presents a potential problem in perception when a lot of data points take the maximum value, and so is especially relevant when the data takes on discrete values. The 1.1 adds an additional bin to the end to store the die rolls of value 12 alone, to avoid having the last bar catch both 11 and 12.

Alternatively to the histogram, consider if a bar chart with non-connected bins might serve your purposes better. The plot below takes the code from before, but adds the "rwidth" parameter to set the proportion of the bin widths that will be filled by each histogram bar.

```
bin_edges = np.arange(1.5, 12.5+1, 1)
plt.hist(die_rolls, bins = bin_edges, rwidth = 0.7)
plt.xticks(np.arange(2, 12+1, 1))

```

With "rwidth" set to 0.7, the bars will take up 70% of the space allocated by each bin, with 30% of the space left empty. This changes the default display of the histogram (which you could think of as "rwidth = 1") into a bar chart.

![Gaps between bars makes it clear that the data is discrete in nature.](https://video.udacity-data.com/topher/2018/March/5aa996d1_l3-c10-dierolls2/l3-c10-dierolls2.png)

By adding gaps between bars, you emphasize the fact that the data is discrete in value. On the other hand, plotting your quantitative data in this manner might cause it to be interpreted as ordinal-type data, which can have an effect on overall perception.

For continuous numeric data, you should not make use of the "rwidth" parameter, since the gaps imply discreteness of value. As another caution, it might be tempting to use seaborn's `countplot` function to plot the distribution of a discrete numeric variable as bars. Be careful about doing this, since each unique numeric value will get a bar, regardless of the spacing in values between bars. (For example, if the unique values were {1, 2, 4, 5}, missing 3, `countplot` would only plot four bars, with the bars for 2 and 4 right next to one another.) Also, even if your data is technically discrete numeric, you should probably not consider either of the variants depicted on this page unless the number of unique values is small enough to allow for the half-unit shift or discrete bars to be interpretable. If you have a large number of unique values over a large enough range, it's better to stick with the standard histogram than risk interpretability issues.

While you might justify plotting discrete numeric data using a bar chart, you’ll be less apt to justify the opposite: plotting ordinal data as a histogram. The space between bars in a bar chart helps to remind the reader that values are not contiguous in an ‘interval’-type fashion: only that there is an order in levels. With that space removed as in a histogram, it's harder to remember this important bit of interpretation.



## Descriptive Statistics, Outliers, and Axis Limits

As you create your plots and perform your exploration, make sure that you pay attention to what the plots tell you that go beyond just the basic descriptive statistics. Note any aspects of the data like number of modes and skew, and note the presence of outliers in the data for further investigation.

Related to the latter point, you might need to change the limits or scale of what is plotted to take a closer look at the underlying patterns in the data. This page covers the topic of axis limits; the next the topic of scales and transformations. In order to change a histogram's axis limits, you can add a Matplotlib [`xlim`](https://matplotlib.org/api/_as_gen/matplotlib.pyplot.xlim.html) call to your code. The function takes a tuple of two numbers specifying the upper and lower bounds of the x-axis range. Alternatively, the `xlim` function can be called with two numeric arguments to the same result.

```
plt.figure(figsize = [10, 5])

# histogram on left: full data
plt.subplot(1, 2, 1)
bin_edges = np.arange(0, df['skew_var'].max()+2.5, 2.5)
plt.hist(data = df, x = 'skew_var', bins = bin_edges)

# histogram on right: focus in on bulk of data < 35
plt.subplot(1, 2, 2)
bin_edges = np.arange(0, 35+1, 1)
plt.hist(data = df, x = 'skew_var', bins = bin_edges)
plt.xlim(0, 35) # could also be called as plt.xlim((0, 35))

```

![img](https://video.udacity-data.com/topher/2018/March/5aab1bfb_l3-c11-outliers1/l3-c11-outliers1.png)

In the generic example above, we might be interested in comparing patterns in other variables between data points that take values less than 35 to those that take values greater than 35. For anything that is concentrated on the bulk of the data in the former group (< 35), use of axis limits can allow focusing on data points in that range without needing to go through creation of a new DataFrame filtering out the data points in the latter group (> 35).



## Scales and Transformations

Certain data distributions will find themselves amenable to scale transformations. The most common example of this is data that follows an approximately [log-normal](https://en.wikipedia.org/wiki/Log-normal_distribution) distribution. This is data that, in their natural units, can look highly skewed: lots of points with low values, with a very long tail of data points with large values. However, after applying a logarithmic transform to the data, the data will follow a normal distribution. (If you need a refresher on the logarithm function, check out [this lesson on Khan Academy](https://www.khanacademy.org/math/algebra2/exponential-and-logarithmic-functions).)

```
plt.figure(figsize = [10, 5])

# left histogram: data plotted in natural units
plt.subplot(1, 2, 1)
bin_edges = np.arange(0, data.max()+100, 100)
plt.hist(data, bins = bin_edges)
plt.xlabel('values')

# right histogram: data plotted after direct log transformation
plt.subplot(1, 2, 2)
log_data = np.log10(data) # direct data transform
log_bin_edges = np.arange(0.8, log_data.max()+0.1, 0.1)
plt.hist(log_data, bins = log_bin_edges)
plt.xlabel('log(values)')

```

(Documentation: [numpy `log10`](https://docs.scipy.org/doc/numpy/reference/generated/numpy.log10.html), [matplotlib `xlabel`](https://matplotlib.org/api/_as_gen/matplotlib.pyplot.xlabel.html))

![img](https://video.udacity-data.com/topher/2018/November/5beca4ca_l3-c12-transforms1/l3-c12-transforms1.png)

In the plot on the left, the few data points with value above 1000 mash the majority of the points into the bins on the far left. With the plot on the right, the logarithmic transform makes those large points look in line with the rest: a raw value of 1000 becomes a value of 3 under log transform, and a raw value of 100 becomes a log-transformed value of 2. The big problem with the right-side plot is that the units on the x-axis are difficult to interpret: for most people, it is only easy to convert from log values to natural values on the integers (and this assumes a nice base like 10 as used in the example).

This is where scale transformations are handy. In a scale transformation, the gaps between values are based on the transformed scale, but you can interpret data in the variable's natural units. It is also a convenient approach since you won't need to engineer new features. Matplotlib's [`xscale`](https://matplotlib.org/api/_as_gen/matplotlib.pyplot.xscale.html) function includes a few built-in transformations: we'll use the 'log' scale here.

```
bin_edges = np.arange(0, data.max()+100, 100)
plt.hist(data, bins = bin_edges)
plt.xscale('log')

```

![img](https://video.udacity-data.com/topher/2018/March/5aab631b_l3-c12-transforms2/l3-c12-transforms2.png)

Notice two things about the plot now. Even though the data is on a log scale, the bins are still linearly spaced. This means that they change size from wide on the left to thin on the right, as the values increase multiplicatively. Secondly, the default label settings are still somewhat tricky to interpret, and are sparse as well.

To address the bin size issue, we just need to change them so that they are evenly-spaced powers of 10. Depending on what you are plotting, a different base power like 2 might be useful instead. For the ticks, we can use [`xticks`](https://matplotlib.org/api/_as_gen/matplotlib.pyplot.xticks.html) to specify locations and labels in their natural units. Remember: we aren't changing the values taken by the data, only how they're displayed. Between integer powers of 10, we don't have clean values for even markings, but we can still get close. Setting ticks in cycles of 1-3-10 or 1-2-5-10 are very useful for base-10 log transforms.

```
bin_edges = 10 ** np.arange(0.8, np.log10(data.max())+0.1, 0.1)
plt.hist(data, bins = bin_edges)
plt.xscale('log')
tick_locs = [10, 30, 100, 300, 1000, 3000]
plt.xticks(tick_locs, tick_locs)

```

It is important that the `xticks` are specified *after* `xscale` since that function has its own built-in tick settings.

![img](https://video.udacity-data.com/topher/2018/March/5aab6792_l3-c12-transforms3/l3-c12-transforms3.png)

We've ended up with the same plot as when we performed the direct log transform, but now with a much nicer set of tick marks and labels.

## Alternative Approach

Be aware that a logarithmic transformation is not the only one possible. When we perform a logarithmic transformation, our data values have to all be positive; it's impossible to take a log of zero or a negative number. In addition, the transformation implies that additive steps on the log scale will result in multiplicative changes in the natural scale, an important implication when it comes to data modeling. The type of transformation that you choose may be informed by the context for the data. For example, [this Wikipedia section](https://en.wikipedia.org/wiki/Log-normal_distribution#Occurrence_and_applications) provides a few examples of places where log-normal distributions have been observed.

If you want to use a different transformation that's not available in `xscale`, then you'll have to perform some feature engineering. In cases like this, we want to be systematic by writing a function that applies both the transformation and its inverse. The inverse will be useful in cases where we specify values in their transformed units and need to get the natural units back. For the purposes of demonstration, let's say that we want to try plotting the above data on a square-root transformation. (Perhaps the numbers represent areas, and we think it makes sense to model the data on a rough estimation of radius, length, or some other 1-d dimension.) We can create a visualization on this transformed scale like this:

```
def sqrt_trans(x, inverse = False):
    """ transformation helper function """
    if not inverse:
        return np.sqrt(x)
    else:
        return x ** 2

bin_edges = np.arange(0, sqrt_trans(data.max())+1, 1)
plt.hist(data.apply(sqrt_trans), bins = bin_edges)
tick_locs = np.arange(0, sqrt_trans(data.max())+10, 10)
plt.xticks(tick_locs, sqrt_trans(tick_locs, inverse = True).astype(int))

```

Note that `data` is a pandas Series, so we can use the [`apply`](https://pandas.pydata.org/pandas-docs/stable/generated/pandas.Series.apply.html) method for the function. If it were a NumPy Array, we would need to apply the function like in the other cases. The tick locations could have also been specified with the natural values, where we apply the standard transformation function on the first argument of `xticks` instead.

![img](https://video.udacity-data.com/topher/2018/March/5aab784e_l3-c12-transforms4/l3-c12-transforms4.png)



## Kernel Density Estimation

Earlier in this lesson, you saw an example of [kernel density estimation](https://en.wikipedia.org/wiki/Kernel_density_estimation) (KDE) through the use of seaborn's [`distplot`](https://seaborn.pydata.org/generated/seaborn.distplot.html#seaborn.distplot) function, which plots a KDE on top of a histogram.

```
sb.distplot(df['num_var'])

```

![img](https://video.udacity-data.com/topher/2018/March/5aab083d_l3-c08-histograms4/l3-c08-histograms4.png)

Kernel density estimation is one way of estimating the probability density function of a variable. In a KDE plot, you can think of each observation as replaced by a small ‘lump’ of area. Stacking these lumps all together produces the final density curve. The default settings use a normal-distribution kernel, but most software that can produce KDE plots also include other kernel function options.

Seaborn's `distplot` function calls another function, [`kdeplot`](https://seaborn.pydata.org/generated/seaborn.kdeplot.html), to generate the KDE. The demonstration code below also uses a third function called by `distplot` for illustration, [`rugplot`](https://seaborn.pydata.org/generated/seaborn.rugplot.html). In a rugplot, data points are depicted as dashes on a number line.

```
data = [0.0, 3.0, 4.5, 8.0]
plt.figure(figsize = [12, 5])

# left plot: showing kde lumps with the default settings
plt.subplot(1, 3, 1)
sb.distplot(data, hist = False, rug = True, rug_kws = {'color' : 'r'})

# central plot: kde with narrow bandwidth to show individual probability lumps
plt.subplot(1, 3, 2)
sb.distplot(data, hist = False, rug = True, rug_kws = {'color' : 'r'},
            kde_kws = {'bw' : 1})

# right plot: choosing a different, triangular kernel function (lump shape)
plt.subplot(1, 3, 3)
sb.distplot(data, hist = False, rug = True, rug_kws = {'color' : 'r'},
            kde_kws = {'bw' : 1.5, 'kernel' : 'tri'})

```

![img](https://video.udacity-data.com/topher/2018/March/5aab7fe3_l3-c15-kde1/l3-c15-kde1.png)

Interpreting proportions from this plot type is slightly trickier than a standard histogram: the vertical axis indicates a density of data rather than straightforward proportions. Under a KDE plot, the total area between the 0-line and the curve will be 1. The probability of an outcome falling between two values is found by computing the area under the curve that falls between those values. Making area judgments like this without computer assistance is difficult and likely to be inaccurate.

Despite the fact that making specific probability judgments are not as intuitive with KDE plots as histograms, there are still reasons to use kernel density estimation. If there are relatively few data points available, KDE provides a smooth estimate of the overall distribution of data. These ideas may not be so easily conveyed through histograms, in which the large discreteness of jumps may end up misleading.

It should also be noted that there is a bandwidth parameter in KDE that specifies how wide the density lumps are. Similar to bin width for histograms, we need to choose a bandwidth size that best shows the signal in the data. A too-small bandwidth can make the data look noisier than it really is, and a too-large bandwidth can smooth out useful features that we could use to make inferences about the data. It’s good to keep this in mind in case the default bandwidths chosen by your visualization software don’t look quite right or if you need to perform further investigations.



## Waffle Plots

One alternative univariate plot type that you might see for categorical data is the **waffle plot**, also known as the square pie chart. While the standard pie chart uses a circle to represent the whole, a waffle plot is plotted onto a square divided into a 10x10 grid. Each small square in the grid represents one percent of the data, and a number of squares are colored by category to indicate total proportions. Compared to a pie chart, it is much easier to make precise assessments of relative frequencies.

![img](https://video.udacity-data.com/topher/2018/November/5be2398e_l3-c16-waffleplots3/l3-c16-waffleplots3.png)

You've seen code for the pie chart (left) previously in the lesson. Code for the waffle plot (right) will be walked through below.

There's no built-in function for waffle plots in Matplotlib or Seaborn, so we'll need to take some additional steps in order to build one with the tools available. First, we need to create a function to decide how many blocks to allocate to each category. The function below, `percentage_blocks`, uses a rule where each category gets a number of blocks equal to the number of full percentage points it covers. The remaining blocks to get to the full one hundred are assigned to the categories with the largest fractional parts.

```
def percentage_blocks(df, var):
    """
    Take as input a dataframe and variable, and return a Pandas series with
    approximate percentage values for filling out a waffle plot.
    """
    # compute base quotas
    percentages = 100 * df[var].value_counts() / df.shape[0]
    counts = np.floor(percentages).astype(int) # integer part = minimum quota
    decimal = (percentages - counts).sort_values(ascending = False)

    # add in additional counts to reach 100
    rem = 100 - counts.sum()
    for cat in decimal.index[:rem]:
        counts[cat] += 1

    return counts

```

![img](https://video.udacity-data.com/topher/2018/November/5be215e8_l3-c16-waffleplotsa/l3-c16-waffleplotsa.png)

Note that if we just rounded the proportions (center), we would round all of them up, ending up with a total of 101 blocks.

Now it's time to actually plot those counts as boxes in the waffle plot form. To do this, we'll make use of Matplotlib's [`bar`](https://matplotlib.org/api/_as_gen/matplotlib.pyplot.bar.html) function. We could have used this function earlier in the lesson to create our bar charts instead of Seaborn's `countplot`, but it would have required us to aggregate the data first to get the height of each bar. For the case of the waffle plot, we're going to specify the x- and y- coordinates of the boxes, and set their widths and heights to be equal, to create squares. The initial plotting code looks like this:

```
waffle_counts = percentage_blocks(df, 'cat_var')

prev_count = 0
# for each category,
for cat in range(waffle_counts.shape[0]):
    # get the block indices
    blocks = np.arange(prev_count, prev_count + waffle_counts[cat])
    # and put a block at each index's location
    x = blocks % 10 # use mod operation to get ones digit
    y = blocks // 10 # use floor division to get tens digit
    plt.bar(x = x, height = 0.8, width = 0.8, bottom = y)
    prev_count += waffle_counts[cat]

```

The blocks are drawn from left to right, bottom to top, using the ones and tens digits for numbers from 0 to 99 to specify the x- and y- positions, respectively. A loop is used to call the `bar` function once for each category; each time it is called, the plotted bars are assigned a different color.

![img](https://video.udacity-data.com/topher/2018/November/5be2305a_l3-c16-waffleplots1/l3-c16-waffleplots1.png)

The last steps that we need to do involve aesthetic cleaning to polish it up for interpretability. We can take away the plot border and ticks, since they're arbitrary, but we should change the limits so that the boxes are square. We should also add a legend so that the mapping from colors to category levels is clear.

```
waffle_counts = percentage_blocks(df, 'cat_var')

prev_count = 0
# for each category,
for cat in range(waffle_counts.shape[0]):
    # get the block indices
    blocks = np.arange(prev_count, prev_count + waffle_counts[cat])
    # and put a block at each index's location
    x = blocks % 10 # use mod operation to get ones digit
    y = blocks // 10 # use floor division to get tens digit
    plt.bar(x = x, height = 0.8, width = 0.8, bottom = y)
    prev_count += waffle_counts[cat]

# aesthetic wrangling
plt.legend(waffle_counts.index, bbox_to_anchor = (1, 0.5), loc = 6)
plt.axis('off')
plt.axis('square')

```

The two calls to Matplotlib's [`axis`](https://matplotlib.org/api/_as_gen/matplotlib.pyplot.axis.html) function make use of two convenience strings for arguments: 'off' removes the axis lines, ticks, and labels, while 'square' ensures that the scaling on each axis is equal within a square bounding box. As for the [`legend`](https://matplotlib.org/api/_as_gen/matplotlib.pyplot.legend.html) call, the first argument is a list of categories as obtained from the sorted `waffle_counts` Series variable. This will match each category to each `bar` call, in order. The "bbox_to_anchor" argument sets an anchor for the legend to the right side of the plot, and "loc = 6" positions the anchor to the center left of the legend. The final plot is as it looks at the top of the page:

![img](https://video.udacity-data.com/topher/2018/November/5be2387b_l3-c16-waffleplots2/l3-c16-waffleplots2.png)

Other variants of the waffle plot exist to extend it beyond just displaying probabilities. By associating each square with an amount rather than a percentage, we can use waffle plots to show absolute frequencies instead. This might cause us to end up with something other than 100 squares.

```
# each box represents five full counts
waffle_counts = (df['cat_var'].value_counts() / 5).astype(int)

prev_count = 0
# for each category,
for cat in range(waffle_counts.shape[0]):
    # get the block indices
    blocks = np.arange(prev_count, prev_count + waffle_counts[cat])
    # and put a block at each index's location
    x = blocks % 10
    y = blocks // 10
    plt.bar(y, 0.8, 0.8, x)
    prev_count += waffle_counts[cat]

# box size legend
plt.bar(7.5, 0.8, 0.8, 2, color = 'white', edgecolor = 'black', lw = 2)
plt.text(8.1, 2.4,'= 5 data points', va = 'center')

# aesthetic wrangling
plt.legend(waffle_counts.index, bbox_to_anchor = (0.8, 0.5), loc = 6)
plt.axis('off')
plt.axis('square')

```

In the above code, `waffle_counts` has been adjusted so that each box represents 5 data points. Most of the code is the same as before, though it should be noted that the `x` and `y` variables have been swapped in the `bar` function so that the boxes are plotted in columns from left to right. Additional `bar` and [`text`](https://matplotlib.org/api/_as_gen/matplotlib.pyplot.text.html) calls have been added to the plot to act as an ad hoc legend. The positions of these elements, and the legend, have been adjusted manually through some trial and error to improve the aesthetic appeal. Note that this constitutes more of an explanatory polishing than it is a part of exploration!

![img](https://video.udacity-data.com/topher/2018/November/5be24166_l3-c16-waffleplots4/l3-c16-waffleplots4.png)

As a further extension, there's no restriction against us using icons for each tally, rather than just squares. Infographics often take this approach, by having each icon represent some number of units (e.g. one person icon representing one million people). But while it can be tempting to use icons to represent values as a bit of visual flair, an icon-based plot contains more chart junk than a bar chart that conveys the same information. There’s a larger cognitive challenge in having to count a number of icons to understand the scale of a value, compared to just referencing a box's endpoint on a labeled axis.

One other downside of the waffle plot is that it is not commonly supported out of the box for most visualization libraries, including Matplotlib and Seaborn. The length of the demonstration code presented above is a testament to that. The effort required to create a meaningful and useful waffle plot means that it is best employed carefully as a part of explanatory visualizations. During the exploratory phase, you're better off using more traditional plots like the bar chart to more rapidly build your understanding of the data.

## Additional Resources

You don't actually need to go through all of the code wrangling shown above to create waffle plots in Python. The [PyWaffle](https://github.com/ligyxy/PyWaffle) package can be used with Matplotlib's `figure` function to create waffle plots, with a few options for the orientation and order of icons, but you'll need to install it separately since it's not a major package. One of the main reasons why I didn't use it above is that the syntax for using it is very different from what you've seen and will see in this course. If you want to make use of the library, check out the examples on the linked GitHub page.



# Bivariate Exploration of Data



## Scatterplots

If we want to inspect the relationship between two numeric variables, the standard choice of plot is the **scatterplot**. In a scatterplot, each data point is plotted individually as a point, its x-position corresponding to one feature value and its y-position corresponding to the second. One basic way of creating a scatterplot is through Matplotlib's [`scatter`](https://matplotlib.org/api/_as_gen/matplotlib.pyplot.scatter.html) function:

```
plt.scatter(data = df, x = 'num_var1', y = 'num_var2')

```

![img](https://video.udacity-data.com/topher/2018/March/5ab03c6b_l4-c02-scatterplot1/l4-c02-scatterplot1.png)

We can see a generally positive relationship between the two variables, as higher values of the x-axis variable are associated with greatly increasing values of the variable plotted on the y-axis.

## Alternative Approach

Seaborn's [`regplot`](https://seaborn.pydata.org/generated/seaborn.regplot.html) function combines scatterplot creation with regression function fitting:

```
sb.regplot(data = df, x = 'num_var1', y = 'num_var2')

```

The basic function parameters, "data", "x", and "y" are the same for `regplot` as they are for matplotlib's `scatter`.

![img](https://video.udacity-data.com/topher/2018/March/5ab03e30_l4-c02-scatterplot2/l4-c02-scatterplot2.png)

By default, the regression function is linear, and includes a shaded confidence region for the regression estimate. In this case, since the trend looks like a \text{log}(y) \propto xlog(y)∝x relationship (that is, linear increases in the value of x are associated with linear increases in the log of y), plotting the regression line on the raw units is not appropriate. If we don't care about the regression line, then we could set `fit_reg = False` in the `regplot` function call. Otherwise, if we want to plot the regression line on the observed relationship in the data, we need to transform the data, as seen in the previous lesson.

```
def log_trans(x, inverse = False):
    if not inverse:
        return np.log10(x)
    else:
        return np.power(10, x)

sb.regplot(df['num_var1'], df['num_var2'].apply(log_trans))
tick_locs = [10, 20, 50, 100, 200, 500]
plt.yticks(log_trans(tick_locs), tick_locs)

```

In this example, the x- and y- values sent to `regplot` are set directly as Series, extracted from the dataframe.

![img](https://video.udacity-data.com/topher/2018/March/5ab047f5_l4-c02-scatterplot3/l4-c02-scatterplot3.png)



## Overplotting, Transparency, and Jitter

If we have a very large number of points to plot or our numeric variables are discrete-valued, then it is possible that using a scatterplot straightforwardly will not be informative. The visualization will suffer from *overplotting*, where the high amount of overlap in points makes it difficult to see the actual relationship between the plotted variables.

```
plt.scatter(data = df, x = 'disc_var1', y = 'disc_var2')

```

![img](https://video.udacity-data.com/topher/2018/March/5ab1488a_l4-c03-overplotting1/l4-c03-overplotting1.png)

In the above plot, we can infer some kind of negative relationship between the two variables, but the degree of variability in the data and strength of relationship are fairly unclear. In cases like this, we may want to employ *transparency* and *jitter* to make the scatterplot more informative. Transparency can be added to a [`scatter`](https://matplotlib.org/api/_as_gen/matplotlib.pyplot.scatter.html) call by adding the "alpha" parameter set to a value between 0 (fully transparent, not visible) and 1 (fully opaque).

```
plt.scatter(data = df, x = 'disc_var1', y = 'disc_var2', alpha = 1/5)

```

![img](https://video.udacity-data.com/topher/2018/March/5ab14acb_l4-c03-overplotting2/l4-c03-overplotting2.png)

Where more points overlap, the darker the image will be. Here, we can now see that there is a moderate negative relationship between the two numeric variables. Values of 0 and 10 on the x-axis are much rarer than the central values.

As an alternative or companion to transparency, we can also add jitter to move the position of each point slightly from its true value. This is not a direct option in matplotlib's `scatter` function, but is a built-in option with seaborn's [`regplot`](https://seaborn.pydata.org/generated/seaborn.regplot.html) function. x- and y- jitter can be added independently, and won't affect the fit of any regression function, if made:

```
sb.regplot(data = df, x = 'disc_var1', y = 'disc_var2', fit_reg = False,
           x_jitter = 0.2, y_jitter = 0.2, scatter_kws = {'alpha' : 1/3})

```

The jitter settings will cause each point to be plotted in a uniform ±0.2 range of their true values. Note that transparency has been changed to be a dictionary assigned to the "scatter_kws" parameter. This is necessary so that transparency is specifically associated with the `scatter` component of the `regplot` function.

![img](https://video.udacity-data.com/topher/2018/March/5ab15147_l4-c03-overplotting3/l4-c03-overplotting3.png)







## Heat Maps

A **heat map** is a 2-d version of the histogram that can be used as an alternative to a scatterplot. Like a scatterplot, the values of the two numeric variables to be plotted are placed on the plot axes. Similar to a histogram, the plotting area is divided into a grid and the number of points in each grid rectangle is added up. Since there won't be room for bar heights, counts are indicated instead by grid cell color. A heat map can be implemented with Matplotlib's [`hist2d`](https://matplotlib.org/api/_as_gen/matplotlib.pyplot.hist2d.html) function.

```
plt.figure(figsize = [12, 5])

# left plot: scatterplot of discrete data with jitter and transparency
plt.subplot(1, 2, 1)
sb.regplot(data = df, x = 'disc_var1', y = 'disc_var2', fit_reg = False,
           x_jitter = 0.2, y_jitter = 0.2, scatter_kws = {'alpha' : 1/3})

# right plot: heat map with bin edges between values
plt.subplot(1, 2, 2)
bins_x = np.arange(0.5, 10.5+1, 1)
bins_y = np.arange(-0.5, 10.5+1, 1)
plt.hist2d(data = df, x = 'disc_var1', y = 'disc_var2',
           bins = [bins_x, bins_y])
plt.colorbar();

```

Notice that since we have two variables, the "bins" parameter takes a list of two bin edge specifications, one for each dimension. Choosing an appropriate bin size is just as important here as it was for the univariate histogram. We add a [`colorbar`](https://matplotlib.org/api/_as_gen/matplotlib.pyplot.colorbar.html) function call to add a colorbar to the side of the plot, showing the mapping from counts to colors.

![img](https://video.udacity-data.com/topher/2018/March/5ab158bb_l4-c04-heatmap1/l4-c04-heatmap1.png)

As the color in the heatmap gets brighter and moves from blue to yellow, the higher the count of points in the corresponding cell.

Heatmaps can also be used as 2-d versions of bar charts, plotting counts on combinations of two categorical variables instead of numeric variables. There is a function in seaborn, `heatmap`, that is built for categorical heatmaps. This will be discussed in more detail later in the lesson, in the section "Clustered Bar Charts".

## Additional Variations

To select a different color palette, you can set the "cmap" parameter in `hist2d`. The most convenient way of doing this is to set the "cmap" value as a string referencing a built-in Matplotlib palette. A list of valid strings can be found on [this part](https://matplotlib.org/api/pyplot_summary.html#colors-in-matplotlib) of the Pyplot API documentation. A further discussion of color in plots will be left to the next lesson. For now, I will just show an example of reversing the default "viridis" color palette, by setting `cmap = 'viridis_r'`.

Furthermore, I would like to distinguish cells with zero counts from those with non-zero counts. The "cmin" parameter specifies the minimum value in a cell before it will be plotted. By adding a `cmin = 0.5` parameter to the `hist2d` call, this means that a cell will only get colored if it contains at least one point.

```
bins_x = np.arange(0.5, 10.5+1, 1)
bins_y = np.arange(-0.5, 10.5+1, 1)
plt.hist2d(data = df, x = 'disc_var1', y = 'disc_var2',
           bins = [bins_x, bins_y], cmap = 'viridis_r', cmin = 0.5)
plt.colorbar()

```

![img](https://video.udacity-data.com/topher/2018/March/5ab172c4_l4-c04-heatmap2/l4-c04-heatmap2.png)

If you have a lot of data, you might want to add annotations to cells in the plot indicating the count of points in each cell. From `hist2d`, this requires the addition of text elements one by one, much like how text annotations were added one by one to the bar plots in the previous lesson. We can get the counts to annotate directly from what is returned by `hist2d`, which includes not just the plotting object, but an array of counts and two vectors of bin edges.

```
# hist2d returns a number of different variables, including an array of counts
bins_x = np.arange(0.5, 10.5+1, 1)
bins_y = np.arange(-0.5, 10.5+1, 1)
h2d = plt.hist2d(data = df, x = 'disc_var1', y = 'disc_var2',
               bins = [bins_x, bins_y], cmap = 'viridis_r', cmin = 0.5)
counts = h2d[0]

# loop through the cell counts and add text annotations for each
for i in range(counts.shape[0]):
    for j in range(counts.shape[1]):
        c = counts[i,j]
        if c >= 7: # increase visibility on darkest cells
            plt.text(bins_x[i]+0.5, bins_y[j]+0.5, int(c),
                     ha = 'center', va = 'center', color = 'white')
        elif c > 0:
            plt.text(bins_x[i]+0.5, bins_y[j]+0.5, int(c),
                     ha = 'center', va = 'center', color = 'black')

```

![img](https://video.udacity-data.com/topher/2018/March/5ab17c13_l4-c04-heatmap3/l4-c04-heatmap3.png)

If you have too many cells in your heat map, then the annotations will end up being too overwhelming, too much to attend to. In cases like that, it's best to leave off the annotations and let the data and colorbar speak for themselves. You're more likely to see annotations in a categorical heat map, where there are going to be fewer cells plotted. Indeed, there is a parameter built into seaborn's `heatmap` function for just that, as will be seen later.



## Violin Plots

There are a few ways of plotting the relationship between one quantitative and one qualitative variable, that demonstrate the data at different levels of abstraction. The **violin plot** is on the lower level of abstraction. For each level of the categorical variable, a distribution of the values on the numeric variable is plotted. The distribution is plotted as a kernel density estimate, something like a smoothed histogram. There is an extra section at the end of the previous lesson that provides more insight into kernel density estimates.

Seaborn's [`violinplot`](https://seaborn.pydata.org/generated/seaborn.violinplot.html) function can be used to create violin plots combined with box plots – we'll discuss box plots on the next page.

```
sb.violinplot(data = df, x = 'cat_var', y = 'num_var')

```

![img](https://video.udacity-data.com/topher/2018/March/5ab1a954_l4-c06-violinplot1/l4-c06-violinplot1.png)

Here, you can see that the numeric data takes on a different shape in each categorical level: Some bimodality is suggested in group Alpha, a relatively high variance is observed in Beta, and Gamma and Delta are skewed negatively and positively, respectively. You can also see that each level has been rendered in a different color, like how the plain `countplot` was in the previous lesson. We can set the "color" parameter to make each curve the same color if it is not meaningful.

Inside each curve, there is a black shape with a white dot inside. This is the miniature box plot mentioned above. A further discussion of box plots will be performed on the next page. If you'd like to remove the box plot, you can set the `inner = None` parameter in the `violinplot` call to simplify the look of the final visualization.

```
base_color = sb.color_palette()[0]
sb.violinplot(data = df, x = 'cat_var', y = 'num_var', color = base_color,
              inner = None)

```

![img](https://video.udacity-data.com/topher/2018/March/5ab20251_l4-c06-violinplot2/l4-c06-violinplot2.png)

## Additional Variation

Much like how the bar chart could be rendered with horizontal bars, the violin plot can also be rendered horizontally. Seaborn is smart enough to make an appropriate inference on which orientation is requested, depending on whether "x" or "y" receives the categorical variable. But if both variables are numeric (e.g., one is discretely-valued) then the "orient" parameter can be used to specify the plot orientation.

```
base_color = sb.color_palette()[0]
sb.violinplot(data = df, x = 'num_var', y = 'cat_var', color = base_color,
              inner = None)

```

![img](https://video.udacity-data.com/topher/2018/March/5ab203d6_l4-c06-violinplot3/l4-c06-violinplot3.png)





## Box Plots

A **box plot** is another way of showing the relationship between a numeric variable and a categorical variable. Compared to the violin plot, the box plot leans more on summarization of the data, primarily just reporting a set of descriptive statistics for the numeric values on each categorical level. A box plot can be created using seaborn's [`boxplot`](https://seaborn.pydata.org/generated/seaborn.boxplot.html) function.

```
plt.figure(figsize = [10, 5])
base_color = sb.color_palette()[0]

# left plot: violin plot
plt.subplot(1, 2, 1)
ax1 = sb.violinplot(data = df, x = 'cat_var', y = 'num_var', color = base_color)

# right plot: box plot
plt.subplot(1, 2, 2)
sb.boxplot(data = df, x = 'cat_var', y = 'num_var', color = base_color)
plt.ylim(ax1.get_ylim()) # set y-axis limits to be same as left plot

```

Note that the "color" parameter is being used here to make each box the same color. In order to provide a better comparison of the violin and box plots, a `ylim` expression has been added to the second plot to match the two plots' y-axis limits. The Axes object returned by `violinplot` is assigned to a variable, `ax1` is used to programmatically obtain those limit values.

(Documentation: [Axes objects](https://matplotlib.org/api/axes_api.html))

![img](https://video.udacity-data.com/topher/2018/March/5ab297bd_l4-c07-boxplot1/l4-c07-boxplot1.png)

The inner boxes and lines in the violin plot match up with the boxes and whiskers in the box plot. In a box plot, the central line in the box indicates the median of the distribution, while the top and bottom of the box represent the third and first quartiles of the data, respectively. Thus, the height of the box is the interquartile range (IQR). From the top and bottom of the box, the whiskers indicate the range from the first or third quartiles to the minimum or maximum value in the distribution. Typically, a maximum range is set on whisker length; by default this is 1.5 times the IQR. For the Gamma level, there are points below the lower whisker that indicate individual outlier points that are more than 1.5 times the IQR below the first quartile.

Comparing the two plots, the box plot is a cleaner summary of the data than the violin plot. It's easier to compare statistics between the groups with a box plot. This makes a box plot worth more consideration if you have a lot of groups to compare, or if you are building explanatory plots. You can clearly see from the box plot that the Delta group has the lowest median. On the other hand, the box plot lacks as nuanced a depiction of distributions as the violin plot: you can't see the slight bimodality present in the Alpha level values. The violin plot may be a better option for exploration, especially since seaborn's implementation also includes the box plot by default.

## Additional Variations

As with `violinplot`, `boxplot` can also render horizontal box plots by setting the numeric and categorical features to the appropriate arguments.

```
base_color = sb.color_palette()[0]
sb.boxplot(data = df, x = 'num_var', y = 'cat_var', color = base_color)

```

![img](https://video.udacity-data.com/topher/2018/March/5ab29ca8_l4-c07-boxplot2/l4-c07-boxplot2.png)

In `violinplot`, there is an additional option for plotting summary statistics in the violin, beyond the default mini box plot. By setting `inner = 'quartile'`, three lines will be plotted within each violin area for the three middle quartiles. The line with thick dashes indicates the median, and the two lines with shorter dashes on either side the first and third quartiles.

```
base_color = sb.color_palette()[0]
sb.violinplot(data = df, x = 'cat_var', y = 'num_var', color = base_color,
              inner = 'quartile')

```

![img](https://video.udacity-data.com/topher/2018/March/5ab2ac0c_l4-c07-boxplot3/l4-c07-boxplot3.png)







## Clustered Bar Charts

To depict the relationship between two categorical variables, we can extend the univariate bar chart seen in the previous lesson into a **clustered bar chart**. Like a standard bar chart, we still want to depict the count of data points in each group, but each group is now a combination of labels on two variables. So we want to organize the bars into an order that makes the plot easy to interpret. In a clustered bar chart, bars are organized into clusters based on levels of the first variable, and then bars are ordered consistently across the second variable within each cluster. This is easiest to see with an example, using seaborn's [`countplot`](https://seaborn.pydata.org/generated/seaborn.countplot.html) function. To take the plot from univariate to bivariate, we add the second variable to be plotted under the "hue" argument:

```
sb.countplot(data = df, x = 'cat_var1', hue = 'cat_var2')

```

![img](https://video.udacity-data.com/topher/2018/March/5ab2c211_l4-c09-clusteredbar1/l4-c09-clusteredbar1.png)

The first categorical variable is depicted by broad x-position (Control, Experiment A, Experiment B). Within each of these groups, three bars are plotted, one for each level of the second categorical variable (Low, Medium, High). Color differentiates each level, and is documented with the legend in the upper-right corner of the plot. The plot tells us that the three "cat_var1" groups are fairly balanced in frequencies across the "cat_var2" levels, though the "Experiment A" group appears to have slighly lower counts of "Medium" points (orange central bar) compared to the other two groups.

The legend position in this example is a bit distracting, however. We can use an [Axes method](https://matplotlib.org/api/axes_api.html) to set the legend properties on the Axes object returned from `countplot`.

```
ax = sb.countplot(data = df, x = 'cat_var1', hue = 'cat_var2')
ax.legend(loc = 8, ncol = 3, framealpha = 1, title = 'cat_var2')

```

(Documentation: [`Axes.legend`](https://matplotlib.org/api/_as_gen/matplotlib.axes.Axes.legend.html))

![img](https://video.udacity-data.com/topher/2018/March/5ab2c577_l4-c09-clusteredbar2/l4-c09-clusteredbar2.png)

## Alternative Approach (Heat Map)

One alternative way of depicting the relationship between two categorical variables is through a heat map. Heat maps were introduced earlier as the 2-d version of a histogram; here, we're using them as the 2-d version of a bar chart. The seaborn function [`heatmap`](https://seaborn.pydata.org/generated/seaborn.heatmap.html) is at home with this type of heat map implementation, but the input arguments are unlike most of the visualization functions that have been introduced in this course. Instead of providing the original dataframe, we need to summarize the counts into a matrix that will then be plotted.

```
ct_counts = df.groupby(['cat_var1', 'cat_var2']).size()
ct_counts = ct_counts.reset_index('count')
ct_counts = ct_counts.pivot(index = 'cat_var2', columns = 'cat_var1', values = 'count')

```

(Documentation: [Series `reset_index`](https://pandas.pydata.org/pandas-docs/stable/generated/pandas.DataFrame.reset_index.html), [DataFrame `pivot`](https://pandas.pydata.org/pandas-docs/stable/generated/pandas.DataFrame.pivot.html))

![img](https://video.udacity-data.com/topher/2018/March/5ab2cc3e_l4-c09-clusteredbar3/l4-c09-clusteredbar3.png)

```
sb.heatmap(ct_counts)

```

![img](https://video.udacity-data.com/topher/2018/March/5ab2cc73_l4-c09-clusteredbar4/l4-c09-clusteredbar4.png)

The heat map tells the same story as the clustered bar chart: the similar colors across the rows suggests that the "cat_var1" group sizes are similarly sized and distributed similarly across levels of "cat_var2". The Experiment A has slightly fewer counts of Medium-level observations, while Control has higher counts of High data points and Experiment B has slightly higher counts of Low points. Compared to the clustered bar chart, however, there is less precision interpreting the magnitude of differences. For this reason, we might want to add annotations to the plot to report counts within each cell.

```
sb.heatmap(ct_counts, annot = True, fmt = 'd')

```

`annot = True` makes it so annotations show up in each cell, but the default string formatting only goes to two digits of precision. Adding `fmt = 'd'` means that annotations will all be formatted as integers instead. You can use `fmt = '.0f'` if you have any cells with no counts, in order to account for NaNs.

![img](https://video.udacity-data.com/topher/2018/March/5ab2d035_l4-c09-clusteredbar5/l4-c09-clusteredbar5.png)





## Faceting

One general visualization technique that will be useful for you to know about to handle plots of two or more variables is **faceting**. In faceting, the data is divided into disjoint subsets, most often by different levels of a categorical variable. For each of these subsets of the data, the same plot type is rendered on other variables. Faceting is a way of comparing distributions or relationships across levels of additional variables, especially when there are three or more variables of interest overall. While faceting is most useful in multivariate visualization, it is still valuable to introduce the technique here in our discussion of bivariate plots.

For example, rather than depicting the relationship between one numeric variable and one categorical variable using a violin plot or box plot, we could use faceting to look at a histogram of the numeric variable for subsets of the data divided by categorical variable levels. Seaborn's [FacetGrid](https://seaborn.pydata.org/generated/seaborn.FacetGrid.html) class facilitates the creation of faceted plots. There are two steps involved in creating a faceted plot. First, we need to create an instance of the FacetGrid object and specify the feature we want to facet by ("cat_var" in our example). Then we use the `map` method on the FacetGrid object to specify the plot type and variable(s) that will be plotted in each subset (in this case, histogram on "num_var").

```
g = sb.FacetGrid(data = df, col = 'cat_var')
g.map(plt.hist, "num_var")

```

In the `map` call, just set the plotting function and variable to be plotted as positional arguments. Don't set them as keyword arguments, like `x = "num_var"`, or the mapping won't work properly.

![img](https://video.udacity-data.com/topher/2018/March/5ab2dbb4_l4-c11-faceting1/l4-c11-faceting1.png)

Notice that each subset of the data is being plotted independently. Each uses the default of ten bins from `hist` to bin together the data, and each plot has a different bin size. Despite that, the axis limits on each facet are the same to allow clear and direct comparisons between groups. It's still worth cleaning things a little bit more by setting the same bin edges on all facets. Extra visualization parameters can be set as additional keyword arguments to the `map` function.

```
bin_edges = np.arange(-3, df['num_var'].max()+1/3, 1/3)
g = sb.FacetGrid(data = df, col = 'cat_var')
g.map(plt.hist, "num_var", bins = bin_edges)

```

![img](https://video.udacity-data.com/topher/2018/March/5ab2df31_l4-c11-faceting2/l4-c11-faceting2.png)

## Additional Variation

If you have many categorical levels to plot, then you might want to add more arguments to the FacetGrid object initialization to facilitate clarity in conveyance of information. The example below includes a categorical variable, "many_cat_var", that has fifteen different levels. Setting `col_wrap = 5` means that the plots will be organized into rows of five facets each, rather than a single long row of fifteen plots.

```
group_means = df.groupby(['many_cat_var']).mean()
group_order = group_means.sort_values(['num_var'], ascending = False).index

g = sb.FacetGrid(data = df, col = 'many_cat_var', col_wrap = 5, size = 2,
                 col_order = group_order)
g.map(plt.hist, 'num_var', bins = np.arange(5, 15+1, 1))
g.set_titles('{col_name}')

```

Other operations may be performed to increase the immediate readability of the plots: setting each facet height to 2 inches ("size"), sorting the facets by group mean ("col_order"), limiting the number of bin edges, and changing the titles of each facet to just the categorical level name using the `set_titles` method and `{col_name}` template variable.

![img](https://video.udacity-data.com/topher/2018/March/5ab2f284_l4-c11-faceting3/l4-c11-faceting3.png)



## Adapted Bar Charts

Histograms and bar charts were introduced in the previous lesson as depicting the distribution of numeric and categorical variables, respectively, with the height (or length) of bars indicating the number of data points that fell within each bar's range of values. These plots can be adapted for use as bivariate plots by, instead of indicating count by height, indicating a mean or other statistic on a second variable.

For example, we could plot a numeric variable against a categorical variable by adapting a bar chart so that its bar heights indicate the mean of the numeric variable. This is the purpose of seaborn's [`barplot`](https://seaborn.pydata.org/generated/seaborn.barplot.html) function:

```
base_color = sb.color_palette()[0]
sb.barplot(data = df, x = 'cat_var', y = 'num_var', color = base_color)

```

Different hues are automatically assigned to each category level unless a fixed color is set in the "color" parameter, like in `countplot` and `violinplot`.

![img](https://video.udacity-data.com/topher/2018/March/5ab2f6cd_l4-c12-adaptations1/l4-c12-adaptations1.png)

The bar heights indicate the mean value on the numeric variable, with error bars plotted to show the uncertainty in the mean based on variance and sample size. The Delta bar dips below the 0 axis due to the negative mean.

As an alternative, the [`pointplot`](https://seaborn.pydata.org/generated/seaborn.pointplot.html) function can be used to plot the averages as points rather than bars. This can be useful if having bars in reference to a 0 baseline aren't important or would be confusing.

```
sb.pointplot(data = df, x = 'cat_var', y = 'num_var', linestyles = "")
plt.ylabel('Avg. value of num_var')

```

By default, `pointplot`will connect values by a line. This is fine if the categorical variable is ordinal in nature, but it can be a good idea to remove the line via `linestyles = ""` for nominal data.

![img](https://video.udacity-data.com/topher/2018/March/5ab34369_l4-c12-adaptations2/l4-c12-adaptations2.png)

The above plots can be useful alternatives to the box plot and violin plot if the data is not conducive to either of those plot types. For example, if the numeric variable is binary in nature, taking values only of 0 or 1, then a box plot or violin plot will not be informative, leaving the adapted bar chart as the best choice for displaying the data.

```
plt.figure(figsize = [12, 5])
base_color = sb.color_palette()[0]

# left plot: violin plot
plt.subplot(1, 3, 1)
sb.violinplot(data = df, x = 'condition', y = 'binary_out', inner = None,
              color = base_color)
plt.xticks(rotation = 10) # include label rotation due to small subplot size

# center plot: box plot
plt.subplot(1, 3, 2)
sb.boxplot(data = df, x = 'condition', y = 'binary_out', color = base_color)
plt.xticks(rotation = 10)

# right plot: adapted bar chart
plt.subplot(1, 3, 3)
sb.barplot(data = df, x = 'condition', y = 'binary_out', color = base_color)
plt.xticks(rotation = 10)

```

![img](https://video.udacity-data.com/topher/2018/March/5ab34899_l4-c12-adaptations3/l4-c12-adaptations3.png)

## Adapted Histograms

Matplotlib's `hist` function can also be adapted so that bar heights indicate value other than a count of points through the use of the "weights" parameter. By default, each data point is given a weight of 1, so that the sum of point weights in each bin is equal to the number of points. If we change the weights to be a representative function of each point's value on a second variable, then the sum will end up representing something other than a count.

```
bin_edges = np.arange(0, df['num_var'].max()+1/3, 1/3)

# count number of points in each bin
bin_idxs = pd.cut(df['num_var'], bin_edges, right = False, include_lowest = True,
                  labels = False).astype(int)
pts_per_bin = df.groupby(bin_idxs).size()

num_var_wts = df['binary_out'] / pts_per_bin[bin_idxs].values

# plot the data using the calculated weights
plt.hist(data = df, x = 'num_var', bins = bin_edges, weights = num_var_wts)
plt.xlabel('num_var')
plt.ylabel('mean(binary_out)')

```

To get the mean of the y-variable ("binary_out") in each bin, the weight of each point should be equal to the y-variable value, divided by the number of points in its x-bin (`num_var_wts`). As part of this computation, we make use of pandas' [`cut`](https://pandas.pydata.org/pandas-docs/stable/generated/pandas.cut.html) function in order to associate each data point to a particular bin (`bin_idxs`). The `labels = False` parameter means that each point's bin membership is associated by a numeric index, rather than a string. We use these numeric indices into the `pts_per_bin`, with the `.values` at the end necessary in order for the Series' indices to not be confused between the indices of `df['binary_out']`.

![img](https://video.udacity-data.com/topher/2018/November/5becb09b_l4-c12-adaptations4/l4-c12-adaptations4.png)

This plot shows that the average outcome of the y-variable "binary_out" generally increases across values of the x-variable "num_var".

More commonly, you'll see plots summarizing one numeric variable against values of a second numeric variable not as adapted histograms, but instead as line plots. These are covered on the next page.



## Line Plots

The **line plot** is a fairly common plot type that is used to plot the trend of one numeric variable against values of a second variable. In contrast to a scatterplot, where all data points are plotted, in a line plot, only one point is plotted for every unique x-value or bin of x-values (like a histogram). If there are multiple observations in an x-bin, then the y-value of the point plotted in the line plot will be a summary statistic (like mean or median) of the data in the bin. The plotted points are connected with a line that emphasizes the sequential or connected nature of the x-values.

If the x-variable represents time, then a line plot of the data is frequently known as a **time series** plot. Often, we have only one observation per time period, like in stock or currency charts. While there is a seaborn function [`tsplot`](https://seaborn.pydata.org/generated/seaborn.tsplot.html) that is intended to be used with time series data, it is fairly specialized and (as of this writing's seaborn 0.8) is slated for major changes.

Instead, we will make use of Matplotlib's [`errorbar`](https://matplotlib.org/api/_as_gen/matplotlib.pyplot.errorbar.html) function, performing some processing on the data in order to get it into its necessary form.

```
plt.errorbar(data = df, x = 'num_var1', y = 'num_var2')

```

![img](https://video.udacity-data.com/topher/2018/March/5ab445d9_l4-c13-lineplot1/l4-c13-lineplot1.png)

If we just blindly stick a dataframe into the function without considering its structure, we might end up with a mess like the above. The function just plots all the data points as a line, connecting values from the first row of the dataframe to the last row. In order to create the line plot as intended, we need to do additional work to summarize the data.

```
# set bin edges, compute centers
bin_size = 0.25
xbin_edges = np.arange(0.5, df['num_var1'].max()+bin_size, bin_size)
xbin_centers = (xbin_edges + bin_size/2)[:-1]

# compute statistics in each bin
data_xbins = pd.cut(df['num_var1'], xbin_edges, right = False, include_lowest = True)
y_means = df['num_var2'].groupby(data_xbins).mean()
y_sems = df['num_var2'].groupby(data_xbins).sem()

# plot the summarized data
plt.errorbar(x = xbin_centers, y = y_means, yerr = y_sems)
plt.xlabel('num_var1')
plt.ylabel('num_var2')

```

Since the x-variable ('num_var1') is continuous, we first set a number of bins into which the data will be grouped. In addition to the usual edges, the center of each bin is also computed for later plotting. For the points in each bin, we compute the mean and standard error of the mean. Note that the [`cut`](https://pandas.pydata.org/pandas-docs/stable/generated/pandas.cut.html) function call is simpler here than in the previous page, since we don't need to compute individual point weights.

![img](https://video.udacity-data.com/topher/2018/November/5becb159_l4-c13-lineplot2/l4-c13-lineplot2.png)

An interesting part of the above summarization of the data is that the uncertainty in the mean generally increases with increasing x-values. But for the largest two points, there are no error bars. Looking at the default `errorbar` plot (or the scatterplot below), we can see this is due to there only being one point in each of the last two bins.

## Alternate Variations

Instead of computing summary statistics on fixed bins, you can also make computations on a rolling window through use of pandas' [`rolling`](https://pandas.pydata.org/pandas-docs/stable/generated/pandas.DataFrame.rolling.html) method. Since the rolling window will make computations on sequential rows of the dataframe, we should use [`sort_values`](https://pandas.pydata.org/pandas-docs/stable/generated/pandas.DataFrame.sort_values.html) to put the x-values in ascending order first.

```
# compute statistics in a rolling window
df_window = df.sort_values('num_var1').rolling(15)
x_winmean = df_window.mean()['num_var1']
y_median = df_window.median()['num_var2']
y_q1 = df_window.quantile(.25)['num_var2']
y_q3 = df_window.quantile(.75)['num_var2']

# plot the summarized data
base_color = sb.color_palette()[0]
line_color = sb.color_palette('dark')[0]
plt.scatter(data = df, x = 'num_var1', y = 'num_var2')
plt.errorbar(x = x_winmean, y = y_median, c = line_color)
plt.errorbar(x = x_winmean, y = y_q1, c = line_color, linestyle = '--')
plt.errorbar(x = x_winmean, y = y_q3, c = line_color, linestyle = '--')

plt.xlabel('num_var1')
plt.ylabel('num_var2')

```

Note that we're also not limited to just one line when plotting. When multiple Matplotlib functions are called one after the other, all of them will be plotted on the same axes. Instead of plotting the mean and error bars, we will plot the three central quartiles, laid on top of the scatterplot.

![img](https://video.udacity-data.com/topher/2018/November/5becb168_l4-c13-lineplot3/l4-c13-lineplot3.png)

Another bivariate application of line plots is to plot the distribution of a numeric variable for different levels of a categorical variable. This is another alternative to using violin plots, box plots, and faceted histograms. With the line plot, one line is plotted for each category level, like overlapping the histograms on top of one another. This can be accomplished through multiple `errorbar` calls using the methods above, or by performing multiple [`hist`](https://matplotlib.org/api/_as_gen/matplotlib.pyplot.hist.html) calls, setting the "histtype = step" parameter so that the bars are depicted as unfilled lines.

```
bin_edges = np.arange(-3, df['num_var'].max()+1/3, 1/3)
g = sb.FacetGrid(data = df, hue = 'cat_var', size = 5)
g.map(plt.hist, "num_var", bins = bin_edges, histtype = 'step')
g.add_legend()

```

Note that I'm performing the multiple `hist` calls through the use of [FacetGrid](https://seaborn.pydata.org/generated/seaborn.FacetGrid.html), setting the categorical variable on the "hue" parameter rather than the "col" parameter. You'll see more of this parameter of FacetGrid in the next lesson. I've also added an `add_legend` method call so that we can identify which level is associated with each curve.

![img](https://video.udacity-data.com/topher/2018/March/5ab4b468_l4-c13-lineplot4/l4-c13-lineplot4.png)

Unfortunately, the "Alpha" curve seems to be pretty lost behind the other three curves since the relatively low number of counts is causing a lot of overlap. Perhaps connecting the centers of the bars with a line, like what was seen in the first `errorbar` example, would be better.

Functions you provide to the `map` method of FacetGrid objects do not need to be built-ins. Below, I've written a function to perform the summarization operations seen above to plot an `errorbar` line for each level of the categorical variable, then fed that function (`freq_poly`) to `map`.

```
def freq_poly(x, bins = 10, **kwargs):
    """ Custom frequency polygon / line plot code. """
    # set bin edges if none or int specified
    if type(bins) == int:
        bins = np.linspace(x.min(), x.max(), bins+1)
    bin_centers = (bin_edges[1:] + bin_edges[:-1]) / 2

    # compute counts
    data_bins = pd.cut(x, bins, right = False,
                       include_lowest = True)
    counts = x.groupby(data_bins).count()

    # create plot
    plt.errorbar(x = bin_centers, y = counts, **kwargs)

bin_edges = np.arange(-3, df['num_var'].max()+1/3, 1/3)
g = sb.FacetGrid(data = df, hue = 'cat_var', size = 5)
g.map(freq_poly, "num_var", bins = bin_edges)
g.add_legend()

```

`**kwargs` is used to allow additional keyword arguments to be set for the `errorbar` function.

(Documentation: [numpy `linspace`](https://docs.scipy.org/doc/numpy/reference/generated/numpy.linspace.html))

![img](https://video.udacity-data.com/topher/2018/March/5ab545af_l4-c13-lineplot5/l4-c13-lineplot5.png)



There might be cases where you are interested to see how closely your numeric data follows some hypothetical distribution. This might be important for certain parametric statistical tests, like checking for assumptions of normality. In cases like this, you can use a quantile-quantile plot, or **Q-Q plot**, to make a visual comparison between your data and your reference distribution. Take for example the following comparison of the following data and a hypothetical normal distribution using the sample statistics:

```
# create a histogram of the data
bin_size = 0.5
bin_edges = np.arange(4, 18 + bin_size, bin_size)
plt.hist(data = df, x = 'num_var', bins = bin_edges);

# overlay a theoretical normal distribution on top
samp_mean = df['num_var'].mean()
samp_sd = df['num_var'].std()

from scipy.stats import norm
x = np.linspace(4, 18, 200)
y = norm.pdf(x, samp_mean, samp_sd) # normal distribution heights
y *= df.shape[0] * bin_size # scale the distribution height

plt.plot(x, y)

```

The matplotlib [`plot`](https://matplotlib.org/api/_as_gen/matplotlib.pyplot.plot.html) function is a generic function for plotting y-values against x-values, by default a line connecting each x-y pair in sequence. In this case, I first use numpy's [`linspace`](https://docs.scipy.org/doc/numpy-1.15.0/reference/generated/numpy.linspace.html) function to generate x-values across the range of the plot. Note that the first two arguments match the `bin_edges` limits, while the third argument specifies the number of values to generate between the two endpoints. Then, I use the scipy package's [`norm`](https://docs.scipy.org/doc/scipy-0.15.1/reference/generated/scipy.stats.norm.html) class to get the height of the normal distribution curve at those x-values, using the sample mean and standard deviation as distribution parameters. `pdf` stands for probability density function, which returns the normal distribution height (density) at each value of x. These values are such that the total area under the curve will add up to 1. Since we've got a histogram with absolute counts on the y-axis, we need to scale the curve so it's on the same scale as the main plot: we do this by multiplying the curve heights by the number of data points and bin size. The code above gives us the following plot:

![img](https://video.udacity-data.com/topher/2018/November/5be4d7a4_l4-c16-qqplot1/l4-c16-qqplot1.png)

From a visual inspection of this overlaid plot, it looks like the data is a bit sparse on the right side compared to the expected normal distribution. There's also a bit of a spike of values between 11 and 12. On the other hand, the left side of the curve isn't too far off from the expected distribution, though it might be said that we might be missing some expected points in the left tail of the distribution. The question that we'd like to address is if there's enough evidence from what we've observed to say that the data is significantly different from the expected normal distribution.

One way we could approach this is through a statistical test, such as using scipy's [`shapiro`](https://docs.scipy.org/doc/scipy-0.15.1/reference/generated/scipy.stats.shapiro.html) function to perform the Shapiro-Wilk test. But since this is a course on data visualization, we'll inspect this question visually, using the Q-Q plot type teased at the top of the page. The main idea of the plot is this: if the data was normally distributed, then we'd expect a certain pattern in terms of how far each data point is from the mean of the distribution. If we order the points from smallest to largest, then we could compare how large the _k_-th ranked data point is against the _k_-th ranked point from the expected distribution.

To get these expected values, we'll make use of the `norm` class's `ppf` function, which stands for percent point function. The *ppf* takes as input a proportion (valued between 0 and 1) and returns the value in the distribution that would leave that proportion of the curve to the left. For a standard normal distribution (mean = 0, standard deviation = 1), the ppf(0.25) = -0.674ppf(0.25)=−0.674, ppf(0.5) = 0ppf(0.5)=0, and ppf(0.75) = 0.674ppf(0.75)=0.674. The main question, then, is what values to stick into the *ppf*.

There's a few different conventions around this, but they generally take the form of the following equation:

> Given _n_ data points, the _k_-th value should be at probability point \frac{k-a}{n+1-2a}n+1−2ak−a, for some _a_ between 0 and 1 (inclusive).

This equation distributes the probability points symmetrically about 0.5, and adjusting _a_ changes how much probability is left in the tails of the [0,1] range. Commonly, _a_ is set to a balanced value of 0.5, which gives the equation \frac{k-0.5}{n}nk−0.5. Let's put this all together using code:

```
n_points = df.shape[0]
qs = (np.arange(n_points) - .5) / n_points
expected_vals = norm.ppf(qs, samp_mean, samp_sd)

plt.scatter(expected_vals, df['num_var'].sort_values())
plt.plot([4,18],[4,18],'--', color = 'black')
plt.axis('equal')
plt.xlabel('Expected Values')
plt.ylabel('Observed Values')

```

It's a good idea to label the axes in this case. Since the actual and expected data are both on the same scale, the labels are a big help to keep things clear. In addition, rather than just plotting the expected and actual data alone, I've also added another `plot` call to add a diagonal x = y line. If the data matches the actual values perfectly on the expected value, they will fall directly on that diagonal line. The `plt.axis('equal')` line supports the visualization, as it will set the axis scaling to be equal, and the diagonal line will be at a 45 degree angle.

![img](https://video.udacity-data.com/topher/2018/November/5be5e565_l4-c16-qqplot2/l4-c16-qqplot2.png)

Excepting the smallest and largest few points, the distribution of observed values is actually fairly in line with the distribution of expected values – that is, it falls along the diagonal line. The smallest and largest observed points are larger than the values that would be expected from the normal distribution, but it's not by much. Given how much farther values can get spread out in the tails of the normal distribution, this shouldn't be a major concern. We're probably fine in treating the data as normally distributed.

Usually, the Q-Q plot is computed and rendered in terms of standardized units, rather than the scale of the original data. A standardized dataset has a mean of 0 and standard deviation of 1, so to convert a set of values into standard scores, we just need to subtract the sample mean from each value to center it around 0, then divide by the sample standard deviation to scale it. Calling methods of the `norm` class without arguments for the mean or standard deviation assume the standard normal distribution. The code changes as follows:

```
expected_scores = norm.ppf(qs)
data_scores = (df['num_var'].sort_values() - samp_mean) / samp_sd

plt.scatter(expected_scores, data_scores)
plt.plot([-2.5,3],[-2.5,3],'--', color = 'black')
plt.axis('equal')
plt.xlabel('Expected Standard Scores')
plt.ylabel('Observed Standard Scores')

```

![img](https://video.udacity-data.com/topher/2018/November/5be600cf_l4-c16-qqplot3/l4-c16-qqplot3.png)

Notice that the shape of the data has not changed since both datasets have been scaled in the exact same way. One of the reasons for performing this scaling is that it makes it easier to talk about the data values against the expected, theoretical distribution. In the first plot, there's no clear indication of where the center of the data lies, and how spread out the data is from that center. In the latter plot, we can use our expectations for how much of the data should be one or two standard deviations from the mean to better understand how the data is distributed. It also separates the values of the theoretical distribution from any properties of the observed data.

Before closing this page out, let's take a quick look at the Q-Q plot when the data distribution does *not* fit the normal distribution assumptions. Instead of generating data from a normal distribution, I'll now generate data from a uniform distribution:

```
# generate the data
np.random.seed(8322489)

n_points = 120
unif_data = np.random.uniform(0, 10, n_points)

# set up the figure
plt.figure(figsize = [12, 5])

# left subplot: plot the data
plt.subplot(1, 2, 1)
bin_size = 0.5
bin_edges = np.arange(0, 10 + bin_size, bin_size)
plt.hist(x = unif_data, bins = bin_edges);

# overlay a theoretical normal distribution on top
samp_mean = unif_data.mean()
samp_sd = unif_data.std()

from scipy.stats import norm
x = np.linspace(0, 10, 200)
y = norm.pdf(x, samp_mean, samp_sd) # normal distribution heights
y *= n_points * bin_size # scale the distribution height
plt.plot(x, y)

# right subplot: create a Q-Q plot
plt.subplot(1, 2, 2)

qs = (np.arange(n_points) - .5) / n_points
expected_scores = norm.ppf(qs)
data_scores = (np.sort(unif_data) - samp_mean) / samp_sd

plt.scatter(expected_scores, data_scores)
plt.plot([-2.5,2.5],[-2.5,2.5],'--', color = 'black')
plt.axis('equal')
plt.xlabel('Expected Standard Scores')
plt.ylabel('Observed Standard Scores')

```

![img](https://video.udacity-data.com/topher/2018/November/5be602af_l4-c16-qqplot4/l4-c16-qqplot4.png)

Left: Original data; Right: Q-Q plot

When we compare the random standardized scores drawn from the uniform distribution to the expected scores from the theoretical normal distribution in the Q-Q plot, we see an S-shaped curve. The comparison of values in the middle of the curve are approximately linear in trend, but the slope is steeper than the desired y = x. Meanwhile on the edges, the slope is extremely shallow, as the uniform distribution is fixed to a finite range, but the normal distribution values in the tails are expected to be much further away. You can somewhat see this in the superimposed distribution line in the left-side plot, where even at the edges of the data, there is still quite a bit of height to the theoretical normal curve. All of this contributes to the result that the randomly-generated uniform data can't be well-approximated by the normal distribution.



## Swarm Plots

In this lesson, you saw many ways of depicting the relationship between a numeric variable and a categorical variable. Violin plots depicted distributions as density curves, while box plots took a more summary approach, plotting the quantiles as boxes with whiskers. Another alternative to these plots is the **swarm plot**. Similar to a scatterplot, each data point is plotted with position according to its value on the two variables being plotted. Instead of randomly jittering points as in a normal scatterplot, points are placed as close to their actual value as possible without allowing any overlap. A swarm plot can be created in seaborn using the [`swarmplot`](https://seaborn.pydata.org/generated/seaborn.swarmplot.html) function, similar to how you would a call `violinplot` or `boxplot`.

```
plt.figure(figsize = [12, 5])
base_color = sb.color_palette()[0]

# left plot: violin plot
plt.subplot(1, 3, 1)
ax1 = sb.violinplot(data = df, x = 'cat_var', y = 'num_var', color = base_color)

# center plot: box plot
plt.subplot(1, 3, 2)
sb.boxplot(data = df, x = 'cat_var', y = 'num_var', color = base_color)
plt.ylim(ax1.get_ylim()) # set y-axis limits to be same as left plot

# right plot: swarm plot
plt.subplot(1, 3, 3)
sb.swarmplot(data = df, x = 'cat_var', y = 'num_var', color = base_color)
plt.ylim(ax1.get_ylim()) # set y-axis limits to be same as left plot

```

![img](https://video.udacity-data.com/topher/2018/March/5ab55333_l4-c18-swarmplot1/l4-c18-swarmplot1.png)

Looking at the plots side by side, you can see relative pros and cons of the swarm plot. Unlike the violin plot and box plot, every point is plotted, so we can now compare the frequency of each group in the same plot. While there is some distortion due to location jitter, we also have a more concrete picture of where the points actually lie, removing the long tails that can be present in violin plots.

However, it is only reasonable to use a swarm plot if we have a small or moderate amount of data. If we have too many points, then the restrictions against overlap will cause too much distortion or require a lot of space to plot the data comfortably. In addition, having too many points can actually be a distraction, making it harder to see the key signals in the visualization. Use your findings from univariate visualizations to inform which bivariate visualizations will be best, or simply experiment with different plot types to see what is most informative.



## Rug and Strip Plots

You might encounter, or be interested in, marginal distributions that are plotted alongside bivariate plots such as scatterplots. A marginal distribution is simply the univariate distribution of a variable, ignoring the values of any other variable. For quantitative data, histograms or density curves are fine choices for marginal plot, but you might also see the **rug plot** employed. In a rug plot, all of the data points are plotted on a single axis, one tick mark or line for each one. Compared to a marginal histogram, the rug plot suffers somewhat in terms of readability of the distribution, but it is more compact in its representation of the data.

Seaborn's [JointGrid](https://seaborn.pydata.org/generated/seaborn.JointGrid.html) class enables this plotting of bivariate relationship with marginal univariate plots for numeric data. The `plot_joint` method specifies a plotting function for the main, joint plot for the two variables, while the `plot_marginals` method specifies the plotting function for the two marginal plots. Here, we make use of seaborn's [`rugplot`](https://seaborn.pydata.org/generated/seaborn.rugplot.html) function.

```
g = sb.JointGrid(data = df, x = 'num_var1', y = 'num_var2')
g.plot_joint(plt.scatter)
g.plot_marginals(sb.rugplot, height = 0.25)

```

The "height" parameter specifies the rug ticks to be 0.25 the height of the marginal axis size.

![img](https://video.udacity-data.com/topher/2018/March/5ab58c38_l4-c17-rugplot1/l4-c17-rugplot1.png)

The rug plot is fine here since the data isn't particularly numerous or overly dense. In other circumstances, a histogram or density curve will be more appropriate. You probably won't consider the rug plot as a primary plot choice, but it can be a good supporter plot in certain circumstances.

Another supporting plot type similar to the rug plot is the **strip plot**. It's like a swarm plot (see the previous page) but without any dodging or jittering to keep points separate or off the categorical line. You can also think of it as a rug plot faceted by categorical levels. You can use seaborn's [`swarmplot`](https://seaborn.pydata.org/generated/seaborn.swarmplot.html) function to add a swarm plot to any other plot. The `inner = "stick"` and `inner = "point"` options can also be used with the `violinplot` function to include a swarm plot inside of the violin areas, instead of a box plot.

```
plt.figure(figsize = [10, 5])
base_color = sb.color_palette()[0]

# left plot: strip plot
plt.subplot(1, 2, 1)
ax1 = sb.stripplot(data = df, x = 'num_var', y = 'cat_var',
                   color = base_color)

# right plot: violin plot with inner strip plot as lines
plt.subplot(1, 2, 2)
sb.violinplot(data = df, x = 'num_var', y = 'cat_var', color = base_color,
             inner = 'stick')

```

![img](https://video.udacity-data.com/topher/2018/March/5ab9416a_l4-c17-rugplot2/l4-c17-rugplot2.png)



One common plotting technique has not been discussed thus far in the course, and that’s **stacking**. Stacked bar charts and histograms are not uncommon, but there are often better plot choices available.

The most basic stacked chart takes a single bar representing the full count, and divides it into colored segments based on frequencies on a categorical variable. If this sounds familiar, that's because it almost perfectly coincides with the description of a pie chart, except that the shape being divided is different.

```
# pre-processing: count and sort by the number of instances of each category
sorted_counts = df['cat_var'].value_counts()

# establish the Figure
plt.figure(figsize = [12, 5])

# left plot: pie chart
plt.subplot(1, 2, 1)
plt.pie(sorted_counts, labels = sorted_counts.index, startangle = 90,
        counterclock = False);
plt.axis('square');

# right plot: horizontally stacked bar
plt.subplot(1, 2, 2)
baseline = 0
for i in range(sorted_counts.shape[0]):
    plt.barh(y = 1, width = sorted_counts[i], left = baseline)
    baseline += sorted_counts[i]

plt.legend(sorted_counts.index)  # add a legend for labeling
plt.ylim([0,2]) # give some vertical spacing around the bar

```

The stacked bar is built through successive calls of the matplotlib [`barh`](https://matplotlib.org/api/_as_gen/matplotlib.pyplot.barh.html) function; each time the function is called, the bar that is plotted is assigned a new color. The choice of "y" is arbitrary: it'll just center the bar around y = 1, but it doesn't have any inherent meaning. The "left" parameter specifies the left edge of each bar added to the stack, which starts at the `baseline` of 0 and is built up with each stacked bar. Note in this case that the bar is being plotted with absolute counts, rather than proportions. A discussion of absolute vs. relative frequencies will come later down the page!

![img](https://video.udacity-data.com/topher/2018/November/5bdcb28b_l4-c19-stackedbars1/l4-c19-stackedbars1.png)

Given this similarity, cautions regarding use of the stacked bar are fairly similar to that of the pie chart:

- Make sure that relative frequencies are a meaningful comparison.
- Try to limit yourself to a small number of categories, up to about five.
- Make sure that categories are arranged in a sensible order, e.g. by frequency for nominal data or by levels for ordinal data.

Otherwise, the standard bar chart is a reliable option that should be used in most cases. Only use the pie chart or singly divided bar if there's a compelling reason to do so.

The debate becomes more interesting when multiple features get involved. When should we feel free to create a stacked bar chart versus using a clustered bar chart? There are two major categories of stacked bar chart that I want to focus on here: plotting by absolute frequency and plotting by relative frequency. We'll start with code for an absolute frequency stacked chart below.

```
cat1_order = ['East', 'South', 'West', 'North']
cat2_order = ['Type X', 'Type Y', 'Type Z', 'Type O']

plt.figure(figsize = [12, 5])

# left plot: clustered bar chart, absolute counts
plt.subplot(1, 2, 1)
sb.countplot(data = df, x = 'cat_var1', hue = 'cat_var2',
             order = cat1_order, hue_order = cat2_order)
plt.legend()

# right plot: stacked bar chart, absolute counts
plt.subplot(1, 2, 2)

baselines = np.zeros(len(cat1_order))
# for each second-variable category:
for i in range(len(cat2_order)):
    # isolate the counts of the first category,
    cat2 = cat2_order[i]
    inner_counts = df[df['cat_var2'] == cat2]['cat_var1'].value_counts()
    # then plot those counts on top of the accumulated baseline
    plt.bar(x = np.arange(len(cat1_order)), height = inner_counts[cat1_order],
            bottom = baselines)
    baselines += inner_counts[cat1_order]

plt.xticks(np.arange(len(cat1_order)), cat1_order)
plt.legend(cat2_order)

```

The strategy for this plot is very similar to the single stacked bar shown above, except that we're using the standard [`bar`](https://matplotlib.org/api/_as_gen/matplotlib.pyplot.bar.html) with "x" and "bottom" parameters, and that `baselines` is a list of base heights. We want to create all of the bars for a particular secondary category at the same time so that creation of the legend has a 1:1 mapping to `bar` calls. You might notice below that the order of labels in the legend is the reverse of the order in which the bars are stacked. You'll see code to handle this in the relative frequency plot below!

![img](https://video.udacity-data.com/topher/2018/November/5be095c0_l4-c19-stackedbars2/l4-c19-stackedbars2.png)

The stacked bar chart plotted by absolute frequency carries one big advantage over the clustered bar chart: for the variable plotted on the x-axis, it's clear which category level has the highest frequency, in this case "East". The values of this variable can be interpreted just like the univariate bar chart. The disadvantage of the stacked bar chart comes with interpretation of the second, stacked variable. If you want to compare the relative counts of this second variable across levels of the first, you can really only do that for the category plotted on the baseline, which in this case is the blue one, "Type X". For the remaining categories, it's much harder to make the comparison of values – you can't really tell that the counts of "Type O" are larger in the "South" than the "North" from the stacked chart, where it's directly comparable in the clustered bar chart.

Now, let's take a look at what happens when we create the stacked bar chart with relative frequencies instead, where each bar is scaled to a total height of 1.

```
cat1_order = ['East', 'South', 'West', 'North']
cat2_order = ['Type X', 'Type Y', 'Type Z', 'Type O']

artists = [] # for storing references to plot elements
baselines = np.zeros(len(cat1_order))
cat1_counts = df['cat_var1'].value_counts()

# for each second-variable category:
for i in range(len(cat2_order)):
    # isolate the counts of the first category,
    cat2 = cat2_order[i]
    inner_counts = df[df['cat_var2'] == cat2]['cat_var1'].value_counts()
    inner_props = inner_counts / cat1_counts
    # then plot those counts on top of the accumulated baseline
    bars = plt.bar(x = np.arange(len(cat1_order)),
                   height = inner_props[cat1_order],
                   bottom = baselines)
    artists.append(bars)
    baselines += inner_props[cat1_order]

plt.xticks(np.arange(len(cat1_order)), cat1_order)
plt.legend(reversed(artists), reversed(cat2_order), framealpha = 1,
           bbox_to_anchor = (1, 0.5), loc = 6);

```

There are two main changes to this code compared to the previous plot. First of all, the `cat1_counts` variable has been computed to change the absolute frequencies into relative frequencies within each x-axis category. Secondly, some code has been added to reverse the order of bars in the legend. The `artists` variable has been added to store references to each of the bar groups added from each `bar` call. Then in the [`legend`](https://matplotlib.org/api/_as_gen/matplotlib.pyplot.legend.html) function call, we make use of the built-in Python function [`reversed`](https://docs.python.org/3/library/functions.html#reversed) to reverse the order in which the artists and labels are included in the legend. The additional parameters affect the positioning of the legend: setting an anchor for the legend box on the right side of the plot via "bbox_to_anchor", and positioning the anchor to the legend's left with "loc = 6".

![img](https://video.udacity-data.com/topher/2018/November/5be0a0aa_l4-c19-stackedbars3/l4-c19-stackedbars3.png)

Since the bars are all the same height of 1 with a relative frequency stacked bar chart, we lose the ability to compare the absolute counts on the categorical variable plotted on the x-axis (i.e. we can't tell that "East" has the most counts and "North" the least amount). In exchange, we can now compare the relative prevalence of the stacked variable on both the first category on the bottom ("Type X") as well as the category on the top ("Type O"). We can now see that, in terms of relative frequency, "Type X" has a fairly consistent presence in "South", "West", and "North", and that "Type O" has its highest relative frequency in "North". Unfortunately, this still doesn't help us make easy comparisons about the "Type Y" and "Type Z" categories that are sandwiched in between. This major limitation is a big reason why other plot types like clustered bar or line charts are often preferable to stacking.

## Further Reading

- Eager Eyes: [Stacked Bars are the Worst](https://eagereyes.org/techniques/stacked-bars-are-the-worst)
- Data Revelations: [How to take the “screaming cats” out of stacked bar and area charts](http://www.datarevelations.com/stackedbars.html)



Extra: Ridgeline PlotsSEND FEEDBACK

[**](https://classroom.udacity.com/nanodegrees/nd002/parts/9f7e8991-8bfb-4103-8307-3b6f93f0ecc7/modules/1dc09d28-5703-493c-aab5-a418b8bfa3e1/lessons/22ff3b91-42f7-420e-b6ad-de0b29684ed0/concepts/9bc43497-5cbb-4ad3-8a68-37c145cfd2c0#)

## Ridgeline Plots

One of the hot new visualization types from recent years is the **ridgeline plot**. In a nutshell, the ridgeline plot is a series of vertically faceted line plots or density curves, but with somewhat overlapping y-axes. This can be thought of as a contrast to the line plot variation seen in the "Line Plots" part of the lesson, where multiple lines were plotted on the same axes, with different hues. On this page, I'll walk through the creation of a ridgeline plot using some of the demonstration data shown in the "Faceting" page:

```
group_means = df.groupby(['many_cat_var']).mean()
group_order = group_means.sort_values(['num_var'], ascending = False).index

g = sb.FacetGrid(data = df, col = 'many_cat_var', col_wrap = 5, size = 2,
                 col_order = group_order)
g.map(plt.hist, 'num_var', bins = np.arange(5, 15+1, 1))
g.set_titles('{col_name}')

```

![img](https://video.udacity-data.com/topher/2018/March/5ab2f284_l4-c11-faceting3/l4-c11-faceting3.png)

Faceted plot, whose data will be converted into a ridgeline form

Two things immediately come to mind for changing the faceted histograms into a ridgeline plot. First of all, changing the form of the distribution plots from histograms to kernel density estimates (as seen in the Extras of the previous lesson) will make the overlaps a bit smoother. Second, we need to facet the levels by rows so that they're all stacked up on top of one another.

```
group_means = df.groupby(['many_cat_var']).mean()
group_order = group_means.sort_values(['num_var'], ascending = False).index

g = sb.FacetGrid(data = df, row = 'many_cat_var', size = 0.75, aspect = 7,
                 row_order = group_order)
g.map(sb.kdeplot, 'num_var', shade = True)
g.set_titles('{row_name}')

```

`FacetGrid` and `set_titles` change "col" to "row", also removing "col_wrap". The "size" and "aspect" dimensions have also been adjusted for the large vertical stacking of facets. The `map` function changes to `kdeplot` and removes "bins", adding the "shade" parameter in its place.

![img](https://video.udacity-data.com/topher/2018/November/5be0d242_l4-c20-ridgeline1/l4-c20-ridgeline1.png)

Now we've got all of the group distributions stacked on top of one another for a uni-dimensional comparison, but the plot's still pretty tall. Next, we'll create some overlap between the individual subplots.

```
group_means = df.groupby(['many_cat_var']).mean()
group_order = group_means.sort_values(['num_var'], ascending = False).index

# adjust the spacing of subplots with gridspec_kws
g = sb.FacetGrid(data = df, row = 'many_cat_var', size = 0.5, aspect = 12,
                 row_order = group_order, gridspec_kws = {'hspace' : -0.2})
g.map(sb.kdeplot, 'num_var', shade = True)

# remove the y-axes
g.set(yticks=[])
g.despine(left=True)

g.set_titles('{row_name}')

```

I've added the "gridspec_kws" parameter to the `FacetGrid` call to adjust the arrangement of subplots in the grid through Matplotlib's [`GridSpec`](https://matplotlib.org/api/_as_gen/matplotlib.gridspec.GridSpec.html) class. By setting "hspec" to a negative value, the subplot axes bounds will overlap vertically. The "size" and "aspect" parameters have also been adjusted. While I'm at it, I'll add some code on the `FacetGrid` object to remove the y-axis through the `despine` method and remove the ticks through the `set` method. They're going to start overlapping, and we don't really need them – we're mostly interested in the relative positions of the distributions rather than specific heights.

![img](https://video.udacity-data.com/topher/2018/November/5be0dd78_l4-c20-ridgeline2/l4-c20-ridgeline2.png)

The individual subplots now overlap, but we've still got a problem: the backgrounds of the subplots are opaque, thus obscuring all but the tops of all of the individual group distributions, with the exception of the lowest. In addition, the individual subplot titles overlap the other distributions with some ambiguity: these should be moved elsewhere in the individual plots. The revised code and plot look like this:

```
group_means = df.groupby(['many_cat_var']).mean()
group_order = group_means.sort_values(['num_var'], ascending = False).index

g = sb.FacetGrid(data = df, row = 'many_cat_var', size = 0.5, aspect = 12,
                 row_order = group_order, gridspec_kws = {'hspace' : -0.2})
g.map(sb.kdeplot, 'num_var', shade = True)

g.set(yticks=[])
g.despine(left=True)

# set the transparency of each subplot to full
g.map(lambda **kwargs: plt.gca().patch.set_alpha(0))

# remove subplot titles and write in new labels
def label_text(x, **kwargs):
    plt.text(4, 0.02, x.iloc[0], ha = 'center', va = 'bottom')
g.map(label_text, 'many_cat_var')
g.set_xlabels('num_var')
g.set_titles('')

```

We make clever use of the FacetGrid object's `map` function to perform the plot modifications. Previously, you've seen `map` used where the first argument is a plotting function, the following arguments are positional variable strings, and any additional arguments are keyword arguments for the plotting function. In actuality, you can set any function as the first argument, which will be applied to each facet. To apply the transparency using `map`, I set up an anonymous lambda function that gets the current Axes ([`gca`](https://matplotlib.org/api/_as_gen/matplotlib.pyplot.gca.html)), selects its background ([`patch`](https://matplotlib.org/api/_as_gen/matplotlib.patches.Patch.html)), and sets its transparency to full.

As for the second `map` argument, it sends a pandas Series to the function specified by the first argument. This Series is filtered to include only the column specified by the second `map` argument, with only the rows appropriate for each facet. In this case, I exploit the fact that the 'many_cat_var' column is filled with copies of the categorical feature string to specify the [`text`](https://matplotlib.org/api/_as_gen/matplotlib.pyplot.text.html) string, with hardcoded positional values appropriate to the plot. (`map` also sends a few general keyword arguments like 'color' automatically to the specified function, hence the need for `**kwargs` to capture them despite not specifying any myself.) One downside to this approach is that the x-axis labels get replaced with 'many_cat_var' after the `map` call, thus requiring the addition of a `set_xlabels` function call to reset the string.

The final ridgeline plot looks like this, where we can see the distribution of our numeric variable on each category, sorted by mean:

![img](https://video.udacity-data.com/topher/2018/November/5be0ea2b_l4-c20-ridgeline3/l4-c20-ridgeline3.png)

## Further Reading

- Seaborn: [ridge plot example](https://seaborn.pydata.org/examples/kde_ridgeplot.html) - I actually used this example to clean up my initial attempts. It's got a little bit more aesthetic cleaning than the above demonstration.







# Multivariate Exploration of Data



## Non-Positional Encodings for Third Variables

There are four major cases to consider when we want to plot three variables together:

- three numeric variables
- two numeric variables and one categorical variable
- one numeric variable and two categorical variables
- three categorical variables

If we have at least two numeric variables, as in the first two cases, one common method for depicting the data is by using a scatterplot to encode two of the numeric variables, then using a non-positional encoding on the points to convey the value on the third variable, whether numeric or categorical. (You will see additional techniques later in the lesson that can also be applied to the other two cases, i.e. where we have at least two categorical variables.)

Three main non-positional encodings stand out: shape, size, and color. For Matplotlib and Seaborn, color is the easiest of these three encodings to apply for a third variable. Color can be used to encode both qualitative and quantitative data, with different types of color palettes used for different use cases. Because of how broadly color can be used, a dedicated discussion of color and its use in Matplotlib and Seaborn will be deferred to the next page in the lesson.

## Encoding via Shape

Shape is a good encoding for categorical variables, using one shape for each level of the categorical variable. Unfortunately, there is no built-in way to automatically assign different shapes in a single call of the `scatter` or `regplot` function. Instead, we need to write a loop to call our plotting function multiple times, isolating data points by categorical level and setting a different "marker" argument value for each one.

```
cat_markers = [['A', 'o'],
               ['B', 's']]

for cat, marker in cat_markers:
    df_cat = df[df['cat_var1'] == cat]
    plt.scatter(data = df_cat, x = 'num_var1', y = 'num_var2', marker = marker)
plt.legend(['A','B'])

```

The 'o' string specifies circular markers for members of category 'A', while the 's' string specifies square markers for members of category 'B'. The [`legend`](https://matplotlib.org/api/_as_gen/matplotlib.pyplot.legend.html) function adds a legend to the plot, with one marker for every `scatter` call made. The function argument sets the labels for those points.

(Documentation: [matplotlib built-in markers](https://matplotlib.org/api/markers_api.html), [marker reference example](https://matplotlib.org/examples/lines_bars_and_markers/marker_reference.html))

![img](https://video.udacity-data.com/topher/2018/March/5abaae7b_l5-c02-encodings1/l5-c02-encodings1.png)

From the positional encodings in the plot, you can see that there is a modest positive relationship between the two numeric variables. Adding the categorical variable via shape encoding, we can see that points of category 'A' tend to be smaller than those of category 'B' in terms of the numeric x-variable ("num_var1"). Neither category seems to have an advantage in terms of variability or value for the numeric y-variable ("num_var2").

Note that the two categories have automatically been double-encoded with different colors, in addition to the explicitly specified markers. If we wanted the points to have the same color as well, we could do that through the "c" parameter in `scatter` or "color" in `regplot`. A small example of where this is useful will be seen in the next section.

## Encoding via Size

Point size is a good encoding for numeric variables. Usually, we want the numeric values to be proportional to the area of the point markers; this is the default functionality of the "s" parameter in `scatter`. (You need to refer to "s" through a dictionary assigned to the "scatter_kws" parameter when working with `regplot`.)

```
plt.scatter(data = df, x = 'num_var1', y = 'num_var2', s = 'num_var3')

# dummy series for adding legend
sizes = [20, 35, 50]
base_color = sb.color_palette()[0]
legend_obj = []
for s in sizes:
    legend_obj.append(plt.scatter([], [], s = s, color = base_color))
plt.legend(legend_obj, sizes)

```

While the creation of the plot is easier with size, we need to put in extra leg work to create a legend. Since, as noted above, `legend` will only create one legend entry per plot function call, we need to create additional dummy `scatter` objects with reference sizes to create the plot. The color is fixed so that all of the legend entries have the same color, and two arguments are provided to the `legend` function: the list of plotting objects to depict in the legend, and their labels.

![img](https://video.udacity-data.com/topher/2018/March/5ababf13_l5-c02-encodings2/l5-c02-encodings2.png)

The size encoding for the third numeric variable ("num_var3") shows that its values are largest in the 'middle' of the distribution of values, and smaller on the upper and bottom edges. It is also clear that size is much less precise an encoding than position, so it is better used to make general, qualitative judgments than precise judgments.

In the case of the example, the data was also scaled in a way that the marker sizes made sense as given. You might need to apply a scaling factor (e.g., multiplying or dividing all values by 2) or shift in order to make the size encoding interpretable. In particular, if the values in your third numeric variable include negative values, then you might want to choose a color encoding instead.

## A Warning on Combining Encodings

It might seem plausible to combine both size and shape encodings into the same plot, to depict the trend in four variables at once. Technically, this may be true, but there are some cautions to be taken with this approach. One surface issue is that the code to depict the plot and a reasonable legend gets complicated. A more important issue is that point areas won't all be the same even with the same value, depending on the shape of the marker:

```
plt.figure(figsize = [5,5])

common_size = 2500
plt.scatter([0],[1], marker = 's', s = common_size)
plt.scatter([1],[1], marker = '^', s = common_size)
plt.scatter([0],[0], marker = 'o', s = common_size)
plt.scatter([1],[0], marker = 'X', s = common_size)

# a little bit of aesthetic cleaning
plt.xlim(-0.5,1.5)
plt.xticks([])
plt.ylim(-0.5,1.5)
plt.yticks([])

```

![img](https://video.udacity-data.com/topher/2018/March/5abac650_l5-c02-encodings3/l5-c02-encodings3.png)

Despite having the same "s" values, the triangle, circle, and X markers all look smaller (have a smaller area) than the square. Perhaps this isn't a major concern, considering that size is better used as a qualitative measure for exploration. But it's still something to consider. A little more discussion of the number of variables that can be reasonably packed into a plot can be found later in the lesson ("How much is too much?").

## Further Reading

- Bloomberg: [Tracking Super Bowl Ticket Prices](https://www.bloomberg.com/graphics/infographics/tracking-super-bowl-ticket-prices.html) - This visualization shows an interesting encoding for a third variable: connecting points by a line to show the changes in the two axis values across time. A different marker at each end of the path shows the starting point and the end point.



## Encoding via Color

Color is a very common encoding for variables, for both qualitative and quantitative variables. You've already seen this employed in previous lessons where position could not be used to encode a value: color for category in a clustered bar chart, and color for count in a heat map (both as a 2-d histogram and as a 2-d bar chart). Here, we'll look at how to employ color in scatterplots, as well as discuss more about color palette choices depending on the type of data you have.

If you have a qualitative variable, you can set different colors for different levels of a categorical variable through the "hue" parameter on seaborn's [**FacetGrid**](https://seaborn.pydata.org/generated/seaborn.FacetGrid.html) class.

```
g = sb.FacetGrid(data = df, hue = 'cat_var1', size = 5)
g.map(plt.scatter, 'num_var1', 'num_var2')
g.add_legend()

```

![img](https://video.udacity-data.com/topher/2018/March/5abbc9e1_l5-c03-color1/l5-c03-color1.png)

We get a plot that is similar to what was observed in the previous page: points of category A tend to be smaller than category B on "num_var1" for the x-axis, and there doesn't appear to be any interaction with "num_var2" as depicted on the y-axis.

For quantitative variables, we should not take the same approach, since **FacetGrid** expects any variable input for subsetting to be categorical. Instead, we can set color based on numeric value in the `scatter` function through the "c" parameter, much like how we set up marker sizes through "s". (Unlike with size, we don't have an easy way of setting color by numeric value through `regplot` due to how its "color" argument is set up.)

```
plt.scatter(data = df, x = 'num_var1', y = 'num_var2', c = 'num_var3')
plt.colorbar()

```

![img](https://video.udacity-data.com/topher/2018/March/5abbe123_l5-c03-color2/l5-c03-color2.png)

As we saw before, when points lie further away from the central line through the data, the value on the third variable decreases. Compared to the size encoding, we have a more precise idea of value on the third variable, though certainly not as precise as positional encodings.

## Color Palettes

Depending on the type of data you have, you may want to change the type of color palette that you use to depict your data. There are three major classes of color palette to consider: qualitative, sequential, and diverging.

**Qualitative** palettes are built for nominal-type data. This is the palette class taken by the default palette.

```
sb.palplot(sb.color_palette(n_colors=9))

```

(Documentation: seaborn [`palplot`](https://seaborn.pydata.org/generated/seaborn.palplot.html), [`color_palette`](https://seaborn.pydata.org/generated/seaborn.color_palette.html))

![img](https://video.udacity-data.com/topher/2018/March/5abbe740_l5-c03-color3/l5-c03-color3.png)

In a qualitative palette, consecutive color values are distinct so that there is no inherent ordering of levels implied. Colors in a good qualitative palette should also try and avoid drastic changes in brightness and saturation that would cause a reader to interpret one category as being more important than the others - unless that emphasis is deliberate and purposeful.

For other types of data (ordinal and numeric), a choice may need to be made between a sequential scale and a diverging scale. In a **sequential** palette, consecutive color values should follow each other systematically. Typically, this follows a light-to-dark trend across a single or small range of hues, where light colors indicate low values and dark colors indicate high values. The default sequential color map, "viridis", takes the opposite approach, with dark colors indicating low values, and light values indicating high.

```
sb.palplot(sb.color_palette('viridis', 9))

```

![img](https://video.udacity-data.com/topher/2018/March/5abbf5e5_l5-c03-color4/l5-c03-color4.png)

Most of the time, a sequential palette will depict ordinal or numeric data just fine. However, if there is a meaningful zero or center value for the variable, you may want to consider using a **diverging** palette. In a diverging palette, two sequential palettes with different hues are put back to back, with a common color (usually white or gray) connecting them. One hue indicates values greater than the center point, while the other indicates values smaller than the center.

```
sb.palplot(sb.color_palette('vlag', 9))

```

![img](https://video.udacity-data.com/topher/2018/March/5abbf873_l5-c03-color5/l5-c03-color5.png)

## Selecting Color Palettes

If you want to change the color map for your plot, the easiest way of doing so is by using one of the built-ins from Matplotlib or Seaborn. [This part](https://matplotlib.org/api/pyplot_summary.html#colors-in-matplotlib) of the Matplotlib documentation has a list of strings that can be understood for color mappings. For most of your purposes, stick with the palettes noted in the top few tables as built-in for Matplotlib ('viridis', etc.) or from ColorBrewer; the remaining palettes may not be as perceptually consistent. Seaborn also adds in a number of its own palettes:

- **Qualitative** (all up to 6 colors): 'deep', 'pastel', 'dark', 'muted', 'bright', 'colorblind'
- **Sequential**: 'rocket' (white-orange-red-purple-black), 'mako' (mint-green-blue-purple-black)
- **Diverging**: 'vlag' (blue-white-red), 'icefire' (blue-black-orange)

For all of these strings, appending '_r' reverses the palette, which is useful if a sequential or diverging palette is rendered counter to your expectations.

A color palette can be set in **FacetGrid** through the "palette" parameter, and in `scatter` through the "cmap" parameter.

```
g = sb.FacetGrid(data = df, hue = 'cat_var1', size = 5,
                 palette = 'colorblind')
g.map(plt.scatter, 'num_var1', 'num_var2')
g.add_legend()

```

![img](https://video.udacity-data.com/topher/2018/March/5abbfe0a_l5-c03-color6/l5-c03-color6.png)

```
plt.scatter(data = df, x = 'num_var1', y = 'num_var2', c = 'num_var3',
            cmap = 'mako_r')
plt.colorbar()

```

![img](https://video.udacity-data.com/topher/2018/March/5abbfe28_l5-c03-color7/l5-c03-color7.png)

When using a diverging color palette, you will likely need to specify the "vmin" and "vmax" parameters in order to have the neutral point in the palette meet the center point in the scale. Alternatively, solutions that create a different normalization function like the one posted in [this Stack Overflow thread](https://stackoverflow.com/questions/20144529/shifted-colorbar-matplotlib) can be used for finer control over the color map. Diverging color scales are common enough for the `heatmap` type that there is a "center" parameter for setting the central value. You'll see a demonstration of this later in the lesson ("Plot Matrices").

## Warnings on Color

There are a couple of things to be aware of in general, when working with color. First of all, try and consider color blindness when selecting color for your plots. You don't want your visualization to shut out the 8% of the population that have some kind of color vision deficiency. Fortunately, the built-in color palettes highlighted in the previous section should minimize these concerns. If you use a different, or custom palette, it might be worth checking your visualization's interpretability through a color blindness sim like [this one](http://www.color-blindness.com/coblis-color-blindness-simulator/).

Secondly, you want to be aware of the effect of transparency and overlap on interpretability. If points of different color on a qualitative scale overlap, the result may be a third color that cannot be matched to something in the palette. If multiple points on a quantitative scale overlap, then the result may be a value that does not actually exist in the data. To be safe here, avoid or minimize transparency in plots with color. You may need to plot only a sample of your points in order to make sure that the effect of the third variable is clearly visible.

```
plt.figure(figsize = [5,5])

# left: qualitative points
plt.scatter(0,0.5,s = 1e4, c = sb.color_palette()[0], alpha = 0.5)
plt.scatter(0,-0.5,s = 1e4, c = sb.color_palette()[1], alpha = 0.5)

# right: quantitative points
plt.scatter(1,0.5,s = 1e4, c = sb.color_palette('Blues')[2], alpha = 0.5)
plt.scatter(1,-0.5,s = 1e4, c = sb.color_palette('Blues')[4], alpha = 0.5)

# set axes for point overlap
plt.xlim(-0.5,1.5)
plt.ylim(-3.5,3.5)
plt.xticks([])
plt.yticks([])

```

![img](https://video.udacity-data.com/topher/2018/March/5abc077b_l5-c03-color8/l5-c03-color8.png)

## Further Reading

- Matplotlib tutorial: [Colormaps in Matplotlib](https://matplotlib.org/tutorials/colors/colormaps.html)
- Seaborn tutorial: [Choosing color palettes](https://seaborn.pydata.org/tutorial/color_palettes.html)
- Eager Eyes: [How The Rainbow Color Map Misleads](https://eagereyes.org/basics/rainbow-color-map) - seaborn will refuse to accept the 'jet' palette string, which corresponds with a rainbow-colored palette that covers the entire range of hues. This, and the next link, will tell you why it's been forbidden.
- Agile Scientific: [No more rainbows!](https://agilescientific.com/blog/2017/12/14/no-more-rainbows)
- Datawrapper: [How to Choose a Color Palette for Choropleth Maps](https://blog.datawrapper.de/how-to-choose-a-color-palette-for-choropleth-maps/) - Though this article discusses color in the context of maps and for a specific software tool, it's a useful reference if you want to create a non-linear normalization function.



## Faceting for Multivariate Data

In the previous lesson, you saw how **FacetGrid** could be used to subset your dataset across levels of a categorical variable, and then create one plot for each subset. Where the faceted plots demonstrated were univariate before, you can actually use any plot type, allowing you to facet bivariate plots to create a multivariate visualization.

```
g = sb.FacetGrid(data = df, col = 'cat_var1', size = 4)
g.map(sb.boxplot, 'cat_var2', 'num_var2')

```

![img](https://video.udacity-data.com/topher/2018/March/5abc34a1_l5-c05-faceting1/l5-c05-faceting1.png)

The faceted box plot suggests a slight interaction between the two categorical variables, where, in level B of "cat_var1", the level of "cat_var2" seems to be have a larger effect on the value of "num_var2", compared to the trend within "cat_var1" level A.

**FacetGrid** also allows for faceting a variable not just by columns, but also by rows. We can set one categorical variable on each of the two facet axes for one additional method of depicting multivariate trends.

```
g = sb.FacetGrid(data = df, col = 'cat_var2', row = 'cat_var1', size = 2.5,
                margin_titles = True)
g.map(plt.scatter, 'num_var1', 'num_var2')

```

Setting `margin_titles = True` means that instead of each facet being labeled with the combination of row and column variable, labels are placed separately on the top and right margins of the facet grid. This is a boon, since the default plot titles are usually too long.

![img](https://video.udacity-data.com/topher/2018/March/5abc3ac4_l5-c05-faceting2/l5-c05-faceting2.png)







## Other Adaptations of Bivariate Plots

You also saw one other way of expanding univariate plots into bivariate plots in the previous lesson: substituting count on a bar chart or histogram for the mean, median, or some other statistic of a second variable. This adaptation can also be done for bivariate plots like the heat map, clustered bar chart, and line plot, to allow them to depict multivariate relationships.

If we want to depict the mean of a third variable in a **2-d histogram**, we need to change the weights of points in the `hist2d` function similar to how we changed the weights in the 1-d histogram.

```
xbin_edges = np.arange(0.25, df['num_var1'].max()+0.5, 0.5)
ybin_edges = np.arange(7,    df['num_var2'].max()+0.5, 0.5)

# count number of points in each bin
xbin_idxs = pd.cut(df['num_var1'], xbin_edges, right = False,
                    include_lowest = True, labels = False).astype(int)
ybin_idxs = pd.cut(df['num_var2'], ybin_edges, right = False,
                    include_lowest = True, labels = False).astype(int)

pts_per_bin = df.groupby([xbin_idxs, ybin_idxs]).size()
pts_per_bin = pts_per_bin.reset_index()
pts_per_bin = pts_per_bin.pivot(index = 'num_var1', columns = 'num_var2').values

z_wts = df['num_var3'] / pts_per_bin[xbin_idxs, ybin_idxs]

# plot the data using the calculated weights
plt.hist2d(data = df, x = 'num_var1', y = 'num_var2', weights = z_wts,
           bins = [xbin_edges, ybin_edges], cmap = 'viridis_r', cmin = 0.5);
plt.xlabel('num_var1')
plt.ylabel('num_var2');
plt.colorbar(label = 'mean(num_var3)');

```

![img](https://video.udacity-data.com/topher/2018/March/5abc4dcf_l5-c06-adaptations1/l5-c06-adaptations1.png)

Considering how few data points there are in the example, and how cleanly the third variable is distributed, the adapted heat map is a bit excessive in terms of work. The low level of point overlap observed earlier means that the scatterplot with color or size encoding was sufficient for depicting the data. You'll be more likely to use the heat map if there is a lot of data to be aggregated.

The code for the **2-d bar chart** doesn't actually change much. The actual `heatmap` call is still the same, only the aggregation of values changes. Instead of taking `size` after the `groupby` operation, we compute the `mean` across dataframe columns and isolate the column of interest.

```
cat_means = df.groupby(['cat_var1', 'cat_var2']).mean()['num_var2']
cat_means = cat_means.reset_index(name = 'num_var2_avg')
cat_means = cat_means.pivot(index = 'cat_var2', columns = 'cat_var1',
                            values = 'num_var2_avg')
sb.heatmap(cat_means, annot = True, fmt = '.3f',
           cbar_kws = {'label' : 'mean(num_var2)'})

```

Note how the "cbar_kws" provides an additional argument to the colorbar component of the heat map call.

![img](https://video.udacity-data.com/topher/2018/March/5abc952c_l5-c06-adaptations2/l5-c06-adaptations2.png)

An alternative approach for two categorical variables and one numeric variable is to adapt a **clustered bar chart** using the `barplot` function instead of the `countplot` function:

```
ax = sb.barplot(data = df, x = 'cat_var1', y = 'num_var2', hue = 'cat_var2')
ax.legend(loc = 8, ncol = 3, framealpha = 1, title = 'cat_var2')

```

![img](https://video.udacity-data.com/topher/2018/March/5abc973f_l5-c06-adaptations3/l5-c06-adaptations3.png)

The "hue" parameter can also be used in a similar fashion in the `boxplot`, `violinplot`, and `pointplot` functions to add a categorical third variable to those plots in a clustered fashion. As a special note for `pointplot`, the default rendering aligns all levels of the "hue" categorical variable vertically. Use the "dodge" parameter to shift the levels in a clustered fashion:

```
ax = sb.pointplot(data = df, x = 'cat_var1', y = 'num_var2', hue = 'cat_var2',
                  dodge = 0.3, linestyles = "")

```

![img](https://video.udacity-data.com/topher/2018/March/5abc9a2f_l5-c06-adaptations4/l5-c06-adaptations4.png)

As a final example, a **line plot** can be adapted from previous code showing how to create frequency polygons for levels of a categorical variable. In this case as well, we create a custom function to send to a **FacetGrid** object's `map` function that computes the means in each bin, then plots them as lines via `errorbar`.

```
def mean_poly(x, y, bins = 10, **kwargs):
    """ Custom adapted line plot code. """
    # set bin edges if none or int specified
    if type(bins) == int:
        bins = np.linspace(x.min(), x.max(), bins+1)
    bin_centers = (bin_edges[1:] + bin_edges[:-1]) / 2

    # compute counts
    data_bins = pd.cut(x, bins, right = False,
                       include_lowest = True)
    means = y.groupby(data_bins).mean()

    # create plot
    plt.errorbar(x = bin_centers, y = means, **kwargs)

bin_edges = np.arange(0.25, df['num_var1'].max()+0.5, 0.5)
g = sb.FacetGrid(data = df, hue = 'cat_var2', size = 5)
g.map(mean_poly, "num_var1", "num_var2", bins = bin_edges)
g.set_ylabels('mean(num_var2)')
g.add_legend()

```

![img](https://video.udacity-data.com/topher/2018/March/5abc9efd_l5-c06-adaptations5/l5-c06-adaptations5.png)



## Plot Matrices

To move back to bivariate exploration for a bit, you might come out of your initial univariate investigation of the data wanting to look at the relationship between many pairs of variables. Rather than generate these bivariate plots one by one, a preliminary option you might consider for exploration is the creation of a plot matrix. In a plot matrix, a matrix of plots is generated. Each row and column represents a different variable, and a subplot against those variables is generated in each plot matrix cell. This contrasts with faceting, where rows and columns will subset the data, and the same variables are depicted in each subplot.

Seaborn's [**PairGrid**](https://seaborn.pydata.org/generated/seaborn.PairGrid.html) class facilitates the creation of this kind of plot matrix.

```
g = sb.PairGrid(data = df, vars = ['num_var1', 'num_var2', 'num_var3'])
g.map_diag(plt.hist)
g.map_offdiag(plt.scatter)

```

By default, **PairGrid** only expects to depict numeric variables; a typical invocation of **PairGrid** plots the same variables on the horizontal and vertical axes. On the diagonals, where the row and column variables match, a histogram is plotted. Off the diagonals, a scatterplot between the two variables is created.

![img](https://video.udacity-data.com/topher/2018/March/5abd22bb_l5-c08-plotmatrices1/l5-c08-plotmatrices1.png)

The [`pairplot`](https://seaborn.pydata.org/generated/seaborn.pairplot.html) function can also be used to render this common use case in a single call.

For other relationships, the flexibility of **PairGrid** shines. For example, if we want to look at the relationship between the numeric and categorical variables in the data, we need to set the different variable types on the rows and columns, then use an appropriate plot type for all matrix cells.

```
g = sb.PairGrid(data = df, x_vars = ['num_var1', 'num_var2', 'num_var3'],
                y_vars = ['cat_var1','cat_var2'])
g.map(sb.violinplot, inner = 'quartile')

```

![img](https://video.udacity-data.com/topher/2018/March/5abd25bb_l5-c08-plotmatrices2/l5-c08-plotmatrices2.png)

When you choose to create a plot matrix, be aware that the time it takes to render the plot depends on the number of data points you have and the number of variables you want to plot. Increasing the number of variables increases the number of plots that need to be rendered in a quadratic fashion. In addition, increasing the number of variables means that the individual subplot size needs to be reduced in order to fit the matrix width on your screen. That means that, if you have a lot of data, it might be difficult to see the relationships between variables due to overplotting, and it will take a long time to complete. One recommended approach is to take a random subset of the data to plot in the plot matrix instead. Use the plot matrix to identify interesting variable pairs, and then follow it up with individual plots on the full data.

## Correlation Matrices

For numeric variables, it can be useful to create a correlation matrix as part of your exploration. While it's true that the [`.corr`](https://pandas.pydata.org/pandas-docs/stable/generated/pandas.DataFrame.corr.html) function is perfectly fine for computing and returning a matrix of correlation coefficients, it's not too much trouble to plot the matrix as a heat map to make it easier to see the strength of the relationships.

```
sb.heatmap(df.corr(), annot = True, fmt = '.2f', cmap = 'vlag_r', center = 0)

```

Instead of using the default sequential color map, a diverging color map is specified and its center is set to 0. That way, we can use hue to tell if a correlation is positive or negative, and see its strength from the hue's intensity.

![img](https://video.udacity-data.com/topher/2018/March/5abd2d01_l5-c08-plotmatrices3/l5-c08-plotmatrices3.png)

Don't forget that correlations are computed based on strength of linear relationship. Compare the correlation between "num_var2" and "num_var3" to the corresponding cell in the first plot matrix as an example of how a correlation statistic might be misleading.



## Feature Engineering

This is not so much an additional technique for adding variables to your plot, but a reminder that feature engineering is a tool that you can leverage as you explore and learn about your data. As you explore a dataset, you might find that two variables are related in some way. Feature engineering is all about creating a new variable with a sum, difference, product, or ratio between those original variables that may lend a better insight into the research questions you seek to answer.

For example, if you have one variable that gives a count of crime incidents, and a second one that gives population totals, then you may want to engineer a new variable by dividing the former by the latter, obtaining an incident rate. This would account for a possible relationship between the original features where if there are more people, there might naturally be more chances for crimes to occur. If we looked at the raw counts rather than the incident rate, we risk just seeing information about population sizes rather than what we might really want.

Another way that you can perform feature engineering is to use the `cut` function to divide a numeric variable into ordered bins. When we split a numeric variable into ordinal bins, it opens it up to more visual encodings. For example, we might facet plots by bins of a numeric variable, or use discrete color bins rather than a continuous color scale. This kind of discretization step might help in storytelling by clearing up noise, allowing the reader to concentrate on major trends in the data. Of course, the bins might also mislead if they're spaced improperly – check out [this PolicyViz post](https://policyviz.com/2017/11/02/choosing-map-bins/) if you'd like to see a deeper discussion in the context of map-based visualizations.



## How Much is Too Much?

By now, you've seen a lot of ways of expanding the number of variables that can be depicted in a single visualization. The basic positional axes can handle two variables: one on the horizontal and one on the vertical. You can facet by both columns and rows to add up to two variables. Encodings in shape, size, and color could add as many as three more. However, you should try and resist the temptation to overuse your newfound power, and to instead practice some restraint in the number of variables that you include in any one plot.

When you have only two variables plotted, A and B, you have only one relationship to understand. Add in a third variable C, and you have three pairwise relationships: A vs. B, A vs. C, and B vs. C. You also need to consider one interaction effect between all three variables: Does the value of C affect the relationship between A and B? With a fourth variable, you have six possible pairwise relationships and four different three-variable interaction effects. This exponential explosion of possible relationships with the number of variables means that there is a potential for cognitive overload if the data isn't conveyed clearly.

This is why it is so important to approach data exploration systematically, rather than just throw as many variables together as possible immediately. When you move from univariate visualizations to bivariate visualizations, you augment your previous understanding of individual distributions by seeing how they relate to one another. If you look at pairwise visualizations before putting together a trivariate plot, then you will have a clear view to how the interaction, if present, changes your previous understanding of the marginal pairwise relationship.

When you move on to explanatory data visualizations, try to limit the number of variables that are introduced at the same time and make sure that the encoding choices convey the main findings to your reader in the clearest way possible. While it's good to keep a soft limit of about three or four variables in a single visualization, you can exceed this if the trends are clear or you introduce features to your reader in a systematic way.







# Explanotary Visualizations

## Revisiting the Data Analysis Process

As a reminder, let's briefly review the data analysis process and revisit the way that exploratory and explanatory visualizations fit into different parts of that process. The five steps of the data analysis process are:

1. **Extract** - Obtain the data from a spreadsheet, SQL, the web, etc.
2. **Clean** - Here we could use expl**or**atory visuals.
3. **Explore** - Here we use expl**or**atory visuals.
4. **Analyze** - Here we might use either expl**or**atory or expl**an**atory visuals.
5. **Share** - Here is where expl**an**atory visuals live.

The previous three lessons in the course have been focused on **exploratory analyses**. In phases with exploratory visualizations, the primary audience for the visuals will be you, the analyst. The plots that have been created and demonstrated haven't been particularly polished, just descriptive enough for you to gain insights into the data.

This lesson is focused on taking those insights and creating **explanatory analyses**. Here, your audience will be broader: your goal will be to convey your findings to other people who don't have the level of hands-on experience with the data as you. Visualizations under this banner should be focused on telling a specific story that you want to convey to that particular audience. Many times, these visualizations evolve from visuals created during the exploratory process, just polished up to highlight the specific intended insights. These highlights might change depending on the audience you're presenting to. You'll revisit those design concepts from earlier in the course to make your plots informative not just for yourself, but also compelling and understandable for others.



## Polishing Plots

Thus far in the course, the code you've seen has been fairly bare-bones, just enough to get your plots created. In order to convey your findings to others quickly and efficiently, you'll need to put work into polishing your plots. There are many dimensions to consider when putting together a polished plot.

##### Choose an appropriate plot

Your choice of plot will depend on the number of variables that you have and their types: nominal, ordinal, discrete numeric, or continuous. Choice of plot also depends on the specific relationship that you want to convey. For example, whether you choose a violin plot, box plot, or adapted bar chart depends on how much data you have and whether distributions are significant or important. You'll be more likely to use a violin plot if you have a lot of data and the distributions are meaningful, and more inclined to use a box plot or bar chart if you have less data, or the distributions are less reliable.

##### Choose appropriate encodings

Your variables should impact not just the type of plot that is chosen, but also the variable encodings. For example, if you have three numeric variables, you shouldn't just assign x-position, y-position, and color encodings randomly. In many cases, the two variables that are most important should take the positional encodings; if one represents an outcome or dependent variable, then it should be plotted on the y-axis. In other cases, it makes sense to plot the dependent measure with color, as though you are taking a top-down view of the plane defined by the two independent measures plotted on the axes.

##### Pay attention to design integrity

When setting up your plotting parameters, remember the design principles from earlier in the course.

Make sure that you minimize chart junk and maximize the data-ink ratio, as far as it maintains good interpretability of the data. When deciding whether or not to add non-positional encodings, make sure that they are meaningful. For example, using color in a frequency bar chart may not be necessary on its own, but will be useful if those colors are used again later in the same presentation, matched with their original groups. By the same token, avoid using the same color scheme for different variables to minimize the chance of reader confusion.

You should also ensure that your plot avoids lie factors as much as possible. If you have a bar chart or histogram, it is best to anchor them to a 0 baseline. If you're employing a scale transformation, signal this clearly in the title, axis labels, and tick marks.

##### Label axes and choose appropriate tick marks

For your positional axes, make sure you include axis labels. This is less important in exploration when you have the code available and have an extended flow to your work, but when you're conveying only the key pieces to others, it's crucial. When you add an axis label, make sure you also provide the units of measurement, if applicable (e.g., stating "Height (cm)" rather than just "Height").

As for tick marks, you should include at least three tick marks on each axis. This is especially important for data that has been transformed: you want enough tick marks so that the scale of the data can be communicated there. If your values are very large or very small numbers, consider using abbreviations to relabel the ticks (e.g., use "250K" instead of "250000").

##### Provide legends for non-positional variables

Make sure that you add a legend for variables not depicted on the axes of your plot. For color encoding, you can add a color bar to the side of the plot. The most important new thing here is that you provide a descriptive label to your legend or color bar, just as you would the axes of your plot.

##### Title your plot and include descriptive comments

Finally, make sure that you provide a descriptive title to your plot. If this is a key plot that presents important findings to others, aim to create a title that draws attention to those main points, rather than just state what variables are plotted.

Also, realize that while a visualization might be the core mechanism by which you convey findings, it need not stand alone. Comments in the text below or surrounding the plot can provide valuable context to help the reader understand your message, or reinforce the main points that they should have gotten.

## Using Matplotlib to Polish Plots

Back in the univariate plots lesson, you were introduced to the general way that visualizations are structured in matplotlib and seaborn: each visualization is based off a single Figure, which contains one or more Axes, and each Axes houses elements like points, lines, and boxes that depict the plotted data. Understanding and making use of this structure will open up your ability to polish your visualizations. Each function below is linked to its documentation page and which object type it is associated with.

- [`figure`](https://matplotlib.org/api/_as_gen/matplotlib.pyplot.figure.html) (Figure): Used to create a new figure. You'll use this first to initialize the figure, most often using the "figsize" parameter to set the figure dimensions.
- [`xlabel`](https://matplotlib.org/api/_as_gen/matplotlib.pyplot.xlabel.html) and [`ylabel`](https://matplotlib.org/api/_as_gen/matplotlib.pyplot.ylabel.html) (Axes): Used for setting axis labels.
- [`xticks`](https://matplotlib.org/api/_as_gen/matplotlib.pyplot.xticks.html) and [`yticks`](https://matplotlib.org/api/_as_gen/matplotlib.pyplot.yticks.html) (Axes): Used for setting tick marks.


- [`legend`](https://matplotlib.org/api/_as_gen/matplotlib.pyplot.legend.html) (Axes): Used to create and customize a legend. One key parameter to use is "title", which allows you to label what feature is being depicted in the legend. You might also need to make use of the "loc" and "ncol" parameters to move and shape the legend if it gets placed in an awkward location by default.
- [`colorbar`](https://matplotlib.org/api/_as_gen/matplotlib.pyplot.colorbar.html) (Axes): Used to add a colorbar to a plot. Use the "label" parameter to set the label on a colorbar.


- [`title`](https://matplotlib.org/api/_as_gen/matplotlib.pyplot.title.html) (Axes): Used for setting axis titles.
- [`suptitle`](https://matplotlib.org/api/_as_gen/matplotlib.pyplot.suptitle.html) (Figure): Used for setting figure titles. The main difference between `suptitle` and `title` is that the former sets a title for the Figure as a whole, and the latter for only a single Axes. This is an important distinction: if you're using faceting or subplotting, you'll want to use `suptitle` to set a title for the figure as a whole.

All of the functions above, or parameters associated with those functions in the case of seaborn, have been used sporadically throughout the course. Below are a couple examples of these polishing functions in use.

This example makes use of the fuel economy dataset. Since a colorbar is being added to the plot, `figsize` is used to make the figure a little bit wider than normal. Title, axes, and colorbar are all labeled. Note how the units of each feature being plotted is given in parentheses in each label.

```
# loading in the data, sampling to reduce points plotted
fuel_econ = pd.read_csv('./data/fuel_econ.csv')

np.random.seed(2018)
sample = np.random.choice(fuel_econ.shape[0], 200, replace = False)
fuel_econ_subset = fuel_econ.loc[sample]

# plotting the data
plt.figure(figsize = [7,4])
plt.scatter(data = fuel_econ_subset, x = 'displ', y = 'comb', c = 'co2',
            cmap = 'viridis_r')
plt.title('Fuel Efficiency and CO2 Output by Engine Size')
plt.xlabel('Displacement (l)')
plt.ylabel('Combined Fuel Eff. (mpg)')
plt.colorbar(label = 'CO2 (g/mi)');

```

![img](https://video.udacity-data.com/topher/2018/September/5b9801a9_l6-c06-polishing1/l6-c06-polishing1.png)



