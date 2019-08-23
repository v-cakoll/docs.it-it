---
title: <commonParameters>
ms.date: 03/30/2017
ms.assetid: ffc20832-34d6-4622-8174-81924fd53514
ms.openlocfilehash: a92a81062e92f832be78af2bfd75270390eaac3e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919486"
---
# <a name="commonparameters"></a><span data-ttu-id="dd460-101">\<commonParameters></span><span class="sxs-lookup"><span data-stu-id="dd460-101">\<commonParameters></span></span>
<span data-ttu-id="dd460-102">Rappresenta una raccolta di parametri che vengono usati globalmente tra più servizi.</span><span class="sxs-lookup"><span data-stu-id="dd460-102">Represents a collection of parameters that are used globally across multiple services.</span></span> <span data-ttu-id="dd460-103">Questa raccolta in genere contiene la stringa di connessione del database che potrebbe essere condivisa dai servizi durevoli.</span><span class="sxs-lookup"><span data-stu-id="dd460-103">This collection will typically include the database connection string that might be shared by durable services.</span></span>  
  
 <span data-ttu-id="dd460-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="dd460-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="dd460-105">\<comportamenti ></span><span class="sxs-lookup"><span data-stu-id="dd460-105">\<behaviors></span></span>  
<span data-ttu-id="dd460-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="dd460-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="dd460-107">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="dd460-107">\<behavior></span></span>  
<span data-ttu-id="dd460-108">\<workflowRuntime></span><span class="sxs-lookup"><span data-stu-id="dd460-108">\<workflowRuntime></span></span>  
<span data-ttu-id="dd460-109">\<commonParameters></span><span class="sxs-lookup"><span data-stu-id="dd460-109">\<commonParameters></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd460-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dd460-110">Syntax</span></span>  
  
