# Event storming
In the realm of software engineering, the "Clearview" project posed a challenge to develop an advanced system for a transparent hiring process. This undertaking necessitated careful planning and the use of event-storming methodology to effectively understand and design a system that aligns with actual needs and workflows. Below, we outline the technical journey of the "Clearview" project, detailing the phases of event-storming while emphasizing the technical aspects and challenges encountered.

## 1. Gathering events and sequencing
The initial step involved gathering key events essential for the operation of the "Clearview" system.The events were arranged chronologically to grasp the flow of data and interactions within the system. This sequence illuminated the temporal dependencies between events and their impact on both system operations and the patient care process. The following events were identified:

- **Candidate registered**: A new candidate is added to the system, marking the beginning of their job search journey.
- **resume uploaded**: The candidate uploads their resume to the system.
- **resume parsed**: uploaded resume parsed for data processing.
- **resume updated**: update resume if any error / after geeting sugggestion from system.
- **resume previewed**: after uploading preview resume.
- **resume submitted**: resume submitted for finding jobs.
- **job applied**: appllied jobs for after seeing matching jobs.
- **ai- resume recieved**: AI modules recived resume data for recommentation and best matching.
- **resume tips showed**: Ai System suggest tips for improving candidate resume.
- **profile anonimized**: anonimize profile for better security and privacy.
- **story created**: AI module generate story of resume after reading resume data.
- **job description recieved**: recieve job posting and decription from various HR system.
- **job matched**: job match between profile and job posting
- **employer registered**: A new company added to the system.
- **company details filled**: employer filled necessary details.
- **job posting fetched**: System fetch jobs from all registered comanies in a specific interval.
- **matching profile fetched**: system finds matching profile for jobs.
- **matching profile displayed**: listout matching profiles for each job in UI
- **profile viewed**:employer view the matching profiles with limitted data/acess
- **employer payment completed**: payment initiated by employer for getting full details.
- **invoice created**: Payment invoice created for future referance.
- **profile unlocked**: after payment candidate profile unclocked for getting candidate full deatails including contact information.
- **mark candidate as hired**: Employer will mark if candidate is hired for a perticular roles.
- **mark candidate as not hired**: sysytem update no hired status.
- **survey taken**: employer and candidate will take survey about the system.
- **admin registered**: A new clearview admin registered for accesssing data.
- **employer listed**: clear view admin lisout all the employers who registered.
- **candidate listed**: clear view admin lisout all the candidtes who registered.
- **analytics data generated**: system generates analytics data for better recommentation.
- **report generated**: admin see the all data as report..


<img src="img/Event Storming 1.png" />


## 2. Adding actors and commands
This phase defined the actors and commands necessary for user interaction with the system and event processing. Example commands include:


**user role**:
- candidate - A job seeker is responsible for registering their profile, uploading their resume, and applying for suitable jobs.
- employer - An employer, including company recruiters and HR personnel, is responsible for registering the company, providing necessary information, and managing matching profiles after payment.
- admin - A person overseeing the Clearview system is responsible for generating reports and accessing analytics data.

**commands**:
- upload data - upload resumes data in a word / pdf format.
- read data - read resume and process data to further job matching
- update data - update resume data and job data
- initiate payment - payment initiated by employer for seing match profiles 
- create invioice - payment invoice creation
- generate analytics - generate data for report and anlaytics


<img src="img/Event Storming 2.png" />

## 3. Grouping events
Events were grouped according to functionality or business processes, e.g., patient registration, data monitoring, and health status analysis. This grouping helped us understand the system's modular nature and facilitated the design of bounded context.

In this phase, bounded contexts:
1. Account
- manages candidates,employers,admin
- set their roles.
- Store their  profile data
- Hold company details

2. Resume Processing
- Parse resume
- Send to AI Module
- Anonimaize data
- Ensure secure profile data
- ensure redily available for report and analysis

3. Job Matching
- Find matching jobs for candidates
- Find matching candidate for employer

4. Report
- Process and show candidates, Employer details
- Fetch and Show resume data

5. Hiring
- Hire Candidates
- Mark candidates hiring
- Mark Job status

6. Batch process
- Fet job data in a specific time interval

7. Feedback
- survey for candidates
- survey for employer
  
<img src="img/Event Storming 4.png" />


# Summary:


