---
title: '&lt;participants&gt; di WCF'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d99dbddc-0057-4e18-8e42-f91411d39970
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e8ba1fd0094b5c070e60ecf2d7da1799de8c194f
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="ltparticipantsgt-of-wcf"></a><span data-ttu-id="f2506-102">&lt;participants&gt; di WCF</span><span class="sxs-lookup"><span data-stu-id="f2506-102">&lt;participants&gt; of WCF</span></span>
<span data-ttu-id="f2506-103">Configurare un elenco di partecipanti del rilevamento che ascoltano i record di rilevamento generati direttamente durante la fase di esecuzione e li elaborano in base alle impostazioni configurate.</span><span class="sxs-lookup"><span data-stu-id="f2506-103">Configure a list of tracking participants that listen to the tracking records being emitted from the runtime directly and process them in whatever way they are configured.</span></span> <span data-ttu-id="f2506-104">Tali impostazioni includono la scrittura in un output specifico, ad esempio file, console, ETW, l'elaborazione/aggregazione dei record o qualsiasi altra combinazione che potrebbe essere richiesta.</span><span class="sxs-lookup"><span data-stu-id="f2506-104">This includes writing to a specific output (e.g., file, Console, ETW), processing/aggregating the records, or any other combination that might be required.</span></span>  
  
 <span data-ttu-id="f2506-105">Per altre informazioni del rilevamento del flusso di lavoro e sui partecipanti di rilevamento, vedere [flusso di lavoro rilevamento e traccia](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) e [partecipanti del rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-participants.md).</span><span class="sxs-lookup"><span data-stu-id="f2506-105">For more information in workflow tracking and tracking participants, see [Workflow Tracking and Tracing](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Tracking Participants](../../../../../docs/framework/windows-workflow-foundation/tracking-participants.md).</span></span>  
  
 <span data-ttu-id="f2506-106">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="f2506-106">\<system.serviceModel></span></span>  
<span data-ttu-id="f2506-107">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="f2506-107">\<tracking></span></span>  
<span data-ttu-id="f2506-108">\<i partecipanti ></span><span class="sxs-lookup"><span data-stu-id="f2506-108">\<participants></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2506-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f2506-109">Syntax</span></span>  
  
```xml
   <tracking>    <participants>       <add name="String"            profileName="String"           type="String" />    </participants> </tracking>   
```
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f2506-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="f2506-110">Attributes and Elements</span></span>  
 <span data-ttu-id="f2506-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="f2506-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f2506-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="f2506-112">Attributes</span></span>  
 <span data-ttu-id="f2506-113">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="f2506-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f2506-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="f2506-114">Child Elements</span></span>  
  
|<span data-ttu-id="f2506-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="f2506-115">Element</span></span>|<span data-ttu-id="f2506-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f2506-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f2506-117">\<add></span><span class="sxs-lookup"><span data-stu-id="f2506-117">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/add-of-participants.md)|<span data-ttu-id="f2506-118">Contiene impostazioni per un partecipante del rilevamento.</span><span class="sxs-lookup"><span data-stu-id="f2506-118">Contains settings for a tracking participant.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f2506-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="f2506-119">Parent Elements</span></span>  
  
