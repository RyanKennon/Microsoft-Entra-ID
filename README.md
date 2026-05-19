<p align="center">
  <img width="474" height="279" alt="image" src="https://github.com/user-attachments/assets/584155f5-b617-48f1-bd7c-22029abedfb7" />
</p>

# Microsoft Entra ID: User & Identity Management Fundamentals


In this project, we explore the core identity and user management capabilities of Microsoft Entra ID. Starting with creating and assigning roles to individual users, we then move into bulk user management via CSV import, license assignment, and configuring tenant-level settings such as custom subdomains, display names, and privacy information. From there, we cover group management including security groups, Microsoft 365 groups, and dynamic groups. The project then shifts to external identity configuration, walking through guest user invitations, self-service sign-up, external collaboration settings, and setting up Google as a federated identity provider — wrapping up by accepting a guest invitation and verifying the end-to-end login experience.

---

## Environments and Technologies Used

- Microsoft Entra ID (formerly Azure Active Directory)
- Microsoft 365 Admin Center
- Microsoft Azure (Active Azure Subscription Required)
- Google Cloud Console (Google APIs)
- Microsoft Entra ID P2 License
- Privileged Identity Management (PIM)
- CSV Bulk Import

---

## Prerequisites

**This project requires an active Azure subscription and an Azure AD P2 license.**

---

