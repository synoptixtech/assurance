---
title: Account and Workspace Setup
nav_order: 1
parent: Setup and Onboarding
layout: default
---

# Adding a user

Under the "Users" tab, select "+ Add User" in the top right.

Provide details for the user, and select their role.

| Property      | Description                               | Mandatory? |
|---------------|-------------------------------------------|------------|
| First Name    | User Details             W                 | Yes        |
| Last Name     | User Details                              | Yes        |
| Email Address | User Details                              | Yes        |
| Role          | The user's role. More details in Details on available roles can be found in [Types of Users](types_of_users.html)| Yes        |
| Organisation  | Mandatory for all except Synoptix roles.  | Yes        |

![A screenshot of the user page](..\..\..\assets\platform_screenshots\add_user.png)

# Logging In

## First Time Login
Once added to the platform by an administrator, the user will receive an email from "no-reply@synoptix.co.uk" requesting that they set up a password for the first time. This is only valid for 24 hours. After this time, the administrator will have to re-request verification through the User Management Page.

## Further Logins
After verifying your account for the first time, when accessing the site [assurance.synoptix.co.uk](https://assurance.synoptix.co.uk) a login page will be displayed.

![A screenshot of the login page](..\..\..\assets\platform_screenshots\login_page.png)

After adding your username and password, an email will be sent requesting an OTP. This 2FA is mandatory for all accounts.

![A screenshot of the OTP page](..\..\..\assets\platform_screenshots\OTP.png)

# Workspace Setup

Your Synoptix administrator will have already created a "Client" space for you. It will initially be blank, with some basic details at the top, and space to add one or more systems below. 

{: .note-title }
> Definition: System
>
> A system in Synx-Assure is an AI system that you want to assure. One system can have multiple projects, which are "use cases" or instantiations for which you are developing a specific assurance argument. A good way of determining what level your system should be defined at is by determining the level that you have discrete "system owners" for.

![Screenshot of Blank Client Page](..\..\..\assets\platform_screenshots\blank_client_page.png)

Once you click "Add System", you can complete the dialog box. 

## System Parameters

| Property           | Description                                                                                         | Mandatory? |
|--------------------|-----------------------------------------------------------------------------------------------------|------------|
| System Name        | A unique name for the system.                                                                       | Yes        |
| Description        | Any additional descriptive properties for the system.                                               | No         |
| System Owner       | Every system needs an owner. This should be the person accountable for the assurance of the system. | Yes        |
| System Owner Email | Contact details for the system owner.                                                               | Yes        |
| System Owner Phone | Contact details for the system owner.                                                               | No         |

![Add System Dialog](..\..\..\assets\platform_screenshots\add_system_dialog.png)

[Proceed to set up Projects and Models](https://docs.synoptix.co.uk/assurance/docs/basic%20technical%20docs/setup/project_creation.html){: .btn .btn-purple }
