---
title: <messageLogging>
ms.date: 03/30/2017
ms.assetid: 1d06a7e6-9633-4a12-8c5d-123adbbc19c5
ms.openlocfilehash: 9291c38af28c18d20e23e34e8316b4a9fe523123
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855130"
---
# <a name="messagelogging"></a><span data-ttu-id="926bc-101">\<messageLogging></span><span class="sxs-lookup"><span data-stu-id="926bc-101">\<messageLogging></span></span>
<span data-ttu-id="926bc-102">Questo elemento definisce le impostazioni per le funzionalità di registrazione dei messaggi di Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="926bc-102">This element defines the settings for the message-logging capabilities of Windows Communication Foundation (WCF).</span></span>  
  
<span data-ttu-id="926bc-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="926bc-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="926bc-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="926bc-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="926bc-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> di diagnostica**](diagnostics.md)</span><span class="sxs-lookup"><span data-stu-id="926bc-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<diagnostics>**](diagnostics.md)</span></span>\
<span data-ttu-id="926bc-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> messageLogging**</span><span class="sxs-lookup"><span data-stu-id="926bc-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<messageLogging>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="926bc-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="926bc-107">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <diagnostics>
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="926bc-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="926bc-108">Attributes and Elements</span></span>  
 <span data-ttu-id="926bc-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="926bc-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="926bc-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="926bc-110">Attributes</span></span>  
  
|<span data-ttu-id="926bc-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="926bc-111">Attribute</span></span>|<span data-ttu-id="926bc-112">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="926bc-112">Description</span></span>|  
|---------------|-----------------|  
|`logEntireMessage`|<span data-ttu-id="926bc-113">Valore che specifica se l'intero messaggio (intestazione e corpo del messaggio) viene registrato.</span><span class="sxs-lookup"><span data-stu-id="926bc-113">A Boolean value that specifies whether the entire message (message header and body) is logged.</span></span> <span data-ttu-id="926bc-114">Il valore predefinito è `false` ovvero solo l'intestazione del messaggio viene registrata.</span><span class="sxs-lookup"><span data-stu-id="926bc-114">The default is `false`, which means that only the message header is logged.</span></span> <span data-ttu-id="926bc-115">Questa impostazione influisce su tutti i livelli di registrazione dei messaggi (servizio, trasporto e formato non valido).</span><span class="sxs-lookup"><span data-stu-id="926bc-115">This setting affects all message logging levels (service, transport, and malformed).</span></span>|  
|`logMalformedMessages`|<span data-ttu-id="926bc-116">Valore che specifica se i messaggi in formato non valido vengono registrati.</span><span class="sxs-lookup"><span data-stu-id="926bc-116">A Boolean value that specifies whether malformed messages are logged.</span></span> <span data-ttu-id="926bc-117">I messaggi in formato non valido non vengono conteggiati per `maxMessagesToLog`.</span><span class="sxs-lookup"><span data-stu-id="926bc-117">Malformed messages do not count toward the `maxMessagesToLog`.</span></span> <span data-ttu-id="926bc-118">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="926bc-118">The default is `false`.</span></span>|  
|`logMessagesAtServiceLevel`|<span data-ttu-id="926bc-119">Valore che specifica se i messaggi vengono tracciati al livello del servizio (prima delle trasformazioni relative a crittografia e trasporto).</span><span class="sxs-lookup"><span data-stu-id="926bc-119">A Boolean value that specifies whether messages are traced at the service level (before encryption- and transport-related transforms).</span></span> <span data-ttu-id="926bc-120">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="926bc-120">The default is `false`.</span></span>|  
|`logMessagesAtTransportLevel`|<span data-ttu-id="926bc-121">Valore che specifica se i messaggi vengono tracciati al livello del trasporto.</span><span class="sxs-lookup"><span data-stu-id="926bc-121">A Boolean value that specifies whether messages are traced at the transport level.</span></span> <span data-ttu-id="926bc-122">Tutti i filtri specificati nel file config vengono applicati e solo i messaggi che corrispondono ai filtri vengono tracciati.</span><span class="sxs-lookup"><span data-stu-id="926bc-122">Any filters specified in the config file are applied, and only messages that match the filters are traced.</span></span> <span data-ttu-id="926bc-123">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="926bc-123">The default is `false`.</span></span>|  
|`maxMessagesToLog`|<span data-ttu-id="926bc-124">Valore che specifica il numero massimo di messaggi da registrare.</span><span class="sxs-lookup"><span data-stu-id="926bc-124">A positive integer that specifies the maximum number of messages to log.</span></span> <span data-ttu-id="926bc-125">Il valore predefinito è 1000.</span><span class="sxs-lookup"><span data-stu-id="926bc-125">The default is 1000.</span></span>|  
|`maxSizeOfMessageToLog`|<span data-ttu-id="926bc-126">Valore che specifica la dimensione massima, in byte, di un messaggio da registrare.</span><span class="sxs-lookup"><span data-stu-id="926bc-126">A positive integer that specifies the maximum size, in bytes, of a message to log.</span></span> <span data-ttu-id="926bc-127">I messaggi di dimensioni maggiori del limite non vengono registrati.</span><span class="sxs-lookup"><span data-stu-id="926bc-127">Messages larger than the limit will not be logged.</span></span> <span data-ttu-id="926bc-128">Questa impostazione influisce su tutti i livelli di traccia.</span><span class="sxs-lookup"><span data-stu-id="926bc-128">This setting affects all trace levels.</span></span> <span data-ttu-id="926bc-129">L'impostazione predefinita è 262144(0x4000).</span><span class="sxs-lookup"><span data-stu-id="926bc-129">The default is 262144(0x4000).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="926bc-130">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="926bc-130">Child Elements</span></span>  
  
