---
title: <add> di <services>
ms.date: 03/30/2017
ms.assetid: 6bdc4590-aa9c-4ec8-9345-879d780cd141
ms.openlocfilehash: 38dec132626b97accacea1b7007d914edcab0abc
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926652"
---
# <a name="add-of-services"></a><span data-ttu-id="cd15a-102">\<aggiungere > di \<Servizi ></span><span class="sxs-lookup"><span data-stu-id="cd15a-102">\<add> of \<services></span></span>
<span data-ttu-id="cd15a-103">Specifica le impostazioni per un'istanza <xref:System.Workflow.Runtime.WorkflowRuntime> di per l'hosting di servizi di Windows Communication Foundation (WCF) basati sul flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="cd15a-103">Specifies settings for an instance of <xref:System.Workflow.Runtime.WorkflowRuntime> for hosting workflow-based Windows Communication Foundation (WCF) services.</span></span> <span data-ttu-id="cd15a-104">L'elemento è di tipo <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="cd15a-104">This element is of type <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span></span>  
  
 <span data-ttu-id="cd15a-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="cd15a-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="cd15a-106">\<comportamenti ></span><span class="sxs-lookup"><span data-stu-id="cd15a-106">\<behaviors></span></span>  
<span data-ttu-id="cd15a-107">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="cd15a-107">\<serviceBehaviors></span></span>  
<span data-ttu-id="cd15a-108">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="cd15a-108">\<behavior></span></span>  
<span data-ttu-id="cd15a-109">\<> dei servizi</span><span class="sxs-lookup"><span data-stu-id="cd15a-109">\<services></span></span>  
<span data-ttu-id="cd15a-110">\<add></span><span class="sxs-lookup"><span data-stu-id="cd15a-110">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd15a-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cd15a-111">Syntax</span></span>  
  
```xml  
<workflowRuntime>
  <services>
    <add type="String" />
  </services>
</workflowRuntime>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cd15a-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="cd15a-112">Attributes and Elements</span></span>  
 <span data-ttu-id="cd15a-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="cd15a-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cd15a-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="cd15a-114">Attributes</span></span>  
  
|<span data-ttu-id="cd15a-115">Attributo</span><span class="sxs-lookup"><span data-stu-id="cd15a-115">Attribute</span></span>|<span data-ttu-id="cd15a-116">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="cd15a-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="cd15a-117">type</span><span class="sxs-lookup"><span data-stu-id="cd15a-117">type</span></span>|<span data-ttu-id="cd15a-118">Stringa che specifica il nome completo di tipo di assembly del servizio da inizializzare.</span><span class="sxs-lookup"><span data-stu-id="cd15a-118">A string that specifies the assembly-qualified type name of the service to be initialized.</span></span> <span data-ttu-id="cd15a-119">Il servizio specificato deve seguire regole precise riguardanti le firme dei relativi costruttori.</span><span class="sxs-lookup"><span data-stu-id="cd15a-119">The service specified must follow certain rules about the signatures of their constructors.</span></span> <span data-ttu-id="cd15a-120">Per altre informazioni, vedere <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="cd15a-120">See <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> for more information.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cd15a-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="cd15a-121">Child Elements</span></span>  
 <span data-ttu-id="cd15a-122">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="cd15a-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="cd15a-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="cd15a-123">Parent Elements</span></span>  
  
|<span data-ttu-id="cd15a-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="cd15a-124">Element</span></span>|<span data-ttu-id="cd15a-125">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="cd15a-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cd15a-126">\<services></span><span class="sxs-lookup"><span data-stu-id="cd15a-126">\<services></span></span>](services-of-workflowruntime.md)|<span data-ttu-id="cd15a-127">Raccolta di servizi da aggiungere al motore di <xref:System.Workflow.Runtime.WorkflowRuntime>.</span><span class="sxs-lookup"><span data-stu-id="cd15a-127">A collection of services that will be added to the <xref:System.Workflow.Runtime.WorkflowRuntime> engine.</span></span> <span data-ttu-id="cd15a-128">Gli elementi sono di tipo <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="cd15a-128">The elements are of type <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span></span>  <span data-ttu-id="cd15a-129">I servizi specificati nella raccolta verranno inizializzati dal motore di runtime del flusso di lavoro e verranno aggiunti ai relativi servizi quando verrà chiamato il costruttore <xref:System.Workflow.Runtime.WorkflowRuntime> appropriato.</span><span class="sxs-lookup"><span data-stu-id="cd15a-129">The services specified in the collection will be initialized by the workflow runtime engine and added to its services when the appropriate <xref:System.Workflow.Runtime.WorkflowRuntime> constructor is called.</span></span> <span data-ttu-id="cd15a-130">Pertanto, i servizi specificati nella raccolta devono seguire regole precise riguardanti le firme dei relativi costruttori.</span><span class="sxs-lookup"><span data-stu-id="cd15a-130">Therefore, the services specified in the collection must follow certain rules about the signatures of their constructors.</span></span> <span data-ttu-id="cd15a-131">Per altre informazioni, vedere <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="cd15a-131">See <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> for more information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cd15a-132">Note</span><span class="sxs-lookup"><span data-stu-id="cd15a-132">Remarks</span></span>  
 <span data-ttu-id="cd15a-133">Il servizio specificato in questo elemento verrà inizializzato dal motore di runtime del flusso di lavoro e aggiunto ai relativi servizi quando verrà chiamato il costruttore <xref:System.Workflow.Runtime.WorkflowRuntime> appropriato.</span><span class="sxs-lookup"><span data-stu-id="cd15a-133">The service specified in this element will be initialized by the workflow runtime engine and added to its services when the appropriate <xref:System.Workflow.Runtime.WorkflowRuntime> constructor is called.</span></span> <span data-ttu-id="cd15a-134">Pertanto, il servizio specificato deve seguire regole precise riguardanti le firme dei relativi costruttori.</span><span class="sxs-lookup"><span data-stu-id="cd15a-134">Therefore, the service specified must follow certain rules about the signatures of their constructors.</span></span> <span data-ttu-id="cd15a-135">Per altre informazioni, vedere <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="cd15a-135">See <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> for more information.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cd15a-136">Esempio</span><span class="sxs-lookup"><span data-stu-id="cd15a-136">Example</span></span>  
  
```xml  
<serviceBehaviors>
  <behavior name="ServiceBehavior">
    <workflowRuntime name="WorkflowServiceHostRuntime"
                     validateOnCreate="true"
                     enablePerformanceCounters="true">
      <services>
        <add type="NetFx.Checkin.Scenario.WorkflowServices.WorkflowBasedServices.Common.TestPersistenceService.FilePersistenceService, NetFx.Checkin.Scenario.WorkflowServices.WorkflowBasedServices.Common" />
      </services>
    </workflowRuntime>
  </behavior>
</serviceBehaviors>
```  
  
## <a name="see-also"></a><span data-ttu-id="cd15a-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cd15a-137">See also</span></span>

- <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>
- <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>
- <xref:System.Workflow.Runtime.WorkflowRuntime>
- <span data-ttu-id="cd15a-138">[File di configurazione del flusso di lavoro](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="cd15a-138">[Workflow Configuration Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span></span>
