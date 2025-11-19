1. Review Inputs
- Why are we performing this design
  The goal of this software is to provide a system that provides a conversational AI program for students, faculty, and administrators to interact with to receive personal or course wide information, such as course schedules, deadlines, announcements, and academic analytics. The AI assistant will integrate with external university systems to deliver on topic answers. The institutions data will be available to the system to ensure accurate responses.

- Primary functional requirements
  Reviewing the functional requirements, the ones determined to be the primary drivers of the system composition and most relevant to this iteration are
  UC1: This is a major function for the system, this drives the conversational aspect of the system
  UC2: This will require a notification interface for the system between many users
  UC7: This will require aggregation of information from large amounts of student data
  UC9: This will require a permission interface for different users, requiring further security
  UC11, UC15, UC17: This will require system-wide monitoring and connection to a notification interface, as well as being aggregated and displayable
  UC12: High-level permission users should be able to change integrations for the system
  UC16: System should include continuous deployment pipes for zero downtime update deployment
  UC18: System AI models and APIs should be configurable
  UC19: New external data should be implementable as well as new AI services
  UC20: System should be able to backup information and restore user information
  UC22: Intervals of of system synchronization should be configurable

- Prioritized quality attributes
  Quality attributes that have been found to impact the systems design are the following
  QA2: This requires further personal and scalable storage for individual users to support user specific responses
  QA3: The system must use SSO security for its user authentication implementation
  QA5: The system must be accesible on multiple types of devices, impacting the design of the system to recognize and cater for several devices
  QA8: This limits the design, as the system  must ensure compliancy with institutional security and privacy regulations throughout the system architecture
  QA10: The system msut be able to handle up to 5000 users concurrently without any performance issues, so the design must be able to handle this scalability
  QA11: Logging performance metrics must take place during system monitoring for later view
  QA12: Another limitation for the design of the system is that it must use standard APIs to ensure interoperability
  QA13: Any failures in the data source should be handled by the system, gracefully, and restore/continue operation
  QA14: Data integrity should be applied in the design as well as consistendy of the data across all of the system

- Constraints that constrain the design
  Constraints on the system that will affect the design, which may follow the same use case or quality attributes listed before, during this iteration are found to be
  CON1: The design must be implemented so that the system is deployed as a cloud native service
  CON2: The system must be able to handle up to 5000 concurrent users, it must ensure scalability for large amounts users so that there is a 2 second or less response time
  CON3: The design must keep in mind that the system must be online and available 99.5% of the month
  CON4: The design must be able to grab university data at cheangeable intervals to stay up to date, and it must be consistent across all systems
  CON5: Secure backup and restoration of user data must be possible for any users without issues
  CON6: The system design must use single sign on authentication and use institutional security and privacy regulations
  CON7: Standard interoperable APIs must be used in the system, limiting the design
  CON8: AI models and API keys must be configurable and cheangeable, so the system is not dependent on any
  CON13: The system must integrate with existing data sources, so the design must follow that before or at deployment it will have to pull information
  CON14: The system must support voice and text communication for the chatbot, so the design must include this accessibility constraint

2. Establish iteration goal
  The goal of the first iteration is to establish the system’s architectural foundation by identifying major interfaces, key quality attributes, essential use cases, and system constraints. This iteration produces the initial module decomposition and selects an architectural pattern to guide further design and development.

3. Choose one or more elements to decompose
  The main AIDAP application layer will be decomposed as it is the main system, which is being driven by the prioritized inputs listed in step 1.

4. Choose one or more design concepts that satisfy the inputs
  This system is comprised of multiple complex subsystems that all work together to fulfill a multitude of services for the user; they will need to be accessible through one interface for the user. Additionally, the system must have multiple interchangeable parts, such as CON8. Given this, it seems appropriate to begin with the Facade design pattern. The Facade pattern provides a single interface that encapsulate a set of interfaces from the subsystem, allowing for a single high-level interface that the user will interact with. The chatbot will be able to access all of these subsystems without the user ever being exposed to the internal structure of the system.

5. Instantiate architectural elements, allocate responsbilities, and define interfaces
User and user permissions service: 
  Responsible for managing user roles and access levels. This element ensures security and system integrity by enforcing proper authorization.
User authentication service: 
  Authenticating users before they are allowed to access any user specific data is in the best interest of stakeholders to hold to privacy concerns. The SSO authentication requirement will need to be applied for this element of the system.
Notifications service: 
  Provides alerts, schedule updates, and announcements. This supports stakeholder needs for timely and automated communication across devices.
System monitoring service:
  Constant system monitoring is used for logging, catching errors, and display for system maintainers.
Conversational service:
  Acts as the primary interface for students, faculty, and administrators. It routes user queries to the subsystems through the facade and returns responses.
AI model and API keys services:
  Handling these elements separately will prove to be beneficial as they will need to be easily updated and interchanged.
System failure and backup services:
  Handling failures as well as backing up information will require temporary information storage that will be updated at a certain interval.
Storage services:
  Provides storage for user-specific data, conversation context, system configurations, and university information. Ensures data integrity, availability, and scalability.
Data integration services:
  The purpose of this element is to pull the information from the university, at the changeable intervals, and synchronize the data between all systems.

6. Sketch views and record design decisions
![alt](project-group-42/images/asdadfas.PNG)

7. Perform analysis of current design and review iteration goal

