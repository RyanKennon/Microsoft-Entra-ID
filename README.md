# Microsoft-Entra-ID

This project requires an active Azure subscription and an Azure AD P2 license.

---

### 1) Create and Login to User Account

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

#Capture 4

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
1. On the **All Users** page select **Michael Scott**
2. Select the **Licenses** menu item on the left and ensure that it says **AAD_PREMIUM_P2**

# Capture 15

---

