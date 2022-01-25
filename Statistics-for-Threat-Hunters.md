# Descriptive Statistics and Data Visualizing <sup>(for Threat Hunters)</sup>
- **Statistics** is the study of the analysis, presentation, collection, interpretation, organization, and large data presentation.
- **Descriptive Statistics** is a way to summarize data with numbers and graphs.

## Basic Terms
![Pupulation vs Sample](/img/statistics-terms-population-vs-sample.png)
- **Data** is a set of observations (a set of possible outcomes); most data can be put into two groups: *qualitative* (an attribute whose value is indicated by a label) or *quantitative* (an attribute whose value is indicated by a number). Quantitative data can be separated into two subgroups: *discrete* and *continuous*.
  - **Qualitative data** are the result of categorizing or describing attributes of a population. Qualitative data are also often called categorical data, e.g., hair color, blood type, ethnic group, etc.
  - **Quantitative data** are always numbers. Quantitative data are the result of counting or measuring attributes of a population.
- A **population** is the entire group of individuals you want to study.
- A **sample** is a subset of the *population*. We use *sample data* to make generalizations about an unknown *population*. In other words, the *sample data* help us to make an estimate of a *population* parameter.
  - A **sample** should have the same characteristics as the population it is representing.
  - To draw valid conclusions from your results, you have to carefully decide how you will select a **sample** that is representative of the group as a whole (population).
  - **Probability Sampling** means that every member of the population has a chance of being selected. It is mainly used in quantitative research. There are four main types of probability sample:
    - **Random Sampling** is a method of selecting a sample that gives every member of the population an equal chance of being selected.
    - In **Systematic Sampling** (similar to *random sampling*), every member of the population is listed with a number, but instead of randomly generating numbers, individuals are chosen at regular intervals.
    - **Stratified Sampling** involves dividing the population into subpopulations that may differ in important ways. The population will be devided into subgroups (called strata) based on the relevant characteristic (e.g. gender, age range, income bracket, job role). Based on the overall proportions of the population, you calculate how many people should be sampled from each subgroup.
    - **Cluster Sampling** involves dividing the population into subgroups, but each subgroup should have similar characteristics to the whole sample. Instead of sampling individuals from each subgroup, you randomly select entire subgroups.
    ![4 Main Types of Probability Sample](/img/statistics-terms-sampling-type.png)
- **Data cleansing** involves spotting and resolving potential data inconsistencies or errors to improve your data quality.
  - **An error** is any value (e.g., recorded weight) that doesn’t reflect the true value (e.g., actual weight) of whatever is being measured.
  - With inaccurate or invalid data, you might make a *Type I or II error* in your conclusion.
  - The **clean data** is *valid* (same format, e.g. textual or numerical data), *accurate*, *complete* (no missing data), *consistent* (no outliners), *unique* (no duplication), and *uniform*.
- The way a set of data is measured is called its **level of measurement**. **Levels of measurement** tell you how precisely variables are recorded.
  - The level at which you measure a variable determines how you can analyze your data. Depending on the **level of measurement**, you can perform different descriptive statistics to get an overall summary of your data and inferential statistics to see if your results support or refute your hypothesis.
  - There are 4 **levels of measurement**, which can be ranked from low to high:
    - **Nominal**: the data can only be *categorized*, e.g., Zip code, City of birth, Gender, Ethnicity, Car brands, Marital status.
    - **Ordinal**: the data can be *categorized* and *ranked*, e.g., Top 5 Olympic medallists, Language ability (e.g., beginner, intermediate, fluent).
    - **Interval**: the data can be *categorized* and *ranked*, and *evenly spaced*, e.g., Test scores, Personality inventories, Temperature in Fahrenheit or Celsius.
    - **Ratio**: the data can be *categorized*, *ranked*, *evenly spaced* and has a *natural zero*, e.g., Height, Age, Weight, Temperature in Kelvin.
- A **frequency** is the number of times a value of the data occurs.
  - **Cumulative relative frequency** is the accumulation of the previous relative frequencies. To find the cumulative relative frequencies, add all the previous relative frequencies to the relative frequency.
- The **distribution of data** is the shape of the graph when all possible values are plotted on a frequency graph.
- **Variability** tells you how far apart points lie from each other and from the center of a distribution or a data set.
  - Variability is most commonly measured with the following descriptive statistics:
    - **Range**: the difference between the highest and lowest values.
    - **Interquartile range**: the range of the middle half of a distribution.
    - **Standard** deviation: average distance from the mean.
    - **Variance**: average of squared distances from the mean.
