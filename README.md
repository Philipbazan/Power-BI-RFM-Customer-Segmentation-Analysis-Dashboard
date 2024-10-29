# Power-BI-RFM-Customer-Segmentation-Analysis-Dashboard
[Project Link](https://app.powerbi.com/view?r=eyJrIjoiMTNiYjQ2MTgtMzQ2NS00NWJjLTlkM2EtNDJiNTcyYTRiOGI1IiwidCI6ImEwN2E1MjljLTRiZGItNGJiNi04NjllLWViNWJmMzFhODI1MyIsImMiOjZ9)
# Introduction
Zomato is a food ordering app.

In this project, I performed an RFM (Recency, Frequency, Monetary) analysis on the Zomato app's customer data to better understand user behavior and segmentation. By calculating RFM scores, I categorized users into distinct segments based on how recently they ordered, their order frequency, and total spent. This segmentation enabled us to identify high-value customers, dormant users, and those with growth potential, providing actionable insights for targeted marketing strategies. The analysis not only highlighted customer lifetime value but also paved the way for personalized retention efforts and marketing strategies to maximize engagement and revenue.

First I created Values for each customer based on R, F, and M and separated them into quintiles ranging from highest 20% to lowest 20%
![RFM screenshot](https://github.com/user-attachments/assets/768d1354-83b3-499f-b1de-1032aa447326)

This then allowed me to create segments based on these scores using DAX formulas like:

Customer Segment = 
VAR SelectedSegment = SELECTEDVALUE(SegmentTable[Segment], "All")
RETURN
SWITCH(
    TRUE(),
    SelectedSegment = "All", "All",
    FORMAT('RFM table'[RFM], "000") IN {"555", "554", "544", "545", "454", "455", "445"}, "Best Customers",
    FORMAT('RFM table'[RFM], "000") IN {"543", "444", "435", "355", "354", "345", "344", "335"}, "Loyal",
    FORMAT('RFM table'[RFM], "000") IN {"553", "551", "552", "541", "542", "533", "532", "531", "452", "451", "442", "441", "431", "453", "433", "432", "423", "353", "352", "351", "342", "341", "333", "323"}, "Potential Loyalist",
    FORMAT('RFM table'[RFM], "000") IN {"512", "511", "422", "421", "412", "411", "311"}, "New Customers",
    FORMAT('RFM table'[RFM], "000") IN {"525", "524", "523", "522", "521", "515", "514", "513", "425", "424", "413", "414", "415", "315", "314", "313"}, "Promising",
    FORMAT('RFM table'[RFM], "000") IN {"535", "534", "443", "434", "343", "334", "325", "324"}, "Need Attention",
    FORMAT('RFM table'[RFM], "000") IN {"331", "321", "312", "221", "213", "231", "241", "251"}, "About To Sleep",
    FORMAT('RFM table'[RFM], "000") IN {"255", "254", "245", "244", "253", "252", "243", "242", "235", "234", "225", "224", "153", "152", "145", "143", "142", "135", "134", "133", "125", "124"}, "At Risk",
    FORMAT('RFM table'[RFM], "000") IN {"155", "154", "144", "214", "215", "115", "114", "113"}, "Cannot Lose Them",
    FORMAT('RFM table'[RFM], "000") IN {"332", "322", "231", "241", "251", "233", "232", "223", "222", "132", "123", "122", "212", "211"}, "Hibernating customers",
    FORMAT('RFM table'[RFM], "000") IN {"111", "112", "121", "131", "141", "151"}, "Lost customers",
    "Other"
)

For example, Best customers are customers which exhibit the highest (4,5) or Top 60%-100% when it comes to Monetary(M) value of thier combined purchases, Frequency (F) of thier purchases, as well as being very Recent (R) purchasers

Please see the dashboard linked at the begginning of the introduction to interact with the dashboard.

![Power BI Project](https://github.com/user-attachments/assets/8729fe0b-98f7-40a0-90e5-e47bdd33d51b)
