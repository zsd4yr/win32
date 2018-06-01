---
Description: Describing the Filter Structure
ms.assetid: 988c11ee-73e8-4494-aa19-050321cdd63e
title: Describing the Filter Structure
ms.technology: desktop
ms.prod: windows
ms.author: windowssdkdev
ms.topic: article
ms.date: 05/31/2018
---

# Describing the Filter Structure

> [!Note]  
> Indexing Service is no longer supported as of Windows XP and is unavailable for use as of Windows 8. Instead, use [Windows Search](https://msdn.microsoft.com/windows/desktop/6da601c6-3742-40ad-99f2-8817f7f642b3) for client side search and [Microsoft Search Server Express]( http://go.microsoft.com/fwlink/p/?linkid=258445) for server side search.

 

Each filter is a dynamic-link library (DLL) file that implements an in-process COM server to supply the specified filtering capabilities. The following figure shows the overall structure of a typical filter DLL. (A more complex example could implement more than one filter class.)

![](images/ixsdll.png)

 

 


