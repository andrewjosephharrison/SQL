# SQL
Sample Advertising Reporting Database

/* Sample AdReporting Database 

Below is a simple representation of an AdReporting database I've built in SQLite using tables designated "accounts", "campaigns", "adtype", and "ad_performance". This is not about the actual numbers (which I made up) so much as it is about giving you an idea of my ability to sift through relevant data by building more complex SQL queries.

I'll first create the tables and then try to pull some meaningful information out of them while leveraging a number of different SQL functions.

*/


/*Create Accounts Table*/

CREATE TABLE accounts (
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    name TEXT,
    city TEXT,
    state TEXT,
    industry TEXT,
    create_date TEXT
    );

/* It's worth noting that SQLite has limited data types - no built in DATE type */

INSERT INTO accounts (name, city, state, industry, create_date) VALUES ("Comcast", "Philadelphia", "PA", "Telecommunications", "2011-03-31");
INSERT INTO accounts (name, city, state, industry, create_date) VALUES ("Burger King", "Miami", "FL", "Food and Drink", "2012-04-01");
INSERT INTO accounts (name, city, state, industry, create_date) VALUES ("Comedy Central", "New York City", "NY", "Media", "2013-12-21");
INSERT INTO accounts (name, city, state, industry, create_date) VALUES ("Guitar Center", "Westlake Village", "CA", "Retail", "2011-05-14");
INSERT INTO accounts (name, city, state, industry, create_date) VALUES ("In-N-Out", "Irvine", "CA", "Food and Drink", "2001-03-31");
INSERT INTO accounts (name, city, state, industry, create_date) VALUES ("Entelo", "San Francisco", "CA", "Tech", "2014-10-05");
INSERT INTO accounts (name, city, state, industry, create_date) VALUES ("Red Lobster", "Orlando", "FL", "Food and Drink", "2012-10-15");
INSERT INTO accounts (name, city, state, industry, create_date) VALUES ("Trump Real Estate", "New York City", "NY", "Real Estate" , "2011-07-11");
INSERT INTO accounts (name, city, state, industry, create_date) VALUES ("Verizon", "Basking Ridge", "NJ", "Telecommunications" , "2012-06-21");
INSERT INTO accounts (name, city, state, industry, create_date) VALUES ("Target", "Minneapolis", "MN", "Retail" , "2012-09-18");


/*Create Campaigns Table*/

CREATE TABLE campaigns (
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    campaign_name TEXT,
    account_id INTEGER,
    start_date TEXT,
    end_date TEXT,
    adtype_id INTEGER,
    ad_performance_ID INTEGER
    );

INSERT INTO campaigns (campaign_name, account_id, start_date, end_date, adtype_id, ad_performance_ID) VALUES ("SpringFling2014", 4, "2013-01-01", "2013-03-31", 3, 10);
INSERT INTO campaigns (campaign_name, account_id, start_date, end_date, adtype_id, ad_performance_ID) VALUES ("Winter2015", 8, "2015-10-01", "2015-12-31", 2, 12);
INSERT INTO campaigns (campaign_name, account_id, start_date, end_date, adtype_id, ad_performance_ID) VALUES ("FallSavings", 10, "2015-07-01", "2015-9-30", 1, 3);
INSERT INTO campaigns (campaign_name, account_id, start_date, end_date, adtype_id, ad_performance_ID) VALUES ("AllYouCanEatCrablegs", 4, "2014-01-01", "2014-11-30", 3, 4);
INSERT INTO campaigns (campaign_name, account_id, start_date, end_date, adtype_id, ad_performance_ID) VALUES ("ExtraFries", 5, "2014-03-01", "2014-10-31", 2, 5);
INSERT INTO campaigns (campaign_name, account_id, start_date, end_date, adtype_id, ad_performance_ID) VALUES ("FreeMilkshake", 5, "2014-11-01", "2014-11-30", 2, 8);
INSERT INTO campaigns (campaign_name, account_id, start_date, end_date, adtype_id, ad_performance_ID) VALUES ("WeArentThatBad", 1, "2013-01-01", "2013-03-31", 1, 7);
INSERT INTO campaigns (campaign_name, account_id, start_date, end_date, adtype_id, ad_performance_ID) VALUES ("UnlimitedData", 9, "2015-04-01", "2015-06-30", 3, 6);
INSERT INTO campaigns (campaign_name, account_id, start_date, end_date, adtype_id, ad_performance_ID) VALUES ("FreePhone", 9, "2015-01-01", "2015-03-31", 1, 9);
INSERT INTO campaigns (campaign_name, account_id, start_date, end_date, adtype_id, ad_performance_ID) VALUES ("TwentyPercentOff", 7, "2015-01-01", "2015-03-31", 3, 1);
INSERT INTO campaigns (campaign_name, account_id, start_date, end_date, adtype_id, ad_performance_ID) VALUES ("DrumRoll2015", 4, "2015-07-01", "2015-9-30", 2, 11);
INSERT INTO campaigns (campaign_name, account_id, start_date, end_date, adtype_id, ad_performance_ID) VALUES ("SeriouslyWeArentThatBad", 1, "2014-06-01", "2014-10-31", 1, 2);
INSERT INTO campaigns (campaign_name, account_id, start_date, end_date, adtype_id, ad_performance_ID) VALUES ("NewSeason", 3, "2014-05-01", "2014-05-30", 3, 13);
INSERT INTO campaigns (campaign_name, account_id, start_date, end_date, adtype_id, ad_performance_ID) VALUES ("RickAndMorty", 3, "2015-10-01", "2015-12-31", 1, 14);
INSERT INTO campaigns (campaign_name, account_id, start_date, end_date, adtype_id, ad_performance_ID) VALUES ("NewContract", 4, "2015-01-01", "2015-03-31", 2, 15);


