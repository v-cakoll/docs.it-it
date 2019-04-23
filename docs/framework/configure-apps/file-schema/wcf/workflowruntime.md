---
title: <workflowRuntime>
ms.date: 03/30/2017
ms.assetid: 304c70fa-78d1-4d0f-b89f-0ca23d734c6f
ms.openlocfilehash: db5e1083c07d4e204eb19eaae9257ed44439132e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59206564"
---
# <a name="workflowruntime"></a><span data-ttu-id="2e491-101">\<workflowRuntime></span><span class="sxs-lookup"><span data-stu-id="2e491-101">\<workflowRuntime></span></span>
<span data-ttu-id="2e491-102">Specifica le impostazioni per un'istanza di <xref:System.Workflow.Runtime.WorkflowRuntime> per ospitare i servizi Windows Communication Foundation (WCF) in base al flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="2e491-102">Specifies settings for an instance of <xref:System.Workflow.Runtime.WorkflowRuntime> for hosting workflow-based Windows Communication Foundation (WCF) services.</span></span>  
  
 <span data-ttu-id="2e491-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="2e491-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="2e491-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="2e491-104">\<behaviors></span></span>  
<span data-ttu-id="2e491-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="2e491-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="2e491-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="2e491-106">\<behavior></span></span>  
<span data-ttu-id="2e491-107">\<workflowRuntime></span><span class="sxs-lookup"><span data-stu-id="2e491-107">\<workflowRuntime></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e491-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2e491-108">Syntax</span></span>  
  
