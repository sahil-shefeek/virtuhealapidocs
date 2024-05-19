# User groups and Authorization


This document provides an overview of the user groups and permissions within the system. Depending on the group to which a user belongs, they have different levels of access and capabilities. The groups are `SuperAdmin`, `Admin`, and `Manager`.


### SuperAdmin

The `SuperAdmin` group has the highest level of permissions. Users in this group have the ability to perform all actions related to the user interface, associates, care homes, care home managers, feedback, and reports.

**Permissions:**
- `add_interfaceuser`
- `change_interfaceuser`
- `view_interfaceuser`
- `add_associates`
- `change_associates`
- `view_associates`
- `add_carehomes`
- `change_carehomes`
- `view_carehomes`
- `add_carehomemanagers`
- `change_carehomemanagers`
- `view_carehomemanagers`
- `view_feedback`
- `view_reports`

### Admin

The `Admin` group has a slightly reduced set of permissions compared to the `SuperAdmin` group. Admins can manage users, associates, care home managers, feedback, and reports but do not have permission to manage care homes.

**Permissions:**
- `add_interfaceuser`
- `change_interfaceuser`
- `view_interfaceuser`
- `add_associates`
- `change_associates`
- `view_associates`
- `add_carehomemanagers`
- `change_carehomemanagers`
- `view_carehomemanagers`
- `add_feedback`
- `view_feedback`
- `add_reports`
- `view_reports`

### Manager

The `Manager` group has the most restricted set of permissions. Managers can add and view feedback, manage associates, and view reports. They also have permissions to view and change users.

**Permissions:**
- `add_feedback`
- `view_feedback`
- `view_interfaceuser`
- `change_interfaceuser`
- `add_associates`
- `change_associates`
- `view_associates`
- `view_reports`

## Group Permission Initialization Script

The management script in the server handles the permission logic. 
To invoke run the command
 ```
 python manage.py init_groups
 ```
> In case of rebuilding the database, the usergroups must be initialised prior to any user creation.
> {style=warning}