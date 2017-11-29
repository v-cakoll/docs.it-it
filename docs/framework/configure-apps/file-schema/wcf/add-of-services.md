---
title: '&lt;add&gt; di &lt;services&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6bdc4590-aa9c-4ec8-9345-879d780cd141
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 60a717513689aeba1bfbd6229d4eef28024df8c9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltaddgt-of-ltservicesgt"></a><span data-ttu-id="51bed-102">&lt;add&gt; di &lt;services&gt;</span><span class="sxs-lookup"><span data-stu-id="51bed-102">&lt;add&gt; of &lt;services&gt;</span></span>
<span data-ttu-id="51bed-103">Specifica le impostazioni di un'istanza della classe <xref:System.Workflow.Runtime.WorkflowRuntime> per ospitare servizi [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] basati sul flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="51bed-103">Specifies settings for an instance of <xref:System.Workflow.Runtime.WorkflowRuntime> for hosting workflow-based [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] services.</span></span> <span data-ttu-id="51bed-104">L'elemento è di tipo <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="51bed-104">This element is of type <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span></span>  
  
 <span data-ttu-id="51bed-105">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="51bed-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="51bed-106">\<i comportamenti ></span><span class="sxs-lookup"><span data-stu-id="51bed-106">\<behaviors></span></span>  
<span data-ttu-id="51bed-107">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="51bed-107">\<serviceBehaviors></span></span>  
<span data-ttu-id="51bed-108">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="51bed-108">\<behavior></span></span>  
<span data-ttu-id="51bed-109">\<Services ></span><span class="sxs-lookup"><span data-stu-id="51bed-109">\<services></span></span>  
<span data-ttu-id="51bed-110">\<add></span><span class="sxs-lookup"><span data-stu-id="51bed-110">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51bed-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="51bed-111">Syntax</span></span>  
  
```xml  
<workflowRuntime>  
   <services>  
      <add type="String"/>  
   </services>  
</workflowRuntime>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="51bed-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="51bed-112">Attributes and Elements</span></span>  
 <span data-ttu-id="51bed-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="51bed-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="51bed-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="51bed-114">Attributes</span></span>  
  
|<span data-ttu-id="51bed-115">Attributo</span><span class="sxs-lookup"><span data-stu-id="51bed-115">Attribute</span></span>|<span data-ttu-id="51bed-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="51bed-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="51bed-117">tipo</span><span class="sxs-lookup"><span data-stu-id="51bed-117">type</span></span>|<span data-ttu-id="51bed-118">Stringa che specifica il nome completo di tipo di assembly del servizio da inizializzare.</span><span class="sxs-lookup"><span data-stu-id="51bed-118">A string that specifies the assembly-qualified type name of the service to be initialized.</span></span> <span data-ttu-id="51bed-119">Il servizio specificato deve seguire regole precise riguardanti le firme dei relativi costruttori.</span><span class="sxs-lookup"><span data-stu-id="51bed-119">The service specified must follow certain rules about the signatures of their constructors.</span></span> <span data-ttu-id="51bed-120">Per altre informazioni, vedere <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="51bed-120">See <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> for more information.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="51bed-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="51bed-121">Child Elements</span></span>  
 <span data-ttu-id="51bed-122">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="51bed-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="51bed-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="51bed-123">Parent Elements</span></span>  
  
|<span data-ttu-id="51bed-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="51bed-124">Element</span></span>|<span data-ttu-id="51bed-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="51bed-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="51bed-126">\<Services ></span><span class="sxs-lookup"><span data-stu-id="51bed-126">\<services></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/services-of-workflowruntime.md)|<span data-ttu-id="51bed-127">Raccolta di servizi da aggiungere al motore di <xref:System.Workflow.Runtime.WorkflowRuntime>.</span><span class="sxs-lookup"><span data-stu-id="51bed-127">A collection of services that will be added to the <xref:System.Workflow.Runtime.WorkflowRuntime> engine.</span></span> <span data-ttu-id="51bed-128">Gli elementi sono di tipo <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="51bed-128">The elements are of type <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span></span>  <span data-ttu-id="51bed-129">I servizi specificati nella raccolta verranno inizializzati dal motore di runtime del flusso di lavoro e verranno aggiunti ai relativi servizi quando verrà chiamato il costruttore <xref:System.Workflow.Runtime.WorkflowRuntime> appropriato.</span><span class="sxs-lookup"><span data-stu-id="51bed-129">The services specified in the collection will be initialized by the workflow runtime engine and added to its services when the appropriate <xref:System.Workflow.Runtime.WorkflowRuntime> constructor is called.</span></span> <span data-ttu-id="51bed-130">Pertanto, i servizi specificati nella raccolta devono seguire regole precise riguardanti le firme dei relativi costruttori.</span><span class="sxs-lookup"><span data-stu-id="51bed-130">Therefore, the services specified in the collection must follow certain rules about the signatures of their constructors.</span></span> <span data-ttu-id="51bed-131">Per altre informazioni, vedere <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="51bed-131">See <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> for more information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="51bed-132">Note</span><span class="sxs-lookup"><span data-stu-id="51bed-132">Remarks</span></span>  
 <span data-ttu-id="51bed-133">Il servizio specificato in questo elemento verrà inizializzato dal motore di runtime del flusso di lavoro e aggiunto ai relativi servizi quando verrà chiamato il costruttore <xref:System.Workflow.Runtime.WorkflowRuntime> appropriato.</span><span class="sxs-lookup"><span data-stu-id="51bed-133">The service specified in this element will be initialized by the workflow runtime engine and added to its services when the appropriate <xref:System.Workflow.Runtime.WorkflowRuntime> constructor is called.</span></span> <span data-ttu-id="51bed-134">Pertanto, il servizio specificato deve seguire regole precise riguardanti le firme dei relativi costruttori.</span><span class="sxs-lookup"><span data-stu-id="51bed-134">Therefore, the service specified must follow certain rules about the signatures of their constructors.</span></span> <span data-ttu-id="51bed-135">Per altre informazioni, vedere <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="51bed-135">See <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> for more information.</span></span>  
  
## <a name="example"></a><span data-ttu-id="51bed-136">Esempio</span><span class="sxs-lookup"><span data-stu-id="51bed-136">Example</span></span>  
  
```xml  
<serviceBehaviors>  
   <behavior name="ServiceBehavior">  
      <workflowRuntime name="WorkflowServiceHostRuntime"  
                       validateOnCreate="true"  
                       enablePerformanceCounters="true">  
         <services>  
             <add type="NetFx.Checkin.Scenario.WorkflowServices.WorkflowBasedServices.Common.TestPersistenceService.FilePersistenceService, NetFx.Checkin.Scenario.WorkflowServices.WorkflowBasedServices.Common"/>  
         </services>  
      </workflowRuntime>  
   </behavior>  
</serviceBehaviors>  
```  
  
## <a name="see-also"></a><span data-ttu-id="51bed-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="51bed-137">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>  
 <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>  
 <xref:System.Workflow.Runtime.WorkflowRuntime>  
 [<span data-ttu-id="51bed-138">File di configurazione del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="51bed-138">Workflow Configuration Files</span></span>](http://msdn.microsoft.com/en-us/ada4bb90-6c9d-4f3d-a9d0-b559bb0f9909)
