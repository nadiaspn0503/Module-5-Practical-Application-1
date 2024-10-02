# Module-5-Practical-Application-1
This repo contains the files for the PCMLAI Module 5 Practical Assignment 1

## Context
Imagine driving through town and a coupon is delivered to your cell phone for a restaurant near where you are driving. Would you accept that coupon and take a short detour to the restaurant? Would you accept the coupon but use it on a subsequent trip? Would you ignore the coupon entirely? What if the coupon was for a bar instead of a restaurant? What about a coffee house? Would you accept a bar coupon with a minor passenger in the car? What about if it was just you and your partner in the car? Would weather impact the rate of acceptance? What about the time of day?

Obviously, proximity to the business is a factor on whether the coupon is delivered to the driver or not, but what are the factors that determine whether a driver accepts the coupon once it is delivered to them? How would you determine whether a driver is likely to accept a coupon?

## Overview
The goal of this project is to use what you know about visualizations and probability distributions to distinguish between customers who accepted a driving coupon versus those that did not.

## Data
This data comes to us from the UCI Machine Learning repository and was collected via a survey on Amazon Mechanical Turk. The survey describes different driving scenarios including the destination, current time, weather, passenger, etc., and then ask the person whether he will accept the coupon if he is the driver. Answers that the user will drive there ‘right away’ or ‘later before the coupon expires’ are labeled as ‘Y = 1’ and answers ‘no, I do not want the coupon’ are labeled as ‘Y = 0’.  There are five different types of coupons -- less expensive restaurants (under \$20), coffee houses, carry out & take away, bar, and more expensive restaurants (\$20 - $50).

## Deliverables
Your final product should be a brief report that highlights the differences between customers who did and did not accept the coupons.  To explore the data you will utilize your knowledge of plotting, statistical summaries, and visualization using Python. You will publish your findings in a public facing github repository as your first portfolio piece.


## Data Description
Keep in mind that these values mentioned below are average values.

The attributes of this data set include:
1. User attributes
    -  Gender: male, female
    -  Age: below 21, 21 to 25, 26 to 30, etc.
    -  Marital Status: single, married partner, unmarried partner, or widowed
    -  Number of children: 0, 1, or more than 1
    -  Education: high school, bachelors degree, associates degree, or graduate degree
    -  Occupation: architecture & engineering, business & financial, etc.
    -  Annual income: less than \\$12500, \\$12500 - \\$24999, \\$25000 - \\$37499, etc.
    -  Number of times that he/she goes to a bar: 0, less than 1, 1 to 3, 4 to 8 or greater than 8
    -  Number of times that he/she buys takeaway food: 0, less than 1, 1 to 3, 4 to 8 or greater
    than 8
    -  Number of times that he/she goes to a coffee house: 0, less than 1, 1 to 3, 4 to 8 or
    greater than 8
    -  Number of times that he/she eats at a restaurant with average expense less than \\$20 per
    person: 0, less than 1, 1 to 3, 4 to 8 or greater than 8
    -  Number of times that he/she goes to a bar: 0, less than 1, 1 to 3, 4 to 8 or greater than 8
    
2. Contextual attributes
    - Driving destination: home, work, or no urgent destination
    - Location of user, coupon and destination: we provide a map to show the geographical
    location of the user, destination, and the venue, and we mark the distance between each
    two places with time of driving. The user can see whether the venue is in the same
    direction as the destination.
    - Weather: sunny, rainy, or snowy
    - Temperature: 30F, 55F, or 80F
    - Time: 10AM, 2PM, or 6PM
    - Passenger: alone, partner, kid(s), or friend(s)

3. Coupon attributes
    - time before it expires: 2 hours or one day
  
## Inital Analysis
Overall the proportion of the total observations that chose to accept the coupon is about 56.84%. With over half of the coupons being accepted, the specifc demographics contributing to driver acceptance or rejection is observed. This is first done by visualizing the coupon column to establish an idea as to what type of coupons promote acceptance and rejection.

