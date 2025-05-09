<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Post-Install Configuration</h1>
This tutorial outlines the post-install configuration of the open-source help desk ticketing system osTicket.<br />



<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- OsTicket

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>Post-Install Configuration Objectives</h2>

- Configure roles
- Configure departments
- Configure teams
- Configure Agents(workers)
- Configure users(customers)
- Configure SLA
- Configure Help Topics 

<h2>Configuration Steps</h2>

<p>
<img width="477" alt="image" src="https://github.com/user-attachments/assets/87ab860e-ac80-412d-abef-65193e8d890f" />
</p>
<p>
 
First, we are going to navigate to the **Help Desk Staff login page** via  http://localhost/osTicket/scp/login.php 
 and log in as the admin.  

Once logged in we'll navigate to:  
**Admin Panel → Agents → Roles**  

Here, you can see different permissions that can be viewed, edited, or added for different roles.  
We are going to create a new role called **"Supreme Admin"** and grant this role **full access** to all permissions.

</p>
<br />

<p>
<img width="483" alt="image" src="https://github.com/user-attachments/assets/eeaadb44-e0b9-4372-a2a0-e5d766b3db78" />
</p>
<p>
 
Now, we are going to move on to **configuring the departments** in **osTicket**.  

Configuring departments in **osTicket** is about creating a structured and organized system for managing support requests. This ensures that tickets are assigned to the correct teams, performance is tracked, and users receive the right level of service. It's a crucial step in setting up **osTicket** to effectively handle your organization's support needs.

### Steps to Configure Departments:
1. Navigate to **Admin Panel** → **Agents** → **Departments**.
2. Click **Add Department**.
3. Enter **SysAdmins** as the department name.
4. Click **Save Changes**.

This process helps streamline ticket management and ensures that issues are handled efficiently by the right team.


</p>
<br />

<p>
<img width="451" alt="image" src="https://github.com/user-attachments/assets/442a90ca-91f9-48ae-b83e-c854f5fa3f65" />
</p>
<p>
 
Now, we are going to move on to **configuring teams** in **osTicket**.  

Configuring teams allows you to create **flexible groups of agents** who can collaborate on tickets, regardless of their departmental affiliation. This is useful for addressing specific issues or projects that may require expertise from multiple departments.

### Example:
We’ll create a team called **"Online Banking"** to handle issues related to online banking. This team can include agents from different departments who have the necessary expertise.

### Steps to Configure Teams:
1. Navigate to **Admin Panel** → **Agents** → **Teams**.
2. Click **Add New Team**.
3. Enter **"Online Banking"** as the team name.
4. Click **Create Team**.
5. We **won’t add any members/agents** to it yet.

This setup allows for greater flexibility in managing tickets across multiple departments.

</p>
<br />

<p>
<img width="464" alt="image" src="https://github.com/user-attachments/assets/eb312331-d029-4446-9381-9d07020e9f09" />
</p>
<p>
 
Now, we are going to make sure that a setting is **unchecked** so that end users can submit a ticket **regardless of whether they have a registered account or not**.  

### Steps to Adjust This Setting:
1. Navigate to **Admin Panel** → **Settings** → **User Settings**.
2. Locate the option that requires user registration to submit tickets.
3. **Ensure this setting is unchecked**.

Typically, in **real-world** scenarios, requiring registration is recommended, but for **lab purposes**, we will allow ticket submissions without registration.

### Benefits of Requiring Registered Users:
- **Security**: Prevents anonymous ticket submissions, reducing spam or malicious activity.
- **Accountability**: Tracks user activity and ensures responsible use of support resources.
- **User Tracking & History**: Maintains a history of user interactions for better troubleshooting and personalized support.
- **Communication**: Makes it easier to update users about ticket status or request additional information.
- **Reporting & Analytics**: Provides more accurate data to improve support processes.

For this lab, we are **not requiring registration**, but in a production environment, enabling this setting is highly beneficial.

