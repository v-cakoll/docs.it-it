---
title: Protocolli di messaggistica
ms.date: 03/30/2017
ms.assetid: 5b20bca7-87b3-4c8f-811b-f215b5987104
ms.openlocfilehash: d35cd496db32e1a2886f7ca06e7a3d0964f9c9b5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184590"
---
# <a name="messaging-protocols"></a><span data-ttu-id="f3c7a-102">Protocolli di messaggistica</span><span class="sxs-lookup"><span data-stu-id="f3c7a-102">Messaging Protocols</span></span>

<span data-ttu-id="f3c7a-103">Lo stack di canali di Windows Communication Foundation (WCF) utilizza i canali di codifica e trasporto per trasformare la rappresentazione interna del messaggio nel relativo formato di trasmissione e inviarlo utilizzando un trasporto specifico.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-103">The Windows Communication Foundation (WCF) channel stack employs encoding and transport channels to transform internal message representation into its wire format and send it by using a particular transport.</span></span> <span data-ttu-id="f3c7a-104">Il trasporto più comunemente utilizzato per garantire l'interoperabilità dei servizi Web è il protocollo HTTP, mentre le codifiche utilizzate dai servizi Web sono in genere SOAP 1.1 basato su XML, SOAP 1.2 e il protocollo MTOM (Message Transmission Optimization Mechanism, meccanismo di ottimizzazione della trasmissione dei messaggi).</span><span class="sxs-lookup"><span data-stu-id="f3c7a-104">The most common transport used for Web services interoperability is HTTP, and the most common encodings used by Web services are XML-based SOAP 1.1, SOAP 1.2, and Message Transmission Optimization Mechanism (MTOM).</span></span>

<span data-ttu-id="f3c7a-105">In questo argomento vengono illustrati i <xref:System.ServiceModel.Channels.HttpTransportBindingElement>dettagli di implementazione di WCF per i protocolli seguenti utilizzati da .</span><span class="sxs-lookup"><span data-stu-id="f3c7a-105">This topic covers WCF implementation details for the following protocols employed by <xref:System.ServiceModel.Channels.HttpTransportBindingElement>.</span></span>

<span data-ttu-id="f3c7a-106">Specifiche/documento:</span><span class="sxs-lookup"><span data-stu-id="f3c7a-106">Specification/document:</span></span>

