---
title: <participants>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 560dd0bb-f9fb-423c-8857-2101a3654b06
ms.openlocfilehash: f04a5ee3940986cabc08895452c12ebcfd631694
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69947574"
---
# <a name="participants"></a><span data-ttu-id="6766b-101">\<partecipanti ></span><span class="sxs-lookup"><span data-stu-id="6766b-101">\<participants></span></span>
<span data-ttu-id="6766b-102">Configurare un elenco di partecipanti del rilevamento che ascoltano i record di rilevamento generati direttamente durante la fase di esecuzione e li elaborano in base alle impostazioni configurate.</span><span class="sxs-lookup"><span data-stu-id="6766b-102">Configure a list of tracking participants that listen to the tracking records being emitted from the runtime directly and process them in whatever way they are configured.</span></span> <span data-ttu-id="6766b-103">Tali impostazioni includono la scrittura in un output specifico, ad esempio file, console, ETW, l'elaborazione/aggregazione dei record o qualsiasi altra combinazione che potrebbe essere richiesta.</span><span class="sxs-lookup"><span data-stu-id="6766b-103">This includes writing to a specific output (e.g., file, Console, ETW), processing/aggregating the records, or any other combination that might be required.</span></span>  
  
 <span data-ttu-id="6766b-104">Per altre informazioni sui partecipanti di rilevamento e rilevamento del flusso di lavoro, vedere Rilevamento e traccia [del flusso di lavoro](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) [partecipanti](../../../windows-workflow-foundation/tracking-participants.md).</span><span class="sxs-lookup"><span data-stu-id="6766b-104">For more information in workflow tracking and tracking participants, see [Workflow Tracking and Tracing](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Tracking Participants](../../../windows-workflow-foundation/tracking-participants.md).</span></span>  
  
<span data-ttu-id="6766b-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="6766b-105">\<system.serviceModel></span></span>  
<span data-ttu-id="6766b-106">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="6766b-106">\<tracking></span></span>  
<span data-ttu-id="6766b-107">\<partecipanti ></span><span class="sxs-lookup"><span data-stu-id="6766b-107">\<participants></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6766b-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6766b-108">Syntax</span></span>  
  
