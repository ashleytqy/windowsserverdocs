---
title: A virtual machine running Windows 8.1 and configured with Dynamic Memory should use recommended values for memory settings
description: " "
ms.prod: windows-server-threshold
ms.service: na
manager: dongill
ms.technology: compute-hyper-v
ms.author: kathydav
ms.topic: article
ms.assetid: b9a14f85-326f-4916-9278-2c8d39a32848
author: KBDAzure
ms.date: 8/16/2016
---
# A virtual machine running Windows 8.1 and configured with Dynamic Memory should use recommended values for memory settings

>Applies To: Windows Server 2016

For more information about best practices and scans, see [Run Best Practices Analyzer Scans and Manage Scan Results](http://go.microsoft.com/fwlink/p/?LinkID=223177).  
  
|Property|Details|  
|-|-|  
|**Operating System**|Windows Server 2016|  
|**Product/Feature**|Hyper-V|  
|**Severity**|Warning|  
|**Category**|Configuration|  
  
In the following sections, italics indicates UI text that appears in the Best Practices Analyzer tool for this issue.  
  
## **Issue**  
*One or more virtual machines are configured to use Dynamic Memory with less than the amount of memory recommended for Windows 8.1.*  
  
## **Impact**  
The guest operating system on the following virtual machines might not run or might run unreliably:   
  
\<list of virtual machines>  
      
  
## **Resolution**  
*Use Hyper-V Manager to increase the minimum memory to at least 256 MB, startup memory to at least 512 MB and maximum memory to at least 1 GB for this virtual machine.*  
  
#### Increase memory using Hyper-V Manager  
  
1.  Open Hyper-V Manager. (From Server Manager, click **Tools** > **Hyper-V Manager**.)  
  
2.  From the list of virtual machines, right-click the one you want, then click **Settings**.  
  
3.  In the navigation pane, click **Memory**.  
  
4.  Change the **RAM** to at least 512 MB.  
  
5.  Under **Dynamic Memory**,  change the **Minimum RAM** to at least 256 MB and the **Maximum RAM** to 1 GB.  
  
6.  Click **OK**.  
  
### Increase memory using Windows PowerShell  
  
1.  Open Windows PowerShell. (From the desktop, click Start and start typing **Windows PowerShell**.)  
  
2.  Right-click **Windows PowerShell** and click **Run as administrator**.  
  
3.  Run a command similar to the following, replacing MyVM with the name  of your virtual machine and the memory values with at least the values shown below.  
  
```  
Get-VM MyVM | Set-VMMemory -DynamicMemoryEnabled $True -MaximumBytes 1GB -MinimumBytes 256MB -StartupBytes 512MB  
```  
  