- [<span data-ttu-id="f3c7a-107">HTTP 1.1</span><span class="sxs-lookup"><span data-stu-id="f3c7a-107">HTTP 1.1</span></span>](https://www.ietf.org/rfc/rfc2616.txt)
- <span data-ttu-id="f3c7a-108">[Associazione HTTP SOAP 1.1](https://www.w3.org/TR/2000/NOTE-SOAP-20000508), Sezione 7</span><span class="sxs-lookup"><span data-stu-id="f3c7a-108">[SOAP 1.1 HTTP Binding](https://www.w3.org/TR/2000/NOTE-SOAP-20000508), Section 7</span></span>
- <span data-ttu-id="f3c7a-109">[Binding HTTP SOAP 1.2](https://www.w3.org/TR/soap12-part2) Sezione 7</span><span class="sxs-lookup"><span data-stu-id="f3c7a-109">[SOAP 1.2 HTTP Binding](https://www.w3.org/TR/soap12-part2) Section 7</span></span>

<span data-ttu-id="f3c7a-110">In questo argomento vengono illustrati i <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement> <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement> dettagli di implementazione di WCF per i protocolli seguenti che e impiegano.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-110">This topic covers WCF implementation details for the following protocols  that <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement> and <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement> employ.</span></span>

<span data-ttu-id="f3c7a-111">Specifica/Documento:</span><span class="sxs-lookup"><span data-stu-id="f3c7a-111">Specification/Document:</span></span>

- [<span data-ttu-id="f3c7a-112">Xml</span><span class="sxs-lookup"><span data-stu-id="f3c7a-112">XML</span></span>](https://www.w3.org/TR/REC-xml)
- [<span data-ttu-id="f3c7a-113">SOAP 1,1</span><span class="sxs-lookup"><span data-stu-id="f3c7a-113">SOAP 1.1</span></span>](https://www.w3.org/TR/2000/NOTE-SOAP-20000508/)
- [<span data-ttu-id="f3c7a-114">SOAP 1.2 Core</span><span class="sxs-lookup"><span data-stu-id="f3c7a-114">SOAP 1.2 Core</span></span>](https://www.w3.org/TR/soap12-part1/)
- [<span data-ttu-id="f3c7a-115">WS-Addressing 2004/08</span><span class="sxs-lookup"><span data-stu-id="f3c7a-115">WS-Addressing 2004/08</span></span>](https://www.w3.org/Submission/2004/SUBM-ws-addressing-20040810/)
- [<span data-ttu-id="f3c7a-116">W3C Web Services Addressing 1.0 - Core</span><span class="sxs-lookup"><span data-stu-id="f3c7a-116">W3C Web Services Addressing 1.0 - Core</span></span>](https://www.w3.org/TR/2006/REC-ws-addr-core-20060509)
- [<span data-ttu-id="f3c7a-117">W3C Web Services Addressing 1.0 - SOAP Binding</span><span class="sxs-lookup"><span data-stu-id="f3c7a-117">W3C Web Services Addressing 1.0 - SOAP Binding</span></span>](https://www.w3.org/TR/2006/REC-ws-addr-soap-20060509)
- [<span data-ttu-id="f3c7a-118">Indirizzamento dei servizi Web W3C 1.0 - Associazione WSDL</span><span class="sxs-lookup"><span data-stu-id="f3c7a-118">W3C Web Services Addressing 1.0 - WSDL Binding</span></span>](https://www.w3.org/TR/2006/CR-ws-addr-wsdl-20060529/)
- [<span data-ttu-id="f3c7a-119">W3C Web Services Addressing 1.0 - Metadata</span><span class="sxs-lookup"><span data-stu-id="f3c7a-119">W3C Web Services Addressing 1.0 - Metadata</span></span>](https://www.w3.org/TR/ws-addr-metadata/)
- [<span data-ttu-id="f3c7a-120">Associazione WSDL SOAP1.1</span><span class="sxs-lookup"><span data-stu-id="f3c7a-120">WSDL SOAP1.1 Binding</span></span>](https://www.w3.org/TR/wsdl/)
- [<span data-ttu-id="f3c7a-121">WSDL SOAP1.2 Binding</span><span class="sxs-lookup"><span data-stu-id="f3c7a-121">WSDL SOAP1.2 Binding</span></span>](https://www.w3.org/Submission/wsdl11soap12/)

<span data-ttu-id="f3c7a-122">In questo argomento vengono illustrati i <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement> dettagli di implementazione di WCF per i protocolli seguenti che utilizzano.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-122">This topic covers WCF implementation details for the following protocols that <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement> employs.</span></span>

<span data-ttu-id="f3c7a-123">Specifiche/documento:</span><span class="sxs-lookup"><span data-stu-id="f3c7a-123">Specification/document:</span></span>

- [<span data-ttu-id="f3c7a-124">XOP</span><span class="sxs-lookup"><span data-stu-id="f3c7a-124">XOP</span></span>](https://www.w3.org/TR/xop10/)
- [<span data-ttu-id="f3c7a-125">Associazione MTOM SOAP 1.2</span><span class="sxs-lookup"><span data-stu-id="f3c7a-125">MTOM + SOAP 1.2 Binding</span></span>](https://www.w3.org/TR/soap12-mtom/)
- [<span data-ttu-id="f3c7a-126">Associazione MTOM SOAP 1.1</span><span class="sxs-lookup"><span data-stu-id="f3c7a-126">MTOM SOAP 1.1 Binding</span></span>](https://www.w3.org/Submission/soap11mtom10/)
- [<span data-ttu-id="f3c7a-127">Asserzione di WS-Policy relativa a MTOM</span><span class="sxs-lookup"><span data-stu-id="f3c7a-127">MTOM WS-Policy Assertion</span></span>](https://www.w3.org/Submission/2006/SUBM-WS-MTOMPolicy-20061101/)

<span data-ttu-id="f3c7a-128">In questo argomento vengono utilizzati gli spazi dei nomi XML e i prefissi associati seguenti:The following XML namespaces and associated prefixes are used throughout this topic:</span><span class="sxs-lookup"><span data-stu-id="f3c7a-128">The following XML namespaces and associated prefixes are used throughout this topic:</span></span>

| <span data-ttu-id="f3c7a-129">Prefisso</span><span class="sxs-lookup"><span data-stu-id="f3c7a-129">Prefix</span></span> | <span data-ttu-id="f3c7a-130">URI (Uniform Resource Identifier) dello spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="f3c7a-130">Namespace Uniform Resource Identifier (URI)</span></span> |
|------------|---------------------------------------------------|
| <span data-ttu-id="f3c7a-131">s11</span><span class="sxs-lookup"><span data-stu-id="f3c7a-131">s11</span></span> | `http://schemas.xmlsoap.org/soap/envelope` |
| <span data-ttu-id="f3c7a-132">s12</span><span class="sxs-lookup"><span data-stu-id="f3c7a-132">s12</span></span> |`http://www.w3.org/2003/05/soap-envelope` |
| <span data-ttu-id="f3c7a-133">wsa</span><span class="sxs-lookup"><span data-stu-id="f3c7a-133">wsa</span></span> |`http://www.w3.org/2004/08/addressing` |
| <span data-ttu-id="f3c7a-134">wsam</span><span class="sxs-lookup"><span data-stu-id="f3c7a-134">wsam</span></span> |`http://www.w3.org/2007/05/addressing/metadata` |
| <span data-ttu-id="f3c7a-135">wsap</span><span class="sxs-lookup"><span data-stu-id="f3c7a-135">wsap</span></span> |`http://schemas.xmlsoap.org/ws/2004/09/policy/addressing` |
| <span data-ttu-id="f3c7a-136">wsa10</span><span class="sxs-lookup"><span data-stu-id="f3c7a-136">wsa10</span></span> |`http://www.w3.org/2005/08/addressing` |
| <span data-ttu-id="f3c7a-137">wsaw10</span><span class="sxs-lookup"><span data-stu-id="f3c7a-137">wsaw10</span></span> |`http://www.w3.org/2006/05/addressing/wsdl` |
| <span data-ttu-id="f3c7a-138">xop</span><span class="sxs-lookup"><span data-stu-id="f3c7a-138">xop</span></span> |`http://www.w3.org/2004/08/xop/include` |
| <span data-ttu-id="f3c7a-139">xmime</span><span class="sxs-lookup"><span data-stu-id="f3c7a-139">xmime</span></span> |`http://www.w3.org/2004/06/xmlmime`<br /><br /> `http://www.w3.org/2005/05/xmlmime` |
| <span data-ttu-id="f3c7a-140">Dp</span><span class="sxs-lookup"><span data-stu-id="f3c7a-140">dp</span></span> |`http://schemas.microsoft.com/net/2006/06/duplex` |

## <a name="soap-11-and-soap-12"></a><span data-ttu-id="f3c7a-141">SOAP 1.1 e SOAP 1.2</span><span class="sxs-lookup"><span data-stu-id="f3c7a-141">SOAP 1.1 and SOAP 1.2</span></span>

### <a name="envelope-and-processing-model"></a><span data-ttu-id="f3c7a-142">Modello di elaborazione della envelope</span><span class="sxs-lookup"><span data-stu-id="f3c7a-142">Envelope and Processing Model</span></span>
<span data-ttu-id="f3c7a-143">WCF implementa l'elaborazione della busta SOAP 1.1 dopo Basic Profile 1.1 (BP11) e Basic Profile 1.0 (SSBP10).</span><span class="sxs-lookup"><span data-stu-id="f3c7a-143">WCF implements SOAP 1.1 envelope processing following Basic Profile 1.1 (BP11) and Basic Profile 1.0 (SSBP10).</span></span> <span data-ttu-id="f3c7a-144">L'elaborazione della SOAP 1.2 envelope viene implementata attenendosi alla specifica SOAP12-Part1.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-144">SOAP 1.2 Envelope processing is implemented following SOAP12-Part1.</span></span>

<span data-ttu-id="f3c7a-145">In questa sezione vengono illustrate alcune scelte di implementazione eseguite da WCF per quanto riguarda BP11 e SOAP12-Part1.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-145">This section explains certain implementation choices taken by WCF with regard to BP11 and SOAP12-Part1.</span></span>

#### <a name="mandatory-header-processing"></a><span data-ttu-id="f3c7a-146">Elaborazione obbligatoria delle intestazioni</span><span class="sxs-lookup"><span data-stu-id="f3c7a-146">Mandatory Header Processing</span></span>
<span data-ttu-id="f3c7a-147">WCF segue le regole `mustUnderstand` per l'elaborazione delle intestazioni contrassegnate come descritte nelle specifiche SOAP 1.1 e SOAP 1.2, con le variazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-147">WCF follows rules for processing headers marked `mustUnderstand` described in the SOAP 1.1 and SOAP 1.2 specifications, with the following variations.</span></span>

<span data-ttu-id="f3c7a-148">Un messaggio che entra nello stack di canali WCF viene elaborato da singoli canali configurati da elementi di associazione associati, ad esempio Codifica sms, Sicurezza, Messaggistica affidabile e Transazioni.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-148">A message that enters the WCF channel stack is processed by individual channels configured by associated binding elements, for example, Text Message Encoding, Security, Reliable Messaging, and Transactions.</span></span> <span data-ttu-id="f3c7a-149">Ogni canale riconosce le intestazioni dallo spazio dei nomi associato e le contrassegna come riconosciute.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-149">Each channel recognizes headers from the associated namespace and marks them as understood.</span></span> <span data-ttu-id="f3c7a-150">Dopo l'inserimento di un messaggio nel dispatcher, il formattatore dell'operazione legge le intestazioni previste dal contratto di messaggio/operazione corrispondente e le contrassegna come riconosciute.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-150">Once a message enters the dispatcher, the operation formatter reads headers expected by the corresponding message/operation contract and marks them understood.</span></span> <span data-ttu-id="f3c7a-151">Quindi, il dispatcher verifica se esistono intestazioni non riconosciute ma la cui intestazione `mustUnderstand` richiede il riconoscimento e, in tal caso, genera un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-151">Then the dispatcher verifies whether any remaining headers are not understood but marked as `mustUnderstand` and throws an exception.</span></span> <span data-ttu-id="f3c7a-152">I messaggi che contengono intestazioni `mustUnderstand` indirizzate al destinatario non vengono elaborati dal codice dell'applicazione di destinazione.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-152">Messages that contain `mustUnderstand` headers that are targeted at the recipient are not processed by recipient application code.</span></span>

<span data-ttu-id="f3c7a-153">Questo tipo di elaborazione a livelli consente la separazione fra i livelli di infrastruttura e livelli di applicazione del nodo SOAP:</span><span class="sxs-lookup"><span data-stu-id="f3c7a-153">Such layered processing allows for separation between infrastructure layers and application layers of the SOAP node:</span></span>

- <span data-ttu-id="f3c7a-154">B1111: le intestazioni che non sono comprese vengono rilevate dopo l'elaborazione del messaggio dallo stack di canali dell'infrastruttura WCF, ma prima che venga elaborato dall'applicazione</span><span class="sxs-lookup"><span data-stu-id="f3c7a-154">B1111: Headers that are not understood are detected after the message is processed by the WCF infrastructure channel stack, but before it is processed by application</span></span>

     <span data-ttu-id="f3c7a-155">Il valore dell'intestazione `mustUnderstand` differisce tra SOAP 1.1 e SOAP 1.2.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-155">The `mustUnderstand` header value differs between SOAP 1.1 and SOAP 1.2.</span></span> <span data-ttu-id="f3c7a-156">Basic Profile 1.1 richiede che il valore di `mustUnderstand` sia 0 o 1 per i messaggi SOAP 1.1.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-156">Basic Profile 1.1 requires that the `mustUnderstand` value be 0 or 1 for SOAP 1.1 messages.</span></span> <span data-ttu-id="f3c7a-157">La specifica di SOAP 1.2, oltre ai valori 0 e 1, prevede inoltre i valori `false` e `true`. Tuttavia, tale specifica consiglia di applicare una rappresentazione canonica dei valori `xs:boolean`, ovvero `false` e `true`.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-157">SOAP 1.2 allows 0, 1, `false`, and `true` as values, but recommends emitting a canonical representation of `xs:boolean` values (`false`, `true`).</span></span>

- <span data-ttu-id="f3c7a-158">B1112: WCF `mustUnderstand` genera valori 0 e 1 per entrambe le versioni SOAP 1.1 e SOAP 1.2 della busta SOAP.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-158">B1112: WCF emits `mustUnderstand` values 0 and 1 for both SOAP 1.1 and SOAP 1.2 versions of the SOAP envelope.</span></span> <span data-ttu-id="f3c7a-159">WCF accetta l'intero `xs:boolean` spazio `mustUnderstand` del valore di `false`per `true`l'intestazione (0, 1, , )</span><span class="sxs-lookup"><span data-stu-id="f3c7a-159">WCF accepts the entire value space of `xs:boolean` for the `mustUnderstand` header (0, 1, `false`, `true`)</span></span>

#### <a name="soap-faults"></a><span data-ttu-id="f3c7a-160">Errori SOAP</span><span class="sxs-lookup"><span data-stu-id="f3c7a-160">SOAP Faults</span></span>
<span data-ttu-id="f3c7a-161">Di seguito è riportato un elenco di implementazioni di errore SOAP specifiche di WCF.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-161">The following is a list of WCF-specific SOAP fault implementations.</span></span>

- <span data-ttu-id="f3c7a-162">B2121: WCF restituisce i seguenti codici `s11:mustUnderstand` `s11:Client`di `s11:Server`errore SOAP 1.1: , e .</span><span class="sxs-lookup"><span data-stu-id="f3c7a-162">B2121: WCF returns the following SOAP 1.1 Fault Codes: `s11:mustUnderstand`, `s11:Client`, and `s11:Server`.</span></span>

- <span data-ttu-id="f3c7a-163">B2122: WCF restituisce i seguenti codici `s12:MustUnderstand` `s12:Sender`di `s12:Receiver`errore SOAP 1.2: , e .</span><span class="sxs-lookup"><span data-stu-id="f3c7a-163">B2122: WCF returns the following SOAP 1.2 Fault Codes: `s12:MustUnderstand`, `s12:Sender`, and `s12:Receiver`.</span></span>

### <a name="http-binding"></a><span data-ttu-id="f3c7a-164">Associazione HTTP</span><span class="sxs-lookup"><span data-stu-id="f3c7a-164">HTTP Binding</span></span>

#### <a name="soap-11-http-binding"></a><span data-ttu-id="f3c7a-165">Associazione SOAP 1,1 HTTP</span><span class="sxs-lookup"><span data-stu-id="f3c7a-165">SOAP 1.1 HTTP Binding</span></span>
<span data-ttu-id="f3c7a-166">WCF implementa l'associazione HTTP SOAP1.1 seguendo la sezione 3.4 della specifica Basic Profile 1.1 con i chiarimenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="f3c7a-166">WCF implements SOAP1.1 HTTP binding following the Basic Profile 1.1 specification section 3.4 with the following clarifications:</span></span>

- <span data-ttu-id="f3c7a-167">B2211: il servizio WCF non implementa il reindirizzamento delle richieste HTTP POST.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-167">B2211: WCF service does not implement redirection of HTTP POST requests.</span></span>

- <span data-ttu-id="f3c7a-168">B2212: I client WCF supportano i cookie HTTP in conformità con 3.4.8.B2212: WCF clients support HTTP Cookies in accordance with 3.4.8.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-168">B2212: WCF clients support HTTP Cookies in accordance with 3.4.8.</span></span>

#### <a name="soap-12-http-binding"></a><span data-ttu-id="f3c7a-169">Associazione SOAP 1,2 HTTP</span><span class="sxs-lookup"><span data-stu-id="f3c7a-169">SOAP 1.2 HTTP Binding</span></span>
<span data-ttu-id="f3c7a-170">WCF implementa l'associazione HTTP SOAP 1.2 come descritto nella specifica SOAP 1.2-part 2 (SOAP12Part2) con i chiarimenti seguenti.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-170">WCF implements SOAP 1.2 HTTP binding as described in the SOAP 1.2-part 2 (SOAP12Part2) specification with the following clarifications.</span></span>

<span data-ttu-id="f3c7a-171">SOAP 1.2 introduce un nuovo parametro Action facoltativo per il tipo di supporto `application/soap+xml`.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-171">SOAP 1.2 introduced an optional action parameter for the `application/soap+xml` media type.</span></span> <span data-ttu-id="f3c7a-172">Questo parametro è utile per ottimizzare l'invio dei messaggi in quanto elimina l'esigenza di analizzare il corpo del messaggio SOAP quando non si utilizza la specifica WS-Addressing.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-172">This parameter is useful to optimize message dispatch without requiring that the body of the SOAP message be parsed when WS-Addressing is not used.</span></span>

- <span data-ttu-id="f3c7a-173">R2221: il parametro Action `application/soap+xml`, quando presente in una richiesta SOAP 1.2, deve corrispondere all'attributo `soapAction` dell'elemento `wsoap12:operation` contenuto nell'associazione WSDL corrispondente.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-173">R2221: The `application/soap+xml` action parameter, when present on a SOAP 1.2 request, must match the `soapAction` attribute on the `wsoap12:operation` element inside the corresponding WSDL binding.</span></span>

- <span data-ttu-id="f3c7a-174">R2222: il parametro Action `application/soap+xml`, quando presente in un messaggio SOAP 1.2, deve corrispondere all'elemento `wsa:Action` quando si utilizza la specifica WS-Addressing 2004/08 o la specifica WS-Addressing 1.0.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-174">R2222: The `application/soap+xml` action parameter, when present on a SOAP 1.2 message, must match `wsa:Action` when WS-Addressing 2004/08 or WS-Addressing 1.0 are used.</span></span>

<span data-ttu-id="f3c7a-175">Quando la specifica WS-Addressing è disabilitata e in una richiesta in ingresso non è incluso alcun parametro Action, il parametro `Action` del messaggio viene considerato come non specificato.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-175">When WS-Addressing is disabled and an incoming request does not contain an action parameter, message `Action` is considered not specified.</span></span>

## <a name="ws-addressing"></a><span data-ttu-id="f3c7a-176">WS-Addressing</span><span class="sxs-lookup"><span data-stu-id="f3c7a-176">WS-Addressing</span></span>
<span data-ttu-id="f3c7a-177">WCF implementa 3 versioni di WS-Addressing:</span><span class="sxs-lookup"><span data-stu-id="f3c7a-177">WCF implements 3 versions of WS-Addressing:</span></span>

- <span data-ttu-id="f3c7a-178">WS-Addressing 2004/08</span><span class="sxs-lookup"><span data-stu-id="f3c7a-178">WS-Addressing 2004/08</span></span>

- <span data-ttu-id="f3c7a-179">Specifica di base di W3C Web Services Addressing 1.0 (ADDR10-CORE) e associazione SOAP (ADDR10-SOAP)</span><span class="sxs-lookup"><span data-stu-id="f3c7a-179">W3C Web Services Addressing 1.0 Core  (ADDR10-CORE) and SOAP Binding (ADDR10-SOAP)</span></span>

- <span data-ttu-id="f3c7a-180">WS-Addressing 1.0 - Metadata</span><span class="sxs-lookup"><span data-stu-id="f3c7a-180">WS-Addressing 1.0 - Metadata</span></span>

### <a name="endpoint-references"></a><span data-ttu-id="f3c7a-181">Riferimenti a endpoint</span><span class="sxs-lookup"><span data-stu-id="f3c7a-181">Endpoint References</span></span>
<span data-ttu-id="f3c7a-182">Tutte le versioni di WS-Addressing implementate da WCF utilizzano i riferimenti endpoint per descrivere gli endpoint.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-182">All versions of WS-Addressing that WCF implements use endpoint references to describe endpoints.</span></span>

#### <a name="endpoint-references-and-ws-addressing-versions"></a><span data-ttu-id="f3c7a-183">Utilizzo dei riferimenti a endpoint con le versioni di WS-Addressing</span><span class="sxs-lookup"><span data-stu-id="f3c7a-183">Endpoint References and WS-Addressing Versions</span></span>
<span data-ttu-id="f3c7a-184">WCF implementa una serie di protocolli di infrastruttura che `EndpointReference` utilizzano WS-Addressing e in particolare l'elemento e `W3C.WsAddressing.EndpointReferenceType` la classe (ad esempio, WS-ReliableMessaging, WS-SecureConversation e WS-Trust).</span><span class="sxs-lookup"><span data-stu-id="f3c7a-184">WCF implements a number of the infrastructure protocols that use WS-Addressing and in particular the `EndpointReference` element and `W3C.WsAddressing.EndpointReferenceType` class (for example, WS-ReliableMessaging, WS-SecureConversation, and WS-Trust).</span></span> <span data-ttu-id="f3c7a-185">WCF supporta l'utilizzo di entrambe le versioni di WS-Addressing con altri protocolli di infrastruttura.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-185">WCF supports the use of either version of WS-Addressing with other infrastructure protocols.</span></span> <span data-ttu-id="f3c7a-186">Gli endpoint WCF supportano una versione di WS-Addressing per endpoint.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-186">WCF endpoints support one version of WS-Addressing per endpoint.</span></span>

<span data-ttu-id="f3c7a-187">Per R3111, lo `EndpointReference` spazio dei nomi per l'elemento o il tipo utilizzato nei messaggi scambiati con un endpoint WCF deve corrispondere alla versione di WS-Addressing implementata da questo endpoint.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-187">For R3111, the namespace for the `EndpointReference` element or type used in messages exchanged with a WCF endpoint must match the version of WS-Addressing implemented by this endpoint.</span></span>

<span data-ttu-id="f3c7a-188">Ad esempio, se un endpoint WCF implementa `AcksTo` WS-ReliableMessaging, l'intestazione restituita da tale endpoint all'interno `CreateSequenceResponse` utilizza la versione WS-Addressing che l'elemento `EncodingBinding` specifica per questo endpoint.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-188">For example, if a WCF endpoint implements WS-ReliableMessaging, the `AcksTo` header returned by such an endpoint inside `CreateSequenceResponse` uses the WS-Addressing version that the `EncodingBinding` element specifies for this endpoint.</span></span>

#### <a name="endpoint-references-and-metadata"></a><span data-ttu-id="f3c7a-189">Utilizzo dei riferimenti a endpoint con i metadati</span><span class="sxs-lookup"><span data-stu-id="f3c7a-189">Endpoint References and Metadata</span></span>
<span data-ttu-id="f3c7a-190">Diversi scenari richiedono la comunicazione di metadati o di riferimenti a metadati relativi a un dato endpoint.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-190">A number of scenarios require communicating metadata or a reference to metadata for a given endpoint.</span></span>

<span data-ttu-id="f3c7a-191">B3121: WCF utilizza i meccanismi descritti nella specifica WS-MetadataExchange (MEX) Sezione 6 per includere i metadati per i riferimenti agli endpoint per valore o per riferimento.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-191">B3121: WCF employs mechanisms described in the WS-MetadataExchange (MEX) specification Section 6 to include metadata for endpoint references by value or by reference.</span></span>

<span data-ttu-id="f3c7a-192">Si consideri uno scenario in cui un servizio WCF richiede l'autenticazione utilizzando `http://sts.fabrikam123.com`un token SAML (Security Assertions Markup Language) emesso dall'autorità emittente di token in .</span><span class="sxs-lookup"><span data-stu-id="f3c7a-192">Consider a scenario where a WCF service requires authentication using a Security Assertions Markup Language (SAML) token issued by the token issuer at `http://sts.fabrikam123.com`.</span></span> <span data-ttu-id="f3c7a-193">L'endpoint WCF descrive questo `sp:IssuedToken` requisito di `sp:Issuer` autenticazione utilizzando l'asserzione con un'asserzione annidata che punta all'autorità emittente di token.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-193">The WCF endpoint describes this authentication requirement by using `sp:IssuedToken` assertion with a nested `sp:Issuer` assertion pointing to the token issuer.</span></span> <span data-ttu-id="f3c7a-194">Le applicazioni client che accedono all'asserzione `sp:Issuer` devono conoscere la modalità di comunicazione con l'endpoint dell'emittente di token.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-194">Client applications that access the `sp:Issuer` assertion need to know how to communicate with the token issuer endpoint.</span></span> <span data-ttu-id="f3c7a-195">In particolare, il client deve conoscere i metadati relativi all'emittente di token.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-195">The client needs to know metadata about the token issuer.</span></span> <span data-ttu-id="f3c7a-196">Utilizzando le estensioni dei metadati di riferimento dell'endpoint definite in MEX, WCF fornisce un riferimento ai metadati dell'autorità emittente di token.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-196">Using the endpoint reference metadata extensions defined in MEX, WCF provides a reference to the token issuer metadata.</span></span>

```xml
<sp:IssuedToken>
  <sp:Issuer>
    <wsa10:Address>
      http://sts.fabrikam123.com
    </wsa10:Address>
    <wsa10:Metadata>
      <mex:Metadata>
        <mex:MetadataSection>
          <mex:MetadataReference>
            <wsa10:Address>
              http://sts.fabrikam123.com/mex
            </wsa10:Address>
          </mex:MetadataReference>
        </mex:MetadataSection>
      </mex:Metadata>
    </wsa10:Metadata>
  </sp:Issuer>
</sp:IssuedToken>
```

### <a name="message-addressing-headers"></a><span data-ttu-id="f3c7a-197">Intestazioni di indirizzamento dei messaggi</span><span class="sxs-lookup"><span data-stu-id="f3c7a-197">Message Addressing Headers</span></span>

#### <a name="message-headers"></a><span data-ttu-id="f3c7a-198">Intestazioni del messaggio</span><span class="sxs-lookup"><span data-stu-id="f3c7a-198">Message Headers</span></span>
<span data-ttu-id="f3c7a-199">Per entrambe le versioni di WS-Addressing, WCF utilizza `wsa:To` `wsa:ReplyTo`le `wsa:Action` `wsa:MessageID`intestazioni dei messaggi seguenti come prescritto dalle specifiche , , , e `wsa:RelatesTo`.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-199">For both WS-Addressing versions, WCF uses the following message headers as prescribed by the specifications `wsa:To`, `wsa:ReplyTo`, `wsa:Action`, `wsa:MessageID`,and `wsa:RelatesTo`.</span></span>

<span data-ttu-id="f3c7a-200">B3211: per tutte le versioni di WS-Addressing, WCF rispetta, ma non `wsa:FaultTo` produce, intestazioni dei messaggi WS-Addressing e `wsa:From`.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-200">B3211: For all WS-Addressing versions, WCF honors, but does not produce out of the box, WS-Addressing message headers `wsa:FaultTo` and `wsa:From`.</span></span>

<span data-ttu-id="f3c7a-201">Le applicazioni che interagiscono con le applicazioni WCF possono aggiungere queste intestazioni di messaggio e WCF le elaborerà di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-201">Applications that interact with WCF applications can add these message headers and WCF will process them accordingly.</span></span>

#### <a name="reference-parameters-and-properties"></a><span data-ttu-id="f3c7a-202">Parametri e proprietà dei riferimenti</span><span class="sxs-lookup"><span data-stu-id="f3c7a-202">Reference Parameters and Properties</span></span>

<span data-ttu-id="f3c7a-203">WCF implementa l'elaborazione dei parametri di riferimento dell'endpoint e delle proprietà di riferimento in base alle rispettive specifiche.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-203">WCF implements processing of endpoint reference parameters and reference properties in accordance with respective specifications.</span></span>

<span data-ttu-id="f3c7a-204">B3221: se configurato per l'utilizzo di WS-Addressing 2004/08, gli endpoint WCF non distinguono tra l'elaborazione delle proprietà di riferimento e i parametri di riferimento.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-204">B3221: When configured to use WS-Addressing 2004/08, WCF endpoints do not differentiate between processing Reference Properties and Reference Parameters.</span></span>

### <a name="message-exchange-patterns"></a><span data-ttu-id="f3c7a-205">Modelli di scambio dei messaggi</span><span class="sxs-lookup"><span data-stu-id="f3c7a-205">Message Exchange Patterns</span></span>
<span data-ttu-id="f3c7a-206">La sequenza dei messaggi coinvolti nella chiamata dell'operazione del servizio Web viene definita modello di *scambio*dei messaggi .</span><span class="sxs-lookup"><span data-stu-id="f3c7a-206">The sequence of messages involved in the Web service operation invocation is referred to as the *message exchange pattern*.</span></span> <span data-ttu-id="f3c7a-207">WCF supporta modelli di scambio di messaggi unidirezionali, richiesta-risposta e duplex.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-207">WCF supports one-way, request-reply, and duplex message exchange patterns.</span></span> <span data-ttu-id="f3c7a-208">Questa sezione descrive i requisiti della specifica WS-Addressing che definiscono il modo in cui il modello di scambio dei messaggi usato influisce sull'elaborazione dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-208">This section clarifies WS-Addressing requirements on message processing depending on the message exchange pattern being used.</span></span>

<span data-ttu-id="f3c7a-209">Contenuto della sezione, il richiedente invia il primo messaggio e il risponditore riceve il primo messaggio.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-209">Throughout this section, the requester sends the first message and the responder receives the first message.</span></span>

#### <a name="one-way-message"></a><span data-ttu-id="f3c7a-210">Modello unidirezionale</span><span class="sxs-lookup"><span data-stu-id="f3c7a-210">One-Way Message</span></span>
<span data-ttu-id="f3c7a-211">Quando un endpoint WCF è configurato `Action` per supportare i messaggi con un dato di seguire un modello unidirezionale, l'endpoint WCF segue i comportamenti e i requisiti seguenti.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-211">When a WCF endpoint is configured to support messages with a given `Action` to follow a one-way pattern, the WCF endpoint follows the following behaviors and requirements.</span></span> <span data-ttu-id="f3c7a-212">Se non diversamente specificato, i comportamenti e le regole si applicano a entrambe le versioni di WS-Addressing supportate in WCF:</span><span class="sxs-lookup"><span data-stu-id="f3c7a-212">Unless otherwise specified, behaviors and rules apply for both versions of WS-Addressing supported in WCF:</span></span>

- <span data-ttu-id="f3c7a-213">R3311: il richiedente deve includere gli elementi `wsa:To` e `wsa:Action` nonché le intestazioni di tutti i parametri specificati nel riferimento a endpoint.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-213">R3311: The requester must include `wsa:To`, `wsa:Action`, and headers for all reference parameters specified by the endpoint reference.</span></span> <span data-ttu-id="f3c7a-214">Quando si utilizza la specifica WS-Addressing 2004/08 e il riferimento a endpoint specifica le proprietà di riferimento [reference properties], occorre aggiungere al messaggio anche le intestazioni corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-214">When WS-Addressing 2004/08 is used and [reference properties] are specified by the endpoint reference, the corresponding headers must be added to the message too.</span></span>

- <span data-ttu-id="f3c7a-215">B3312: il richiedente può includere le intestazioni `MessageID` e `ReplyTo` e `FaultTo`.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-215">B3312: The requester may include `MessageID`, `ReplyTo`, and `FaultTo` headers.</span></span> <span data-ttu-id="f3c7a-216">Dopo essere stati ignorati dall'infrastruttura del destinatario, questi elementi vengono passati all'applicazione.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-216">The receiver infrastructure will ignore them, and they will be passed to the application.</span></span>

- <span data-ttu-id="f3c7a-217">R3313: quando si utilizza il protocollo HTTP e non viene inviato alcun messaggio sul canale di risposta HTTP, il risponditore deve inviare una risposta HTTP contenente un corpo vuoto e un codice di stato HTTP 202.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-217">R3313: When HTTP is used and no message is being sent on the HTTP response leg, the responder must send an HTTP response with an empty body and an HTTP 202 status code.</span></span>

     <span data-ttu-id="f3c7a-218">Quando si utilizza il trasporto HTTP e il contratto dell'operazione dichiara un messaggio unidirezionale, la risposta HTTP può comunque essere utilizzata per l'invio di messaggi di infrastruttura. Ad esempio, la funzionalità di messaggistica affidabile può inviare un messaggio `SequenceAcknowledgement` in una risposta HTTP.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-218">When the HTTP transport is in use and the operation contract declares a message one-way, the HTTP response can still be used for sending infrastructure messages—for example, reliable messaging can send a `SequenceAcknowledgement` message on an HTTP response.</span></span>

- <span data-ttu-id="f3c7a-219">B3314: il risponditore WCF non invia un messaggio di errore in risposta a un messaggio unidirezionale.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-219">B3314: The WCF responder does not send a fault message in response to a one-way message.</span></span>

#### <a name="request-reply"></a><span data-ttu-id="f3c7a-220">Request/Reply</span><span class="sxs-lookup"><span data-stu-id="f3c7a-220">Request-Reply</span></span>
<span data-ttu-id="f3c7a-221">Quando un endpoint WCF è configurato `Action` per un messaggio con un dato di follow-the follow del modello di richiesta-risposta, l'endpoint WCF segue i comportamenti e i requisiti riportati di seguito.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-221">When a WCF endpoint is configured for a message with a given `Action` to follow the request-reply pattern, the WCF endpoint follows the behaviors and requirements below.</span></span> <span data-ttu-id="f3c7a-222">Se non diversamente specificato diversamente, i comportamenti e le regole si applicano a entrambe le versioni di WS-Addressing supportate in WCF:</span><span class="sxs-lookup"><span data-stu-id="f3c7a-222">Unless specified otherwise, behaviors and rules apply for both versions of WS-Addressing supported in WCF:</span></span>

- <span data-ttu-id="f3c7a-223">R3321: il richiedente deve `wsa:To`includere `wsa:Action` `wsa:MessageID`nella richiesta , , e le intestazioni per tutti i parametri di riferimento o le proprietà di riferimento (o entrambi) specificati dal riferimento all'endpoint.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-223">R3321: The requester must include in the request `wsa:To`, `wsa:Action`, `wsa:MessageID`, and headers for all reference parameters or reference properties (or both) specified by the endpoint reference.</span></span>

- <span data-ttu-id="f3c7a-224">R3322: quando si utilizza la specifica WS-Addressing 2004/08, nella richiesta deve essere incluso anche l'elemento `ReplyTo`.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-224">R3322: When WS-Addressing 2004/08 is used, `ReplyTo` must also be included in the request.</span></span>

- <span data-ttu-id="f3c7a-225">R3323: quando WS-Addressing 1.0 `ReplyTo` viene utilizzato e non è presente nella richiesta, viene `http://www.w3.org/2005/08/addressing/anonymous` utilizzato un riferimento all'endpoint predefinito con la proprietà [address] uguale a.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-225">R3323: When WS-Addressing 1.0 is used and `ReplyTo` is not present in the request, a default endpoint reference with the [address] property equal to `http://www.w3.org/2005/08/addressing/anonymous` is used.</span></span>

- <span data-ttu-id="f3c7a-226">R3324: il richiedente `wsa:To` `wsa:Action`deve `wsa:RelatesTo` includere le intestazioni , e nel messaggio di risposta, nonché le `ReplyTo` intestazioni per tutti i parametri di riferimento o le proprietà di riferimento (o entrambi) specificati dal riferimento all'endpoint nella richiesta.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-226">R3324: The requester must include `wsa:To`, `wsa:Action`, and `wsa:RelatesTo` headers in the reply message, as well as headers for all reference parameters or reference properties (or both) specified by the `ReplyTo` endpoint reference in the request.</span></span>

### <a name="web-services-addressing-faults"></a><span data-ttu-id="f3c7a-227">Errori di indirizzamento dei servizi Web</span><span class="sxs-lookup"><span data-stu-id="f3c7a-227">Web Services Addressing Faults</span></span>
<span data-ttu-id="f3c7a-228">R3411: WCF produce i seguenti errori definiti da WS-Addressing 2004/08.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-228">R3411: WCF produces the following faults defined by WS-Addressing 2004/08.</span></span>

| <span data-ttu-id="f3c7a-229">Codice</span><span class="sxs-lookup"><span data-stu-id="f3c7a-229">Code</span></span> | <span data-ttu-id="f3c7a-230">Causa</span><span class="sxs-lookup"><span data-stu-id="f3c7a-230">Cause</span></span> |
|----------|-----------|
| `wsa:DestinationUnreachable` | <span data-ttu-id="f3c7a-231">Il messaggio in ingresso presenta un riferimento `ReplyTo` diverso dall'indirizzo per risposte definito per questo canale. Non esiste alcun endpoint in attesa presso l'indirizzo specificato nell'intestazione di destinazione.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-231">The message arrived with a `ReplyTo` that is different from the reply address established for this channel; there is no endpoint listening at the address specified in the To header.</span></span> |
| `wsa:ActionNotSupported` | <span data-ttu-id="f3c7a-232">I canali dell'infrastruttura o il dispatcher associato all'endpoint non riconoscono l'azione specificata nell'intestazione `Action`.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-232">the infrastructure channels or dispatcher associated with the endpoint do not recognize the action specified in the `Action` header.</span></span> |

<span data-ttu-id="f3c7a-233">R3412: WCF produce i seguenti errori definiti da WS-Addressing 1.0.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-233">R3412: WCF produces the following faults defined by WS-Addressing 1.0.</span></span>

| <span data-ttu-id="f3c7a-234">Codice</span><span class="sxs-lookup"><span data-stu-id="f3c7a-234">Code</span></span> | <span data-ttu-id="f3c7a-235">Causa</span><span class="sxs-lookup"><span data-stu-id="f3c7a-235">Cause</span></span> |
|----------|-----------|
| `wsa10:InvalidAddressingHeader` | <span data-ttu-id="f3c7a-236">`wsa:To`Duplicare `wsa:ReplyTo` `wsa:From` , `wsa:MessageID`, o .</span><span class="sxs-lookup"><span data-stu-id="f3c7a-236">Duplicate `wsa:To`, `wsa:ReplyTo`, `wsa:From` or `wsa:MessageID`.</span></span> <span data-ttu-id="f3c7a-237">Duplicare `wsa:RelatesTo` con `RelationshipType`lo stesso file .</span><span class="sxs-lookup"><span data-stu-id="f3c7a-237">Duplicate `wsa:RelatesTo` with the same `RelationshipType`.</span></span> |
| `wsa10:MessageAddressingHeaderRequired` | <span data-ttu-id="f3c7a-238">L'intestazione obbligatoria di indirizzamento è mancante.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-238">The required Addressing header is missing.</span></span> |
| `wsa10:DestinationUnreachable` | <span data-ttu-id="f3c7a-239">Il messaggio in ingresso presenta un riferimento `ReplyTo` diverso dall'indirizzo per risposte definito per questo canale.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-239">The message arrived with a `ReplyTo` that is different from the reply address established for this channel.</span></span> <span data-ttu-id="f3c7a-240">Non esiste alcun endpoint in attesa presso l'indirizzo specificato nell'intestazione di destinazione.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-240">There is no endpoint listening at the address specified in the To header.</span></span> |
| `wsa10:ActionNotSupported` | <span data-ttu-id="f3c7a-241">I canali dell'infrastruttura o il dispatcher associato all'endpoint non riconoscono l'azione specificata nell'intestazione `Action`.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-241">An action specified in the `Action` header is not recognized by the infrastructure channels or dispatcher associated with the endpoint.</span></span> |
| `wsa10:EndpointUnavailable` | <span data-ttu-id="f3c7a-242">Il canale RM restituisce questo errore per indicare che l'endpoint non elaborerà la sequenza basata sull'esame delle intestazioni di indirizzamento del messaggio `CreateSequence`.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-242">The RM channel sends this fault back, indicating the endpoint will not process the sequence based upon examination of the `CreateSequence` message’s addressing headers.</span></span> |

<span data-ttu-id="f3c7a-243">Il codice delle tabelle precedenti viene mappato al codice `FaultCode` in SOAP 1.1 e al codice `SubCode` (in cui il codice corrisponde al mittente) in SOAP 1.2.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-243">Code in the preceding tables maps to `FaultCode` in SOAP 1.1 and `SubCode` (with Code=Sender) in SOAP 1.2.</span></span>

### <a name="wsdl-11-binding-and-ws-policy-assertions"></a><span data-ttu-id="f3c7a-244">Utilizzo di associazioni WSDL 1.1 con le asserzioni di WS-Policy</span><span class="sxs-lookup"><span data-stu-id="f3c7a-244">WSDL 1.1 Binding and WS-Policy Assertions</span></span>

#### <a name="indicating-use-of-ws-addressing"></a><span data-ttu-id="f3c7a-245">Definizione dell'uso di WS-Addressing</span><span class="sxs-lookup"><span data-stu-id="f3c7a-245">Indicating Use of WS-Addressing</span></span>
<span data-ttu-id="f3c7a-246">WCF utilizza asserzioni di criteri per indicare il supporto dell'endpoint per una particolare versione di WS-Addressing.WCF uses policy assertions to indicate endpoint support for a particular WS-Addressing version.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-246">WCF uses policy assertions to indicate endpoint support for a particular WS-Addressing version.</span></span>

<span data-ttu-id="f3c7a-247">L'asserzione di criteri seguente contiene il soggetto dei criteri di endpoint [WS-PA] e indica che i messaggi scambiati con l'endpoint devono utilizzare la specifica WS-Addressing 2004/08.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-247">The following policy assertion has Endpoint Policy Subject [WS-PA] and indicates messages sent and received from the endpoint must use WS-Addressing 2004/08.</span></span>

```xml
<wsap:UsingAddressing />
```

<span data-ttu-id="f3c7a-248">Questa asserzione di criteri si aggiunge alla specifica WS-Addressing 2004/08.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-248">This policy assertion augments the WS-Addressing 2004/08 specification.</span></span>

<span data-ttu-id="f3c7a-249">Tramite l'asserzione di criteri seguente viene indicato che nei messaggi inviati/ricevuti deve essere utilizzato WS-Addressing 1.0.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-249">The following policy assertion this indicates that messages sent/received must use WS-Addressing 1.0.</span></span>

```xml
<wsam:Addressing/>
```

<span data-ttu-id="f3c7a-250">Nell'asserzione di criteri seguente è incluso un soggetto dei criteri di endpoint [WS-PA] e viene indicato che nei messaggi scambiati con l'endpoint deve essere utilizzata la specifica WS-Addressing 2004/08.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-250">The following policy assertion has an Endpoint Policy Subject [WS-PA] and indicates that messages sent and received from the endpoint must use WS-Addressing 2004/08.</span></span>

```xml
<wsaw10:UsingAddressing />
```

<span data-ttu-id="f3c7a-251">L'elemento `wsaw10:UsingAddressing` è preso in prestito da [WS-Addressing-WSDL] e viene utilizzato nel contesto di WS-Policy in conformità alla sezione 3.1.2 di tale specifica.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-251">The `wsaw10:UsingAddressing` element is borrowed from [WS-Addressing-WSDL] and is used in the context of WS-Policy in compliance with that specification, section 3.1.2.</span></span>

<span data-ttu-id="f3c7a-252">L'utilizzo dell'intestazione di indirizzamento non modifica la semantica delle associazioni WSDL 1.1 HTTP, SOAP 1.1 HTTP e SOAP 1.2 HTTP.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-252">Use of Addressing does not alter the semantics of WSDL 1.1, SOAP 1.1, and SOAP 1.2 HTTP Bindings.</span></span> <span data-ttu-id="f3c7a-253">Ad esempio, se si prevede una risposta a una richiesta inviata a un endpoint in cui vengono utilizzati WS-Addressing e l'associazione WSDL SOAP 1.x HTTP, la risposta deve essere inviata tramite la risposta HTTP.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-253">For example, if a reply is expected to a request that is sent to an endpoint that uses Addressing and WSDL SOAP 1.x HTTP binding, the reply must be sent by using the HTTP response.</span></span>

<span data-ttu-id="f3c7a-254">Per le risposte inviate tramite la risposta http, l'asserzione WS-AM è:</span><span class="sxs-lookup"><span data-stu-id="f3c7a-254">For replies sent over the http response, the WS-AM assertion is:</span></span>

```xml
<wsam:AnonymousResponses/>
```

<span data-ttu-id="f3c7a-255">L'asserzione di criteri completa potrebbe essere simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="f3c7a-255">The complete policy assertion might look like this:</span></span>

```xml
<wsam:Addressing>
    <wsp:Policy>
        <wsam:AnonymousResponses />
    </wsp:Policy>
</wsam:Addressing>
```

<span data-ttu-id="f3c7a-256">Tuttavia, sono presenti modelli di scambio dei messaggi che traggono profitto dalla presenza di due connessioni HTTP opposte indipendenti stabilite tra il richiedente e il risponditore, ad esempio i messaggi unidirezionali non richiesti inviati dal risponditore.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-256">However, there are message exchange patterns that benefit from having two independent converse HTTP connections established between the requester and the responder, for example, unsolicited one-way messages sent by the responder.</span></span>

<span data-ttu-id="f3c7a-257">WCF offre una funzionalità tramite la quale due canali di trasporto sottostanti possono formare un canale Duplex composito, in cui un canale viene utilizzato per i messaggi di input e l'altro per i messaggi di output.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-257">WCF offers a feature by which two underlying transport channels can form a Composite Duplex channel, where one channel is used for input messages and the other is used for output messages.</span></span> <span data-ttu-id="f3c7a-258">Nel caso del trasporto HTTP, il modello duplex composito offre due connessioni HTTP opposte.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-258">In the case of the HTTP Transport, Composite Duplex provides two converse HTTP connections.</span></span> <span data-ttu-id="f3c7a-259">Il richiedente utilizza una connessione per inviare i messaggi al risponditore, mentre quest'ultimo utilizza l'altra connessione per inviare i messaggi di risposta al richiedente.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-259">The requester uses one connection to send messages to the responder, and the responder uses the other to send messages back to the requester.</span></span>

<span data-ttu-id="f3c7a-260">Per le risposte inviate tramite richieste http distinte, l'asserzione ws-am è:</span><span class="sxs-lookup"><span data-stu-id="f3c7a-260">For replies sent over separate http requests, the ws-am assertion is</span></span>

```xml
<wsam:NonAnonymousResponses/>
```

<span data-ttu-id="f3c7a-261">L'asserzione di criteri completa potrebbe essere simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="f3c7a-261">The complete policy assertion might look like this:</span></span>

```xml
<wsam:Addressing>
    <wsp:Policy>
        <wsam:NonAnonymousResponses />
    </wsp:Policy>
</wsam:Addressing>
```

<span data-ttu-id="f3c7a-262">Per l'utilizzo dell'asserzione seguente che presenta il soggetto dei criteri di endpoint [WS-PA] negli endpoint in cui vengono utilizzate le associazioni SOAP 1.x HTTP WSDL 1.1 sono richieste due connessioni HTTP opposte e distinte da utilizzare rispettivamente per i messaggi dal richiedente al risponditore e dal risponditore al richiedente.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-262">Use of the following assertion that has Endpoint Policy Subject [WS-PA] on endpoints that use WSDL 1.1 SOAP 1.x HTTP bindings requires two separate converse HTTP connections to be used for messages flowing from requester to responder and responder to requester, respectively.</span></span>

```xml
<cdp:CompositeDuplex/>
```

<span data-ttu-id="f3c7a-263">L'istruzione precedente comporta i requisiti seguenti per l'intestazione `wsa:ReplyTo` dei messaggi di richiesta:</span><span class="sxs-lookup"><span data-stu-id="f3c7a-263">The previous statement leads to the following requirements on the `wsa:ReplyTo` header for request messages:</span></span>

- <span data-ttu-id="f3c7a-264">R3514: i messaggi di richiesta `ReplyTo` inviati a `[address]` un endpoint `http://www.w3.org/2005/08/addressing/anonymous` devono avere un'intestazione con la proprietà diversa da se `wsap10:UsingAddressing` l'endpoint utilizza un'associazione HTTP SOAP 1.x WSDL 1.1 e dispone di un'alternativa di criteri con `wsap:UsingAddressing` un'asserzione o associata. `cdp:CompositeDuplex`</span><span class="sxs-lookup"><span data-stu-id="f3c7a-264">R3514: Request messages sent to an endpoint must have a `ReplyTo` header with the `[address]` property not equal to `http://www.w3.org/2005/08/addressing/anonymous` if the endpoint uses a WSDL 1.1 SOAP 1.x HTTP binding and has a policy alternative with a `wsap10:UsingAddressing` or `wsap:UsingAddressing` assertion coupled with `cdp:CompositeDuplex` attached.</span></span>

- <span data-ttu-id="f3c7a-265">R3515: i messaggi di richiesta `ReplyTo` inviati a `[address]` un `http://www.w3.org/2005/08/addressing/anonymous`endpoint devono avere `ReplyTo` un'intestazione con la proprietà uguale o non avere un'intestazione, se l'endpoint utilizza un'associazione HTTP WSDL 1.1 SOAP 1.x e dispone di un'alternativa di criteri con `wsap10:UsingAddressing` asserzione e asserzione associata. `cdp:CompositeDuplex`</span><span class="sxs-lookup"><span data-stu-id="f3c7a-265">R3515: Request messages sent to an endpoint must have a `ReplyTo` header with the `[address]` property equal to `http://www.w3.org/2005/08/addressing/anonymous`, or not have a `ReplyTo` header at all, if the endpoint uses a WSDL 1.1 SOAP 1.x HTTP binding and has a policy alternative with `wsap10:UsingAddressing` assertion and no `cdp:CompositeDuplex` assertion attached.</span></span>

- <span data-ttu-id="f3c7a-266">R3516: i messaggi di richiesta `ReplyTo` inviati a `[address]` un `http://www.w3.org/2005/08/addressing/anonymous` endpoint devono avere un'intestazione con una proprietà uguale a `wsap:UsingAddressing` se `cdp:CompositeDuplex` l'endpoint utilizza un'associazione HTTP SOAP 1.x WSDL 1.1 e dispone di un'alternativa dei criteri con asserzione e asserzione associata.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-266">R3516: Request messages sent to an endpoint must have a `ReplyTo` header with an `[address]` property equal to `http://www.w3.org/2005/08/addressing/anonymous` if the endpoint uses a WSDL 1.1 SOAP 1.x HTTP binding and has a policy alternative with `wsap:UsingAddressing` assertion and no `cdp:CompositeDuplex` assertion attached.</span></span>

<span data-ttu-id="f3c7a-267">La specifica WS-Addressing WSDL tenta di descrivere associazioni del protocollo simili introducendo un elemento `<wsaw:Anonymous/>` con tre valori testuali (obbligatorio, facoltativo e proibito) per indicare requisiti nell'intestazione `wsa:ReplyTo` (sezione 3.2).</span><span class="sxs-lookup"><span data-stu-id="f3c7a-267">The WS-addressing WSDL specification attempts to describe similar protocol bindings by introducing an element `<wsaw:Anonymous/>` with three textual values (required, optional, and prohibited) to indicate requirements on the `wsa:ReplyTo` header (section 3.2).</span></span> <span data-ttu-id="f3c7a-268">Sfortunatamente, tale definizione dell'elemento non è utilizzabile in modo specifico nel contesto di WS-Policy, perché richiede estensioni specifiche di dominio per supportare l'intersezione di alternative che utilizzano tale elemento come asserzione.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-268">Unfortunately, such element definition is not particularly usable as an assertion in the context of WS-Policy, because it requires domain-specific extensions to support the intersection of alternatives using such an element as an assertion.</span></span> <span data-ttu-id="f3c7a-269">A differenza del comportamento di endpoint in transito, che rende il valore dell'intestazione `ReplyTo` specifico del trasporto HTTP, il suddetto elemento indica questo valore senza associarlo a un determinato protocollo.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-269">Such element definition also indicates the value of the `ReplyTo` header as opposed to the endpoint behavior on the wire, which makes it specific to HTTP transport.</span></span>

#### <a name="action-definition"></a><span data-ttu-id="f3c7a-270">Definizione dell'attributo Action</span><span class="sxs-lookup"><span data-stu-id="f3c7a-270">Action Definition</span></span>
<span data-ttu-id="f3c7a-271">La specifica WS-Addressing 2004/08 definisce un attributo `wsa:Action` per gli elementi `wsdl:portType/wsdl:operation/[wsdl:input | wsdl:output | wsdl:fault]`.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-271">WS-Addressing 2004/08 defines a `wsa:Action` attribute for the `wsdl:portType/wsdl:operation/[wsdl:input | wsdl:output | wsdl:fault]` elements.</span></span> <span data-ttu-id="f3c7a-272">L'associazione WS-Addressing 1.0 WSDL (WS-ADDR10-WSDL) definisce un attributo simile, ovvero `wsaw10:Action`.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-272">WS-Addressing 1.0 WSDL Binding (WS-ADDR10-WSDL) defines a similar attribute, `wsaw10:Action`.</span></span>

<span data-ttu-id="f3c7a-273">L'unica differenza consiste nella semantica del modello Action predefinito, descritta rispettivamente nella sezione 3.3.2 della specifica WS-ADDR e nella sezione 4.4.4 della specifica WS-ADDR10-WSDL.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-273">The only difference between the two is the default Action pattern semantics described in section 3.3.2 of WS-ADDR and section 4.4.4 of WS-ADDR10-WSDL, respectively.</span></span>

<span data-ttu-id="f3c7a-274">È ragionevole avere due endpoint che condividono lo stesso `portType` (o contratto, nella terminologia WCF) ma utilizzando versioni diverse di WS-Addressing.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-274">It is a reasonable to have two endpoints that share the same `portType` (or contract, in WCF terminology) but using different versions of WS-Addressing.</span></span> <span data-ttu-id="f3c7a-275">Tuttavia, se l'attributo Action è definito dall'attributo `portType` e deve essere condiviso da tutti gli endpoint che implementano l'attributo `portType`, risulta impossibile supportare entrambi i modelli Action predefiniti.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-275">But given that Action is defined by the `portType` and should not change across the endpoints that implement the `portType`, it becomes impossible to support both default action patterns.</span></span>

<span data-ttu-id="f3c7a-276">Per risolvere questa controversia, WCF supporta una `Action` singola versione dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-276">To resolve this controversy, WCF supports a single version of the `Action` attribute.</span></span>

<span data-ttu-id="f3c7a-277">B3521: WCF `wsaw10:Action` utilizza `wsdl:portType/wsdl:operation/[wsdl:input | wsdl:output | wsdl:fault]` l'attributo sugli elementi come definito in `Action` WS-ADDR10-WSDL per determinare l'URI per i messaggi corrispondenti indipendentemente dalla versione DI WS-Addressing utilizzata dall'endpoint.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-277">B3521: WCF uses the `wsaw10:Action` attribute on `wsdl:portType/wsdl:operation/[wsdl:input | wsdl:output | wsdl:fault]` elements as defined in WS-ADDR10-WSDL to determine the `Action` URI for the corresponding messages irrespective of the WS-Addressing version used by the endpoint.</span></span>

#### <a name="use-endpoint-reference-inside-wsdl-port"></a><span data-ttu-id="f3c7a-278">Utilizzare il riferimento a endpoint nell'elemento wsdl:port</span><span class="sxs-lookup"><span data-stu-id="f3c7a-278">Use Endpoint Reference Inside WSDL Port</span></span>
<span data-ttu-id="f3c7a-279">La sezione 4.1 di WS-ADDR10-WSDL estende l'elemento `wsdl:port` per includere l'elemento figlio `<wsa10:EndpointReference…/>` allo scopo di descrivere l'endpoint in termini di WS-Addressing.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-279">WS-ADDR10-WSDL section 4.1 extends the `wsdl:port` element to include the `<wsa10:EndpointReference…/>` child element to describe the endpoint in WS-Addressing terms.</span></span> <span data-ttu-id="f3c7a-280">WCF espande questa utilità in WS-Addressing 2004/08, consentendo `<wsa:EndpointReference…/>` `wsdl:port`la visualizzazione come elemento figlio di .</span><span class="sxs-lookup"><span data-stu-id="f3c7a-280">WCF expands this utility on WS-Addressing 2004/08, allowing `<wsa:EndpointReference…/>` to appear as a child element of `wsdl:port`.</span></span>

- <span data-ttu-id="f3c7a-281">R3531: se a un endpoint è associata un'alternativa criteri avente un'asserzione di criteri `<wsaw10:UsingAddressing/>``wsdl:port`.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-281">R3531: If an endpoint has an attached policy alternative with a `<wsaw10:UsingAddressing/>` policy assertion, the corresponding `wsdl:port` element can contain a child element `<wsa10:EndpointReference …/>`.</span></span>

- <span data-ttu-id="f3c7a-282">R3532: se `wsdl:port` un oggetto `<wsa10:EndpointReference …/>`contiene `wsa10:EndpointReference/wsa10:Address` un elemento figlio , `@address` il valore dell'elemento figlio deve corrispondere al valore dell'attributo dell'elemento di pari livello. `wsdl:port` / `wsdl:location`</span><span class="sxs-lookup"><span data-stu-id="f3c7a-282">R3532: If a `wsdl:port` contains a child element `<wsa10:EndpointReference …/>`, the `wsa10:EndpointReference/wsa10:Address` child element value must match the value of the `@address` attribute of the sibling `wsdl:port`/`wsdl:location` element.</span></span>

- <span data-ttu-id="f3c7a-283">R3533: se a un endpoint è associata un'alternativa criteri avente un'asserzione di criteri `<wsap:UsingAddressing/>``wsdl:port`.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-283">R3533: If an endpoint has an attached policy alternative with `<wsap:UsingAddressing/>` policy assertion, the corresponding `wsdl:port` element can contain a child element `<wsa:EndpointReference …/>`.</span></span>

- <span data-ttu-id="f3c7a-284">R3534: se `wsdl:port` un oggetto `<wsa:EndpointReference …/>`contiene `wsa:EndpointReference/wsa:Address` un elemento figlio , `@address` il valore dell'elemento figlio deve corrispondere al valore dell'attributo dell'elemento di pari livello. `wsdl:port` / `wsdl:location`</span><span class="sxs-lookup"><span data-stu-id="f3c7a-284">R3534: If a `wsdl:port` contains a child element `<wsa:EndpointReference …/>`, the `wsa:EndpointReference/wsa:Address` child element value must match the value of the `@address` attribute of the sibling `wsdl:port`/`wsdl:location` element.</span></span>

### <a name="composition-with-ws-security"></a><span data-ttu-id="f3c7a-285">Integrazione con WS-Security</span><span class="sxs-lookup"><span data-stu-id="f3c7a-285">Composition with WS-Security</span></span>
<span data-ttu-id="f3c7a-286">Secondo le sezioni di WS-ADDR e WS-ADDR10 relative alle considerazioni sulla sicurezza, è consigliabile firmare tutte le intestazioni dei messaggi di indirizzamento insieme al corpo del messaggio, in modo da associarli fra loro.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-286">According to security consideration sections in WS-ADDR and WS-ADDR10, all addressing message headers are recommended to be signed together with the message body to bind them together.</span></span>

<span data-ttu-id="f3c7a-287">Quando si utilizza WS-Security per garantire l'integrità dei messaggi, le intestazioni dei messaggi di WS-Addressing nonché le intestazioni ottenute dai parametri o dalle proprietà del riferimento (o da entrambi) devono essere firmate insieme al corpo del messaggio.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-287">When WS-Security is used for message integrity protection, WS-Addressing message headers as well as headers resulted from reference parameters or properties (or both) must be signed together with the body of the message.</span></span>

### <a name="examples"></a><span data-ttu-id="f3c7a-288">Esempi</span><span class="sxs-lookup"><span data-stu-id="f3c7a-288">Examples</span></span>

#### <a name="one-way-message"></a><span data-ttu-id="f3c7a-289">Modello unidirezionale</span><span class="sxs-lookup"><span data-stu-id="f3c7a-289">One-Way Message</span></span>
<span data-ttu-id="f3c7a-290">In questo scenario, il mittente invia un messaggio unidirezionale al destinatario.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-290">In this scenario, the sender sends a one-way message to the receiver.</span></span> <span data-ttu-id="f3c7a-291">Vengono utilizzate le specifiche SOAP 1.2, HTTP 1.1 e W3C WS-Addressing 1.0.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-291">SOAP 1.2, HTTP 1.1, and W3C WS-Addressing 1.0 are used.</span></span>

<span data-ttu-id="f3c7a-292">Struttura dei messaggi di richiesta: le intestazioni dei messaggi includono gli elementi `wsa10:To` e `wsa10:Action`.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-292">The Request Message Structure: The message headers include `wsa10:To` and `wsa10:Action` elements.</span></span> <span data-ttu-id="f3c7a-293">Il corpo dei messaggi include un elemento `<app:Ping>` specifico dello spazio dei nomi dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-293">The message body includes a specific `<app:Ping>` element from the application namespace.</span></span>

<span data-ttu-id="f3c7a-294">Intestazioni HTTP: la destinazione in POST `wsa10:To` corrisponde all'URI nell'elemento.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-294">HTTP Headers: The destination in POST matches the URI in the `wsa10:To` element.</span></span>

<span data-ttu-id="f3c7a-295">L'intestazione Content-Type dispone del valore di `application/soap+xml` come richiesto da SOAP 1.2.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-295">The Content-Type header has the value of `application/soap+xml` as required by SOAP 1.2.</span></span> <span data-ttu-id="f3c7a-296">I parametri `charset` e `action` sono inclusi.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-296">Parameters `charset` and `action` are included.</span></span> <span data-ttu-id="f3c7a-297">Il parametro `action` dell'intestazione Content-Type corrisponde al valore dell'intestazione dei messaggi `wsa10:Action`.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-297">The `action` parameter of the Content-Type header matches the value of the `wsa10:Action` message header.</span></span>

```
POST http://fabrikam123.com/Service HTTP/1.1
Content-Type: application/soap+xml; charset=utf-8;  
              action="http://fabrikam123.com/Service/OneWay"
Host: 131.107.72.15
Content-Length: 1501
Expect: 100-continue
Proxy-Connection: Keep-Alive
<s12:Envelope>
  <s12:Header>
    <wsa10:To s12:mustUnderstand="1">
        http://fabrikam123.com/Service
    </wsa10:To>
    <wsa10:Action s12:mustUnderstand="1">
        http://fabrikam123.com/Service/OneWay
    </wsa10:Action>
  </s12:Header>
  <s12:Body>
    <Ping xmlns="http://fabrikam123.com/Service/">
      <Text>Hello World</Text>
    </Ping>
  </s12:Body>
</s12:Envelope>
```

<span data-ttu-id="f3c7a-298">Il destinatario fornisce con una risposta HTTP vuota e lo stato 202.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-298">The receiver responds with an empty HTTP response and status 202.</span></span> <span data-ttu-id="f3c7a-299">Un esempio della risposta HTTP:</span><span class="sxs-lookup"><span data-stu-id="f3c7a-299">An example of the HTTP response:</span></span>

```
HTTP/1.1 202 Accepted
Date: Fri, 15 Jul 2005 08:56:07 GMT
Server: Microsoft-IIS/6.0
MicrosoftOfficeWebServer: 5.0_Pub
X-Powered-By: ASP.NET
X-AspNet-Version: 2.0.50215
Cache-Control: private
Content-Length: 0
```

## <a name="soap-message-transmission-optimization-mechanism"></a><span data-ttu-id="f3c7a-300">SOAP MTOM</span><span class="sxs-lookup"><span data-stu-id="f3c7a-300">SOAP Message Transmission Optimization Mechanism</span></span>
<span data-ttu-id="f3c7a-301">In questa sezione vengono descritti i dettagli di implementazione WCF per il servizio MTOM SOAP HTTP.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-301">This section describes the WCF implementation details for the HTTP SOAP MTOM.</span></span> <span data-ttu-id="f3c7a-302">La tecnologia MTOM è un meccanismo di codifica dei messaggi SOAP della stessa classe della codifica testo/XML tradizionale o della codifica binaria WCF.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-302">MTOM technology is SOAP message encoding mechanism of the same class as traditional text/XML encoding or WCF Binary encoding.</span></span> <span data-ttu-id="f3c7a-303">Il meccanismo MTOM prevede le funzionalità seguenti:</span><span class="sxs-lookup"><span data-stu-id="f3c7a-303">MTOM includes the following:</span></span>

- <span data-ttu-id="f3c7a-304">Meccanismo di codifica e assemblaggio di pacchetti XML descritto da [XOP] che ottimizza le voci di informazioni XML contenenti dati binari con codifica in base 64 suddividendoli in parti binarie distinte.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-304">An XML encoding and packaging mechanism described by [XOP] that optimizes XML information items containing base64-encoded binary data into separate binary parts.</span></span>

- <span data-ttu-id="f3c7a-305">Incapsulamento MIME del pacchetto XOP che serializza l'InfoSet XML e ogni parte binaria del pacchetto XOP in una parte MIME distinta.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-305">A MIME encapsulation of the XOP package that serializes the XML Infoset and each binary part of the XOP package into a separate MIME part.</span></span>

- <span data-ttu-id="f3c7a-306">Codifica MIME XOP applicata alla SOAP 1.x envelope.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-306">A MIME XOP encoding applied to SOAP 1.x Envelope.</span></span>

- <span data-ttu-id="f3c7a-307">Associazione di trasporto HTTP.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-307">An HTTP transport binding.</span></span>

<span data-ttu-id="f3c7a-308">È possibile usare MTOM con trasporti non HTTP con WCF.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-308">It is possible to use MTOM with non-HTTP transports with WCF.</span></span> <span data-ttu-id="f3c7a-309">quanto descritto in questo argomento si basa sul protocollo HTTP.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-309">However, in this topic we will focus on HTTP.</span></span>

<span data-ttu-id="f3c7a-310">Il formato MTOM sfrutta un numeroso set di specifiche relative al meccanismo MTOM stesso, a XOP e a MIME.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-310">The MTOM format leverages a large set of specifications covering MTOM itself, XOP, and MIME.</span></span> <span data-ttu-id="f3c7a-311">La modularità di questo set di specifiche rende piuttosto difficile ricavare in modo esatto i requisiti relativi alla semantica di formato ed elaborazione.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-311">Modularity of this specification set makes it somewhat difficult to reconstruct exact requirements on the format and processing semantics.</span></span> <span data-ttu-id="f3c7a-312">Questa sezione descrive i requisiti di formato ed elaborazione dell'associazione MTOM HTTP.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-312">This section describes the format and processing requirements for MTOM HTTP binding.</span></span>

### <a name="mtom-message-encoding"></a><span data-ttu-id="f3c7a-313">Codifica dei messaggi MTOM</span><span class="sxs-lookup"><span data-stu-id="f3c7a-313">MTOM Message Encoding</span></span>

#### <a name="generating-mtom-messages"></a><span data-ttu-id="f3c7a-314">Generazione di messaggi MTOM</span><span class="sxs-lookup"><span data-stu-id="f3c7a-314">Generating MTOM messages</span></span>
<span data-ttu-id="f3c7a-315">La sezione 3.1 di [XOP] descrive il processo di codifica di elementi XML aventi voci di informazioni sugli elementi contenenti valori in base 64 in un pacchetto XOP definito in modo astratto.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-315">The [XOP] section 3.1 describes the process of encoding XML with element information items that contain base64 values into an abstractly defined XOP package.</span></span>

<span data-ttu-id="f3c7a-316">La sequenza di passaggi seguente descrive il processo di codifica specifico del meccanismo MTOM:</span><span class="sxs-lookup"><span data-stu-id="f3c7a-316">The following sequence of steps describes the MTOM-specific encoding process:</span></span>

1. <span data-ttu-id="f3c7a-317">Assicurarsi che la busta SOAP da codificare non `[local name]` `Include`contenga alcun elemento di informazioni sull'elemento con un `[namespace name]` e `http://www.w3.org/2004/08/xop/include` un oggetto di .</span><span class="sxs-lookup"><span data-stu-id="f3c7a-317">Ensure that the SOAP Envelope to be encoded contains no element information item with a `[namespace name]` of `http://www.w3.org/2004/08/xop/include` and a `[local name]` of `Include`.</span></span>

2. <span data-ttu-id="f3c7a-318">Creare un pacchetto MIME vuoto.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-318">Create an empty MIME package.</span></span>

3. <span data-ttu-id="f3c7a-319">Identificare all'interno dell'InfoSet XML originale le voci di informazioni sugli elementi da ottimizzare.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-319">Identify within the Original XML Infoset the element information items to be optimized.</span></span> <span data-ttu-id="f3c7a-320">Per gli elementi da ottimizzare, i `[children]` caratteri che costituiscono l'elemento di `xs:base64Binary` informazioni dell'elemento devono essere in formato canonico (vedere XSD-2, 3.2.16 base64Binary) e non devono contenere spazi vuoti che precedono, inline o seguono il contenuto diverso dallo spazio vuoto.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-320">For the items to be optimized, the characters that make up the `[children]` of the element information item must be in the canonical form of `xs:base64Binary` (see XSD-2, 3.2.16 base64Binary) and must not contain any white-space characters preceding, inline with, or following the non-white-space content.</span></span>

4. <span data-ttu-id="f3c7a-321">Creare una XOP SOAP envelope uguale alla SOAP envelope originale, sostituendo tuttavia al figlio di ogni voce di informazioni sugli elementi identificato nel passaggio precedente una voce di informazioni sugli elementi `xop:Include` costruito come segue:</span><span class="sxs-lookup"><span data-stu-id="f3c7a-321">Create an XOP SOAP Envelope that is a copy of the Original SOAP Envelope, but with the children of each element information item identified in the previous step replaced by an `xop:Include` element information item constructed as follows:</span></span>

    1. <span data-ttu-id="f3c7a-322">Trasformare i caratteri sostituiti in dati binari elaborandoli come dati codificati in base 64.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-322">Transform the replaced characters into binary data by processing them as base64-encoded data.</span></span>

    2. <span data-ttu-id="f3c7a-323">Generare un valore univoco di intestazione Content-ID che soddisfi i requisiti R3133 e R3134.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-323">Generate a unique Content-ID header value that satisfies requirements R3133 and R3134.</span></span>

    3. <span data-ttu-id="f3c7a-324">Generare un'intestazione MIME Content-Transfer-Encoding con il valore in binario.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-324">Generate a Content-Transfer-Encoding MIME header with the value binary.</span></span>

    4. <span data-ttu-id="f3c7a-325">Se la voce di informazioni sugli elementi da ottimizzare (ovvero il padre [parent] della voce di informazioni sugli elementi `xop:Include` appena aggiunto) contiene una voce di informazioni sugli attributi `xmime:contentType`, generare un'intestazione Content-Type MIME con il valore dell'attributo `xmime:contentType`.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-325">If the element information item being optimized (the [parent] of the newly inserted `xop:Include` element information item) has an `xmime:contentType` attribute information item, generate a Content-Type MIME header with the value of the `xmime:contentType` attribute.</span></span>

    5. <span data-ttu-id="f3c7a-326">Generare una nuova parte MIME binaria avente un contenuto formato dagli elementi seguenti: dati binari decodificati a partire dai caratteri sostituiti elaborati come dati in base 64, intestazione Content-ID come da passaggio 4b, intestazione Content- Transfer-Encoding come da passaggio 4c e intestazione Content-Type come da passaggio 4d, se presente.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-326">Generate a new binary MIME part with content formed by binary data decoded from the replaced characters processed as base64, Content-ID header from 4b, Content- Transfer-Encoding header from 4c, Content-Type header if generated in step 4d.</span></span>

    6. <span data-ttu-id="f3c7a-327">Aggiungere un attributo `href` all'elemento `xop:Include` con il valore cid: uri derivato dal valore dell'intestazione Content-ID generato nel passaggio 4b.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-327">Add an `href` attribute to the `xop:Include` element with the value cid: uri derived from Content-ID header value generated in step 4b.</span></span> <span data-ttu-id="f3c7a-328">Rimuovere i caratteri\<di inclusione " " e ">", eseguire `cid:`l'escape URL nella stringa rimanente e aggiungere il prefisso .</span><span class="sxs-lookup"><span data-stu-id="f3c7a-328">Remove the enclosing "\<" and ">" characters, URL-escape the remaining string, and add the prefix `cid:`.</span></span> <span data-ttu-id="f3c7a-329">La suddetta conversione, da eseguire in base ai documenti RFC1738 e RFC2396, deve riguardare almeno il set di caratteri seguente,</span><span class="sxs-lookup"><span data-stu-id="f3c7a-329">The following minimum character set is required to be escaped by RFC1738 and RFC2396.</span></span> <span data-ttu-id="f3c7a-330">ma può essere applicata anche ad altri caratteri.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-330">Other characters can be escaped.</span></span>

        ```
        Hexadecimal 00-1F , 7F, 20, "<" | ">" | "#" | "%" | <">
        "{" | "}" | "|" | "\" | "^" | "[" | "]" | "`" | "~" | "^"
        ```

5. <span data-ttu-id="f3c7a-331">Creare una parte MIME radice contenente la XOP SOAP envelope ottenuta nel passaggio 4.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-331">Create a root MIME part with the XOP SOAP Envelope from step 4.</span></span>

6. <span data-ttu-id="f3c7a-332">Scrivere le intestazioni HTTP, compresa l'intestazione Content-Type HTTP.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-332">Write the HTTP headers, including the HTTP Content-Type header.</span></span>

7. <span data-ttu-id="f3c7a-333">Scrivere il pacchetto MIME.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-333">Write the MIME package.</span></span>

#### <a name="processing-mtom-messages"></a><span data-ttu-id="f3c7a-334">Elaborazione di messaggi MTOM</span><span class="sxs-lookup"><span data-stu-id="f3c7a-334">Processing MTOM messages</span></span>
<span data-ttu-id="f3c7a-335">L'elaborazione di un messaggio MTOM è l'esatto contrario del processo descritto nella sezione precedente "Generazione di messaggi MTOM":</span><span class="sxs-lookup"><span data-stu-id="f3c7a-335">Processing of an MTOM message is the exact reverse of the process described in the preceding "Generating MTOM messages" section:</span></span>

1. <span data-ttu-id="f3c7a-336">Verificare che la parte MIME radice contenga l'elemento Content-Type `application/xop+xml`.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-336">Ensure the root MIME part has the Content-Type `application/xop+xml`.</span></span>

2. <span data-ttu-id="f3c7a-337">Costruire una SOAP envelope analizzando la parte MIME radice del pacchetto come documento XML.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-337">Construct a SOAP Envelope by parsing the root MIME part of the package as an XML document.</span></span> <span data-ttu-id="f3c7a-338">La codifica dei caratteri viene determinata in base al parametro `charset` del Content-Type della parte MIME radice.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-338">Character encoding is determined by the `charset` parameter of the Content-Type of the root MIME part.</span></span>

3. <span data-ttu-id="f3c7a-339">Per ogni voce di informazioni sugli elementi della SOAP envelope costruita, che come unico membro della proprietà dei relativi figli [children] presenta una voce di informazioni sugli elementi `xop:Include`, eseguire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="f3c7a-339">For each element information item in the constructed SOAP Envelope, which has, as the sole member of its [children] property, an `xop:Include` element information item:</span></span>

    1. <span data-ttu-id="f3c7a-340">Rimuovere il prefisso `cid:` ed eseguire la conversione URI inversa di tutte le sequenze escape (RFC 2396) contenute nel valore dell'attributo `@href` dell'elemento `xop:Include`.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-340">Remove the `cid:` prefix and unescape all URI-escape sequences (RFC 2396) in the value of the `@href` attribute of the `xop:Include` element.</span></span> <span data-ttu-id="f3c7a-341">Racchiudere la stringa\<di risultato in " ", ">".</span><span class="sxs-lookup"><span data-stu-id="f3c7a-341">Enclose the result string in "\<", ">".</span></span>

    2. <span data-ttu-id="f3c7a-342">Individuare la parte MIME contenente il valore dell'intestazione Content-ID corrispondente alla stringa ottenuta nel passaggio 3a.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-342">Locate the MIME part with the Content-ID header value that matches the string derived in step 3a.</span></span>

    3. <span data-ttu-id="f3c7a-343">Sostituire la voce di informazioni sugli elementi `xop:Include` contenuto nella proprietà `children` di ogni elemento contenente le voci di informazioni sugli elementi che rappresentano la codifica canonica in base 64 (vedere XSD-2, 3.2.16 base64Binary) del corpo dell'entità della parte MIME identificato nel passaggio 3b. In pratica, sostituire la voce di informazioni sugli elementi `xop:Include` con i dati ricostruiti a partire dalla parte di pacchetto.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-343">Replace the `xop:Include` element information item that appears in the `children` property of each item with the character information items that represent the canonical base64 encoding (see XSD-2, 3.2.16 base64Binary) of the entity body of the MIME part identified in step 3b (effectively replace the `xop:Include` element information item with the data reconstructed from the package part).</span></span>

#### <a name="http-content-type-header"></a><span data-ttu-id="f3c7a-344">Intestazione Content-Type HTTP</span><span class="sxs-lookup"><span data-stu-id="f3c7a-344">HTTP Content-Type Header</span></span>
<span data-ttu-id="f3c7a-345">Di seguito è riportato un elenco di chiarimenti WCF per il formato dell'intestazione Content-Type HTTP di un messaggio con codifica MTOM SOAP 1.x derivato dai requisiti indicati nella specifica MTOM stessa e derivano da MTOM e RFC 2387.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-345">The following is a list of WCF clarifications for the format of the HTTP Content-Type header of a SOAP 1.x MTOM-encoded message derived from requirements stated in the MTOM specification itself and are derived from MTOM and RFC 2387.</span></span>

- <span data-ttu-id="f3c7a-346">R4131: un'intestazione Content-Type HTTP deve contenere il valore multipart/related (che non fa distinzione fra maiuscole e minuscole) e i relativi parametri.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-346">R4131: An HTTP Content-Type header must have the value of multipart/related (case-insensitive) and its parameters.</span></span> <span data-ttu-id="f3c7a-347">Anche i nomi dei parametri non fanno distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-347">Parameter names are case-insensitive.</span></span> <span data-ttu-id="f3c7a-348">Inoltre, l'ordine dei parametri è irrilevante.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-348">Parameter order is not significant.</span></span>

- <span data-ttu-id="f3c7a-349">La notazione BNF completa dell'intestazione Content-Type dei messaggi MIME è riportata nella sezione 5.1 del documento RFC 2045.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-349">The full Backus-Naur Form (BNF) of the Content-Type header for MIME messages is listed in RFC 2045, section 5.1.</span></span>

- <span data-ttu-id="f3c7a-350">R4132: un'intestazione Content-Type HTTP deve contenere un parametro di tipo avente il valore `application/xop+xml` compreso fra virgolette doppie.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-350">R4132: An HTTP Content-Type header must have a type parameter with the value `application/xop+xml` enclosed in double quotation marks.</span></span>

<span data-ttu-id="f3c7a-351">Mentre il requisito di utilizzare le virgolette doppie non è esplicito in RFC 2387, il\@testo osserva che tutti i parametri multipart/tipo di supporto correlati molto probabilmente contengono caratteri riservati come " " o " " /" e pertanto devono essere racchiusi tra virgolette doppie.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-351">While the requirement to use double quotation marks is not explicit in RFC 2387, the text observes that all of the multipart/related media type parameters most likely contain reserved characters like "\@" or "/" and therefore need double quotation marks.</span></span>

- <span data-ttu-id="f3c7a-352">R4133: un'intestazione Content-Type HTTP deve presentare un parametro start con il valore dell'intestazione Content-ID della parte MIME contenente l'elemento SOAP 1.x Envelope, racchiuso fra virgolette doppie.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-352">R4133: An HTTP Content-Type header should have a start parameter with the value of the Content-ID header of the MIME part that contains the SOAP 1.x Envelope, enclosed in double quotation marks.</span></span> <span data-ttu-id="f3c7a-353">Se tale parametro viene omesso, la SOAP 1.x envelope deve essere inclusa nella prima parte MIME.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-353">If the start parameter is omitted, the first MIME part must contain the SOAP 1.x Envelope.</span></span>

- <span data-ttu-id="f3c7a-354">R4134: un'intestazione Content-Type HTTP di un messaggio con codifica SOAP 1.1 MTOM deve includere il parametro start-info con il valore text/xml racchiuso fra virgolette doppie.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-354">R4134: An HTTP Content-Type header for a SOAP 1.1 MTOM encoded message must include the start-info parameter with the value of text/xml, enclosed in double quotation marks.</span></span>

- <span data-ttu-id="f3c7a-355">R4135: un'intestazione Content-Type HTTP di un messaggio con codifica SOAP 1.2 MTOM deve includere il parametro start-info con il valore `application/soap+xml` racchiuso fra virgolette doppie.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-355">R4135: An HTTP Content-Type header for a SOAP 1.2 MTOM-encoded message must include the start-info parameter with the value of `application/soap+xml`, enclosed in double quotation marks.</span></span>

- <span data-ttu-id="f3c7a-356">R4136: un'intestazione Content-Type HTTP di un messaggio con codifica SOAP 1.x MTOM deve contenere un parametro boundary il cui valore (racchiuso fra virgolette doppie) corrisponda al formato BNF del limite MIME definito nella sezione 5.1.1 del documento RFC 2046.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-356">R4136: HTTP Content-Type header for a SOAP 1.x MTOM-encoded message must have the boundary parameter with the value (enclosed in double quotation marks) that matches the MIME boundary BNF defined in RFC 2046, section 5.1.1</span></span>

    ```
    boundary := 0*69<bchars> bcharsnospace
    bchars := bcharsnospace / " "
    bcharsnospace :=    DIGIT / ALPHA / "'" / "(" / ")" / "+"
                        / "_" / "," / "-" / "." / "/" / ":" / "=" / "?"
    ```

     <span data-ttu-id="f3c7a-357">Esempi:</span><span class="sxs-lookup"><span data-stu-id="f3c7a-357">Examples:</span></span>

     <span data-ttu-id="f3c7a-358">CORRETTO</span><span class="sxs-lookup"><span data-stu-id="f3c7a-358">CORRECT</span></span>

    ```
    Content-Type: multipart/related; type="application/xop+xml";start=" <part0@tempuri.org>";boundary="uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=1";start-info="text/xml"
    ```

     <span data-ttu-id="f3c7a-359">CORRETTO</span><span class="sxs-lookup"><span data-stu-id="f3c7a-359">CORRECT</span></span>

    ```
    Content-Type: Multipart/Related; type="application/xop+xml";start-info="text/xml";boundary="uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=1"
    ```

     <span data-ttu-id="f3c7a-360">NON CORRETTO</span><span class="sxs-lookup"><span data-stu-id="f3c7a-360">INCORRECT</span></span>

    ```
    Content-Type: Multipart/Related; type=application/xop+xml;start=" <part0@tempuri.org>";start-info="text/xml";boundary="uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=1"
    ```

#### <a name="infoset-mime-part"></a><span data-ttu-id="f3c7a-361">Parte MIME InfoSet</span><span class="sxs-lookup"><span data-stu-id="f3c7a-361">Infoset MIME Part</span></span>
<span data-ttu-id="f3c7a-362">La SOAP 1.x envelope è incapsulata come parte radice del pacchetto XOP MIME e spesso viene detta "parte `infoset`".</span><span class="sxs-lookup"><span data-stu-id="f3c7a-362">The SOAP 1.x Envelope is encapsulated as a root part of the XOP MIME package and is often called the `infoset` part.</span></span>

- <span data-ttu-id="f3c7a-363">R4141: la SOAP 1.x envelope deve essere incapsulata come parte radice del pacchetto XOP MIME, detto "parte `infoset`", a cui si fa riferimento nell'intestazione Content-Type HTTP.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-363">R4141: The SOAP 1.x Envelope must be encapsulated as a root part of the XOP MIME package, called the `infoset` part and referenced from the HTTP Content-Type.</span></span>

- <span data-ttu-id="f3c7a-364">R4142: la parte `Infoset` SOAP deve contenere le intestazioni MIME seguenti: `Content-ID`, `Content-Transfer-Encoding` e `Content-Type`.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-364">R4142: The SOAP `Infoset` part must include the following MIME headers: `Content-ID`, `Content-Transfer-Encoding`, and `Content-Type`.</span></span>

<span data-ttu-id="f3c7a-365">Il formato dell'intestazione Content-ID è definito nel documento RFC 2045 come</span><span class="sxs-lookup"><span data-stu-id="f3c7a-365">The format of the Content-ID header is defined by RFC 2045 as</span></span>

```
"Content-ID" ":" msg-id
```

<span data-ttu-id="f3c7a-366">in cui l'elemento `msg-id` è definito nel documento RFC 2822 (che sostituisce il documento RFC 822, a cui si fa riferimento nel documento RFC 2045) come:</span><span class="sxs-lookup"><span data-stu-id="f3c7a-366">where `msg-id` is defined in RFC 2822 (that supersedes RFC 822, referenced in RFC 2045) as:</span></span>

```
msg-id    =       [CFWS] "<" id-left "@" id-right ">" [CFWS]
```

<span data-ttu-id="f3c7a-367">ed è effettivamente un indirizzo\<e-mail racchiuso tra " " e ">".</span><span class="sxs-lookup"><span data-stu-id="f3c7a-367">and is effectively an email address enclosed within "\<" and  ">".</span></span> <span data-ttu-id="f3c7a-368">Il prefisso e il suffisso `[CFWS]` sono stati aggiunti nel documento RFC 2822 per contenere commenti e non devono essere utilizzati per mantenere l'interoperabilità.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-368">The `[CFWS]` prefix and suffix were added in RFC 2822 to carry comments and should not be used to preserve interoperability.</span></span>

<span data-ttu-id="f3c7a-369">R4143: il valore dell'intestazione Content-ID della parte MIME InfoSet deve attenersi alle regole di definizione dell'elemento `msg-id` indicate nel documento RFC 2822, omettendo le parti `[CFWS]` di prefisso e suffisso.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-369">R4143: The value of the Content-ID header for the Infoset MIME part must follow `msg-id` production from RFC 2822 with the `[CFWS]` prefix and suffix parts omitted.</span></span>

<span data-ttu-id="f3c7a-370">Un certo numero di implementazioni MIME relaxed\<requisiti per il valore racchiuso tra `absoluteURI` " "\<e ">" per essere un indirizzo di posta elettronica e utilizzato racchiuso tra " " , ">" oltre all'indirizzo di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-370">A number of MIME implementations relaxed requirements for the value enclosed within "\<" and ">" to be an email address and used `absoluteURI` enclosed in "\<" , ">" in addition to the email address.</span></span> <span data-ttu-id="f3c7a-371">Questa versione di WCF utilizza i valori dell'intestazione MIME Content-ID nel modulo:</span><span class="sxs-lookup"><span data-stu-id="f3c7a-371">This version of WCF uses values of the Content-ID MIME header of the form:</span></span>

```
Content-ID: <http://tempuri.org/0>
```

<span data-ttu-id="f3c7a-372">R4144: i processori MTOM devono accettare valori di intestazione Content-ID corrispondenti all'elemento `msg-id` con requisiti ridotti riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-372">R4144: MTOM processors should accept Content-ID header values that match the following relaxed `msg-id`.</span></span>

```
msg-id-relaxed =     [CFWS] "<" (absoluteURI | mail-address) ">" [CFWS]
mail-address   =     id-left "@" id-right
```

<span data-ttu-id="f3c7a-373">Il protocollo MIME (RFC 2045) fornisce l'intestazione Content-Transfer-Encoding per comunicare la codifica del contenuto della parte MIME.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-373">MIME (RFC 2045) provides the Content-Transfer-Encoding header to communicate encoding of the content of the MIME part.</span></span> <span data-ttu-id="f3c7a-374">L'impostazione predefinita dell'intestazione Content-Transfer-Encoding è una codifica a 7 bit, che tuttavia per la maggior parte dei messaggi SOAP risulta inadatta. Pertanto, tale intestazione è necessaria per garantire una maggiore interoperabilità:</span><span class="sxs-lookup"><span data-stu-id="f3c7a-374">The default defined for Content-Transfer-Encoding is 7-bit, which is not suitable for most SOAP messages, so the Content-Transfer-Encoding header is needed for greater interoperability:</span></span>

- <span data-ttu-id="f3c7a-375">R4145: la parte SOAP InfoSet deve contenere l'intestazione Content-Transfer-Encoding.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-375">R4145: The SOAP Infoset part must contain the Content-Transfer-Encoding header.</span></span>

- <span data-ttu-id="f3c7a-376">R4146: se la codifica dei caratteri della SOAP envelope è UTF-8, il valore dell'intestazione Content-Transfer-Encoding deve corrispondere a una codifica a 8 bit.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-376">R4146: If the SOAP Envelope character encoding is UTF-8, the value of the Content-Transfer-Encoding header must be 8-bit.</span></span>

- <span data-ttu-id="f3c7a-377">R4147: se la codifica dei caratteri della SOAP envelope è UTF-16, il valore dell'intestazione Content-Transfer-Encoding deve corrispondere a una codifica binaria.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-377">R4147: If the SOAP Envelope character encoding is UTF-16, the value of the Content-Transfer-Encoding header must be binary.</span></span>

- <span data-ttu-id="f3c7a-378">Secondo quanto indicato nella sezione 5 di [XOP]:</span><span class="sxs-lookup"><span data-stu-id="f3c7a-378">According to [XOP] section 5,</span></span>

- <span data-ttu-id="f3c7a-379">R4148: la parte del set di infoset SOAP1.1 deve contenere l'intestazione Content-Type con il tipo di supporto application/xop-xml e i parametri type, "text/xml" e charset</span><span class="sxs-lookup"><span data-stu-id="f3c7a-379">R4148: SOAP1.1 Infoset part must contain Content-Type header with media type application/xop+xml and parameters type="text/xml" and charset</span></span>

    ```
    Content-Type: application/xop+xml;
                  charset=utf-8;type="text/xml"
    ```

- <span data-ttu-id="f3c7a-380">R4149: la parte dell'Infoset SOAP 1.2 deve `application/xop+xml` contenere l'intestazione Content-Type con il tipo di supporto e i parametri type , "`application/soap+xml`e `charset`.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-380">R4149: The SOAP 1.2 Infoset part must contain the Content-Type header with media type `application/xop+xml` and parameters type="`application/soap+xml`" and `charset`.</span></span>

    ```
    Content-Type: application/xop+xml;
                  charset=utf-8;type="application/soap+xml"
    ```

     <span data-ttu-id="f3c7a-381">Benché XOP consenta di definire il parametro `charset` di `application/xop+xml` come facoltativo, tale parametro è necessario per l'interoperabilità, analogamente al requisito di BP 1.1 relativo al parametro `charset` del tipo di supporto `text/xml`.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-381">While XOP defines the `charset` parameter for `application/xop+xml` to be optional, it is needed for interoperability similar to the BP 1.1 requirement on the `charset` parameter for the `text/xml` media type.</span></span>

- <span data-ttu-id="f3c7a-382">R41410: i parametri `type` e `charset` devono essere presenti nell'intestazione Content-Type della parte SOAP 1.x InfoSet.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-382">R41410: The `type` and `charset` parameters must be present on the Content-Type header of the SOAP 1.x Infoset part.</span></span>

#### <a name="wcf-endpoint-support-for-mtom"></a><span data-ttu-id="f3c7a-383">Supporto degli endpoint WCF per MTOM</span><span class="sxs-lookup"><span data-stu-id="f3c7a-383">WCF Endpoint Support for MTOM</span></span>
<span data-ttu-id="f3c7a-384">Lo scopo del meccanismo MTOM è codificare un messaggio SOAP allo scopo di ottimizzare i dati codificati in base 64.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-384">The purpose of MTOM is to encode a SOAP message to optimize base64-encoded data.</span></span> <span data-ttu-id="f3c7a-385">Segue un elenco di vincoli:</span><span class="sxs-lookup"><span data-stu-id="f3c7a-385">The following is a list of constraints:</span></span>

- <span data-ttu-id="f3c7a-386">R4151: qualsiasi voce di informazioni sugli elementi contenente dati con codifica in base 64 può essere ottimizzata.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-386">R4151: Any element information item that contains base64-encoded data may be optimized.</span></span>

- <span data-ttu-id="f3c7a-387">B4152: WCF ottimizza gli elementi di informazioni sugli elementi che contengono dati con codifica base64 e superano i 1024 byte di lunghezza.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-387">B4152: WCF optimizes element information items that contain base64-encoded data and exceed 1024 bytes in length.</span></span>

<span data-ttu-id="f3c7a-388">Un endpoint WCF configurato per l'utilizzo di MTOM invierà sempre messaggi con codifica MTOM.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-388">A WCF endpoint configured to use MTOM will always send MTOM-encoded messages.</span></span> <span data-ttu-id="f3c7a-389">Anche se nessuna parte soddisfa i criteri previsti, il messaggio viene comunque considerato come messaggio con codifica MTOM, serializzato come pacchetto MIME e avente una sola parte MIME contenente la SOAP envelope.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-389">Even if no parts meet the required criteria, the message is still MTOM-encoded (serialized as a MIME package with a single MIME part containing the SOAP envelope).</span></span>

### <a name="ws-policy-assertion-for-mtom"></a><span data-ttu-id="f3c7a-390">Asserzione di WS-Policy relativa a MTOM</span><span class="sxs-lookup"><span data-stu-id="f3c7a-390">WS-Policy Assertion for MTOM</span></span>
<span data-ttu-id="f3c7a-391">WCF utilizza la seguente asserzione di criteri per indicare l'utilizzo Di MTOM per endpoint:WCF uses the following policy assertion to indicate MTOM usage by endpoint:</span><span class="sxs-lookup"><span data-stu-id="f3c7a-391">WCF uses the following policy assertion to indicate MTOM usage by endpoint:</span></span>

```xml
<wsoma:OptimizedMimeSerialization ... />
```

- <span data-ttu-id="f3c7a-392">R4211: l'asserzione di criteri precedente contiene un soggetto dei criteri di endpoint e impone che tutti i messaggi inviati all'endpoint e provenienti da quest'ultimo vengano ottimizzati tramite il meccanismo MTOM.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-392">R4211: The preceding policy assertion has an Endpoint Policy Subject and specifies that all messages sent to and received from the endpoint must be optimized using MTOM.</span></span>

- <span data-ttu-id="f3c7a-393">B4212: se configurato per l'utilizzo dell'ottimizzazione MTOM, un endpoint WCF `wsdl:binding`aggiunge un'asserzione di criteri MTOM ai criteri associati al file corrispondente.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-393">B4212: When configured to use MTOM optimization, an WCF endpoint adds an MTOM Policy assertion to the policy attached to the corresponding `wsdl:binding`.</span></span>

### <a name="composition-with-ws-security"></a><span data-ttu-id="f3c7a-394">Integrazione con WS-Security</span><span class="sxs-lookup"><span data-stu-id="f3c7a-394">Composition with WS-Security</span></span>
<span data-ttu-id="f3c7a-395">MTOM è un meccanismo `text/xml` di codifica simile a XML binario WCF.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-395">MTOM is an encoding mechanism that is similar to `text/xml` and WCF Binary XML.</span></span> <span data-ttu-id="f3c7a-396">Il meccanismo MTOM può integrarsi perfettamente con il protocollo WS-Security e gli altri protocolli WS - \*: un messaggio protetto mediante il protocollo WS-Security può infatti essere ottimizzato tramite MTOM.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-396">MTOM offers natural composition with WS-Security and other WS-\* protocols: a message secured using WS-Security can be optimized using MTOM.</span></span>

### <a name="examples"></a><span data-ttu-id="f3c7a-397">Esempi</span><span class="sxs-lookup"><span data-stu-id="f3c7a-397">Examples</span></span>

#### <a name="wcf-soap-11-message-encoded-using-mtom"></a><span data-ttu-id="f3c7a-398">Esempio di messaggio WCF SOAP 1.1 codificato tramite MTOM</span><span class="sxs-lookup"><span data-stu-id="f3c7a-398">WCF SOAP 1.1 Message Encoded Using MTOM</span></span>

```
POST http://131.107.72.15/Mtom/svc/service.svc/Soap11MtomUTF8 HTTP/1.1
SOAPAction: "http://xmlsoap.org/echoBinaryAsString"
Content-Type: multipart/related;type="application/xop+xml";
              start="<http://tempuri.org/0>";start-info="text/xml";
       boundary="uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=1"
Host: 131.107.72.15
Content-Length: 1501
--uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=1
Content-ID: <http://tempuri.org/0>
Content-Transfer-Encoding: 8bit
Content-Type: application/xop+xml;charset=utf-8;type="text/xml"
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Body>
    <EchoBinaryAsString xmlns="http://xmlsoap.org/Ping">
      <array>
        <xop:Include
         href="cid:http%3A%2F%2Ftempuri.org%2F1%2F632618206521093670"
         xmlns:xop="http://www.w3.org/2004/08/xop/include"/>
      </array>
    </EchoBinaryAsString>
  </s:Body>
</s:Envelope>
--uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=1
Content-ID: <http://tempuri.org/1/632618206521093670>
Content-Transfer-Encoding: binary
Content-Type: application/octet-stream
…Binary Content..
--uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=1
```

#### <a name="wcf-secure-soap-12-message-encoded-using-mtom"></a><span data-ttu-id="f3c7a-399">Esempio di messaggio WCF Secure SOAP 1.2 codificato tramite MTOM</span><span class="sxs-lookup"><span data-stu-id="f3c7a-399">WCF Secure SOAP 1.2 Message Encoded Using MTOM</span></span>
<span data-ttu-id="f3c7a-400">Questo esempio illustra la codifica tramite MTOM e SOAP 1.2 di un messaggio protetto mediante WS-Security.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-400">In this example, a message is encoded using MTOM and SOAP 1.2 that is protected using WS-Security.</span></span> <span data-ttu-id="f3c7a-401">Le parti binarie identificate per la codifica sono il contenuto del token `BinarySecurityToken`, il valore `CipherValue` dell'elemento `EncryptedData` che corrisponde alla firma crittografata e il corpo crittografato.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-401">The binary parts identified for encoding are the contents of the `BinarySecurityToken`, `CipherValue` of the `EncryptedData` corresponding to the encrypted signature and encrypted body.</span></span> <span data-ttu-id="f3c7a-402">Si noti che l'oggetto `CipherValue` non è stato identificato per l'ottimizzazione `EncryptedKey` da WCF, perché la sua lunghezza è inferiore a 1024 byte.</span><span class="sxs-lookup"><span data-stu-id="f3c7a-402">Note that the `CipherValue` of the `EncryptedKey` was not identified for optimization by WCF, because its length is less then 1024 bytes.</span></span>

```
POST http://131.107.72.15/Mtom/service.svc/Soap12MtomSecureSignEncrypt HTTP/1.1
Content-Type: multipart/related; type="application/xop+xml";
              start="<http://tempuri.org/0>";
            boundary="uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=3";
              start-info="application/soap+xml";
              action="http://xmlsoap.org/echoBinaryAsString"
Host: 131.107.72.15
Content-Length: 1941
--uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=3
Content-ID: <http://tempuri.org/0>
Content-Transfer-Encoding: 8bit
Content-Type: application/xop+xml;charset=utf-8;type="application/soap+xml"
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/" xmlns:u="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd">
  <s:Header>
    <o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd">
      <u:Timestamp u:Id="uuid-4d4ee765-5717-4d53-9ac9-99bddc07df6c-5">
        <u:Created>2005-09-09T06:57:32.488Z</u:Created>
        <u:Expires>2005-09-09T07:02:32.488Z</u:Expires>
      </u:Timestamp>
      <o:BinarySecurityToken u:Id="uuid-4d4ee765-5717-4d53-9ac9-99bddc07df6c-2" ValueType="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-x509-token-profile-1.0#X509v3" EncodingType="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-soap-message-security-1.0#Base64Binary">
        <xop:Include href="cid:http%3A%2F%2Ftempuri.org%2F1%2F632618206525089430" xmlns:xop="http://www.w3.org/2004/08/xop/include"/>
      </o:BinarySecurityToken>
      <e:EncryptedKey Id="_1" xmlns:e="http://www.w3.org/2001/04/xmlenc#">
        <e:EncryptionMethod Algorithm="http://www.w3.org/2001/04/xmlenc#rsa-oaep-mgf1p"/>
        <KeyInfo xmlns="http://www.w3.org/2000/09/xmldsig#">
          <o:SecurityTokenReference>
            <o:KeyIdentifier ValueType="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-x509-token-profile-1.0#X509SubjectKeyIdentifier">Xeg55vRyK3ZhAEhEf+YT0z986L0=</o:KeyIdentifier>
          </o:SecurityTokenReference>
        </KeyInfo>
        <e:CipherData>          <e:CipherValue>oQfpxwT8/SAGyZQzKE2b4yO6dXuQj7pwJ+5CGL3Rf7C06bQ5ttMoQ9GLJcQYkXTzin+WwHEgs5bj5ml9HKTW9QAU5JJ6lksdymmQvWP5ZtGPBVchO4sofEGoCKmBiZL/DYS/cnbzgnc/3a6NYnc10y2fWGaGLiqa00zijAw7o0Y=</e:CipherValue>
        </e:CipherData>
      </e:EncryptedKey>
      <c:DerivedKeyToken u:Id="_2" xmlns:c="http://schemas.xmlsoap.org/ws/2005/02/sc">
        <o:SecurityTokenReference>
          <o:Reference URI="#_1"/>
        </o:SecurityTokenReference>
        <c:Nonce>OrEPRX7fISIS4sXYWPMv3g==</c:Nonce>
      </c:DerivedKeyToken>
      <e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#">
        <e:DataReference URI="#_3"/>
        <e:DataReference URI="#_4"/>
      </e:ReferenceList>
      <e:EncryptedData Id="_4" Type="http://www.w3.org/2001/04/xmlenc#Element" xmlns:e="http://www.w3.org/2001/04/xmlenc#">
        <e:EncryptionMethod Algorithm="http://www.w3.org/2001/04/xmlenc#aes256-cbc"/>
        <KeyInfo xmlns="http://www.w3.org/2000/09/xmldsig#">
          <o:SecurityTokenReference>
            <o:Reference URI="#_2"/>
          </o:SecurityTokenReference>
        </KeyInfo>
        <e:CipherData>
          <e:CipherValue>
            <xop:Include href="cid:http%3A%2F%2Ftempuri.org%2F2%2F632618206525089430" xmlns:xop="http://www.w3.org/2004/08/xop/include"/>
          </e:CipherValue>
        </e:CipherData>
      </e:EncryptedData>
    </o:Security>
  </s:Header>
  <s:Body u:Id="_0">
    <e:EncryptedData Id="_3" Type="http://www.w3.org/2001/04/xmlenc#Content" xmlns:e="http://www.w3.org/2001/04/xmlenc#">
      <e:EncryptionMethod Algorithm="http://www.w3.org/2001/04/xmlenc#aes256-cbc"/>
      <KeyInfo xmlns="http://www.w3.org/2000/09/xmldsig#">
        <o:SecurityTokenReference xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd">
          <o:Reference URI="#_2"/>
        </o:SecurityTokenReference>
      </KeyInfo>
      <e:CipherData>
        <e:CipherValue>
          <xop:Include href="cid:http%3A%2F%2Ftempuri.org%2F3%2F632618206525089430" xmlns:xop="http://www.w3.org/2004/08/xop/include"/>
        </e:CipherValue>
      </e:CipherData>
    </e:EncryptedData>
  </s:Body>
</s:Envelope>
--uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=3
Content-ID: <http://tempuri.org/1/632618206525089430>
Content-Transfer-Encoding: binary
Content-Type: application/octet-stream
...Binary content of BinarySecurityToken - X509 Certificate...
--uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=3
Content-ID: <http://tempuri.org/2/632618206525089430>
Content-Transfer-Encoding: binary
Content-Type: application/octet-stream
...Binary serialization of the encrypted primary signature...
--uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=3
Content-ID: <http://tempuri.org/3/632618206525089430>
Content-Transfer-Encoding: binary
Content-Type: application/octet-stream
...Binary serialization of the encrypted Body...
--uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=3--
```
