---
title: Visualizzazione dei log dei messaggi
ms.date: 03/30/2017
ms.assetid: 3012fa13-f650-45fb-aaea-c5cca8c7d372
ms.openlocfilehash: b0f35d4cca037e663c5c298103c4a8228bb16d52
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70797301"
---
# <a name="viewing-message-logs"></a><span data-ttu-id="967eb-102">Visualizzazione dei log dei messaggi</span><span class="sxs-lookup"><span data-stu-id="967eb-102">Viewing Message Logs</span></span>
<span data-ttu-id="967eb-103">In questo argomento viene illustrato come visualizzare i log dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="967eb-103">This topic describes how you can view message logs.</span></span>  
  
## <a name="viewing-message-logs-in-the-service-trace-viewer"></a><span data-ttu-id="967eb-104">Visualizzazione dei log dei messaggi nel visualizzatore di tracce dei servizi</span><span class="sxs-lookup"><span data-stu-id="967eb-104">Viewing Message Logs in the Service Trace Viewer</span></span>  
 <span data-ttu-id="967eb-105">Un messaggio verrà trasformato mentre viene elaborato da WCF.</span><span class="sxs-lookup"><span data-stu-id="967eb-105">A message will be transformed as it is processed by WCF.</span></span> <span data-ttu-id="967eb-106">Di conseguenza, un messaggio registrato riflette solo il suo contenuto nel momento in cui è stato registrato, non il contenuto in transito.</span><span class="sxs-lookup"><span data-stu-id="967eb-106">Therefore, a message being logged reflects only the message's content at the point it was logged, not the content on the wire.</span></span>  
  
 <span data-ttu-id="967eb-107">Poichè l'output della registrazione dei messaggi non ha alcuna relazione con il formato di trasferimento del messaggio, la registrazione genera sempre il messaggio decodificato.</span><span class="sxs-lookup"><span data-stu-id="967eb-107">Since the output of message logging has no relationship to the transfer format of the message, message logging always outputs the decoded message.</span></span> <span data-ttu-id="967eb-108">Se la registrazione del messaggio è stata configurata correttamente, i messaggi registrati devono essere visualizzati in testo normale.</span><span class="sxs-lookup"><span data-stu-id="967eb-108">If you have configured message logging properly, any logged message should be in plain text.</span></span> <span data-ttu-id="967eb-109">Ad esempio, il formato (testo normale) dei messaggi registrati non è influenzato dall'utilizzo di un codificatore di messaggi binario.</span><span class="sxs-lookup"><span data-stu-id="967eb-109">For example, the format (plain text) of the logged messages is not affected by the usage of a binary message encoder.</span></span>  
  
 <span data-ttu-id="967eb-110">L'output di XmlWriterTraceListener è un file che contiene una sequenza di frammenti XML.</span><span class="sxs-lookup"><span data-stu-id="967eb-110">The output of the XmlWriterTraceListener is a file that contains a sequence of XML fragments.</span></span> <span data-ttu-id="967eb-111">È necessario sapere che il file non è un file XML valido.</span><span class="sxs-lookup"><span data-stu-id="967eb-111">You should be aware that the file is not a valid XML file.</span></span> <span data-ttu-id="967eb-112">È consigliabile utilizzare lo [strumento Visualizzatore di tracce dei servizi (SvcTraceViewer. exe)](../service-trace-viewer-tool-svctraceviewer-exe.md) per visualizzare i file di log dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="967eb-112">It is recommended that you use the [Service Trace Viewer Tool (SvcTraceViewer.exe)](../service-trace-viewer-tool-svctraceviewer-exe.md) to view the message log files.</span></span> <span data-ttu-id="967eb-113">Per ulteriori informazioni sull'utilizzo di questo strumento, vedere [utilizzo di Service Trace Viewer per la visualizzazione di tracce correlate e risoluzione dei problemi](./tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md).</span><span class="sxs-lookup"><span data-stu-id="967eb-113">For more information on how to use this tool, see [Using Service Trace Viewer for Viewing Correlated Traces and Troubleshooting](./tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md).</span></span>  
  
 <span data-ttu-id="967eb-114">Nel Visualizzatore di tracce dei servizi, i messaggi sono elencati nella scheda **messaggio** . I messaggi che hanno causato, o che sono correlati a un errore dell'elaborazione sono evidenziati in giallo (livello di avviso) o rosso (livello dell'errore), a seconda della gravità dell'errore.</span><span class="sxs-lookup"><span data-stu-id="967eb-114">In the Service Trace Viewer, messages are listed in the **Message** tab. Messages that have caused, or are related to, a processing error are highlighted in yellow (warning level) or red (error level), depending on the severity of the error.</span></span> <span data-ttu-id="967eb-115">Un doppio clic sul messaggio ne rivela la traccia nel contesto della richiesta di elaborazione.</span><span class="sxs-lookup"><span data-stu-id="967eb-115">Double-clicking on the message brings up the message trace in the context of the processing request.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="967eb-116">Se un messaggio non ha intestazione, non viene registrato alcun tag `<header/>`.</span><span class="sxs-lookup"><span data-stu-id="967eb-116">If a message has no header, no `<header/>` tag is logged.</span></span>  
  
