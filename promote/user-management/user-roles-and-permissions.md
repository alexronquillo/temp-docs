# User roles and permissions

There are four roles a user can have in justtrack:

* [Admin](user-roles-and-permissions.md#admin)
* [Manager](user-roles-and-permissions.md#manager)
* [Member](user-roles-and-permissions.md#member)
* [External](user-roles-and-permissions.md#external)

Here, you'll learn the differences between these roles and, specifically, what permissions each role is granted.

{% hint style="info" %}
Depending on your organization, some platform features listed in the roles' permissions may not be applicable.
{% endhint %}

## Admin

Admins can edit and view all features in the platform:

| Feature   | Edit | View |
| --------- | ---- | ---- |
| Users     | Yes  | Yes  |
| Apps      | Yes  | Yes  |
| Networks  | Yes  | Yes  |
| Creatives | Yes  | Yes  |

From these permissions, there are two important corollaries. Admins are the only users who can:

* Create, edit, and view other users.
* Change a Member's or External User's information, including their password.

## Manager

Managers have edit and view permissions for most features in the platform:

| Feature   | Edit | View |
| --------- | ---- | ---- |
| Users     | No   | No   |
| Apps      | Yes  | Yes  |
| Networks  | Yes  | Yes  |
| Creatives | Yes  | Yes  |

From these permissions, there are two important corollaries:

* Managers can't create, edit, or view other users.
* Managers can edit and view their own information by clicking their avatar in the top navigation:

<figure><img src="../.gitbook/assets/user-profile (1).png" alt="Arrow pointing to User Profile avatar" width="563"><figcaption><p>User Profile</p></figcaption></figure>

## Member

Members have view permissions for most features in the platform. However, they have no edit permissions:

| Feature   | Edit | View |
| --------- | ---- | ---- |
| Users     | No   | No   |
| Apps      | No   | Yes  |
| Networks  | No   | Yes  |
| Creatives | No   | Yes  |

Members can't edit their own information. Only an Admin can edit their information on their behalf.

## External

External Users can only view creatives. They have no edit permissions:

| Feature   | Edit | View |
| --------- | ---- | ---- |
| Users     | No   | No   |
| Apps      | No   | No   |
| Networks  | No   | No   |
| Creatives | No   | Yes  |

Like Members, External Users can't edit their own information. Only an Admin can edit their information on their behalf.

## Further reading

Now that you know what the four roles in justtrack are, you can learn how to:

* [Add a new user](create-a-new-user.md)
* [Change a user's role](change-a-users-settings.md)
* [Activate and deactivate a user](activate-or-deactivate-a-user.md)
