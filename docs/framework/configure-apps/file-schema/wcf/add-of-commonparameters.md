---
title: '&lt;add&gt; di &lt;commonParameters&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3713bf25-20c8-455f-bb85-de46b6487932
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: dbdc3b87b0b501ffdbe2d6b16d59e86659b27585
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltaddgt-of-ltcommonparametersgt"></a><span data-ttu-id="1d2ad-102">&lt;add&gt; di &lt;commonParameters&gt;</span><span class="sxs-lookup"><span data-stu-id="1d2ad-102">&lt;add&gt; of &lt;commonParameters&gt;</span></span>
<span data-ttu-id="1d2ad-103">Specifica una coppia nome/valore di parametri che vengono usati globalmente tra più servizi.</span><span class="sxs-lookup"><span data-stu-id="1d2ad-103">Specifies a name-value pair of parameters that are used globally across multiple services.</span></span> <span data-ttu-id="1d2ad-104">Questo parametro in genere contiene una stringa di connessione al database che potrebbe essere condivisa dai servizi durevoli.</span><span class="sxs-lookup"><span data-stu-id="1d2ad-104">Typically this parameter includes the database connection string that might be shared by durable services.</span></span>  
  
 <span data-ttu-id="1d2ad-105">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="1d2ad-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="1d2ad-106">\<i comportamenti ></span><span class="sxs-lookup"><span data-stu-id="1d2ad-106">\<behaviors></span></span>  
<span data-ttu-id="1d2ad-107">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="1d2ad-107">\<serviceBehaviors></span></span>  
<span data-ttu-id="1d2ad-108">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="1d2ad-108">\<behavior></span></span>  
<span data-ttu-id="1d2ad-109">\<workflowRuntime ></span><span class="sxs-lookup"><span data-stu-id="1d2ad-109">\<workflowRuntime></span></span>  
<span data-ttu-id="1d2ad-110">\<Parametricomuni ></span><span class="sxs-lookup"><span data-stu-id="1d2ad-110">\<commonParameters></span></span>  
<span data-ttu-id="1d2ad-111">\<add></span><span class="sxs-lookup"><span data-stu-id="1d2ad-111">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d2ad-112">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1d2ad-112">Syntax</span></span>  
  
```xml  
<workflowRuntime>  
   <commonParameters>  
      <add name="String" value="String" />  
   </commonParameters>  
</workflowRuntime>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1d2ad-113">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="1d2ad-113">Attributes and Elements</span></span>  
 <span data-ttu-id="1d2ad-114">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="1d2ad-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1d2ad-115">Attributi</span><span class="sxs-lookup"><span data-stu-id="1d2ad-115">Attributes</span></span>  
  
|<span data-ttu-id="1d2ad-116">Attributo</span><span class="sxs-lookup"><span data-stu-id="1d2ad-116">Attribute</span></span>|<span data-ttu-id="1d2ad-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1d2ad-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1d2ad-118">name</span><span class="sxs-lookup"><span data-stu-id="1d2ad-118">name</span></span>|<span data-ttu-id="1d2ad-119">Nome del parametro specificato per un servizio.</span><span class="sxs-lookup"><span data-stu-id="1d2ad-119">The name of the parameter specified for a service.</span></span>|  
|<span data-ttu-id="1d2ad-120">predefinito</span><span class="sxs-lookup"><span data-stu-id="1d2ad-120">value</span></span>|<span data-ttu-id="1d2ad-121">Valore del parametro specificato per un servizio.</span><span class="sxs-lookup"><span data-stu-id="1d2ad-121">The value of the parameter specified for a service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1d2ad-122">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="1d2ad-122">Child Elements</span></span>  
 <span data-ttu-id="1d2ad-123">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="1d2ad-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1d2ad-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="1d2ad-124">Parent Elements</span></span>  
  
|<span data-ttu-id="1d2ad-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="1d2ad-125">Element</span></span>|<span data-ttu-id="1d2ad-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1d2ad-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1d2ad-127">\<Parametricomuni ></span><span class="sxs-lookup"><span data-stu-id="1d2ad-127">\<commonParameters></span></span>](http://msdn.microsoft.com/en-us/d0e1e6fc-985a-4713-b7da-194e30dfab4c)|<span data-ttu-id="1d2ad-128">Raccolta di parametri comuni usati dai servizi.</span><span class="sxs-lookup"><span data-stu-id="1d2ad-128">A collection of common parameters used by services.</span></span> <span data-ttu-id="1d2ad-129">Questa raccolta in genere contiene la stringa di connessione del database che potrebbe essere condivisa dai servizi durevoli.</span><span class="sxs-lookup"><span data-stu-id="1d2ad-129">This collection will typically include the database connection string that might be shared by durable services.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1d2ad-130">Note</span><span class="sxs-lookup"><span data-stu-id="1d2ad-130">Remarks</span></span>  
 <span data-ttu-id="1d2ad-131">L'elemento `<commonParameters>` definisce qualsiasi parametro usato globalmente tra più servizi, ad esempio `ConnectionString` quando si usa <xref:System.Workflow.Runtime.Hosting.SharedConnectionWorkflowCommitWorkBatchService>.</span><span class="sxs-lookup"><span data-stu-id="1d2ad-131">The `<commonParameters>` element defines any parameters that are used globally across multiple services, for example `ConnectionString` when using the <xref:System.Workflow.Runtime.Hosting.SharedConnectionWorkflowCommitWorkBatchService>.</span></span>  
  
 <span data-ttu-id="1d2ad-132">È possibile consentire a servizi che eseguono il commit di batch di lavoro su archivi di persistenza, ad esempio <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService> e <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>, di ritentare la transazione usando il parametro `EnableRetries`, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="1d2ad-132">For services that commit work batches to persistence stores, such as <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService> and <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>, you can enable them to retry their transaction by using the `EnableRetries` parameter as shown in the following example:</span></span>  
  
```xml  
<WorkflowRuntime Name="SampleApplication" UnloadOnIdle="false">  
    <commonParameters>  
        <add name="ConnectionString" value="Initial Catalog=WorkflowStore;Data Source=localhost;Integrated Security=SSPI;" />  
        <add name="EnableRetries" value="True" />  
    </commonParameters>  
    <Services>  
        <add type="System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService, System.Workflow.Runtime, Version=3.0.00000.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35" EnableRetries="False" />   
     </Services>  
