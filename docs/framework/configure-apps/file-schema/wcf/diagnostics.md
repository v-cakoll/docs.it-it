---
title: <diagnostics>
ms.date: 03/30/2017
ms.assetid: 0c2f95c4-cc12-4fb5-a70c-7fc6fa95db58
ms.openlocfilehash: 2749bc6c66d491a8a160d98b508fb43aa027b806
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398048"
---
# \<diagnostics>
<span data-ttu-id="64254-101">L'elemento `diagnostics` definisce le impostazioni che possono essere usate da un amministratore per il controllo e l'ispezione in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="64254-101">The `diagnostics` element defines settings that can be used by an administrator for run-time inspection and control.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<diagnostics>**  
  
## <a name="syntax"></a><span data-ttu-id="64254-102">Sintassi</span><span class="sxs-lookup"><span data-stu-id="64254-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="64254-103">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="64254-103">Attributes and Elements</span></span>  
 <span data-ttu-id="64254-104">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="64254-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="64254-105">Attributi</span><span class="sxs-lookup"><span data-stu-id="64254-105">Attributes</span></span>  
  
|<span data-ttu-id="64254-106">Attributo</span><span class="sxs-lookup"><span data-stu-id="64254-106">Attribute</span></span>|<span data-ttu-id="64254-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="64254-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="64254-108">etwProviderId</span><span class="sxs-lookup"><span data-stu-id="64254-108">etwProviderId</span></span>|<span data-ttu-id="64254-109">Stringa che specifica l'identificatore per il provider Event-Tracing che determina la scrittura di eventi nelle sessioni ETW.</span><span class="sxs-lookup"><span data-stu-id="64254-109">A string that specifies the identifier for the Event-Tracing provider, which writes events to ETW sessions.</span></span>|  
|<span data-ttu-id="64254-110">performanceCounters</span><span class="sxs-lookup"><span data-stu-id="64254-110">performanceCounters</span></span>|<span data-ttu-id="64254-111">Specifica se sono abilitati i contatori delle prestazioni per l'assembly.</span><span class="sxs-lookup"><span data-stu-id="64254-111">Specifies whether performance counters for the assembly are enabled.</span></span> <span data-ttu-id="64254-112">I valori validi sono:</span><span class="sxs-lookup"><span data-stu-id="64254-112">Valid values are</span></span><br /><br /> <span data-ttu-id="64254-113">-Off: i contatori delle prestazioni sono disabilitati.</span><span class="sxs-lookup"><span data-stu-id="64254-113">-   Off: Performance counters are disabled.</span></span><br /><span data-ttu-id="64254-114">-ServiceOnly: sono abilitati solo i contatori delle prestazioni rilevanti per questo servizio.</span><span class="sxs-lookup"><span data-stu-id="64254-114">-   ServiceOnly: Only performance counters relevant to this service is enabled.</span></span><br /><span data-ttu-id="64254-115">-All: i contatori delle prestazioni possono essere visualizzati in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="64254-115">-   All: Performance counters can be viewed at runtime.</span></span><br /><span data-ttu-id="64254-116">-Default: viene creata una singola istanza del contatore delle prestazioni _WCF_Admin.</span><span class="sxs-lookup"><span data-stu-id="64254-116">-   Default: A single performance counter instance _WCF_Admin is created.</span></span> <span data-ttu-id="64254-117">L'istanza viene usata per attivare la raccolta di dati SQM che devono essere usati dall'infrastruttura.</span><span class="sxs-lookup"><span data-stu-id="64254-117">This instance is used to enable the collection of SQM data for used by the infrastructure.</span></span> <span data-ttu-id="64254-118">Nessuno dei valori di contatore per questa istanza è aggiornato e pertanto rimarrà a zero.</span><span class="sxs-lookup"><span data-stu-id="64254-118">None of the counter values for this instance are updated and therefore will remain at zero.</span></span> <span data-ttu-id="64254-119">Questo è il valore predefinito se per WCF non è presente alcuna configurazione.</span><span class="sxs-lookup"><span data-stu-id="64254-119">This is the default value if no configuration is present for WCF.</span></span>|  
|<span data-ttu-id="64254-120">wmiProviderEnabled</span><span class="sxs-lookup"><span data-stu-id="64254-120">wmiProviderEnabled</span></span>|<span data-ttu-id="64254-121">Valore booleano che specifica se il provider WMI per l'assembly è abilitato.</span><span class="sxs-lookup"><span data-stu-id="64254-121">A Boolean value that specifies whether the WMI provider for the assembly is enabled.</span></span> <span data-ttu-id="64254-122">Il provider WMI è necessario per consentire all'utente di ottenere l'accesso in fase di esecuzione alle funzionalità di ispezione e controllo di Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="64254-122">The WMI provider is required for user to gain run-time access to the inspection and control features of Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="64254-123">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="64254-123">The default is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="64254-124">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="64254-124">Child Elements</span></span>  
  