|<span data-ttu-id="926bc-131">Elemento</span><span class="sxs-lookup"><span data-stu-id="926bc-131">Element</span></span>|<span data-ttu-id="926bc-132">Descrizione</span><span class="sxs-lookup"><span data-stu-id="926bc-132">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="926bc-133">filters</span><span class="sxs-lookup"><span data-stu-id="926bc-133">filters</span></span>|<span data-ttu-id="926bc-134">L'elemento `filters` contiene una raccolta dei filtri di XPath.</span><span class="sxs-lookup"><span data-stu-id="926bc-134">The `filters` element holds a collection of XPath filters.</span></span> <span data-ttu-id="926bc-135">Se la registrazione dei messaggi di trasporto è attivata (`logMessagesAtTransportLevel` è `true`), verranno registrati solo i messaggi corrispondenti ai filtri.</span><span class="sxs-lookup"><span data-stu-id="926bc-135">When transport message logging is enabled (`logMessagesAtTransportLevel` is `true`), only messages matching the filters will be logged.</span></span><br /><br /> <span data-ttu-id="926bc-136">I filtri vengono applicati solo a livello di trasporto.</span><span class="sxs-lookup"><span data-stu-id="926bc-136">Filters are applied only at the transport layer.</span></span> <span data-ttu-id="926bc-137">I filtri non influiscono sulla registrazione dei messaggi a livello di servizio e in formato non valido.</span><span class="sxs-lookup"><span data-stu-id="926bc-137">Service level and malformed message logging are not affected by filters.</span></span><br /><br /> <span data-ttu-id="926bc-138">L'unico attributo di questo elemento, `filter`, è un XpathFilter.</span><span class="sxs-lookup"><span data-stu-id="926bc-138">The only attribute for this element, `filter`, is an XpathFilter.</span></span><br /><br /> `<filters>     <add xmlns:soap="http://www.w3.org/2003/05/soap-envelope">/soap:Envelope</add> </filters>`|  
  
### <a name="parent-elements"></a><span data-ttu-id="926bc-139">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="926bc-139">Parent Elements</span></span>  
  
