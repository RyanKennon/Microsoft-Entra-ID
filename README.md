# Microsoft Entra ID – User & Identity Management Fundamentals

This project requires an active Azure subscription and an Azure AD P2 license.

---

### 1) Create User Account

1. In the your **Microsoft 365 admin account** expand the **Entra ID** dropdown
2. Under **Users** select **All Users** then **New User** and **Create New User**

# Capture 1
   
3. Create the user using the following information
  - **User Principle Name:** MichaelS
  - **Display Name:** Michael Scott
4. Enable **Auto-generate password** then select **Review and Create** then **Create** the user

# Capture 2

---

### 2) Assign User the Application Admin Role

1. On the **Users** page select **Michael Scott**
2. Choose **Assigned Roles** and select **Add Assignments**

# Capture 3

3. Select **Application Administrator** role then select **Next**

# Capture 4

5. For the **Assignment Type** choose the **Active** value then enter a justification and press **Assign**

# Capture 5

5. Hit the **Refresh** button to confirm the assignment was a success

# Capture 6

---

### 3) Remove Assigned Role From a User

1. Select the **Roles and Administrators** tab
2. In the **All Roles** select the **Application Administrator** role from the list

# Capture 7

3. For the user named **Michael Scott** select the **Remove** option and select **Yes**

# Capture 8

4. *Refresh** and confirm that **Michael Scott** is no longer listed as having the **Application Administrator** role

---

### 4) Bulk Import Users using a CSV

1. Select the **Users** tab and make sure **All Users** is open
2. Select the **Bulk Operations** dropdown then select **Bulk Create**
3. Where it says **Upload Your CSV File** upload this file and press **Submit**

# Capture 10 also need to make the file of all The Office characters

4. **Refresh** the page to confirm users were created.

---

### 5) Delete and Restore a User

1. Check the box next to **Ryan Howard** then press **Delete**

# Capture 11

2. Select **Deleted Users** on the **Navigation Menu**
3. Check the box next to **Ryan Howard** then press **Restore Users**

# Capture 12

4. Navigate back to the **All Users** tab and confirm **Ryan Howard** appears

---

### 6) Update a Users Usage Location

1. Select **Properties** then scroll down until you find **Usage Location**
2. Make sure the location says **United States**

# Capture 13

3. If it doesn't say **United States** press the **Pencil** next to where it says **Settings**
4. In the **Usage Location** drop down select **United States** then **Save**

# Capture 14

---

### 7) Add a Microsoft Entra ID P2 License to a User Account

1. Open the **Microsoft 365 Admin Center** and log in as your **Administrator Account**
2. On the **Navigation Menu** open the **Billing** section then select **Licenses**
3. Select the **Microsoft Entra ID P2** License

# Capture 16

4. Choose **Assign Licenses**
5. Search **Michael Scott** and select **Assign Licenses** at the bottom of the page

# Capture 17

---

### 8) Confirm User Has an Active License

1. Go back to the **Microsoft Entra Admin Center**
2. On the **All Users** page select **Michael Scott**
3. Select the **Licenses** menu item on the left and ensure that it says **AAD_PREMIUM_P2**

# Capture 15

---

### 9) Create Custom Subdomains

1. Open the **Domain Names** tab then select **Add Custom Domains**

# Capture 18

2. In the **Custom Domain** field create a custom subdomain for the sales department using the following format then select **Add Domain**
   `Sales.LabTenantName.onmicrosoft.com`

# Navigation 2

3. Open the **Microsoft 365 Admin Center** link
4. Once there open the **Domains** tab and select **Add Domain**

# Capture 19

5. In the **Domain Name** field create a custom subdomain for the sales department using the following format then select **Use This Domain**
   `Sales.LabTenantName.onmicrosoft.com`

# Capture 20

6. Go back to the **Microsoft Entra Admin Center** and select **Refresh** on the **Custom Domain Names** page to find the new domain

# Capture 21

---

