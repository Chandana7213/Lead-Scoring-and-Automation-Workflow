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
# Task2 
![image](https://github.com/user-attachments/assets/e5084eda-ef75-4144-b254-7010888a0664)
# Task 3
![Screenshot (207)](https://github.com/user-attachments/assets/47ab69f2-e313-4130-a722-4176e9972c03)

# Links
https://zapier.com/editor/268437861/published               
https://zapier.com/editor/268437861/published                                          
https://zapier.com/editor/268462970/published/_GEN_1732282739487/sample

Steps in Zapier
Trigger: New Google Forms submission.                  
Google Sheets Action: Fetch the total lead score from the sheet.                              
Filter by Zapier: Only proceed if the score > 70 and then edited to > 90.                                                 
Gmail Action: Send a welcome email for high-scoring leads.                   
Google Sheets Action: Log low-scoring leads (<70) in a separate nurturing spreadsheet.      

# Final Conclusion
This project was an enriching experience where I independently designed and implemented a lead management workflow for TechNova using Zapier, Google Forms, Google Sheets, Gmail, and Google Calendar. From capturing and scoring leads to addressing edge cases and scaling for advanced capabilities, every step was thoughtfully executed.

I applied my skills and dedication to create an automated system that prioritizes leads, addresses incomplete data, ensures high-value leads are managed effectively, and incorporates advanced features like keyword extraction and sales rep assignment. This solution is robust, scalable, and designed to enhance TechNova's lead management process with all my dedication and hardwork.

# Key Achievements
Automated lead scoring for prioritization.
Addressed edge cases for incomplete data and high-value lead management.
Enhanced workflow with advanced features like keyword extraction and lead distribution.
Seamlessly integrated tools for an efficient, unified system.
This project reflects my passion and commitment to delivering impactful solutions. Thank you for the opportunity to showcase my skills!
