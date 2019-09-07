---
title: <add> di <commonParameters>
ms.date: 03/30/2017
ms.assetid: 3713bf25-20c8-455f-bb85-de46b6487932
ms.openlocfilehash: d682acd7fff6bab2c66660a028f8a75b780e21d2
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400671"
---
# <a name="add-of-commonparameters"></a><span data-ttu-id="2003b-102">\<aggiungere > di \<parametricomuni ></span><span class="sxs-lookup"><span data-stu-id="2003b-102">\<add> of \<commonParameters></span></span>
<span data-ttu-id="2003b-103">Specifica una coppia nome/valore di parametri che vengono usati globalmente tra più servizi.</span><span class="sxs-lookup"><span data-stu-id="2003b-103">Specifies a name-value pair of parameters that are used globally across multiple services.</span></span> <span data-ttu-id="2003b-104">Questo parametro in genere contiene una stringa di connessione al database che potrebbe essere condivisa dai servizi durevoli.</span><span class="sxs-lookup"><span data-stu-id="2003b-104">Typically this parameter includes the database connection string that might be shared by durable services.</span></span>  
  
<span data-ttu-id="2003b-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="2003b-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="2003b-106">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="2003b-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="2003b-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamenti >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="2003b-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="2003b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> serviceBehaviors**](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="2003b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="2003b-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamento >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="2003b-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="2003b-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> workflowRuntime**](workflowruntime.md)</span><span class="sxs-lookup"><span data-stu-id="2003b-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowRuntime>**](workflowruntime.md)</span></span>\
<span data-ttu-id="2003b-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> Parametricomuni**](commonparameters.md)</span><span class="sxs-lookup"><span data-stu-id="2003b-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<commonParameters>**](commonparameters.md)</span></span>\
<span data-ttu-id="2003b-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Aggiungi >**</span><span class="sxs-lookup"><span data-stu-id="2003b-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2003b-113">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2003b-113">Syntax</span></span>  
  
```xml  
<workflowRuntime>
  <commonParameters>
    <add name="String" value="String" />
  </commonParameters>
</workflowRuntime>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2003b-114">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="2003b-114">Attributes and Elements</span></span>  
 <span data-ttu-id="2003b-115">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="2003b-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2003b-116">Attributi</span><span class="sxs-lookup"><span data-stu-id="2003b-116">Attributes</span></span>  
  
|<span data-ttu-id="2003b-117">Attributo</span><span class="sxs-lookup"><span data-stu-id="2003b-117">Attribute</span></span>|<span data-ttu-id="2003b-118">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="2003b-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2003b-119">name</span><span class="sxs-lookup"><span data-stu-id="2003b-119">name</span></span>|<span data-ttu-id="2003b-120">Nome del parametro specificato per un servizio.</span><span class="sxs-lookup"><span data-stu-id="2003b-120">The name of the parameter specified for a service.</span></span>|  
|<span data-ttu-id="2003b-121">value</span><span class="sxs-lookup"><span data-stu-id="2003b-121">value</span></span>|<span data-ttu-id="2003b-122">Valore del parametro specificato per un servizio.</span><span class="sxs-lookup"><span data-stu-id="2003b-122">The value of the parameter specified for a service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2003b-123">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="2003b-123">Child Elements</span></span>  
 <span data-ttu-id="2003b-124">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="2003b-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2003b-125">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="2003b-125">Parent Elements</span></span>  
  
|<span data-ttu-id="2003b-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="2003b-126">Element</span></span>|<span data-ttu-id="2003b-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2003b-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2003b-128">\<commonParameters></span><span class="sxs-lookup"><span data-stu-id="2003b-128">\<commonParameters></span></span>](commonparameters.md)|<span data-ttu-id="2003b-129">Raccolta di parametri comuni usati dai servizi.</span><span class="sxs-lookup"><span data-stu-id="2003b-129">A collection of common parameters used by services.</span></span> <span data-ttu-id="2003b-130">Questa raccolta in genere contiene la stringa di connessione del database che potrebbe essere condivisa dai servizi durevoli.</span><span class="sxs-lookup"><span data-stu-id="2003b-130">This collection will typically include the database connection string that might be shared by durable services.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2003b-131">Note</span><span class="sxs-lookup"><span data-stu-id="2003b-131">Remarks</span></span>  
 <span data-ttu-id="2003b-132">L'elemento `<commonParameters>` definisce qualsiasi parametro usato globalmente tra più servizi, ad esempio `ConnectionString` quando si usa <xref:System.Workflow.Runtime.Hosting.SharedConnectionWorkflowCommitWorkBatchService>.</span><span class="sxs-lookup"><span data-stu-id="2003b-132">The `<commonParameters>` element defines any parameters that are used globally across multiple services, for example `ConnectionString` when using the <xref:System.Workflow.Runtime.Hosting.SharedConnectionWorkflowCommitWorkBatchService>.</span></span>  
  
 <span data-ttu-id="2003b-133">È possibile consentire a servizi che eseguono il commit di batch di lavoro su archivi di persistenza, ad esempio <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService> e <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>, di ritentare la transazione usando il parametro `EnableRetries`, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="2003b-133">For services that commit work batches to persistence stores, such as <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService> and <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>, you can enable them to retry their transaction by using the `EnableRetries` parameter as shown in the following example:</span></span>  
  
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
    <add type="System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService, System.Workflow.Runtime, Version=3.0.00000.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35"
         enableRetries="False" />
  </services>
</workflowRuntime>
```  
  
 <span data-ttu-id="2003b-134">Si noti che `EnableRetries` il parametro può essere impostato a livello globale (come illustrato nella sezione *parametricomuni* ) o per i singoli servizi che supportano `EnableRetries` (come illustrato nella sezione *Servizi* ).</span><span class="sxs-lookup"><span data-stu-id="2003b-134">Notice that the `EnableRetries` parameter can be set at either a global level (as shown in the *CommonParameters* section) or for individual services that support `EnableRetries` (as shown in the *Services* section).</span></span>  
  
 <span data-ttu-id="2003b-135">Per ulteriori informazioni sull'utilizzo di un file di configurazione per controllare il comportamento <xref:System.Workflow.Runtime.WorkflowRuntime> di un oggetto di un'applicazione host Windows Workflow Foundation, vedere [file di configurazione del flusso di lavoro](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="2003b-135">For more information on using a configuration file to control the behavior of a <xref:System.Workflow.Runtime.WorkflowRuntime> object of a Windows Workflow Foundation host application, see [Workflow Configuration Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2003b-136">Esempio</span><span class="sxs-lookup"><span data-stu-id="2003b-136">Example</span></span>  
  
```xml  
<commonParameters>
  <add name="ConnectionString"
       value="Initial Catalog=WorkflowStore;Data Source=localhost;Integrated Security=SSPI;" />
  <add name="EnableRetries"
       value="true" />
</commonParameters>
```  
  
## <a name="see-also"></a><span data-ttu-id="2003b-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2003b-137">See also</span></span>

- <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>
- <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>
- <xref:System.Workflow.Runtime.WorkflowRuntime>
- <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService>
- <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>
- <span data-ttu-id="2003b-138">[File di configurazione del flusso di lavoro](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="2003b-138">[Workflow Configuration Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span></span>
- [<span data-ttu-id="2003b-139">\<commonParameters></span><span class="sxs-lookup"><span data-stu-id="2003b-139">\<commonParameters></span></span>](commonparameters.md)
