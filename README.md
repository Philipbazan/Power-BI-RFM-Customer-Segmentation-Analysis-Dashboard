# Power-BI-RFM-Customer-Segmentation-Analysis-Dashboard
[Project Link](https://app.powerbi.com/view?r=eyJrIjoiMTNiYjQ2MTgtMzQ2NS00NWJjLTlkM2EtNDJiNTcyYTRiOGI1IiwidCI6ImEwN2E1MjljLTRiZGItNGJiNi04NjllLWViNWJmMzFhODI1MyIsImMiOjZ9)
# Introduction
Zomato is a food ordering app.

In this project, I performed an RFM (Recency, Frequency, Monetary) analysis on the Zomato app's customer data to better understand user behavior and segmentation. By calculating RFM scores, I categorized users into distinct segments based on how recently they ordered, their order frequency, and total spent. This segmentation enabled us to identify high-value customers, dormant users, and those with growth potential, providing actionable insights for targeted marketing strategies. The analysis not only highlighted customer lifetime value but also paved the way for personalized retention efforts and marketing strategies to maximize engagement and revenue.

First I created Values for each customer based on R, F, and M and separated them into quintiles ranging from highest 20% to lowest 20%
![RFM screenshot](https://github.com/user-attachments/assets/768d1354-83b3-499f-b1de-1032aa447326)

This then allowed me to create segments based on these scores using DAX formulas like:

![Screenshot 2024-10-28 183030](https://github.com/user-attachments/assets/111d9f8c-2c48-43a2-907f-c4b4851545ca)

For example, Best customers are customers which exhibit the highest (4,5) or Top 60%-100% when it comes to Monetary(M) value of thier combined purchases, Frequency (F) of thier purchases, as well as being very Recent (R) purchasers
Best customers were segments like 555 and 544

This Segmentation allowed me to perform various analyses contrasting each segment which represented distinct and unique customer behavior, allowing for deep insight.

Please see the dashboard linked at the begginning of the introduction to interact with the dashboard.

![Power BI Project](https://github.com/user-attachments/assets/8729fe0b-98f7-40a0-90e5-e47bdd33d51b)
