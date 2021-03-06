---
title: SAP Concur App Center - Enabling and Disabling ‘Enterprise Application’ Solutions from the Concur App Center - Basic Configurations
layout: reference
---

## Enabling an App

This guide will provide the steps to enable an enterprise application. Enabling an Enterprise application does require administrative permissions. This guide will provide information on the permission required, adding the permissions for existing users and enabling the application.

Depending on the application, there are two methods of enabling the integration:

* Connect from the App Center. Note: Apps eligible for this type of connection utilize [OAuth 2.0 Company-Level Authorization](/api-reference/authentication/company-auth.html) and will have a “Connect” button displayed within the app listing.

![Connect from SAP Concur App Center Image](./guide-to-enabling-app-center-solutions-basic-connect-from-app-center.png)

* Username and password. All other apps utilize this connection method. Skip to instructions

## Connecting from the App Center

To enable an app the:

* Concur App Center must be enabled for your company
* User enabling the app must have the appropriate credentials

### Step 1: Confirm the App Center is enabled

Activating an Enterprise applications requires that your company has enabled the App Center. If the App Center is enabled, you will see the “App Center” tab when logged into Concur.

![SAP Concur App Center Enabled Image](./guide-to-enabling-app-center-solutions-basic-app-center-enabled.png)

If the App Center tab is unavailable, please log a ticket with the Concur Helpdesk.

### Step 2: Add or Check Permissions

Note: This step can either be completed by your own authorized Concur Administrator or you can log a ticket with the Concur Helpdesk to have this step completed for you by our support team.

If you do not have the appropriate permissions to activate the app, the “connect” button will be disabled as shown below. If the connect button is enabled, skip to step 3.

A user at your company with the appropriate permissions is required to activate the application. The instructions below provide information on adding the **Web Service Administrator** permissions for users that will be responsible for enabling and disabling enterprise applications.

![SAP Concur App Center Checking Permissions Image](./guide-to-enabling-app-center-solutions-basic-check-permissions.png)

#### How to assign the WS Admin User Permission in Concur Standard Edition:

* Click Administration and then Setup.
* Select Users from the menu on the left and click select the user to provide access.
* Permissions: Select "Can Administer" check box.

![Standard Enabling WS Admin Image](./guide-to-enabling-app-center-solutions-basic-enable-ws-admin-standard.png)

#### How to assign the WS Admin User Profile in Concur Professional Edition:

* Click into the Administration tab & then click into the Company Admin menu.
* Within the Administration area, click User Permissions.
* Find the user whom will activate the application and select Add to grant Web Services AdministratorPermission.

![Professional Enabling WS Admin Image](./guide-to-enabling-app-center-solutions-basic-enable-ws-admin-professional.png)

### Step 3: Enable the App

* The Concur administrator who has been named in the newly created WS Admin Profile logs into Concur with the new credentials. The client may then connect to the application from the App Center. The full client guide can be found here:

[App Center Administration Guide](https://www.concurtraining.com/customers/tech_pubs/Docs/ConcurPremier/UG_Shr/Shr_UG_AppCenterAdmin.pdf)

## Disabling an app from the App Center

The administrator can disconnect from an app at any time. As soon as the app is disconnected, the integration will be stopped.

### Step 1: Select the app listing in the App Center

* Applications can be found utilizing search or the categories filter.
* Enterprise integrations will be found in the “Enterprise Applications” section of the App Center.
* Click on the listing you would like to disconnect.

![Finding the app to disable image](./guide-to-enabling-app-center-solutions-basic-disabling-find.png)

### Step 2: Click Disconnect

* Within the app, administrators with the appropriate credentials will see the option to “disconnect”.

![Disconnecting an app image](./guide-to-enabling-app-center-solutions-basic-disabling-disconnect.png)

### Step 3: Confirm Disconnect

* Click “Yes” to confirm disconnect and complete the process.
* The “Connected” indication will no longer appear.

![Disconnecting confirmation image](./guide-to-enabling-app-center-solutions-basic-disabling-confirmation.png)

## Connecting using a username and password

### Step 1: Create & Transfer Credentials

> Note: This step can be completed by your own authorized Concur Administrator. It is important that this Web Services Admin User Profile is not the same as any actual user of the system. **If an actual user’s credentials are utilized for this purpose and they leave the company, the applications will no longer function**.

#### How to Create a WS Admin User Profile in Concur Standard Edition

* Click Administration and then Setup.
* Select Users from the menu on the left and click Create/Edit User.

![Creating a WS Admin user in standard image](./guide-to-enabling-app-center-solutions-basic-create-ws-admin-user-standard.png)

The new WS Admin User Profile in Concur Standard Edition should have the following attributes:

* **LoginID**: Include WSAdmin and the name of the application as the login id like this: WSAdmin-AppProviderName@YourCompanyDomain.com
* **First Name**: To easily identify this user profile later and also indicate who the authorized user was that enabled the application, use a combination of “WSAdmin” and the first name of the actual administrator who is authorizing the application. Example: WSADMIN_John
* **Last Name**: Insert the actual last name of the authorized administrator who will enable the application.
* **Password**: Create a unique and secure password for the user.
* **Permissions**:
  * Select "Can Administer" check box
  * Select...
    * "Can Submit Expense Reports",
    * "Can Book Travel" and/or
    * "Is Invoice AP User"
  * ...check boxes based on what type of data is needed for the application. The system will grant the relevant data access based on the roles that are assigned to this user. For example, if the app needs to access Travel data and the WS Admin User Profile does not have access to travel, the app will not access travel data.
* Click **Save** then securely send the **Login ID** and **Password** to your app provider.

#### How to Create a WS Admin User Profile in Concur Professional Edition:

* Click into the **Administration** tab & then click into the **Company Admin** menu.
* Click **Add New User**.

![Creating a WS Admin user in professional image](./guide-to-enabling-app-center-solutions-basic-create-ws-admin-user-professional.png)

The new WS Admin User Profile in Concur Professional Edition should have the following attributes:

* **LoginID**: Include WSAdmin and the name of the application as the login id like this: WSAdmin-AppProviderName@YourCompanyDomain.com
* **Password**: Create a unique and secure password for the user.
* **First Name**: To easily identify this user profile later and also indicate who the authorized user was that enabledthe application, use a combination of “WSAdmin” and the first name of the actual administrator who is authorizingthe application. Example: WSADMIN_John
* **Last Name**: Insert the actual last name of the authorized administrator who will enable the application.
* **Email Address**: use the actual email address of the authorized administrator

![WS Admin user permission in professional image](./guide-to-enabling-app-center-solutions-basic-enable-ws-admin-professional-user-permission.png)

Next, while still in the **Administration** area, click **User Permissions**

* Find the new WSAdmin User and select **Add** to grant **Web Services Administrator** permission.
* Ensure the WSAdmin profile also has the Expense User, Travel User, & Invoice User permissions or roles forapps integrating with Expense, Travel, and/or Invoice Services respectively. The system will grant the relevantdata access based on the roles that are assigned to this user. For example, if the app needs to access Traveldata and the WS Admin User Profile does not have access to book travel, the app will not be able to access thenecessary travel data.
* Once your new user profile has been created, transfer the Login Name and Password securely to the appprovider you are working with to create a secure data connection.

### Step 2: Enable the App

* The Concur administrator who has been named in the newly created WS Admin Profile logs into Concur with the new credentials.
* Then go to to **Administration > Company > Web Services > Enable Partner Application** and find the app.
* Click “Enable” and confirm the sharing of data.

![Enabling the application image](./guide-to-enabling-app-center-solutions-basic-enable-application.png)