</WorkflowRuntime>  
```  
  
 <span data-ttu-id="1d2ad-133">Si noti che il `EnableRetries` parametro può essere impostato su un livello globale (come illustrato nel *Parametricomuni* sezione) o per servizi individuali che supportano `EnableRetries` (come illustrato nel *servizi*sezione).</span><span class="sxs-lookup"><span data-stu-id="1d2ad-133">Notice that the `EnableRetries` parameter can be set at either a global level (as shown in the *CommonParameters* section) or for individual services that support `EnableRetries` (as shown in the *Services* section).</span></span>  
  
 <span data-ttu-id="1d2ad-134">Per ulteriori informazioni sull'utilizzo di un file di configurazione per controllare il comportamento di un <xref:System.Workflow.Runtime.WorkflowRuntime> oggetto di un'applicazione host di Windows Workflow Foundation, vedere [i file di configurazione del flusso di lavoro](http://msdn.microsoft.com/en-us/ada4bb90-6c9d-4f3d-a9d0-b559bb0f9909).</span><span class="sxs-lookup"><span data-stu-id="1d2ad-134">For more information on using a configuration file to control the behavior of a <xref:System.Workflow.Runtime.WorkflowRuntime> object of a Windows Workflow Foundation host application, see [Workflow Configuration Files](http://msdn.microsoft.com/en-us/ada4bb90-6c9d-4f3d-a9d0-b559bb0f9909).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1d2ad-135">Esempio</span><span class="sxs-lookup"><span data-stu-id="1d2ad-135">Example</span></span>  
  
```xml  
<commonParameters>  
   <add name="ConnectionString" value="Initial Catalog=WorkflowStore;Data Source=localhost;Integrated Security=SSPI;"/>  
   <add name="EnableRetries" value="true"/>  
</commonParameters>  
```  
  
## <a name="see-also"></a><span data-ttu-id="1d2ad-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1d2ad-136">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>  
 <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>  
 <xref:System.Workflow.Runtime.WorkflowRuntime>  
 <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService>  
 <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>  
 [<span data-ttu-id="1d2ad-137">File di configurazione del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="1d2ad-137">Workflow Configuration Files</span></span>](http://msdn.microsoft.com/en-us/ada4bb90-6c9d-4f3d-a9d0-b559bb0f9909)  
 [<span data-ttu-id="1d2ad-138">\<Parametricomuni ></span><span class="sxs-lookup"><span data-stu-id="1d2ad-138">\<commonParameters></span></span>](http://msdn.microsoft.com/en-us/d0e1e6fc-985a-4713-b7da-194e30dfab4c)