|<span data-ttu-id="926bc-140">Elemento</span><span class="sxs-lookup"><span data-stu-id="926bc-140">Element</span></span>|<span data-ttu-id="926bc-141">Descrizione</span><span class="sxs-lookup"><span data-stu-id="926bc-141">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="926bc-142">diagnostica</span><span class="sxs-lookup"><span data-stu-id="926bc-142">diagnostics</span></span>|<span data-ttu-id="926bc-143">Definisce le impostazioni WCF per l'ispezione e il controllo in fase di esecuzione da parte dell'amministratore.</span><span class="sxs-lookup"><span data-stu-id="926bc-143">Defines WCF settings for runtime inspection and control for the administrator.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="926bc-144">Note</span><span class="sxs-lookup"><span data-stu-id="926bc-144">Remarks</span></span>  
 <span data-ttu-id="926bc-145">I messaggi vengono registrati a tre livelli diversi nello stack: servizio, trasportare e formato non valido.</span><span class="sxs-lookup"><span data-stu-id="926bc-145">Messages are logged at three different levels in the stack: service, transport, and malformed.</span></span> <span data-ttu-id="926bc-146">Ciascun livello può essere attivato separatamente.</span><span class="sxs-lookup"><span data-stu-id="926bc-146">Each level can be activated separately.</span></span>  
  
 <span data-ttu-id="926bc-147">È possibile aggiungere filtri XPath per registrare messaggi specifici a livello di trasporto e di servizio.</span><span class="sxs-lookup"><span data-stu-id="926bc-147">XPath filters can be added to log specific messages at the transport and service levels.</span></span> <span data-ttu-id="926bc-148">Se non viene definito nessun filtro, tutti i messaggi vengono registrati.</span><span class="sxs-lookup"><span data-stu-id="926bc-148">If no filters are defined, all messages are logged.</span></span> <span data-ttu-id="926bc-149">I filtri vengono applicati solo alle intestazioni del messaggio.</span><span class="sxs-lookup"><span data-stu-id="926bc-149">Filters are applied only to the headers of the message.</span></span> <span data-ttu-id="926bc-150">Il corpo viene ignorato.</span><span class="sxs-lookup"><span data-stu-id="926bc-150">The body is ignored.</span></span> <span data-ttu-id="926bc-151">WCF ignora il corpo del messaggio per migliorare le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="926bc-151">WCF ignores the message body to improve performance.</span></span> <span data-ttu-id="926bc-152">Se si desidera applicare un filtro in base al contenuto del corpo del messaggio, è possibile creare un listener personalizzato con un filtro appropriato.</span><span class="sxs-lookup"><span data-stu-id="926bc-152">If you want to filter based on the content of the body, you can create a custom listener with a filter that does so.</span></span>  
  
 <span data-ttu-id="926bc-153">Per attivare la traccia dei messaggi è necessario creare un listener di traccia.</span><span class="sxs-lookup"><span data-stu-id="926bc-153">You need to create a trace listener to activate message tracing.</span></span> <span data-ttu-id="926bc-154">Il listener stesso può essere un qualsiasi listener che funziona con l'architettura di traccia di <xref:System.Diagnostics>.</span><span class="sxs-lookup"><span data-stu-id="926bc-154">The listener itself can be any listener that works with the <xref:System.Diagnostics> tracing architecture.</span></span> <span data-ttu-id="926bc-155">Nell'esempio seguente viene illustrato come creare un listener di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="926bc-155">The following example demonstrates how to create such a listener.</span></span>  
  
```xml  
<system.diagnostics>
  <sources>
    <source name="System.ServiceModel"
            switchValue="Verbose">
      <listeners>
        <clear />
        <add type="System.Diagnostics.DefaultTraceListener"
             name="Default"
             traceOutputOptions="None" />
        <add name="ServiceModel Listener"
             traceOutputOptions="None" />
      </listeners>
    </source>
    <source name="System.ServiceModel.MessageLogging">
      <listeners>
        <clear />
        <add type="System.Diagnostics.DefaultTraceListener"
             name="Default"
             traceOutputOptions="None" />
        <add name="MessageLogging Listener"
             traceOutputOptions="None" />
      </listeners>
    </source>
  </sources>
  <sharedListeners>
    <add initializeData="C:\ItProTools\TraceLog.xml"
         type="System.Diagnostics.XmlWriterTraceListener, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"
         name="ServiceModel Listener"
         traceOutputOptions="LogicalOperationStack, DateTime, Timestamp, ProcessId, ThreadId, Callstack" />
    <add initializeData="C:\ItProTools\MessageLog.log"
         type="System.Diagnostics.XmlWriterTraceListener, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"
         name="MessageLogging Listener"
         traceOutputOptions="LogicalOperationStack, DateTime, Timestamp, ProcessId, ThreadId, Callstack" />
  </sharedListeners>
</system.diagnostics>
```  
  
## <a name="example"></a><span data-ttu-id="926bc-156">Esempio</span><span class="sxs-lookup"><span data-stu-id="926bc-156">Example</span></span>  
  
```xml  
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
```  
  
## <a name="see-also"></a><span data-ttu-id="926bc-157">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="926bc-157">See also</span></span>

- <xref:System.ServiceModel.Configuration.DiagnosticSection>
- <xref:System.ServiceModel.Diagnostics>
- <xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A>
- <xref:System.ServiceModel.Configuration.MessageLoggingElement>
- [<span data-ttu-id="926bc-158">Configurazione della registrazione dei messaggi</span><span class="sxs-lookup"><span data-stu-id="926bc-158">Configuring Message Logging</span></span>](../../../wcf/diagnostics/configuring-message-logging.md)
