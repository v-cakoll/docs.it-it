---
title: Propagazione
ms.date: 03/30/2017
ms.assetid: f8181e75-d693-48d1-b333-a776ad3b382a
ms.openlocfilehash: 732ae5cb1ce311b78728f8d5de0fd9102bf32499
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84578955"
---
# <a name="propagation"></a><span data-ttu-id="95cd3-102">Propagazione</span><span class="sxs-lookup"><span data-stu-id="95cd3-102">Propagation</span></span>
<span data-ttu-id="95cd3-103">In questo argomento viene descritta la propagazione delle attività nel modello di traccia Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="95cd3-103">This topic describes activity propagation in the Windows Communication Foundation (WCF) tracing model.</span></span>  
  
## <a name="using-propagation-to-correlate-activities-across-endpoints"></a><span data-ttu-id="95cd3-104">Utilizzo della propagazione per correlare attività attraverso endpoint</span><span class="sxs-lookup"><span data-stu-id="95cd3-104">Using Propagation to Correlate Activities Across Endpoints</span></span>  
 <span data-ttu-id="95cd3-105">La propagazione fornisce all'utente la correlazione diretta delle tracce di errore per la stessa unità di elaborazione attraverso endpoint dell'applicazione, ad esempio, una richiesta.</span><span class="sxs-lookup"><span data-stu-id="95cd3-105">Propagation provides the user with direct correlation of error traces for the same unit of processing across application endpoints, for example, a request.</span></span> <span data-ttu-id="95cd3-106">Gli errori generati in endpoint diversi per la stessa unità di elaborazione vengono raggruppati nella stessa attività, anche attraverso domini applicazione.</span><span class="sxs-lookup"><span data-stu-id="95cd3-106">Errors emitted at different endpoints for the same unit of processing are grouped in the same activity, even across application domains.</span></span> <span data-ttu-id="95cd3-107">Questa operazione viene eseguita tramite la propagazione dell'ID attività nelle intestazioni del messaggio.</span><span class="sxs-lookup"><span data-stu-id="95cd3-107">This is done through propagation of the activity ID in the message headers.</span></span> <span data-ttu-id="95cd3-108">Se, pertanto, un client va in timeout a causa di un errore interno nel server, entrambi gli errori vengono visualizzati nella stessa attività per la correlazione diretta.</span><span class="sxs-lookup"><span data-stu-id="95cd3-108">Therefore, if a client times out because of an internal error in the server, both errors appear in the same activity for direct correlation.</span></span>  
  
 <span data-ttu-id="95cd3-109">A tale scopo, usare l'impostazione `ActivityTracing` come illustrato nell'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="95cd3-109">To do this, use the `ActivityTracing` setting as demonstrated in the previous example.</span></span> <span data-ttu-id="95cd3-110">Impostare inoltre l'attributo `propagateActivity` per l'origine di traccia `System.ServiceModel` in tutti gli endpoint.</span><span class="sxs-lookup"><span data-stu-id="95cd3-110">In addition, set the `propagateActivity` attribute for the `System.ServiceModel` trace source at all endpoints.</span></span>  
  
```xml  
<source name="System.ServiceModel" switchValue="Verbose,ActivityTracing" propagateActivity="true" >  
```  
  
 <span data-ttu-id="95cd3-111">La propagazione delle attività è una funzionalità configurabile che consente a WCF di aggiungere un'intestazione ai messaggi in uscita, che include l'ID attività in TLS.</span><span class="sxs-lookup"><span data-stu-id="95cd3-111">Activity propagation is a configurable capability that causes WCF to add a header to outbound messages, which includes the activity ID on the TLS.</span></span> <span data-ttu-id="95cd3-112">Includendo questa intestazione nelle tracce successive lato server, è possibile correlare le attività di client e server.</span><span class="sxs-lookup"><span data-stu-id="95cd3-112">By including this on subsequent traces on the server side, we can correlate client and server activities.</span></span>  
  
## <a name="propagation-definition"></a><span data-ttu-id="95cd3-113">Definizione di propagazione</span><span class="sxs-lookup"><span data-stu-id="95cd3-113">Propagation Definition</span></span>  
 <span data-ttu-id="95cd3-114">Il gAId dell'attività M viene propagato all'attività N se si applicano tutte le condizioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="95cd3-114">Activity M’s gAId is propagated to activity N if all of the following conditions apply.</span></span>  
  
- <span data-ttu-id="95cd3-115">N viene creato a causa di M</span><span class="sxs-lookup"><span data-stu-id="95cd3-115">N is created because of M</span></span>  
  
- <span data-ttu-id="95cd3-116">Il gAId di M è conosciuto a N</span><span class="sxs-lookup"><span data-stu-id="95cd3-116">M’s gAId is known to N</span></span>  
  
- <span data-ttu-id="95cd3-117">Il gAId di N è uguale al gAId di M.</span><span class="sxs-lookup"><span data-stu-id="95cd3-117">N's gAId is equal to M’s gAId.</span></span>  
  
 <span data-ttu-id="95cd3-118">Il gAId viene propagato tramite l'intestazione del messaggio ActivityId, come illustrato nell'XML Schema seguente.</span><span class="sxs-lookup"><span data-stu-id="95cd3-118">The gAId is propagated through the ActivityId message header, as illustrated in the following XML schema.</span></span>  
  
