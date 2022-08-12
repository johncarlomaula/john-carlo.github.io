# Is Friday the 13th Associated with More Injuries?

**Project Description:** In this project, I explore the National Electronic Injury Surveillance System (NEISS) dataset to see if there are more injuries associated with Friday the 13th compared to other days.

<img src="images/project6_images/intro.jpeg?_raw=true"/>

The association of Friday the 13th with bad luck is a popular superstition that inspired many movies and video games. **Paraskevidekatriaphobia** is the fear of Friday the 13th. While this might be considered an irrational fear, I think it would be interesting to see if people do experience more bad luck on Friday the 13th.

One way I can achieve that is by determining if more injuries occur on that day compared to others. The National Electronic Injury Surveillance System dataset is a collection of product-related injuries in the United States collected by the U.S. Consumer Product Safety Commission (CPSC). Using data from the last 5 years, I performed an analysis to see if more injuries occur on Friday the 13th, which could be attributed to bad luck. 

### NEISS Dataset Overview

I provided a summary of the dataset below. For more information about the dataset and the code used to generate the plots below, you can check out my [Github page](https://github.com/johncarlomaula/neiss-injury-project) for this project.

- The dataset contains 1,757,100 rows and 25 variables.
- Variables include treatment date, demographics (e.g. sex, age, etc.), body part injured, diagnosis, and so on.
- 8,406 of the injuries occured on Friday the 13th, which occurred 9 times during 2017 - 2021.

For the purpose of this project, treatment date will be used as a proxy for the date that the injury occurred. 

### Do more injuries occur on Friday the 13th?

I plotted the number of injuries treated each day. Due to a large amount of data and variability in the data, I decided to calculate a rolling average with a window of 7 days to smooth out the plot.
<img src="images/project6_images/injuries_rolling.png?_raw=true"/>

Based on this plot, there does not appear to be a difference between the number of injuries on Friday the 13th compared to other days. The number of injuries appear to be more associated with the time of year. Injuries occur more frequently during the summer (May, July, and September) and the least during the winter (December to February). 

There is also a sharp decrease in the number of injuries beginning in March 2020, when lockdown for the COVID-19 pandemic began. 

### Are people of a certain age more likely to get injured on Friday the 13th?

I decided to see if the distribution of age is different between the two groups (Friday the 13th vs. other days).

<img src="images/project6_images/age_plot.png?_raw=true"/>

Based on the violin plot above, there does not appear to be a significant difference in the distribution of age between the two groups. The distribution of age for both groups is strongly right-skewed with a median of 25.0 years.

### Are people of a certain sex more likely to get injured on Friday the 13th?

Next, I decided to investigate if people of a certain sex are more likely to get injured on Friday the 13th.

<img src="images/project6_images/sex_plot.png?_raw=true"/>

While men tend to get more injured the women, there does not appear to be a significant difference in the relative frequencies of injuries for both groups. As of now, the data for people who identify as non-binary is very low. 

### Are people more likely to get injured by certain products on Friday the 13th?

I wanted to see if the category of product associated with the injury is different on Friday the 13th compared to other days. The majority of cases in the dataset only have one category of products involved, so I decided to focus on that product (i.e., primary product). Also, since there are hundreds of categories of products, I decided to focus on the top 10 most common ones.

<img src="images/project6_images/products_plot.png?_raw=true"/>

The top 10 category of products are the same for both groups with a slightly different order. The relative frequencies appear to be the same for both groups except for basketball and football-related injuries, which have a higher relative frequency on Friday the 13th. However, this is most likely due to football and basketball games occurring more frequenctly on Fridays than bad luck.

### Are people more likely to injure a specific body part on Friday the 13th?

Next, I wanted to see if a specific body part is injured more often on Friday the 13th compared to other days. I only included the top 10 most injured body parts in the plot below for readability.

<img src="images/project6_images/body_parts_plot.png?_raw=true"/>

The top 10 most injured body parts are the same for both groups (with a slightly different order) with head and face being the most injured body part. The relative frequencies are also the same for both groups in all categories. Thus, there does not appear to be a significant difference in the injured body parts between the two groups.

### Are people more likely to get a specific diagnosis for injuries on Friday the 13th?

I did the same thing for the injury diagnosis. Again, I only included the ten most common diagnoses for readability.

<img src="images/project6_images/diagnosis_plot.png?_raw=true"/>

Just like product category and body parts, the top 10 diagnoses are the same for both groups with a slightly different order. The most common diagnosis is under the "other" category, which contain *pain*, *injury*, or *not specified* as the most common values.

The relative frequencies are about the same in all categories for both groups. However, 0.59% more fractures occur on Friday the 13th compared to the other days, but this may be due to fractures being a common injury to obtain during sporting events, which occur frequently on Fridays.

### Are people more likely to get injured in a specific location on Friday the 13th?

Finally, I looked at the location to see if people are more likely to get injured in a specific location on Friday the 13th.

<img src="images/project6_images/location_plot.png?_raw=true"/>

The ordering of the relative frequencies for each location are the same for both groups with the majority of injuries occurring at home. The values are also the same for both groups except for school, where 1.5 times more injuries occur on Friday the 13th. However, this may be due to sporting events, which are often held in school, taking place frequently on Fridays, and the weekends being part of the other group, which can lower the relative frequency of school-related injuries.

### Conclusion

Overall, there does not appear to be a significant difference in the number of injuries that occur on Friday the 13th compared to other days. We also explored other variables such as age, sex, product, etc. and found no association with Friday the 13th, with the exception of sports-related injuries that is most likely due to sporting events frequently taking place on Fridays. Thus, at least in terms of injury, there is nothing to worry about on Friday the 13th!

Treatment date was used as a proxy for the date that the injury occured. Since these days could be different, this dataset might not be the best representation of injuries occurring on Friday the 13th. A better dataset might be retrieved from emergency department cases where the injury most likely occurred on the same day.
