
# ADR-008: Event Driven

## Date:
2024-09-29

## Status:
Accepted

## Context:
Clearview Systems aims to enhance real-time data processing and improve responsiveness across its platform. Modules like Resume processing, Module re-training and report generation are event drive in nature.

## Decision:
Adopt an Event-Driven Architecture (EDA) to facilitate asynchronous communication between microservices, enabling greater scalability and responsiveness in Clearview Systems.

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
