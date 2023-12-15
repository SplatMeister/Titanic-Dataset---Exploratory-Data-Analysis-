Exploratory Data Analysis – Titanic Dataset
https://www.kaggle.com/competitions/titanic
Section 1
The Titanic data set consist of attributes on passenger details and mainly if each passengers survived or not during the Titanic’s maiden voyage. The remaining attributes contain information of each passenger details from name, gender, family count, fare amount, cabin type and embarked location.  
1.1 Python libraries used for exploratory data analysis 
In order to carry out the expoloratary analysis several python libraries are imported (Appendix 1.1.1). 
1.	Pandas – To import the data set and to manipulate and to carry out further analysis.
2.	Numpy – To carry out mathamatical operations on the data set. 
3.	Plotly – To visualize and for findings. 
1.2 Importing the data set to Python 
As the first step, after importing the above-mentioned libraries and importing the Titanic dataset to the Python environment using Pandas. 
To understand all the attributes and its unique values, created a lambda function to generate all attributes and the respective unique values (Appendix 1.2.1).
1.3 Identifying null values in the Titanic data set
In order to identify if there are any null values in the data frame, applied the ‘isnull()’ method (Appendix 1.3.1). There after 866 total null values were visible.  
Attribute	Null Values
Age	177
Cabin	687
Embarked	2
Table 1 Total null values
The 866 null values require to be replaced with correct values to carry out data exploration. Therefore, under the ‘Age’ column the 177 null values require to be replaced with the average age by passenger class. To visualize this, a box plot is generated based on the three passenger classes (Appendix 1.3.2). 
 
Figure 1 Bar plot with average age vs passenger class
As per the (Figure 1) in passenger class 1 the average age is 37, class 2 the average age is 29 and passenger class 3 average age is 24. Therefore, replacing the respective average age according to ‘pclass’ column by using a function (Appendix 1.3.3). 
As the second stage of replacing the null values in the column ‘Cabin’, it is evident that there is a large count of unique values and replacing with most frequent values will not provide an accurate analysis. Therefore, replacing all null values in ‘Cabin’ column as ‘Unknown’ (Appendix 1.3.4).
For the final stage of data preperation, the ‘Embarked’ column consists 2 null values. In order to replace the values. Calculating the ‘mode’ of the values in the ‘Embarked’ column and replacing the two null values with the most frequently occering vlaue which is ‘S’ (Southampton)(Appendix 1.3.5).
Finally, checking again if all null values are replaced accordingly before the data analysis and generating insights. 
1.4 Data exploration and analyzing Titanic data set
Since the Titanic data set is predominantly highlights the types of individuals who survived. To understand the gender of all passengers and if they survived or not using a histogram (Appendix 1.4.1). 
 
Figure 2 Histogram Survival count by gender
Based on (Figure 2) it is visible that most of the individuals that did not survive are males which is 468 in number. This is due to a general norm, where during an emergency priority is given to females over males. Therefore, the females who did not survive is at 81. 
However, it is important to identify the number of females who did not survive on the titanic and the reason for it. To identify, the reason and what attributes are contributing for females who didn’t survive. Creating a new data frame with only females that didn’t survive and visualizing it on a bar plot with their respective age and the fare amount (Appendix 1.4.2). 
1.	Creating a new data frame with only females who did not survive the titanic to determine the passenger class they were assigned to.
2.	Then identify, which passenger class is responsible for the most female deaths. 
  
Figure 3 Histogram Survival count by gender
Histogram in (Figure 3) represents all females who did not survive and to identify which passenger class they belong to. It is evident that most females who are 24 years in age that resided in passenger class 3 did not survive.  To further visualize where these cabins were placed on the titanic, the following Titanic ship design portrays where each cabin type is placed on the Titanic.
 
Figure 4 Titanic design of all classes
The above (Figure 4) depicts the two third class cabins and how each cabin is placed. Both cabins are at the far end of the ship, and it was the most inaccessible locations for passengers. During an emergency female passenger must travel the furthest to reach the top of the decks ship. Therefore, due to the accident many female passengers did not survive. 
1.5 Data exploration and analyzing age distribution
Based on the Titanic data set there were passengers from 4 month old new born to 80 year old passengers. To identify which age bracket survived in the Titanic, a histogram is used to visually represent. To analyze the age groups implemented the following steps (Appendix 1.5.1).
1.	Created a new column in the data frame ‘Age Group’ in order to identify the age group.
2.	Divided the age values into 8 groups ranging from 0 to 10 and ending 80 using the age bracket as the criteria and creating labels accordingly. 
3.	Included the gender for age group in the visualization to generate inights.  
 
