---
title: '&lt;workflowInstanceManagement&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 63ac89ba-c844-4ae2-96ae-cd752a90a109
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 9883cedbbe3657eb82c25abbad66487e39ce2579
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltworkflowinstancemanagementgt"></a><span data-ttu-id="4d032-102">&lt;workflowInstanceManagement&gt;</span><span class="sxs-lookup"><span data-stu-id="4d032-102">&lt;workflowInstanceManagement&gt;</span></span>
<span data-ttu-id="4d032-103">Comportamento del servizio che consente di specificare impostazioni che controllano la modalità di esecuzione delle istanze del flusso di lavoro, inclusa la persistenza, il comportamento delle eccezioni non gestite e il comportamento di inattività.</span><span class="sxs-lookup"><span data-stu-id="4d032-103">A service behavior that enables you to specify settings that control how workflow instances are run, including persistence, unhandled Exception behavior and idle behavior.</span></span>  
  
<span data-ttu-id="4d032-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="4d032-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="4d032-105">\<i comportamenti ></span><span class="sxs-lookup"><span data-stu-id="4d032-105">\<behaviors></span></span>  
<span data-ttu-id="4d032-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="4d032-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="4d032-107">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="4d032-107">\<behavior></span></span>  
<span data-ttu-id="4d032-108">\<workflowInstanceManagement ></span><span class="sxs-lookup"><span data-stu-id="4d032-108">\<workflowInstanceManagement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d032-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4d032-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowInstanceManagement authorizedWindowsGroup="" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4d032-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="4d032-110">Attributes and Elements</span></span>  
 <span data-ttu-id="4d032-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="4d032-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4d032-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="4d032-112">Attributes</span></span>  
  
|<span data-ttu-id="4d032-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="4d032-113">Attribute</span></span>|<span data-ttu-id="4d032-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4d032-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4d032-115">authorizedWindowsGroup</span><span class="sxs-lookup"><span data-stu-id="4d032-115">authorizedWindowsGroup</span></span>||  
  
### <a name="child-elements"></a><span data-ttu-id="4d032-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="4d032-116">Child Elements</span></span>  
 <span data-ttu-id="4d032-117">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="4d032-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4d032-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="4d032-118">Parent Elements</span></span>  
  
|<span data-ttu-id="4d032-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="4d032-119">Element</span></span>|<span data-ttu-id="4d032-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4d032-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4d032-121">\<comportamento > di \<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="4d032-121">\<behavior> of \<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="4d032-122">Specifica un elemento di comportamento.</span><span class="sxs-lookup"><span data-stu-id="4d032-122">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4d032-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4d032-123">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Description.WorkflowInstanceManagementBehavior>  
 <xref:System.ServiceModel.Activities.Configuration.WorkflowInstanceManagementElement>
