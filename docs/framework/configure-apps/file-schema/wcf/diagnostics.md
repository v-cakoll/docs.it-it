---
title: '&lt;diagnostics&gt;'
ms.date: 03/30/2017
ms.assetid: 0c2f95c4-cc12-4fb5-a70c-7fc6fa95db58
ms.openlocfilehash: de11145620e8fdf96785908df85ab5ecdfd2e25e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54524593"
---
# <a name="ltdiagnosticsgt"></a><span data-ttu-id="2221c-102">&lt;diagnostics&gt;</span><span class="sxs-lookup"><span data-stu-id="2221c-102">&lt;diagnostics&gt;</span></span>
<span data-ttu-id="2221c-103">L'elemento `diagnostics` definisce le impostazioni che possono essere usate da un amministratore per il controllo e l'ispezione in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="2221c-103">The `diagnostics` element defines settings that can be used by an administrator for run-time inspection and control.</span></span>  
  
 <span data-ttu-id="2221c-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="2221c-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="2221c-105">\<diagnostica ></span><span class="sxs-lookup"><span data-stu-id="2221c-105">\<diagnostics></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2221c-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2221c-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2221c-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="2221c-107">Attributes and Elements</span></span>  
 <span data-ttu-id="2221c-108">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="2221c-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2221c-109">Attributi</span><span class="sxs-lookup"><span data-stu-id="2221c-109">Attributes</span></span>  
  
|<span data-ttu-id="2221c-110">Attributo</span><span class="sxs-lookup"><span data-stu-id="2221c-110">Attribute</span></span>|<span data-ttu-id="2221c-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2221c-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2221c-112">etwProviderId</span><span class="sxs-lookup"><span data-stu-id="2221c-112">etwProviderId</span></span>|<span data-ttu-id="2221c-113">Stringa che specifica l'identificatore per il provider Event-Tracing che determina la scrittura di eventi nelle sessioni ETW.</span><span class="sxs-lookup"><span data-stu-id="2221c-113">A string that specifies the identifier for the Event-Tracing provider, which writes events to ETW sessions.</span></span>|  
|<span data-ttu-id="2221c-114">performanceCounters</span><span class="sxs-lookup"><span data-stu-id="2221c-114">performanceCounters</span></span>|<span data-ttu-id="2221c-115">Specifica se sono abilitati i contatori delle prestazioni per l'assembly.</span><span class="sxs-lookup"><span data-stu-id="2221c-115">Specifies whether performance counters for the assembly are enabled.</span></span> <span data-ttu-id="2221c-116">I valori validi sono:</span><span class="sxs-lookup"><span data-stu-id="2221c-116">Valid values are</span></span><br /><br /> <span data-ttu-id="2221c-117">-Disattivata: I contatori delle prestazioni sono disattivati.</span><span class="sxs-lookup"><span data-stu-id="2221c-117">-   Off: Performance counters are disabled.</span></span><br /><span data-ttu-id="2221c-118">-ServiceOnly: Sono attivati solo i contatori delle prestazioni attinenti a questo servizio.</span><span class="sxs-lookup"><span data-stu-id="2221c-118">-   ServiceOnly: Only performance counters relevant to this service is enabled.</span></span><br /><span data-ttu-id="2221c-119">-Tutte: I contatori delle prestazioni possono essere visualizzati in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="2221c-119">-   All: Performance counters can be viewed at runtime.</span></span><br /><span data-ttu-id="2221c-120">-Il valore predefinito: Viene creata una sola istanza del contatore delle prestazioni _WCF_Admin.</span><span class="sxs-lookup"><span data-stu-id="2221c-120">-   Default: A single performance counter instance _WCF_Admin is created.</span></span> <span data-ttu-id="2221c-121">L'istanza viene usata per attivare la raccolta di dati SQM che devono essere usati dall'infrastruttura.</span><span class="sxs-lookup"><span data-stu-id="2221c-121">This instance is used to enable the collection of SQM data for used by the infrastructure.</span></span> <span data-ttu-id="2221c-122">Nessuno dei valori di contatore per questa istanza è aggiornato e pertanto rimarrà a zero.</span><span class="sxs-lookup"><span data-stu-id="2221c-122">None of the counter values for this instance are updated and therefore will remain at zero.</span></span> <span data-ttu-id="2221c-123">Questo è il valore predefinito se per WCF non è presente alcuna configurazione.</span><span class="sxs-lookup"><span data-stu-id="2221c-123">This is the default value if no configuration is present for WCF.</span></span>|  
|<span data-ttu-id="2221c-124">wmiProviderEnabled</span><span class="sxs-lookup"><span data-stu-id="2221c-124">wmiProviderEnabled</span></span>|<span data-ttu-id="2221c-125">Valore booleano che specifica se il provider WMI per l'assembly è abilitato.</span><span class="sxs-lookup"><span data-stu-id="2221c-125">A Boolean value that specifies whether the WMI provider for the assembly is enabled.</span></span> <span data-ttu-id="2221c-126">Il provider WMI è necessario per consentire all'utente di ottenere l'accesso in fase di esecuzione alle funzionalità di ispezione e controllo di Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="2221c-126">The WMI provider is required for user to gain run-time access to the inspection and control features of Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="2221c-127">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="2221c-127">The default is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2221c-128">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="2221c-128">Child Elements</span></span>  
  
