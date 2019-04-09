---
title: <commonParameters>
ms.date: 03/30/2017
ms.assetid: ffc20832-34d6-4622-8174-81924fd53514
ms.openlocfilehash: b9ab4e8ca5a71d54a80d17322b61c83d41af2b40
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59088353"
---
# <a name="commonparameters"></a><span data-ttu-id="fcd6a-101">\<commonParameters></span><span class="sxs-lookup"><span data-stu-id="fcd6a-101">\<commonParameters></span></span>
<span data-ttu-id="fcd6a-102">Rappresenta una raccolta di parametri che vengono usati globalmente tra più servizi.</span><span class="sxs-lookup"><span data-stu-id="fcd6a-102">Represents a collection of parameters that are used globally across multiple services.</span></span> <span data-ttu-id="fcd6a-103">Questa raccolta in genere contiene la stringa di connessione del database che potrebbe essere condivisa dai servizi durevoli.</span><span class="sxs-lookup"><span data-stu-id="fcd6a-103">This collection will typically include the database connection string that might be shared by durable services.</span></span>  
  
 <span data-ttu-id="fcd6a-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="fcd6a-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="fcd6a-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="fcd6a-105">\<behaviors></span></span>  
<span data-ttu-id="fcd6a-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="fcd6a-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="fcd6a-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="fcd6a-107">\<behavior></span></span>  
<span data-ttu-id="fcd6a-108">\<workflowRuntime></span><span class="sxs-lookup"><span data-stu-id="fcd6a-108">\<workflowRuntime></span></span>  
<span data-ttu-id="fcd6a-109">\<commonParameters></span><span class="sxs-lookup"><span data-stu-id="fcd6a-109">\<commonParameters></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fcd6a-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fcd6a-110">Syntax</span></span>  
  
```xml  
<workflowRuntime>
  <commonParameters>
    <add name="String"
         value="String" />
  </commonParameters>
</workflowRuntime>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fcd6a-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="fcd6a-111">Attributes and Elements</span></span>  
 <span data-ttu-id="fcd6a-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="fcd6a-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fcd6a-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="fcd6a-113">Attributes</span></span>  
 <span data-ttu-id="fcd6a-114">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="fcd6a-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="fcd6a-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="fcd6a-115">Child Elements</span></span>  
  
|<span data-ttu-id="fcd6a-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="fcd6a-116">Element</span></span>|<span data-ttu-id="fcd6a-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fcd6a-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fcd6a-118">\<add></span><span class="sxs-lookup"><span data-stu-id="fcd6a-118">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-commonparameters.md)|<span data-ttu-id="fcd6a-119">Aggiunge alla raccolta una coppia nome/valore di parametri comuni usati dai servizi.</span><span class="sxs-lookup"><span data-stu-id="fcd6a-119">Adds a name-value pair of common parameters used by services to the collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="fcd6a-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="fcd6a-120">Parent Elements</span></span>  
  
|<span data-ttu-id="fcd6a-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="fcd6a-121">Element</span></span>|<span data-ttu-id="fcd6a-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fcd6a-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fcd6a-123">\<workflowRuntime></span><span class="sxs-lookup"><span data-stu-id="fcd6a-123">\<workflowRuntime></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/workflowruntime.md)|<span data-ttu-id="fcd6a-124">Specifica le impostazioni per un'istanza di <xref:System.Workflow.Runtime.WorkflowRuntime> per ospitare i servizi Windows Communication Foundation (WCF) in base al flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="fcd6a-124">Specifies settings for an instance of <xref:System.Workflow.Runtime.WorkflowRuntime> for hosting workflow-based Windows Communication Foundation (WCF) services.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fcd6a-125">Note</span><span class="sxs-lookup"><span data-stu-id="fcd6a-125">Remarks</span></span>  
 <span data-ttu-id="fcd6a-126">L'elemento `<commonParameters>` definisce qualsiasi parametro usato globalmente tra più servizi, ad esempio `ConnectionString` quando si usa <xref:System.Workflow.Runtime.Hosting.SharedConnectionWorkflowCommitWorkBatchService>.</span><span class="sxs-lookup"><span data-stu-id="fcd6a-126">The `<commonParameters>` element defines any parameters that are used globally across multiple services, for example `ConnectionString` when using the <xref:System.Workflow.Runtime.Hosting.SharedConnectionWorkflowCommitWorkBatchService>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fcd6a-127">Il servizio di rilevamento SQL non utilizzerà in modo coerente il valore `ConnectionString` nel caso in cui venga specificato nella sezione `<commonParameters>`.</span><span class="sxs-lookup"><span data-stu-id="fcd6a-127">SQL Tracking service does not consistently use the `ConnectionString` value if it is specified in the `<commonParameters>` section.</span></span> <span data-ttu-id="fcd6a-128">Alcune delle relative operazioni, ad esempio il recupero della proprietà `StateMachineWorkflowInstance.StateHistory`, potrebbero non riuscire.</span><span class="sxs-lookup"><span data-stu-id="fcd6a-128">Some of its operations such as retrieving the `StateMachineWorkflowInstance.StateHistory` property may fail.</span></span> <span data-ttu-id="fcd6a-129">Una soluzione alternativa consente nello specificare l'attributo `ConnectionString` nella sezione di configurazione per il provider di rilevamento, come indicato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="fcd6a-129">To workaround this, specify the `ConnectionString` attribute in the configuration section for tracking provider, as indicated in the following example.</span></span>  
  
 `<add`  
  
 `type="System.Workflow.Runtime.Tracking.SqlTrackingService, System.Workflow.Runtime, Version=3.0.00000.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35"`  
  
 `ConnectionString="Data Source=localhost;Initial Catalog=Partner20WFTP;Integrated Security=True;" />`  
  
 <span data-ttu-id="fcd6a-130">È possibile consentire a servizi che eseguono il commit di batch di lavoro su archivi di persistenza, ad esempio <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService> e <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>, di ritentare la transazione usando il parametro `EnableRetries`, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="fcd6a-130">For services that commit work batches to persistence stores, such as <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService> and <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>, you can enable them to retry their transaction by using the `EnableRetries` parameter as shown in the following example:</span></span>  
  
```xml  
<workflowRuntime name="SampleApplication"
                 unloadOnIdle="false">
  <commonParameters>
    <add name="ConnectionString"
         value="Initial Catalog=WorkflowStore;Data Source=localhost;Integrated Security=SSPI;" />
    <add name="EnableRetries"
         value="True" />
  </commonParameters>
  <services>
    <add type="System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService, System.Workflow.Runtime,
               Version=3.0.00000.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35"
         enableRetries="False" />
  </services>
