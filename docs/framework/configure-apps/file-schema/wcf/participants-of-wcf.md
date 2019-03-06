---
title: <participants> di WCF
ms.date: 03/30/2017
ms.assetid: d99dbddc-0057-4e18-8e42-f91411d39970
ms.openlocfilehash: c1f43fc425a172ce630b48d046ed75d09c74c2e3
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57362851"
---
# <a name="participants-of-wcf"></a><span data-ttu-id="33692-102">\<i partecipanti > di WCF</span><span class="sxs-lookup"><span data-stu-id="33692-102">\<participants> of WCF</span></span>
<span data-ttu-id="33692-103">Configurare un elenco di partecipanti del rilevamento che ascoltano i record di rilevamento generati direttamente durante la fase di esecuzione e li elaborano in base alle impostazioni configurate.</span><span class="sxs-lookup"><span data-stu-id="33692-103">Configure a list of tracking participants that listen to the tracking records being emitted from the runtime directly and process them in whatever way they are configured.</span></span> <span data-ttu-id="33692-104">Tali impostazioni includono la scrittura in un output specifico, ad esempio file, console, ETW, l'elaborazione/aggregazione dei record o qualsiasi altra combinazione che potrebbe essere richiesta.</span><span class="sxs-lookup"><span data-stu-id="33692-104">This includes writing to a specific output (e.g., file, Console, ETW), processing/aggregating the records, or any other combination that might be required.</span></span>  
  
 <span data-ttu-id="33692-105">Per altre informazioni sul rilevamento del flusso di lavoro e sui partecipanti di rilevamento, vedere [flusso di lavoro di rilevamento e traccia](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) e [partecipanti del rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-participants.md).</span><span class="sxs-lookup"><span data-stu-id="33692-105">For more information in workflow tracking and tracking participants, see [Workflow Tracking and Tracing](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Tracking Participants](../../../../../docs/framework/windows-workflow-foundation/tracking-participants.md).</span></span>  
  
 <span data-ttu-id="33692-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="33692-106">\<system.serviceModel></span></span>  
<span data-ttu-id="33692-107">\<tracking></span><span class="sxs-lookup"><span data-stu-id="33692-107">\<tracking></span></span>  
<span data-ttu-id="33692-108">\<i partecipanti ></span><span class="sxs-lookup"><span data-stu-id="33692-108">\<participants></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33692-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="33692-109">Syntax</span></span>  
  
