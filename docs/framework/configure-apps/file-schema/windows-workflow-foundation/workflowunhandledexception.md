---
title: <workflowUnhandledException>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 57adeab5-f06a-44b2-916b-0e177cf0f4a6
ms.openlocfilehash: cfe3350ac42d1e0e837b79f25753f62dc2051dd2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59096251"
---
# <a name="workflowunhandledexception"></a><span data-ttu-id="cad69-101">\<workflowUnhandledException></span><span class="sxs-lookup"><span data-stu-id="cad69-101">\<workflowUnhandledException></span></span>
<span data-ttu-id="cad69-102">Comportamento del servizio che consente di specificare l'azione da intraprendere quando si verifica un'eccezione non gestita all'interno di un servizio flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="cad69-102">A service behavior that enables you to specify the action to take when an unhandled exception occurs within a workflow service.</span></span>  
  
<span data-ttu-id="cad69-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="cad69-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="cad69-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="cad69-104">\<behaviors></span></span>  
<span data-ttu-id="cad69-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="cad69-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="cad69-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="cad69-106">\<behavior></span></span>  
<span data-ttu-id="cad69-107">\<workflowUnhandledException></span><span class="sxs-lookup"><span data-stu-id="cad69-107">\<workflowUnhandledException></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cad69-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cad69-108">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowUnhandledException action="Abandon/AbandonAndSuspend/Cancel/Terminate" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cad69-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="cad69-109">Attributes and Elements</span></span>  
 <span data-ttu-id="cad69-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="cad69-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cad69-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="cad69-111">Attributes</span></span>  
  
|<span data-ttu-id="cad69-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="cad69-112">Attribute</span></span>|<span data-ttu-id="cad69-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cad69-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="cad69-114">action</span><span class="sxs-lookup"><span data-stu-id="cad69-114">action</span></span>|<span data-ttu-id="cad69-115">Stringa che specifica l'azione da intraprendere quando si verifica un'eccezione non gestita.</span><span class="sxs-lookup"><span data-stu-id="cad69-115">A string that specifies the action to take when an unhandled exception occurs.</span></span> <span data-ttu-id="cad69-116">L'attributo è di tipo <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction>.</span><span class="sxs-lookup"><span data-stu-id="cad69-116">This attribute is of type <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction></span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cad69-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="cad69-117">Child Elements</span></span>  
 <span data-ttu-id="cad69-118">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="cad69-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="cad69-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="cad69-119">Parent Elements</span></span>  
  
|<span data-ttu-id="cad69-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="cad69-120">Element</span></span>|<span data-ttu-id="cad69-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cad69-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cad69-122">\<comportamento > di \<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="cad69-122">\<behavior> of \<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="cad69-123">Specifica un elemento di comportamento.</span><span class="sxs-lookup"><span data-stu-id="cad69-123">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cad69-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cad69-124">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowUnhandledExceptionElement>