</workflowRuntime>
```  
  
 <span data-ttu-id="fcd6a-131">Si noti che il `EnableRetries` parametro può essere impostato a livello globale (come illustrato nella *CommonParameters* sezione) o per servizi individuali che supportano `EnableRetries` (come illustrato nella *Services*sezione).</span><span class="sxs-lookup"><span data-stu-id="fcd6a-131">Notice that the `EnableRetries` parameter can be set either at a global level (as shown in the *CommonParameters* section) or for individual services that support `EnableRetries` (as shown in the *Services* section).</span></span>  
  
 <span data-ttu-id="fcd6a-132">Nel codice di esempio seguente viene illustrato come modificare i parametri comuni a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="fcd6a-132">The following sample code shows how to change the common parameters programmatically.</span></span>  
  
```  
Configuration config=WebConfigurationManager.OpenWebConfiguration("/Workflow", "Default Web Site", null, "localhost");  
WorkflowRuntimeSection wfruntime=config.GetSection("WorkflowRuntime") as WorkflowRuntimeSection;  
NameValueConfigurationCollection commonParameters=wfruntime.CommonParameters;  
commonParameters["ConnectionString"].Value="another connection string";  
config.Save();  
```  
  
 <span data-ttu-id="fcd6a-133">Per altre informazioni sull'uso di un file di configurazione per controllare il comportamento di un <xref:System.Workflow.Runtime.WorkflowRuntime> oggetto di un'applicazione host di Windows Workflow Foundation, vedere [i file di configurazione del flusso di lavoro](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="fcd6a-133">For more information about using a configuration file to control the behavior of a <xref:System.Workflow.Runtime.WorkflowRuntime> object of a Windows Workflow Foundation host application, see [Workflow Configuration Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="fcd6a-134">Esempio</span><span class="sxs-lookup"><span data-stu-id="fcd6a-134">Example</span></span>  
  
```xml  
<commonParameters>
   <add name="ConnectionString"
        value="Initial Catalog=WorkflowStore;Data Source=localhost;Integrated Security=SSPI;" />
   <add name="EnableRetries"
        value="true" />
</commonParameters>
```  
  
## <a name="see-also"></a><span data-ttu-id="fcd6a-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fcd6a-135">See also</span></span>

- <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>
- <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>
- <xref:System.Workflow.Runtime.WorkflowRuntime>
- <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService>
- <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>
- [<span data-ttu-id="fcd6a-136">File di configurazione del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="fcd6a-136">Workflow Configuration Files</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))
- [<span data-ttu-id="fcd6a-137">\<add></span><span class="sxs-lookup"><span data-stu-id="fcd6a-137">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-commonparameters.md)