## <a name="viewing-messages-logged-by-a-client-a-relay-and-a-service"></a><span data-ttu-id="967eb-117">Visualizzazione dei messaggi registrati da client, relay e servizio</span><span class="sxs-lookup"><span data-stu-id="967eb-117">Viewing Messages Logged by a Client, a Relay, and a Service</span></span>  
 <span data-ttu-id="967eb-118">L'ambiente può contenere un client che invia un messaggio a un relay che successivamente lo inoltra al servizio.</span><span class="sxs-lookup"><span data-stu-id="967eb-118">Your environment may contain a client, which sends a message to a relay, that subsequently forwards the message to the service.</span></span> <span data-ttu-id="967eb-119">Quando la registrazione dei messaggi è abilitata in tutte e tre le posizioni e tutti e tre i log dei messaggi vengono visualizzati nello [strumento Visualizzatore di tracce dei servizi (SvcTraceViewer. exe)](../service-trace-viewer-tool-svctraceviewer-exe.md) contemporaneamente, il rendering degli scambi di log dei messaggi verrà eseguito in modo errato.</span><span class="sxs-lookup"><span data-stu-id="967eb-119">When message logging is enabled on all three locations, and all three message logs are viewed in [Service Trace Viewer Tool (SvcTraceViewer.exe)](../service-trace-viewer-tool-svctraceviewer-exe.md) simultaneously, the message log exchanges will be incorrectly rendered.</span></span> <span data-ttu-id="967eb-120">Questa situazione si verifica perché `CorrelationId` e `ActivityId` nell'intestazione del messaggio non sono univoci per ogni coppia invio-ricezione.</span><span class="sxs-lookup"><span data-stu-id="967eb-120">This is because the `CorrelationId` and `ActivityId` in the Message header are not unique for every send-receive pair.</span></span>  
  
 <span data-ttu-id="967eb-121">Per risolvere il problema, utilizzare uno dei metodi seguenti:</span><span class="sxs-lookup"><span data-stu-id="967eb-121">You can use either one of the following methods to resolve this problem.</span></span>  
  
- <span data-ttu-id="967eb-122">Visualizzare solo due dei tre registri messaggi nello [strumento Visualizzatore di tracce dei servizi (SvcTraceViewer. exe)](../service-trace-viewer-tool-svctraceviewer-exe.md) in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="967eb-122">Only view two of the three message logs in the [Service Trace Viewer Tool (SvcTraceViewer.exe)](../service-trace-viewer-tool-svctraceviewer-exe.md) at any time.</span></span>  
  
- <span data-ttu-id="967eb-123">Se è necessario visualizzare contemporaneamente tutti e tre i log nello [strumento Visualizzatore di tracce dei servizi (SvcTraceViewer. exe)](../service-trace-viewer-tool-svctraceviewer-exe.md) , è possibile modificare il servizio di inoltro creando una nuova <xref:System.ServiceModel.Channels.Message> istanza.</span><span class="sxs-lookup"><span data-stu-id="967eb-123">If you must view all three logs in the [Service Trace Viewer Tool (SvcTraceViewer.exe)](../service-trace-viewer-tool-svctraceviewer-exe.md) at the same time, you can modify the relay service by creating a new <xref:System.ServiceModel.Channels.Message> instance.</span></span> <span data-ttu-id="967eb-124">Tale istanza deve essere una copia del corpo del messaggio in arrivo, più tutte le intestazioni tranne quelle per le intestazioni `ActivityId` e `Action`.</span><span class="sxs-lookup"><span data-stu-id="967eb-124">This instance should be a copy of the body of the incoming message, plus all the headers except for the `ActivityId` and `Action` headers.</span></span> <span data-ttu-id="967eb-125">Nell'esempio di codice seguente viene illustrato come procedere.</span><span class="sxs-lookup"><span data-stu-id="967eb-125">The following example code demonstrates how to do this.</span></span>  
  
