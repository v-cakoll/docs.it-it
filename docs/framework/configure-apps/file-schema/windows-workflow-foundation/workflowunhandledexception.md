---
title: '&lt;workflowUnhandledException&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 57adeab5-f06a-44b2-916b-0e177cf0f4a6
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 03123081c16a94d006ebee6373cf744d7d46b5b8
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="ltworkflowunhandledexceptiongt"></a><span data-ttu-id="efc86-102">&lt;workflowUnhandledException&gt;</span><span class="sxs-lookup"><span data-stu-id="efc86-102">&lt;workflowUnhandledException&gt;</span></span>
<span data-ttu-id="efc86-103">Comportamento del servizio che consente di specificare l'azione da intraprendere quando si verifica un'eccezione non gestita all'interno di un servizio flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="efc86-103">A service behavior that enables you to specify the action to take when an unhandled exception occurs within a workflow service.</span></span>  
  
<span data-ttu-id="efc86-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="efc86-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="efc86-105">\<i comportamenti ></span><span class="sxs-lookup"><span data-stu-id="efc86-105">\<behaviors></span></span>  
<span data-ttu-id="efc86-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="efc86-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="efc86-107">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="efc86-107">\<behavior></span></span>  
<span data-ttu-id="efc86-108">\<workflowUnhandledException ></span><span class="sxs-lookup"><span data-stu-id="efc86-108">\<workflowUnhandledException></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="efc86-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="efc86-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowUnhandledException action="Abandon/AbandonAndSuspend/Cancel/Terminate" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="efc86-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="efc86-110">Attributes and Elements</span></span>  
 <span data-ttu-id="efc86-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="efc86-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="efc86-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="efc86-112">Attributes</span></span>  
  
|<span data-ttu-id="efc86-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="efc86-113">Attribute</span></span>|<span data-ttu-id="efc86-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="efc86-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="efc86-115">action</span><span class="sxs-lookup"><span data-stu-id="efc86-115">action</span></span>|<span data-ttu-id="efc86-116">Stringa che specifica l'azione da intraprendere quando si verifica un'eccezione non gestita.</span><span class="sxs-lookup"><span data-stu-id="efc86-116">A string that specifies the action to take when an unhandled exception occurs.</span></span> <span data-ttu-id="efc86-117">L'attributo è di tipo <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction>.</span><span class="sxs-lookup"><span data-stu-id="efc86-117">This attribute is of type <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction></span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="efc86-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="efc86-118">Child Elements</span></span>  
 <span data-ttu-id="efc86-119">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="efc86-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="efc86-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="efc86-120">Parent Elements</span></span>  
  
|<span data-ttu-id="efc86-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="efc86-121">Element</span></span>|<span data-ttu-id="efc86-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="efc86-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="efc86-123">\<comportamento > di \<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="efc86-123">\<behavior> of \<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="efc86-124">Specifica un elemento di comportamento.</span><span class="sxs-lookup"><span data-stu-id="efc86-124">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="efc86-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="efc86-125">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior>  
 <xref:System.ServiceModel.Activities.Configuration.WorkflowUnhandledExceptionElement>