|<span data-ttu-id="f2506-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="f2506-120">Element</span></span>|<span data-ttu-id="f2506-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f2506-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f2506-122">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="f2506-122">\<tracking></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/tracking.md)|<span data-ttu-id="f2506-123">Rappresenta una sezione di configurazione per la definizione delle impostazioni di rilevamento di un servizio flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="f2506-123">Represents a configuration section for defining tracking settings for a workflow service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f2506-124">Note</span><span class="sxs-lookup"><span data-stu-id="f2506-124">Remarks</span></span>  
 <span data-ttu-id="f2506-125">I partecipanti del rilevamento vengono usati per ottenere i dati di rilevamento generati dal flusso di lavoro e archiviarli in supporti differenti.</span><span class="sxs-lookup"><span data-stu-id="f2506-125">Tracking participants are used to get the tracking data emitted from the workflow and store it into different mediums.</span></span> <span data-ttu-id="f2506-126">Analogamente, è anche possibile eseguire qualsiasi operazione di post-elaborazione sui record di rilevamento all'interno del partecipante del rilevamento.</span><span class="sxs-lookup"><span data-stu-id="f2506-126">Likewise, any post processing on the tracking Records can also be done within the tracking participant.</span></span>  
  
 <span data-ttu-id="f2506-127">Più partecipanti del rilevamento possono usare simultaneamente gli eventi di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="f2506-127">Multiple tracking participants can consume the tracking events simultaneously.</span></span> <span data-ttu-id="f2506-128">Ogni partecipante del rilevamento può essere associato a un profilo di rilevamento diverso.</span><span class="sxs-lookup"><span data-stu-id="f2506-128">Each tracking participant can be associated with a different tracking profile.</span></span>  
  
 <span data-ttu-id="f2506-129">Viene fornito un partecipante del rilevamento standard che scrive i record di rilevamento in una sessione ETW.</span><span class="sxs-lookup"><span data-stu-id="f2506-129">A standard tracking participant is provided which writes the tracking records to an ETW session.</span></span> <span data-ttu-id="f2506-130">Il partecipante viene configurato su un servizio flusso di lavoro aggiungendo un comportamento specifico del rilevamento in un file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="f2506-130">The participant is configured on a workflow service by adding a tracking-specific behavior in a configuration file.</span></span> <span data-ttu-id="f2506-131">L'abilitazione di un partecipante del rilevamento ETW consente la visualizzazione dei record di rilevamento nel Visualizzatore eventi.</span><span class="sxs-lookup"><span data-stu-id="f2506-131">Enabling an ETW tracking participant allows tracking records to be viewed in the event viewer.</span></span> <span data-ttu-id="f2506-132">Se tale partecipante non soddisfa i propri requisiti, è anche possibile scrivere un partecipante del rilevamento personalizzato.</span><span class="sxs-lookup"><span data-stu-id="f2506-132">If that does not meet your requirements, you can also write a custom tracking participant.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f2506-133">Esempio</span><span class="sxs-lookup"><span data-stu-id="f2506-133">Example</span></span>  
 <span data-ttu-id="f2506-134">Nell'esempio di configurazione seguente viene mostrato il partecipante del rilevamento ETW standard configurato nel file Web.config.</span><span class="sxs-lookup"><span data-stu-id="f2506-134">The following configuration example shows the standard ETW tracking participant being configured in the Web.config file.</span></span>  
  
 <span data-ttu-id="f2506-135">L'ID del provider usato dal partecipante del rilevamento ETW per scrivere i record di rilevamento in ETW è definito nella sezione `<diagnostics>`.</span><span class="sxs-lookup"><span data-stu-id="f2506-135">The Provider Id that the ETW Tracking Participant uses for writing the Tracking Records to ETW is defined in the `<diagnostics>` section.</span></span> <span data-ttu-id="f2506-136">Al partecipante di rilevamento è associato un profilo per specificare i record di rilevamento che ha sottoscritto.</span><span class="sxs-lookup"><span data-stu-id="f2506-136">The tracking participant has a profile associated with it to specify the tracking records it has subscribed to.</span></span> <span data-ttu-id="f2506-137">Tale profilo è definito dall'attributo `profileName` dell'elemento `<add>`.</span><span class="sxs-lookup"><span data-stu-id="f2506-137">This is defined by the `profileName` attribute of the `<add>` element.</span></span> <span data-ttu-id="f2506-138">Dopo aver definito tali elementi, il partecipante del rilevamento viene aggiunto al comportamento del servizio `<etwTracking>`,</span><span class="sxs-lookup"><span data-stu-id="f2506-138">Once these are defined, the Tracking Participant is added to the `<etwTracking>` service behavior.</span></span> <span data-ttu-id="f2506-139">che aggiungerà i partecipanti del rilevamento selezionati alle estensioni dell'istanza del flusso di lavoro, in modo che inizino a ricevere i record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="f2506-139">This will add the selected Tracking Participants to the Workflow instance’s extensions, so that they begin to receive the Tracking Records.</span></span>  
  
```xml  
<configuration>   
  <system.web>   
    <compilation targetFrameworkMoniker=".NETFramework,Version=v4.0"/>   
  </system.web>   
  <system.serviceModel>   
    <diagnostics etwProviderId="52A3165D-4AD9-405C-B1E8-7D9A257EAC9F" />                
    <tracking>   
      <participants>   
        <add name="EtwTrackingParticipant"   
             type="System.Activities.Tracking.EtwTrackingParticipant, System.Activities, Version=4.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35"   
             profileName="HealthMonitoring_Tracking_Profile"/>   
      </participants>   
    </tracking>   
    <behaviors>   
      <serviceBehaviors>   
        <behavior>   
          <etwTracking profileName="Sample Tracking Profile"/>  
        </behavior>   
      </serviceBehaviors>   
    </behaviors>   
  </system.serviceModel>   
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f2506-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f2506-140">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.TrackingSection>  
 <xref:System.ServiceModel.Activities.Description.EtwTrackingBehavior>  
 [<span data-ttu-id="f2506-141">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="f2506-141">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="f2506-142">Partecipanti di rilevamento</span><span class="sxs-lookup"><span data-stu-id="f2506-142">Tracking Participants</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-participants.md)