```csharp
Message outgoingMessage = Message.CreateMessage(incomingMessage.Version, incomingMessage.Headers.Action, incomingMessage.GetReaderAtBodyContents());  
  
for (int i = 0; i < incomingMessage.Headers.Count; i++)  
{  
   if (incomingMessage.Headers[i].Name.Equals("ActivityId", StringComparison.InvariantCultureIgnoreCase) ||  
incomingMessage.Headers[i].Name.Equals("Action", StringComparison.InvariantCultureIgnoreCase))  
   {  
      continue;  
    }  
    outgoingMessage.Headers.CopyHeaderFrom(incomingMessage, i);  
}  
```  
  
## <a name="exceptional-cases-for-inaccurate-message-logging-content"></a><span data-ttu-id="967eb-126">Situazioni particolari di contenuto della registrazione del messaggio inaccurata</span><span class="sxs-lookup"><span data-stu-id="967eb-126">Exceptional Cases for Inaccurate Message Logging Content</span></span>  
 <span data-ttu-id="967eb-127">Nelle condizioni seguenti, i messaggi registrati potrebbero non rappresentare in modo esatto il flusso di ottetti in transito.</span><span class="sxs-lookup"><span data-stu-id="967eb-127">Under the following conditions, messages being logged might not be the exact representation of the octet stream present on the wire.</span></span>  
  
- <span data-ttu-id="967eb-128">Per BasicHttpBinding, le intestazioni di envelope vengono registrate per i messaggi in arrivo nello spazio dei nomi /addressing/none.</span><span class="sxs-lookup"><span data-stu-id="967eb-128">For BasicHttpBinding, envelope headers are logged for the incoming messages in the /addressing/none namespace.</span></span>  
  
- <span data-ttu-id="967eb-129">Gli spazi vuoti possono essere non corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="967eb-129">White spaces can be mismatched.</span></span>  
  
- <span data-ttu-id="967eb-130">Per i messaggi in arrivo, gli elementi vuoti possono essere rappresentati in modo diverso.</span><span class="sxs-lookup"><span data-stu-id="967eb-130">For incoming messages, empty elements can be represented differently.</span></span> <span data-ttu-id="967eb-131">Ad esempio, \<Tag >\</Tag > anziché \<Tag/></span><span class="sxs-lookup"><span data-stu-id="967eb-131">For example, \<tag>\</tag> instead of  \<tag/></span></span>  
  
- <span data-ttu-id="967eb-132">Quando la registrazione di PII note è disattivata per impostazione predefinita o esplicita, enableLoggingKnownPii="true".</span><span class="sxs-lookup"><span data-stu-id="967eb-132">When known PII logging is disabled either by default or explicit setting enableLoggingKnownPii="true".</span></span>  
  
- <span data-ttu-id="967eb-133">È attivata la codifica per la trasformazione a UTF-8.</span><span class="sxs-lookup"><span data-stu-id="967eb-133">Encoding is enabled for transforming to UTF-8.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="967eb-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="967eb-134">See also</span></span>

- [<span data-ttu-id="967eb-135">Strumento Visualizzatore di tracce dei servizi (SvcTraceViewer.exe)</span><span class="sxs-lookup"><span data-stu-id="967eb-135">Service Trace Viewer Tool (SvcTraceViewer.exe)</span></span>](../service-trace-viewer-tool-svctraceviewer-exe.md)
- [<span data-ttu-id="967eb-136">Uso del visualizzatore di tracce dei servizi per la visualizzazione di tracce correlate e la risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="967eb-136">Using Service Trace Viewer for Viewing Correlated Traces and Troubleshooting</span></span>](./tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md)
- [<span data-ttu-id="967eb-137">Registrazione messaggi</span><span class="sxs-lookup"><span data-stu-id="967eb-137">Message Logging</span></span>](message-logging.md)
