---
title: <workflowUnhandledException>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 57adeab5-f06a-44b2-916b-0e177cf0f4a6
ms.openlocfilehash: cfe3350ac42d1e0e837b79f25753f62dc2051dd2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59096251"
---
# <a name="workflowunhandledexception"></a><span data-ttu-id="9d45e-101">\<workflowUnhandledException></span><span class="sxs-lookup"><span data-stu-id="9d45e-101">\<workflowUnhandledException></span></span>
<span data-ttu-id="9d45e-102">Comportamento del servizio che consente di specificare l'azione da intraprendere quando si verifica un'eccezione non gestita all'interno di un servizio flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="9d45e-102">A service behavior that enables you to specify the action to take when an unhandled exception occurs within a workflow service.</span></span>  
  
<span data-ttu-id="9d45e-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="9d45e-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="9d45e-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="9d45e-104">\<behaviors></span></span>  
<span data-ttu-id="9d45e-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="9d45e-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="9d45e-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="9d45e-106">\<behavior></span></span>  
<span data-ttu-id="9d45e-107">\<workflowUnhandledException></span><span class="sxs-lookup"><span data-stu-id="9d45e-107">\<workflowUnhandledException></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d45e-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9d45e-108">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowUnhandledException action="Abandon/AbandonAndSuspend/Cancel/Terminate" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9d45e-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="9d45e-109">Attributes and Elements</span></span>  
 <span data-ttu-id="9d45e-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="9d45e-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9d45e-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="9d45e-111">Attributes</span></span>  
  
|<span data-ttu-id="9d45e-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="9d45e-112">Attribute</span></span>|<span data-ttu-id="9d45e-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9d45e-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9d45e-114">action</span><span class="sxs-lookup"><span data-stu-id="9d45e-114">action</span></span>|<span data-ttu-id="9d45e-115">Stringa che specifica l'azione da intraprendere quando si verifica un'eccezione non gestita.</span><span class="sxs-lookup"><span data-stu-id="9d45e-115">A string that specifies the action to take when an unhandled exception occurs.</span></span> <span data-ttu-id="9d45e-116">Questo attributo è di tipo</span><span class="sxs-lookup"><span data-stu-id="9d45e-116">This attribute is of type</span></span> <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction>|  
  
### <a name="child-elements"></a><span data-ttu-id="9d45e-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="9d45e-117">Child Elements</span></span>  
 <span data-ttu-id="9d45e-118">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="9d45e-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9d45e-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="9d45e-119">Parent Elements</span></span>  
  
|<span data-ttu-id="9d45e-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="9d45e-120">Element</span></span>|<span data-ttu-id="9d45e-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9d45e-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9d45e-122">\<comportamento > di \<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="9d45e-122">\<behavior> of \<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="9d45e-123">Specifica un elemento di comportamento.</span><span class="sxs-lookup"><span data-stu-id="9d45e-123">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9d45e-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9d45e-124">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowUnhandledExceptionElement>
