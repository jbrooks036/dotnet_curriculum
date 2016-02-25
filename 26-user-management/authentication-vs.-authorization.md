
# User Management

In MVC 5, **Registration**, **Login**, and **Change Password** are already handled by .NET framework  
* `Account` = basic login stuff  
* `Manage` = changing user info, changing password
* Account and Manage Controllers are built-in
* Account and Manage ViewModels are also built-in  

### Authorization vs. Authentication

* The two concepts are completely orthogonal and independent, but both are central to security design  
* The failure to get either one correct opens up the avenue to compromise

**Authorization** refers to the rules that determine who is allowed to do what
* E.g. Adam may be authorized to create and delete databases, while Sam is only authorized to read them

**Authentication** is the process of ascertaining that someone really is who they claim to be
* E.g. Eve uses her password and thumbprint to authenticate her access to the data

In terms of web apps, very crudely speaking:
* authentication is when you check login credentials to see if you recognize a user as logged in, while
* authorization is when you look to your access control to determine whether the user is allowed to edit, delete or create content


#### For further information please visit <a href="http://en.wikipedia.org/wiki/AAA_protocol">this link</a></h3>