/*Create AdType Table*/

CREATE TABLE adtype (
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    typename TEXT,
    extention TEXT
    );

INSERT INTO adtype (typename, extention) VALUES ("Display",".png");
INSERT INTO adtype (typename, extention) VALUES ("Native",".jpg");
INSERT INTO adtype (typename, extention) VALUES ("Video",".mpeg");


/*Create ad_performance Table*/

CREATE TABLE ad_performance (
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    domain TEXT,
    impressions REAL,
    clicks REAL,
    conversions REAL
    );

INSERT INTO ad_performance (domain, impressions, clicks, conversions) VALUES ("buzzfeed.com",1000,200,50);
INSERT INTO ad_performance (domain, impressions, clicks, conversions) VALUES ("clickhole.com",2000,200,20);
INSERT INTO ad_performance (domain, impressions, clicks, conversions) VALUES ("onion.com",5000,200,30);
INSERT INTO ad_performance (domain, impressions, clicks, conversions) VALUES ("facebook.com",1200,70,12);
INSERT INTO ad_performance (domain, impressions, clicks, conversions) VALUES ("cracked.com",1500,250,50);
INSERT INTO ad_performance (domain, impressions, clicks, conversions) VALUES ("buzzfeed.com",3000,200,25);
INSERT INTO ad_performance (domain, impressions, clicks, conversions) VALUES ("buzzfeed.com",1000,100,20);
INSERT INTO ad_performance (domain, impressions, clicks, conversions) VALUES ("cracked.com",2000,250,50);
INSERT INTO ad_performance (domain, impressions, clicks, conversions) VALUES ("vice.com",3000,200,50);
INSERT INTO ad_performance (domain, impressions, clicks, conversions) VALUES ("vice.com",1000,200,50);
INSERT INTO ad_performance (domain, impressions, clicks, conversions) VALUES ("facebook.com",2000,100,10);
INSERT INTO ad_performance (domain, impressions, clicks, conversions) VALUES ("outdoors.com",3000,150,20);
INSERT INTO ad_performance (domain, impressions, clicks, conversions) VALUES ("complex.com",1000,200,20);
INSERT INTO ad_performance (domain, impressions, clicks, conversions) VALUES ("onion.com",1500,100,5);


SELECT * FROM accounts;
SELECT * FROM campaigns;
SELECT * FROM adtype;
SELECT * FROM ad_performance;

/* 

Q) Find the total number of campaigns that have run historically under each account in the database. Sort by highest total number of campaigns.

A) We'll need to use a LEFT OUTER JOIN and a COUNT function. LEFT OUTER JOIN is used instead of an INNER JOIN because we want to see the accounts listed even if they have had no campaigns. As a belated answer to your interview question, LEFT OUTER JOIN pulls all of the rows from the first table (in this case accounts) and matches them against the second table (campaigns) using the specified conditional. If the second table has no match, the field is displayed as "NULL". 

An INNER JOIN would only return rows from "accounts" that matched up to the ON conditional, and would not show us the accounts with no campaigns. 

*/

SELECT accounts.name, COUNT(campaigns.campaign_name) AS number_of_campaigns FROM accounts
    LEFT OUTER JOIN campaigns
    ON accounts.id = campaigns.account_id
    GROUP BY accounts.name
    ORDER BY number_of_campaigns DESC;
    




/* 

Q) Find the ad type (display, native, video) that has the highest click through rate across the board for our database.


A) We need to join three tables for this problem. Typename from the "adtype" table needs to be matched to the impression data on the "ad_performance" table, and the only common factor lies in the "campaigns" id fields. Since we are only concerned with campaigns that have data, a standard INNER JOIN will be fine.

Once we group by ad type, we can create a formula to calculate click through rate on an aggregate level. 

*/ 

SELECT adtype.typename, sum(clicks) as total_clicks, sum(impressions) as total_impressions, ROUND(((sum(clicks)/sum(impressions))*100),2) as clickthroughrate_percentage FROM ad_performance
    JOIN campaigns
    ON campaigns.ad_performance_id = ad_performance.id
    JOIN adtype
    ON adtype.id = campaigns.adtype_id
    GROUP BY adtype.typename;
    

/* 
Q) Find the conversion rate (conversions/click) by quarter for 2015 campaigns.

A) Since there are no buckets for quarter in our database, we need to create them using the CASE function. We will then GROUP BY quarter and calculate by creating a conversion rate formula.


Two things to note:
1) We wouldn't have enough information to handle this if we had any campaigns that carried over quarters for 2015. The conversion rate could fluctuate over time, and we would need to dig deeper to determine the clicks split on a weekly (or even daily) basis to properly bucket them into quarters. I'm keeping this database simple for now by cleanly designating 2015 campaigns in quarterly increments, but these are exactly the sort of edge cases I was forced to deal with while fine tuning SQL queries at Quantcast for our pod metrics dashboard.

2) SQLite seems to be pretty terrible at date functionality. I'm going to CASE bucket using start date - usually I would have tried to do a range

*/

SELECT 
    CASE
        WHEN start_date = "2015-01-01" THEN "Q1"
        WHEN start_date = "2015-04-01" THEN "Q2"
        WHEN start_date = "2015-07-01" THEN "Q3"
        ELSE "Q4"
    END "quarter",
    sum(ad_performance.conversions),
    sum(ad_performance.clicks),
    round(((sum(ad_performance.conversions)/sum(ad_performance.clicks))*100),2) as conversionrate_percentage
    FROM campaigns
        JOIN ad_performance
        ON campaigns.ad_performance_ID = ad_performance.ID
        GROUP BY quarter
        ORDER BY quarter;