Figure 5 Total Survived Count by Age group and Sex
The histogram in (Figure 5) visualize the age groups of survived victims based on the gender. Age group between 20 - 30 year old passengers had highest survival count. Out of which most were female passengers. 
Furthermore, the age group 0 – 10 year old children had an equal number of male female children who survived. It is evident that equal priority is given to children in spite what their gender maybe. 
To determine the status of survival of all passengers based on their fare, passenger class, gender, embarked location, and the respective family relation count. Visualizing all these attributes in one chart with subplots for overall data exploration and insight generation (Appendix 1.5.2).
 
Figure 6 Total Survival Count by attributes
On the above subplots based on each attribute the following data explorations are performed.


The Fare Amount
The social class of the passengers if the wealthy managed to survive over the non-wealthy passengers. 
To validate the social class of the passengers, identifying the average amount paid, or the total value paid by passengers on passenger class (Appendix 1.5.3).
Based on average fare by age group it is visible that proportionately many have paid a higher fare for passenger class 1. 

After further analysis based on (Figure 6), its visible that most of the passengers did not pay for the voyage. However, most of the passengers may have received invitations for the Titanic voyage, since it was the first maiden voyage and special guests were invited.
Passenger Class
If the passenger class on the Titanic played a role in the survivor count. Passenger class 3 had the highest number of individuals who did not survive. However, the lowest number of passengers are in the 2nd passenger class. It is visible that the location of the cabins played an important role in determining the chances of surviving. 
Furthermore, the age distribution of passengers can give insights about what age group individuals were present in the cabins (Appendix 1.5.4).

 
Figure 8 Violin plot of Passenger Classes against Age
Each passenger class in the above violin plot visualize the distribution of age groups by the count of survivors. Passenger class 3 had the youngest average age of 24 with the highest density and passenger class 1 had the highest average age of 38. Therefore, we can see that passenger class 1 consisted more older passengers and passenger class 3 had the highest number of young adults. 
Gender of passengers
To identify the survival rate by gender, implemented the ‘groupby()’ method and index ‘Sex’ and values as ‘Survived’ and calculated the mean value. Thereafter, to generate insights visualized the survival rate by the mean value.
Based on the below pie chart females had a survival rate of 79% on (Figure 9) (Appendix 1.5.5). This is predominantly due to the priority that is given to females over males followed by children on the Titanic.

 
Figure 9 Survival Rate by Gender
Additional family members
In relation to the passengers who survived, did the number of additional family members make an impact on the survival count? However, many travelers were single and traveling alone, and the second tier of family members for these individuals were siblings or spouses. It is evident that, in addition to solo travelers, some passengers had brought along siblings or spouses on the voyage.
Passengers embarked location
The passengers who embarked from Southampton had the highest passenger count on the Titanic. Furthermore, the highest number of passengers who did not survive are also from Southampton. However, most of the passengers embarked from this specific location.



1.6 Findings and insights through data exploration
The Titanic data set result in many hidden insights that are complicated than popular believes for the past decades. The maiden voyage of the Titanic was a spectacular event, where many of the wealthy took part in the voyage. However, based on the above data exploration, it was evident that over 400 of the guests were invites who did not pay for the voyage.  
The hypothesis that, based on the passenger class if the passengers have a better chance in surviving is proven. Therefore, passengers who were in the first class, had the highest possibility of surviving and upon further investigation. The Titanic plan depicts that the cabin 1 was placed in the center for easy access to the deck. Furthermore, from the females that did not survive a large propionate were young adults aged 24. 
Although the Titanic is one of the most tragic events in history. There are new learnings that can be adopted for better safety measures for other passenger liners that are designed today. The design of passenger liners may have not evolved since 1912, however, the outlook and the placement of cabins are relatively the same. Therefore, based on the above data exploration, it is important to identify the potential risk factors associated with cabin placement, such as the location of cabin 3 on the Titanic. Consequently, it is essential to prioritize and incorporate emergency exits in current passenger liner designs to facilitate easy access to the deck in the event of an emergency, which may ultimately aid in increasing survival rates.