- A result of an experiment is called an **outcome**.
- The **continuous outcomes** is *measured*, while the **discrete outcomes** are *counted*.

## Calculative Terms
Your concentration should be on what the following terms tell us about the data. Let a calculator or computer do the arithmetic.

### Percentiles
- A **percentile** indicates the relative standing of a data value when data are sorted into numerical order from smallest to largest.
- **Percentages** of data values are less than or equal to the *p<sup>th</sup>* *percentile*, e.g., $15\%$ of data values are less than or equal to the *15<sup>th</sup>* percentile.

### Quartile
- **Quartiles** are special percentiles. The first quartile, $Q_1$, is the same as the *25<sup>th</sup>* percentile, and the third quartile, $Q_3$, is the same as the *75<sup>th</sup>* percentile. The *median*, is called both the second quartile and the *50<sup>th</sup>* percentile.

### Mean ($\mu$ or $\overline{x}$)
- **Mean (avereage)** is the *average* of a data set; the sum of all values divided by the total number of values.

### Median
- **Median** is a number that measures the *center (middle)* of the data; the middle number in an ordered data set.

### Mode
- **Mode** is the most common number in a data set; the most frequent value.

### Skewness and the Mean, Median, and Mode
![Skweness of the Data](/img/statistics-terms-skewness.png)
- If the *distribution of data* is skewed to the left, the *mean* is less than the *median*, which is often less than the *mode*. If the *distribution of data* is skewed to the right, the *mode* is often less than the *median*, which is less than the *mean*. In a perfectly *symmetrical distribution*, the *mean* and the *median* are the same.

### Range
- The **range** tells you the spread of your data from the lowest to the highest value in the distribution.
#### Calculation
To find the range, simply subtract the lowest value from the highest value in the data set.
$$
\begin{aligned}
  R_x = Max(X) - Min (X)
\end{aligned}
$$

### Interquartile range
- The **interquartile range** gives you the spread of the middle of your distribution.
#### Calculation
For any distribution that’s ordered from low to high, the interquartile range contains half of the values. While the first quartile (Q1) contains the first 25% of values, the fourth quartile (Q4) contains the last 25% of values.
$$
\begin{aligned}
  IQR_x = Q_3 - Q_1
\end{aligned}
$$

### Standard Deviation (SD)
- The **standard deviation** is the average amount of variability in your dataset. In other words, the **standard deviation** is a number that measures how far data values are from their *mean*.
- The **standard deviation** determines whether a particular data value is close to or far from the *mean* which is always *positive* or *zero*.
- The **standard deviation** is *small* when the data are all concentrated close to the mean, exhibiting little variation or spread. The **standard deviation** is *larger* when the data values are more spread out from the mean, exhibiting more variation.
- **Chebyshev's Rule**
  - At least $75\%$ of the data is within $2$ *standard deviations* of the *mean*.
  - At least $89\%$ of the data is within $3$ *standard deviations* of the *mean*.
  - At least $95\%$ of the data is within $4.5$ *standard deviations* of the *mean*.
- **Empirical Rule**
  - This rule only applies when the shape of the *distribution of the data* is **bell-shaped** and **symmetric**.
  - $68\%$ of the data is within $1$ *standard deviation* of the *mean*.
  - $95\%$ of the data is within $2$ *standard deviations* of the *mean*.
  - $99.7\%$ of the data is within $3$ *standard deviations* of the *mean*.
  ![The Empirical Rule](/img/statistics-terms-standard-deviation.png)
#### Calculation
$$
\begin{aligned}
  \sigma=\sqrt{\displaystyle \frac {\sum_{i=1}^n{(x_i–\overline{x})^2}}{(n-1)}}
\end{aligned}
$$
- If $x$ is a number from the data set, then the difference $x–\overline{x}$ is called its **deviation** where $\overline{x}$ is the *mean* of the data set.
- To calculate the **standard deviation**, we use the following formula where $x–\overline{x}$ is the *deviation*, and $n$ is the size of the data set (sample).

### Variance
- **Variance** shows the degree of spread in data set. In other words, **variance** measures how far a data set is spread out.
- The more spread the data, the larger the **variance** is in relation to the *mean*.
#### Calculation
$$
\begin{aligned}
  \sigma^2=\displaystyle \frac {\sum_{i=1}^n{(x_i–\overline{x})^2}}{(n-1)}
