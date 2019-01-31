---
title: <participants>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 560dd0bb-f9fb-423c-8857-2101a3654b06
ms.openlocfilehash: ffb38bca1848d7f679b6a2a717cd7082cfe356f3
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55277381"
---
# <a name="participants"></a><span data-ttu-id="d335b-101">\<i partecipanti ></span><span class="sxs-lookup"><span data-stu-id="d335b-101">\<participants></span></span>
<span data-ttu-id="d335b-102">Configurare un elenco di partecipanti del rilevamento che ascoltano i record di rilevamento generati direttamente durante la fase di esecuzione e li elaborano in base alle impostazioni configurate.</span><span class="sxs-lookup"><span data-stu-id="d335b-102">Configure a list of tracking participants that listen to the tracking records being emitted from the runtime directly and process them in whatever way they are configured.</span></span> <span data-ttu-id="d335b-103">Tali impostazioni includono la scrittura in un output specifico, ad esempio file, console, ETW, l'elaborazione/aggregazione dei record o qualsiasi altra combinazione che potrebbe essere richiesta.</span><span class="sxs-lookup"><span data-stu-id="d335b-103">This includes writing to a specific output (e.g., file, Console, ETW), processing/aggregating the records, or any other combination that might be required.</span></span>  
  
 <span data-ttu-id="d335b-104">Per altre informazioni sul rilevamento del flusso di lavoro e sui partecipanti di rilevamento, vedere [flusso di lavoro di rilevamento e traccia](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) e [partecipanti del rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-participants.md).</span><span class="sxs-lookup"><span data-stu-id="d335b-104">For more information in workflow tracking and tracking participants, see [Workflow Tracking and Tracing](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Tracking Participants](../../../../../docs/framework/windows-workflow-foundation/tracking-participants.md).</span></span>  
  
<span data-ttu-id="d335b-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="d335b-105">\<system.serviceModel></span></span>  
<span data-ttu-id="d335b-106">\<tracking></span><span class="sxs-lookup"><span data-stu-id="d335b-106">\<tracking></span></span>  
<span data-ttu-id="d335b-107">\<i partecipanti ></span><span class="sxs-lookup"><span data-stu-id="d335b-107">\<participants></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d335b-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d335b-108">Syntax</span></span>  
  
