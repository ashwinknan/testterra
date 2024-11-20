---
description: How multiple users can work on the same project
---

# Collaboration

## Scenes

Scenes are integral to collaborative projects. The system provides mechanisms to prevent conflicting edits and ensure scene integrity.

## **Scene Locking**

A scene becomes **locked** when another user is actively working on it. Locked scenes ensure that no two users can edit the same scene simultaneously, avoiding conflicts.

If you attempt to launch a project and the **starting or your last edited scene is locked**, you will:

* Be prompted to choose from other **open scenes**.
* Have the option to **create a new scene** for your work.

**Delete** and **Duplicate** actions are disabled for locked scenes.

{% hint style="info" %}
While switching scenes, You can either **Cloud Save** your current changes or **Discard Changes** before moving to a new scene. This ensures that incomplete or unreviewed changes are not unintentionally synced.
{% endhint %}

## **Cloud Save**

The **Cloud Save** feature allows users to collaborate effectively on shared projects by syncing their changes to the cloud. This ensures seamless teamwork and minimises the risk of conflicting edits.

* The “Save To Cloud” button is located next to the **Play** button.
* Clicking on this will cloud save any changes made to the **current scene** and **any** **script/s edited since your last cloud save**.
* Cloud saving any script or reusable changes will automatically alert any other user working on the project to pull/fetch your latest changes.
* Note: You **cannot Cloud Save** if there are pending fetches from the cloud. Resolve these before saving.

## **Local Save**

Local saving occurs automatically during various points while you work. You can manually Local Save using the **Cmd/Ctrl+S shortcut** or the **Save** button in to toolbar. Local saves keep changes on your machine but do not sync them with the cloud unless you do so.

## **Pulling Cloud Changes**

Collaborators can stay updated with the latest project edits, ensuring alignment and consistency. When another user cloud saves their changes:

* Their scene changes are automatically synced to your local copy.

## **Script Change Notifications**

* When another user cloud saves any script changes: this will trigger an **alert** for all collaborators.
* Users are notified that **new script changes** are available. On clicking the “Pull from Cloud” button, the system displays a list of scripts with **mismatches** between local and cloud versions, allowing users to review and update. These conflicts need to be resolved before you can cloud save your work.
* If you have not worked on any scripts since your last cloud save it is advisable to select “Cloud Save” versions of all script files
* Pick “Local Save” script versions only if you are certain you have recent changes to a script or you have experienced a crash and need your local recovered file.

{% hint style="info" %}
While opening a project, if collaborators have made Cloud Save with changes while you were not on the project, when you next open the project, the system will display a list of scenes and scripts with **mismatches** between local and cloud versions.

It is advisable to choose “Cloud Save” files unless you have experienced a crash and need your local recovered file
{% endhint %}



