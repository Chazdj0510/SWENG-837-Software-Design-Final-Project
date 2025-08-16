# SWENG-837-Software-Design-Final-Project - Healthcare System

## Overview

This project presents a modular, cloud-deployable healthcare system designed using Object-Oriented Analysis and Design (OOAD) principles. It emphasizes domain modeling, UML-based architecture, and design pattern integration to solve real-world challenges in prescription management, appointment scheduling, and insurance verification.

---

## Project Goal

Design an optimal software solution using:

- **OOAD**: Reusable, maintainable object-oriented structures
- **Domain Modeling**: Technology-agnostic entity relationships
- **Design Patterns**: GRASP, SOLID, GoF, and Microservices best practices

---

## Problem Statement & Requirements

### Business Requirements
- Address inefficiencies in prescription dispensing and appointment scheduling
- Provide secure, scalable access for patients, providers, and pharmacists
- Support business goals like compliance, traceability, and operational efficiency

### Non-Functional Requirements
- **Performance**: Scalable architecture with low latency
- **Security**: OAuth2, IAM roles, TLS encryption, HIPAA compliance
- **Maintainability**: Modular components, IaC scripts, clear documentation
- **Availability**: Cloud-hosted with fault tolerance and backups
## UML Diagrams & Design Component Explanations

This section explains the purpose, structure, and rationale behind each UML diagram and architectural component used in the project.

---

### 1. Use Case Diagram

**Purpose**: Captures the system’s functional scope by showing how external actors (users, systems) interact with the system.

**Explanation**:
- **Actors**: Patient, Provider, Pharmacist, Insurance System
- **Use Cases**: Schedule Appointment, Request Prescription, Dispense Medication, Verify Insurance
- **Rationale**: Helps identify system boundaries and user goals, guiding domain modeling and interface design.

---

### 2. Domain Model

**Purpose**: Represents core entities and their relationships, independent of implementation.

**Explanation**:
- **Entities**: Patient, Appointment, Prescription, Medication, Provider
- **Relationships**: One-to-many between Patient and Appointment; Aggregation between Prescription and Medication
- **Rationale**: Clarifies business logic and informs class diagram structure.

---

### 3. Class Diagram

**Purpose**: Translates the domain model into implementable classes with attributes and methods.

**Explanation**:
- **Classes**: `Patient`, `Appointment`, `Prescription`, `Medication`, `Provider`
- **Attributes**: e.g., `Prescription.dateIssued`, `Medication.dosage`
- **Methods**: e.g., `Appointment.schedule()`, `Prescription.validateInsurance()`
- **Rationale**: Supports maintainable, object-oriented design aligned with SOLID principles.

---

### 4. Sequence Diagrams

**Purpose**: Shows object interactions over time for specific use cases.

**Explanation**:
- **Use Case**: “Schedule Appointment”
- **Objects**: `Patient`, `AppointmentController`, `CalendarService`
- **Flow**: Patient requests → Controller validates → CalendarService books slot
- **Rationale**: Clarifies message flow and method invocation order.

---

### 5. State Diagram

**Purpose**: Models the lifecycle of a key object and its state transitions.

**Explanation**:
- **Object**: `Prescription`
- **States**: Draft → Submitted → Approved → Dispensed → Archived
- **Transitions**: Triggered by actions like `submit()`, `approve()`, `dispense()`
- **Rationale**: Ensures predictable behavior and supports exception handling.

---

### 6. Activity Diagram (Swimlane)

**Purpose**: Visualizes workflows and actor responsibilities.

**Explanation**:
- **Process**: “Dispense Medication”
- **Swimlanes**: Patient, Provider, Pharmacist
- **Activities**: Request → Approve → Dispense → Confirm
- **Rationale**: Highlights role-based responsibilities and parallel flows.

---

### 7. Component Diagram

**Purpose**: Depicts high-level system architecture and dependencies.

**Explanation**:
- **Components**: UI Layer, Service Layer, Database, External APIs
- **Dependencies**: UI → Service → DB/API
- **Rationale**: Supports modularity and aligns with microservices architecture.

---

### 8. Cloud Deployment Diagram

**Purpose**: Shows how system components are deployed on the cloud.

