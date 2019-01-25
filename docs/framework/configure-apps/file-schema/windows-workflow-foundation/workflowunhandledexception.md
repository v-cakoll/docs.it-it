---
title: '&lt;workflowUnhandledException&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 57adeab5-f06a-44b2-916b-0e177cf0f4a6
ms.openlocfilehash: 5c5dddc6d126811d7fd1eaae2f85df1e42c1cd41
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54700871"
---
# <a name="ltworkflowunhandledexceptiongt"></a><span data-ttu-id="0634c-102">&lt;workflowUnhandledException&gt;</span><span class="sxs-lookup"><span data-stu-id="0634c-102">&lt;workflowUnhandledException&gt;</span></span>
<span data-ttu-id="0634c-103">Comportamento del servizio che consente di specificare l'azione da intraprendere quando si verifica un'eccezione non gestita all'interno di un servizio flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="0634c-103">A service behavior that enables you to specify the action to take when an unhandled exception occurs within a workflow service.</span></span>  
  
<span data-ttu-id="0634c-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="0634c-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="0634c-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="0634c-105">\<behaviors></span></span>  
<span data-ttu-id="0634c-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="0634c-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="0634c-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="0634c-107">\<behavior></span></span>  
<span data-ttu-id="0634c-108">\<workflowUnhandledException></span><span class="sxs-lookup"><span data-stu-id="0634c-108">\<workflowUnhandledException></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0634c-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0634c-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowUnhandledException action="Abandon/AbandonAndSuspend/Cancel/Terminate" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0634c-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="0634c-110">Attributes and Elements</span></span>  
 <span data-ttu-id="0634c-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="0634c-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0634c-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="0634c-112">Attributes</span></span>  
  
|<span data-ttu-id="0634c-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="0634c-113">Attribute</span></span>|<span data-ttu-id="0634c-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0634c-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0634c-115">action</span><span class="sxs-lookup"><span data-stu-id="0634c-115">action</span></span>|<span data-ttu-id="0634c-116">Stringa che specifica l'azione da intraprendere quando si verifica un'eccezione non gestita.</span><span class="sxs-lookup"><span data-stu-id="0634c-116">A string that specifies the action to take when an unhandled exception occurs.</span></span> <span data-ttu-id="0634c-117">L'attributo è di tipo <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction>.</span><span class="sxs-lookup"><span data-stu-id="0634c-117">This attribute is of type <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction></span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0634c-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="0634c-118">Child Elements</span></span>  
 <span data-ttu-id="0634c-119">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="0634c-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0634c-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="0634c-120">Parent Elements</span></span>  
  
|<span data-ttu-id="0634c-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="0634c-121">Element</span></span>|<span data-ttu-id="0634c-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0634c-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0634c-123">\<comportamento > di \<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="0634c-123">\<behavior> of \<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="0634c-124">Specifica un elemento di comportamento.</span><span class="sxs-lookup"><span data-stu-id="0634c-124">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0634c-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0634c-125">See also</span></span>
- <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowUnhandledExceptionElement>
