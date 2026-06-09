# Elder-Care-May-Outreach
I built a dynamic report to identify U.S.-based patients aged 70+ with May 2025 appointments. Using Excel functions (FILTER, CHOOSECOLS, SORT), I created a updatable system that streamlines the "Supporting Our Elders" outreach program, ensuring the clinic can efficiently coordinate card orders and patient engagement.

# Business Question
-	Can you get me the May appointments for the “Supporting Our Elders” program? I need to order the “Thank You” cards to send out to our 70+ year olds patients? Remember just the US branches.

# Finished Product
-	A report featuring 70+ year old patients who have May appointments.

# Goals
-	Querying 1000 patient records using dynamic filters.

# Data Source
I got this dataset from Kaggle! Here is the [link](https://www.kaggle.com/datasets/nudratabbas/messy-clinic-appointments-dataset) <br>

I used the cleaned dataset from [this other](https://github.com/Marissa-the-Analyst/Data-Healed) project!

# Process
I took the data columns I wanted using CHOOSECOL, into a filter to meet the query specifications (age, USD, department, and month). Then I made sure to sort by date and used COUNTA and FILTER to get a handy count for the requester. This main filter was created using a dynamic table array, and dataset got updated to include more appointments or appointments were canceled, the array would automatically update. <br>

This is the primary formula used. <br>

=SORT(FILTER(CHOOSECOLS(Table13[[Paitent-ID-Update]:[follow_up_required]],5,2,3,4,8),(Table13[age]>70) * (Table13[appointment_date]>=DATE(2025,5,1)) * (Table13[appointment_date]<=DATE(2025,5,31)) * (Table13[Currency]="USD"))) <br>
<br>
Then I formatted the table and removed gridlines/exported to a PDF. The PDF is perfect to be a formalized report or attachment, but copy-pasting into an email would also have worked just fine!
