---
title: <add>di WCF
ms.date: 03/30/2017
ms.assetid: c196f6d7-77f6-4266-973c-305b2b4dd8a2
ms.openlocfilehash: 0b21bdabc76ec4853a0f2664cdd3cead149417a1
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850305"
---
# <a name="add-of-wcf"></a><span data-ttu-id="470aa-102">\<aggiungere > di WCF</span><span class="sxs-lookup"><span data-stu-id="470aa-102">\<add> of WCF</span></span>
<span data-ttu-id="470aa-103">Configurare un partecipante del rilevamento che ascolta i record di rilevamento generati direttamente durante la fase di esecuzione e li elabora in base alle impostazioni configurate.</span><span class="sxs-lookup"><span data-stu-id="470aa-103">Configure a tracking participant that listens to the tracking records being emitted from the runtime directly and process them in whatever way it was configured.</span></span> <span data-ttu-id="470aa-104">Tali impostazioni includono la scrittura in un output specifico, ad esempio file, console, ETW, l'elaborazione/aggregazione dei record o qualsiasi altra combinazione che potrebbe essere richiesta.</span><span class="sxs-lookup"><span data-stu-id="470aa-104">This includes writing to a specific output (e.g., file, Console, ETW), processing/aggregating the records, or any other combination that might be required.</span></span>  
  
 <span data-ttu-id="470aa-105">Per altre informazioni sui partecipanti di rilevamento e rilevamento del flusso di lavoro, vedere Rilevamento e traccia [del flusso di lavoro](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) [partecipanti](../../../windows-workflow-foundation/tracking-participants.md).</span><span class="sxs-lookup"><span data-stu-id="470aa-105">For more information in workflow tracking and tracking participants, see [Workflow Tracking and Tracing](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Tracking Participants](../../../windows-workflow-foundation/tracking-participants.md).</span></span>  
  
<span data-ttu-id="470aa-106">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="470aa-106">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="470aa-107">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="470aa-107">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="470aa-108">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<rilevamento >** ](tracking-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="470aa-108">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)</span></span>\
<span data-ttu-id="470aa-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<partecipanti >** ](participants-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="470aa-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<participants>**](participants-of-wcf.md)</span></span>\
<span data-ttu-id="470aa-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Aggiungi >**</span><span class="sxs-lookup"><span data-stu-id="470aa-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="470aa-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="470aa-111">Syntax</span></span>  
  