\end{aligned}
$$

### Correlation Coefficient
![Correlation Coefficient](/img/statistics-terms-correlation-coefficient.png)
- A **correlation coefficient** is a number between $-1$ and $1$ that tells you the strength and direction of a relationship between variables.
- The sign of the **coefficient** reflects whether the variables change in the same or opposite directions:
  - A **positive** value means the variables change together in the *same direction*.
  - A **negative** value means they change together in *opposite directions*.

### Standard Error
- The **standard error** of the *mean* is a description of how far (on average) that the *sample mean* will be from the *population mean* in the sample size of $n$. In other words, the **standard error** indicates how different the *population mean* is likely to be from a *sample mean*. 
- The **standard error** shows how much the *sample mean* would vary if you were to repeat a study using new samples from within a single population.
- The **standard deviation** measures the amount of variability from the individual data values to the *mean*, while the **standard error** of the *mean* measures how far the *sample mean* of the data is likely to be from the true *population mean*.
- The bigger sample size, the less **standard error**.
#### Calculation
$$
\begin{aligned}
  \sigma_{\overline{x}}=\displaystyle \frac {s}{\sqrt{n}}
\end{aligned}
$$

### Confidence Interval
- When you make an estimate in statistics there is always uncertainty around that estimate because the number is based on a *sample* of the *population*. Therefore we need some kind of confidence in expanding the out come of the sample data to the population.
- The **confidence interval** is the range of values that you expect your estimate to fall between a certain percentage of the time if you run your experiment again or re-sample the population in the same way.
#### Calculation
$$
\begin{aligned}
  CI=\overline{x} \pm t . \sigma_{\overline{x}}
