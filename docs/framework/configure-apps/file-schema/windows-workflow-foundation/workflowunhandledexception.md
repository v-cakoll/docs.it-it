---
title: <workflowUnhandledException>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 57adeab5-f06a-44b2-916b-0e177cf0f4a6
ms.openlocfilehash: c46d1fb9eb853e57c7ad1b97eb9a22556cdfb7d8
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69913104"
---
# <a name="workflowunhandledexception"></a><span data-ttu-id="1816b-101">\<> workflowUnhandledException</span><span class="sxs-lookup"><span data-stu-id="1816b-101">\<workflowUnhandledException></span></span>
<span data-ttu-id="1816b-102">Comportamento del servizio che consente di specificare l'azione da intraprendere quando si verifica un'eccezione non gestita all'interno di un servizio flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="1816b-102">A service behavior that enables you to specify the action to take when an unhandled exception occurs within a workflow service.</span></span>  
  
<span data-ttu-id="1816b-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="1816b-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="1816b-104">\<comportamenti ></span><span class="sxs-lookup"><span data-stu-id="1816b-104">\<behaviors></span></span>  
<span data-ttu-id="1816b-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="1816b-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="1816b-106">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="1816b-106">\<behavior></span></span>  
<span data-ttu-id="1816b-107">\<> workflowUnhandledException</span><span class="sxs-lookup"><span data-stu-id="1816b-107">\<workflowUnhandledException></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1816b-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1816b-108">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowUnhandledException action="Abandon/AbandonAndSuspend/Cancel/Terminate" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1816b-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="1816b-109">Attributes and Elements</span></span>  
 <span data-ttu-id="1816b-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="1816b-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1816b-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="1816b-111">Attributes</span></span>  
  
|<span data-ttu-id="1816b-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="1816b-112">Attribute</span></span>|<span data-ttu-id="1816b-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1816b-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1816b-114">action</span><span class="sxs-lookup"><span data-stu-id="1816b-114">action</span></span>|<span data-ttu-id="1816b-115">Stringa che specifica l'azione da intraprendere quando si verifica un'eccezione non gestita.</span><span class="sxs-lookup"><span data-stu-id="1816b-115">A string that specifies the action to take when an unhandled exception occurs.</span></span> <span data-ttu-id="1816b-116">L'attributo è di tipo <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction>.</span><span class="sxs-lookup"><span data-stu-id="1816b-116">This attribute is of type <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction></span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1816b-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="1816b-117">Child Elements</span></span>  
 <span data-ttu-id="1816b-118">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="1816b-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1816b-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="1816b-119">Parent Elements</span></span>  
  
|<span data-ttu-id="1816b-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="1816b-120">Element</span></span>|<span data-ttu-id="1816b-121">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="1816b-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1816b-122">\<comportamento > di \<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="1816b-122">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="1816b-123">Specifica un elemento di comportamento.</span><span class="sxs-lookup"><span data-stu-id="1816b-123">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1816b-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1816b-124">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowUnhandledExceptionElement>
