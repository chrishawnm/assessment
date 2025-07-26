Hello!

Here's my submission for this assessment.

data modeling (dbt)

Here's a view of my data model. I decided to go with a medallion architecture (bronze/silver/gold) in order fit the use case better than a dimensional data model.
![Alt text](extras/lineage.png)

1. Assumptions:
  i. I assumed that the datasets that were provided were going to be my raw datasets so I have them as my bronze datasets in which I don't make much changes to them.
  ii. I looked over the following video to get a better understanding of the num docs field and why vault was more than the other event types: https://www.harvey.ai/platform/vault
2. Interpretation:
   i. gold_user_engagement: Below are the fields I used to highlight user monthly engagement
        sessions
        num_event_types
        total_docs
        types
        avg_docs_per_session
        last_day
        avg_feedback_score
        pct_good_feedback
        active_days
        avg_docs_per_active_day
   

1. Materializations: Not every table was materialized to a table output. I used three materializations (table, views, ephemeral). For ephemeral tables, I mainly did this because they were mainly in my silver (transformation layer) and a lot of the scripts I was using were calculations for a view or table. It also helped me with storage. I decided to have the bronze layer in which all of the raw data is at as views because we aren't really using these tables. For my gold tables, those are all materialized as tables since we want our end users to be able to query from them and use them in dashboards frequently. 
