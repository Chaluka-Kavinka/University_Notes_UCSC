Numerical representation involves using **descriptive statistics** to simplify raw data into an understandable form by highlighting its most important features. While graphs give us a picture, numerical measures give us the exact "GPS coordinates" and "size" of our data.

# 1. Measures of Location (The "Where")

These measures help identify the central or typical value of a dataset.

- **Mean (Arithmetic Average):** The sum of all values divided by the number of values.
	_Fancy Example:_ If five friends have $10,$10,$10,$10, and $110, the **Mean** is $30. It is very sensitive to that one rich friend (the outlier).

- **Median:** The exact middle value when data is ordered.
	_Fancy Example:_ In the same group of friends, the **Median** is $10. It ignored the rich friend and told you what a "typical" person in the group actually has.

- **Mode:** The value that appears most frequently. It is the only measure you can use for non-numerical data like "favorite color".

- **Quartiles & Percentiles:** These divide your data into chunks (Quartiles into 4 parts, Percentiles into 100). Your **Median** is simply the 50th Percentile (P50​) or the 2nd Quartile (Q2​).

---
# 2. Measures of Dispersion (The "Spread")

Dispersion tells you how "scattered" your data points are around the center.

- **Range:** The difference between the largest and smallest values. It’s simple but easily ruined by a single extreme outlier.

- **Interquartile Range (IQR):** The range of the **middle 50%** of your data $(Q3​−Q1​)$. It is "resistant," meaning outliers can't touch it.

- **Standard Deviation** $(s)$: The most common measure of spread, showing the average distance of every point from the mean.

- **Coefficient of Variation (CV):** This is the **Standard Deviation divided by the Mean**.
	_Fancy Example:_ If you want to compare the weight variability of **Elephants** (tons) vs. **Mice** (grams), you use CV because it cancels out the units, allowing a fair comparison.

---
# 3. The Five-Number Summary & Box Plots

A **Box-and-Whiskers Plot** is a graphical version of the **Five-Number Summary**: Minimum, $Q1$​, Median, $Q3​$, and Maximum.

- **Symmetric:** The median is in the center of the box.

- **Positively Skewed:** The median is to the left, and the right "whisker" is very long.

- **Outliers:** Any point more than $1.5 \times IQR$ away from the box is a possible outlier.

---

# 4. Measures of Relationship

When studying two variables at once, we look for how they "co-vary."

- **Correlation** $(r)$: Measures the strength of a linear relationship on a scale from **-1 to +1**.
	- **+1:** Perfect positive (they go up together).
	- **-1:** Perfect negative (one goes up, the other goes down).
	- **0:** No linear relationship.

- **Coefficient of Determination** $(r^2)$: The square of the correlation. it tells you what **percentage** of the change in one variable is explained by the other.

---
# Short Note for Remember Things Better

|Measure Type|Specific Tool|Best Used For...|
|---|---|---|
|**Center**|**Mean**|General average (No outliers)|
|**Center**|**Median**|"Fair" middle (Has outliers)|
|**Spread**|**IQR**|Middle 50% spread|
|**Spread**|**Std. Dev**|Standard distance from mean|
|**Relative Spread**|**CV**|Comparing different units/groups|
|**Relationship**|**Correlation (**r**)**|Strength of the "link"|

# Analogy for Understanding:

Imagine you are a **scout looking for a new basketball player.** The **Mean** score tells you their career average. The **Standard Deviation** tells you if they are consistent (low SD) or a "wild card" who scores 40 points one day and 0 the next (high SD). The **CV** would help you compare a player in the NBA to a player in a local league to see who is more "dominant" relative to their own peers.

---
# Lecture Notes

![[IS 1212 Handout 3 - Numerical Representation.pdf]]