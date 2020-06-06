---
title: <participants>di WCF
ms.date: 03/30/2017
ms.assetid: d99dbddc-0057-4e18-8e42-f91411d39970
ms.openlocfilehash: 35ed7a49967143838a6f74c51e77c553817bd09a
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855090"
---
# <a name="participants-of-wcf"></a><span data-ttu-id="18394-102">\<participants>di WCF</span><span class="sxs-lookup"><span data-stu-id="18394-102">\<participants> of WCF</span></span>
<span data-ttu-id="18394-103">Configurare un elenco di partecipanti del rilevamento che ascoltano i record di rilevamento generati direttamente durante la fase di esecuzione e li elaborano in base alle impostazioni configurate.</span><span class="sxs-lookup"><span data-stu-id="18394-103">Configure a list of tracking participants that listen to the tracking records being emitted from the runtime directly and process them in whatever way they are configured.</span></span> <span data-ttu-id="18394-104">Tali impostazioni includono la scrittura in un output specifico, ad esempio file, console, ETW, l'elaborazione/aggregazione dei record o qualsiasi altra combinazione che potrebbe essere richiesta.</span><span class="sxs-lookup"><span data-stu-id="18394-104">This includes writing to a specific output (e.g., file, Console, ETW), processing/aggregating the records, or any other combination that might be required.</span></span>  
  
