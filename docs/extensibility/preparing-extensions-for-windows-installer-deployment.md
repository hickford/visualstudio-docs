---
title: "Preparing Extensions for Windows Installer Deployment | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.technology: 
  - "vs-ide-sdk"
ms.topic: "conceptual"
helpviewer_keywords: 
  - "vsix msi"
ms.assetid: 5ee2d1ba-478a-4cb7-898f-c3b4b2ee834e
author: "gregvanl"
ms.author: "gregvanl"
manager: douge
ms.workload: 
  - "vssdk"
---
# Prepare extensions for Windows Installer deployment
You cannot use a Windows Installer package (MSI) to deploy a VSIX package. However, you can extract the contents of a VSIX package for MSI deployment. This document shows how to prepare a project whose default output is a VSIX package for inclusion in a Setup project.  
  
## Prepare an extension project for Windows Installer deployment  
 Perform these steps on new extension projects before adding to a Setup project.  
  
### To prepare an extension project for Windows Installer deployment  
  
1.  Create a VSPackage, MEF component, Editor Adornment, or other extensibility project type that includes a VSIX manifest.  
  
2.  Open the VSIX manifest in the code editor.  
  
3.  Set the `InstalledByMsi` element of the VSIX manifest to `true`. For more information about the VSIX manifest, see [VSIX extension schema 2.0 reference](../extensibility/vsix-extension-schema-2-0-reference.md).  
  
     This prevents the VSIX installer from attempting to install the component.  
  
4.  Right-click the project in **Solution Explorer** and click **Properties**.  
  
5.  Select the **VSIX** tab.  
  
6.  Check the box labeled **Copy VSIX content to the following location** and type the path to where the Setup project will pick up the files.  
  
## Extract files from an existing VSIX package  
 Perform these steps to add the content of an existing VSIX package to a Setup project when you do not have the source files.  
  
### To extract files from an existing VSIX package  
  
1.  Rename the *.VSIX* file containing the extension from *filename.vsix* to *filename.zip*.  
  
2.  Copy the contents of the *.zip* file into a directory.  
  
3.  Delete the *[Content_types].xml* file from the directory.  
  
4.  Edit the VSIX manifest, as shown in the previous procedure.  
  
5.  Add the remaining files to your Setup project.  
  
## See also  
 [Visual Studio installer deployment](http://msdn.microsoft.com/en-us/121be21b-b916-43e2-8f10-8b080516d2a0)   
 [Walkthrough: Create a custom action](http://msdn.microsoft.com/en-us/4bd4b63a-2b91-431e-839c-5752443f0eaf)