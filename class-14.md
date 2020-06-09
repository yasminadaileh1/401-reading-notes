# Access Control (ACL)

**Access Controls** are the selective **restriction of resources**. Access Controls are implemented everywhere in computer systems. UNIX files have **read**, **write**, and **execute permissions** assigned to owners, and **groups**. APIs restrict access to internal and external developers differently.

In **RESTful** APIs, it is important to limit access to clients based on **credentials**. This means a user A should not be able to delete a users B resource, unless B said that A is allowed to. Limiting what actions a user can preform on a given resource is called **Access Control**. A user can be given a token at `signup` and `login`, and that user can pass that token back to the server on requests with limited access controls. Once the server parses the **token**, it can determine if the user is authorized to preform the request.

**content management system** (CMS): it is a `software application` or set of related `programs` that are used to create and **manage digital content**. 
And it might Allow :
1. admin users to create categories, content
1. editor users to create, edit and delete existing content
1. guest users to access (read) content
1. user users (logged in users) to access (read) content and apply a thumbs-up/down to content, but not change the actual content

### Back End (API Layer) can do:

1. Manage the login cycle with the front-end application
2. Maintain the User’s database
3. Maintain roles for each user
4. Authenticate users (basic and bearer)
5. Create, manage, and apply Role Based Access Controls
6. Maintain and reference their capabilities, based on their role
7. Restrict access to features (like routes) based on capabilities
 - Express Middleware could be used to restrict access to routes
 - Mongoose Middleware/Hooks could be use to restrict access to business logic

### Front End (Client Layer) can do:

1. Initiate the login process
2. Store login tokens as cookies
3. Manage login state, capabilities
4. Control physical & visual access (hide/show/alter) to components based on RBAC rules
5. Alter behaviors based on RBAC rules