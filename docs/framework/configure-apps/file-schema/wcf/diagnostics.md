---
title: <diagnostics>
ms.date: 03/30/2017
ms.assetid: 0c2f95c4-cc12-4fb5-a70c-7fc6fa95db58
ms.openlocfilehash: 170cae5b328c86073c1d8e7710bb19e98ab5688c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925868"
---
# <a name="diagnostics"></a><span data-ttu-id="1c4fc-101">\<> di diagnostica</span><span class="sxs-lookup"><span data-stu-id="1c4fc-101">\<diagnostics></span></span>
<span data-ttu-id="1c4fc-102">L'elemento `diagnostics` definisce le impostazioni che possono essere usate da un amministratore per il controllo e l'ispezione in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="1c4fc-102">The `diagnostics` element defines settings that can be used by an administrator for run-time inspection and control.</span></span>  
  
 <span data-ttu-id="1c4fc-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="1c4fc-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="1c4fc-104">\<> di diagnostica</span><span class="sxs-lookup"><span data-stu-id="1c4fc-104">\<diagnostics></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c4fc-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1c4fc-105">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <diagnostics etwProviderId="String"
               performanceCounters="Off/ServiceOnly/All/Default"
               wmiProviderEnabled="Boolean">
    <endToEndTracing activityTracing="Boolean"
                     messageFlowTracing="Boolean"
                     propagateActivity="Boolean" />
    <messageLogging logEntireMessage="Boolean"
                    logMalformedMessages="Boolean"
                    logMessagesAtServiceLevel="Boolean"
                    logMessagesAtTransportLevel="Boolean"
                    maxMessagesToLog="Integer"
                    maxSizeOfMessageToLog="Integer">
      <filters>
        <clear />
      </filters>
    </messageLogging>
  </diagnostics>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1c4fc-106">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="1c4fc-106">Attributes and Elements</span></span>  
 <span data-ttu-id="1c4fc-107">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="1c4fc-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1c4fc-108">Attributi</span><span class="sxs-lookup"><span data-stu-id="1c4fc-108">Attributes</span></span>  
  
|<span data-ttu-id="1c4fc-109">Attributo</span><span class="sxs-lookup"><span data-stu-id="1c4fc-109">Attribute</span></span>|<span data-ttu-id="1c4fc-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1c4fc-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1c4fc-111">etwProviderId</span><span class="sxs-lookup"><span data-stu-id="1c4fc-111">etwProviderId</span></span>|<span data-ttu-id="1c4fc-112">Stringa che specifica l'identificatore per il provider Event-Tracing che determina la scrittura di eventi nelle sessioni ETW.</span><span class="sxs-lookup"><span data-stu-id="1c4fc-112">A string that specifies the identifier for the Event-Tracing provider, which writes events to ETW sessions.</span></span>|  
|<span data-ttu-id="1c4fc-113">performanceCounters</span><span class="sxs-lookup"><span data-stu-id="1c4fc-113">performanceCounters</span></span>|<span data-ttu-id="1c4fc-114">Specifica se sono abilitati i contatori delle prestazioni per l'assembly.</span><span class="sxs-lookup"><span data-stu-id="1c4fc-114">Specifies whether performance counters for the assembly are enabled.</span></span> <span data-ttu-id="1c4fc-115">I valori validi sono:</span><span class="sxs-lookup"><span data-stu-id="1c4fc-115">Valid values are</span></span><br /><br /> <span data-ttu-id="1c4fc-116">Off I contatori delle prestazioni sono disattivati.</span><span class="sxs-lookup"><span data-stu-id="1c4fc-116">-   Off: Performance counters are disabled.</span></span><br /><span data-ttu-id="1c4fc-117">ServiceOnly Sono attivati solo i contatori delle prestazioni attinenti a questo servizio.</span><span class="sxs-lookup"><span data-stu-id="1c4fc-117">-   ServiceOnly: Only performance counters relevant to this service is enabled.</span></span><br /><span data-ttu-id="1c4fc-118">Tutti I contatori delle prestazioni possono essere visualizzati in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="1c4fc-118">-   All: Performance counters can be viewed at runtime.</span></span><br /><span data-ttu-id="1c4fc-119">Predefinita Viene creata una sola istanza del contatore delle prestazioni _WCF_Admin.</span><span class="sxs-lookup"><span data-stu-id="1c4fc-119">-   Default: A single performance counter instance _WCF_Admin is created.</span></span> <span data-ttu-id="1c4fc-120">L'istanza viene usata per attivare la raccolta di dati SQM che devono essere usati dall'infrastruttura.</span><span class="sxs-lookup"><span data-stu-id="1c4fc-120">This instance is used to enable the collection of SQM data for used by the infrastructure.</span></span> <span data-ttu-id="1c4fc-121">Nessuno dei valori di contatore per questa istanza è aggiornato e pertanto rimarrà a zero.</span><span class="sxs-lookup"><span data-stu-id="1c4fc-121">None of the counter values for this instance are updated and therefore will remain at zero.</span></span> <span data-ttu-id="1c4fc-122">Questo è il valore predefinito se per WCF non è presente alcuna configurazione.</span><span class="sxs-lookup"><span data-stu-id="1c4fc-122">This is the default value if no configuration is present for WCF.</span></span>|  
|<span data-ttu-id="1c4fc-123">wmiProviderEnabled</span><span class="sxs-lookup"><span data-stu-id="1c4fc-123">wmiProviderEnabled</span></span>|<span data-ttu-id="1c4fc-124">Valore booleano che specifica se il provider WMI per l'assembly è abilitato.</span><span class="sxs-lookup"><span data-stu-id="1c4fc-124">A Boolean value that specifies whether the WMI provider for the assembly is enabled.</span></span> <span data-ttu-id="1c4fc-125">Il provider WMI è necessario per consentire all'utente di ottenere l'accesso in fase di esecuzione alle funzionalità di ispezione e controllo di Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="1c4fc-125">The WMI provider is required for user to gain run-time access to the inspection and control features of Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="1c4fc-126">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="1c4fc-126">The default is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1c4fc-127">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="1c4fc-127">Child Elements</span></span>  
  
