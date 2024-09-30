
# ADR-008: Event Driven

## Date:
2024-09-29

## Status:
Accepted

## Context:
The ClearView platform must process candidate actions such as uploadresumes, updating resumes, search jobs, and finding tips. These actions must be handled in near real-time to ensure efficiency and provide a seamless user experience.
The ClearView platform must process employer actions such as finding candidates, updating resumes, search jobs, and finding tips. These actions must be handled in near real-time to ensure efficiency and provide a seamless user experience.

## Decision:
We will adopt an Event-Driven Architecture (EDA) to decouple the services and enable real-time communication across the services and components.
### Drivers
- Scalability: The platform needs to handle an increasing volume of candidates,employers,resumes, jobs, and jobmatching.
- Decoupling: Services like Job, resume , jobmatching should operate independently to allow for easier updates and better fault tolerance.
- Real-Time Processing: Candidates and employers expect immediate result after their actions.
### Scenarios
- When a candidate upload resume, the  application generates an event (e.g., resumeuploadevent) with file details.
- This event is published to an event broker  where other components ( e.g., resume parser,jobmatcher) can listen and react accordingly.
- After the resumeuploadevent is processed, other events like ResumeParsed and storycreated can trigger subsequent services.

## Consequences:
### PROS:
- Scalability: Services can scale independently, accommodating fluctuating loads without impacting other services.
- Loose Coupling: Microservices are decoupled, allowing for independent development and deployment.
- Improved Responsiveness: User interactions can be processed in real time, enhancing user experience.
- Enhanced Fault Tolerance: Systems can continue to operate even when some services are temporarily unavailable.

### Cons:
- Increased Complexity: The system architecture becomes more complex, necessitating robust monitoring and logging solutions.
- Eventual Consistency: Data may not be immediately consistent across services, requiring careful handling of business processes.
- Learning Curve: Development teams may need training on EDA principles and tools.