### 10) Changing the Tenant Display Name

1. Open the **Overview** menu and select **Properties**
2. Change the **Name** and the **Technical Contact to the following then select **Save**
  `**Name:** Dunder-Mifflin
   **Technical Contact:** *Your Global Admin Account*`

# Capture 22

---

### 11) Setting Your Privacy Information

1. In the **Overview** menu in the **Properties** tab
2. Enter the email address for **Michael Scott** as the **Global Privacy Contact**
3. Enter this **[URL](https://github.com/RyanKennon/Microsoft-Entra-ID/blob/main/Privacy%20Statement%20Sample.pdf)** into the **Privacy Statement URL** text box then **Save**

# Capture 23

---

### 12) Check Your Privacy Statement

1. Select your **Username** in the top right of the screen then select **View Account**

# Capture 24

2. Select the **Settings & Privacy** menu then select **Privacy**
3. Under **Organizational Privacy Statement** select **View**

# Capture 25

4. Confirm the **Privacy Statement** pops up

---

### 13) Create a Security Group

1. In the **Groups** menu select the **All Groups** tab then select **New Group**

# Capture 26

2. Create a group using the following information:
   `**Group Type:** Security
   **Group Name:** sg-dm
   **Membership Type:** Assigned
   **Owners:** *Assign your administrator account as the group owner*
   **Members:** Dwight Schrute`

# Capture 27

3. Select **Create** at the bottom of the page
4. Verify the group is in the **All Groups** list

# Capture 28

---

### 14) Create a Microsoft 365 group in Microsoft Entra ID

1. On the **All Groups** page select **New Group**
2. Create a group with the following information:
   `**Group Type:** Microsoft 365
   **Group Name:** Sales Representatives
   **Membership Type:** Assigned
   **Owners:** *Assign your administrator account as the group owner*
   **Members:** Jim Halpert, Dwight Schrute, Andy Bernard, Stanley Hudson, Phyllis Lapin`

# Capture 29

3. Verify the group is in the **All Groups** list

# Capture 30

---

### 15) Creating a Dynamic Group with All Users as Members

1. On the **All Groups** page select **New Group**
2. Enter the following information but do not create the group:
   `**Group Type:** Security
   **Group Name:** DynamicGroup
   **Membership Type:** Dynamic User
   **Owners:** *Assign your administrator account as the group owner*`
3. Where is says **Dynamic Users Members** select **Add Dynamic Query**

# Capture 31

4. Above the **Rule Syntax** box select **Edit**
5. Enter the following expression in the **Rule Syntax** box then press **Ok**:
   `user.objectId -ne null`

# Capture 32

6. Select **Save** then **Create**
7. Verify the group is in the **All Groups** list

# Capture 33

8. Open the **DynamicGroup** then select **Members**
9. Review the members

---

### 16) Enable Guest Users to Perform Self Serice Sign-Up

1. On the **Users** menu navigate to **User Settings** and select **Manage External Collaboration Settings**

# Capture 34

2. For the option labeled **Enable Guest Self-Service Sign Up Via User Flows** mark **Yes**
3. **Save** at the top of the screen

# Capture 35

---

### 17) Configure External Collaboration Settings

1. Open the **External Identities** menu then select **All Identity Providers**
2. Find where it says **Email One-Time Passcode** then select **Configured**

# Capture 36

3. For **Email One-Time Passcode for Guests** select **Yes** then **Save**

# Capture 37

4. Select the **External Collaboration Settings**
5. Find where it says **Guest User Access** select **Guest User Access is Restricted to Properties and Memberships of Their Own Directory Objects (Most Rrestrictive)**

# Capture 38

6. Find the **Guest Invite Settings** select **Member Users and Users Assigned to Specific Admin Roles Can Invite Guest Users Including Guests with Member Permissions**

# Capture 39

7. **Save** your changes

---

### 18) Add a Guest User to the Directory

1. Open the **Users** menu, on the **All Users** page select **New User** then **Invite External User**
2. Enter the email **externaluser@email.com** for the **Email**

# Capture 40

3. Select the **Properties** tab
4. For the **User Type** make sure it is filled in as **Guest**

# Capture 41

5. Select **Review and Invite** then **Invite**

---

### 19) Bulk Invite Guest Users

1. On the **All Users** page select **Bulk Operations** then **Bulk Invite**
2. Where it says **Download CSV Template** select download and follow along with the template to create guest users
3. Enter this file into where it says **Upload Your CSV File** then **Submit**

# Capture 42

4. Verify the guest users appear in the **All Users** page

---

### 20) Configure Google to be Used as an Identity Provider

1. Go to the [**Google APIs Site**](https://console.cloud.google.com/projectselector2/apis/dashboard?pli=1&supportedpurview=project&authuser=1) and sign in with your **Google Account**
2. Click **Select a Project** then **New Project** and select **create**
3. Open the project by clicking **Select Project** on the **Notifications** page

# Capture 43

4. On the left side of the screen select the **OAuth Consent Screen** then select **Get Started**
5. Enter the following information to create the project
   `**App Information**
   **App Name:** Microsoft Entra ID
   **User Support Email:** Select email name form dropdown menu
   **Audience**
   **Internal/External:** External
   **Contact Information:** Use User Support Email address
   **Finish**
   **Mark the agreement checkbox**`
6. Select the **Create OAuth Client** button
7. For the **Application Type** choose **Web Application**
8. Under **Authorized JavaScript Origins** select **Add URI** then add `https://microsoftonline.com` as the URI

# Capture 44

9. Under **Authorized Redirect URIs** select **Add URI**
    `**First URI:** https://login.microsoftonline.com
   **Second URI:** https://login.microsoftonline.com/te/**tenant ID**/oauth2/authresp
   **Third URI:** https://login.microsoftonline.com/te/**tenant name**.onmicrosoft.com/oauth2/authresp`

# Capture 45

10. Once everything is entered select **Create**

---

### 21) Add a Test User in Google

1. On the **Google API Site** select the **Audience** tab on the left side of the screen
2. Scroll down to **Test Users** then select **Add Users**

# Capture 46

3. Enter **The Email Account Your Using for This Lab** then select **Save**

---

### 22) Add Authorized Domain to Branding

1. On the **Google API Site** select the **Branding** tab on the left side of the screen
2. Find the **Authorized Domains** section at the bottom of the page then select **Add Domain** and add the domain `microsoftonline.com`
3. In the **Developer Contact Information** make sure the email address your using in this lab appears in the box
4. Select **Save**

# Capture 47 block out my email address

---

### 23) Find Google Client ID and Client Secret

1. On the **Google API Site** select the **Clients** tab on the left side of the screen
2. On the right side of the screen under **Additional Information** the **Client ID** appears
3. Below that under the **Client Secrets** the **Client Secret** appears

# Capture 49 block out the client id and client secret

---

### 24) Configure Microsoft Entra ID for Google Federation

1. On the **Microsoft Entra ID Admin Center** open the **External Identities** tab
2. Open the **All Identity Providers** page then select **Configure** next to **Google**

# Capture 48

3. Enter the **Client ID** and the **Client Secret** then select **Save**
4. Verify that on the **External Identities** page it says **Configured** next to **Google**

# Capture 50

---

### 25) Invite the Test User Account

1. Open the **All Users** page in **Microsoft Entra ID Admin Center**
2. Select **New User** then **Invite External User**

# Capture 51

3. Enter the email account that you were using while entering information on the Google API site
4. Select **Review and Invite** then **Invite**

---

### 26) Accept the Invitation and Login

1. Open the email account that you have been using during these previous steps
2. Open the **Microsoft Invitation on Behalf of** email then select **Accept Invitation**

# Capture 52

3. After logging in it will take you to the **Apps Dashboard** with the correct user information on the left side of the screen

# Navigation 6

---