```xml
<tracking>
  <participants>
    <add name="String" 
         profileName="String" 
         type="String" />
  </participants>
</tracking>   
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6766b-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="6766b-109">Attributes and Elements</span></span>  
 <span data-ttu-id="6766b-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="6766b-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6766b-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="6766b-111">Attributes</span></span>  
 <span data-ttu-id="6766b-112">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="6766b-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="6766b-113">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="6766b-113">Child Elements</span></span>  
  
|<span data-ttu-id="6766b-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="6766b-114">Element</span></span>|<span data-ttu-id="6766b-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6766b-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6766b-116">\<add></span><span class="sxs-lookup"><span data-stu-id="6766b-116">\<add></span></span>](add-of-participants.md)|<span data-ttu-id="6766b-117">Contiene impostazioni per un partecipante del rilevamento.</span><span class="sxs-lookup"><span data-stu-id="6766b-117">Contains settings for a tracking participant.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6766b-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="6766b-118">Parent Elements</span></span>  
  
|<span data-ttu-id="6766b-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="6766b-119">Element</span></span>|<span data-ttu-id="6766b-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6766b-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6766b-121">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="6766b-121">\<tracking></span></span>](tracking.md)|<span data-ttu-id="6766b-122">Rappresenta una sezione di configurazione per la definizione delle impostazioni di rilevamento di un servizio flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="6766b-122">Represents a configuration section for defining tracking settings for a workflow service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6766b-123">Note</span><span class="sxs-lookup"><span data-stu-id="6766b-123">Remarks</span></span>  
 <span data-ttu-id="6766b-124">I partecipanti del rilevamento vengono usati per ottenere i dati di rilevamento generati dal flusso di lavoro e archiviarli in supporti differenti.</span><span class="sxs-lookup"><span data-stu-id="6766b-124">Tracking participants are used to get the tracking data emitted from the workflow and store it into different mediums.</span></span> <span data-ttu-id="6766b-125">Analogamente, è anche possibile eseguire qualsiasi operazione di post-elaborazione sui record di rilevamento all'interno del partecipante del rilevamento.</span><span class="sxs-lookup"><span data-stu-id="6766b-125">Likewise, any post processing on the tracking Records can also be done within the tracking participant.</span></span>  
  
 <span data-ttu-id="6766b-126">Più partecipanti del rilevamento possono usare simultaneamente gli eventi di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="6766b-126">Multiple tracking participants can consume the tracking events simultaneously.</span></span> <span data-ttu-id="6766b-127">Ogni partecipante del rilevamento può essere associato a un profilo di rilevamento diverso.</span><span class="sxs-lookup"><span data-stu-id="6766b-127">Each tracking participant can be associated with a different tracking profile.</span></span>  
  
 <span data-ttu-id="6766b-128">Viene fornito un partecipante del rilevamento standard che scrive i record di rilevamento in una sessione ETW.</span><span class="sxs-lookup"><span data-stu-id="6766b-128">A standard tracking participant is provided which writes the tracking records to an ETW session.</span></span> <span data-ttu-id="6766b-129">Il partecipante viene configurato su un servizio flusso di lavoro aggiungendo un comportamento specifico del rilevamento in un file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="6766b-129">The participant is configured on a workflow service by adding a tracking-specific behavior in a configuration file.</span></span> <span data-ttu-id="6766b-130">L'abilitazione di un partecipante del rilevamento ETW consente la visualizzazione dei record di rilevamento nel Visualizzatore eventi.</span><span class="sxs-lookup"><span data-stu-id="6766b-130">Enabling an ETW tracking participant allows tracking records to be viewed in the event viewer.</span></span> <span data-ttu-id="6766b-131">Se tale partecipante non soddisfa i propri requisiti, è anche possibile scrivere un partecipante del rilevamento personalizzato.</span><span class="sxs-lookup"><span data-stu-id="6766b-131">If that does not meet your requirements, you can also write a custom tracking participant.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6766b-132">Esempio</span><span class="sxs-lookup"><span data-stu-id="6766b-132">Example</span></span>  
 <span data-ttu-id="6766b-133">Nell'esempio di configurazione seguente viene mostrato il partecipante del rilevamento ETW standard configurato nel file Web.config.</span><span class="sxs-lookup"><span data-stu-id="6766b-133">The following configuration example shows the standard ETW tracking participant being configured in the Web.config file.</span></span>  
  
 <span data-ttu-id="6766b-134">L'ID del provider utilizzato dal partecipante del rilevamento ETW per la scrittura dei record di rilevamento in ETW è definito nella  **\<sezione diagnostica >** .</span><span class="sxs-lookup"><span data-stu-id="6766b-134">The Provider Id that the ETW Tracking Participant uses for writing the Tracking Records to ETW is defined in the **\<diagnostics>** section.</span></span> <span data-ttu-id="6766b-135">Al partecipante di rilevamento è associato un profilo per specificare i record di rilevamento che ha sottoscritto.</span><span class="sxs-lookup"><span data-stu-id="6766b-135">The tracking participant has a profile associated with it to specify the tracking records it has subscribed to.</span></span> <span data-ttu-id="6766b-136">Questa operazione viene definita dall' attributo ProfileName dell'  **\<elemento Add >** .</span><span class="sxs-lookup"><span data-stu-id="6766b-136">This is defined by the **profileName** attribute of the **\<add>** element.</span></span> <span data-ttu-id="6766b-137">Una volta definiti, il partecipante del rilevamento viene aggiunto al comportamento  **\<** del servizio > di etwTracking.</span><span class="sxs-lookup"><span data-stu-id="6766b-137">Once these are defined, the Tracking Participant is added to the **\<etwTracking>** service behavior.</span></span> <span data-ttu-id="6766b-138">che aggiungerà i partecipanti del rilevamento selezionati alle estensioni dell'istanza del flusso di lavoro, in modo che inizino a ricevere i record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="6766b-138">This will add the selected Tracking Participants to the Workflow instance’s extensions, so that they begin to receive the Tracking Records.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="6766b-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6766b-139">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.TrackingSection>
- <xref:System.ServiceModel.Activities.Description.EtwTrackingBehavior>
- <xref:System.ServiceModel.Activities.Configuration.EtwTrackingBehaviorElement>
- [<span data-ttu-id="6766b-140">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="6766b-140">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="6766b-141">Partecipanti di rilevamento</span><span class="sxs-lookup"><span data-stu-id="6766b-141">Tracking Participants</span></span>](../../../windows-workflow-foundation/tracking-participants.md)
