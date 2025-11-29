Step 1: Review Inputs
Reviewing the inputs, the ones found to be most relevant to this iteration are the following:
All usecases are relevant for this iteration, each one defining a new ability for different stakeholder access levels
QA4: Accessing usser information only allowed for a certain access level
CON6: Secure user role access must be achieved for the product to fulfill this constraint
CRN8: Relates to this iteration pertaining to the application of the roles and permissions

Step 2: Establish iteration goal by selecting drivers
The goal of this iteration is to design the user and user permissions service, maintaining its purpose and responsibilities. This is the beginning of the decomposition of specific sections of the system, and will be focusing on QA4, CON6, CRN8, and the discsernment of different roles from the UCs

Step 3: Choose one or more elements of the system to decompose
For this iteration, the User and User Permissions Service is selected for decomposition. Since user authentication, role management, and permission handling directly affect system security, access control, and overall interaction flow, decomposing this subsystem early provides a stable foundation for later iterations. Additionally, refining this component supports the broader architectural development of the AIDAP product by clarifying how users interact with system services, how permissions shape system behavior, and how access policies integrate with the conversational interface.

Step 4: Choose one or more design concepts that satisfy the inputs considered in this iteration
The strategy behavioural pattern was chosen for this portion of the design. The strategy pattern lets each user role have its own permission behaviour, attaching itself to the user object when it is instantiated through the UserFactory class. The user object will delegate all permission checks to the strategy that was attached, allowing different roles to be attached to different users.

Step 5: Instantiate architectural elements, allocate responsibilities and
define interfaces
<img width="709" height="509" alt="justanimg" src="https://github.com/user-attachments/assets/73bf8b0a-dec8-4e72-881f-39fcd5d919df" />
 
Step 6: Sketch views and record design decisions
<img width="795" height="810" alt="iteration3img" src="https://github.com/user-attachments/assets/a2f3c0a1-fc2d-457d-b515-942f40fce739" />
 
Step 7: Perform analysis of current design and review iteration goal and
design objectives
For this iteration, the User and User Permissions components are selected for decomposition. These elements directly relate to key drivers such as security, maintainability, and the need for flexible access control. Breaking them down now allows the project to establish a clear structure for how different user types interact with the system.

The decomposition of the User and User Permissions components has been successfully completed for this iteration. The system now has a clearer, well-defined structure for representing user roles and applying permission logic, aligning with the key drivers of security, maintainability, and access control. This work provides a solid foundation for future iterations by ensuring that user interactions and authorization rules are consistently and reliably supported within the AIDAP architecture.
