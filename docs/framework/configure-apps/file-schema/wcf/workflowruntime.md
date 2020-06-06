---
title: <workflowRuntime>
ms.date: 03/30/2017
ms.assetid: 304c70fa-78d1-4d0f-b89f-0ca23d734c6f
ms.openlocfilehash: d12656b77fa219080382603fd04a542d2fa9064a
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70399080"
---
# \<workflowRuntime>
<span data-ttu-id="1e7e9-101">Specifica le impostazioni per un'istanza di <xref:System.Workflow.Runtime.WorkflowRuntime> per l'hosting di servizi di Windows Communication Foundation (WCF) basati sul flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="1e7e9-101">Specifies settings for an instance of <xref:System.Workflow.Runtime.WorkflowRuntime> for hosting workflow-based Windows Communication Foundation (WCF) services.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowRuntime>**  
  
## <a name="syntax"></a><span data-ttu-id="1e7e9-102">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1e7e9-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1e7e9-103">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="1e7e9-103">Attributes and Elements</span></span>  
 <span data-ttu-id="1e7e9-104">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="1e7e9-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1e7e9-105">Attributi</span><span class="sxs-lookup"><span data-stu-id="1e7e9-105">Attributes</span></span>  
  
|<span data-ttu-id="1e7e9-106">Attributo</span><span class="sxs-lookup"><span data-stu-id="1e7e9-106">Attribute</span></span>|<span data-ttu-id="1e7e9-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1e7e9-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1e7e9-108">cachedInstanceExpiration</span><span class="sxs-lookup"><span data-stu-id="1e7e9-108">cachedInstanceExpiration</span></span>|<span data-ttu-id="1e7e9-109">Valore <xref:System.TimeSpan> facoltativo che specifica la durata massima di memorizzazione in stato inattivo di un'istanza del flusso di lavoro prima che venga interrotta o scaricata automaticamente.</span><span class="sxs-lookup"><span data-stu-id="1e7e9-109">An optional <xref:System.TimeSpan> value that specifies the maximum duration a workflow instance can stay in-memory in idle state before it is forcefully unloaded or aborted.</span></span> <span data-ttu-id="1e7e9-110">Se l'attributo `PersistenceService` di workflowruntime esegue il metodo unloadOnIdle, questo attributo viene ignorato.</span><span class="sxs-lookup"><span data-stu-id="1e7e9-110">If the workflowruntime has `PersistenceService` which performs unloadOnIdle, this attribute is ignored.</span></span>|  
|<span data-ttu-id="1e7e9-111">enablePerformanceCounters</span><span class="sxs-lookup"><span data-stu-id="1e7e9-111">enablePerformanceCounters</span></span>|<span data-ttu-id="1e7e9-112">Valore booleano facoltativo che specifica se i contatori delle prestazioni sono attivi.</span><span class="sxs-lookup"><span data-stu-id="1e7e9-112">An optional Boolean value that specifies whether performance counters are enabled.</span></span> <span data-ttu-id="1e7e9-113">I contatori delle prestazioni forniscono informazioni su varie statistiche correlate al flusso di lavoro, ma provocano una riduzione delle prestazioni quando il motore di runtime del flusso di lavoro viene avviato e quando le istanze del flusso di lavoro sono in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="1e7e9-113">Performance counters provide information on various workflow-related statistics, but they cause a performance penalty when the workflow runtime engine starts, and when workflow instances are running.</span></span> <span data-ttu-id="1e7e9-114">Il valore predefinito è `true`.</span><span class="sxs-lookup"><span data-stu-id="1e7e9-114">The default value is `true`.</span></span>|  
|<span data-ttu-id="1e7e9-115">name</span><span class="sxs-lookup"><span data-stu-id="1e7e9-115">name</span></span>|<span data-ttu-id="1e7e9-116">Stringa contenente il nome del motore di runtime del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="1e7e9-116">A string containing the name of the workflow runtime engine.</span></span> <span data-ttu-id="1e7e9-117">Il nome viene usato in output per distinguere questo runtime da altri runtime che potrebbero essere in esecuzione nel sistema, ad esempio nei contatori delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="1e7e9-117">The name is used in output to distinguish this runtime from other runtimes that may be running on the system, for example, in performance counters.</span></span><br /><br /> <span data-ttu-id="1e7e9-118">Il valore predefinito è una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="1e7e9-118">The default is an empty string.</span></span>|  
|<span data-ttu-id="1e7e9-119">validateOnCreate</span><span class="sxs-lookup"><span data-stu-id="1e7e9-119">validateOnCreate</span></span>|<span data-ttu-id="1e7e9-120">Valore booleano facoltativo che specifica se all'apertura dell'elemento WorkflowServiceHost verrà eseguita la convalida della definizione del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="1e7e9-120">An optional Boolean value that specifies whether validation of workflow definition will occur when the WorkflowServiceHost is opened.</span></span>  <span data-ttu-id="1e7e9-121">Quando questo attributo viene impostato su `true`, la convalida del flusso di lavoro viene eseguita ogni volta che viene chiamato il metodo `WorkflowServiceHost.Open`.</span><span class="sxs-lookup"><span data-stu-id="1e7e9-121">When this attribute is set to `true`, the workflow validation is executed every time `WorkflowServiceHost.Open` is called.</span></span> <span data-ttu-id="1e7e9-122">Se vengono individuati errori di convalida, viene generata un'eccezione <xref:System.Workflow.ComponentModel.Compiler.WorkflowValidationFailedException>.</span><span class="sxs-lookup"><span data-stu-id="1e7e9-122">If validation errors are found, a <xref:System.Workflow.ComponentModel.Compiler.WorkflowValidationFailedException> error is thrown.</span></span><br /><br /> <span data-ttu-id="1e7e9-123">Quando questa proprietà è impostata su `false` la definizione del flusso di lavoro non viene convalidata.</span><span class="sxs-lookup"><span data-stu-id="1e7e9-123">When this property is set to `false`, no Workflow definition validation will happen.</span></span><br /><br /> <span data-ttu-id="1e7e9-124">Il valore predefinito di questa proprietà è `true`.</span><span class="sxs-lookup"><span data-stu-id="1e7e9-124">The default value for this property is `true`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1e7e9-125">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="1e7e9-125">Child Elements</span></span>  
  