|<span data-ttu-id="2221c-129">Elemento</span><span class="sxs-lookup"><span data-stu-id="2221c-129">Element</span></span>|<span data-ttu-id="2221c-130">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2221c-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2221c-131">\<endToEndTracing></span><span class="sxs-lookup"><span data-stu-id="2221c-131">\<endToEndTracing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endtoendtracing.md)|<span data-ttu-id="2221c-132">Elemento di configurazione che consente di abilitare e disabilitare aspetti diversi di traccia end-to-end durante l'esecuzione di un'applicazione di servizio.</span><span class="sxs-lookup"><span data-stu-id="2221c-132">A configuration element that allows you to enable and disable different aspects of end-to-end tracing during the running of a service application.</span></span>|  
|[<span data-ttu-id="2221c-133">\<messageLogging></span><span class="sxs-lookup"><span data-stu-id="2221c-133">\<messageLogging></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/messagelogging.md)|<span data-ttu-id="2221c-134">Descrive le impostazioni per la registrazione dei messaggi WCF.</span><span class="sxs-lookup"><span data-stu-id="2221c-134">Describes the settings for WCF message logging.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2221c-135">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="2221c-135">Parent Elements</span></span>  
  
|<span data-ttu-id="2221c-136">Elemento</span><span class="sxs-lookup"><span data-stu-id="2221c-136">Element</span></span>|<span data-ttu-id="2221c-137">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2221c-137">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2221c-138">serviceModel</span><span class="sxs-lookup"><span data-stu-id="2221c-138">serviceModel</span></span>|<span data-ttu-id="2221c-139">Elemento radice di tutti gli elementi di configurazione WCF.</span><span class="sxs-lookup"><span data-stu-id="2221c-139">The root element of all WCF configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2221c-140">Note</span><span class="sxs-lookup"><span data-stu-id="2221c-140">Remarks</span></span>  
 <span data-ttu-id="2221c-141">La sezione `diagnostics` definisce le impostazioni dei diagnostica per tutti i servizi trovati in un assembly.</span><span class="sxs-lookup"><span data-stu-id="2221c-141">The `diagnostics` section defines the diagnostics settings for all services located in an assembly.</span></span> <span data-ttu-id="2221c-142">Non è possibile definire impostazioni diagnostiche separate a livello di servizio a meno che l'assembly non comprenda solo uno servizio.</span><span class="sxs-lookup"><span data-stu-id="2221c-142">It is not possible to define separate diagnostics settings at the service level unless there is only one service in the assembly.</span></span> <span data-ttu-id="2221c-143">Gli attributi sono impostati secondo i requisiti della sezione.</span><span class="sxs-lookup"><span data-stu-id="2221c-143">Attributes are set according to the requirements of the section.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2221c-144">Esempio</span><span class="sxs-lookup"><span data-stu-id="2221c-144">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="2221c-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2221c-145">See also</span></span>
- <xref:System.ServiceModel.Configuration.DiagnosticSection>
- <xref:System.ServiceModel.Diagnostics>
