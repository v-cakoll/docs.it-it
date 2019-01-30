---
title: <workflowUnhandledException>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 57adeab5-f06a-44b2-916b-0e177cf0f4a6
ms.openlocfilehash: caf5be7aaff0df436be3a1d618a9f89bb32e6bb7
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55254847"
---
# <a name="workflowunhandledexception"></a><span data-ttu-id="655e6-101">\<workflowUnhandledException></span><span class="sxs-lookup"><span data-stu-id="655e6-101">\<workflowUnhandledException></span></span>
<span data-ttu-id="655e6-102">Comportamento del servizio che consente di specificare l'azione da intraprendere quando si verifica un'eccezione non gestita all'interno di un servizio flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="655e6-102">A service behavior that enables you to specify the action to take when an unhandled exception occurs within a workflow service.</span></span>  
  
<span data-ttu-id="655e6-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="655e6-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="655e6-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="655e6-104">\<behaviors></span></span>  
<span data-ttu-id="655e6-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="655e6-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="655e6-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="655e6-106">\<behavior></span></span>  
<span data-ttu-id="655e6-107">\<workflowUnhandledException></span><span class="sxs-lookup"><span data-stu-id="655e6-107">\<workflowUnhandledException></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="655e6-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="655e6-108">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowUnhandledException action="Abandon/AbandonAndSuspend/Cancel/Terminate" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="655e6-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="655e6-109">Attributes and Elements</span></span>  
 <span data-ttu-id="655e6-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="655e6-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="655e6-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="655e6-111">Attributes</span></span>  
  
|<span data-ttu-id="655e6-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="655e6-112">Attribute</span></span>|<span data-ttu-id="655e6-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="655e6-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="655e6-114">action</span><span class="sxs-lookup"><span data-stu-id="655e6-114">action</span></span>|<span data-ttu-id="655e6-115">Stringa che specifica l'azione da intraprendere quando si verifica un'eccezione non gestita.</span><span class="sxs-lookup"><span data-stu-id="655e6-115">A string that specifies the action to take when an unhandled exception occurs.</span></span> <span data-ttu-id="655e6-116">L'attributo è di tipo <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction>.</span><span class="sxs-lookup"><span data-stu-id="655e6-116">This attribute is of type <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction></span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="655e6-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="655e6-117">Child Elements</span></span>  
 <span data-ttu-id="655e6-118">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="655e6-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="655e6-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="655e6-119">Parent Elements</span></span>  
  
|<span data-ttu-id="655e6-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="655e6-120">Element</span></span>|<span data-ttu-id="655e6-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="655e6-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="655e6-122">\<comportamento > di \<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="655e6-122">\<behavior> of \<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="655e6-123">Specifica un elemento di comportamento.</span><span class="sxs-lookup"><span data-stu-id="655e6-123">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="655e6-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="655e6-124">See also</span></span>
- <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowUnhandledExceptionElement>