|<span data-ttu-id="1c4fc-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="1c4fc-128">Element</span></span>|<span data-ttu-id="1c4fc-129">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1c4fc-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1c4fc-130">\<endToEndTracing></span><span class="sxs-lookup"><span data-stu-id="1c4fc-130">\<endToEndTracing></span></span>](endtoendtracing.md)|<span data-ttu-id="1c4fc-131">Elemento di configurazione che consente di abilitare e disabilitare aspetti diversi di traccia end-to-end durante l'esecuzione di un'applicazione di servizio.</span><span class="sxs-lookup"><span data-stu-id="1c4fc-131">A configuration element that allows you to enable and disable different aspects of end-to-end tracing during the running of a service application.</span></span>|  
|[<span data-ttu-id="1c4fc-132">\<messageLogging></span><span class="sxs-lookup"><span data-stu-id="1c4fc-132">\<messageLogging></span></span>](messagelogging.md)|<span data-ttu-id="1c4fc-133">Descrive le impostazioni per la registrazione dei messaggi WCF.</span><span class="sxs-lookup"><span data-stu-id="1c4fc-133">Describes the settings for WCF message logging.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1c4fc-134">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="1c4fc-134">Parent Elements</span></span>  
  
|<span data-ttu-id="1c4fc-135">Elemento</span><span class="sxs-lookup"><span data-stu-id="1c4fc-135">Element</span></span>|<span data-ttu-id="1c4fc-136">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1c4fc-136">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1c4fc-137">serviceModel</span><span class="sxs-lookup"><span data-stu-id="1c4fc-137">serviceModel</span></span>|<span data-ttu-id="1c4fc-138">Elemento radice di tutti gli elementi di configurazione WCF.</span><span class="sxs-lookup"><span data-stu-id="1c4fc-138">The root element of all WCF configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1c4fc-139">Note</span><span class="sxs-lookup"><span data-stu-id="1c4fc-139">Remarks</span></span>  
 <span data-ttu-id="1c4fc-140">La sezione `diagnostics` definisce le impostazioni dei diagnostica per tutti i servizi trovati in un assembly.</span><span class="sxs-lookup"><span data-stu-id="1c4fc-140">The `diagnostics` section defines the diagnostics settings for all services located in an assembly.</span></span> <span data-ttu-id="1c4fc-141">Non è possibile definire impostazioni diagnostiche separate a livello di servizio a meno che l'assembly non comprenda solo uno servizio.</span><span class="sxs-lookup"><span data-stu-id="1c4fc-141">It is not possible to define separate diagnostics settings at the service level unless there is only one service in the assembly.</span></span> <span data-ttu-id="1c4fc-142">Gli attributi sono impostati secondo i requisiti della sezione.</span><span class="sxs-lookup"><span data-stu-id="1c4fc-142">Attributes are set according to the requirements of the section.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1c4fc-143">Esempio</span><span class="sxs-lookup"><span data-stu-id="1c4fc-143">Example</span></span>  
  
```xml  
<diagnostics wmiProviderEnabled="false"
             performanceCounters="all">
  <messageLogging logEntireMessage="true"
                  logMalformedMessages="true"
                  logMessagesAtServiceLevel="true"
                  logMessagesAtTransportLevel="true"
                  maxMessagesToLog="42"
                  maxSizeOfMessageToLog="42">
    <filters>
      <clear />
    </filters>
  </messageLogging>
</diagnostics>
```  
  
## <a name="see-also"></a><span data-ttu-id="1c4fc-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1c4fc-144">See also</span></span>

- <xref:System.ServiceModel.Configuration.DiagnosticSection>
- <xref:System.ServiceModel.Diagnostics>
