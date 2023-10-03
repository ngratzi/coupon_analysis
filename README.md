# Coupon Analysis

# Context
Imagine driving through town and a coupon is delivered to your cell phone for a restaraunt near where you are driving. Would you accept that coupon and take a short detour to the restaraunt? Would you accept the coupon but use it on a sunbsequent trip? Would you ignore the coupon entirely? What if the coupon was for a bar instead of a restaraunt? What about a coffee house? Would you accept a bar coupon with a minor passenger in the car? What about if it was just you and your partner in the car? Would weather impact the rate of acceptance? What about the time of day?
Obviously, proximity to the business is a factor on whether the coupon is delivered to the driver or not, but what are the factors that determine whether a driver accepts the coupon once it is delivered to them? How would you determine whether a driver is likely to accept a coupon?

# Objective
Explore one of the other coupon groups and try to determine the characteristics of passengers who accept the coupons.

# Analysis

## Overview of All Coupon Acceptance Rates

| Coupon                |   False  |    True  |      Sum | Acceptance Rate |
|-----------------------|---------:|---------:|---------:|----------------:|
| Bar                   | 0.093819 | 0.065200 | 0.159019 |        0.410015 |
| Restaurant(20-50)     | 0.065752 | 0.051876 | 0.117629 |        0.441019 |
| Coffee House          | 0.157758 | 0.157285 | 0.315043 |        0.499249 |
| Restaurant(<20)       | 0.064333 | 0.155314 | 0.219647 |        0.707107 |
| Carry out & Take away | 0.049905 | 0.138757 | 0.188663 |        0.735478 |

![Description of image](images/coupon_acceptance.png)

From the data above, the coupon with the largest acceptance rate was the "Carry out & Take away" coupon with ~73% acceptance rate. The Bar coupon was the lowest with 41% acceptance rate. Lets look into the lowest accepted coupons and see if we can identify the target groups for each.

### Bar Coupon Target Groups

Having processed the dataset below are some target groups found for the Bar Coupon.

#### Target Group 1: 
- visit the bar more than once a month AND 
- are over the age of 25

| Group     |   False  |   True  |    Sum  | Acceptance Rate |
|----------------------|---------:|--------:|--------:|----------------:|
| Age > 25 & Visit > 1 |      128 |     292 |     420 |        0.695238 |
| All Others           |     1062 |     535 |    1597 |        0.335003 |

![Description of image](images/bar_visits_age.png)

Among those that visit the bar more than once a month AND are over the age of 25, the acceptance rate was 69.52%, which is 28.52% higher than the overall acceptance rate of 41.00%, indicating that this would be a more granular group to target in future coupon campaigns. Furthermore, a z-test on the data yielded a p-value of 1.08683e-40, which, being less than 0.05, indicates that this difference is statistically significant.

#### Target Group 2

 - go to bars more than once a month AND
 - had passengers that were not a kid AND
 - had occupations other than farming, fishing, or forestry

| Group | False | True | Sum | Acceptance Rate |
|--------------------------|-------|------|-----|-----------------|
| All Others | 1021 | 427 | 1448 | 0.294890 |
| Target Group | 169 | 400 | 569 | 0.702988 |

![Description of image](images/bar_visits_pax_occupation.png)

Among those that go to bars more than once a month AND had passengers that were not a kid AND had occupations other than farming, fishing, or forestry, the acceptance rate was 70.29%, which is 29.29% higher than the overall acceptance rate of 41.00%, indicating that this would be a even more granular group to target in future coupon campaigns. Furthermore, a z-test on the data yielded a p-value of 4.048403e-63, which, being less than 0.05, indicates that this difference is statistically significant.

#### Target Group 3
- Visit bars more than once a month, travel with passengers other than children, and are not widowed,
- Visit bars more than once a month and are under the age of 30, or
- Frequent inexpensive restaurants more than 4 times a month with an income of less than $50K,

| Group   | False | True | Sum  | Acceptance Rate |
|---------------|-------|------|------|-----------------|
| All Others    | 1002  | 671  | 1673 | 0.401076        |
| Target Group  | 188   | 156  | 344  | 0.453488        |

![Description of image](images/bar_complex.png)

The coupon acceptance rate was 45.34%. This rate is a modest increase of only 4.34% compared to the overall acceptance rate of 41.00%. A z-test on this data gave a p-value of 0.0718. Since this value is greater than 0.05, the observed difference is not statistically significant. Hence, targeting this particular group is not recommended.

### Restaurant (20 - 50) Coupon