![Barplot visualizing the driver coupon acceptance and rejection based on coupon type.](https://github.com/user-attachments/assets/ecd39d35-898a-4423-b8ee-7c1b89f9c0f4)

The hightes acceptance seems to be both the restaurant(<20) and coffee house coupons have the hghest acceptance. It should be noted that the highest rejection is also for the coffeehouse coupons. In relation to each other, the restaurant(<20) coupons seem to have better acceptance as the rejection level is lower. Restaurant(<20) annd Carry out & Take away coupons are the only coupons with a higher acceptance proportion than rejection.

Next the overall data can be visualized using a histogram of the acceptance and rejection of coupons based on temperature. The temperature fall into three categories: 30°F, 55°F, and 80°F.

![Histogram visualizing the driver coupon acceptance and rejection based on temperatire.](https://github.com/user-attachments/assets/2352fbf6-3799-4a20-95bd-f3d4b99d0b14)

Although rejection based on temperature seems to be higher than acceptance. Warmer temperatures tend to lead to higher acceptance. This goes hand in hand with the fact that sunny weather usually results in an acceptance compared to rainy and snowy weather.

![Histogram visualizing the driver coupon acceptance and rejection based on weather.](https://github.com/user-attachments/assets/d7cbef17-608d-45d2-a19a-0ad9e7c47ece)

## Bar Coupon Analysis
The demographics that affect the acceptance and rejection of bar coupons can be idetified once a DataFrame of just the bar coupons is created. From this DataFrame it is identified that the proportion of the total bar coupons that are accepted is about 41.00%. With under half of the coupons being accepted, the specifc demographics contributing to driver acceptance or rejection of bar coupons is observed. This is done through 4 different observations.

1. Comparing the bar coupon acceptance rate of drivers who went to the bar 3 times or fewer a month to those who went more.

![Barplot visualizing the driver acceptance and rejection of bar coupons based on the number of times the bar was visted a month.](https://github.com/user-attachments/assets/5d84fc63-a804-4d4e-b2a0-55c634d92971)

The acceptance of the bar coupons for people who vist the bar 3 times or less a month (never, less than 1, and 1-3 times a month) is about 37.07%. The acceptance of the bar coupons for people who vist the bar more than 3 times a month (4-8 and greater than 8 times a month) is about 76.88%. It should be noted that these proportions are specific to their own category. The acceptance rate for those visiting the bar 3 times or less a month does not include those who visted the bar more than 3 times a month. This is shown in the barplot. Despite te proportion of acceptance for drivers visting the bar more than 3 times a month being higher, the barplot shows that when comparing all 5 criteria togther, the acceptance for drivers who go to the bar less than once a month or 1-3 times a month have the highest acceptance overall. 

2. Comparing the bar coupon acceptance rate of drivers who went to the bar more than once a month and are over the age of 25 to all others.

![Barplot visualizing the driver acceptance and rejection of bar coupons based those who went to the bar more than once a month and are over the age of 25 to all others.](https://github.com/user-attachments/assets/ab263947-148b-4bc3-b826-88754a924401)

The acceptance of the bar coupons for drivers who visit the bar more than once a month (1-3, 4-8, and greater than 8 times a month) and are over the age of 25 (26, 31, 36, 41, 46, and 50plus years old) is about 69.52%. The acceptance of the bar coupons for all other drivers is about 33.50%.

3. Comparing the bar coupon acceptance rate of drivers who went to the bar more than once a month, with non kid passengers, and do not have a farming, fishing, or forestry occupation.

![Barplot visualizing the driver acceptance and rejection of bar coupons based those who went to the bar more than once a month, with non kid passengers, and do not have a farming, fishing, or forestry occupation.](https://github.com/user-attachments/assets/e5505e2d-1306-4584-a126-851541d2f3df)

The acceptance of the bar coupons for drivers who visit the bar more than once a month (1-3, 4-8, and greater than 8 times a month) with non kid passengers (Alone, Friend(s), and Partner), and do not have a farming, fishing, or forestry occupation is about 71.32%. The acceptance of the bar coupons for all other drivers is about 29.60%.

4. Comparing the bar coupon acceptance rate of drivers who go to a cheap restaurant more than 4 times a month, with an income below $50K.

![Barplot visualizing the driver acceptance and rejection of bar coupons based those who go to a cheap restaurant more than 4 times a month, with an income below $50K](https://github.com/user-attachments/assets/a8e9e8a6-51fb-466b-b0cd-bce414fd5f4c)

The acceptance of the bar coupons for drivers who go to a cheap restaurant more than 4 times a month (4-8, and greater than 8 times a month) with an income below $50K (Less than $12500','$12500 - $24999','$25000 - $37499','$37500 - $49999) is about 45.35%. The acceptance of the bar coupons for all other drivers is about 40.11%.

## Carry out & Take Away Coupon Analysis
The demographics that affect the acceptance and rejection of Carry out & Take Away coupons can be idetified once a DataFrame of just the Carry out & Take Away coupons is created. From this DataFrame it is identified that the proportion of the total Carry out & Take Away coupons that are accepted is about 73.55%. With a significant amount of the coupons being accepted, the specifc demographics contributing to driver acceptance or rejection of Carry out & Take Away coupons is observed. This is done through 4 different observations.

1. Comparing the Carry out & Take Away coupon acceptance rate of drivers who went get take out 3 times or fewer a month to those who went more.

![Barplot visualizing the driver acceptance and rejection of Carry out & Take Away coupons based on the number of times take out was gotten a month.](https://github.com/user-attachments/assets/e88010ee-5a18-4eab-a9a6-0ffdd69d9df3)


The acceptance of the Carry out & Take Away coupons for people who get take out 3 times or less a month (never, less than 1, and 1-3 times a month) is about 72.31%. The acceptance of the Carry out & Take Away coupons for people who get take out more than 3 times a month (4-8 and greater than 8 times a month) is about 74.96%. It should be noted that these proportions are specific to their own category. The acceptance rate for those who get take out 3 times or less a month does not include those who get take out more than 3 times a month. This is shown in the barplot. Despite te proportion of acceptance for drivers who get take out more than 3 times a month being higher, the barplot shows that when comparing all 5 criteria togther, the acceptance for drivers who get take out 1-3 and 4-8 times a month have the highest acceptance overall. 

2. Comparing the Carry out & Take Away coupon acceptance rate of drivers who got Carry out & Take Away more than once a month with an income below $50K to all others.

![Barplot visualizing the driver acceptance and rejection of Carry out & Take Away coupons based on those who get take out more than once a month, with an income below $50](https://github.com/user-attachments/assets/f8a5cc5c-da10-4635-8b4c-0b3bd27b7b41)

The acceptance of the Carry out & Take Away coupons for drivers who get take out more than once a month (1-3, 4-8, and greater than 8 times a month) with an income below $50K (Less than $12500','$12500 - $24999','$25000 - $37499','$37500 - $49999) is about 75.09%. The acceptance of the Carry out & Take Away coupons for all other drivers is about 72.31%.

3. Comparing the Carry out & Take Away coupon acceptance rate of drivers who go to a cheap restaurant more than once a month and are under the age of 26 to all others.

![Barplot visualizing the driver acceptance and rejection of Carry out & Take Away coupons based those who go to a cheap restaurant more than once a month and are under the age of 26 to all others.](https://github.com/user-attachments/assets/40aae734-aa94-455a-a6b1-3e48e988cc4c)

The acceptance of the Carry out & Take Away coupons for drivers who go to a cheap restaurant more than once a month (1-3, 4-8, and greater than 8 times a month) and are under the age of 26 (below21 and 21 years old) is about 75.05%. The acceptance of the Carry out & Take Away coupons for all other drivers is about 73.18%.

4. Comparing the Carry out & Take Away coupon acceptance rate of drivers who got Carry out & Take Away more than once a month with no passengers after noon to all others.

![arplot visualizing the driver acceptance and rejection of Carry out & Take Away coupons based on those who get take out more than once a month, with no passengers, after noon.](https://github.com/user-attachments/assets/055f090d-081d-426b-ad1c-b8b23940eabe)

The acceptance of the Carry out & Take Away coupons for drivers who get take out more than once a month (1-3, 4-8, and greater than 8 times a month), with no passengers (Alone), after noon (2PM, 6PM, and 10PM) is about 81.33%. The acceptance of the Carry out & Take Away coupons for all other drivers is about 71.50%.
