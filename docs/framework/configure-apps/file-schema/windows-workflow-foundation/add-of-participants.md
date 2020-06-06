---
title: <add> di <participants>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 3c730850-6f8e-4102-acb8-8effb4e09463
ms.openlocfilehash: 61832edbf7d206d6a5f7a85619eb17ebc010c193
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79152359"
---
# <a name="add-of-participants"></a><span data-ttu-id="8769d-102">\<add> di \<participants></span><span class="sxs-lookup"><span data-stu-id="8769d-102">\<add> of \<participants></span></span>
<span data-ttu-id="8769d-103">Configurare un partecipante del rilevamento che ascolta i record di rilevamento generati direttamente durante la fase di esecuzione e li elabora in base alle impostazioni configurate.</span><span class="sxs-lookup"><span data-stu-id="8769d-103">Configure a tracking participant that listens to the tracking records being emitted from the runtime directly and process them in whatever way it was configured.</span></span> <span data-ttu-id="8769d-104">Tali impostazioni includono la scrittura in un output specifico, ad esempio file, console, ETW, l'elaborazione/aggregazione dei record o qualsiasi altra combinazione che potrebbe essere richiesta.</span><span class="sxs-lookup"><span data-stu-id="8769d-104">This includes writing to a specific output (e.g., file, Console, ETW), processing/aggregating the records, or any other combination that might be required.</span></span>  
  
 <span data-ttu-id="8769d-105">Per altre informazioni sui partecipanti di rilevamento e rilevamento del flusso di lavoro, vedere Rilevamento e traccia [del flusso di lavoro](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) [partecipanti](../../../windows-workflow-foundation/tracking-participants.md).</span><span class="sxs-lookup"><span data-stu-id="8769d-105">For more information in workflow tracking and tracking participants, see [Workflow Tracking and Tracing](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Tracking Participants](../../../windows-workflow-foundation/tracking-participants.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<participants>**](participants.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="8769d-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8769d-106">Syntax</span></span>  
  
```xml
<tracking>
  <participants>
    <add name="String" profileName="String" type="String" />
  </participants>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8769d-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="8769d-107">Attributes and Elements</span></span>  
 <span data-ttu-id="8769d-108">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="8769d-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8769d-109">Attributi</span><span class="sxs-lookup"><span data-stu-id="8769d-109">Attributes</span></span>  
  
|<span data-ttu-id="8769d-110">Elemento</span><span class="sxs-lookup"><span data-stu-id="8769d-110">Element</span></span>|<span data-ttu-id="8769d-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8769d-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8769d-112">name</span><span class="sxs-lookup"><span data-stu-id="8769d-112">name</span></span>|<span data-ttu-id="8769d-113">Stringa che specifica il nome di un partecipante del rilevamento.</span><span class="sxs-lookup"><span data-stu-id="8769d-113">A string that specifies the name of a tracking participant.</span></span>|  
|<span data-ttu-id="8769d-114">profileName</span><span class="sxs-lookup"><span data-stu-id="8769d-114">profileName</span></span>|<span data-ttu-id="8769d-115">Stringa che specifica il nome del profilo di rilevamento che definisce i record di rilevamento sottoscritti dal partecipante del rilevamento.</span><span class="sxs-lookup"><span data-stu-id="8769d-115">A string that specifies the name of the tracking profile which defines the tracking records the tracking participant has subscribed to.</span></span>|  
|<span data-ttu-id="8769d-116">tipo</span><span class="sxs-lookup"><span data-stu-id="8769d-116">type</span></span>|<span data-ttu-id="8769d-117">Stringa che specifica il tipo di un partecipante del rilevamento.</span><span class="sxs-lookup"><span data-stu-id="8769d-117">A string that specifies the type of a tracking participant.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8769d-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="8769d-118">Child Elements</span></span>  
 <span data-ttu-id="8769d-119">No.</span><span class="sxs-lookup"><span data-stu-id="8769d-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8769d-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="8769d-120">Parent Elements</span></span>  
  
|<span data-ttu-id="8769d-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="8769d-121">Element</span></span>|<span data-ttu-id="8769d-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8769d-122">Description</span></span>|  
|-------------|-----------------|  
|[\<participants>](participants.md)|<span data-ttu-id="8769d-123">Elenco di partecipanti del rilevamento.</span><span class="sxs-lookup"><span data-stu-id="8769d-123">A list of tracking participants</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8769d-124">Commenti</span><span class="sxs-lookup"><span data-stu-id="8769d-124">Remarks</span></span>  
 <span data-ttu-id="8769d-125">I partecipanti del rilevamento vengono usati per ottenere i dati di rilevamento generati dal flusso di lavoro e archiviarli in supporti differenti.</span><span class="sxs-lookup"><span data-stu-id="8769d-125">Tracking participants are used to get the tracking data emitted from the workflow and store it into different mediums.</span></span> <span data-ttu-id="8769d-126">Analogamente, è anche possibile eseguire qualsiasi operazione di post-elaborazione sui record di rilevamento all'interno del partecipante del rilevamento.</span><span class="sxs-lookup"><span data-stu-id="8769d-126">Likewise, any post processing on the tracking Records can also be done within the tracking participant.</span></span>  
  
 <span data-ttu-id="8769d-127">Più partecipanti del rilevamento possono usare simultaneamente gli eventi di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="8769d-127">Multiple tracking participants can consume the tracking events simultaneously.</span></span> <span data-ttu-id="8769d-128">Ogni partecipante del rilevamento può essere associato a un profilo di rilevamento diverso.</span><span class="sxs-lookup"><span data-stu-id="8769d-128">Each tracking participant can be associated with a different tracking profile.</span></span>  
  
 <span data-ttu-id="8769d-129">Viene fornito un partecipante del rilevamento standard che scrive i record di rilevamento in una sessione ETW.</span><span class="sxs-lookup"><span data-stu-id="8769d-129">A standard tracking participant is provided which writes the tracking records to an ETW session.</span></span> <span data-ttu-id="8769d-130">Il partecipante viene configurato su un servizio flusso di lavoro aggiungendo un comportamento specifico del rilevamento in un file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="8769d-130">The participant is configured on a workflow service by adding a tracking-specific behavior in a configuration file.</span></span> <span data-ttu-id="8769d-131">L'abilitazione di un partecipante del rilevamento ETW consente la visualizzazione dei record di rilevamento nel Visualizzatore eventi.</span><span class="sxs-lookup"><span data-stu-id="8769d-131">Enabling an ETW tracking participant allows tracking records to be viewed in the event viewer.</span></span> <span data-ttu-id="8769d-132">Se tale partecipante non soddisfa i propri requisiti, è anche possibile scrivere un partecipante del rilevamento personalizzato.</span><span class="sxs-lookup"><span data-stu-id="8769d-132">If that does not meet your requirements, you can also write a custom tracking participant.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8769d-133">Esempio</span><span class="sxs-lookup"><span data-stu-id="8769d-133">Example</span></span>  
 <span data-ttu-id="8769d-134">Nell'esempio di configurazione seguente viene mostrato il partecipante del rilevamento ETW standard configurato nel file Web.config.</span><span class="sxs-lookup"><span data-stu-id="8769d-134">The following configuration example shows the standard ETW tracking participant being configured in the Web.config file.</span></span>  
  
 <span data-ttu-id="8769d-135">L'ID del provider utilizzato dal partecipante del rilevamento ETW per la scrittura dei record di rilevamento in ETW è definito nella **\<diagnostics>** sezione.</span><span class="sxs-lookup"><span data-stu-id="8769d-135">The Provider Id that the ETW Tracking Participant uses for writing the Tracking Records to ETW is defined in the **\<diagnostics>** section.</span></span> <span data-ttu-id="8769d-136">Al partecipante di rilevamento è associato un profilo per specificare i record di rilevamento che ha sottoscritto.</span><span class="sxs-lookup"><span data-stu-id="8769d-136">The tracking participant has a profile associated with it to specify the tracking records it has subscribed to.</span></span> <span data-ttu-id="8769d-137">Questa operazione viene definita dall'attributo **ProfileName** dell' **\<add>** elemento.</span><span class="sxs-lookup"><span data-stu-id="8769d-137">This is defined by the **profileName** attribute of the **\<add>** element.</span></span> <span data-ttu-id="8769d-138">Una volta definite, il partecipante del rilevamento viene aggiunto al **\<etwTracking>** comportamento del servizio.</span><span class="sxs-lookup"><span data-stu-id="8769d-138">Once these are defined, the Tracking Participant is added to the **\<etwTracking>** service behavior.</span></span> <span data-ttu-id="8769d-139">che aggiungerà i partecipanti del rilevamento selezionati alle estensioni dell'istanza del flusso di lavoro, in modo che inizino a ricevere i record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="8769d-139">This will add the selected Tracking Participants to the Workflow instance’s extensions, so that they begin to receive the Tracking Records.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="8769d-140">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="8769d-140">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.TrackingSection>
- <xref:System.ServiceModel.Activities.Description.EtwTrackingBehavior>
- <xref:System.ServiceModel.Activities.Configuration.EtwTrackingBehaviorElement>
- [<span data-ttu-id="8769d-141">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="8769d-141">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="8769d-142">Partecipanti di rilevamento</span><span class="sxs-lookup"><span data-stu-id="8769d-142">Tracking Participants</span></span>](../../../windows-workflow-foundation/tracking-participants.md)