## Table of Contents
- [1) Create User Account](#1-create-user-account)
- [2) Assign User the Application Admin Role](#2-assign-user-the-application-admin-role)
- [3) Remove Assigned Role From a User](#3-remove-assigned-role-from-a-user)
- [4) Bulk Import Users using a CSV](#4-bulk-import-users-using-a-csv)
- [5) Delete and Restore a User](#5-delete-and-restore-a-user)
- [6) Update a Users Usage Location](#6-update-a-users-usage-location)
- [7) Add a Microsoft Entra ID P2 License to a User Account](#7-add-a-microsoft-entra-id-p2-license-to-a-user-account)
- [8) Confirm User Has an Active License](#8-confirm-user-has-an-active-license)
- [9) Create Custom Subdomains](#9-create-custom-subdomains)
- [10) Changing the Tenant Display Name](#10-changing-the-tenant-display-name)
- [11) Setting Your Privacy Information](#11-setting-your-privacy-information)
- [12) Check Your Privacy Statement](#12-check-your-privacy-statement)
- [13) Create a Security Group](#13-create-a-security-group)
- [14) Create a Microsoft 365 group in Microsoft Entra ID](#14-create-a-microsoft-365-group-in-microsoft-entra-id)
- [15) Creating a Dynamic Group with All Users as Members](#15-creating-a-dynamic-group-with-all-users-as-members)
- [16) Enable Guest Users to Perform Self Serice Sign-Up](#16-enable-guest-users-to-perform-self-serice-sign-up)
- [17) Configure External Collaboration Settings](#17-configure-external-collaboration-settings)
- [18) Add a Guest User to the Directory](#18-add-a-guest-user-to-the-directory)
- [19) Bulk Invite Guest Users](#19-bulk-invite-guest-users)
- [20) Configure Google to be Used as an Identity Provider](#20-configure-google-to-be-used-as-an-identity-provider)
- [21) Add a Test User in Google](#21-add-a-test-user-in-google)
- [22) Add Authorized Domain to Branding](#22-add-authorized-domain-to-branding)
- [23) Find Google Client ID and Client Secret](#23-find-google-client-id-and-client-secret)
- [24) Configure Microsoft Entra ID for Google Federation](#24-configure-microsoft-entra-id-for-google-federation)
- [25) Invite the Test User Account](#25-invite-the-test-user-account)
- [26) Accept the Invitation and Login](#26-accept-the-invitation-and-login)

---

### 1) Create User Account

1. In the your **Microsoft 365 admin account** expand the **Entra ID** dropdown
2. Under **Users** select **All Users** then **New User** and **Create New User**

<p align="center">
  <img width="1001" height="570" alt="Capture1" src="https://github.com/user-attachments/assets/cdbd8dea-1115-4b4f-a0e2-34150ac2e6fc" />
</p>

3. Create the user using the following information
  - **User Principle Name:** MichaelS
  - **Display Name:** Michael Scott
4. Enable **Auto-generate password** then select **Review and Create** then **Create** the user

<p align="center">
  <img width="714" height="603" alt="Capture2" src="https://github.com/user-attachments/assets/8d1534f2-8c15-4f1c-9b35-f6f0a9c02cff" />
</p>

---

### 2) Assign User the Application Admin Role

1. On the **Users** page select **Michael Scott**
2. Choose **Assigned Roles** and select **Add Assignments**

<p align="center">
  <img width="891" height="621" alt="Capture3" src="https://github.com/user-attachments/assets/40a60986-3d26-4167-b169-4981c3cc7b72" />
</p>

3. Select **Application Administrator** role then select **Next**

<p align="center">
  <img width="637" height="492" alt="Capture4" src="https://github.com/user-attachments/assets/fcec9dc8-401c-4585-956a-a027f25a1d24" />
</p>

4. For the **Assignment Type** choose the **Active** value then enter a justification and press **Assign**

<p align="center">
  <img width="570" height="556" alt="Capture5" src="https://github.com/user-attachments/assets/3b7fcc32-e266-4881-a29d-3fa27de11ff2" />
</p>

5. Hit the **Refresh** button to confirm the assignment was a success

<p align="center">
  <img width="1089" height="258" alt="Capture6" src="https://github.com/user-attachments/assets/ff781a51-0d70-4e8f-a735-2022a6370f48" />
</p>

---

### 3) Remove Assigned Role From a User

1. Select the **Roles and Administrators** tab
2. In the **All Roles** select the **Application Administrator** role from the list

<p align="center">
  <img width="1527" height="733" alt="Capture7" src="https://github.com/user-attachments/assets/cc02116e-3b06-4146-92ed-c13578f55da0" />
</p>

3. For the user named **Michael Scott** select the **Remove** option and select **Yes**

<p align="center">
  <img width="1330" height="234" alt="Capture8" src="https://github.com/user-attachments/assets/6a74f2ed-c242-4482-9542-0c9ffb98d1c3" />
</p>

4. **Refresh** and confirm that **Michael Scott** is no longer listed as having the **Application Administrator** role

---

### 4) Bulk Import Users using a CSV

1. Select the **Users** tab and make sure **All Users** is open
2. Select the **Bulk Operations** dropdown then select **Bulk Create**
3. Where it says **Upload Your CSV File** upload [this file](https://raw.githubusercontent.com/RyanKennon/Microsoft-Entra-ID/refs/heads/main/TheOfficeCSV.csv) and press **Submit**

<p align="center">
  <img width="1592" height="533" alt="Capture10" src="https://github.com/user-attachments/assets/965ecfbb-f9b9-4b4e-8a67-cd197a17c4f3" />
</p>

4. **Refresh** the page to confirm users were created.

---

### 5) Delete and Restore a User

1. Check the box next to **Ryan Howard** then press **Delete**

<p align="center">
  <img width="858" height="700" alt="Capture11" src="https://github.com/user-attachments/assets/f7858bc6-2e11-46bb-9b52-c6e88b3721c7" />
</p>

2. Select **Deleted Users** on the **Navigation Menu**
3. Check the box next to **Ryan Howard** then press **Restore Users**

<p align="center">
  <img width="1080" height="466" alt="Capture12" src="https://github.com/user-attachments/assets/8e303c85-1326-4ff0-b0a7-57426fc7095b" />
</p>

4. Navigate back to the **All Users** tab and confirm **Ryan Howard** appears

---

### 6) Update a Users Usage Location

1. Select **Properties** then scroll down until you find **Usage Location**
2. Make sure the location says **United States**

<p align="center">
  <img width="307" height="148" alt="Capture13" src="https://github.com/user-attachments/assets/080107c1-e49e-4fd8-9f83-97fb01479b02" />
</p>

3. If it doesn't say **United States** press the **Pencil** next to where it says **Settings**
4. In the **Usage Location** drop down select **United States** then **Save**

<p align="center">
  <img width="839" height="276" alt="Capture14" src="https://github.com/user-attachments/assets/8cbfe2bf-1cfa-4fba-9292-846b62ef2623" />
</p>

---

### 7) Add a Microsoft Entra ID P2 License to a User Account

1. Open the **Microsoft 365 Admin Center** and log in as your **Administrator Account**
2. On the **Navigation Menu** open the **Billing** section then select **Licenses**
3. Select the **Microsoft Entra ID P2** License

<p align="center">
  <img width="1050" height="675" alt="Capture16" src="https://github.com/user-attachments/assets/deca2b70-a3c6-4d38-9e62-456f1ebfd54c" />
</p>

4. Choose **Assign Licenses**
5. Search **Michael Scott** and select **Assign Licenses** at the bottom of the page

<p align="center">
  <img width="565" height="846" alt="Capture17" src="https://github.com/user-attachments/assets/b57c113f-2bfa-459f-b480-b61ce8f7adbd" />
</p>

---

### 8) Confirm User Has an Active License

1. Go back to the **Microsoft Entra Admin Center**
2. On the **All Users** page select **Michael Scott**
3. Select the **Licenses** menu item on the left and ensure that it says **AAD_PREMIUM_P2**

<p align="center">
  <img width="1124" height="637" alt="Capture15" src="https://github.com/user-attachments/assets/cfccf57b-f933-40f5-963a-cdd510abc7e2" />
</p>

---

### 9) Create Custom Subdomains

1. Open the **Domain Names** tab then select **Add Custom Domains**

<p align="center">
  <img width="1182" height="540" alt="Capture18" src="https://github.com/user-attachments/assets/ee92ddd1-b3b5-4589-8197-e82aa273c5cd" />
</p>

2. In the **Custom Domain** field create a custom subdomain for the sales department using the following format then select **Add Domain**
   `Sales.LabTenantName.onmicrosoft.com`

<p align="center">
  <img width="300" height="219" alt="Navigation2" src="https://github.com/user-attachments/assets/09d88988-53a0-4e2b-88d8-8232550ae5e5" />
</p>

3. Open the **Microsoft 365 Admin Center** link
4. Once there open the **Domains** tab and select **Add Domain**

<p align="center">
  <img width="1091" height="530" alt="Capture19" src="https://github.com/user-attachments/assets/c50eadcf-b2a0-4251-88d2-069e333be99b" />
</p>

5. In the **Domain Name** field create a custom subdomain for the sales department using the following format then select **Use This Domain**
   `Sales.LabTenantName.onmicrosoft.com`

<p align="center">
  <img width="671" height="261" alt="Capture20" src="https://github.com/user-attachments/assets/a117d3ce-ad57-4139-9bc9-9b64f2206bbe" />
</p>

6. Go back to the **Microsoft Entra Admin Center** and select **Refresh** on the **Custom Domain Names** page to find the new domain

<p align="center">
  <img width="1168" height="445" alt="Capture21" src="https://github.com/user-attachments/assets/b2674730-0761-455f-b094-118dd24f223a" />
</p>

---

### 10) Changing the Tenant Display Name

1. Open the **Overview** menu and select **Properties**
2. Change the **Name** and the **Technical Contact** to the following then select **Save**
  `**Name:** Dunder-Mifflin
   **Technical Contact:** *Your Global Admin Account*`

<p align="center">
  <img width="1092" height="681" alt="Capture22" src="https://github.com/user-attachments/assets/6207c6f0-4a37-4261-a87d-bcfad0373159" />
</p>

---

### 11) Setting Your Privacy Information

1. In the **Overview** menu in the **Properties** tab
2. Enter the email address for **Michael Scott** as the **Global Privacy Contact**
3. Enter this **[URL](https://github.com/RyanKennon/Microsoft-Entra-ID/blob/main/Privacy%20Statement%20Sample.pdf)** into the **Privacy Statement URL** text box then **Save**

<p align="center">
  <img width="723" height="288" alt="Capture23" src="https://github.com/user-attachments/assets/61405bcf-b2c6-4224-a1ff-9a458af4b4b5" />
</p>

---

### 12) Check Your Privacy Statement

1. Select your **Username** in the top right of the screen then select **View Account**

<p align="center">
  <img width="320" height="207" alt="Capture24" src="https://github.com/user-attachments/assets/5c79f75a-f8a1-4363-9358-0da2689df78d" />
</p>

2. Select the **Settings & Privacy** menu then select **Privacy**
3. Under **Organizational Privacy Statement** select **View**

<p align="center">
  <img width="1372" height="727" alt="Capture25" src="https://github.com/user-attachments/assets/36f0a534-064c-4e01-890a-67074e550bf5" />
</p>

4. Confirm the **Privacy Statement** pops up

---

### 13) Create a Security Group

1. In the **Groups** menu select the **All Groups** tab then select **New Group**

<p align="center">
  <img width="976" height="452" alt="Capture26" src="https://github.com/user-attachments/assets/8ed2f07a-e7f2-4b7a-9ecb-15e0dfdfe94c" />
</p>

2. Create a group using the following information:
   `**Group Type:** Security
   **Group Name:** sg-dm
   **Membership Type:** Assigned
   **Owners:** *Assign your administrator account as the group owner*
   **Members:** Dwight Schrute`

<p align="center">
  <img width="703" height="464" alt="Capture27" src="https://github.com/user-attachments/assets/ad632834-62f2-4792-8072-8231c4638d0f" />
</p>

3. Select **Create** at the bottom of the page
4. Verify the group is in the **All Groups** list

<p align="center">
  <img width="1043" height="355" alt="Capture28" src="https://github.com/user-attachments/assets/54fb8a30-5ea3-45e4-8ec4-577d717ee9f3" />
</p>

---

### 14) Create a Microsoft 365 group in Microsoft Entra ID

1. On the **All Groups** page select **New Group**
2. Create a group with the following information:
   `**Group Type:** Microsoft 365
   **Group Name:** Sales Representatives
   **Membership Type:** Assigned
   **Owners:** *Assign your administrator account as the group owner*
   **Members:** Jim Halpert, Dwight Schrute, Andy Bernard, Stanley Hudson, Phyllis Lapin`

<p align="center">
  <img width="755" height="604" alt="Capture29" src="https://github.com/user-attachments/assets/1b6a316d-0a93-487c-880b-a441ca25d4a6" />
</p>

3. Verify the group is in the **All Groups** list

<p align="center">
  <img width="1059" height="459" alt="Capture30" src="https://github.com/user-attachments/assets/d6e80dc7-3ba6-440d-ba85-fb98bb748863" />
</p>

---

### 15) Creating a Dynamic Group with All Users as Members

1. On the **All Groups** page select **New Group**
2. Enter the following information but do not create the group:
   `**Group Type:** Security
   **Group Name:** DynamicGroup
   **Membership Type:** Dynamic User
   **Owners:** *Assign your administrator account as the group owner*`
3. Where is says **Dynamic Users Members** select **Add Dynamic Query**

<p align="center">
  <img width="742" height="581" alt="Capture31" src="https://github.com/user-attachments/assets/08dd63a2-9616-4e7d-904f-f8b92f440f91" />
</p>

4. Above the **Rule Syntax** box select **Edit**
5. Enter the following expression in the **Rule Syntax** box then press **Ok**:
   `user.objectId -ne null`

<p align="center">
  <img width="841" height="148" alt="Capture32" src="https://github.com/user-attachments/assets/9061148c-befa-41d9-a651-4a6efb88d513" />
</p>

6. Select **Save** then **Create**
7. Verify the group is in the **All Groups** list

<p align="center">
  <img width="1305" height="515" alt="Capture33" src="https://github.com/user-attachments/assets/95905673-5afe-45d9-b82e-9c5aab9958c2" />
</p>

8. Open the **DynamicGroup** then select **Members**
9. Review the members

---

### 16) Enable Guest Users to Perform Self Service Sign-Up

1. On the **Users** menu navigate to **User Settings** and select **Manage External Collaboration Settings**

<p align="center">
  <img width="854" height="670" alt="Capture34" src="https://github.com/user-attachments/assets/9bcaef76-807a-4025-adf2-8bcfa1ad9dbd" />
</p>

2. For the option labeled **Enable Guest Self-Service Sign Up Via User Flows** mark **Yes**
3. **Save** at the top of the screen

<p align="center">
  <img width="317" height="104" alt="Capture35" src="https://github.com/user-attachments/assets/d246f918-b19f-4bab-bbe9-fc5d09a6ca5f" />
</p>

---

### 17) Configure External Collaboration Settings

1. Open the **External Identities** menu then select **All Identity Providers**
2. Find where it says **Email One-Time Passcode** then select **Configured**

<p align="center">
  <img width="826" height="564" alt="Capture36" src="https://github.com/user-attachments/assets/8692d091-fabe-4636-acb3-29089a34b71d" />
</p>

3. For **Email One-Time Passcode for Guests** select **Yes** then **Save**

<p align="center">
  <img width="234" height="76" alt="Capture37" src="https://github.com/user-attachments/assets/1ab0ff6a-8b36-4653-906c-8bce43f8b247" />
</p>

4. Select the **External Collaboration Settings**
5. Find where it says **Guest User Access** select **Guest User Access is Restricted to Properties and Memberships of Their Own Directory Objects (Most Restrictive)**

<p align="center">
  <img width="704" height="171" alt="Capture38" src="https://github.com/user-attachments/assets/1da09bdc-8a74-4001-834a-8d93573cf8e7" />
</p>

6. Find the **Guest Invite Settings** select **Member Users and Users Assigned to Specific Admin Roles Can Invite Guest Users Including Guests with Member Permissions**

<p align="center">
  <img width="774" height="197" alt="Capture39" src="https://github.com/user-attachments/assets/966fe1aa-e03c-4e24-bb25-93e42a970bfd" />
</p>

7. **Save** your changes

---

### 18) Add a Guest User to the Directory

1. Open the **Users** menu, on the **All Users** page select **New User** then **Invite External User**
2. Enter the email `externaluser@email.com` for the **Email**

<p align="center">
  <img width="839" height="49" alt="Capture40" src="https://github.com/user-attachments/assets/d14ed54d-e4d4-4f55-a8c6-a63232afbb15" />
</p>

3. Select the **Properties** tab
4. For the **User Type** make sure it is filled in as **Guest**

<p align="center">
  <img width="830" height="30" alt="Capture41" src="https://github.com/user-attachments/assets/3f5f81dd-e3b9-42e9-be4f-675d5fbf5a7a" />
</p>

5. Select **Review and Invite** then **Invite**

---

### 19) Bulk Invite Guest Users

1. On the **All Users** page select **Bulk Operations** then **Bulk Invite**
2. Where it says **Download CSV Template** select download and follow along with the template to create guest users
3. Enter this file into where it says **Upload Your CSV File** then **Submit**

<p align="center">
  <img width="297" height="274" alt="Capture42" src="https://github.com/user-attachments/assets/8b828459-1a13-4c2c-95ff-871e654e2743" />
</p>

4. Verify the guest users appear in the **All Users** page

---

### 20) Configure Google to be Used as an Identity Provider

1. Go to the [**Google APIs Site**](https://console.cloud.google.com/projectselector2/apis/dashboard?pli=1&supportedpurview=project&authuser=1) and sign in with your **Google Account**
2. Click **Select a Project** then **New Project** and select **create**
3. Open the project by clicking **Select Project** on the **Notifications** page

<p align="center">
  <img width="402" height="176" alt="Capture43" src="https://github.com/user-attachments/assets/4100de45-1ff2-447d-a879-7e926b7b5b91" />
</p>

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

<p align="center">
  <img width="580" height="531" alt="Capture44" src="https://github.com/user-attachments/assets/7a04389f-d9b3-42da-a572-2aedca770788" />
</p>

9. Under **Authorized Redirect URIs** select **Add URI**
    `**First URI:** https://login.microsoftonline.com
   **Second URI:** https://login.microsoftonline.com/te/**tenant ID**/oauth2/authresp
   **Third URI:** https://login.microsoftonline.com/te/**tenant name**.onmicrosoft.com/oauth2/authresp`

<p align="center">
  <img width="503" height="289" alt="Capture45" src="https://github.com/user-attachments/assets/9ecfcdbd-bbfc-4160-af1a-1dea8f6e9b5c" />
</p>

10. Once everything is entered select **Create**

---

### 21) Add a Test User in Google

1. On the **Google API Site** select the **Audience** tab on the left side of the screen
2. Scroll down to **Test Users** then select **Add Users**

<p align="center">
  <img width="158" height="106" alt="Capture46" src="https://github.com/user-attachments/assets/22742c20-318f-476b-82d8-760b128feea1" />
</p>

3. Enter **The Email Account Your Using for This Lab** then select **Save**

---

### 22) Add Authorized Domain to Branding

1. On the **Google API Site** select the **Branding** tab on the left side of the screen
2. Find the **Authorized Domains** section at the bottom of the page then select **Add Domain** and add the domain `microsoftonline.com`
3. In the **Developer Contact Information** make sure the email address your using in this lab appears in the box
4. Select **Save**

<p align="center">
  <img width="542" height="341" alt="Untitled Diagram-Page-47 drawio" src="https://github.com/user-attachments/assets/70b784e3-38d3-4d0f-abf7-82eec5155948" />
</p>

---

### 23) Find Google Client ID and Client Secret

1. On the **Google API Site** select the **Clients** tab on the left side of the screen
2. On the right side of the screen under **Additional Information** the **Client ID** appears
3. Below that under the **Client Secrets** the **Client Secret** appears

<p align="center">
  <img width="813" height="585" alt="Untitled Diagram-Page-49 drawio" src="https://github.com/user-attachments/assets/5a45b3e1-688d-4227-91a4-7b605b692d4d" />
</p>

---

### 24) Configure Microsoft Entra ID for Google Federation

1. On the **Microsoft Entra ID Admin Center** open the **External Identities** tab
2. Open the **All Identity Providers** page then select **Configure** next to **Google**

<p align="center">
  <img width="757" height="493" alt="Capture48" src="https://github.com/user-attachments/assets/97d60da4-bf38-4508-a136-bd9ee3cee451" />
</p>

3. Enter the **Client ID** and the **Client Secret** then select **Save**
4. Verify that on the **External Identities** page it says **Configured** next to **Google**

<p align="center">
  <img width="493" height="314" alt="Capture50" src="https://github.com/user-attachments/assets/7a495df2-f68e-418f-b054-71b6db6804f3" />
</p>

---

### 25) Invite the Test User Account

1. Open the **All Users** page in **Microsoft Entra ID Admin Center**
2. Select **New User** then **Invite External User**

<p align="center">
  <img width="277" height="181" alt="Capture51" src="https://github.com/user-attachments/assets/df7f5899-4f1d-44b4-b028-2836a9f35a01" />
</p>

3. Enter the email account that you were using while entering information on the Google API site
4. Select **Review and Invite** then **Invite**

---

### 26) Accept the Invitation and Login

1. Open the email account that you have been using during these previous steps
2. Open the **Microsoft Invitation on Behalf of** email then select **Accept Invitation**

<p align="center">
  <img width="703" height="325" alt="Capture52" src="https://github.com/user-attachments/assets/94585805-58e8-4345-9af0-d09498c531c3" />
</p>

3. After logging in it will take you to the **Apps Dashboard** with the correct user information on the left side of the screen

<p align="center">
  <img width="1383" height="403" alt="Navigation6" src="https://github.com/user-attachments/assets/ef7713b7-2638-4538-88c0-a217ab85ee9d" />
</p>

---