</p>
<br />

<p>
<img width="696" alt="image" src="https://github.com/user-attachments/assets/bcde730b-2615-409f-aca8-a4c3c7cec805" />
</p>
<p>
Next, we're going to configure our Agents(workers) and set them up with username, password, and permissions. To get here we can navigate from Admin Panel -> Agents -> Add New
By creating agents in our lab, we're populating our support system with the staff members who would be using it in a real-world scenario, allowing us to fully explore and understand how osTicket functions in a multi-user environment.
</p>
<br />

<p>
<img width="712" alt="image" src="https://github.com/user-attachments/assets/4cc9660c-3912-4002-9cd8-ae7761b75760" />
</p>
<p>

Now, we are going to **set up our customers** in osTicket. This allows us to **test ticket submission** and the overall workflow between customers and support agents.

### Steps to Add a New Customer:
1. Navigate to **Agent Panel** → **Users** → **Add User**.
2. Fill in the required details (Name, Email, Phone, etc.).
3. Click **Add User** to finalize the setup.

### Why Set Up Customers?
- **Test Ticket Submission**: Ensures that users can submit tickets and receive support.
- **Simulate Real-World Scenarios**: Helps understand how customers interact with the help desk.
- **Validate Workflow**: Confirms that tickets move properly between users and agents.

This step ensures that our help desk system is functioning correctly and ready for real-world use.

</p>
<br />

<p>
<img width="713" alt="image" src="https://github.com/user-attachments/assets/65c07382-de0e-45c0-a0fd-6e9f81a8b7ac" />
</p>
<p>

Now, we are going to **configure our SLAs (Service Level Agreements)** in osTicket. SLAs define the **timeframes** in which tickets must be addressed and resolved based on their priority level. This helps manage customer expectations and ensures support requests are handled promptly.

### Steps to Configure SLAs:

1. Navigate to **Admin Panel** → **Manage** → **SLA**.
2. Click **Add New SLA Plan** to create a new SLA.
3. Define the following categories:
   - **Sev-A (Highest Priority)**: Requires **immediate** attention.
   - **Sev-B (Medium Priority)**: Important but not critical.
   - **Sev-C (Lower Priority)**: Can be addressed during standard business hours.
4. Set the **grace period**, which acts as a buffer before the SLA timer starts counting.
5. Configure the **schedules**:
   - **Sev-A & Sev-B**: Run **24/7**, meaning they are tracked around the clock.
   - **Sev-C**: Runs only during **business hours (8 AM - 5 PM)**.
6. Click **Save Changes** to finalize your SLAs.

### Why Use SLAs?

- **Ensures Timely Responses**: Helps prioritize urgent issues.
- **Improves Customer Satisfaction**: Customers know when to expect resolutions.
- **Organizes Ticket Workflow**: Tickets are categorized and managed efficiently.

This setup ensures that the help desk operates smoothly, with clear guidelines on response and resolution times.

</p>
<br />

<p>
<img width="706" alt="image" src="https://github.com/user-attachments/assets/079a7a05-6cb7-4383-8ac5-039ba0986517" />
</p>
<p>
## Configuring Help Topics in osTicket

Help Topics are categories or subjects that users can select when submitting a new support ticket. They describe the type of issue or request the user is reporting. Help Topics can be configured in the Admin Panel under:

**Admin Panel -> Manage -> Help Topics**

### Importance of Help Topics

Help Topics in osTicket serve as a crucial categorization tool for incoming support requests. When a user submits a ticket, they select a Help Topic that best describes the nature of their issue, such as:

- **Business Critical Outage**
- **Password Reset**

This categorization allows osTicket to:
- Automatically route the ticket to the appropriate department or agent.
- Apply the correct Service Level Agreement (SLA) to ensure timely resolution.
- Potentially trigger custom workflows or gather additional information relevant to the specific issue.
</p>
<br />