```xml  
<xsd:element name="ActivityId" type="integer" minOccurs="0">  
  <xsd:attribute name="CorrelationId" type="integer" minOccurs="0"/>  
</xsd:element>  
```  
  
 <span data-ttu-id="95cd3-119">Di seguito è riportato un esempio di intestazione del messaggio.</span><span class="sxs-lookup"><span data-stu-id="95cd3-119">The following is an example of the message header.</span></span>  
  
```xml  
<MessageLogTraceRecord>  
  <s:Envelope xmlns:s="http://www.w3.org/2003/05/soap-envelope"
                      xmlns:a="http://www.w3.org/2005/08/addressing">  
    <s:Header>  
      <a:Action s:mustUnderstand="1">http://Microsoft.ServiceModel.Samples/ICalculator/Subtract  
      </a:Action>  
      <a:MessageID>urn:uuid:f0091eae-d339-4c7e-9408-ece34602f1ce  
      </a:MessageID>  
      <ActivityId CorrelationId="f94c6af1-7d5d-4295-b693-4670a8a0ce34"
               xmlns="http://schemas.microsoft.com/2004/09/ServiceModel/Diagnostics">  
        17f59a29-b435-4a15-bf7b-642ffc40eac8  
      </ActivityId>  
      <a:ReplyTo>  
          <a:Address>http://www.w3.org/2005/08/addressing/anonymous</a:Address>  
      </a:ReplyTo>  
      <a:To s:mustUnderstand="1">net.tcp://localhost/servicemodelsamples/service</a:To>  
   </s:Header>  
   <s:Body>  
     <Subtract xmlns="http://Microsoft.ServiceModel.Samples">  
       <n1>145</n1>  
       <n2>76.54</n2>  
     </Subtract>  
   </s:Body>  
  </s:Envelope>  
</MessageLogTraceRecord>  
```  
  
## <a name="propagation-and-activity-boundaries"></a><span data-ttu-id="95cd3-120">Limiti della propagazione e dell'attività</span><span class="sxs-lookup"><span data-stu-id="95cd3-120">Propagation and Activity Boundaries</span></span>  
 <span data-ttu-id="95cd3-121">Quando l'ID attività viene propagato attraverso endpoint, il destinatario del messaggio emette tracce Start e Stop con quell'ID attività (propagato).</span><span class="sxs-lookup"><span data-stu-id="95cd3-121">When the activity ID is propagated across endpoints, the message receiver emits a Start and Stop traces with that (propagated) activity ID.</span></span> <span data-ttu-id="95cd3-122">Esiste pertanto una traccia Start e Stop con quel gAId da ogni origine di traccia.</span><span class="sxs-lookup"><span data-stu-id="95cd3-122">Therefore, there is a Start and Stop trace with that gAId from each trace source.</span></span> <span data-ttu-id="95cd3-123">Se gli endpoint sono nello stesso processo e usano lo stesso nome di origine di traccia, vengono creati più Start e Stop con lo stesso lAId (stesso gAId, stessa origine di traccia, stesso processo).</span><span class="sxs-lookup"><span data-stu-id="95cd3-123">If the endpoints are in the same process and use the same trace source name, multiple Start and Stop with the same lAId (same gAId, same trace source, same process) are created.</span></span>  
  
## <a name="synchronization"></a><span data-ttu-id="95cd3-124">Sincronizzazione</span><span class="sxs-lookup"><span data-stu-id="95cd3-124">Synchronization</span></span>  
 <span data-ttu-id="95cd3-125">Per sincronizzare eventi attraverso endpoint che vengono eseguiti in computer diversi, viene aggiunto un CorrelationId all'intestazione ActivityId propagata nei messaggi.</span><span class="sxs-lookup"><span data-stu-id="95cd3-125">To synchronize events across endpoints that run on different machines, a CorrelationId is added to the ActivityId header that is propagated in messages.</span></span> <span data-ttu-id="95cd3-126">Gli strumenti possono usare questo ID per sincronizzare gli eventi attraverso computer con discrepanza dell'orologio.</span><span class="sxs-lookup"><span data-stu-id="95cd3-126">Tools can use this ID to synchronize events across machines with clock discrepancy.</span></span> <span data-ttu-id="95cd3-127">Nello specifico, lo strumento Visualizzatore delle tracce dei servizi usa questo ID per visualizzare i flussi dei messaggi tra endpoint.</span><span class="sxs-lookup"><span data-stu-id="95cd3-127">Specifically, the Service Trace Viewer tool uses this ID for showing message flows between endpoints.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95cd3-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="95cd3-128">See also</span></span>

- [<span data-ttu-id="95cd3-129">Configurazione delle funzionalità di traccia</span><span class="sxs-lookup"><span data-stu-id="95cd3-129">Configuring Tracing</span></span>](configuring-tracing.md)
- [<span data-ttu-id="95cd3-130">Uso del visualizzatore di tracce dei servizi per la visualizzazione di tracce correlate e la risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="95cd3-130">Using Service Trace Viewer for Viewing Correlated Traces and Troubleshooting</span></span>](using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md)
- [<span data-ttu-id="95cd3-131">Scenari di analisi end-to-end</span><span class="sxs-lookup"><span data-stu-id="95cd3-131">End-To-End Tracing Scenarios</span></span>](end-to-end-tracing-scenarios.md)
- [<span data-ttu-id="95cd3-132">Strumento Visualizzatore di tracce dei servizi (SvcTraceViewer.exe)</span><span class="sxs-lookup"><span data-stu-id="95cd3-132">Service Trace Viewer Tool (SvcTraceViewer.exe)</span></span>](../../service-trace-viewer-tool-svctraceviewer-exe.md)
