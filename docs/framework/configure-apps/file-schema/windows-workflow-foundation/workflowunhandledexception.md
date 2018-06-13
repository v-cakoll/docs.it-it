---
title: '&lt;workflowUnhandledException&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 57adeab5-f06a-44b2-916b-0e177cf0f4a6
ms.openlocfilehash: d9db6ecc2e95e0d1ec5738f1d2f4a09a89c57f21
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32755136"
---
# <a name="ltworkflowunhandledexceptiongt"></a><span data-ttu-id="9408d-102">&lt;workflowUnhandledException&gt;</span><span class="sxs-lookup"><span data-stu-id="9408d-102">&lt;workflowUnhandledException&gt;</span></span>
<span data-ttu-id="9408d-103">Comportamento del servizio che consente di specificare l'azione da intraprendere quando si verifica un'eccezione non gestita all'interno di un servizio flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="9408d-103">A service behavior that enables you to specify the action to take when an unhandled exception occurs within a workflow service.</span></span>  
  
<span data-ttu-id="9408d-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="9408d-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="9408d-105">\<i comportamenti ></span><span class="sxs-lookup"><span data-stu-id="9408d-105">\<behaviors></span></span>  
<span data-ttu-id="9408d-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="9408d-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="9408d-107">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="9408d-107">\<behavior></span></span>  
<span data-ttu-id="9408d-108">\<workflowUnhandledException ></span><span class="sxs-lookup"><span data-stu-id="9408d-108">\<workflowUnhandledException></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9408d-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9408d-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowUnhandledException action="Abandon/AbandonAndSuspend/Cancel/Terminate" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9408d-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="9408d-110">Attributes and Elements</span></span>  
 <span data-ttu-id="9408d-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="9408d-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9408d-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="9408d-112">Attributes</span></span>  
  
|<span data-ttu-id="9408d-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="9408d-113">Attribute</span></span>|<span data-ttu-id="9408d-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9408d-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9408d-115">action</span><span class="sxs-lookup"><span data-stu-id="9408d-115">action</span></span>|<span data-ttu-id="9408d-116">Stringa che specifica l'azione da intraprendere quando si verifica un'eccezione non gestita.</span><span class="sxs-lookup"><span data-stu-id="9408d-116">A string that specifies the action to take when an unhandled exception occurs.</span></span> <span data-ttu-id="9408d-117">L'attributo è di tipo <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction>.</span><span class="sxs-lookup"><span data-stu-id="9408d-117">This attribute is of type <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction></span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9408d-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="9408d-118">Child Elements</span></span>  
 <span data-ttu-id="9408d-119">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="9408d-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9408d-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="9408d-120">Parent Elements</span></span>  
  
|<span data-ttu-id="9408d-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="9408d-121">Element</span></span>|<span data-ttu-id="9408d-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9408d-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9408d-123">\<comportamento > di \<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="9408d-123">\<behavior> of \<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="9408d-124">Specifica un elemento di comportamento.</span><span class="sxs-lookup"><span data-stu-id="9408d-124">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9408d-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9408d-125">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior>  
 <xref:System.ServiceModel.Activities.Configuration.WorkflowUnhandledExceptionElement>
