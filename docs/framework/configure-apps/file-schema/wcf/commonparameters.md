---
title: '&lt;parametri comuni&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ffc20832-34d6-4622-8174-81924fd53514
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: bbb67714a58df0c5ccec86c7eac85a5194d780a5
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="ltcommonparametersgt"></a><span data-ttu-id="fe8be-102">&lt;parametri comuni&gt;</span><span class="sxs-lookup"><span data-stu-id="fe8be-102">&lt;commonParameters&gt;</span></span>
<span data-ttu-id="fe8be-103">Rappresenta una raccolta di parametri che vengono usati globalmente tra più servizi.</span><span class="sxs-lookup"><span data-stu-id="fe8be-103">Represents a collection of parameters that are used globally across multiple services.</span></span> <span data-ttu-id="fe8be-104">Questa raccolta in genere contiene la stringa di connessione del database che potrebbe essere condivisa dai servizi durevoli.</span><span class="sxs-lookup"><span data-stu-id="fe8be-104">This collection will typically include the database connection string that might be shared by durable services.</span></span>  
  
 <span data-ttu-id="fe8be-105">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="fe8be-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="fe8be-106">\<i comportamenti ></span><span class="sxs-lookup"><span data-stu-id="fe8be-106">\<behaviors></span></span>  
<span data-ttu-id="fe8be-107">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="fe8be-107">\<serviceBehaviors></span></span>  
<span data-ttu-id="fe8be-108">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="fe8be-108">\<behavior></span></span>  
<span data-ttu-id="fe8be-109">\<workflowRuntime ></span><span class="sxs-lookup"><span data-stu-id="fe8be-109">\<workflowRuntime></span></span>  
<span data-ttu-id="fe8be-110">\<Parametricomuni ></span><span class="sxs-lookup"><span data-stu-id="fe8be-110">\<commonParameters></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe8be-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fe8be-111">Syntax</span></span>  
  
