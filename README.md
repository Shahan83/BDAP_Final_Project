# BDAP_Final_Project - Ponpare Kaggle project

Final Project for the Big Data and Analytics Course from Kaggle: "Predict which coupons a customer will buy."

Link for the Project Description and Data - https://www.kaggle.com/c/coupon-purchase-prediction

Ponpare released a year’s worth of data, from 07/01/2011 to 06/30/2012 (except the information related to the very last week i.e. 06/24/2012-06/30/2012, which is kept out for the model evaluation purposes) about the users, visits, purchases, and products of its coupon website. This contains coupon view and purchase logs of 22873 users. In this time period they viewed 32,628 coupons. Of these, attributes of only 19,413 coupons have been provided.

We need to predict as to which of the new 310 coupons [whose attributes are provided] will be purchased by customers. Other information provided includes Past browsing data of users, demographic data of users and data about coupons and where they can be accessed etc. Namely, we have the following data files:

User_list.csv: Master list of all the registered users including their state, sex, age, registration and withdraw dates, residential prefecture and user ID hashtag.

Column Name Description Type Length Decimal Note

USER_ID_HASH User ID VARCHAR2 32

REG_DATE Registered date DATE Sign up date

SEX_ID Gender CHAR 1 f = female m = male

AGE Age NUMBER 4 0

WITHDRAW_DATE Unregistered date DATE

PREF_NAME Residential Prefecture VARCHAR2 2 [JPN] Not registered if empty

Coupon_list_train.csv - Some information about some of the coupons that has been offered in the past year (during 07/01/2011-06/24/2012) including their general category, sub-category, store location, store state, discount rate, original/discounted price of the item, validity period, availability period, coupon ID hashtag, etc. This is part of the training dataset and does not include any coupon in the test dataset i.e. any coupon offered anytime during 06/24/2012-06/30/2012.

Coupon_list_test.csv - The master list of coupons which are considered part of the test set. The predictions should be sourced only from these 310 coupons.

Column Name Description Type Length Decimal Note

CAPSULE_TEXT Capsule text VARCHAR2 20 [JPN]

GENRE_NAME Category name VARCHAR2 50 [JPN]

PRICE_RATE Discount rate NUMBER 4 0

CATALOG_PRICE List price NUMBER 10 0

DISCOUNT_PRICE Discount price NUMBER 10 0

DISPFROM Sales release date DATE

DISPEND Sales end date DATE

DISPPERIOD Sales period (day) NUMBER 4 0

VALIDFROM The term of validity starts DATE

VALIDEND The term of validity ends DATE

VALIDPERIOD Validity period (day) NUMBER 4 0

USABLE_DATE_MON Is available on Monday CHAR 1

USABLE_DATE_TUE Is available on Tuesday CHAR 1

USABLE_DATE_WED Is available on Wednesday CHAR 1

USABLE_DATE_THU Is available on Thursday CHAR 1

USABLE_DATE_FRI Is available on Friday CHAR 1

USABLE_DATE_SAT Is available on Saturday CHAR 1

USABLE_DATE_SUN Is available on Sunday CHAR 1

USABLE_DATE_HOLIDAY Is available on holiday CHAR 1

USABLE_DATE_BEFORE_HOLIDAY Is available on the day CHAR 1

before holiday

LARGE_AREA_NAME Large area name of shop location VARCHAR2 30 [JPN]

KEN_NAME Prefecture name of shop VARCHAR2 8 [JPN]

SMALL_AREA_NAME Small area name of shop location VARCHAR2 30 [JPN]

COUPON_ID_HASH Coupon ID VARCHAR2 32

Coupon_visit_train.csv - Information about the visits (or simply the records of the all clicks on each coupon by any registered user in the website during 07/01/2011-06/24/2012) including: the date of visit, the user ID of the visitor, the coupon ID of the visited coupon, etc. This information is not provided for the test period.

Column Name Description Type Length Decimal Note

PURCHASE_FLG Purchased flag NUMBER 1 0 0:Not purchased 1:Purchased

PURCHASEID_hash Purchase ID VARCHAR2 128

I_DATE View date DATE Purchase date if purchased

PAGE_SERIAL VARCHAR2

REFERRER_hash Referer VARCHAR2 4000

VIEW_COUPON_ID_hash Browsing Coupon ID VARCHAR2 128

USER_ID_hash User ID VARCHAR2 10

SESSION_ID_hash Session ID VARCHAR2 128

Coupon_detail_train.csv - Information about the purchases in the website during 07/01/2011-06/24/2012 including the location, number of purchased items, date of purchase, the user ID of the purchaser, the coupon ID of the purchased coupon, etc. Again, this information is not provided for the test period.

Column Name Description Type Length Decimal Note

ITEM_COUNT Purchased item count NUMBER 10 0

I_DATE Purchase date DATE

SMALL_AREA_NAME Small area name VARCHAR2 30 [JPN] User residential area name

PURCHASEID_hash Purchase ID VARCHAR2 32

USER_ID_hash User ID VARCHAR2 32

COUPON_ID_hash Coupon ID VARCHAR2 32

Coupon_area_train.csv - the coupon listing area for the training set coupons.

Coupon_area_test.csv - the coupon listing area for the test set coupons.

Column Name Description Type Length Decimal Note

SMALL_AREA_NAME Small area name VARCHAR2 30 [JPN]

PREF_NAME Listed prefecture name VARCHAR2 8 [JPN]

COUPON_ID Coupon ID VARCHAR2 32


 Steps in the Analysis of data:
 
 
A. Translate the data

B. Clean and Merge the data

C. Exploratory Analysis

D. Calculate Cosine Similarity

E. Take top 10 coupons according to similarity
