---
title: <etwTracking>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: cb45c82e-6ea1-4c4d-924c-118a25ae1f35
ms.openlocfilehash: d562bd4e3d46a1bdf41fc4065fee926850a49aa1
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79152171"
---
# \<etwTracking>
<span data-ttu-id="463a9-101">Comportamento del servizio che consente a un servizio di utilizzare il rilevamento ETW mediante un oggetto <xref:System.Activities.Tracking.EtwTrackingParticipant>.</span><span class="sxs-lookup"><span data-stu-id="463a9-101">A service behavior that allows a service to utilize ETW tracking using an <xref:System.Activities.Tracking.EtwTrackingParticipant>.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<etwTracking>**  
  
## <a name="syntax"></a><span data-ttu-id="463a9-102">Sintassi</span><span class="sxs-lookup"><span data-stu-id="463a9-102">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <etwTracking profileName="String" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="463a9-103">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="463a9-103">Attributes and Elements</span></span>  
 <span data-ttu-id="463a9-104">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="463a9-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="463a9-105">Attributi</span><span class="sxs-lookup"><span data-stu-id="463a9-105">Attributes</span></span>  
  
|<span data-ttu-id="463a9-106">Attributo</span><span class="sxs-lookup"><span data-stu-id="463a9-106">Attribute</span></span>|<span data-ttu-id="463a9-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="463a9-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="463a9-108">profileName</span><span class="sxs-lookup"><span data-stu-id="463a9-108">profileName</span></span>|<span data-ttu-id="463a9-109">Stringa che specifica il nome del profilo di rilevamento associato a questo comportamento.</span><span class="sxs-lookup"><span data-stu-id="463a9-109">A string that specifies the name of the tracking profile associated with this behavior.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="463a9-110">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="463a9-110">Child Elements</span></span>  
 <span data-ttu-id="463a9-111">No.</span><span class="sxs-lookup"><span data-stu-id="463a9-111">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="463a9-112">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="463a9-112">Parent Elements</span></span>  
  
|<span data-ttu-id="463a9-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="463a9-113">Element</span></span>|<span data-ttu-id="463a9-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="463a9-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="463a9-115">\<behavior>di\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="463a9-115">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="463a9-116">Specifica un elemento di comportamento.</span><span class="sxs-lookup"><span data-stu-id="463a9-116">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="463a9-117">Commenti</span><span class="sxs-lookup"><span data-stu-id="463a9-117">Remarks</span></span>  
 <span data-ttu-id="463a9-118">Quando viene aggiunto alla configurazione del comportamento del servizio, questo elemento di configurazione configura un partecipante del rilevamento su un servizio flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="463a9-118">When added to the service’s behavior configuration, this configuration element configures a tracking participant on a workflow service.</span></span>  
  
 <span data-ttu-id="463a9-119">I partecipanti del rilevamento vengono usati per ottenere i dati di rilevamento generati dal flusso di lavoro e archiviarli in supporti differenti.</span><span class="sxs-lookup"><span data-stu-id="463a9-119">Tracking participants are used to get the tracking data emitted from the workflow and store it into different mediums.</span></span> <span data-ttu-id="463a9-120">Analogamente, è anche possibile eseguire qualsiasi operazione di post-elaborazione sui record di rilevamento all'interno del partecipante del rilevamento.</span><span class="sxs-lookup"><span data-stu-id="463a9-120">Likewise, any post processing on the tracking Records can also be done within the tracking participant.</span></span>  
  
## <a name="example"></a><span data-ttu-id="463a9-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="463a9-121">Example</span></span>  
 <span data-ttu-id="463a9-122">Nell'esempio di configurazione seguente viene mostrato il partecipante del rilevamento ETW standard configurato nel file Web.config.</span><span class="sxs-lookup"><span data-stu-id="463a9-122">The following configuration example shows the standard ETW tracking participant being configured in the Web.config file.</span></span>  
  
 <span data-ttu-id="463a9-123">L'ID del provider utilizzato dal partecipante del rilevamento ETW per la scrittura dei record di rilevamento in ETW è definito nella **\<diagnostics>** sezione.</span><span class="sxs-lookup"><span data-stu-id="463a9-123">The Provider Id that the ETW Tracking Participant uses for writing the Tracking Records to ETW is defined in the **\<diagnostics>** section.</span></span> <span data-ttu-id="463a9-124">Al partecipante di rilevamento è associato un profilo per specificare i record di rilevamento che ha sottoscritto.</span><span class="sxs-lookup"><span data-stu-id="463a9-124">The tracking participant has a profile associated with it to specify the tracking records it has subscribed to.</span></span> <span data-ttu-id="463a9-125">Questa operazione viene definita dall'attributo **ProfileName** dell' **\<add>** elemento.</span><span class="sxs-lookup"><span data-stu-id="463a9-125">This is defined by the **profileName** attribute of the **\<add>** element.</span></span> <span data-ttu-id="463a9-126">Una volta definite, il partecipante del rilevamento viene aggiunto al **\<etwTracking>** comportamento del servizio.</span><span class="sxs-lookup"><span data-stu-id="463a9-126">Once these are defined, the Tracking Participant is added to the **\<etwTracking>** service behavior.</span></span> <span data-ttu-id="463a9-127">che aggiungerà i partecipanti del rilevamento selezionati alle estensioni dell'istanza del flusso di lavoro, in modo che inizino a ricevere i record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="463a9-127">This will add the selected Tracking Participants to the Workflow instance’s extensions, so that they begin to receive the Tracking Records.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="463a9-128">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="463a9-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.EtwTrackingBehavior>
- <xref:System.ServiceModel.Activities.Configuration.EtwTrackingBehaviorElement>
- [<span data-ttu-id="463a9-129">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="463a9-129">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="463a9-130">Partecipanti di rilevamento</span><span class="sxs-lookup"><span data-stu-id="463a9-130">Tracking Participants</span></span>](../../../windows-workflow-foundation/tracking-participants.md)