```xml  
<tracking>
  <participants>
    <add name="String"
         profileName="String"
         type="String" />
  </participants>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="470aa-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="470aa-112">Attributes and Elements</span></span>  
 <span data-ttu-id="470aa-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="470aa-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="470aa-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="470aa-114">Attributes</span></span>  
  
|<span data-ttu-id="470aa-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="470aa-115">Element</span></span>|<span data-ttu-id="470aa-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="470aa-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="470aa-117">name</span><span class="sxs-lookup"><span data-stu-id="470aa-117">name</span></span>|<span data-ttu-id="470aa-118">Stringa che specifica il nome di un partecipante del rilevamento.</span><span class="sxs-lookup"><span data-stu-id="470aa-118">A string that specifies the name of a tracking participant.</span></span>|  
|<span data-ttu-id="470aa-119">profileName</span><span class="sxs-lookup"><span data-stu-id="470aa-119">profileName</span></span>|<span data-ttu-id="470aa-120">Stringa che specifica il nome del profilo di rilevamento che definisce i record di rilevamento sottoscritti dal partecipante del rilevamento.</span><span class="sxs-lookup"><span data-stu-id="470aa-120">A string that specifies the name of the tracking profile which defines the tracking records the tracking participant has subscribed to.</span></span>|  
|<span data-ttu-id="470aa-121">type</span><span class="sxs-lookup"><span data-stu-id="470aa-121">type</span></span>|<span data-ttu-id="470aa-122">Stringa che specifica il tipo di un partecipante del rilevamento.</span><span class="sxs-lookup"><span data-stu-id="470aa-122">A string that specifies the type of a tracking participant.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="470aa-123">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="470aa-123">Child Elements</span></span>  
 <span data-ttu-id="470aa-124">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="470aa-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="470aa-125">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="470aa-125">Parent Elements</span></span>  
  
|<span data-ttu-id="470aa-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="470aa-126">Element</span></span>|<span data-ttu-id="470aa-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="470aa-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="470aa-128">\<participants></span><span class="sxs-lookup"><span data-stu-id="470aa-128">\<participants></span></span>](../windows-workflow-foundation/participants.md)|<span data-ttu-id="470aa-129">Elenco di partecipanti del rilevamento.</span><span class="sxs-lookup"><span data-stu-id="470aa-129">A list of tracking participants</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="470aa-130">Note</span><span class="sxs-lookup"><span data-stu-id="470aa-130">Remarks</span></span>  
 <span data-ttu-id="470aa-131">I partecipanti del rilevamento vengono usati per ottenere i dati di rilevamento generati dal flusso di lavoro e archiviarli in supporti differenti.</span><span class="sxs-lookup"><span data-stu-id="470aa-131">Tracking participants are used to get the tracking data emitted from the workflow and store it into different mediums.</span></span> <span data-ttu-id="470aa-132">Analogamente, è anche possibile eseguire qualsiasi operazione di post-elaborazione sui record di rilevamento all'interno del partecipante del rilevamento.</span><span class="sxs-lookup"><span data-stu-id="470aa-132">Likewise, any post processing on the tracking Records can also be done within the tracking participant.</span></span>  
  
 <span data-ttu-id="470aa-133">Più partecipanti del rilevamento possono usare simultaneamente gli eventi di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="470aa-133">Multiple tracking participants can consume the tracking events simultaneously.</span></span> <span data-ttu-id="470aa-134">Ogni partecipante del rilevamento può essere associato a un profilo di rilevamento diverso.</span><span class="sxs-lookup"><span data-stu-id="470aa-134">Each tracking participant can be associated with a different tracking profile.</span></span>  
  
 <span data-ttu-id="470aa-135">Viene fornito un partecipante del rilevamento standard che scrive i record di rilevamento in una sessione ETW.</span><span class="sxs-lookup"><span data-stu-id="470aa-135">A standard tracking participant is provided which writes the tracking records to an ETW session.</span></span> <span data-ttu-id="470aa-136">Il partecipante viene configurato su un servizio flusso di lavoro aggiungendo un comportamento specifico del rilevamento in un file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="470aa-136">The participant is configured on a workflow service by adding a tracking-specific behavior in a configuration file.</span></span> <span data-ttu-id="470aa-137">L'abilitazione di un partecipante del rilevamento ETW consente la visualizzazione dei record di rilevamento nel Visualizzatore eventi.</span><span class="sxs-lookup"><span data-stu-id="470aa-137">Enabling an ETW tracking participant allows tracking records to be viewed in the event viewer.</span></span> <span data-ttu-id="470aa-138">Se tale partecipante non soddisfa i propri requisiti, è anche possibile scrivere un partecipante del rilevamento personalizzato.</span><span class="sxs-lookup"><span data-stu-id="470aa-138">If that does not meet your requirements, you can also write a custom tracking participant.</span></span>  
  
## <a name="example"></a><span data-ttu-id="470aa-139">Esempio</span><span class="sxs-lookup"><span data-stu-id="470aa-139">Example</span></span>  
 <span data-ttu-id="470aa-140">Nell'esempio di configurazione seguente viene mostrato il partecipante del rilevamento ETW standard configurato nel file Web.config.</span><span class="sxs-lookup"><span data-stu-id="470aa-140">The following configuration example shows the standard ETW tracking participant being configured in the Web.config file.</span></span>  
  
 <span data-ttu-id="470aa-141">L'ID del provider usato dal partecipante del rilevamento ETW per scrivere i record di rilevamento in ETW è definito nella sezione `<diagnostics>`.</span><span class="sxs-lookup"><span data-stu-id="470aa-141">The Provider Id that the ETW Tracking Participant uses for writing the Tracking Records to ETW is defined in the `<diagnostics>` section.</span></span> <span data-ttu-id="470aa-142">Al partecipante di rilevamento è associato un profilo per specificare i record di rilevamento che ha sottoscritto.</span><span class="sxs-lookup"><span data-stu-id="470aa-142">The tracking participant has a profile associated with it to specify the tracking records it has subscribed to.</span></span> <span data-ttu-id="470aa-143">Tale profilo è definito dall'attributo `profileName` dell'elemento `<add>`.</span><span class="sxs-lookup"><span data-stu-id="470aa-143">This is defined by the `profileName` attribute of the `<add>` element.</span></span> <span data-ttu-id="470aa-144">Dopo aver definito tali elementi, il partecipante del rilevamento viene aggiunto al comportamento del servizio `<etwTracking>`,</span><span class="sxs-lookup"><span data-stu-id="470aa-144">Once these are defined, the Tracking Participant is added to the `<etwTracking>` service behavior.</span></span> <span data-ttu-id="470aa-145">che aggiungerà i partecipanti del rilevamento selezionati alle estensioni dell'istanza del flusso di lavoro, in modo che inizino a ricevere i record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="470aa-145">This will add the selected Tracking Participants to the Workflow instance’s extensions, so that they begin to receive the Tracking Records.</span></span>  
  
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
             profileName="HealthMonitoring_Tracking_Profile" />
      </participants>
    </tracking>
    <behaviors>
      <serviceBehaviors>
        <behavior>
          <etwTracking profileName="Sample Tracking Profile" />
        </behavior>
      </serviceBehaviors>
    </behaviors>
  </system.serviceModel>
</configuration>
```  
  
## <a name="see-also"></a><span data-ttu-id="470aa-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="470aa-146">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.TrackingSection>
- <xref:System.ServiceModel.Activities.Description.EtwTrackingBehavior>
- <xref:System.ServiceModel.Activities.Configuration.EtwTrackingBehaviorElement>
- [<span data-ttu-id="470aa-147">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="470aa-147">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="470aa-148">Partecipanti di rilevamento</span><span class="sxs-lookup"><span data-stu-id="470aa-148">Tracking Participants</span></span>](../../../windows-workflow-foundation/tracking-participants.md)