```xml
<tracking>
  <participants>
    <add name="String" 
         profileName="String" 
         type="String" />
  </participants>
</tracking>   
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d335b-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="d335b-109">Attributes and Elements</span></span>  
 <span data-ttu-id="d335b-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="d335b-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d335b-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="d335b-111">Attributes</span></span>  
 <span data-ttu-id="d335b-112">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="d335b-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d335b-113">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="d335b-113">Child Elements</span></span>  
  
|<span data-ttu-id="d335b-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="d335b-114">Element</span></span>|<span data-ttu-id="d335b-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d335b-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d335b-116">\<add></span><span class="sxs-lookup"><span data-stu-id="d335b-116">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/add-of-participants.md)|<span data-ttu-id="d335b-117">Contiene impostazioni per un partecipante del rilevamento.</span><span class="sxs-lookup"><span data-stu-id="d335b-117">Contains settings for a tracking participant.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d335b-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="d335b-118">Parent Elements</span></span>  
  
|<span data-ttu-id="d335b-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="d335b-119">Element</span></span>|<span data-ttu-id="d335b-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d335b-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d335b-121">\<tracking></span><span class="sxs-lookup"><span data-stu-id="d335b-121">\<tracking></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/tracking.md)|<span data-ttu-id="d335b-122">Rappresenta una sezione di configurazione per la definizione delle impostazioni di rilevamento di un servizio flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="d335b-122">Represents a configuration section for defining tracking settings for a workflow service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d335b-123">Note</span><span class="sxs-lookup"><span data-stu-id="d335b-123">Remarks</span></span>  
 <span data-ttu-id="d335b-124">I partecipanti del rilevamento vengono usati per ottenere i dati di rilevamento generati dal flusso di lavoro e archiviarli in supporti differenti.</span><span class="sxs-lookup"><span data-stu-id="d335b-124">Tracking participants are used to get the tracking data emitted from the workflow and store it into different mediums.</span></span> <span data-ttu-id="d335b-125">Analogamente, è anche possibile eseguire qualsiasi operazione di post-elaborazione sui record di rilevamento all'interno del partecipante del rilevamento.</span><span class="sxs-lookup"><span data-stu-id="d335b-125">Likewise, any post processing on the tracking Records can also be done within the tracking participant.</span></span>  
  
 <span data-ttu-id="d335b-126">Più partecipanti del rilevamento possono usare simultaneamente gli eventi di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="d335b-126">Multiple tracking participants can consume the tracking events simultaneously.</span></span> <span data-ttu-id="d335b-127">Ogni partecipante del rilevamento può essere associato a un profilo di rilevamento diverso.</span><span class="sxs-lookup"><span data-stu-id="d335b-127">Each tracking participant can be associated with a different tracking profile.</span></span>  
  
 <span data-ttu-id="d335b-128">Viene fornito un partecipante del rilevamento standard che scrive i record di rilevamento in una sessione ETW.</span><span class="sxs-lookup"><span data-stu-id="d335b-128">A standard tracking participant is provided which writes the tracking records to an ETW session.</span></span> <span data-ttu-id="d335b-129">Il partecipante viene configurato su un servizio flusso di lavoro aggiungendo un comportamento specifico del rilevamento in un file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="d335b-129">The participant is configured on a workflow service by adding a tracking-specific behavior in a configuration file.</span></span> <span data-ttu-id="d335b-130">L'abilitazione di un partecipante del rilevamento ETW consente la visualizzazione dei record di rilevamento nel Visualizzatore eventi.</span><span class="sxs-lookup"><span data-stu-id="d335b-130">Enabling an ETW tracking participant allows tracking records to be viewed in the event viewer.</span></span> <span data-ttu-id="d335b-131">Se tale partecipante non soddisfa i propri requisiti, è anche possibile scrivere un partecipante del rilevamento personalizzato.</span><span class="sxs-lookup"><span data-stu-id="d335b-131">If that does not meet your requirements, you can also write a custom tracking participant.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d335b-132">Esempio</span><span class="sxs-lookup"><span data-stu-id="d335b-132">Example</span></span>  
 <span data-ttu-id="d335b-133">Nell'esempio di configurazione seguente viene mostrato il partecipante del rilevamento ETW standard configurato nel file Web.config.</span><span class="sxs-lookup"><span data-stu-id="d335b-133">The following configuration example shows the standard ETW tracking participant being configured in the Web.config file.</span></span>  
  
 <span data-ttu-id="d335b-134">L'Id del Provider usato dal partecipante del rilevamento ETW per scrivere i record di rilevamento in ETW è definito nel  **\<diagnostica >** sezione.</span><span class="sxs-lookup"><span data-stu-id="d335b-134">The Provider Id that the ETW Tracking Participant uses for writing the Tracking Records to ETW is defined in the **\<diagnostics>** section.</span></span> <span data-ttu-id="d335b-135">Al partecipante di rilevamento è associato un profilo per specificare i record di rilevamento che ha sottoscritto.</span><span class="sxs-lookup"><span data-stu-id="d335b-135">The tracking participant has a profile associated with it to specify the tracking records it has subscribed to.</span></span> <span data-ttu-id="d335b-136">Ciò viene definito dal **profileName** attributo il  **\<aggiungere >** elemento.</span><span class="sxs-lookup"><span data-stu-id="d335b-136">This is defined by the **profileName** attribute of the **\<add>** element.</span></span> <span data-ttu-id="d335b-137">Dopo aver definito tali elementi, viene aggiunto il partecipante di rilevamento per il  **\<etwTracking >** comportamento del servizio.</span><span class="sxs-lookup"><span data-stu-id="d335b-137">Once these are defined, the Tracking Participant is added to the **\<etwTracking>** service behavior.</span></span> <span data-ttu-id="d335b-138">che aggiungerà i partecipanti del rilevamento selezionati alle estensioni dell'istanza del flusso di lavoro, in modo che inizino a ricevere i record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="d335b-138">This will add the selected Tracking Participants to the Workflow instance’s extensions, so that they begin to receive the Tracking Records.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d335b-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d335b-139">See also</span></span>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.TrackingSection>
- <xref:System.ServiceModel.Activities.Description.EtwTrackingBehavior>
- <xref:System.ServiceModel.Activities.Configuration.EtwTrackingBehaviorElement>
- [<span data-ttu-id="d335b-140">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="d335b-140">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="d335b-141">Partecipanti di rilevamento</span><span class="sxs-lookup"><span data-stu-id="d335b-141">Tracking Participants</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-participants.md)
