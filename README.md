This dataset is about a digital advertising performance system.
It tracks the ads that were shown to users, how users interacted with those ads, which campaigns those ads belonged to, who the users actually are, and how much each campaign spent.
In short, the data is built for analyzing marketing performance, audience behaviour, and budget efficiency.
The first table ad_events.csv — what users actually did; this table logs every interaction a user had with an ad. It includes impressions, clicks, likes, comments, shares, purchases.
The Second Table ads.csv — details for each ad, This table describes every ad that ran. It includes the ad ID, the campaign it belongs to, the platform (Facebook/Instagram), the ad type, and targeting information.
The third table campaigns.csv — the marketing campaigns. This table contains the actual campaigns with campaign name, start and end dates, and the budget.  This is what I use to measure things like top best campaigns, campaigns that waste money etc
Fourth table users.csv, This table contains user demographic and interest information, gender,         age group, location, interests. This lets me find out who actually purchases, which age group,      which country, which interests, which gender.

The tables connect through ad_id, campaign_id, and user_id, 
campaigns - ads - ad_events - users
A campaign has many ads.
Each ad has many events (impressions, clicks, purchases).
Each user can generate multiple events.

I used these KPIs to cover campaign performance, ad performance, audience behavior, and engagements,
I’m including Marketing Performance KPIs such as 
Total Impressions How many times ads were viewed.
Total Clicks How many users interacted by clicking.
 Total Purchases How many conversions happened.
Click Through Rate (CTR) 
CTR = Clicks ÷ Impressions
Shows how attractive the ads were.

 
Conversion Rate (CR)
CR = Purchases ÷ Clicks
Shows how good ads and landing pages are at converting.
 Total Users Reached, how many unique users saw at least one ad.
 Campaign Performance KPIs, these tell you which campaigns performed well and which ones burned budget.
 Total Budget per Campaign Spend comparison across campaigns.
 Purchases per Campaign Measures campaign-level conversions.
Cost Per Purchase (CPP)
CPP = Budget ÷ Purchases
Shows which campaigns waste money.
 Top Performing Campaigns
Ranked by purchases.
Non-Performing / Worst Campaigns
Ad Performance KPIs
These measure the success of individual ads.
 Purchases by Ad ID Identify top-performing ads.
Platform Performance (FB vs Instagram)
Which platform brings better engagement and conversions.

Audience Behavior KPIs
These explain who is actually converting. Purchases by Age Group, Which age segments buy the most, Purchases by Gender, Male vs Female purchase distribution, Purchases by Country, Purchases by Interests
 Engagement KPIs, 
These help you understand actions before purchase, Total Engagement Events (clicks, likes, shares, comments combined)

Technical Aproach
1. Data Import & Preparation — Power Query Editor
I used Power BI Power Query to: Import the four CSV datasets (campaigns, ads, users, ad_events)
Perform initial cleaning such as: Removing unnecessary columns, Fixing data types (dates, integers, text categories), Ensuring user_id, ad_id, and campaign_id were consistent across tables, Handle missing or invalid records in event logs and user data.
 2. Data Modeling — Power BI Data Model, I built a star schema by connecting tables through key fields: campaigns[campaign_id] → ads[campaign_id]
ads[ad_id] → ad_events[ad_id]
users[user_id] → ad_events[user_id]
This relational model allowed accurate filtering, aggregation, and drill-down across campaigns, ads, users, and event types.
3. DAX Measures — Calculations for KPIs, I used DAX (Data Analysis Expressions) to create calculated measures, including, Total Purchases, Total Clicks, Total Impressions, Conversion Rate, Click-Through Rate. DAX allowed me to compute advanced metrics and business KPIs dynamically across the dashboard.
4. Visual Analysis & Dashboard Design — Power BI Visuals
I used a combination of visuals to deliver insights: Cards → High-level KPIs (CTR, CR, total budget, impressions)
Bar/Column Charts → Top & bottom campaigns, ad performance
Treemap → Purchases by Interest
Pie/Donut Charts → Gender and platform distribution
Tables → Cost-per-purchase and ROI analysis
I also applied custom formatting (colors, borders, titles, themes) to improve readability.# Main-Project
Main project
