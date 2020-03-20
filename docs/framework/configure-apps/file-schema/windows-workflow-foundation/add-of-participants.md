---
title: <add> di <participants>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 3c730850-6f8e-4102-acb8-8effb4e09463
ms.openlocfilehash: 61832edbf7d206d6a5f7a85619eb17ebc010c193
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152359"
---
# <a name="add-of-participants"></a><span data-ttu-id="23e6d-102">\<aggiungere> \<di partecipanti></span><span class="sxs-lookup"><span data-stu-id="23e6d-102">\<add> of \<participants></span></span>
<span data-ttu-id="23e6d-103">Configurare un partecipante del rilevamento che ascolta i record di rilevamento generati direttamente durante la fase di esecuzione e li elabora in base alle impostazioni configurate.</span><span class="sxs-lookup"><span data-stu-id="23e6d-103">Configure a tracking participant that listens to the tracking records being emitted from the runtime directly and process them in whatever way it was configured.</span></span> <span data-ttu-id="23e6d-104">Tali impostazioni includono la scrittura in un output specifico, ad esempio file, console, ETW, l'elaborazione/aggregazione dei record o qualsiasi altra combinazione che potrebbe essere richiesta.</span><span class="sxs-lookup"><span data-stu-id="23e6d-104">This includes writing to a specific output (e.g., file, Console, ETW), processing/aggregating the records, or any other combination that might be required.</span></span>  
  
 <span data-ttu-id="23e6d-105">Per ulteriori informazioni sui partecipanti di rilevamento e rilevamento del flusso di lavoro, vedere Tracciabilità del flusso di [lavoro e tracciabilità](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) dei [partecipanti.](../../../windows-workflow-foundation/tracking-participants.md)</span><span class="sxs-lookup"><span data-stu-id="23e6d-105">For more information in workflow tracking and tracking participants, see [Workflow Tracking and Tracing](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Tracking Participants](../../../windows-workflow-foundation/tracking-participants.md).</span></span>  
  
