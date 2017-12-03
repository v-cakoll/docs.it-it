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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 28e0f2b0ed88ee73edb52a8c18346746beb34771
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="ltworkflowinstancemanagementgt"></a><span data-ttu-id="535b1-102">&lt;workflowInstanceManagement&gt;</span><span class="sxs-lookup"><span data-stu-id="535b1-102">&lt;workflowInstanceManagement&gt;</span></span>
<span data-ttu-id="535b1-103">Comportamento del servizio che consente di specificare impostazioni che controllano la modalità di esecuzione delle istanze del flusso di lavoro, inclusa la persistenza, il comportamento delle eccezioni non gestite e il comportamento di inattività.</span><span class="sxs-lookup"><span data-stu-id="535b1-103">A service behavior that enables you to specify settings that control how workflow instances are run, including persistence, unhandled Exception behavior and idle behavior.</span></span>  
  
<span data-ttu-id="535b1-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="535b1-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="535b1-105">\<i comportamenti ></span><span class="sxs-lookup"><span data-stu-id="535b1-105">\<behaviors></span></span>  
<span data-ttu-id="535b1-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="535b1-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="535b1-107">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="535b1-107">\<behavior></span></span>  
<span data-ttu-id="535b1-108">\<workflowInstanceManagement ></span><span class="sxs-lookup"><span data-stu-id="535b1-108">\<workflowInstanceManagement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="535b1-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="535b1-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowInstanceManagement authorizedWindowsGroup="" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="535b1-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="535b1-110">Attributes and Elements</span></span>  
 <span data-ttu-id="535b1-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="535b1-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="535b1-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="535b1-112">Attributes</span></span>  
  
|<span data-ttu-id="535b1-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="535b1-113">Attribute</span></span>|<span data-ttu-id="535b1-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="535b1-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="535b1-115">authorizedWindowsGroup</span><span class="sxs-lookup"><span data-stu-id="535b1-115">authorizedWindowsGroup</span></span>||  
  
### <a name="child-elements"></a><span data-ttu-id="535b1-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="535b1-116">Child Elements</span></span>  
 <span data-ttu-id="535b1-117">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="535b1-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="535b1-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="535b1-118">Parent Elements</span></span>  
  
|<span data-ttu-id="535b1-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="535b1-119">Element</span></span>|<span data-ttu-id="535b1-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="535b1-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="535b1-121">\<comportamento > di \<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="535b1-121">\<behavior> of \<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="535b1-122">Specifica un elemento di comportamento.</span><span class="sxs-lookup"><span data-stu-id="535b1-122">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="535b1-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="535b1-123">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Description.WorkflowInstanceManagementBehavior>  
 <xref:System.ServiceModel.Activities.Configuration.WorkflowInstanceManagementElement>
