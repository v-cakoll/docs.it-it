---
title: Configurazione della traccia del flusso di messaggi
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 15571ca2-bee2-47fb-ba10-fcbc09152ad0
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8df32a64c07db8a45dfb41a46e7a65a92fbef434
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="configuring-message-flow-tracing"></a><span data-ttu-id="c3bff-102">Configurazione della traccia del flusso di messaggi</span><span class="sxs-lookup"><span data-stu-id="c3bff-102">Configuring Message Flow Tracing</span></span>
<span data-ttu-id="c3bff-103">Se la traccia delle attività di [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] è abilitata, gli ID di attività end-to-end vengono assegnati alle attività logiche in tutto lo stack [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c3bff-103">When [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] activity tracing is enabled, End-To-End Activity IDs are assigned to logical activities throughout the [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] stack.</span></span> <span data-ttu-id="c3bff-104">In [!INCLUDE[netfx_current_short](../../../../../includes/netfx-current-short-md.md)] è ora disponibile una versione con prestazioni superiori di questa funzionalità utilizzabile con Event Tracing for Windows (ETW) denominata traccia del flusso di messaggi.</span><span class="sxs-lookup"><span data-stu-id="c3bff-104">In [!INCLUDE[netfx_current_short](../../../../../includes/netfx-current-short-md.md)], there is now a higher performance version of this feature that works with Event Tracing for Windows (ETW) called message flow tracing.</span></span> <span data-ttu-id="c3bff-105">Se abilitati, gli ID di attività end-to-end vengono raccolti dai messaggi in ingresso o assegnati a tali messaggi se vuoti e vengono propagati in tutti gli eventi di traccia generati successivamente alla decodifica del messaggio da parte del canale.</span><span class="sxs-lookup"><span data-stu-id="c3bff-105">When enabled, End-To-End activity IDs are taken from (or assigned to if empty) incoming messages and are propagated to all tracing events that are emitted after the message has been decoded by the channel.</span></span> <span data-ttu-id="c3bff-106">I clienti possono utilizzare questa funzionalità per ricostruire flussi di messaggi con i log di traccia dai vari servizi dopo la decodifica.</span><span class="sxs-lookup"><span data-stu-id="c3bff-106">Customers can use this feature to reconstruct message flows with trace logs from different services after decoding.</span></span>  
  
 <span data-ttu-id="c3bff-107">La traccia può essere abilitata in seguito al rilevamento di un problema con l'applicazione, quindi disabilitata una volta che il problema viene risolto.</span><span class="sxs-lookup"><span data-stu-id="c3bff-107">Tracing can be enabled after a problem is detected with the application and then disabled once the problem is resolved.</span></span>  
  
## <a name="enabling-tracing"></a><span data-ttu-id="c3bff-108">Abilitazione della traccia</span><span class="sxs-lookup"><span data-stu-id="c3bff-108">Enabling Tracing</span></span>  
 <span data-ttu-id="c3bff-109">È possibile abilitare la traccia del flusso di messaggi impostando l'elemento di configurazione `messageFlowTracing` di .NET Framework 4 su `true`, come mostrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="c3bff-109">You can enable message flow tracing by setting the .NET Framework 4 `messageFlowTracing` configuration element to `true`, as shown in the following example.</span></span>  
  
```xml  
<system.servicemodel>  
  <diagnostics>  
    <endToEndTracing propagateActivity="true" messageFlowTracing="true" />  
  </diagnostics>  
</system.servicemodel>  
```  
  
> [!NOTE]
>  <span data-ttu-id="c3bff-110">Poiché l'elemento di configurazione `endToEndTracing` si trova in un file Web.config, non può essere configurato dinamicamente in modo analogo a ETW.</span><span class="sxs-lookup"><span data-stu-id="c3bff-110">Because the `endToEndTracing` configuration element resides in a Web.config file, it cannot be dynamically configured in the same way as ETW.</span></span> <span data-ttu-id="c3bff-111">Affinché l'elemento di configurazione `endToEndTracing` venga applicato, è necessario riciclare l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="c3bff-111">For the `endToEndTracing` configuration element to take effect, the application must be recycled.</span></span>  
  
 <span data-ttu-id="c3bff-112">Le attività sono correlate dall'interscambio di un identificatore denominato ID attività.</span><span class="sxs-lookup"><span data-stu-id="c3bff-112">Activities are correlated by the interchange of an identifier called the activity ID.</span></span> <span data-ttu-id="c3bff-113">Questo identificatore è un GUID e viene generato dalla classe System.Diagnostics.CorrelationManager.</span><span class="sxs-lookup"><span data-stu-id="c3bff-113">This identifier is a GUID, and is generated by the System.Diagnostics.CorrelationManager class.</span></span> <span data-ttu-id="c3bff-114">Se si modifica System.Diagnostics.Trace.CorrelationManager.ActivityID, assicurarsi che il valore venga impostato sul valore originale quando il controllo dell'esecuzione viene trasferito di nuovo al codice WCF.</span><span class="sxs-lookup"><span data-stu-id="c3bff-114">If you manipulate System.Diagnostics.Trace.CorrelationManager.ActivityID, ensure that the value is set to original when execution control transfers back to WCF code.</span></span>  <span data-ttu-id="c3bff-115">Inoltre, se si utilizza un modello di programmazione WCF asincrono, assicurarsi che System.Diagnostics.Trace.CorrelationManager.ActivityID venga trasferito tra i thread.</span><span class="sxs-lookup"><span data-stu-id="c3bff-115">Also, if you use an asynchronous WCF programming model ensure that System.Diagnostics.Trace.CorrelationManager.ActivityID is transferred between the threads.</span></span>  
  
## <a name="message-flow-tracing-and-rest-services"></a><span data-ttu-id="c3bff-116">Traccia del flusso di messaggi e servizi REST</span><span class="sxs-lookup"><span data-stu-id="c3bff-116">Message Flow Tracing and REST Services</span></span>  
 <span data-ttu-id="c3bff-117">La traccia del flusso di messaggi consente di tracciare una richiesta end-to-end.</span><span class="sxs-lookup"><span data-stu-id="c3bff-117">Message flow tracing allows you to trace a request end to end.</span></span>  <span data-ttu-id="c3bff-118">Con i servizi basati su SOAP un ID attività viene inviato n un'intestazione di messaggio SOAP.</span><span class="sxs-lookup"><span data-stu-id="c3bff-118">With SOAP-based services an Activity ID is sent in a SOAP message header.</span></span> <span data-ttu-id="c3bff-119">Le richieste REST non contengono questa intestazione, per cui viene invece utilizzata un'intestazione di evento HTTP speciale.</span><span class="sxs-lookup"><span data-stu-id="c3bff-119">REST requests do not contain this header so a special HTTP event header is used instead.</span></span> <span data-ttu-id="c3bff-120">Nel frammento di codice seguente viene illustrato come recuperare il valore dell'ID attività a livello di codice:</span><span class="sxs-lookup"><span data-stu-id="c3bff-120">The following code snippet shows how you can programmatically retrieve the Activity ID value:</span></span>  
  
```csharp
Object output = null;
if (OperationContext.Current.IncomingMessageProperties.TryGetValue(HttpRequestMessageProperty.Name, out output))
{
   HttpRequestMessageProperty httpHeaders = output as HttpRequestMessageProperty;
   // Retrieve the Activity Id from the HTTP header    string e2eId = httpHeaders.Headers["E2EActivity"];
   // ...
}
```

 <span data-ttu-id="c3bff-121">È possibile aggiungere l'intestazione a livello di codice utilizzando codice seguente:</span><span class="sxs-lookup"><span data-stu-id="c3bff-121">You can programmatically add the header using the following code:</span></span>  
  
```csharp  
HttpContent content = new StreamContent(contentStream);  
Guid correlation = Guid.NewGuid();  
content.Headers.Add("E2EActivity", Convert.ToBase64String(correlation.ToByteArray()));  
```
