# [Nucle Cloud](https://nucle.cloud) Python Library

In order to make life easier for you, we have created a Nucle Cloud Python library that you can download and use.
This tool will allow you instant access to the Nucle Cloud API service in a Python environment, you will be writing less lines of code and save a lot of time.

 
## Instalation 

`pip install nucle.cloud`


## Content
First thing to do when using the library is to import it like bellow

`from Nucle.Cloud import *`

### User
- `UserModel Create(string projectId,string userName,string email,string password)`  
Create new user, return the user created.  
-  `LoginResult LoginWithEmail(string projectId,string email,string password )`  
Login a user with email.  
-  `LoginResult LoginWithUserName(string projectId,string userName,string password )`  
Login a user with userName.  
- `LoginResult RevokeToken(string userToken)`  
 Revoke a user token.  
- `SendResetPassword(string projectId,string email)`    
Send password reset email to email user.  
- `SendEmailConfirmation(string projectId,string email)`  
Send email confirmation to email user.  
- `UserModel Upgrade(string userToken,string userName,string email,string password)`  
Upgrade anonymous to real user, return upgraded user.  
- `UserModel GetById(string userToken,string userId)`  
Get user by id.  
- `string GetType(string userToken)`  
Get user type(REAL/ANONYMOUS/EXTERNALLOGIN).  
- `UserModel SetDisplayName(string userToken,string displayName)`  
Set user displayName.  
- `GeolocalizationModel GetGeolocalizationData(string userToken)`  
Get user geolocalization data.  
 - `UserModel Delete(string userToken)`  
Delete user, return deleted user.  
 

### Anonymous 

    

 - `LoginResult Login(string projectId,string deviceId)`  
Login anonymous user.  
 - `LoginResult Create(string projectId,string deviceId)`  
Create anonymous user.  
### External Login

   
- `UserModel Create(string projectId,string loginProvider,string providerKey,string providerDisplayName,string userEmail,string userName)`  
Create external login.   
- `LoginResult Login(string projectId,string loginProvider,string providerKey)`  
Login using external login.  
- `ExternalLoginModel Get(string userToken,string loginProvider,string providerKey)`  
Get external login.  
- `ExternalLoginModel Delete(string userToken,string loginProvider,pstring roviderKey)`  
Delete external login, return deleted external login.  

### Preset
 - `PresetModel GetById(string userToken,string presetId)`  
Get preset by id.  
 - `PresetModel GetByName(string userToken,string presetName)`  
Get preset by name.  

### Variable

- `VariableModel Update(string userToken,string presetId, string value)`  
 Update variable, if it does not exists this will create a new variable with the value provided.  
- `VariableModel Get(string userToken,string presetId)`  
 Get variable.   
- `VariableModel Delete(string userToken,string presetId)`  
Delete variable, return deleted variable.  
- `VariablesModel GetList(string userToken,string presetId,int skip,int take,orderType orderType, string searchValue)`  
 Get variables list.  
 *orderType:* (argument) enum  HighToLow=0, LowToHigh=1, Newest=2, Oldest=3.   
 *VariablesModel:* (return type )an object that contains a list of (VariableModel) and totalCount of variables without pagination applied. 
- `int Count(string userToken,string presetId,string searchValue)`  
Get the count of variables without pagination applied.  

## Example

Create a new user and print its id.   
Project Id to get from [Nucle.cloud](https://nucle.cloud) dashboard.   
```
from Nucle.Cloud import *

projectId ='b943b785-********************8ec173'
newUser = User.Create(projectId,'ross88@gmail.com', 'P@ssw0rd', 'ross')
print('New user id= '+newUser.id)
```

Login a user and print its token.  
Project Id to get from [Nucle.cloud](https://nucle.cloud) dashboard.   
```
from Nucle.Cloud import *

projectId ='b943b785-********************8ec173'
loginResult = User.LoginWithEmail(projectId,'ross88@gmail.com', 'P@ssw0rd')
print('User token= '+loginResult.userToken)
```

## GitHub 

You can always check the source code on [GitHub](https://github.com/nuclecloud/python), report any bugs or contribute if you would like.