**Explanation**:
- **Platform**: AWS
- **Services**: EC2 (App Server), RDS (Database), S3 (Storage), Lambda (Event Handling)
- **Security**: IAM roles, TLS, OAuth2
- **Rationale**: Ensures scalability, security, and fault tolerance.

---

### 9. Skeleton Classes & Tables

**Purpose**: Provides basic class outlines and database schema.

**Explanation**:
- **Classes**: `Patient`, `Appointment`, `Prescription`
- **Tables**: `patients`, `appointments`, `prescriptions`
- **Rationale**: Bridges design with implementation and supports ORM mapping.

---

### 10. Design Patterns

**Purpose**: Enhances design quality through proven patterns.

**Explanation**:
- **GRASP**: Controller (`AppointmentController`), Information Expert (`Prescription`)
- **SOLID**: SRP in `MedicationService`, DIP via interfaces
- **GoF**: Factory (`PrescriptionFactory`), Observer (`MedicationLog`), Strategy (`InsuranceValidator`)
- **Microservices**: Stateless services, API Gateway, Event-driven communication
- **Rationale**: Promotes scalability, maintainability, and testability

---

## Design Principles & Patterns

- **GRASP**: Controller, Information Expert, Low Coupling
- **SOLID**: SRP in `PrescriptionController`, DIP via interfaces
- **GoF**: Factory (`PrescriptionFactory`), Observer (`MedicationLog`), Strategy (`InsuranceValidator`)
- **Microservices**: API Gateway, Event-Driven, Service Discovery

---

## Cloud Architecture

- **Platform**: AWS
- **Services**: EC2, RDS (MySQL), S3, Lambda, IAM
- **IaC**: Terraform scripts for provisioning
- **Security**: OAuth2, TLS, IAM roles, audit logging

---

## Repository Structure

```
├── 📁 images/           # UML diagrams and architecture visuals
├── 📁 scripts/          # Dockerfile, Terraform, SQL schema
├── 📁 powerpoint/       # Presentation slides
├── 📁 word/             # Written report and rationale
├── 📄 README.md         # Project summary and design explanation
```
---

## Reference Projects

- https://github.com/aws-samples  
- https://github.com/Azure-Samples  
- https://github.com/aws-samples/amazon-bedrock-kendra-lex-chatbot  
- https://github.com/aws-samples/generative-ai-amazon-bedrock-langchain-agent-example  
- https://github.com/aws-samples/aws-refarch-wordpress  

---

## Reference Blogs

- https://aws.amazon.com/blogs/machine-learning/deploy-generative-ai-self-service-question-answering-using-the-qnabot-on-aws-solution-powered-by-amazon-lex-with-amazon-kendra-and-amazon-bedrock/  
- https://aws.amazon.com/blogs/machine-learning/build-generative-ai-agents-with-amazon-bedrock-amazon-dynamodb-amazon-kendra-amazon-lex-and-langchain/  

---

## Additional Resources

- https://www.geeksforgeeks.org/system-design/patterns-and-frameworks-in-ooad/  
- https://www2.cs.uh.edu/~svenkat/SoftwareDesign/slides/ObjectOrientedDesignPrinciples.pdf  
- https://www.geeksforgeeks.org/system-design/what-is-domain-class-in-uml/  
- https://www.cerritos.edu/dwhitney/SitePages/CIS201/Lectures/IM-7ed-Chapter04.pdf  
- https://en.wikipedia.org/wiki/Domain_model  
- https://indico.mpp.mpg.de/event/2835/contributions/5798/attachments/4721/5217/patterns.pdf  
- https://docs.aws.amazon.com/whitepapers/latest/microservices-on-aws/simple-microservices-architecture-on-aws.html  
- https://learn.microsoft.com/en-us/azure/architecture/guide/architecture-styles/microservices  
- https://cloud.google.com/blog/topics/developers-practitioners/microservices-architecture-google-cloud  
- https://github.com/donnemartin/system-design-primer  
- https://www.designgurus.io/blog/system-design-primer-the-ultimate-guide  
- https://github.com/tssovi/grokking-the-object-oriented-design-interview/tree/master/object-oriented-design-case-studies  

---

## Author

Created by Chastidy Joanem
GitHub: @chazdj0510(https://github.com/chazdj0510)
