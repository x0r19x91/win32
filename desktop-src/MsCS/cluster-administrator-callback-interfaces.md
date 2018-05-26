---
title: Failover Cluster Administrator Callback Interfaces
description: List of Failover Cluster Administrator callback interfaces.
audience: developer
author: REDMOND\\markl
manager: REDMOND\\markl
ms.assetid: 4a2b0c21-1b3f-4037-a143-02956e6996ce
ms.prod: windows-server-dev
ms.technology: failover-clustering
ms.tgt_platform: multiple
keywords:
- Failover Cluster Administrator Failover Cluster ,Failover Cluster Administrator Extension API,callback interfaces
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
---

# Failover Cluster Administrator Callback Interfaces

\[With the exception of [**IWCPropertySheetCallback**](/windows/previous-versions/cluadmex/nn-cluadmex-iwcpropertysheetcallback?branch=master), support for Failover Cluster Administrator callback interfaces was removed in Windows Server 2008.\]

[Failover Cluster Administrator](cluster-administrator.md) implements the following callback interfaces to allow allow your extension to create new property pages, wizard pages, and context menu items:

-   [**IWCContextMenuCallback**](/windows/previous-versions/cluadmex/nn-cluadmex-iwccontextmenucallback?branch=master)
-   [**IWCPropertySheetCallback**](/windows/previous-versions/cluadmex/nn-cluadmex-iwcpropertysheetcallback?branch=master)
-   [**IWCWizardCallback**](/windows/previous-versions/cluadmex/nn-cluadmex-iwcwizardcallback?branch=master)
-   [**IWCWizard97Callback**](/windows/previous-versions/cluadmex/nn-cluadmex-iwcwizard97callback?branch=master)

 

 