```xml  
<workflowRuntime>
  <commonParameters>
    <add name="String"
         value="String" />
  </commonParameters>
</workflowRuntime>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dd460-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="dd460-111">Attributes and Elements</span></span>  
 <span data-ttu-id="dd460-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="dd460-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dd460-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="dd460-113">Attributes</span></span>  
 <span data-ttu-id="dd460-114">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="dd460-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="dd460-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="dd460-115">Child Elements</span></span>  
  
|<span data-ttu-id="dd460-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="dd460-116">Element</span></span>|<span data-ttu-id="dd460-117">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="dd460-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dd460-118">\<add></span><span class="sxs-lookup"><span data-stu-id="dd460-118">\<add></span></span>](add-of-commonparameters.md)|<span data-ttu-id="dd460-119">Aggiunge alla raccolta una coppia nome/valore di parametri comuni usati dai servizi.</span><span class="sxs-lookup"><span data-stu-id="dd460-119">Adds a name-value pair of common parameters used by services to the collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="dd460-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="dd460-120">Parent Elements</span></span>  
  
|<span data-ttu-id="dd460-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="dd460-121">Element</span></span>|<span data-ttu-id="dd460-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dd460-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dd460-123">\<workflowRuntime></span><span class="sxs-lookup"><span data-stu-id="dd460-123">\<workflowRuntime></span></span>](workflowruntime.md)|<span data-ttu-id="dd460-124">Specifica le impostazioni per un'istanza <xref:System.Workflow.Runtime.WorkflowRuntime> di per l'hosting di servizi di Windows Communication Foundation (WCF) basati sul flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="dd460-124">Specifies settings for an instance of <xref:System.Workflow.Runtime.WorkflowRuntime> for hosting workflow-based Windows Communication Foundation (WCF) services.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dd460-125">Note</span><span class="sxs-lookup"><span data-stu-id="dd460-125">Remarks</span></span>  
 <span data-ttu-id="dd460-126">L'elemento `<commonParameters>` definisce qualsiasi parametro usato globalmente tra più servizi, ad esempio `ConnectionString` quando si usa <xref:System.Workflow.Runtime.Hosting.SharedConnectionWorkflowCommitWorkBatchService>.</span><span class="sxs-lookup"><span data-stu-id="dd460-126">The `<commonParameters>` element defines any parameters that are used globally across multiple services, for example `ConnectionString` when using the <xref:System.Workflow.Runtime.Hosting.SharedConnectionWorkflowCommitWorkBatchService>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="dd460-127">Il servizio di rilevamento SQL non utilizzerà in modo coerente il valore `ConnectionString` nel caso in cui venga specificato nella sezione `<commonParameters>`.</span><span class="sxs-lookup"><span data-stu-id="dd460-127">SQL Tracking service does not consistently use the `ConnectionString` value if it is specified in the `<commonParameters>` section.</span></span> <span data-ttu-id="dd460-128">Alcune delle relative operazioni, ad esempio il recupero della proprietà `StateMachineWorkflowInstance.StateHistory`, potrebbero non riuscire.</span><span class="sxs-lookup"><span data-stu-id="dd460-128">Some of its operations such as retrieving the `StateMachineWorkflowInstance.StateHistory` property may fail.</span></span> <span data-ttu-id="dd460-129">Una soluzione alternativa consente nello specificare l'attributo `ConnectionString` nella sezione di configurazione per il provider di rilevamento, come indicato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="dd460-129">To workaround this, specify the `ConnectionString` attribute in the configuration section for tracking provider, as indicated in the following example.</span></span>  
  
 `<add`  
  
 `type="System.Workflow.Runtime.Tracking.SqlTrackingService, System.Workflow.Runtime, Version=3.0.00000.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35"`  
  
 `ConnectionString="Data Source=localhost;Initial Catalog=Partner20WFTP;Integrated Security=True;" />`  
  
 <span data-ttu-id="dd460-130">È possibile consentire a servizi che eseguono il commit di batch di lavoro su archivi di persistenza, ad esempio <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService> e <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>, di ritentare la transazione usando il parametro `EnableRetries`, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="dd460-130">For services that commit work batches to persistence stores, such as <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService> and <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>, you can enable them to retry their transaction by using the `EnableRetries` parameter as shown in the following example:</span></span>  
  
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
  
 <span data-ttu-id="dd460-131">Si noti che `EnableRetries` il parametro può essere impostato a livello globale (come illustrato nella sezione *parametricomuni* ) o per i singoli servizi che supportano `EnableRetries` (come illustrato nella sezione *Servizi* ).</span><span class="sxs-lookup"><span data-stu-id="dd460-131">Notice that the `EnableRetries` parameter can be set either at a global level (as shown in the *CommonParameters* section) or for individual services that support `EnableRetries` (as shown in the *Services* section).</span></span>  
  
 <span data-ttu-id="dd460-132">Nel codice di esempio seguente viene illustrato come modificare i parametri comuni a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="dd460-132">The following sample code shows how to change the common parameters programmatically.</span></span>  
  
```  
Configuration config=WebConfigurationManager.OpenWebConfiguration("/Workflow", "Default Web Site", null, "localhost");  
WorkflowRuntimeSection wfruntime=config.GetSection("WorkflowRuntime") as WorkflowRuntimeSection;  
NameValueConfigurationCollection commonParameters=wfruntime.CommonParameters;  
commonParameters["ConnectionString"].Value="another connection string";  
config.Save();  
```  
  
 <span data-ttu-id="dd460-133">Per ulteriori informazioni sull'utilizzo di un file di configurazione per controllare il comportamento <xref:System.Workflow.Runtime.WorkflowRuntime> di un oggetto di un'applicazione host Windows Workflow Foundation, vedere [file di configurazione del flusso di lavoro](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="dd460-133">For more information about using a configuration file to control the behavior of a <xref:System.Workflow.Runtime.WorkflowRuntime> object of a Windows Workflow Foundation host application, see [Workflow Configuration Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="dd460-134">Esempio</span><span class="sxs-lookup"><span data-stu-id="dd460-134">Example</span></span>  
  
```xml  
<commonParameters>
   <add name="ConnectionString"
        value="Initial Catalog=WorkflowStore;Data Source=localhost;Integrated Security=SSPI;" />
   <add name="EnableRetries"
        value="true" />
</commonParameters>
```  
  
## <a name="see-also"></a><span data-ttu-id="dd460-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dd460-135">See also</span></span>

- <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>
- <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>
- <xref:System.Workflow.Runtime.WorkflowRuntime>
- <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService>
- <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>
- <span data-ttu-id="dd460-136">[File di configurazione del flusso di lavoro](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="dd460-136">[Workflow Configuration Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span></span>
- [<span data-ttu-id="dd460-137">\<add></span><span class="sxs-lookup"><span data-stu-id="dd460-137">\<add></span></span>](add-of-commonparameters.md)