```xml  
<workflowRuntime cachedInstanceExpiration="TimeSpan"
                 enablePerformanceCounters="Boolean"
                 name="String"
                 validateOnCreate="Boolean">
  <commonParameters>
    <add name="String"
         value="String" />
  </commonParameters>
  <services>
    <add type="String" />
  </services>
</workflowRuntime>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2e491-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="2e491-109">Attributes and Elements</span></span>  
 <span data-ttu-id="2e491-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="2e491-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2e491-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="2e491-111">Attributes</span></span>  
  
|<span data-ttu-id="2e491-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="2e491-112">Attribute</span></span>|<span data-ttu-id="2e491-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2e491-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2e491-114">cachedInstanceExpiration</span><span class="sxs-lookup"><span data-stu-id="2e491-114">cachedInstanceExpiration</span></span>|<span data-ttu-id="2e491-115">Valore <xref:System.TimeSpan> facoltativo che specifica la durata massima di memorizzazione in stato inattivo di un'istanza del flusso di lavoro prima che venga interrotta o scaricata automaticamente.</span><span class="sxs-lookup"><span data-stu-id="2e491-115">An optional <xref:System.TimeSpan> value that specifies the maximum duration a workflow instance can stay in-memory in idle state before it is forcefully unloaded or aborted.</span></span> <span data-ttu-id="2e491-116">Se l'attributo `PersistenceService` di workflowruntime esegue il metodo unloadOnIdle, questo attributo viene ignorato.</span><span class="sxs-lookup"><span data-stu-id="2e491-116">If the workflowruntime has `PersistenceService` which performs unloadOnIdle, this attribute is ignored.</span></span>|  
|<span data-ttu-id="2e491-117">enablePerformanceCounters</span><span class="sxs-lookup"><span data-stu-id="2e491-117">enablePerformanceCounters</span></span>|<span data-ttu-id="2e491-118">Valore booleano facoltativo che specifica se i contatori delle prestazioni sono attivi.</span><span class="sxs-lookup"><span data-stu-id="2e491-118">An optional Boolean value that specifies whether performance counters are enabled.</span></span> <span data-ttu-id="2e491-119">I contatori delle prestazioni forniscono informazioni su varie statistiche correlate al flusso di lavoro, ma provocano una riduzione delle prestazioni quando il motore di runtime del flusso di lavoro viene avviato e quando le istanze del flusso di lavoro sono in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="2e491-119">Performance counters provide information on various workflow-related statistics, but they cause a performance penalty when the workflow runtime engine starts, and when workflow instances are running.</span></span> <span data-ttu-id="2e491-120">Il valore predefinito è `true`.</span><span class="sxs-lookup"><span data-stu-id="2e491-120">The default value is `true`.</span></span>|  
|<span data-ttu-id="2e491-121">name</span><span class="sxs-lookup"><span data-stu-id="2e491-121">name</span></span>|<span data-ttu-id="2e491-122">Stringa contenente il nome del motore di runtime del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="2e491-122">A string containing the name of the workflow runtime engine.</span></span> <span data-ttu-id="2e491-123">Il nome viene usato in output per distinguere questo runtime da altri runtime che potrebbero essere in esecuzione nel sistema, ad esempio nei contatori delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="2e491-123">The name is used in output to distinguish this runtime from other runtimes that may be running on the system, for example, in performance counters.</span></span><br /><br /> <span data-ttu-id="2e491-124">Il valore predefinito è una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="2e491-124">The default is an empty string.</span></span>|  
|<span data-ttu-id="2e491-125">validateOnCreate</span><span class="sxs-lookup"><span data-stu-id="2e491-125">validateOnCreate</span></span>|<span data-ttu-id="2e491-126">Valore booleano facoltativo che specifica se all'apertura dell'elemento WorkflowServiceHost verrà eseguita la convalida della definizione del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="2e491-126">An optional Boolean value that specifies whether validation of workflow definition will occur when the WorkflowServiceHost is opened.</span></span>  <span data-ttu-id="2e491-127">Quando questo attributo viene impostato su `true`, la convalida del flusso di lavoro viene eseguita ogni volta che viene chiamato il metodo `WorkflowServiceHost.Open`.</span><span class="sxs-lookup"><span data-stu-id="2e491-127">When this attribute is set to `true`, the workflow validation is executed every time `WorkflowServiceHost.Open` is called.</span></span> <span data-ttu-id="2e491-128">Se vengono individuati errori di convalida, viene generata un'eccezione <xref:System.Workflow.ComponentModel.Compiler.WorkflowValidationFailedException>.</span><span class="sxs-lookup"><span data-stu-id="2e491-128">If validation errors are found, a <xref:System.Workflow.ComponentModel.Compiler.WorkflowValidationFailedException> error is thrown.</span></span><br /><br /> <span data-ttu-id="2e491-129">Quando questa proprietà è impostata su `false` la definizione del flusso di lavoro non viene convalidata.</span><span class="sxs-lookup"><span data-stu-id="2e491-129">When this property is set to `false`, no Workflow definition validation will happen.</span></span><br /><br /> <span data-ttu-id="2e491-130">Il valore predefinito di questa proprietà è `true`.</span><span class="sxs-lookup"><span data-stu-id="2e491-130">The default value for this property is `true`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2e491-131">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="2e491-131">Child Elements</span></span>  
  
|<span data-ttu-id="2e491-132">Elemento</span><span class="sxs-lookup"><span data-stu-id="2e491-132">Element</span></span>|<span data-ttu-id="2e491-133">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2e491-133">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2e491-134">commonParameters</span><span class="sxs-lookup"><span data-stu-id="2e491-134">commonParameters</span></span>|<span data-ttu-id="2e491-135">Raccolta di parametri comuni usati dai servizi.</span><span class="sxs-lookup"><span data-stu-id="2e491-135">A collection of common parameters used by services.</span></span> <span data-ttu-id="2e491-136">Questa raccolta in genere contiene la stringa di connessione del database che potrebbe essere condivisa dai servizi durevoli.</span><span class="sxs-lookup"><span data-stu-id="2e491-136">This collection will typically include the database connection string that might be shared by durable services.</span></span>|  
|<span data-ttu-id="2e491-137">servizi</span><span class="sxs-lookup"><span data-stu-id="2e491-137">services</span></span>|<span data-ttu-id="2e491-138">Raccolta di servizi da aggiungere al motore di <xref:System.Workflow.Runtime.WorkflowRuntime>.</span><span class="sxs-lookup"><span data-stu-id="2e491-138">A collection of services that will be added to the <xref:System.Workflow.Runtime.WorkflowRuntime> engine.</span></span> <span data-ttu-id="2e491-139">Gli elementi sono di tipo <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="2e491-139">The elements are of type <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span></span>  <span data-ttu-id="2e491-140">I servizi specificati nella raccolta verranno inizializzati dal motore di runtime del flusso di lavoro e verranno aggiunti ai relativi servizi quando verrà chiamato il costruttore <xref:System.Workflow.Runtime.WorkflowRuntime> appropriato.</span><span class="sxs-lookup"><span data-stu-id="2e491-140">The services specified in the collection will be initialized by the workflow runtime engine and added to its services when the appropriate <xref:System.Workflow.Runtime.WorkflowRuntime> constructor is called.</span></span> <span data-ttu-id="2e491-141">Pertanto, i servizi specificati nella raccolta devono seguire regole precise riguardanti le firme dei relativi costruttori.</span><span class="sxs-lookup"><span data-stu-id="2e491-141">Therefore, the services specified in the collection must follow certain rules about the signatures of their constructors.</span></span> <span data-ttu-id="2e491-142">Per altre informazioni, vedere <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="2e491-142">See <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> for more information.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2e491-143">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="2e491-143">Parent Elements</span></span>  
  
|<span data-ttu-id="2e491-144">Elemento</span><span class="sxs-lookup"><span data-stu-id="2e491-144">Element</span></span>|<span data-ttu-id="2e491-145">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2e491-145">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2e491-146">\<behavior></span><span class="sxs-lookup"><span data-stu-id="2e491-146">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="2e491-147">Specifica un elemento di comportamento.</span><span class="sxs-lookup"><span data-stu-id="2e491-147">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2e491-148">Note</span><span class="sxs-lookup"><span data-stu-id="2e491-148">Remarks</span></span>  
 <span data-ttu-id="2e491-149">Per altre informazioni sull'uso di un file di configurazione per controllare il comportamento di un <xref:System.Workflow.Runtime.WorkflowRuntime> oggetto di un'applicazione host di Windows Workflow Foundation, vedere [i file di configurazione del flusso di lavoro](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="2e491-149">For more information on using a configuration file to control the behavior of a <xref:System.Workflow.Runtime.WorkflowRuntime> object of a Windows Workflow Foundation host application, see [Workflow Configuration Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2e491-150">Esempio</span><span class="sxs-lookup"><span data-stu-id="2e491-150">Example</span></span>  
  
```xml  
<serviceBehaviors>
   <behavior name="ServiceBehavior">
      <workflowRuntime name="WorkflowServiceHostRuntime"
                       validateOnCreate="true"
                       enablePerformanceCounters="true">
         <commonParameters>
            <add name="ConnectionString" value="Initial Catalog=WorkflowStore;Data Source=localhost;Integrated Security=SSPI;" />
            <add name="EnableRetries" value="True" />
         </commonParameters>
         <services>
             <add type="NetFx.Checkin.Scenario.WorkflowServices.WorkflowBasedServices.Common.TestPersistenceService.FilePersistenceService, NetFx.Checkin.Scenario.WorkflowServices.WorkflowBasedServices.Common"/>
         </services>
      </workflowRuntime>
   </behavior>
</serviceBehaviors>
```  
  
## <a name="see-also"></a><span data-ttu-id="2e491-151">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2e491-151">See also</span></span>

- <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>
- <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>
- <xref:System.Workflow.Runtime.WorkflowRuntime>
- <span data-ttu-id="2e491-152">[File di configurazione del flusso di lavoro](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="2e491-152">[Workflow Configuration Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span></span>