```xml  
<workflowRuntime>  
   <commonParameters>  
      <add name="String" value="String" />  
   </commonParameters>  
</workflowRuntime>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fe8be-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="fe8be-112">Attributes and Elements</span></span>  
 <span data-ttu-id="fe8be-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="fe8be-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fe8be-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="fe8be-114">Attributes</span></span>  
 <span data-ttu-id="fe8be-115">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="fe8be-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="fe8be-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="fe8be-116">Child Elements</span></span>  
  
|<span data-ttu-id="fe8be-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="fe8be-117">Element</span></span>|<span data-ttu-id="fe8be-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fe8be-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fe8be-119">\<add></span><span class="sxs-lookup"><span data-stu-id="fe8be-119">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-commonparameters.md)|<span data-ttu-id="fe8be-120">Aggiunge alla raccolta una coppia nome/valore di parametri comuni usati dai servizi.</span><span class="sxs-lookup"><span data-stu-id="fe8be-120">Adds a name-value pair of common parameters used by services to the collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="fe8be-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="fe8be-121">Parent Elements</span></span>  
  
|<span data-ttu-id="fe8be-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="fe8be-122">Element</span></span>|<span data-ttu-id="fe8be-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fe8be-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fe8be-124">\<workflowRuntime ></span><span class="sxs-lookup"><span data-stu-id="fe8be-124">\<workflowRuntime></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/workflowruntime.md)|<span data-ttu-id="fe8be-125">Specifica le impostazioni di un'istanza della classe <xref:System.Workflow.Runtime.WorkflowRuntime> per ospitare servizi [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] basati sul flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="fe8be-125">Specifies settings for an instance of <xref:System.Workflow.Runtime.WorkflowRuntime> for hosting workflow-based [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] services.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fe8be-126">Note</span><span class="sxs-lookup"><span data-stu-id="fe8be-126">Remarks</span></span>  
 <span data-ttu-id="fe8be-127">L'elemento `<commonParameters>` definisce qualsiasi parametro usato globalmente tra più servizi, ad esempio `ConnectionString` quando si usa <xref:System.Workflow.Runtime.Hosting.SharedConnectionWorkflowCommitWorkBatchService>.</span><span class="sxs-lookup"><span data-stu-id="fe8be-127">The `<commonParameters>` element defines any parameters that are used globally across multiple services, for example `ConnectionString` when using the <xref:System.Workflow.Runtime.Hosting.SharedConnectionWorkflowCommitWorkBatchService>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fe8be-128">Il servizio di rilevamento SQL non utilizzerà in modo coerente il valore `ConnectionString` nel caso in cui venga specificato nella sezione `<commonParameters>`.</span><span class="sxs-lookup"><span data-stu-id="fe8be-128">SQL Tracking service does not consistently use the `ConnectionString` value if it is specified in the `<commonParameters>` section.</span></span> <span data-ttu-id="fe8be-129">Alcune delle relative operazioni, ad esempio il recupero della proprietà `StateMachineWorkflowInstance.StateHistory`, potrebbero non riuscire.</span><span class="sxs-lookup"><span data-stu-id="fe8be-129">Some of its operations such as retrieving the `StateMachineWorkflowInstance.StateHistory` property may fail.</span></span> <span data-ttu-id="fe8be-130">Una soluzione alternativa consente nello specificare l'attributo `ConnectionString` nella sezione di configurazione per il provider di rilevamento, come indicato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="fe8be-130">To workaround this, specify the `ConnectionString` attribute in the configuration section for tracking provider, as indicated in the following example.</span></span>  
  
 `<add`  
  
 `type="System.Workflow.Runtime.Tracking.SqlTrackingService, System.Workflow.Runtime, Version=3.0.00000.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35"`  
  
 `ConnectionString="Data Source=localhost;Initial Catalog=Partner20WFTP;Integrated Security=True;" />`  
  
 <span data-ttu-id="fe8be-131">È possibile consentire a servizi che eseguono il commit di batch di lavoro su archivi di persistenza, ad esempio <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService> e <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>, di ritentare la transazione usando il parametro `EnableRetries`, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="fe8be-131">For services that commit work batches to persistence stores, such as <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService> and <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>, you can enable them to retry their transaction by using the `EnableRetries` parameter as shown in the following example:</span></span>  
  
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
  
 <span data-ttu-id="fe8be-132">Si noti che il `EnableRetries` parametro può essere impostato a livello globale (come illustrato nel *Parametricomuni* sezione) o per servizi individuali che supportano `EnableRetries` (come illustrato nel *servizi*sezione).</span><span class="sxs-lookup"><span data-stu-id="fe8be-132">Notice that the `EnableRetries` parameter can be set either at a global level (as shown in the *CommonParameters* section) or for individual services that support `EnableRetries` (as shown in the *Services* section).</span></span>  
  
 <span data-ttu-id="fe8be-133">Nel codice di esempio seguente viene illustrato come modificare i parametri comuni a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="fe8be-133">The following sample code shows how to change the common parameters programmatically.</span></span>  
  
```  
Configuration config=WebConfigurationManager.OpenWebConfiguration("/Workflow", "Default Web Site", null, "localhost");  
WorkflowRuntimeSection wfruntime=config.GetSection("WorkflowRuntime") as WorkflowRuntimeSection;  
NameValueConfigurationCollection commonParameters=wfruntime.CommonParameters;  
commonParameters["ConnectionString"].Value="another connection string";  
config.Save();  
```  
  
 <span data-ttu-id="fe8be-134">Per ulteriori informazioni sull'utilizzo di un file di configurazione per controllare il comportamento di un <xref:System.Workflow.Runtime.WorkflowRuntime> oggetto di un'applicazione host di Windows Workflow Foundation, vedere [i file di configurazione del flusso di lavoro](http://msdn.microsoft.com/en-us/ada4bb90-6c9d-4f3d-a9d0-b559bb0f9909).</span><span class="sxs-lookup"><span data-stu-id="fe8be-134">For more information about using a configuration file to control the behavior of a <xref:System.Workflow.Runtime.WorkflowRuntime> object of a Windows Workflow Foundation host application, see [Workflow Configuration Files](http://msdn.microsoft.com/en-us/ada4bb90-6c9d-4f3d-a9d0-b559bb0f9909).</span></span>  
  
## <a name="example"></a><span data-ttu-id="fe8be-135">Esempio</span><span class="sxs-lookup"><span data-stu-id="fe8be-135">Example</span></span>  
  
```xml  
<commonParameters>  
   <add name="ConnectionString" value="Initial Catalog=WorkflowStore;Data Source=localhost;Integrated Security=SSPI;"/>  
   <add name="EnableRetries" value="true"/>  
</commonParameters>  
```  
  
## <a name="see-also"></a><span data-ttu-id="fe8be-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fe8be-136">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>  
 <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>  
 <xref:System.Workflow.Runtime.WorkflowRuntime>  
 <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService>  
 <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>  
 [<span data-ttu-id="fe8be-137">File di configurazione del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="fe8be-137">Workflow Configuration Files</span></span>](http://msdn.microsoft.com/en-us/ada4bb90-6c9d-4f3d-a9d0-b559bb0f9909)  
 [<span data-ttu-id="fe8be-138">\<add></span><span class="sxs-lookup"><span data-stu-id="fe8be-138">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-commonparameters.md)
