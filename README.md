# Lead-Scoring-and-Automation-Workflow
# Overview
This repository documents the implementation of a lead scoring system for TechNova using Google Forms, Google Sheets, and Zapier. The workflow captures lead information, calculates scores, and automates actions like sending emails and segmenting leads.
## TechNova Lead Scoring and Automation Workflow
# Overview
This repository documents the implementation of a lead scoring system for TechNova using Google Forms, Google Sheets, and Zapier. The workflow captures lead information, calculates scores, and automates actions like sending emails and segmenting leads.

### Task 1: Lead Scoring System
1. Lead Scoring System Design
We assigned points to each response option as follows:
2. Workflow Automation with Zapier
The workflow automates the following actions:

# Triggers on Google Form submission.
Calculates the lead score using Google Sheets formulas.
Sends a personalized email for leads with a score above 70.
Logs low-scoring leads (<70) in a separate nurturing spreadsheet.
Formulas Used in Google Sheets
Total Lead Score Calculation

# Excel
=SUM(
    IF(A2="1-50 employees",10, IF(A2="51-200 employees",20, IF(A2="201-1000 employees",30,40))),
    IF(B2="Less than $10,000",10, IF(B2="$10,000 - $50,000",20, IF(B2="$50,001 - $100,000",30,40))),
    IF(C2="Immediate (1 month)",40, IF(C2="Short-term (1-3 months)",30, IF(C2="Medium-term (3-6 months)",20,10)))
)              
Replace A2, B2, and C2 with the respective columns for Company Size, Annual Budget, and Urgency.
Industry Column Formula (Optional Example)                       
=IF(D2="Technology", 20, IF(D2="Finance", 15, IF(D2="Healthcare", 10, IF(D2="Retail", 5, 0))))
Conditional Email Trigger A helper column (E2) to indicate if the score exceeds 70:            
=IF(SUM(Your_Scoring_Formula)>70, "Send Email", "Nurture")               
# Zapier Workflow
Published Zap Link
![Screenshot (199)](https://github.com/user-attachments/assets/bafbb78f-1ba8-4744-b830-1fe9d4f427d8)

![Screenshot (201)](https://github.com/user-attachments/assets/9d39bd97-969a-42fa-913e-1aee8e9b8ab1)

![Screenshot (205)](https://github.com/user-attachments/assets/2457a238-a64a-4840-bd74-a29c7e93cbf9)

![Screenshot (195)](https://github.com/user-attachments/assets/0dafc0e0-935d-4ab5-8f1b-1243c587c7a4)

![Screenshot (196)](https://github.com/user-attachments/assets/c3ef7028-20be-4019-a5f2-d789b0a496f3)
https://zapier.com/editor/268437861/published

Steps in Zapier
Trigger: New Google Forms submission.
Google Sheets Action: Fetch the total lead score from the sheet.
Filter by Zapier: Only proceed if the score > 70.
Gmail Action: Send a welcome email for high-scoring leads.
Google Sheets Action: Log low-scoring leads (<70) in a separate nurturing spreadsheet.
