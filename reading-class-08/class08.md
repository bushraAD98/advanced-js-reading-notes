
# Role-Based Access Control :
## What is RBAC?
Role-based access control (RBAC), also known as role-based security, is a mechanism that restricts system access. It involves setting permissions and privileges to enable access to authorized users. Most large organizations use role-based access control to provide their employees with varying levels of access based on their roles and responsibilities. This protects sensitive data and ensures employees can only access information and perform actions they need to do their jobs.

For example, you may designate a user an administrator, a specialist, or an end-user, and limit access to specific resources or tasks. Inside an organization, different roles may be provided write access while others may only be provided viewing permissions.  

![img](./roles.png)
*****

## What are Examples of RBAC?
Through RBAC, you can control what end-users can do at board and granular levels. You can designate whether the user is an administrator or standard user, and align roles and permissions based on the user's position in the organization. 

The core principle is to allocate only enough access for an employee to do their job.

If the employee's job changes, you may need to add and/or remove them for their current role group.

By adding a user to a role group, the user has access to all the permissions of that group. If they are removed, access becomes restricted. Users can also be assigned temporary access to certain data or programs to complete a task and be removed after.

Common examples of RBAC include:

Software engineering role: Has access to GCP, AWS, and GitHub
Marketing role: Has access to HubSpot, Google Analytics, Facebook Ads, and Google Ads
Finance role: Has access to Xero and ADP
Human resources role: Has access to Lever and BambooHR  

****
 ## Benefits of RBAC :

- Create a systematic, repeatable assignment of permissions
- Audit user privileges and correct identified issues
Add, remove or change roles, as well as implement them across API calls

- Reduce potential errors when assigning user permissions

- Reduce administrative work and IT support by allowing you to quickly switch roles and permissions globally across operating systems, platforms, and applications

- Decrease the risk of data breaches and data leakage by restricting access to sensitive information

****
## What are Complementary Control Mechanisms to RBAC?

- Discretionary access control (DAC): DAC is an access control method where the owner of a protected system or resource sets policies defining who can access it. This can include physical or digital controls, and is less restrictive than other access control systems, as it offers individuals complete control over their own resources. The downside is it is inherently less secure, as associated programs will inherit security settings and the owner may accidentally grant access to the wrong end-user.

- Mandatory access control (MAC): MAC is an access control method where a central authority regulates access rights based on multiple levels of security. MAC assigns classifications to system resources, the security kernel, and the operating system. Only users or devices with the required information security clearance can access protected resources. This is a common access control method in government and military organizations. 

******

## What are the Alternatives to RBAC?

- Access control lists (ACL): An access control list (ACL) is a table that lists permissions attached to computing resources. It tells the operating system which users can access an object, and what actions they can carry out. There is an entry for each individual user, which is linked to attributes for each object (e.g. view, export, create). For most businesses, RBAC is superior to ACL in terms of security and administrative overhead. ACL is better suited for implementing controls for low-level data, while RBAC is better used as a company-wide access control system. 

- Attribute-based access control (ABAC): ABAC evaluates a set of rules and policies to manage access rights according to specific attributes, such as environmental, system, object, or user information. It applies boolean logic to grant or deny access to users based on the evaluation of atomic or set-valued attributes and the relationships between them. ABAC differs to RBAC as it doesn't rely on pre-defined roles, and ABAC provides more granularity. For example, an RBAC system may grant access to GitHub for all managers, while an ABAC policy would limit access to only software engineers.