\end{aligned}
$$
- $t$ comes out of the **[T-Distribution Table](https://home.ubalt.edu/ntsbarsh/business-stat/StatistialTables.pdf)**.

### Probability ($P(A)$)
- **Probability** is a mathematical tool used to study randomness. It deals with the chance (the likelihood) of an event occurring.
- **Probabilities** are between zero and one.
- The **conditional probability** of $A$ given $B$ is written $P(A|B)$. $P(A|B)$ is the *probability* that event $A$ will occur given that the event $B$ has already occurred.
#### Probability Distribution
- A **probability distribution** describes all the possible *outcomes* and *probabilities (likelihoods)* that a random variable can take within a given range. E.g., the **probability distribution** of a fair 6-sided die is $\displaystyle \frac {1}{6}$.
#### Calculation
$$
\begin{aligned}
  P(A)=\displaystyle \frac {the\ number\ of\ outcomes\ for\ event\ A}{the\ total\ number\ of\ outcomes\ in\ the\ sample\ space}
\end{aligned}
$$
- To calculate the *probability* of an event A when all *outcomes* in the sample space are equally likely, count the number of outcomes for event $A$ and divide by the total number of *outcomes* in the sample space.

### Expected Value $E(X)$
- The **expected value** is an anticipated value for an *outcome* at some point in the future.
#### Calculation
$$
\begin{aligned}
  E(X)=\sum_{x \in X}{xP(x)}
\end{aligned}
$$
##### Example
The roulette game consists of a small ball and a wheel with $38$ numbered pockets around the edge. So, the probablity of winning is $\displaystyle \frac {1}{38}$. If we bet $1 and we win, the payoff is $35; otherwise the player loses the bet. The expected profit from such a bet will be losing some money.

$E(gain\ from\ \$1\ bet)=\$35 \times \displaystyle \frac {1}{38} - \$1 \times \displaystyle \frac {37}{38} = -\$\displaystyle \frac {1}{19}$

### Normal Distribution
![Normal Distribution](/img/statistics-terms-normal-discribution.png)
- The **normal distribution** is the **bell-shaped** *probablity distribution*.
- The **normal distribution** is extremely important, but it cannot be applied to everything in the real world.
- Since it is a continuous distribution, the total area under the curve is $1$.

### Central Limit Theorem
- If we collect samples of size $n$ that are **large enough**, calculate the sum of each sample and create a *histogram*, then the resulting *histogram* will tend to have a normal *bell-shape*.
- The **central limit theorem** for sample *means* says that if you repeatedly draw samples of a given size (such as repeatedly rolling ten dice) and calculate their *means*, those *means* tend to follow a *normal distribution*.
- The **central limit theorem** can be used to illustrate the *law of large numbers*. The law of large numbers states that the *larger* the sample size you take from a population, the closer the sample mean $\overline{x}$ gets to $\mu$ where $\overline{x}$ is the *mean* of the sample and $\mu$ is the *mean* of the population.

## Hypothesis Testing
Hypothesis testing uses data from a sample to draw conclusions about a population parameter or a population probability distribution. In other words, a hypothesis test involves collecting data from a sample and evaluating the data. Then, the statistician makes a decision as to whether or not there is sufficient evidence, based upon analyses of the data, to reject the null hypothesis.
![Hypothesis Testing](/img/statistics-terms-hypothesis.png)
### Hypothesis Testing with One Sample (One-Tailed Test)
- **$H_0$ (Null Hypothesis)** refers to a hypothesis that states that there is no relationship between variables (population parameters).
- **$H_1$ (Alternative Hypothesis; also $H_a$)** is a claim about the population that is contradictory to $H_0$ and what we conclude when we reject $H_0$. The alternate hypothesis is the claim for which we are seeking statistical proof.
- The favored claim ($H_0$) will not be rejected in favor of the alternative claim ($H_1$ or $H_a$) unless the sample evidence provides significant support for the alternative assertion. The four possible outcomes are as follows. Bear in mind that we talk about **to reject**, not **to prove**; we either can **reject** $H_0$ or **faild to reject** $H_0$.
  - The decision is **not to reject** $H_0$ when $H_0$ is **true** (correct decision).
  - The decision is to **reject** $H_0$ when $H_0$ is **true** (incorrect decision known as a *Type I error (False Positive)*).
  - The decision is **not to reject** $H_0$ when, $H_0$ is **false** (incorrect decision known as a *Type II error (False Positive)*).
  - The decision is to **reject** $H_0$ when $H_0$ is **false** (correct decision whose probability is called the *Power of the Test*).
![Hypothesis Testing Table](/img/statistics-terms-hypothesis-table.png)
#### Calculation
$$
\begin{aligned}
  z=\displaystyle \frac {\overline{x} - \mu}{\sigma - \sqrt{n}}
\end{aligned}
$$
Where $\overline{x}$ is the *mean* of the **sample** and $\mu$ is the *mean* of the **population**.
- According to the formula, we will have the following rejection and acceptance areas.

  |Alternative Hypothesis ($H_1$)|Rejection Area for Level $\alpha$ Test|
  |:---:|:---|
  | $\overline{x} > \mu'$  | $z \ge z_{\alpha}$ (Uper-tailed Test) |
  | $\overline{x} < \mu'$  | $z \le -z_{\alpha}$ (Uper-tailed Test) |
  | $\overline{x} \ne \mu'$  | either $z \ge z_{\frac {\alpha}{2}}$ or $z \le -z_{\frac {\alpha}{2}}$ (Two-tailed Test) |
  
  ![Hypothesis Testing Table](/img/statistics-terms-alpha-level.png)
#### Null vs Alternative Hypotheses Possibilities
- The equality sign is always with the null hypothesis.

|$H_0$|$H_1$|
|:---:|:---:|
| $\theta = \theta'$ | $\theta \ne \theta'$ or (either $\theta > \theta'$ or $\theta < \theta'$) |
| $\theta \le \theta'$ | $\theta > \theta'$ |
| $\theta \ge \theta'$ | $\theta < \theta'$ |

#### Examples
- **$H_0$**: No more than $30\%$ of the citizens have voted in the primary election ($p ≤ 30$).
- **$H_1$**: More than $30\%$ of the citizens have voted in the primary election ($p > 30$).
- **Type I Error**: Frank thinks that his rock climbing equipment may not be safe when, in fact, it really is safe.
- **Type II Error**: Frank thinks that his rock climbing equipment may be safe when, in fact, it is not safe.

## Visualization of Data: Chart Types
![Chart Types](/img/chart-types.png)
- There are many ways to visualize data. Which one to choose will depend on the nature of the data and the goal of the visualization.
- When the data are quantitative (i.e. numbers), then they should be put on a number line. This is because the ordering and the distance between the numbers convey important information.

### Pie Chart
![Pie Chart](/img/chart-types-pie.svg)
- Pie charts can be effective in showing the contributions of data segments as a percentage of a whole.
- A **Donut Chart** is a Pie Chart with an area of the centre cut out.

### Bar Chart or Column Chart
![Bar Chart](/img/chart-types-bar.svg)
- In a **bar chart**, values are indicated by the length of bars, each of which corresponds with a measured group.
- A **Bar Chart** uses either horizontal or vertical bars (column chart) to show discrete, numerical comparisons across categories.
- **Bar charts** are effective when you have data that can be split into multiple categories.
- **Bar charts** are used to compare data across categories, highlight differences, show trends and outliers, and reveal historical highs and lows at a glance.
- **Bars Charts** are distinguished from *Histograms*, as they do not display continuous developments over an interval.
- The following charts show the difference between the same data plotted in *Bar Chart* and *Pie Chart* fashions.
![Bar Chart vs Pie Chart](/img/chart-types-pie-vs-bar-01.png)
### Other Types of Bar Chart
- **Stacked Bar Chart** is a *bar chart* with two or more data series stacked one on top of the other that shows how each value contributes to the total.
![Stacked Bar Chart](/img/chart-types-bar-stacked.png)
- A **Grouped Bar Chart** (aka clustered bar chart, multi-series bar chart) extends the bar chart, plotting numeric values for levels of two categorical variables instead of one.
![Grouped Bar Chart](/img/chart-types-bar-grouped.png)
- A **Pareto Chart** consists of bars that are sorted into order by category size (largest to smallest).

### Histogram Chart
![Histogram](/img/chart-types-histogram.png)
- A **Histogram** visualises the distribution of data over a continuous interval or certain time period.
- Each bar in a **Histogram** represents the tabulated frequency at each interval/bin.
- **Histograms** help give an estimate as to where values are concentrated, what the extremes are and whether there are any gaps or unusual values.
### Other Types of Bar Chart
![Histogram](/img/chart-types-histogram-different-width.png)
- The **Histogram Chart** allows to use blocks with different *widths*.
- The **Histogram** gives two kinds of information about the data:
  - *Density* (crowding): The height of the bar tells how many subjects there are for one unit on the horizontal scale.
  - *Percentages* (relative frequences): Those are given by `area = height x width`.

### Box Plot Chart or Box-and-Whisker Plot Chart
![Box Plot](/img/chart-types-box-plot.svg)
- A **Box Plot** is a convenient way of visually displaying the data distribution through their quartiles.
- **Box Plot Charts** are useful for visualizing the distribution of data based on the following *five* groupings: lower quartile, upper quartile, minimum, maximum, and median.
![Box Plot Anatomy](/img/chart-types-box-plot-anatomy.png)
- The *interquartile range (IQR)* tells you the range of the middle half of your dataset; data between $Q_1$ to $Q_3$.
- **Box and Whisker Plot Charts** is similar to a *histogram* but is usually better for showing several simultaneous comparisons such as data grouped by month, etc.

#### Advantages of using a **Box Plot**
- What the key values are, such as: the mean ($Q_2$), median, $25^{th}$ percentile ($Q_1$), etc.
- If there are any outliers and what their values are.
- Is the data symmetrical?
- How tightly is the data grouped?
- If the data is skewed and if so, in what direction?

### Violin Plot
![Violin Plot](/img/chart-types-violin.svg)
- A **Violin Plot** is is a combination of a *Box Plot* and a *Density Plot* and used to visualise the distribution of the data and its probability density.

![Violin Plot](/img/chart-types-violin-anatomy.svg)

### Line Chart
![Line Chart](/img/chart-types-line.svg)
- **Line Charts** are used to display quantitative values over a continuous interval or time period.
- A **Line Chart** is most frequently used to show trends and analyse how the data has changed over time.
- The line's journey across the **Line Chart** can create patterns that reveal trends in a dataset.
- When **grouped** with other lines (other data series), individual lines can be compared to one another.

### Sparkline
![Sparkline Chart](/img/chart-types-sparkline.svg)
- A Sparkline is similar to **line chart** excpet plotting multiple lines on a single set of axes.
- A **Sparkline** consists of one or more line charts in a vertical stack.
- The following charts show the difference between the same data plotted in *Line Chart* and *Sparkline* fashions.
![Line Chrat vs. Sparkline](/img/chart-types-line-vs-sparkline-01.png)
![Line Chrat vs. Sparkline](/img/chart-types-line-vs-sparkline-02.png)

### Area Chart
![Area Chart](/img/chart-types-area.svg)
- An **Area chart** can add depth to your *line chart*, especially multidimensional data.
- **Area Charts** are used to display the development of quantitative values over an interval or time period.
- **Stacked Area Graphs** work in the same way as simple *Area Graphs* do, except for the use of multiple data series that start each point from the point left by the previous data series.
![Stacked Area Chart](/img/chart-types-area-stacked.png)

### Stream Graph
![Stream Graph](/img/chart-types-stream.svg)
- **Stream Graph** is a variation of a Stacked Area Graph, but instead of plotting values against a fixed, straight axis, a **Stream Graph** has values displaced around a varying central baseline.
- **Stream Graphs** are ideal for displaying high-volume datasets, in order to discover trends and patterns over time across a wide range of categories.
- **Stream Graphs** display the changes in data over time of different categories through the use of flowing, organic shapes that somewhat resemble a river-like stream.
- In a **Stream Graph**, the size of each individual stream shape is proportional to the values in each category.
- Colour can be used to either distinguish each category

### Scatter Plot Chart
![Scatter Plot](/img/chart-types-scatter-plot.svg)
- **Scatter Plots** are employed to find the relationship between two variables, often quantities.
- **Scatter Plots** are ideal when you have paired numerical data and you want to see if one variable impacts the other.
- Various types of correlation can be interpreted through the patterns displayed on Scatterplots.
  - These are: positive (values increase together), negative (one value decreases as the other increases), null (no correlation), linear, exponential and U-shaped.
  - Points that end up far outside the general cluster of points are known as outliers.
  - The **Line of Best Fit** or a **Trend Line** can be used to make estimates via interpolation.

![Scatter Plot Anatomy](/img/chart-types-scatter-plot-anatomy.png)

### Bubble Plot Chart
![Bubble Chart](/img/chart-types-bubble.png)
- **Bubble Plots** are similar to *Scatter Plot* charts but support three (or four) values instead of two: `X value`, `Y value`, `Size`, and `Category`.
- **Bubble Charts** are typically used to compare and show the relationships between categories, by the use of positioning and proportions.

### Radar Chart
![Radar Chart](/img/chart-types-radar.png)
- **Radar Charts** are useful for seeing which variables have similar values or if there are any outliers amongst each variable.

### Sunburst Diagram
![Sunburst Diagram](/img/chart-types-sunburst.png)
- A **Sunburst Diagram** shows hierarchy through a series of rings, that are sliced for each category node.
- Rings are sliced up and divided based on their hierarchical relationship to the parent slice.

### Bullet Graph
![Bullet Graph](/img/chart-types-bullet.svg)
- **Bullet Graphs** are ideal for displaying single values within some quantitative context, such as a goal value.
- **Bullet Graphs** functions like a Bar Chart, but are accompanied by extra visual elements to pack in more context.

![Bullet Graph Anatomy](/img/chart-types-bullet-anatomy.svg)

### Funnel Chart
![Funnel Chart](/img/chart-types-funnel.svg)
- **Funnel charts** are often used to visualize optimizations, specifically to see which stages most affect drop-off.
- **Funnel Charts** are most often seen in business or sales contexts, where we need to track how a starting set of visitors or users drop out of a process or flow. 

### Heatmap
![Heatmap Chart](/img/chart-types-heatmap.svg)
- A **Heatmap** shows magnitude of a phenomenon as color in two dimensions.
- The variation in color may be by hue or intensity, giving obvious visual cues to the reader about how the phenomenon is clustered or varies over space.
- **Heatmaps** are useful for cross-examining multivariate data, through placing variables in the rows and columns and colouring the cells within the table.
- **Heatmaps** can also be used to show the changes in data over time if one of the rows or columns are set to time intervals.

### Chord Diagram
![Chord Diagram](/img/chart-types-chord.svg)
- **Chord Diagram** visualizes the inter-relationships between entities. The connections between entities are used to display that they share something in common.
- **Chord Diagrams** is ideal for comparing the similarities within a dataset or between different groups of data.

![Chord Diagram Anatomy](/img/chart-types-chord-anatomy.svg)
#### Other Types of Chord Diagram
![Non-ribbon Chord Diagram](/img/chart-types-non-ribbon-chord.svg)
- A **Non-ribbon Chord Diagram** is a stripped-down version of a *Chord Diagram*, with only the nodes and connection lines showing.

### Snakey Diagram
![Snakey Diagram](/img/chart-types-sankey.png)
- **Sankey Diagrams** display flows and their quantities in proportion to one another.
- The width of the arrows or lines are used to show their magnitudes, so the bigger the arrow, the larger the quantity of flow.
- Colour can be used to divide the **Sankey Diagram** into different categories or to show the transition from one state of the process to another.

### Parallel Coordinates Plot
![Parallel Coordinates Plot](/img/chart-types-parallel-coordinates.svg)
- **Parallel Coordinates Plots** are ideal for comparing many variables together and seeing the relationships between them.
- Each axis can have a different scale, as each variable works off a different unit of measurement, or all the axes can be normalised to keep all the scales uniform.

### Treemap Diagram
![Treemap Diagram](/img/chart-types-treemap.png)
- **Treemaps** are an alternative way of visualising the hierarchical structure of a *Tree Diagram* while also displaying quantities for each category via area size.
- When a quantity is assigned to a category, its area size is displayed in proportion to that quantity and to the other quantities within the same parent category in a part-to-whole relationship.
- Also, the area size of the parent category is the total of its subcategories.

### Network Diagram
![Network Diagram](/img/chart-types-network-diagram.svg)
- A **Network Diagram** shows how things are interconnected through the use of nodes.
- *Nodes* (edges) in **Network Diagram** can be in different shapes, size, and colors to indicate size and multiple categorization.
- *Vertices* (links) in **Network Diagram** can also be in different size to show the bond. They can also show the direction of the relationship.
- By mapping out connected systems, **Network Diagrams** can be used to interpret the structure of a network through looking for any clustering of the nodes.

### Nightingale Rose Chart
![Nightingale Rose Chart](/img/chart-types-nightingale-rose.svg)
- **Nightingale Rose Charts** are drawn on a polar coordinate grid.
- Each category or interval in a **Nightingale Rose Chart** is divided into equal segments on this radial chart.
- How far each segment extends from the centre of the polar axis depends on the value it represents as it is shown in the anatomy.

![Nightingale Rose Chart](/img/chart-types-nightingale-rose-anatomy.svg)
- The major flaw with **Nightingale Rose Charts** is that the outer segments are given more emphasis because of their larger area size.

## Visualization of Data: Combined Charts
Dual-axis charts overlay two different charts with a shared horizontal axis, but potentially different vertical axis scales (one for each component chart). This can be useful to show a direct comparison between the two sets of vertical values, while also including the context of the horizontal-axis variable.

### Bar-Line Combo Chart
![Bar Line Chart](/img/chart-types-bar-line.svg)
- **Bar-Line Combo Charts** use a bar and a line to visualize a result set with both a continuous and a categorical metric.
- **Bar Line Charts** can compare values against a goal line, or a group of values against an average.

### Scatter-Line Combo Chart



### Error Bar

## How to chose the best chart?
![Choose the Best Chart Type - by Google](/img/choose-the-best-chart-01.png)
![Choose the Best Chart Type - by Active Reports JS](/img/choose-the-best-chart-02.png)
![Choose the Best Chart Type - by MicroSoft](/img/choose-the-best-chart-03.png)
---
Recrouse:
- [Google Charts - How to choose the best chart or graph for your data](https://cloud.google.com/blog/products/data-analytics/different-types-graphs-charts-uses)
- [ActiveReoirtsJS - Chart Types](https://www.grapecity.com/activereportsjs/docs/v1/DeveloperGuide/ActiveReportsJSDesigner/Report-Controls/Chart/Chart-Types)
- [Tableau - Which Type of Chart or Graph is Right for You?](https://www.tableau.com/learn/whitepapers/which-chart-or-graph-is-right-for-you)
- [Chartio - Chart Types](https://chartio.com/docs/charts/chart-types/#bar)
- [Chartio - Guides to Charts](https://chartio.com/learn/charts)
- [The Data Visualization Catalouge](https://datavizcatalogue.com/index.html)
- [The Basic Terminologies of Statistics You Should Know](https://statanalytica.com/blog/terminologies-of-statistics/)
- [Introductory Statistics](https://openstax.org/details/books/introductory-statistics)
- [The Beginner's Guide to Statistical Analysis](https://www.scribbr.com/category/statistics/)
- [Hypothesis Tests](https://www.colorado.edu/amath/sites/default/files/attached-files/lesson9_hyptests.pdf)