```xml  
<tracking>
  <participants>
    <add name="String"
         profileName="String"
         type="String" />
  </participants>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="33692-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="33692-110">Attributes and Elements</span></span>  
 <span data-ttu-id="33692-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="33692-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="33692-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="33692-112">Attributes</span></span>  
 <span data-ttu-id="33692-113">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="33692-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="33692-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="33692-114">Child Elements</span></span>  
  
|<span data-ttu-id="33692-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="33692-115">Element</span></span>|<span data-ttu-id="33692-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="33692-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="33692-117">\<add></span><span class="sxs-lookup"><span data-stu-id="33692-117">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/add-of-participants.md)|<span data-ttu-id="33692-118">Contiene impostazioni per un partecipante del rilevamento.</span><span class="sxs-lookup"><span data-stu-id="33692-118">Contains settings for a tracking participant.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="33692-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="33692-119">Parent Elements</span></span>  
  
|<span data-ttu-id="33692-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="33692-120">Element</span></span>|<span data-ttu-id="33692-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="33692-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="33692-122">\<tracking></span><span class="sxs-lookup"><span data-stu-id="33692-122">\<tracking></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/tracking.md)|<span data-ttu-id="33692-123">Rappresenta una sezione di configurazione per la definizione delle impostazioni di rilevamento di un servizio flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="33692-123">Represents a configuration section for defining tracking settings for a workflow service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="33692-124">Note</span><span class="sxs-lookup"><span data-stu-id="33692-124">Remarks</span></span>  
 <span data-ttu-id="33692-125">I partecipanti del rilevamento vengono usati per ottenere i dati di rilevamento generati dal flusso di lavoro e archiviarli in supporti differenti.</span><span class="sxs-lookup"><span data-stu-id="33692-125">Tracking participants are used to get the tracking data emitted from the workflow and store it into different mediums.</span></span> <span data-ttu-id="33692-126">Analogamente, è anche possibile eseguire qualsiasi operazione di post-elaborazione sui record di rilevamento all'interno del partecipante del rilevamento.</span><span class="sxs-lookup"><span data-stu-id="33692-126">Likewise, any post processing on the tracking Records can also be done within the tracking participant.</span></span>  
  
 <span data-ttu-id="33692-127">Più partecipanti del rilevamento possono usare simultaneamente gli eventi di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="33692-127">Multiple tracking participants can consume the tracking events simultaneously.</span></span> <span data-ttu-id="33692-128">Ogni partecipante del rilevamento può essere associato a un profilo di rilevamento diverso.</span><span class="sxs-lookup"><span data-stu-id="33692-128">Each tracking participant can be associated with a different tracking profile.</span></span>  
  
 <span data-ttu-id="33692-129">Viene fornito un partecipante del rilevamento standard che scrive i record di rilevamento in una sessione ETW.</span><span class="sxs-lookup"><span data-stu-id="33692-129">A standard tracking participant is provided which writes the tracking records to an ETW session.</span></span> <span data-ttu-id="33692-130">Il partecipante viene configurato su un servizio flusso di lavoro aggiungendo un comportamento specifico del rilevamento in un file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="33692-130">The participant is configured on a workflow service by adding a tracking-specific behavior in a configuration file.</span></span> <span data-ttu-id="33692-131">L'abilitazione di un partecipante del rilevamento ETW consente la visualizzazione dei record di rilevamento nel Visualizzatore eventi.</span><span class="sxs-lookup"><span data-stu-id="33692-131">Enabling an ETW tracking participant allows tracking records to be viewed in the event viewer.</span></span> <span data-ttu-id="33692-132">Se tale partecipante non soddisfa i propri requisiti, è anche possibile scrivere un partecipante del rilevamento personalizzato.</span><span class="sxs-lookup"><span data-stu-id="33692-132">If that does not meet your requirements, you can also write a custom tracking participant.</span></span>  
  
## <a name="example"></a><span data-ttu-id="33692-133">Esempio</span><span class="sxs-lookup"><span data-stu-id="33692-133">Example</span></span>  
 <span data-ttu-id="33692-134">Nell'esempio di configurazione seguente viene mostrato il partecipante del rilevamento ETW standard configurato nel file Web.config.</span><span class="sxs-lookup"><span data-stu-id="33692-134">The following configuration example shows the standard ETW tracking participant being configured in the Web.config file.</span></span>  
  
 <span data-ttu-id="33692-135">L'ID del provider usato dal partecipante del rilevamento ETW per scrivere i record di rilevamento in ETW è definito nella sezione `<diagnostics>`.</span><span class="sxs-lookup"><span data-stu-id="33692-135">The Provider Id that the ETW Tracking Participant uses for writing the Tracking Records to ETW is defined in the `<diagnostics>` section.</span></span> <span data-ttu-id="33692-136">Al partecipante di rilevamento è associato un profilo per specificare i record di rilevamento che ha sottoscritto.</span><span class="sxs-lookup"><span data-stu-id="33692-136">The tracking participant has a profile associated with it to specify the tracking records it has subscribed to.</span></span> <span data-ttu-id="33692-137">Tale profilo è definito dall'attributo `profileName` dell'elemento `<add>`.</span><span class="sxs-lookup"><span data-stu-id="33692-137">This is defined by the `profileName` attribute of the `<add>` element.</span></span> <span data-ttu-id="33692-138">Dopo aver definito tali elementi, il partecipante del rilevamento viene aggiunto al comportamento del servizio `<etwTracking>`,</span><span class="sxs-lookup"><span data-stu-id="33692-138">Once these are defined, the Tracking Participant is added to the `<etwTracking>` service behavior.</span></span> <span data-ttu-id="33692-139">che aggiungerà i partecipanti del rilevamento selezionati alle estensioni dell'istanza del flusso di lavoro, in modo che inizino a ricevere i record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="33692-139">This will add the selected Tracking Participants to the Workflow instance’s extensions, so that they begin to receive the Tracking Records.</span></span>  
  
```xml  
<configuration>
  <system.web>
    <compilation targetFrameworkMoniker=".NETFramework,Version=v4.0" />
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
  
## <a name="see-also"></a><span data-ttu-id="33692-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="33692-140">See also</span></span>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.TrackingSection>
- <xref:System.ServiceModel.Activities.Description.EtwTrackingBehavior>
- [<span data-ttu-id="33692-141">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="33692-141">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="33692-142">Partecipanti di rilevamento</span><span class="sxs-lookup"><span data-stu-id="33692-142">Tracking Participants</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-participants.md)