|<span data-ttu-id="1e7e9-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="1e7e9-126">Element</span></span>|<span data-ttu-id="1e7e9-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1e7e9-127">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1e7e9-128">commonParameters</span><span class="sxs-lookup"><span data-stu-id="1e7e9-128">commonParameters</span></span>|<span data-ttu-id="1e7e9-129">Raccolta di parametri comuni usati dai servizi.</span><span class="sxs-lookup"><span data-stu-id="1e7e9-129">A collection of common parameters used by services.</span></span> <span data-ttu-id="1e7e9-130">Questa raccolta in genere contiene la stringa di connessione del database che potrebbe essere condivisa dai servizi durevoli.</span><span class="sxs-lookup"><span data-stu-id="1e7e9-130">This collection will typically include the database connection string that might be shared by durable services.</span></span>|  
|<span data-ttu-id="1e7e9-131">services</span><span class="sxs-lookup"><span data-stu-id="1e7e9-131">services</span></span>|<span data-ttu-id="1e7e9-132">Raccolta di servizi da aggiungere al motore di <xref:System.Workflow.Runtime.WorkflowRuntime>.</span><span class="sxs-lookup"><span data-stu-id="1e7e9-132">A collection of services that will be added to the <xref:System.Workflow.Runtime.WorkflowRuntime> engine.</span></span> <span data-ttu-id="1e7e9-133">Gli elementi sono di tipo <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="1e7e9-133">The elements are of type <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span></span>  <span data-ttu-id="1e7e9-134">I servizi specificati nella raccolta verranno inizializzati dal motore di runtime del flusso di lavoro e verranno aggiunti ai relativi servizi quando verrà chiamato il costruttore <xref:System.Workflow.Runtime.WorkflowRuntime> appropriato.</span><span class="sxs-lookup"><span data-stu-id="1e7e9-134">The services specified in the collection will be initialized by the workflow runtime engine and added to its services when the appropriate <xref:System.Workflow.Runtime.WorkflowRuntime> constructor is called.</span></span> <span data-ttu-id="1e7e9-135">Pertanto, i servizi specificati nella raccolta devono seguire regole precise riguardanti le firme dei relativi costruttori.</span><span class="sxs-lookup"><span data-stu-id="1e7e9-135">Therefore, the services specified in the collection must follow certain rules about the signatures of their constructors.</span></span> <span data-ttu-id="1e7e9-136">Per altre informazioni, vedere <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="1e7e9-136">See <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> for more information.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1e7e9-137">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="1e7e9-137">Parent Elements</span></span>  
  
|<span data-ttu-id="1e7e9-138">Elemento</span><span class="sxs-lookup"><span data-stu-id="1e7e9-138">Element</span></span>|<span data-ttu-id="1e7e9-139">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1e7e9-139">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="1e7e9-140">Specifica un elemento di comportamento.</span><span class="sxs-lookup"><span data-stu-id="1e7e9-140">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1e7e9-141">Commenti</span><span class="sxs-lookup"><span data-stu-id="1e7e9-141">Remarks</span></span>  
 <span data-ttu-id="1e7e9-142">Per ulteriori informazioni sull'utilizzo di un file di configurazione per controllare il comportamento di un <xref:System.Workflow.Runtime.WorkflowRuntime> oggetto di un'applicazione host Windows Workflow Foundation, vedere [file di configurazione del flusso di lavoro](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="1e7e9-142">For more information on using a configuration file to control the behavior of a <xref:System.Workflow.Runtime.WorkflowRuntime> object of a Windows Workflow Foundation host application, see [Workflow Configuration Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1e7e9-143">Esempio</span><span class="sxs-lookup"><span data-stu-id="1e7e9-143">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="1e7e9-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1e7e9-144">See also</span></span>

- <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>
- <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>
- <xref:System.Workflow.Runtime.WorkflowRuntime>
- <span data-ttu-id="1e7e9-145">[File di configurazione del flusso di lavoro](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="1e7e9-145">[Workflow Configuration Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span></span>