<span data-ttu-id="23e6d-106">[**\<>di configurazione**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="23e6d-106">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="23e6d-107">&nbsp;&nbsp;[**\<Sistema.>ServiceModelServiceModel>**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="23e6d-107">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="23e6d-108">&nbsp;&nbsp;&nbsp;&nbsp;[**\<>di tracciamento**](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="23e6d-108">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="23e6d-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<partecipanti>**](participants.md)</span><span class="sxs-lookup"><span data-stu-id="23e6d-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<participants>**](participants.md)</span></span>\
<span data-ttu-id="23e6d-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<aggiungere>**</span><span class="sxs-lookup"><span data-stu-id="23e6d-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23e6d-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="23e6d-111">Syntax</span></span>  
  
```xml
<tracking>
  <participants>
    <add name="String" profileName="String" type="String" />
  </participants>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="23e6d-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="23e6d-112">Attributes and Elements</span></span>  
 <span data-ttu-id="23e6d-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="23e6d-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="23e6d-114">Attributes</span><span class="sxs-lookup"><span data-stu-id="23e6d-114">Attributes</span></span>  
  
|<span data-ttu-id="23e6d-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="23e6d-115">Element</span></span>|<span data-ttu-id="23e6d-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="23e6d-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="23e6d-117">name</span><span class="sxs-lookup"><span data-stu-id="23e6d-117">name</span></span>|<span data-ttu-id="23e6d-118">Stringa che specifica il nome di un partecipante del rilevamento.</span><span class="sxs-lookup"><span data-stu-id="23e6d-118">A string that specifies the name of a tracking participant.</span></span>|  
|<span data-ttu-id="23e6d-119">profileName</span><span class="sxs-lookup"><span data-stu-id="23e6d-119">profileName</span></span>|<span data-ttu-id="23e6d-120">Stringa che specifica il nome del profilo di rilevamento che definisce i record di rilevamento sottoscritti dal partecipante del rilevamento.</span><span class="sxs-lookup"><span data-stu-id="23e6d-120">A string that specifies the name of the tracking profile which defines the tracking records the tracking participant has subscribed to.</span></span>|  
|<span data-ttu-id="23e6d-121">type</span><span class="sxs-lookup"><span data-stu-id="23e6d-121">type</span></span>|<span data-ttu-id="23e6d-122">Stringa che specifica il tipo di un partecipante del rilevamento.</span><span class="sxs-lookup"><span data-stu-id="23e6d-122">A string that specifies the type of a tracking participant.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="23e6d-123">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="23e6d-123">Child Elements</span></span>  
 <span data-ttu-id="23e6d-124">No.</span><span class="sxs-lookup"><span data-stu-id="23e6d-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="23e6d-125">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="23e6d-125">Parent Elements</span></span>  
  
|<span data-ttu-id="23e6d-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="23e6d-126">Element</span></span>|<span data-ttu-id="23e6d-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="23e6d-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="23e6d-128">\<partecipanti></span><span class="sxs-lookup"><span data-stu-id="23e6d-128">\<participants></span></span>](participants.md)|<span data-ttu-id="23e6d-129">Elenco di partecipanti del rilevamento.</span><span class="sxs-lookup"><span data-stu-id="23e6d-129">A list of tracking participants</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="23e6d-130">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="23e6d-130">Remarks</span></span>  
 <span data-ttu-id="23e6d-131">I partecipanti del rilevamento vengono usati per ottenere i dati di rilevamento generati dal flusso di lavoro e archiviarli in supporti differenti.</span><span class="sxs-lookup"><span data-stu-id="23e6d-131">Tracking participants are used to get the tracking data emitted from the workflow and store it into different mediums.</span></span> <span data-ttu-id="23e6d-132">Analogamente, è anche possibile eseguire qualsiasi operazione di post-elaborazione sui record di rilevamento all'interno del partecipante del rilevamento.</span><span class="sxs-lookup"><span data-stu-id="23e6d-132">Likewise, any post processing on the tracking Records can also be done within the tracking participant.</span></span>  
  
 <span data-ttu-id="23e6d-133">Più partecipanti del rilevamento possono usare simultaneamente gli eventi di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="23e6d-133">Multiple tracking participants can consume the tracking events simultaneously.</span></span> <span data-ttu-id="23e6d-134">Ogni partecipante del rilevamento può essere associato a un profilo di rilevamento diverso.</span><span class="sxs-lookup"><span data-stu-id="23e6d-134">Each tracking participant can be associated with a different tracking profile.</span></span>  
  
 <span data-ttu-id="23e6d-135">Viene fornito un partecipante del rilevamento standard che scrive i record di rilevamento in una sessione ETW.</span><span class="sxs-lookup"><span data-stu-id="23e6d-135">A standard tracking participant is provided which writes the tracking records to an ETW session.</span></span> <span data-ttu-id="23e6d-136">Il partecipante viene configurato su un servizio flusso di lavoro aggiungendo un comportamento specifico del rilevamento in un file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="23e6d-136">The participant is configured on a workflow service by adding a tracking-specific behavior in a configuration file.</span></span> <span data-ttu-id="23e6d-137">L'abilitazione di un partecipante del rilevamento ETW consente la visualizzazione dei record di rilevamento nel Visualizzatore eventi.</span><span class="sxs-lookup"><span data-stu-id="23e6d-137">Enabling an ETW tracking participant allows tracking records to be viewed in the event viewer.</span></span> <span data-ttu-id="23e6d-138">Se tale partecipante non soddisfa i propri requisiti, è anche possibile scrivere un partecipante del rilevamento personalizzato.</span><span class="sxs-lookup"><span data-stu-id="23e6d-138">If that does not meet your requirements, you can also write a custom tracking participant.</span></span>  
  
## <a name="example"></a><span data-ttu-id="23e6d-139">Esempio</span><span class="sxs-lookup"><span data-stu-id="23e6d-139">Example</span></span>  
 <span data-ttu-id="23e6d-140">Nell'esempio di configurazione seguente viene mostrato il partecipante del rilevamento ETW standard configurato nel file Web.config.</span><span class="sxs-lookup"><span data-stu-id="23e6d-140">The following configuration example shows the standard ETW tracking participant being configured in the Web.config file.</span></span>  
  
 <span data-ttu-id="23e6d-141">L'ID provider utilizzato dal partecipante del rilevamento ETW per scrivere i record di rilevamento in ETW è definito nella sezione relativa alla>di \*\* \<diagnostica.\*\*</span><span class="sxs-lookup"><span data-stu-id="23e6d-141">The Provider Id that the ETW Tracking Participant uses for writing the Tracking Records to ETW is defined in the **\<diagnostics>** section.</span></span> <span data-ttu-id="23e6d-142">Al partecipante di rilevamento è associato un profilo per specificare i record di rilevamento che ha sottoscritto.</span><span class="sxs-lookup"><span data-stu-id="23e6d-142">The tracking participant has a profile associated with it to specify the tracking records it has subscribed to.</span></span> <span data-ttu-id="23e6d-143">Questo è definito dall'attributo **profileName** dell'elemento \*\* \<add>.\*\*</span><span class="sxs-lookup"><span data-stu-id="23e6d-143">This is defined by the **profileName** attribute of the **\<add>** element.</span></span> <span data-ttu-id="23e6d-144">Una volta definiti, il partecipante di rilevamento viene aggiunto al comportamento del servizio \*\* \<etwTracking>.\*\*</span><span class="sxs-lookup"><span data-stu-id="23e6d-144">Once these are defined, the Tracking Participant is added to the **\<etwTracking>** service behavior.</span></span> <span data-ttu-id="23e6d-145">che aggiungerà i partecipanti del rilevamento selezionati alle estensioni dell'istanza del flusso di lavoro, in modo che inizino a ricevere i record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="23e6d-145">This will add the selected Tracking Participants to the Workflow instance’s extensions, so that they begin to receive the Tracking Records.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="23e6d-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="23e6d-146">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.TrackingSection>
- <xref:System.ServiceModel.Activities.Description.EtwTrackingBehavior>
- <xref:System.ServiceModel.Activities.Configuration.EtwTrackingBehaviorElement>
- [<span data-ttu-id="23e6d-147">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="23e6d-147">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="23e6d-148">Partecipanti di rilevamento</span><span class="sxs-lookup"><span data-stu-id="23e6d-148">Tracking Participants</span></span>](../../../windows-workflow-foundation/tracking-participants.md)
