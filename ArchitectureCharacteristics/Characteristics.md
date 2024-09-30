# Architecture characteristics

## Requirements Refinement
To effectively select the appropriate architecture characteristics, it is essential to begin with the requirements and meticulously identify keywords, aligning them with the pertinent definitions of architecture characteristics.


|    | Actions                   | Requirement                                                                                                                                                                                                                                                                                                                                         | Architecture Characteristics                                                    |
|----|---------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------|
| 1  | Registration              | Candidate:</br><ul><li>Registration with basic personal information</li></ul>Employer: </br><ul><li>Registration with basic personal & company information </li></ul>System: </br><ul><li>Authorization & Authentication </li><li> Store details in the DB </li></ul>AI: <br/><ul><li>Fetch the company details after Employer Registers </li></ul> | Security<br/>Data Privacy<br/>Scalability                                       |
| 2  | Upload Resume             | Candidate: </br><ul><li>Uploads the resume in PDF, word format </li></ul>System: </br><ul><li>Validate and parse the resume and store in DB </li></ul>                                                                                                                                                                                              | Security<br/>Performance<br/>Recoverability<br/>Adaptability                    |
| 3  | Resume Tips               | AI: </br><ul><li>Analyze/Reanalyze and provide the Tips to improve the resume</li></ul>Candidate:</br><ul><li>Review the tips and update the resume and resubmit</li></ul>                                                                                                                                                                          | Accuracy<br/>Security<br/>Adaptability                                          |
| 4  | Create SMART Goal & Story | AI: </br><ul><li>Create SMART Goals and Stories for each candidate </li></ul>                                                                                                                                                                                                                                                                       | Accuracy<br/>Security<br/>Consistency<br/>Adaptability                          |
| 5  | Submit Resume             | Candidate: </br><ul><li>Review the updates and goals/story and submit.</li></ul>System: </br><ul><li>Store the details in the DB</li></ul>                                                                                                                                                                                                          | Recoverability<br/>Data Integrity                                               |
| 6  | Anonymize Resume          | AI: </br><ul><li>Analyze the resume and anonymize the biased data</li></ul>                                                                                                                                                                                                                                                                         | Accuracy<br/>Consistency<br/>Security<br/>Adaptability                          |
| 7  | Find Match                | System:</br><ul><li> Find the resume and job match </li><li>Calculate the Similarity/Match Score </li><li>Store the details to DB </li></ul>Candidate:</br><ul><li> Review the Match and Score</li></ul>                                                                                                                                            | Accuracy <br/>Scalability <br/>Performance <br/>Data Integrity <br/>Adaptability |
| 8  | Display Match to Employer | System:</br><ul><li> List the Match and Score to the Employer </li></ul>Employer:</br><ul><li> View the Match and Score </li></ul>                                                                                                                                                                                                                  | Accuracy <br/>Performance                                                       |
| 9  | Unlock Resume             | Employer:</br><ul><li>Make Payment and unlock the profile </li></ul>System:</br><ul><li>Send the actual resume to the employer</li><li>Update details in the DB </li></ul>                                                                                                                                                                          | Security                                                                        |
| 10 | Mark as Hired             | Employer:</br><ul><li> Mark the candidate as Hired/Not Hired </li></ul>System:</br><ul><li>Update the details in the DB </li></ul>                                                                                                                                                                                                                  | Data Integrity                                                                  |
| 11 | Remove Resume             | Candidate:</br><ul><li>Remove/Delete the resume from the system</li></ul>System:</br><ul><li>Mark the candidate as inactive</li><li>Remove the candidate details like Match and Score</li> <li>Update the details in the DB</li></ul>                                                                                                               | Security                                                                        |
| 12 | Delete Account            | Candidate:</br><ul><li>Delete the account from system </li></ul>System:</br><ul><li>Delete all the details from the system and DB </li><li>Mark the user as deleted</li></ul>                                                                                                                                                                       | Security                                                                        |
| 13 | HRMS Integration          | System:</br><ul><li>Integrate the HRMS systems to fetch the Job Details</li><li>Convert the received data to standard format</li><li>Store the standardized data to DB </li></ul>                                                                                                                                                                   | Interoperability <br/>Adaptability <br/>Security                                |
| 14 | Admin View                | Admin:</br><ul><li>View the system analytics details</li><li>Generate reports</li></ul>                                                                                                                                                                                                                                                             | Scalability                                                                     |
| 15 | Other Consideration       | ???                                                                                                                                                                                                                                                                                                                                                 | ???                                                                             |



| Term             | Definition                                                                                                                                                                                                                                                                                                                                                                                             |
|------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Security         | Security encompasses the strategies, practices, and technologies designed to protect data and systems from unauthorized access, breaches, attacks, and other cyber threats. It involves ensuring data confidentiality, integrity, and availability, protecting against vulnerabilities, and complying with relevant regulations and standards.                                                         |
| Performance      | Performance refers to a system's responsiveness, speed, and stability under a given load. It measures how quickly a system can process transactions, execute tasks, and deliver information to users. High performance contributes to a better user experience and efficiency in operations.                                                                                                           |
| Scalability      | Scalability refers to a system's ability to handle increased loads without compromising performance or user experience. This can involve scaling up (adding more resources to the existing infrastructure) or scaling out (adding more instances of resources). Scalability ensures that the system can grow in response to increased demand, whether it's handling more data, users, or transactions. |
| Interoperability | The ability of the system to interface and interact with other systems to complete a business request                                                                                                                                                                                                                                                                                                  |
| Data Integrity   | The data across the system is correct and there is no data loss in the system                                                                                                                                                                                                                                                                                                                          |
| Adaptability     | The ease in which a system can adapt to changes in environment and functionality                                                                                                                                                                                                                                                                                                                       |
| Recoverability   | The ability of the system to start where it left off in the event of a system crash                                                                                                                                                                                                                                                                                                                    |


