# blazorAuthenticationAndAuthorization
Basic app with ASP.NET Core authentication, authorization and management of users with page of product where we can see role and permission based authorization.

In blazor app, we will implement a complete Permission-Based Authorization in ASP.NET Core using .NET 6 and Microsoft Identity package. We built the entire system from scratch to control the level of authorization on the basis of User Roles. The SuperAdmin will be able to control the permission and add new roles as well. This is a neat way to secure your ASP.NET Core Web Applications from users with limited permissions. 

What’s Role-Based Authorization?
Role-Based Authorization in ASP.NET Core is a way to restrict/allow users to access specific resources in the application. The [Authorize] attribute when declared in the Controller or any action methods, restricts users bases on his/her role settings.
For instance, the Delete method is accessible only to users who have the Role ‘SuperAdmin’ assigned to them, and so on. You are getting the point, yeah?

When run the application , with SuperAdmin credentials. Navigate to /products. As excepted, the superadmin has access to all the features of the Product module

You can also supply different content for display if the user isn't authorized:
<AuthorizeView>
    <Authorized>
        <h1>Hello, @context.User.Identity.Name!</h1>
        <p>You can only see this content if you're authorized.</p>
        <button @onclick="SecureMethod">Authorized Only Button</button>
    </Authorized>
    <NotAuthorized>
        <h1>Authentication Failure!</h1>
        <p>You're not signed in.</p>
    </NotAuthorized>
</AuthorizeView>

Features :
- User List – To display all the registered users
- Roles List – To Display / Add Roles
- User – Roles Management – To assign various roles to each user.
- Default Seeding – Seed default roles and users on application startup
- Permission Management – Role-based permissions controller
- Dummy Products Management – To Create / Read / Modify Products (Note that this will not be implemented completely). The aim is to dynamically restrict users based on their roles from various actions on the Product Entity. For instance, only Admins can modify the data.
