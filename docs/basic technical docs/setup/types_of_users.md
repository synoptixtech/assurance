---
title: Types of Users
nav_order: 3
parent: Setup and Onboarding
layout: default
---

# Types of Users

## Role Summaries

Each available role and their intended use is summarised below. Only Synoptix roles can ever be multi-client, to ensure data stays within individual instances. 

| Role              | Description                                                                                                                                                   | Held by:            |
|-------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------|
| Local Admin       | The client side administrators. Able to add systems, users, and change settings within a specific client. Client will be allocated by Synoptix administrator. | Client              |
| Client Modeller   | Someone actively developing models for a specific client.                                                                                                     | Client              |
| Approver          | Someone, independent on modelling, who is able to approve and authorise models and sections of models.                                                        | Client              |
| Senior Leader     | A read-only view for those not involved in modelling.                                                                                                         | Client              |
| Super Admin       | Synoptix-side super administrators with global permissions. Reserved for a small number of platform owners.                                                   | Synoptix users only |
| Synoptix Modeller | Someone activitely developing models over a number of clients.                                                                                                | Synoptix users only |

## Role Permissions

Role permissions are summarised here. Actual implemented permissions are slightly more granular, and can be viewed by administrators within the platform itself.

| Role              | Audit | Reports | Models            | Projects  | Systems   | Clients   | Users                       |
|-------------------|-------|---------|-------------------|-----------|-----------|-----------|-----------------------------|
| Local Admin       | View  | View    | View/Edit         | View/Edit | View/Edit |           | View/Edit (own client only) |
| Client Modeller   |       | View    | View/Edit         | View      | View      |           |                             |
| Approver          |       | View    | View/Approve      | View      | View      |           |                             |
| Senior Leader     |       | View    | View              | View      | View      |           |                             |
| Super Admin       | View  | View    | View/Edit/Approve |           |           | View/Edit | View/Edit                   |
| Synoptix Modeller |       | View    | View/Edit         |           |           | View      |                             |