# Choosing the Top 7 characteristics
The primary considerations that should be prioritized are as follows:
* *Security*, given the nature of the system that will be storing the personal and company details and dealing with AI LLM system, security is uncompromised characteristics.
* *Performance*, given the requirement to integrate with external HRMS systems, integrating with LLM system, generating resume tips and goals and report generations system should respond promptly.
* *Scalability*, given the nature of the system to support dynamic candidate and company load, system should be scalable.
* *Interoperability*, given the nature of the system to connect with external HRMS system and fetch the information, system should be Interoperable.
* *Data Integrity*, given the nature of the system to anonymize the user data and create goals and story, data loss or corruption should not occur.
* *Adaptability*, given the nature of the system to deal with different resume formats, personalized resume data content and different HRMS standards, system should be highly adaptable.
* *Recoverability*, given the nature of the system to support multiple iteration of resume update and job postings, system should be able to resume from previous step.

## *[NEED TO REVIEW AND UPDATE THE BELOW]*
The importance of *Scalability* has been downplayed as the maximum load has already been defined. In the event of adding new sensors, the system can be manually rescaled by incorporating additional nodes or hardware. More info here: [ADR-008](/ADR/ADR-008-scalibility-downplayed.md)
Regarding *Deployability*, its significance is diminished as the system will be installed only once per hospital, without the need for migrations. More info here: [ADR-009](/ADR/ADR-009-deployability-downplayed.md)


# Finding top3 architecture characteristics
On the Event storming session, there were discovered 4 logic modules of *MonitorMe* application:

<img src="images/4components.png" />

The subsequent step involves tagging identified components, placing sticky notes where the characteristic is necessary. 

<img src="images/components-sticky-cards.png">

As shown in the picture above, certain characteristics are significant only for individual modules, such as *Security*, *Fault-tolerance*, and *Configurability*. 
Among the remaining four characteristics:
* *Availability*
* *Evolvability*
* *Performance*
* *Elasticity*

Then, during requirements distillation we assigned the requirements to the characteristics:

## Availability:

- MonitorMe needs to be highly available to ensure continuous monitoring of patients' vital signs.
- The system should be resilient to failures of individual vital sign devices or software components, ensuring uninterrupted monitoring.
- Availability is crucial for timely alerts to medical professionals in case of any issues detected with patients' vital signs.
- The system should have redundancy mechanisms in place to handle failures without disruption to the monitoring process.
- In case of hardware or software failures, the system should gracefully degrade functionality to ensure critical monitoring tasks continue.

## Evolvability:

- StayHealthy, Inc. anticipates future changes and additions to the vital sign monitoring devices.
- The architecture should be designed to accommodate future expansions and integrations seamlessly.
- Modularity and extensibility should be key design principles to facilitate easy integration of new vital sign devices or changes to existing ones.
- The system should support updates and enhancements without significant downtime or disruption to ongoing monitoring activities.
- StayHealthy, Inc. should be able to adapt the system to meet changing business needs and market demands efficiently.

## Performance:

- The system should provide real-time monitoring with an average response time of 1 second or less for consolidating and displaying patients' vital signs.
- Efficient data processing and analysis are required to ensure timely alerts to medical professionals based on preset thresholds or detected issues.
- Scalability and optimization are necessary to handle the varying rates at which vital sign readings are transmitted from different monitoring devices.
- The system should be capable of storing and retrieving past 24 hours of vital sign readings for each patient efficiently.
- Performance optimizations should be implemented to handle the concurrent monitoring of multiple patients with different vital sign devices.

## Elasticity:

- The architecture should be able to scale resources dynamically to accommodate varying workloads and the addition of new patients or vital sign devices.
- Elasticity is crucial to handle peak loads and spikes in data transmission rates from vital sign devices without impacting system performance.
- Auto-scaling mechanisms should be implemented to adjust computing resources based on demand, ensuring optimal resource utilization and cost-effectiveness.
- The system should be designed to scale horizontally to support the deployment of multiple instances across different physical hospital locations without sacrificing performance or availability.


it is challenging to narrow down to only three characteristics, but it is important to note that *Availability* is contingent upon both *Performance* and *Elasticity*. Moreover Availability is not considered in the selection of the system architecture as it is not specified in the template. Availability will be ensured at the infrastructure level. [ADR-010](/ADR/ADR-010-availability-not-used-for-choosing-system-architecture.md)
If both are satisfactory, the system should remain available. Consequently, the final Top 3 are *Evolvability*, *Performance*, and *Elasticity* [ADR-011](/ADR/ADR-011-top3-characteristics.md).


<img src="images/top3-final.png" />