<span data-ttu-id="18394-105">Per altre informazioni sui partecipanti di rilevamento e rilevamento del flusso di lavoro, vedere Rilevamento e traccia [del flusso di lavoro](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) [partecipanti](../../../windows-workflow-foundation/tracking-participants.md).</span><span class="sxs-lookup"><span data-stu-id="18394-105">For more information in workflow tracking and tracking participants, see [Workflow Tracking and Tracing](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Tracking Participants](../../../windows-workflow-foundation/tracking-participants.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<participants>**  
  
## <a name="syntax"></a><span data-ttu-id="18394-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="18394-106">Syntax</span></span>  
  
```xml  
<tracking>
  <participants>
    <add name="String"
         profileName="String"
         type="String" />
  </participants>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="18394-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="18394-107">Attributes and Elements</span></span>  
 <span data-ttu-id="18394-108">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="18394-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="18394-109">Attributi</span><span class="sxs-lookup"><span data-stu-id="18394-109">Attributes</span></span>  
 <span data-ttu-id="18394-110">No.</span><span class="sxs-lookup"><span data-stu-id="18394-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="18394-111">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="18394-111">Child Elements</span></span>  
  
|<span data-ttu-id="18394-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="18394-112">Element</span></span>|<span data-ttu-id="18394-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="18394-113">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](../windows-workflow-foundation/add-of-participants.md)|<span data-ttu-id="18394-114">Contiene impostazioni per un partecipante del rilevamento.</span><span class="sxs-lookup"><span data-stu-id="18394-114">Contains settings for a tracking participant.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="18394-115">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="18394-115">Parent Elements</span></span>  
  
|<span data-ttu-id="18394-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="18394-116">Element</span></span>|<span data-ttu-id="18394-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="18394-117">Description</span></span>|  
|-------------|-----------------|  
|[\<tracking>](../windows-workflow-foundation/tracking.md)|<span data-ttu-id="18394-118">Rappresenta una sezione di configurazione per la definizione delle impostazioni di rilevamento di un servizio flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="18394-118">Represents a configuration section for defining tracking settings for a workflow service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="18394-119">Commenti</span><span class="sxs-lookup"><span data-stu-id="18394-119">Remarks</span></span>  
 <span data-ttu-id="18394-120">I partecipanti del rilevamento vengono usati per ottenere i dati di rilevamento generati dal flusso di lavoro e archiviarli in supporti differenti.</span><span class="sxs-lookup"><span data-stu-id="18394-120">Tracking participants are used to get the tracking data emitted from the workflow and store it into different mediums.</span></span> <span data-ttu-id="18394-121">Analogamente, è anche possibile eseguire qualsiasi operazione di post-elaborazione sui record di rilevamento all'interno del partecipante del rilevamento.</span><span class="sxs-lookup"><span data-stu-id="18394-121">Likewise, any post processing on the tracking Records can also be done within the tracking participant.</span></span>  
  
 <span data-ttu-id="18394-122">Più partecipanti del rilevamento possono usare simultaneamente gli eventi di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="18394-122">Multiple tracking participants can consume the tracking events simultaneously.</span></span> <span data-ttu-id="18394-123">Ogni partecipante del rilevamento può essere associato a un profilo di rilevamento diverso.</span><span class="sxs-lookup"><span data-stu-id="18394-123">Each tracking participant can be associated with a different tracking profile.</span></span>  
  
 <span data-ttu-id="18394-124">Viene fornito un partecipante del rilevamento standard che scrive i record di rilevamento in una sessione ETW.</span><span class="sxs-lookup"><span data-stu-id="18394-124">A standard tracking participant is provided which writes the tracking records to an ETW session.</span></span> <span data-ttu-id="18394-125">Il partecipante viene configurato su un servizio flusso di lavoro aggiungendo un comportamento specifico del rilevamento in un file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="18394-125">The participant is configured on a workflow service by adding a tracking-specific behavior in a configuration file.</span></span> <span data-ttu-id="18394-126">L'abilitazione di un partecipante del rilevamento ETW consente la visualizzazione dei record di rilevamento nel Visualizzatore eventi.</span><span class="sxs-lookup"><span data-stu-id="18394-126">Enabling an ETW tracking participant allows tracking records to be viewed in the event viewer.</span></span> <span data-ttu-id="18394-127">Se tale partecipante non soddisfa i propri requisiti, è anche possibile scrivere un partecipante del rilevamento personalizzato.</span><span class="sxs-lookup"><span data-stu-id="18394-127">If that does not meet your requirements, you can also write a custom tracking participant.</span></span>  
  
## <a name="example"></a><span data-ttu-id="18394-128">Esempio</span><span class="sxs-lookup"><span data-stu-id="18394-128">Example</span></span>  
 <span data-ttu-id="18394-129">Nell'esempio di configurazione seguente viene mostrato il partecipante del rilevamento ETW standard configurato nel file Web.config.</span><span class="sxs-lookup"><span data-stu-id="18394-129">The following configuration example shows the standard ETW tracking participant being configured in the Web.config file.</span></span>  
  
 <span data-ttu-id="18394-130">L'ID del provider usato dal partecipante del rilevamento ETW per scrivere i record di rilevamento in ETW è definito nella sezione `<diagnostics>`.</span><span class="sxs-lookup"><span data-stu-id="18394-130">The Provider Id that the ETW Tracking Participant uses for writing the Tracking Records to ETW is defined in the `<diagnostics>` section.</span></span> <span data-ttu-id="18394-131">Al partecipante di rilevamento è associato un profilo per specificare i record di rilevamento che ha sottoscritto.</span><span class="sxs-lookup"><span data-stu-id="18394-131">The tracking participant has a profile associated with it to specify the tracking records it has subscribed to.</span></span> <span data-ttu-id="18394-132">Tale profilo è definito dall'attributo `profileName` dell'elemento `<add>`.</span><span class="sxs-lookup"><span data-stu-id="18394-132">This is defined by the `profileName` attribute of the `<add>` element.</span></span> <span data-ttu-id="18394-133">Dopo aver definito tali elementi, il partecipante del rilevamento viene aggiunto al comportamento del servizio `<etwTracking>`,</span><span class="sxs-lookup"><span data-stu-id="18394-133">Once these are defined, the Tracking Participant is added to the `<etwTracking>` service behavior.</span></span> <span data-ttu-id="18394-134">che aggiungerà i partecipanti del rilevamento selezionati alle estensioni dell'istanza del flusso di lavoro, in modo che inizino a ricevere i record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="18394-134">This will add the selected Tracking Participants to the Workflow instance’s extensions, so that they begin to receive the Tracking Records.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="18394-135">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="18394-135">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.TrackingSection>
- <xref:System.ServiceModel.Activities.Description.EtwTrackingBehavior>
- [<span data-ttu-id="18394-136">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="18394-136">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="18394-137">Partecipanti di rilevamento</span><span class="sxs-lookup"><span data-stu-id="18394-137">Tracking Participants</span></span>](../../../windows-workflow-foundation/tracking-participants.md)