|<span data-ttu-id="64254-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="64254-125">Element</span></span>|<span data-ttu-id="64254-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="64254-126">Description</span></span>|  
|-------------|-----------------|  
|[\<endToEndTracing>](endtoendtracing.md)|<span data-ttu-id="64254-127">Elemento di configurazione che consente di abilitare e disabilitare aspetti diversi di traccia end-to-end durante l'esecuzione di un'applicazione di servizio.</span><span class="sxs-lookup"><span data-stu-id="64254-127">A configuration element that allows you to enable and disable different aspects of end-to-end tracing during the running of a service application.</span></span>|  
|[\<messageLogging>](messagelogging.md)|<span data-ttu-id="64254-128">Descrive le impostazioni per la registrazione dei messaggi WCF.</span><span class="sxs-lookup"><span data-stu-id="64254-128">Describes the settings for WCF message logging.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="64254-129">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="64254-129">Parent Elements</span></span>  
  
|<span data-ttu-id="64254-130">Elemento</span><span class="sxs-lookup"><span data-stu-id="64254-130">Element</span></span>|<span data-ttu-id="64254-131">Descrizione</span><span class="sxs-lookup"><span data-stu-id="64254-131">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="64254-132">serviceModel</span><span class="sxs-lookup"><span data-stu-id="64254-132">serviceModel</span></span>|<span data-ttu-id="64254-133">Elemento radice di tutti gli elementi di configurazione WCF.</span><span class="sxs-lookup"><span data-stu-id="64254-133">The root element of all WCF configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="64254-134">Commenti</span><span class="sxs-lookup"><span data-stu-id="64254-134">Remarks</span></span>  
 <span data-ttu-id="64254-135">La sezione `diagnostics` definisce le impostazioni dei diagnostica per tutti i servizi trovati in un assembly.</span><span class="sxs-lookup"><span data-stu-id="64254-135">The `diagnostics` section defines the diagnostics settings for all services located in an assembly.</span></span> <span data-ttu-id="64254-136">Non è possibile definire impostazioni diagnostiche separate a livello di servizio a meno che l'assembly non comprenda solo uno servizio.</span><span class="sxs-lookup"><span data-stu-id="64254-136">It is not possible to define separate diagnostics settings at the service level unless there is only one service in the assembly.</span></span> <span data-ttu-id="64254-137">Gli attributi sono impostati secondo i requisiti della sezione.</span><span class="sxs-lookup"><span data-stu-id="64254-137">Attributes are set according to the requirements of the section.</span></span>  
  
## <a name="example"></a><span data-ttu-id="64254-138">Esempio</span><span class="sxs-lookup"><span data-stu-id="64254-138">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="64254-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="64254-139">See also</span></span>

- <xref:System.ServiceModel.Configuration.DiagnosticSection>
- <xref:System.ServiceModel.Diagnostics>
