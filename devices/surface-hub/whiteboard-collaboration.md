---
title: Set up and use Whiteboard to Whiteboard collaboration 
description: Microsoft Whiteboard’s latest update includes the capability for two Surface Hubs to collaborate in real time on the same board.
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: surfacehub
author: jdeckerms
ms.author: jdecker
ms.date: 06/19/2017
localizationpriority: medium
---

# Set up and use Whiteboard to Whiteboard collaboration (Surface Hub)

Microsoft Whiteboard’s latest update (17.8302.5275X or greater) includes the capability for two Surface Hubs to collaborate in real time on the same board. 

By ensuring that your organization meets the prerequisites, users can then ink, collaborate, and ideate together. Mobile device management (MDM) allows you to control default settings and provides access to these capabilities. For more information about mobile device management for Surface Hub, see [Manage settings with an MDM provider (Surface Hub)](manage-settings-with-mdm-for-surface-hub.md).

![example of a whiteboard with collaborative inking](images/wb-collab-example.png)

## Prerequisites for Whiteboard to Whiteboard collaboration

To get Whiteboard to Whiteboard collaboration up and running, you’ll need to make sure your organization meets the following requirements:

- Office 365 with cloud-based Azure Active Directory (Azure AD) for all users
- OneDrive for Business deployed for all users who intend to collaborate
- Currently not utilizing Office 365 Germany or Office 365 	operated by 21Vianet
- Surface Hub needs to be updated to Windows 10, version 1607 or newer
- Port 443 needs to be open since Whiteboard makes standard https requests

 
>[!NOTE]
>Collaborative sessions can only take place between users within the same tenant, so users outside of your organization won’t be able to join even if they have a Surface Hub.

## Using Whiteboard to Whiteboard collaboration

To start a collaboration session:

1.	In the Whiteboard app, tap the **Sign in** button.
2.	Sign in with your organization ID.
3.	Tap the **Invite** button next to your name at the top of the app.
4.	Tap **Start session**. Whiteboard will generate a link that you can share.

    ![screenshot of the link dialog box on whiteboard](images/wb-collab-link.png)
    
5.	Copy and paste this link into a Skype chat with another Surface Hub

When the other Surface Hub receives the link, the recipient can tap on the link, sign in to Whiteboard, and then begin collaborating. You can copy and paste other content, use smart ink features like Ink to Shape, and co-author together.

After you’re done, you can export a copy of the Whiteboard collaboration for yourself through the Share charm and leave the board for others to continue working. 

## How to control and manage Whiteboard to Whiteboard collaboration

Whiteboard has settings that can be managed via MDM. These allow you to disable or enable collaboration functionality in case your organization can’t meet the prerequisites or you’d rather not have your organization use this feature. 

The value for each setting can be True or False. The default value for each setting is False. 
 
The OMA URI for each setting consists of `./User/Vendor/MSFT/EnterpriseModernAppManagement/AppManagement/AppStore/Microsoft.Office.Whiteboard_8wekyb3d8bbwe/AppSettingPolicy/` and the string from the OMA URI column in the table. For example, the full OMA URI for **Enable sign-in** is `./User/Vendor/MSFT/EnterpriseModernAppManagement/AppManagement/AppStore/Microsoft.Office.Whiteboard_8wekyb3d8bbwe/AppSettingPolicy/EnableSignIn`.

| Setting | Details | OMA URI | Supported with<br>Intune? | Supported with<br>Configuration Manager? | Supported with<br>SyncML*? |
| --- | ---- | --- |---- | --- | --- |
| Enable sign-in | Users can sign in and authenticate | EnableSignIn  | Yes <br> [Use a custom policy.](#example-intune)  |  Yes.<br> [Use a custom setting.](#example-sccm) | Yes |
| Disable sign-in | Users are unable to sign in and access collaboration or education features | DisableSignIn  | Yes <br> [Use a custom policy.](#example-intune)  |  Yes.<br> [Use a custom setting.](#example-sccm) | Yes |
| Disable Collaboration | Users can sign in but not create or join collaborative sessions | DisableCollaboration  | Yes <br> [Use a custom policy.](#example-intune)  |  Yes.<br> [Use a custom setting.](#example-sccm) | Yes |
\*Settings supported with SyncML can also be configured in a Windows Configuration Designer provisioning package.

Whiteboard also has other MDM settings that can be managed and set for defaults, exporting, and sharing. You can see these additional settings in [Manage settings with an MDM provider (Surface Hub)](manage-settings-with-mdm-for-surface-hub.md#whiteboard-collaboration-settings).





## Related topics

- [Windows 10 Creators Update for Surface Hub](https://www.microsoft.com/surface/support/surface-hub/windows-10-creators-update-surface-hub)
- [Support documentation for Microsoft Whiteboard](https://support.office.com/en-us/article/Whiteboard-Help-0c0f2aa0-b1bb-491c-b814-fd22de4d7c01)