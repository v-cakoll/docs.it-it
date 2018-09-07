---
title: Protocolli di messaggistica
ms.date: 03/30/2017
ms.assetid: 5b20bca7-87b3-4c8f-811b-f215b5987104
ms.openlocfilehash: 3e56636e8364eec333f9585a0f62f6510561d1cc
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2018
ms.locfileid: "43868734"
---
# <a name="messaging-protocols"></a><span data-ttu-id="83fd4-102">Protocolli di messaggistica</span><span class="sxs-lookup"><span data-stu-id="83fd4-102">Messaging Protocols</span></span>
<span data-ttu-id="83fd4-103">Lo stack di canale Windows Communication Foundation (WCF) utilizza i canali di codifica e di trasporto per trasformare rappresentazioni interne dei messaggi in formato di trasmissione e inviarlo tramite un determinato trasporto.</span><span class="sxs-lookup"><span data-stu-id="83fd4-103">The Windows Communication Foundation (WCF) channel stack employs encoding and transport channels to transform internal message representation into its wire format and send it by using a particular transport.</span></span> <span data-ttu-id="83fd4-104">Il trasporto più comunemente utilizzato per garantire l'interoperabilità dei servizi Web è il protocollo HTTP, mentre le codifiche utilizzate dai servizi Web sono in genere SOAP 1.1 basato su XML, SOAP 1.2 e il protocollo MTOM (Message Transmission Optimization Mechanism, meccanismo di ottimizzazione della trasmissione dei messaggi).</span><span class="sxs-lookup"><span data-stu-id="83fd4-104">The most common transport used for Web services interoperability is HTTP, and the most common encodings used by Web services are XML-based SOAP 1.1, SOAP 1.2, and Message Transmission Optimization Mechanism (MTOM).</span></span>  
  
 <span data-ttu-id="83fd4-105">In questo argomento vengono descritti i dettagli di implementazione WCF per i protocolli seguenti usati da <xref:System.ServiceModel.Channels.HttpTransportBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="83fd4-105">This topic covers WCF implementation details for the following protocols employed by <xref:System.ServiceModel.Channels.HttpTransportBindingElement>.</span></span>  
  
|<span data-ttu-id="83fd4-106">Specifica/documento</span><span class="sxs-lookup"><span data-stu-id="83fd4-106">Specification/document</span></span>|<span data-ttu-id="83fd4-107">Collegamento</span><span class="sxs-lookup"><span data-stu-id="83fd4-107">Link</span></span>|  
|-----------------------------|----------|  
|<span data-ttu-id="83fd4-108">HTTP 1.1</span><span class="sxs-lookup"><span data-stu-id="83fd4-108">HTTP 1.1</span></span>|http://www.ietf.org/rfc/rfc2616.txt|  
|<span data-ttu-id="83fd4-109">Associazione SOAP 1,1 HTTP</span><span class="sxs-lookup"><span data-stu-id="83fd4-109">SOAP 1.1 HTTP Binding</span></span>|<span data-ttu-id="83fd4-110">http://www.w3.org/TR/2000/NOTE-SOAP-20000508/, Sezione 7</span><span class="sxs-lookup"><span data-stu-id="83fd4-110">http://www.w3.org/TR/2000/NOTE-SOAP-20000508/, Section 7</span></span>|  
|<span data-ttu-id="83fd4-111">Associazione SOAP 1,2 HTTP</span><span class="sxs-lookup"><span data-stu-id="83fd4-111">SOAP 1.2 HTTP Binding</span></span>|<span data-ttu-id="83fd4-112">http://www.w3.org/TR/soap12-part2/, Sezione 7</span><span class="sxs-lookup"><span data-stu-id="83fd4-112">http://www.w3.org/TR/soap12-part2/, Section 7</span></span>|  
  
 <span data-ttu-id="83fd4-113">In questo argomento vengono descritti i dettagli di implementazione di WCF per i seguenti protocolli <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement> e <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement> impiegare.</span><span class="sxs-lookup"><span data-stu-id="83fd4-113">This topic covers WCF implementation details for the following protocols  that <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement> and <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement> employ.</span></span>  
  
|<span data-ttu-id="83fd4-114">Specifica/documento</span><span class="sxs-lookup"><span data-stu-id="83fd4-114">Specification/Document</span></span>|<span data-ttu-id="83fd4-115">Collegamento</span><span class="sxs-lookup"><span data-stu-id="83fd4-115">Link</span></span>|  
|-----------------------------|----------|  
|<span data-ttu-id="83fd4-116">XML</span><span class="sxs-lookup"><span data-stu-id="83fd4-116">XML</span></span>|http://www.w3.org/TR/REC-xml|  
|<span data-ttu-id="83fd4-117">SOAP 1,1</span><span class="sxs-lookup"><span data-stu-id="83fd4-117">SOAP 1.1</span></span>|http://www.w3.org/TR/2000/NOTE-SOAP-20000508/|  
|<span data-ttu-id="83fd4-118">SOAP 1.2 Core</span><span class="sxs-lookup"><span data-stu-id="83fd4-118">SOAP 1.2 Core</span></span>|http://www.w3.org/TR/soap12-part1/|  
|<span data-ttu-id="83fd4-119">WS-Addressing 2004/08</span><span class="sxs-lookup"><span data-stu-id="83fd4-119">WS-Addressing 2004/08</span></span>|http://www.w3.org/Submission/2004/SUBM-ws-addressing-20040810/|  
|<span data-ttu-id="83fd4-120">W3C Web Services Addressing 1.0 - Core</span><span class="sxs-lookup"><span data-stu-id="83fd4-120">W3C Web Services Addressing 1.0 - Core</span></span>|http://www.w3.org/TR/2006/REC-ws-addr-core-20060509|  
|<span data-ttu-id="83fd4-121">W3C Web Services Addressing 1.0 - SOAP Binding</span><span class="sxs-lookup"><span data-stu-id="83fd4-121">W3C Web Services Addressing 1.0 - SOAP Binding</span></span>|http://www.w3.org/TR/2006/REC-ws-addr-soap-20060509|  
|<span data-ttu-id="83fd4-122">W3C Web Services Addressing 1.0 con associazione WSDL</span><span class="sxs-lookup"><span data-stu-id="83fd4-122">W3C Web Services Addressing 1.0 - WSDL Binding</span></span>|http://www.w3.org/TR/2006/CR-ws-addr-wsdl-20060529/|  
<span data-ttu-id="83fd4-123">W3C Web Services Addressing 1.0 - Metadata</span><span class="sxs-lookup"><span data-stu-id="83fd4-123">W3C Web Services Addressing 1.0 - Metadata</span></span>|http://www.w3.org/TR/ws-addr-metadata/|  
|<span data-ttu-id="83fd4-124">Associazione WSDL SOAP1.1</span><span class="sxs-lookup"><span data-stu-id="83fd4-124">WSDL SOAP1.1 Binding</span></span>|http://www.w3.org/TR/wsdl/|  
|<span data-ttu-id="83fd4-125">Associazione WSDL SOAP1.2</span><span class="sxs-lookup"><span data-stu-id="83fd4-125">WSDL SOAP1.2 Binding</span></span>|http://www.w3.org/Submission/wsdl11soap12/|  
  
 <span data-ttu-id="83fd4-126">In questo argomento vengono descritti i dettagli di implementazione di WCF per i seguenti protocolli <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement> impiega.</span><span class="sxs-lookup"><span data-stu-id="83fd4-126">This topic covers WCF implementation details for the following protocols that <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement> employs.</span></span>  
  
|<span data-ttu-id="83fd4-127">Specifica/documento</span><span class="sxs-lookup"><span data-stu-id="83fd4-127">Specification/document</span></span>|<span data-ttu-id="83fd4-128">Collegamento</span><span class="sxs-lookup"><span data-stu-id="83fd4-128">Link</span></span>|  
|-----------------------------|----------|  
|<span data-ttu-id="83fd4-129">XOP</span><span class="sxs-lookup"><span data-stu-id="83fd4-129">XOP</span></span>|http://www.w3.org/TR/xop10/|  
|<span data-ttu-id="83fd4-130">Associazione MTOM SOAP 1.2</span><span class="sxs-lookup"><span data-stu-id="83fd4-130">MTOM + SOAP 1.2 Binding</span></span>|http://www.w3.org/TR/soap12-mtom/|  
|<span data-ttu-id="83fd4-131">Associazione MTOM SOAP 1.1</span><span class="sxs-lookup"><span data-stu-id="83fd4-131">MTOM SOAP 1.1 Binding</span></span>|http://www.w3.org/Submission/soap11mtom10/|  
|<span data-ttu-id="83fd4-132">Asserzione di WS-Policy relativa a MTOM</span><span class="sxs-lookup"><span data-stu-id="83fd4-132">MTOM WS-Policy Assertion</span></span>|<span data-ttu-id="83fd4-133">http://www.w3.org/Submission/2006/SUBM-WS-MTOMPolicy-20061101/.</span><span class="sxs-lookup"><span data-stu-id="83fd4-133">http://www.w3.org/Submission/2006/SUBM-WS-MTOMPolicy-20061101/.</span></span>|  
  
 <span data-ttu-id="83fd4-134">In questo argomento vengono utilizzati gli spazi dei nomi XML e i relativi prefissi associati seguenti.</span><span class="sxs-lookup"><span data-stu-id="83fd4-134">The following XML namespaces and associated prefixes are used throughout this topic.</span></span>  
  
|<span data-ttu-id="83fd4-135">Prefisso</span><span class="sxs-lookup"><span data-stu-id="83fd4-135">Prefix</span></span>|<span data-ttu-id="83fd4-136">URI (Uniform Resource Identifier) dello spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="83fd4-136">Namespace Uniform Resource Identifier (URI)</span></span>|  
|------------|---------------------------------------------------|  
|<span data-ttu-id="83fd4-137">s11</span><span class="sxs-lookup"><span data-stu-id="83fd4-137">s11</span></span>|http://schemas.xmlsoap.org/soap/envelope|  
|<span data-ttu-id="83fd4-138">s12</span><span class="sxs-lookup"><span data-stu-id="83fd4-138">s12</span></span>|http://www.w3.org/2003/05/soap-envelope|  
|<span data-ttu-id="83fd4-139">wsa</span><span class="sxs-lookup"><span data-stu-id="83fd4-139">wsa</span></span>|http://www.w3.org/2004/08/addressing|  
|<span data-ttu-id="83fd4-140">wsam</span><span class="sxs-lookup"><span data-stu-id="83fd4-140">wsam</span></span>|http://www.w3.org/2007/05/addressing/metadata|  
|<span data-ttu-id="83fd4-141">wsap</span><span class="sxs-lookup"><span data-stu-id="83fd4-141">wsap</span></span>|http://schemas.xmlsoap.org/ws/2004/09/policy/addressing|  
|<span data-ttu-id="83fd4-142">wsa10</span><span class="sxs-lookup"><span data-stu-id="83fd4-142">wsa10</span></span>|http://www.w3.org/2005/08/addressing|  
|<span data-ttu-id="83fd4-143">wsaw10</span><span class="sxs-lookup"><span data-stu-id="83fd4-143">wsaw10</span></span>|http://www.w3.org/2006/05/addressing/wsdl|  
|<span data-ttu-id="83fd4-144">xop</span><span class="sxs-lookup"><span data-stu-id="83fd4-144">xop</span></span>|http://www.w3.org/2004/08/xop/include|  
|<span data-ttu-id="83fd4-145">xmime</span><span class="sxs-lookup"><span data-stu-id="83fd4-145">xmime</span></span>|http://www.w3.org/2004/06/xmlmime<br /><br /> http://www.w3.org/2005/05/xmlmime|  
<span data-ttu-id="83fd4-146">punto di distribuzione</span><span class="sxs-lookup"><span data-stu-id="83fd4-146">dp</span></span>|http://schemas.microsoft.com/net/2006/06/duplex|  
  
## <a name="soap-11-and-soap-12"></a><span data-ttu-id="83fd4-147">SOAP 1.1 e SOAP 1.2</span><span class="sxs-lookup"><span data-stu-id="83fd4-147">SOAP 1.1 and SOAP 1.2</span></span>  
  
### <a name="envelope-and-processing-model"></a><span data-ttu-id="83fd4-148">Modello di elaborazione della envelope</span><span class="sxs-lookup"><span data-stu-id="83fd4-148">Envelope and Processing Model</span></span>  
 <span data-ttu-id="83fd4-149">WCF implementa l'elaborazione di envelope di SOAP 1.1 seguendo Basic Profile 1.1 (BP11) e Basic Profile 1.0 (SSBP10).</span><span class="sxs-lookup"><span data-stu-id="83fd4-149">WCF implements SOAP 1.1 envelope processing following Basic Profile 1.1 (BP11) and Basic Profile 1.0 (SSBP10).</span></span> <span data-ttu-id="83fd4-150">L'elaborazione della SOAP 1.2 envelope viene implementata attenendosi alla specifica SOAP12-Part1.</span><span class="sxs-lookup"><span data-stu-id="83fd4-150">SOAP 1.2 Envelope processing is implemented following SOAP12-Part1.</span></span>  
  
 <span data-ttu-id="83fd4-151">Questa sezione illustra alcune scelte di implementazione da WCF in relazione alle specifiche BP11 e SOAP12-Part1.</span><span class="sxs-lookup"><span data-stu-id="83fd4-151">This section explains certain implementation choices taken by WCF with regard to BP11 and SOAP12-Part1.</span></span>  
  
#### <a name="mandatory-header-processing"></a><span data-ttu-id="83fd4-152">Elaborazione obbligatoria delle intestazioni</span><span class="sxs-lookup"><span data-stu-id="83fd4-152">Mandatory Header Processing</span></span>  
 <span data-ttu-id="83fd4-153">WCF segue le regole per l'elaborazione di intestazioni contrassegnate `mustUnderstand` descritto nelle specifiche SOAP 1.1 e SOAP 1.2, con le variazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="83fd4-153">WCF follows rules for processing headers marked `mustUnderstand` described in the SOAP 1.1 and SOAP 1.2 specifications, with the following variations.</span></span>  
  
 <span data-ttu-id="83fd4-154">Un messaggio che viene inserito lo stack dei canali WCF viene elaborato da canali specifici configurati in base agli elementi di associazione associata, ad esempio, codifica del messaggio di testo, sicurezza, messaggistica affidabile e le transazioni.</span><span class="sxs-lookup"><span data-stu-id="83fd4-154">A message that enters the WCF channel stack is processed by individual channels configured by associated binding elements, for example, Text Message Encoding, Security, Reliable Messaging, and Transactions.</span></span> <span data-ttu-id="83fd4-155">Ogni canale riconosce le intestazioni dallo spazio dei nomi associato e le contrassegna come riconosciute.</span><span class="sxs-lookup"><span data-stu-id="83fd4-155">Each channel recognizes headers from the associated namespace and marks them as understood.</span></span> <span data-ttu-id="83fd4-156">Dopo l'inserimento di un messaggio nel dispatcher, il formattatore dell'operazione legge le intestazioni previste dal contratto di messaggio/operazione corrispondente e le contrassegna come riconosciute.</span><span class="sxs-lookup"><span data-stu-id="83fd4-156">Once a message enters the dispatcher, the operation formatter reads headers expected by the corresponding message/operation contract and marks them understood.</span></span> <span data-ttu-id="83fd4-157">Quindi, il dispatcher verifica se esistono intestazioni non riconosciute ma la cui intestazione `mustUnderstand` richiede il riconoscimento e, in tal caso, genera un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="83fd4-157">Then the dispatcher verifies whether any remaining headers are not understood but marked as `mustUnderstand` and throws an exception.</span></span> <span data-ttu-id="83fd4-158">I messaggi che contengono intestazioni `mustUnderstand` indirizzate al destinatario non vengono elaborati dal codice dell'applicazione di destinazione.</span><span class="sxs-lookup"><span data-stu-id="83fd4-158">Messages that contain `mustUnderstand` headers that are targeted at the recipient are not processed by recipient application code.</span></span>  
  
 <span data-ttu-id="83fd4-159">Questo tipo di elaborazione a livelli consente la separazione fra i livelli di infrastruttura e livelli di applicazione del nodo SOAP:</span><span class="sxs-lookup"><span data-stu-id="83fd4-159">Such layered processing allows for separation between infrastructure layers and application layers of the SOAP node:</span></span>  
  
-   <span data-ttu-id="83fd4-160">B1111: Le intestazioni non riconosciute vengono rilevate dopo che il messaggio viene elaborato dallo stack dei canali WCF dell'infrastruttura, ma prima che venga elaborato dall'applicazione</span><span class="sxs-lookup"><span data-stu-id="83fd4-160">B1111: Headers that are not understood are detected after the message is processed by the WCF infrastructure channel stack, but before it is processed by application</span></span>  
  
     <span data-ttu-id="83fd4-161">Il valore dell'intestazione `mustUnderstand` differisce tra SOAP 1.1 e SOAP 1.2.</span><span class="sxs-lookup"><span data-stu-id="83fd4-161">The `mustUnderstand` header value differs between SOAP 1.1 and SOAP 1.2.</span></span> <span data-ttu-id="83fd4-162">Basic Profile 1.1 richiede che il valore di `mustUnderstand` sia 0 o 1 per i messaggi SOAP 1.1.</span><span class="sxs-lookup"><span data-stu-id="83fd4-162">Basic Profile 1.1 requires that the `mustUnderstand` value be 0 or 1 for SOAP 1.1 messages.</span></span> <span data-ttu-id="83fd4-163">La specifica di SOAP 1.2, oltre ai valori 0 e 1, prevede inoltre i valori `false` e `true`. Tuttavia, tale specifica consiglia di applicare una rappresentazione canonica dei valori `xs:boolean`, ovvero `false` e `true`.</span><span class="sxs-lookup"><span data-stu-id="83fd4-163">SOAP 1.2 allows 0, 1, `false`, and `true` as values, but recommends emitting a canonical representation of `xs:boolean` values (`false`, `true`).</span></span>  
  
-   <span data-ttu-id="83fd4-164">B1112: WCF genera `mustUnderstand` valori 0 e 1 per le versioni sia di SOAP 1.1 e SOAP 1.2 della SOAP envelope.</span><span class="sxs-lookup"><span data-stu-id="83fd4-164">B1112: WCF emits `mustUnderstand` values 0 and 1 for both SOAP 1.1 and SOAP 1.2 versions of the SOAP envelope.</span></span> <span data-ttu-id="83fd4-165">WCF accetta l'intero spazio dei valori `xs:boolean` per il `mustUnderstand` intestazione (0, 1, `false`, `true`)</span><span class="sxs-lookup"><span data-stu-id="83fd4-165">WCF accepts the entire value space of `xs:boolean` for the `mustUnderstand` header (0, 1, `false`, `true`)</span></span>  
  
#### <a name="soap-faults"></a><span data-ttu-id="83fd4-166">Errori SOAP</span><span class="sxs-lookup"><span data-stu-id="83fd4-166">SOAP Faults</span></span>  
 <span data-ttu-id="83fd4-167">Di seguito è un elenco delle implementazioni di errore SOAP WCF specifico.</span><span class="sxs-lookup"><span data-stu-id="83fd4-167">The following is a list of WCF-specific SOAP fault implementations.</span></span>  
  
-   <span data-ttu-id="83fd4-168">B2121: WCF restituisce i seguenti codici di errore SOAP 1.1: `s11:mustUnderstand`, `s11:Client`, e `s11:Server`.</span><span class="sxs-lookup"><span data-stu-id="83fd4-168">B2121: WCF returns the following SOAP 1.1 Fault Codes: `s11:mustUnderstand`, `s11:Client`, and `s11:Server`.</span></span>  
  
-   <span data-ttu-id="83fd4-169">B2122: Poiché WCF restituisce i seguenti codici di errore SOAP 1.2: `s12:MustUnderstand`, `s12:Sender`, e `s12:Receiver`.</span><span class="sxs-lookup"><span data-stu-id="83fd4-169">B2122: WCF returns the following SOAP 1.2 Fault Codes: `s12:MustUnderstand`, `s12:Sender`, and `s12:Receiver`.</span></span>  
  
### <a name="http-binding"></a><span data-ttu-id="83fd4-170">Associazione HTTP</span><span class="sxs-lookup"><span data-stu-id="83fd4-170">HTTP Binding</span></span>  
  
#### <a name="soap-11-http-binding"></a><span data-ttu-id="83fd4-171">Associazione SOAP 1,1 HTTP</span><span class="sxs-lookup"><span data-stu-id="83fd4-171">SOAP 1.1 HTTP Binding</span></span>  
 <span data-ttu-id="83fd4-172">WCF implementa associazione SOAP 1.1 HTTP dopo la specifica Basic Profile 1.1 sezione 3.4 con le precisazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="83fd4-172">WCF implements SOAP1.1 HTTP binding following the Basic Profile 1.1 specification section 3.4 with the following clarifications:</span></span>  
  
-   <span data-ttu-id="83fd4-173">B2211: Il servizio WCF non implementa il reindirizzamento delle richieste HTTP POST.</span><span class="sxs-lookup"><span data-stu-id="83fd4-173">B2211: WCF service does not implement redirection of HTTP POST requests.</span></span>  
  
-   <span data-ttu-id="83fd4-174">B2212: I client WCF supportano i cookie HTTP in conformità alla sezione 3.4.8.</span><span class="sxs-lookup"><span data-stu-id="83fd4-174">B2212: WCF clients support HTTP Cookies in accordance with 3.4.8.</span></span>  
  
#### <a name="soap-12-http-binding"></a><span data-ttu-id="83fd4-175">Associazione SOAP 1,2 HTTP</span><span class="sxs-lookup"><span data-stu-id="83fd4-175">SOAP 1.2 HTTP Binding</span></span>  
 <span data-ttu-id="83fd4-176">WCF implementa l'associazione SOAP 1.2 HTTP come descritto nella SOAP 1.2-part 2 (SOAP12Part2) specifica con le precisazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="83fd4-176">WCF implements SOAP 1.2 HTTP binding as described in the SOAP 1.2-part 2 (SOAP12Part2) specification with the following clarifications.</span></span>  
  
 <span data-ttu-id="83fd4-177">SOAP 1.2 introduce un nuovo parametro Action facoltativo per il tipo di supporto `application/soap+xml`.</span><span class="sxs-lookup"><span data-stu-id="83fd4-177">SOAP 1.2 introduced an optional action parameter for the `application/soap+xml` media type.</span></span> <span data-ttu-id="83fd4-178">Questo parametro è utile per ottimizzare l'invio dei messaggi in quanto elimina l'esigenza di analizzare il corpo del messaggio SOAP quando non si utilizza la specifica WS-Addressing.</span><span class="sxs-lookup"><span data-stu-id="83fd4-178">This parameter is useful to optimize message dispatch without requiring that the body of the SOAP message be parsed when WS-Addressing is not used.</span></span>  
  
-   <span data-ttu-id="83fd4-179">R2221: il parametro Action `application/soap+xml`, quando presente in una richiesta SOAP 1.2, deve corrispondere all'attributo `soapAction` dell'elemento `wsoap12:operation` contenuto nell'associazione WSDL corrispondente.</span><span class="sxs-lookup"><span data-stu-id="83fd4-179">R2221: The `application/soap+xml` action parameter, when present on a SOAP 1.2 request, must match the `soapAction` attribute on the `wsoap12:operation` element inside the corresponding WSDL binding.</span></span>  
  
-   <span data-ttu-id="83fd4-180">R2222: il parametro Action `application/soap+xml`, quando presente in un messaggio SOAP 1.2, deve corrispondere all'elemento `wsa:Action` quando si utilizza la specifica WS-Addressing 2004/08 o la specifica WS-Addressing 1.0.</span><span class="sxs-lookup"><span data-stu-id="83fd4-180">R2222: The `application/soap+xml` action parameter, when present on a SOAP 1.2 message, must match `wsa:Action` when WS-Addressing 2004/08 or WS-Addressing 1.0 are used.</span></span>  
  
 <span data-ttu-id="83fd4-181">Quando la specifica WS-Addressing è disabilitata e in una richiesta in ingresso non è incluso alcun parametro Action, il parametro `Action` del messaggio viene considerato come non specificato.</span><span class="sxs-lookup"><span data-stu-id="83fd4-181">When WS-Addressing is disabled and an incoming request does not contain an action parameter, message `Action` is considered not specified.</span></span>  
  
## <a name="ws-addressing"></a><span data-ttu-id="83fd4-182">WS-Addressing</span><span class="sxs-lookup"><span data-stu-id="83fd4-182">WS-Addressing</span></span>  
 <span data-ttu-id="83fd4-183">WCF di implementare 3 versioni di WS-Addressing:</span><span class="sxs-lookup"><span data-stu-id="83fd4-183">WCF implements 3 versions of WS-Addressing:</span></span>  
  
-   <span data-ttu-id="83fd4-184">WS-Addressing 2004/08</span><span class="sxs-lookup"><span data-stu-id="83fd4-184">WS-Addressing 2004/08</span></span>  
  
-   <span data-ttu-id="83fd4-185">Specifica di base di W3C Web Services Addressing 1.0 (ADDR10-CORE) e associazione SOAP (ADDR10-SOAP)</span><span class="sxs-lookup"><span data-stu-id="83fd4-185">W3C Web Services Addressing 1.0 Core  (ADDR10-CORE) and SOAP Binding (ADDR10-SOAP)</span></span>  
  
-   <span data-ttu-id="83fd4-186">WS-Addressing 1.0 - Metadata</span><span class="sxs-lookup"><span data-stu-id="83fd4-186">WS-Addressing 1.0 - Metadata</span></span>  
  
### <a name="endpoint-references"></a><span data-ttu-id="83fd4-187">Riferimenti a endpoint</span><span class="sxs-lookup"><span data-stu-id="83fd4-187">Endpoint References</span></span>  
 <span data-ttu-id="83fd4-188">Tutte le versioni di WS-Addressing che WCF implementa usano riferimenti a endpoint per descrivere gli endpoint.</span><span class="sxs-lookup"><span data-stu-id="83fd4-188">All versions of WS-Addressing that WCF implements use endpoint references to describe endpoints.</span></span>  
  
#### <a name="endpoint-references-and-ws-addressing-versions"></a><span data-ttu-id="83fd4-189">Utilizzo dei riferimenti a endpoint con le versioni di WS-Addressing</span><span class="sxs-lookup"><span data-stu-id="83fd4-189">Endpoint References and WS-Addressing Versions</span></span>  
 <span data-ttu-id="83fd4-190">WCF implementa diversi protocolli di infrastruttura che utilizzano WS-Addressing e in particolare il `EndpointReference` elemento e `W3C.WsAddressing.EndpointReferenceType` classe (ad esempio, WS-ReliableMessaging WS-SecureConversation e WS-Trust).</span><span class="sxs-lookup"><span data-stu-id="83fd4-190">WCF implements a number of the infrastructure protocols that use WS-Addressing and in particular the `EndpointReference` element and `W3C.WsAddressing.EndpointReferenceType` class (for example, WS-ReliableMessaging, WS-SecureConversation, and WS-Trust).</span></span> <span data-ttu-id="83fd4-191">WCF supporta l'utilizzo di entrambe le versioni di WS-Addressing con gli altri protocolli di infrastruttura.</span><span class="sxs-lookup"><span data-stu-id="83fd4-191">WCF supports the use of either version of WS-Addressing with other infrastructure protocols.</span></span> <span data-ttu-id="83fd4-192">Gli endpoint WCF supportano una versione di WS-Addressing per ogni endpoint.</span><span class="sxs-lookup"><span data-stu-id="83fd4-192">WCF endpoints support one version of WS-Addressing per endpoint.</span></span>  
  
 <span data-ttu-id="83fd4-193">R3111: lo spazio dei nomi per il `EndpointReference` elemento o del tipo utilizzato nei messaggi scambiati con un endpoint WCF deve corrispondere alla versione di WS-Addressing implementata da questo endpoint.</span><span class="sxs-lookup"><span data-stu-id="83fd4-193">For R3111, the namespace for the `EndpointReference` element or type used in messages exchanged with a WCF endpoint must match the version of WS-Addressing implemented by this endpoint.</span></span>  
  
 <span data-ttu-id="83fd4-194">Ad esempio, se un endpoint WCF implementa WS-ReliableMessaging, il `AcksTo` intestazione restituita da tale endpoint all'interno `CreateSequenceResponse` Usa la versione di WS-Addressing che il `EncodingBinding` elemento specifica per questo endpoint.</span><span class="sxs-lookup"><span data-stu-id="83fd4-194">For example, if a WCF endpoint implements WS-ReliableMessaging, the `AcksTo` header returned by such an endpoint inside `CreateSequenceResponse` uses the WS-Addressing version that the `EncodingBinding` element specifies for this endpoint.</span></span>  
  
#### <a name="endpoint-references-and-metadata"></a><span data-ttu-id="83fd4-195">Utilizzo dei riferimenti a endpoint con i metadati</span><span class="sxs-lookup"><span data-stu-id="83fd4-195">Endpoint References and Metadata</span></span>  
 <span data-ttu-id="83fd4-196">Diversi scenari richiedono la comunicazione di metadati o di riferimenti a metadati relativi a un dato endpoint.</span><span class="sxs-lookup"><span data-stu-id="83fd4-196">A number of scenarios require communicating metadata or a reference to metadata for a given endpoint.</span></span>  
  
 <span data-ttu-id="83fd4-197">B3121: WCF utilizza i meccanismi descritti nella sezione 6 di includere i metadati per i riferimenti all'endpoint per valore o per riferimento specifica WS-MetadataExchange (MEX).</span><span class="sxs-lookup"><span data-stu-id="83fd4-197">B3121: WCF employs mechanisms described in the WS-MetadataExchange (MEX) specification Section 6 to include metadata for endpoint references by value or by reference.</span></span>  
  
 <span data-ttu-id="83fd4-198">Si consideri uno scenario in cui un servizio WCF richiede l'autenticazione tramite un token Security Assertions Markup Language (SAML) emesso dall'emittente del token a http://sts.fabrikam123.com.</span><span class="sxs-lookup"><span data-stu-id="83fd4-198">Consider a scenario where a WCF service requires authentication using a Security Assertions Markup Language (SAML) token issued by the token issuer at http://sts.fabrikam123.com.</span></span> <span data-ttu-id="83fd4-199">L'endpoint WCF descrive questo requisito di autenticazione utilizzando `sp:IssuedToken` asserzione con nidificato `sp:Issuer` asserzione che punta all'emittente del token.</span><span class="sxs-lookup"><span data-stu-id="83fd4-199">The WCF endpoint describes this authentication requirement by using `sp:IssuedToken` assertion with a nested `sp:Issuer` assertion pointing to the token issuer.</span></span> <span data-ttu-id="83fd4-200">Le applicazioni client che accedono all'asserzione `sp:Issuer` devono conoscere la modalità di comunicazione con l'endpoint dell'emittente di token.</span><span class="sxs-lookup"><span data-stu-id="83fd4-200">Client applications that access the `sp:Issuer` assertion need to know how to communicate with the token issuer endpoint.</span></span> <span data-ttu-id="83fd4-201">In particolare, il client deve conoscere i metadati relativi all'emittente di token.</span><span class="sxs-lookup"><span data-stu-id="83fd4-201">The client needs to know metadata about the token issuer.</span></span> <span data-ttu-id="83fd4-202">Usa le estensioni dei metadati di riferimento endpoint definite nel MEX, WCF fornisce un riferimento ai metadati dell'emittente del token.</span><span class="sxs-lookup"><span data-stu-id="83fd4-202">Using the endpoint reference metadata extensions defined in MEX, WCF provides a reference to the token issuer metadata.</span></span>  
  
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
  
### <a name="message-addressing-headers"></a><span data-ttu-id="83fd4-203">Intestazioni di indirizzamento dei messaggi</span><span class="sxs-lookup"><span data-stu-id="83fd4-203">Message Addressing Headers</span></span>  
  
#### <a name="message-headers"></a><span data-ttu-id="83fd4-204">Intestazioni del messaggio</span><span class="sxs-lookup"><span data-stu-id="83fd4-204">Message Headers</span></span>  
 <span data-ttu-id="83fd4-205">Per entrambe le versioni di WS-Addressing, WCF Usa le seguenti intestazioni del messaggio come previsto dalle specifiche `wsa:To`, `wsa:ReplyTo`, `wsa:Action`, `wsa:MessageID`, e `wsa:RelatesTo`.</span><span class="sxs-lookup"><span data-stu-id="83fd4-205">For both WS-Addressing versions, WCF uses the following message headers as prescribed by the specifications `wsa:To`, `wsa:ReplyTo`, `wsa:Action`, `wsa:MessageID`,and `wsa:RelatesTo`.</span></span>  
  
 <span data-ttu-id="83fd4-206">B3211: Per tutte le versioni di WS-Addressing, WCF rispetta, ma non viene generato per impostazione predefinita, le intestazioni dei messaggi WS-Addressing `wsa:FaultTo` e `wsa:From`.</span><span class="sxs-lookup"><span data-stu-id="83fd4-206">B3211: For all WS-Addressing versions, WCF honors, but does not produce out of the box, WS-Addressing message headers `wsa:FaultTo` and `wsa:From`.</span></span>  
  
 <span data-ttu-id="83fd4-207">Le applicazioni che interagiscono con le applicazioni WCF possono aggiungere che queste intestazioni del messaggio e WCF verranno elaborate di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="83fd4-207">Applications that interact with WCF applications can add these message headers and WCF will process them accordingly.</span></span>  
  
#### <a name="reference-parameters-and-properties"></a><span data-ttu-id="83fd4-208">Parametri per riferimento e proprietà dei riferimenti</span><span class="sxs-lookup"><span data-stu-id="83fd4-208">Reference Parameters and Properties</span></span>  
 <span data-ttu-id="83fd4-209">WCF implementa l'elaborazione dei parametri di riferimento dell'endpoint e riferimento p</span><span class="sxs-lookup"><span data-stu-id="83fd4-209">WCF implements processing of endpoint reference parameters and reference p</span></span>  
  
 <span data-ttu-id="83fd4-210">in conformità alle rispettive specifiche.</span><span class="sxs-lookup"><span data-stu-id="83fd4-210">roperties in accordance with respective specifications.</span></span>  
  
 <span data-ttu-id="83fd4-211">B3221: Quando configurato per usare WS-Addressing 2004/08, gli endpoint WCF viene fatta distinzione tra l'elaborazione delle proprietà di riferimento e i parametri per riferimento.</span><span class="sxs-lookup"><span data-stu-id="83fd4-211">B3221: When configured to use WS-Addressing 2004/08, WCF endpoints do not differentiate between processing Reference Properties and Reference Parameters.</span></span>  
  
### <a name="message-exchange-patterns"></a><span data-ttu-id="83fd4-212">Modelli di scambio dei messaggi</span><span class="sxs-lookup"><span data-stu-id="83fd4-212">Message Exchange Patterns</span></span>  
 <span data-ttu-id="83fd4-213">La sequenza dei messaggi coinvolti nella chiamata di operazione del servizio Web è detta il *modello di scambio messaggi*.</span><span class="sxs-lookup"><span data-stu-id="83fd4-213">The sequence of messages involved in the Web service operation invocation is referred to as the *message exchange pattern*.</span></span> <span data-ttu-id="83fd4-214">I modelli di scambio di messaggi duplex WCF supporta unidirezionali e request / reply.</span><span class="sxs-lookup"><span data-stu-id="83fd4-214">WCF supports one-way, request-reply, and duplex message exchange patterns.</span></span> <span data-ttu-id="83fd4-215">Questa sezione descrive i requisiti della specifica WS-Addressing che definiscono il modo in cui il modello di scambio dei messaggi usato influisce sull'elaborazione dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="83fd4-215">This section clarifies WS-Addressing requirements on message processing depending on the message exchange pattern being used.</span></span>  
  
 <span data-ttu-id="83fd4-216">Contenuto della sezione, il richiedente invia il primo messaggio e il risponditore riceve il primo messaggio.</span><span class="sxs-lookup"><span data-stu-id="83fd4-216">Throughout this section, the requester sends the first message and the responder receives the first message.</span></span>  
  
#### <a name="one-way-message"></a><span data-ttu-id="83fd4-217">Modello unidirezionale</span><span class="sxs-lookup"><span data-stu-id="83fd4-217">One-Way Message</span></span>  
 <span data-ttu-id="83fd4-218">Quando un endpoint WCF è configurato per supportare messaggi aventi un determinato `Action` per seguire un modello unidirezionale, l'endpoint WCF segue i seguenti comportamenti e requisiti.</span><span class="sxs-lookup"><span data-stu-id="83fd4-218">When a WCF endpoint is configured to support messages with a given `Action` to follow a one-way pattern, the WCF endpoint follows the following behaviors and requirements.</span></span> <span data-ttu-id="83fd4-219">Salvo diversamente specificato, per entrambe le versioni di WS-Addressing supportate in WCF si applicano i comportamenti e le regole:</span><span class="sxs-lookup"><span data-stu-id="83fd4-219">Unless otherwise specified, behaviors and rules apply for both versions of WS-Addressing supported in WCF:</span></span>  
  
-   <span data-ttu-id="83fd4-220">R3311: il richiedente deve includere gli elementi `wsa:To` e `wsa:Action` nonché le intestazioni di tutti i parametri specificati nel riferimento a endpoint.</span><span class="sxs-lookup"><span data-stu-id="83fd4-220">R3311: The requester must include `wsa:To`, `wsa:Action`, and headers for all reference parameters specified by the endpoint reference.</span></span> <span data-ttu-id="83fd4-221">Quando si utilizza la specifica WS-Addressing 2004/08 e il riferimento a endpoint specifica le proprietà di riferimento [reference properties], occorre aggiungere al messaggio anche le intestazioni corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="83fd4-221">When WS-Addressing 2004/08 is used and [reference properties] are specified by the endpoint reference, the corresponding headers must be added to the message too.</span></span>  
  
-   <span data-ttu-id="83fd4-222">B3312: il richiedente può includere le intestazioni `MessageID` e `ReplyTo` e `FaultTo`.</span><span class="sxs-lookup"><span data-stu-id="83fd4-222">B3312: The requester may include `MessageID`, `ReplyTo`, and `FaultTo` headers.</span></span> <span data-ttu-id="83fd4-223">Dopo essere stati ignorati dall'infrastruttura del destinatario, questi elementi vengono passati all'applicazione.</span><span class="sxs-lookup"><span data-stu-id="83fd4-223">The receiver infrastructure will ignore them, and they will be passed to the application.</span></span>  
  
-   <span data-ttu-id="83fd4-224">R3313: quando si utilizza il protocollo HTTP e non viene inviato alcun messaggio sul canale di risposta HTTP, il risponditore deve inviare una risposta HTTP contenente un corpo vuoto e un codice di stato HTTP 202.</span><span class="sxs-lookup"><span data-stu-id="83fd4-224">R3313: When HTTP is used and no message is being sent on the HTTP response leg, the responder must send an HTTP response with an empty body and an HTTP 202 status code.</span></span>  
  
     <span data-ttu-id="83fd4-225">Quando si utilizza il trasporto HTTP e il contratto dell'operazione dichiara un messaggio unidirezionale, la risposta HTTP può comunque essere utilizzata per l'invio di messaggi di infrastruttura. Ad esempio, la funzionalità di messaggistica affidabile può inviare un messaggio `SequenceAcknowledgement` in una risposta HTTP.</span><span class="sxs-lookup"><span data-stu-id="83fd4-225">When the HTTP transport is in use and the operation contract declares a message one-way, the HTTP response can still be used for sending infrastructure messages—for example, reliable messaging can send a `SequenceAcknowledgement` message on an HTTP response.</span></span>  
  
-   <span data-ttu-id="83fd4-226">B3314: Il risponditore WCF non invia un messaggio di errore in risposta a un messaggio unidirezionale.</span><span class="sxs-lookup"><span data-stu-id="83fd4-226">B3314: The WCF responder does not send a fault message in response to a one-way message.</span></span>  
  
#### <a name="request-reply"></a><span data-ttu-id="83fd4-227">Request/Reply</span><span class="sxs-lookup"><span data-stu-id="83fd4-227">Request-Reply</span></span>  
 <span data-ttu-id="83fd4-228">Quando un endpoint WCF è configurato per un messaggio con un determinato `Action` per seguire il modello request / reply, l'endpoint WCF attiene ai comportamenti e requisiti riportati di seguito.</span><span class="sxs-lookup"><span data-stu-id="83fd4-228">When a WCF endpoint is configured for a message with a given `Action` to follow the request-reply pattern, the WCF endpoint follows the behaviors and requirements below.</span></span> <span data-ttu-id="83fd4-229">Se non specificato diversamente, si applicano le regole e i comportamenti per entrambe le versioni di WS-Addressing supportate in WCF:</span><span class="sxs-lookup"><span data-stu-id="83fd4-229">Unless specified otherwise, behaviors and rules apply for both versions of WS-Addressing supported in WCF:</span></span>  
  
-   <span data-ttu-id="83fd4-230">R3321: Il richiedente deve includere nella richiesta `wsa:To`, `wsa:Action`, `wsa:MessageID`e le intestazioni per tutti i parametri per riferimento oppure riferimento proprietà (o entrambi) specificati nel riferimento a endpoint.</span><span class="sxs-lookup"><span data-stu-id="83fd4-230">R3321: The requester must include in the request `wsa:To`, `wsa:Action`, `wsa:MessageID`, and headers for all reference parameters or reference properties (or both) specified by the endpoint reference.</span></span>  
  
-   <span data-ttu-id="83fd4-231">R3322: quando si utilizza la specifica WS-Addressing 2004/08, nella richiesta deve essere incluso anche l'elemento `ReplyTo`.</span><span class="sxs-lookup"><span data-stu-id="83fd4-231">R3322: When WS-Addressing 2004/08 is used, `ReplyTo` must also be included in the request.</span></span>  
  
-   <span data-ttu-id="83fd4-232">R3323: Quando si utilizza WS-Addressing 1.0 e `ReplyTo` non è presente nella richiesta, un riferimento all'endpoint predefinito con la proprietà [address] uguale a "http://www.w3.org/2005/08/addressing/anonymous" viene usato.</span><span class="sxs-lookup"><span data-stu-id="83fd4-232">R3323: When WS-Addressing 1.0 is used and `ReplyTo` is not present in the request, a default endpoint reference with the [address] property equal to "http://www.w3.org/2005/08/addressing/anonymous" is used.</span></span>  
  
-   <span data-ttu-id="83fd4-233">R3324: Il richiedente deve includere `wsa:To`, `wsa:Action`, e `wsa:RelatesTo` intestazioni nel messaggio di risposta, nonché le intestazioni per tutti i parametri per riferimento oppure riferimento proprietà (o entrambi) specificato da di `ReplyTo` riferimento dell'endpoint nel richiesta.</span><span class="sxs-lookup"><span data-stu-id="83fd4-233">R3324: The requester must include `wsa:To`, `wsa:Action`, and `wsa:RelatesTo` headers in the reply message, as well as headers for all reference parameters or reference properties (or both) specified by the `ReplyTo` endpoint reference in the request.</span></span>  
  
### <a name="web-services-addressing-faults"></a><span data-ttu-id="83fd4-234">Errori di indirizzamento dei servizi Web</span><span class="sxs-lookup"><span data-stu-id="83fd4-234">Web Services Addressing Faults</span></span>  
 <span data-ttu-id="83fd4-235">R3411: WCF genera gli errori seguenti definiti da WS-Addressing 2004/08.</span><span class="sxs-lookup"><span data-stu-id="83fd4-235">R3411: WCF produces the following faults defined by WS-Addressing 2004/08.</span></span>  
  
|<span data-ttu-id="83fd4-236">Codice</span><span class="sxs-lookup"><span data-stu-id="83fd4-236">Code</span></span>|<span data-ttu-id="83fd4-237">Causa</span><span class="sxs-lookup"><span data-stu-id="83fd4-237">Cause</span></span>|  
|----------|-----------|  
|<span data-ttu-id="83fd4-238">wsa:DestinationUnreachable</span><span class="sxs-lookup"><span data-stu-id="83fd4-238">wsa:DestinationUnreachable</span></span>|<span data-ttu-id="83fd4-239">Il messaggio in ingresso presenta un riferimento `ReplyTo` diverso dall'indirizzo per risposte definito per questo canale. Non esiste alcun endpoint in attesa presso l'indirizzo specificato nell'intestazione di destinazione.</span><span class="sxs-lookup"><span data-stu-id="83fd4-239">The message arrived with a `ReplyTo` that is different from the reply address established for this channel; there is no endpoint listening at the address specified in the To header.</span></span>|  
|<span data-ttu-id="83fd4-240">wsa:ActionNotSupported</span><span class="sxs-lookup"><span data-stu-id="83fd4-240">wsa:ActionNotSupported</span></span>|<span data-ttu-id="83fd4-241">I canali dell'infrastruttura o il dispatcher associato all'endpoint non riconoscono l'azione specificata nell'intestazione `Action`.</span><span class="sxs-lookup"><span data-stu-id="83fd4-241">the infrastructure channels or dispatcher associated with the endpoint do not recognize the action specified in the `Action` header.</span></span>|  
  
 <span data-ttu-id="83fd4-242">R3412: WCF genera gli errori seguenti definiti da WS-Addressing 1.0.</span><span class="sxs-lookup"><span data-stu-id="83fd4-242">R3412: WCF produces the following faults defined by WS-Addressing 1.0.</span></span>  
  
|<span data-ttu-id="83fd4-243">Codice</span><span class="sxs-lookup"><span data-stu-id="83fd4-243">Code</span></span>|<span data-ttu-id="83fd4-244">Causa</span><span class="sxs-lookup"><span data-stu-id="83fd4-244">Cause</span></span>|  
|----------|-----------|  
|<span data-ttu-id="83fd4-245">wsa10:InvalidAddressingHeader</span><span class="sxs-lookup"><span data-stu-id="83fd4-245">wsa10:InvalidAddressingHeader</span></span>|<span data-ttu-id="83fd4-246">Duplica `wsa:To`, `wsa:ReplyTo`, `wsa:From` o `wsa:MessageID`.</span><span class="sxs-lookup"><span data-stu-id="83fd4-246">Duplicate `wsa:To`, `wsa:ReplyTo`, `wsa:From` or `wsa:MessageID`.</span></span> <span data-ttu-id="83fd4-247">Duplica `wsa:RelatesTo` con lo stesso `RelationshipType`.</span><span class="sxs-lookup"><span data-stu-id="83fd4-247">Duplicate `wsa:RelatesTo` with the same `RelationshipType`.</span></span>|  
|<span data-ttu-id="83fd4-248">wsa10:MessageAddressingHeaderRequired</span><span class="sxs-lookup"><span data-stu-id="83fd4-248">wsa10:MessageAddressingHeaderRequired</span></span>|<span data-ttu-id="83fd4-249">L'intestazione obbligatoria di indirizzamento è mancante.</span><span class="sxs-lookup"><span data-stu-id="83fd4-249">The required Addressing header is missing.</span></span>|  
|<span data-ttu-id="83fd4-250">wsa10:DestinationUnreachable</span><span class="sxs-lookup"><span data-stu-id="83fd4-250">wsa10:DestinationUnreachable</span></span>|<span data-ttu-id="83fd4-251">Il messaggio in ingresso presenta un riferimento `ReplyTo` diverso dall'indirizzo per risposte definito per questo canale.</span><span class="sxs-lookup"><span data-stu-id="83fd4-251">The message arrived with a `ReplyTo` that is different from the reply address established for this channel.</span></span> <span data-ttu-id="83fd4-252">Non esiste alcun endpoint in attesa presso l'indirizzo specificato nell'intestazione di destinazione.</span><span class="sxs-lookup"><span data-stu-id="83fd4-252">There is no endpoint listening at the address specified in the To header.</span></span>|  
|<span data-ttu-id="83fd4-253">wsa10:ActionNotSupported</span><span class="sxs-lookup"><span data-stu-id="83fd4-253">wsa10:ActionNotSupported</span></span>|<span data-ttu-id="83fd4-254">I canali dell'infrastruttura o il dispatcher associato all'endpoint non riconoscono l'azione specificata nell'intestazione `Action`.</span><span class="sxs-lookup"><span data-stu-id="83fd4-254">An action specified in the `Action` header is not recognized by the infrastructure channels or dispatcher associated with the endpoint.</span></span>|  
|<span data-ttu-id="83fd4-255">wsa10:EndpointUnavailable</span><span class="sxs-lookup"><span data-stu-id="83fd4-255">wsa10:EndpointUnavailable</span></span>|<span data-ttu-id="83fd4-256">Il canale RM restituisce questo errore per indicare che l'endpoint non elaborerà la sequenza basata sull'esame delle intestazioni di indirizzamento del messaggio `CreateSequence`.</span><span class="sxs-lookup"><span data-stu-id="83fd4-256">The RM channel sends this fault back, indicating the endpoint will not process the sequence based upon examination of the `CreateSequence` message’s addressing headers.</span></span>|  
  
 <span data-ttu-id="83fd4-257">Il codice delle tabelle precedenti viene mappato al codice `FaultCode` in SOAP 1.1 e al codice `SubCode` (in cui il codice corrisponde al mittente) in SOAP 1.2.</span><span class="sxs-lookup"><span data-stu-id="83fd4-257">Code in the preceding tables maps to `FaultCode` in SOAP 1.1 and `SubCode` (with Code=Sender) in SOAP 1.2.</span></span>  
  
### <a name="wsdl-11-binding-and-ws-policy-assertions"></a><span data-ttu-id="83fd4-258">Utilizzo di associazioni WSDL 1.1 con le asserzioni di WS-Policy</span><span class="sxs-lookup"><span data-stu-id="83fd4-258">WSDL 1.1 Binding and WS-Policy Assertions</span></span>  
  
#### <a name="indicating-use-of-ws-addressing"></a><span data-ttu-id="83fd4-259">Definizione dell'uso di WS-Addressing</span><span class="sxs-lookup"><span data-stu-id="83fd4-259">Indicating Use of WS-Addressing</span></span>  
 <span data-ttu-id="83fd4-260">WCF utilizza le asserzioni di criteri per indicare il supporto di endpoint per una particolare versione di WS-Addressing.</span><span class="sxs-lookup"><span data-stu-id="83fd4-260">WCF uses policy assertions to indicate endpoint support for a particular WS-Addressing version.</span></span>  
  
 <span data-ttu-id="83fd4-261">L'asserzione di criteri seguente contiene il soggetto dei criteri di endpoint [WS-PA] e indica che i messaggi scambiati con l'endpoint devono utilizzare la specifica WS-Addressing 2004/08.</span><span class="sxs-lookup"><span data-stu-id="83fd4-261">The following policy assertion has Endpoint Policy Subject [WS-PA] and indicates messages sent and received from the endpoint must use WS-Addressing 2004/08.</span></span>  
  
```xml  
<wsap:UsingAddressing />  
```  
  
 <span data-ttu-id="83fd4-262">Questa asserzione di criteri si aggiunge alla specifica WS-Addressing 2004/08.</span><span class="sxs-lookup"><span data-stu-id="83fd4-262">This policy assertion augments the WS-Addressing 2004/08 specification.</span></span>  
  
 <span data-ttu-id="83fd4-263">Tramite l'asserzione di criteri seguente viene indicato che nei messaggi inviati/ricevuti deve essere utilizzato WS-Addressing 1.0.</span><span class="sxs-lookup"><span data-stu-id="83fd4-263">The following policy assertion this indicates that messages sent/received must use WS-Addressing 1.0.</span></span>  
  
```xml
<wsam:Addressing/>   
```  
  
 <span data-ttu-id="83fd4-264">Nell'asserzione di criteri seguente è incluso un soggetto dei criteri di endpoint [WS-PA] e viene indicato che nei messaggi scambiati con l'endpoint deve essere utilizzata la specifica WS-Addressing 2004/08.</span><span class="sxs-lookup"><span data-stu-id="83fd4-264">The following policy assertion has an Endpoint Policy Subject [WS-PA] and indicates that messages sent and received from the endpoint must use WS-Addressing 2004/08.</span></span>  
  
```xml  
<wsaw10:UsingAddressing />  
```  
  
 <span data-ttu-id="83fd4-265">L'elemento `wsaw10:UsingAddressing` è preso in prestito da [WS-Addressing-WSDL] e viene utilizzato nel contesto di WS-Policy in conformità alla sezione 3.1.2 di tale specifica.</span><span class="sxs-lookup"><span data-stu-id="83fd4-265">The `wsaw10:UsingAddressing` element is borrowed from [WS-Addressing-WSDL] and is used in the context of WS-Policy in compliance with that specification, section 3.1.2.</span></span>  
  
 <span data-ttu-id="83fd4-266">L'utilizzo dell'intestazione di indirizzamento non modifica la semantica delle associazioni WSDL 1.1 HTTP, SOAP 1.1 HTTP e SOAP 1.2 HTTP.</span><span class="sxs-lookup"><span data-stu-id="83fd4-266">Use of Addressing does not alter the semantics of WSDL 1.1, SOAP 1.1, and SOAP 1.2 HTTP Bindings.</span></span> <span data-ttu-id="83fd4-267">Ad esempio, se si prevede una risposta a una richiesta inviata a un endpoint in cui vengono utilizzati WS-Addressing e l'associazione WSDL SOAP 1.x HTTP, la risposta deve essere inviata tramite la risposta HTTP.</span><span class="sxs-lookup"><span data-stu-id="83fd4-267">For example, if a reply is expected to a request that is sent to an endpoint that uses Addressing and WSDL SOAP 1.x HTTP binding, the reply must be sent by using the HTTP response.</span></span>  
  
 <span data-ttu-id="83fd4-268">Per le risposte inviate tramite la risposta http, l'asserzione WS-AM è:</span><span class="sxs-lookup"><span data-stu-id="83fd4-268">For replies sent over the http response, the WS-AM assertion is:</span></span>  
  
```xml  
<wsam:AnonymousResponses/>  
```  
  
 <span data-ttu-id="83fd4-269">L'asserzione di criteri completa potrebbe essere simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="83fd4-269">The complete policy assertion might look like this:</span></span>  
  
```xml  
<wsam:Addressing>  
    <wsp:Policy>  
        <wsam:AnonymousResponses />   
    </wsp:Policy>  
</wsam:Addressing>  
```  
  
 <span data-ttu-id="83fd4-270">Tuttavia, sono presenti modelli di scambio dei messaggi che traggono profitto dalla presenza di due connessioni HTTP opposte indipendenti stabilite tra il richiedente e il risponditore, ad esempio i messaggi unidirezionali non richiesti inviati dal risponditore.</span><span class="sxs-lookup"><span data-stu-id="83fd4-270">However, there are message exchange patterns that benefit from having two independent converse HTTP connections established between the requester and the responder, for example, unsolicited one-way messages sent by the responder.</span></span>  
  
 <span data-ttu-id="83fd4-271">WCF offre una funzionalità di base al quale due canali di trasporto sottostanti possono formare un canale Duplex composito, in cui un canale viene utilizzato per i messaggi di input e l'altra viene usata per i messaggi di output.</span><span class="sxs-lookup"><span data-stu-id="83fd4-271">WCF offers a feature by which two underlying transport channels can form a Composite Duplex channel, where one channel is used for input messages and the other is used for output messages.</span></span> <span data-ttu-id="83fd4-272">Nel caso del trasporto HTTP, il modello duplex composito offre due connessioni HTTP opposte.</span><span class="sxs-lookup"><span data-stu-id="83fd4-272">In the case of the HTTP Transport, Composite Duplex provides two converse HTTP connections.</span></span> <span data-ttu-id="83fd4-273">Il richiedente utilizza una connessione per inviare i messaggi al risponditore, mentre quest'ultimo utilizza l'altra connessione per inviare i messaggi di risposta al richiedente.</span><span class="sxs-lookup"><span data-stu-id="83fd4-273">The requester uses one connection to send messages to the responder, and the responder uses the other to send messages back to the requester.</span></span>  
  
 <span data-ttu-id="83fd4-274">Per le risposte inviate tramite richieste http distinte, l'asserzione ws-am è:</span><span class="sxs-lookup"><span data-stu-id="83fd4-274">For replies sent over separate http requests, the ws-am assertion is</span></span>  
  
```xml  
<wsam:NonAnonymousResponses/>  
```  
  
 <span data-ttu-id="83fd4-275">L'asserzione di criteri completa potrebbe essere simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="83fd4-275">The complete policy assertion might look like this:</span></span>  
  
```xml  
<wsam:Addressing>  
    <wsp:Policy>  
      <wsam:NonAnonymousResponses />   
   </wsp:Policy>  
  </wsam:Addressing>  
```  
  
 <span data-ttu-id="83fd4-276">Per l'utilizzo dell'asserzione seguente che presenta il soggetto dei criteri di endpoint [WS-PA] negli endpoint in cui vengono utilizzate le associazioni SOAP 1.x HTTP WSDL 1.1 sono richieste due connessioni HTTP opposte e distinte da utilizzare rispettivamente per i messaggi dal richiedente al risponditore e dal risponditore al richiedente.</span><span class="sxs-lookup"><span data-stu-id="83fd4-276">Use of the following assertion that has Endpoint Policy Subject [WS-PA] on endpoints that use WSDL 1.1 SOAP 1.x HTTP bindings requires two separate converse HTTP connections to be used for messages flowing from requester to responder and responder to requester, respectively.</span></span>  
  
```xml  
<cdp:CompositeDuplex/>  
```  
  
 <span data-ttu-id="83fd4-277">L'istruzione precedente comporta i requisiti seguenti per l'intestazione `wsa:ReplyTo` dei messaggi di richiesta:</span><span class="sxs-lookup"><span data-stu-id="83fd4-277">The previous statement leads to the following requirements on the `wsa:ReplyTo` header for request messages:</span></span>  
  
-   <span data-ttu-id="83fd4-278">R3514: Richiedere i messaggi inviati a un endpoint devono presentare un `ReplyTo` intestazione con il `[address]` proprietà non è uguale a "http://www.w3.org/2005/08/addressing/anonymous" se l'endpoint utilizza un'associazione WSDL 1.1 SOAP 1.x HTTP e dispone di un'alternativa criteri avente un' `wsap10:UsingAddressing` o `wsap:UsingAddressing` asserzione associata `cdp:CompositeDuplex` collegato.</span><span class="sxs-lookup"><span data-stu-id="83fd4-278">R3514: Request messages sent to an endpoint must have a `ReplyTo` header with the `[address]` property not equal to "http://www.w3.org/2005/08/addressing/anonymous" if the endpoint uses a WSDL 1.1 SOAP 1.x HTTP binding and has a policy alternative with a `wsap10:UsingAddressing` or `wsap:UsingAddressing` assertion coupled with `cdp:CompositeDuplex` attached.</span></span>  
  
-   <span data-ttu-id="83fd4-279">R3515: Richiedere i messaggi inviati a un endpoint devono presentare un `ReplyTo` intestazione con il `[address]` proprietà è uguale a "http://www.w3.org/2005/08/addressing/anonymous", o non hanno un `ReplyTo` intestazione affatto, se l'endpoint utilizza un'associazione WSDL 1.1 SOAP 1.x HTTP e dispone di un'alternativa criteri con `wsap10:UsingAddressing` asserzione e nessun `cdp:CompositeDuplex` asserzione associata.</span><span class="sxs-lookup"><span data-stu-id="83fd4-279">R3515: Request messages sent to an endpoint must have a `ReplyTo` header with the `[address]` property equal to "http://www.w3.org/2005/08/addressing/anonymous", or not have a `ReplyTo` header at all, if the endpoint uses a WSDL 1.1 SOAP 1.x HTTP binding and has a policy alternative with `wsap10:UsingAddressing` assertion and no `cdp:CompositeDuplex` assertion attached.</span></span>  
  
-   <span data-ttu-id="83fd4-280">R3516: Richiedere i messaggi inviati a un endpoint devono presentare un `ReplyTo` intestazione con un `[address]` proprietà è uguale a "http://www.w3.org/2005/08/addressing/anonymous" se l'endpoint utilizza un'associazione WSDL 1.1 SOAP 1.x HTTP e dispone di un'alternativa criteri avente `wsap:UsingAddressing` asserzione e nessun `cdp:CompositeDuplex`asserzione associata.</span><span class="sxs-lookup"><span data-stu-id="83fd4-280">R3516: Request messages sent to an endpoint must have a `ReplyTo` header with an `[address]` property equal to "http://www.w3.org/2005/08/addressing/anonymous" if the endpoint uses a WSDL 1.1 SOAP 1.x HTTP binding and has a policy alternative with `wsap:UsingAddressing` assertion and no `cdp:CompositeDuplex` assertion attached.</span></span>  
  
 <span data-ttu-id="83fd4-281">La specifica WS-Addressing WSDL tenta di descrivere associazioni del protocollo simili introducendo un elemento `<wsaw:Anonymous/>` con tre valori testuali (obbligatorio, facoltativo e proibito) per indicare requisiti nell'intestazione `wsa:ReplyTo` (sezione 3.2).</span><span class="sxs-lookup"><span data-stu-id="83fd4-281">The WS-addressing WSDL specification attempts to describe similar protocol bindings by introducing an element `<wsaw:Anonymous/>` with three textual values (required, optional, and prohibited) to indicate requirements on the `wsa:ReplyTo` header (section 3.2).</span></span> <span data-ttu-id="83fd4-282">Sfortunatamente, tale definizione dell'elemento non è utilizzabile in modo specifico nel contesto di WS-Policy, perché richiede estensioni specifiche di dominio per supportare l'intersezione di alternative che utilizzano tale elemento come asserzione.</span><span class="sxs-lookup"><span data-stu-id="83fd4-282">Unfortunately, such element definition is not particularly usable as an assertion in the context of WS-Policy, because it requires domain-specific extensions to support the intersection of alternatives using such an element as an assertion.</span></span> <span data-ttu-id="83fd4-283">A differenza del comportamento di endpoint in transito, che rende il valore dell'intestazione `ReplyTo` specifico del trasporto HTTP, il suddetto elemento indica questo valore senza associarlo a un determinato protocollo.</span><span class="sxs-lookup"><span data-stu-id="83fd4-283">Such element definition also indicates the value of the `ReplyTo` header as opposed to the endpoint behavior on the wire, which makes it specific to HTTP transport.</span></span>  
  
#### <a name="action-definition"></a><span data-ttu-id="83fd4-284">Definizione dell'attributo Action</span><span class="sxs-lookup"><span data-stu-id="83fd4-284">Action Definition</span></span>  
 <span data-ttu-id="83fd4-285">La specifica WS-Addressing 2004/08 definisce un attributo `wsa:Action` per gli elementi `wsdl:portType/wsdl:operation/[wsdl:input | wsdl:output | wsdl:fault]`.</span><span class="sxs-lookup"><span data-stu-id="83fd4-285">WS-Addressing 2004/08 defines a `wsa:Action` attribute for the `wsdl:portType/wsdl:operation/[wsdl:input | wsdl:output | wsdl:fault]` elements.</span></span> <span data-ttu-id="83fd4-286">L'associazione WS-Addressing 1.0 WSDL (WS-ADDR10-WSDL) definisce un attributo simile, ovvero `wsaw10:Action`.</span><span class="sxs-lookup"><span data-stu-id="83fd4-286">WS-Addressing 1.0 WSDL Binding (WS-ADDR10-WSDL) defines a similar attribute, `wsaw10:Action`.</span></span>  
  
 <span data-ttu-id="83fd4-287">L'unica differenza consiste nella semantica del modello Action predefinito, descritta rispettivamente nella sezione 3.3.2 della specifica WS-ADDR e nella sezione 4.4.4 della specifica WS-ADDR10-WSDL.</span><span class="sxs-lookup"><span data-stu-id="83fd4-287">The only difference between the two is the default Action pattern semantics described in section 3.3.2 of WS-ADDR and section 4.4.4 of WS-ADDR10-WSDL, respectively.</span></span>  
  
 <span data-ttu-id="83fd4-288">È ammissibile avere due endpoint che condividono lo stesso `portType` (o contratto, nella terminologia di WCF), ma mediante versioni diverse di WS-Addressing.</span><span class="sxs-lookup"><span data-stu-id="83fd4-288">It is a reasonable to have two endpoints that share the same `portType` (or contract, in WCF terminology) but using different versions of WS-Addressing.</span></span> <span data-ttu-id="83fd4-289">Tuttavia, se l'attributo Action è definito dall'attributo `portType` e deve essere condiviso da tutti gli endpoint che implementano l'attributo `portType`, risulta impossibile supportare entrambi i modelli Action predefiniti.</span><span class="sxs-lookup"><span data-stu-id="83fd4-289">But given that Action is defined by the `portType` and should not change across the endpoints that implement the `portType`, it becomes impossible to support both default action patterns.</span></span>  
  
 <span data-ttu-id="83fd4-290">Per risolvere questa problematica, WCF supporta una sola versione del `Action` attributo.</span><span class="sxs-lookup"><span data-stu-id="83fd4-290">To resolve this controversy, WCF supports a single version of the `Action` attribute.</span></span>  
  
 <span data-ttu-id="83fd4-291">B3521: WCF utilizza il `wsaw10:Action` attributo `wsdl:portType/wsdl:operation/[wsdl:input | wsdl:output | wsdl:fault]` gli elementi come definito in WS-ADDR10-WSDL per determinare il `Action` URI per i messaggi corrispondenti indipendentemente dalla versione WS-Addressing utilizzata dall'endpoint.</span><span class="sxs-lookup"><span data-stu-id="83fd4-291">B3521: WCF uses the `wsaw10:Action` attribute on `wsdl:portType/wsdl:operation/[wsdl:input | wsdl:output | wsdl:fault]` elements as defined in WS-ADDR10-WSDL to determine the `Action` URI for the corresponding messages irrespective of the WS-Addressing version used by the endpoint.</span></span>  
  
#### <a name="use-endpoint-reference-inside-wsdl-port"></a><span data-ttu-id="83fd4-292">Utilizzare il riferimento a endpoint nell'elemento wsdl:port</span><span class="sxs-lookup"><span data-stu-id="83fd4-292">Use Endpoint Reference Inside WSDL Port</span></span>  
 <span data-ttu-id="83fd4-293">La sezione 4.1 di WS-ADDR10-WSDL estende l'elemento `wsdl:port` per includere l'elemento figlio `<wsa10:EndpointReference…/>` allo scopo di descrivere l'endpoint in termini di WS-Addressing.</span><span class="sxs-lookup"><span data-stu-id="83fd4-293">WS-ADDR10-WSDL section 4.1 extends the `wsdl:port` element to include the `<wsa10:EndpointReference…/>` child element to describe the endpoint in WS-Addressing terms.</span></span> <span data-ttu-id="83fd4-294">WCF estende questa utilità in WS-Addressing 2004/08, consentendo `<wsa:EndpointReference…/>` venga visualizzato come elemento figlio di `wsdl:port`.</span><span class="sxs-lookup"><span data-stu-id="83fd4-294">WCF expands this utility on WS-Addressing 2004/08, allowing `<wsa:EndpointReference…/>` to appear as a child element of `wsdl:port`.</span></span>  
  
-   <span data-ttu-id="83fd4-295">R3531: se a un endpoint è associata un'alternativa criteri avente un'asserzione di criteri `<wsaw10:UsingAddressing/>`, l'elemento`wsdl:port`corrispondente può contenere un elemento figlio`<wsa10:EndpointReference …/>`.</span><span class="sxs-lookup"><span data-stu-id="83fd4-295">R3531: If an endpoint has an attached policy alternative with a `<wsaw10:UsingAddressing/>` policy assertion, the corresponding `wsdl:port` element can contain a child element `<wsa10:EndpointReference …/>`.</span></span>  
  
-   <span data-ttu-id="83fd4-296">R3532: Se un `wsdl:port` contiene un elemento figlio `<wsa10:EndpointReference …/>`, il `wsa10:EndpointReference/wsa10:Address` valore dell'elemento figlio deve corrispondere al valore della `@address` attributo dell'elemento di pari livello `wsdl:port` / `wsdl:location` elemento.</span><span class="sxs-lookup"><span data-stu-id="83fd4-296">R3532: If a `wsdl:port` contains a child element `<wsa10:EndpointReference …/>`, the `wsa10:EndpointReference/wsa10:Address` child element value must match the value of the `@address` attribute of the sibling `wsdl:port`/`wsdl:location` element.</span></span>  
  
-   <span data-ttu-id="83fd4-297">R3533: se a un endpoint è associata un'alternativa criteri avente un'asserzione di criteri `<wsap:UsingAddressing/>`, l'elemento`wsdl:port`corrispondente può contenere un elemento figlio`<wsa:EndpointReference …/>`.</span><span class="sxs-lookup"><span data-stu-id="83fd4-297">R3533: If an endpoint has an attached policy alternative with `<wsap:UsingAddressing/>` policy assertion, the corresponding `wsdl:port` element can contain a child element `<wsa:EndpointReference …/>`.</span></span>  
  
-   <span data-ttu-id="83fd4-298">R3534: Se un `wsdl:port` contiene un elemento figlio `<wsa:EndpointReference …/>`, il `wsa:EndpointReference/wsa:Address` valore dell'elemento figlio deve corrispondere al valore della `@address` attributo dell'elemento di pari livello `wsdl:port` / `wsdl:location` elemento.</span><span class="sxs-lookup"><span data-stu-id="83fd4-298">R3534: If a `wsdl:port` contains a child element `<wsa:EndpointReference …/>`, the `wsa:EndpointReference/wsa:Address` child element value must match the value of the `@address` attribute of the sibling `wsdl:port`/`wsdl:location` element.</span></span>  
  
### <a name="composition-with-ws-security"></a><span data-ttu-id="83fd4-299">Integrazione con WS-Security</span><span class="sxs-lookup"><span data-stu-id="83fd4-299">Composition with WS-Security</span></span>  
 <span data-ttu-id="83fd4-300">Secondo le sezioni di WS-ADDR e WS-ADDR10 relative alle considerazioni sulla sicurezza, è consigliabile firmare tutte le intestazioni dei messaggi di indirizzamento insieme al corpo del messaggio, in modo da associarli fra loro.</span><span class="sxs-lookup"><span data-stu-id="83fd4-300">According to security consideration sections in WS-ADDR and WS-ADDR10, all addressing message headers are recommended to be signed together with the message body to bind them together.</span></span>  
  
 <span data-ttu-id="83fd4-301">Quando si utilizza WS-Security per garantire l'integrità dei messaggi, le intestazioni dei messaggi di WS-Addressing nonché le intestazioni ottenute dai parametri o dalle proprietà del riferimento (o da entrambi) devono essere firmate insieme al corpo del messaggio.</span><span class="sxs-lookup"><span data-stu-id="83fd4-301">When WS-Security is used for message integrity protection, WS-Addressing message headers as well as headers resulted from reference parameters or properties (or both) must be signed together with the body of the message.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="83fd4-302">Esempi</span><span class="sxs-lookup"><span data-stu-id="83fd4-302">Examples</span></span>  
  
#### <a name="one-way-message"></a><span data-ttu-id="83fd4-303">Modello unidirezionale</span><span class="sxs-lookup"><span data-stu-id="83fd4-303">One-Way Message</span></span>  
 <span data-ttu-id="83fd4-304">In questo scenario, il mittente invia un messaggio unidirezionale al destinatario.</span><span class="sxs-lookup"><span data-stu-id="83fd4-304">In this scenario, the sender sends a one-way message to the receiver.</span></span> <span data-ttu-id="83fd4-305">Vengono utilizzate le specifiche SOAP 1.2, HTTP 1.1 e W3C WS-Addressing 1.0.</span><span class="sxs-lookup"><span data-stu-id="83fd4-305">SOAP 1.2, HTTP 1.1, and W3C WS-Addressing 1.0 are used.</span></span>  
  
 <span data-ttu-id="83fd4-306">Struttura dei messaggi di richiesta: le intestazioni dei messaggi includono gli elementi `wsa10:To` e `wsa10:Action`.</span><span class="sxs-lookup"><span data-stu-id="83fd4-306">The Request Message Structure: The message headers include `wsa10:To` and `wsa10:Action` elements.</span></span> <span data-ttu-id="83fd4-307">Il corpo dei messaggi include un elemento `<app:Ping>` specifico dello spazio dei nomi dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="83fd4-307">The message body includes a specific `<app:Ping>` element from the application namespace.</span></span>  
  
 <span data-ttu-id="83fd4-308">Intestazioni HTTP: La destinazione indicata in POST corrisponde all'URI specificato nel `wsa10:To` elemento.</span><span class="sxs-lookup"><span data-stu-id="83fd4-308">HTTP Headers: The destination in POST matches the URI in the `wsa10:To` element.</span></span>  
  
 <span data-ttu-id="83fd4-309">L'intestazione Content-Type dispone del valore di `application/soap+xml` come richiesto da SOAP 1.2.</span><span class="sxs-lookup"><span data-stu-id="83fd4-309">The Content-Type header has the value of `application/soap+xml` as required by SOAP 1.2.</span></span> <span data-ttu-id="83fd4-310">I parametri `charset` e `action` sono inclusi.</span><span class="sxs-lookup"><span data-stu-id="83fd4-310">Parameters `charset` and `action` are included.</span></span> <span data-ttu-id="83fd4-311">Il parametro `action` dell'intestazione Content-Type corrisponde al valore dell'intestazione dei messaggi `wsa10:Action`.</span><span class="sxs-lookup"><span data-stu-id="83fd4-311">The `action` parameter of the Content-Type header matches the value of the `wsa10:Action` message header.</span></span>  
  
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
  
 <span data-ttu-id="83fd4-312">Il destinatario fornisce con una risposta HTTP vuota e lo stato 202.</span><span class="sxs-lookup"><span data-stu-id="83fd4-312">The receiver responds with an empty HTTP response and status 202.</span></span> <span data-ttu-id="83fd4-313">Un esempio della risposta HTTP:</span><span class="sxs-lookup"><span data-stu-id="83fd4-313">An example of the HTTP response:</span></span>  
  
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
  
## <a name="soap-message-transmission-optimization-mechanism"></a><span data-ttu-id="83fd4-314">SOAP MTOM</span><span class="sxs-lookup"><span data-stu-id="83fd4-314">SOAP Message Transmission Optimization Mechanism</span></span>  
 <span data-ttu-id="83fd4-315">In questa sezione descrive i dettagli di implementazione WCF per il meccanismo HTTP SOAP MTOM.</span><span class="sxs-lookup"><span data-stu-id="83fd4-315">This section describes the WCF implementation details for the HTTP SOAP MTOM.</span></span> <span data-ttu-id="83fd4-316">Tecnologia MTOM è un meccanismo di codifica messaggi SOAP della stessa classe di codifica text/XML tradizionali o codifica binaria di WCF.</span><span class="sxs-lookup"><span data-stu-id="83fd4-316">MTOM technology is SOAP message encoding mechanism of the same class as traditional text/XML encoding or WCF Binary encoding.</span></span> <span data-ttu-id="83fd4-317">Il meccanismo MTOM prevede le funzionalità seguenti:</span><span class="sxs-lookup"><span data-stu-id="83fd4-317">MTOM includes the following:</span></span>  
  
-   <span data-ttu-id="83fd4-318">Meccanismo di codifica e assemblaggio di pacchetti XML descritto da [XOP] che ottimizza le voci di informazioni XML contenenti dati binari con codifica in base 64 suddividendoli in parti binarie distinte.</span><span class="sxs-lookup"><span data-stu-id="83fd4-318">An XML encoding and packaging mechanism described by [XOP] that optimizes XML information items containing base64-encoded binary data into separate binary parts.</span></span>  
  
-   <span data-ttu-id="83fd4-319">Incapsulamento MIME del pacchetto XOP che serializza l'InfoSet XML e ogni parte binaria del pacchetto XOP in una parte MIME distinta.</span><span class="sxs-lookup"><span data-stu-id="83fd4-319">A MIME encapsulation of the XOP package that serializes the XML Infoset and each binary part of the XOP package into a separate MIME part.</span></span>  
  
-   <span data-ttu-id="83fd4-320">Codifica MIME XOP applicata alla SOAP 1.x envelope.</span><span class="sxs-lookup"><span data-stu-id="83fd4-320">A MIME XOP encoding applied to SOAP 1.x Envelope.</span></span>  
  
-   <span data-ttu-id="83fd4-321">Associazione di trasporto HTTP.</span><span class="sxs-lookup"><span data-stu-id="83fd4-321">An HTTP transport binding.</span></span>  
  
 <span data-ttu-id="83fd4-322">È possibile utilizzare il meccanismo MTOM con trasporti non HTTP con WCF.</span><span class="sxs-lookup"><span data-stu-id="83fd4-322">It is possible to use MTOM with non-HTTP transports with WCF.</span></span> <span data-ttu-id="83fd4-323">quanto descritto in questo argomento si basa sul protocollo HTTP.</span><span class="sxs-lookup"><span data-stu-id="83fd4-323">However, in this topic we will focus on HTTP.</span></span>  
  
 <span data-ttu-id="83fd4-324">Il formato MTOM sfrutta un numeroso set di specifiche relative al meccanismo MTOM stesso, a XOP e a MIME.</span><span class="sxs-lookup"><span data-stu-id="83fd4-324">The MTOM format leverages a large set of specifications covering MTOM itself, XOP, and MIME.</span></span> <span data-ttu-id="83fd4-325">La modularità di questo set di specifiche rende piuttosto difficile ricavare in modo esatto i requisiti relativi alla semantica di formato ed elaborazione.</span><span class="sxs-lookup"><span data-stu-id="83fd4-325">Modularity of this specification set makes it somewhat difficult to reconstruct exact requirements on the format and processing semantics.</span></span> <span data-ttu-id="83fd4-326">Questa sezione descrive i requisiti di formato ed elaborazione dell'associazione MTOM HTTP.</span><span class="sxs-lookup"><span data-stu-id="83fd4-326">This section describes the format and processing requirements for MTOM HTTP binding.</span></span>  
  
### <a name="mtom-message-encoding"></a><span data-ttu-id="83fd4-327">Codifica dei messaggi MTOM</span><span class="sxs-lookup"><span data-stu-id="83fd4-327">MTOM Message Encoding</span></span>  
  
#### <a name="generating-mtom-messages"></a><span data-ttu-id="83fd4-328">Generazione di messaggi MTOM</span><span class="sxs-lookup"><span data-stu-id="83fd4-328">Generating MTOM messages</span></span>  
 <span data-ttu-id="83fd4-329">La sezione 3.1 di [XOP] descrive il processo di codifica di elementi XML aventi voci di informazioni sugli elementi contenenti valori in base 64 in un pacchetto XOP definito in modo astratto.</span><span class="sxs-lookup"><span data-stu-id="83fd4-329">The [XOP] section 3.1 describes the process of encoding XML with element information items that contain base64 values into an abstractly defined XOP package.</span></span>  
  
 <span data-ttu-id="83fd4-330">La sequenza di passaggi seguente descrive il processo di codifica specifico del meccanismo MTOM:</span><span class="sxs-lookup"><span data-stu-id="83fd4-330">The following sequence of steps describes the MTOM-specific encoding process:</span></span>  
  
1.  <span data-ttu-id="83fd4-331">Assicurarsi che la SOAP Envelope da codificare non contiene alcun elemento informazioni sull'elemento con un `[namespace name]` di "http://www.w3.org/2004/08/xop/include" e un `[local name]` di `Include`.</span><span class="sxs-lookup"><span data-stu-id="83fd4-331">Ensure that the SOAP Envelope to be encoded contains no element information item with a `[namespace name]` of "http://www.w3.org/2004/08/xop/include" and a `[local name]` of `Include`.</span></span>  
  
2.  <span data-ttu-id="83fd4-332">Creare un pacchetto MIME vuoto.</span><span class="sxs-lookup"><span data-stu-id="83fd4-332">Create an empty MIME package.</span></span>  
  
3.  <span data-ttu-id="83fd4-333">Identificare all'interno dell'InfoSet XML originale le voci di informazioni sugli elementi da ottimizzare.</span><span class="sxs-lookup"><span data-stu-id="83fd4-333">Identify within the Original XML Infoset the element information items to be optimized.</span></span> <span data-ttu-id="83fd4-334">Per gli elementi da ottimizzare, i caratteri che costituiscono il `[children]` le informazioni elemento elemento deve essere nel formato canonico `xs:base64Binary` (vedere XSD-2, 3.2.16 base64Binary) e non deve contenere i caratteri spazi vuoti precedente, in linea con, o Dopo il contenuto di spazio non vuoto.</span><span class="sxs-lookup"><span data-stu-id="83fd4-334">For the items to be optimized, the characters that make up the `[children]` of the element information item must be in the canonical form of `xs:base64Binary` (see XSD-2, 3.2.16 base64Binary) and must not contain any white-space characters preceding, inline with, or following the non-white-space content.</span></span>  
  
4.  <span data-ttu-id="83fd4-335">Creare una XOP SOAP envelope uguale alla SOAP envelope originale, sostituendo tuttavia al figlio di ogni voce di informazioni sugli elementi identificato nel passaggio precedente una voce di informazioni sugli elementi `xop:Include` costruito come segue:</span><span class="sxs-lookup"><span data-stu-id="83fd4-335">Create an XOP SOAP Envelope that is a copy of the Original SOAP Envelope, but with the children of each element information item identified in the previous step replaced by an `xop:Include` element information item constructed as follows:</span></span>  
  
    1.  <span data-ttu-id="83fd4-336">Trasformare i caratteri sostituiti in dati binari elaborandoli come dati codificati in base 64.</span><span class="sxs-lookup"><span data-stu-id="83fd4-336">Transform the replaced characters into binary data by processing them as base64-encoded data.</span></span>  
  
    2.  <span data-ttu-id="83fd4-337">Generare un valore univoco di intestazione Content-ID che soddisfi i requisiti R3133 e R3134.</span><span class="sxs-lookup"><span data-stu-id="83fd4-337">Generate a unique Content-ID header value that satisfies requirements R3133 and R3134.</span></span>  
  
    3.  <span data-ttu-id="83fd4-338">Generare un'intestazione MIME Content-Transfer-Encoding con il valore in binario.</span><span class="sxs-lookup"><span data-stu-id="83fd4-338">Generate a Content-Transfer-Encoding MIME header with the value binary.</span></span>  
  
    4.  <span data-ttu-id="83fd4-339">Se la voce di informazioni sugli elementi da ottimizzare (ovvero il padre [parent] della voce di informazioni sugli elementi `xop:Include` appena aggiunto) contiene una voce di informazioni sugli attributi `xmime:contentType`, generare un'intestazione Content-Type MIME con il valore dell'attributo `xmime:contentType`.</span><span class="sxs-lookup"><span data-stu-id="83fd4-339">If the element information item being optimized (the [parent] of the newly inserted `xop:Include` element information item) has an `xmime:contentType` attribute information item, generate a Content-Type MIME header with the value of the `xmime:contentType` attribute.</span></span>  
  
    5.  <span data-ttu-id="83fd4-340">Generare una nuova parte MIME binaria avente un contenuto formato dagli elementi seguenti: dati binari decodificati a partire dai caratteri sostituiti elaborati come dati in base 64, intestazione Content-ID come da passaggio 4b, intestazione Content- Transfer-Encoding come da passaggio 4c e intestazione Content-Type come da passaggio 4d, se presente.</span><span class="sxs-lookup"><span data-stu-id="83fd4-340">Generate a new binary MIME part with content formed by binary data decoded from the replaced characters processed as base64, Content-ID header from 4b, Content- Transfer-Encoding header from 4c, Content-Type header if generated in step 4d.</span></span>  
  
    6.  <span data-ttu-id="83fd4-341">Aggiungere un attributo `href` all'elemento `xop:Include` con il valore cid: uri derivato dal valore dell'intestazione Content-ID generato nel passaggio 4b.</span><span class="sxs-lookup"><span data-stu-id="83fd4-341">Add an `href` attribute to the `xop:Include` element with the value cid: uri derived from Content-ID header value generated in step 4b.</span></span> <span data-ttu-id="83fd4-342">Rimuovere il tipo di inclusione "\<" e ">" caratteri escape-URL la stringa restante e aggiungere il prefisso `cid:`.</span><span class="sxs-lookup"><span data-stu-id="83fd4-342">Remove the enclosing "\<" and ">" characters, URL-escape the remaining string, and add the prefix `cid:`.</span></span> <span data-ttu-id="83fd4-343">La suddetta conversione, da eseguire in base ai documenti RFC1738 e RFC2396, deve riguardare almeno il set di caratteri seguente,</span><span class="sxs-lookup"><span data-stu-id="83fd4-343">The following minimum character set is required to be escaped by RFC1738 and RFC2396.</span></span> <span data-ttu-id="83fd4-344">ma può essere applicata anche ad altri caratteri.</span><span class="sxs-lookup"><span data-stu-id="83fd4-344">Other characters can be escaped.</span></span>  
  
        ```  
        Hexadecimal 00-1F , 7F, 20, "<" | ">" | "#" | "%" | <">  
        "{" | "}" | "|" | "\" | "^" | "[" | "]" | "`" | "~" | "^"  
        ```  
  
5.  <span data-ttu-id="83fd4-345">Creare una parte MIME radice contenente la XOP SOAP envelope ottenuta nel passaggio 4.</span><span class="sxs-lookup"><span data-stu-id="83fd4-345">Create a root MIME part with the XOP SOAP Envelope from step 4.</span></span>  
  
6.  <span data-ttu-id="83fd4-346">Scrivere le intestazioni HTTP, compresa l'intestazione Content-Type HTTP.</span><span class="sxs-lookup"><span data-stu-id="83fd4-346">Write the HTTP headers, including the HTTP Content-Type header.</span></span>  
  
7.  <span data-ttu-id="83fd4-347">Scrivere il pacchetto MIME.</span><span class="sxs-lookup"><span data-stu-id="83fd4-347">Write the MIME package.</span></span>  
  
#### <a name="processing-mtom-messages"></a><span data-ttu-id="83fd4-348">Elaborazione di messaggi MTOM</span><span class="sxs-lookup"><span data-stu-id="83fd4-348">Processing MTOM messages</span></span>  
 <span data-ttu-id="83fd4-349">L'elaborazione di un messaggio MTOM è l'esatto contrario del processo descritto nella sezione precedente "Generazione di messaggi MTOM":</span><span class="sxs-lookup"><span data-stu-id="83fd4-349">Processing of an MTOM message is the exact reverse of the process described in the preceding "Generating MTOM messages" section:</span></span>  
  
1.  <span data-ttu-id="83fd4-350">Verificare che la parte MIME radice contenga l'elemento Content-Type `application/xop+xml`.</span><span class="sxs-lookup"><span data-stu-id="83fd4-350">Ensure the root MIME part has the Content-Type `application/xop+xml`.</span></span>  
  
2.  <span data-ttu-id="83fd4-351">Costruire una SOAP envelope analizzando la parte MIME radice del pacchetto come documento XML.</span><span class="sxs-lookup"><span data-stu-id="83fd4-351">Construct a SOAP Envelope by parsing the root MIME part of the package as an XML document.</span></span> <span data-ttu-id="83fd4-352">La codifica dei caratteri viene determinata in base al parametro `charset` del Content-Type della parte MIME radice.</span><span class="sxs-lookup"><span data-stu-id="83fd4-352">Character encoding is determined by the `charset` parameter of the Content-Type of the root MIME part.</span></span>  
  
3.  <span data-ttu-id="83fd4-353">Per ogni voce di informazioni sugli elementi della SOAP envelope costruita, che come unico membro della proprietà dei relativi figli [children] presenta una voce di informazioni sugli elementi `xop:Include`, eseguire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="83fd4-353">For each element information item in the constructed SOAP Envelope, which has, as the sole member of its [children] property, an `xop:Include` element information item:</span></span>  
  
    1.  <span data-ttu-id="83fd4-354">Rimuovere il prefisso `cid:` ed eseguire la conversione URI inversa di tutte le sequenze escape (RFC 2396) contenute nel valore dell'attributo `@href` dell'elemento `xop:Include`.</span><span class="sxs-lookup"><span data-stu-id="83fd4-354">Remove the `cid:` prefix and unescape all URI-escape sequences (RFC 2396) in the value of the `@href` attribute of the `xop:Include` element.</span></span> <span data-ttu-id="83fd4-355">Racchiudere la stringa di risultato in "\<", ">".</span><span class="sxs-lookup"><span data-stu-id="83fd4-355">Enclose the result string in "\<", ">".</span></span>  
  
    2.  <span data-ttu-id="83fd4-356">Individuare la parte MIME contenente il valore dell'intestazione Content-ID corrispondente alla stringa ottenuta nel passaggio 3a.</span><span class="sxs-lookup"><span data-stu-id="83fd4-356">Locate the MIME part with the Content-ID header value that matches the string derived in step 3a.</span></span>  
  
    3.  <span data-ttu-id="83fd4-357">Sostituire la voce di informazioni sugli elementi `xop:Include` contenuto nella proprietà `children` di ogni elemento contenente le voci di informazioni sugli elementi che rappresentano la codifica canonica in base 64 (vedere XSD-2, 3.2.16 base64Binary) del corpo dell'entità della parte MIME identificato nel passaggio 3b. In pratica, sostituire la voce di informazioni sugli elementi `xop:Include` con i dati ricostruiti a partire dalla parte di pacchetto.</span><span class="sxs-lookup"><span data-stu-id="83fd4-357">Replace the `xop:Include` element information item that appears in the `children` property of each item with the character information items that represent the canonical base64 encoding (see XSD-2, 3.2.16 base64Binary) of the entity body of the MIME part identified in step 3b (effectively replace the `xop:Include` element information item with the data reconstructed from the package part).</span></span>  
  
#### <a name="http-content-type-header"></a><span data-ttu-id="83fd4-358">Intestazione Content-Type HTTP</span><span class="sxs-lookup"><span data-stu-id="83fd4-358">HTTP Content-Type Header</span></span>  
 <span data-ttu-id="83fd4-359">Di seguito è riportato un elenco di precisazioni WCF per il formato dell'intestazione Content-Type HTTP di un messaggio SOAP 1.x con codifica MTOM derivato dai requisiti dichiarati nella specifica di MTOM e si basano MTOM e RFC 2387.</span><span class="sxs-lookup"><span data-stu-id="83fd4-359">The following is a list of WCF clarifications for the format of the HTTP Content-Type header of a SOAP 1.x MTOM-encoded message derived from requirements stated in the MTOM specification itself and are derived from MTOM and RFC 2387.</span></span>  
  
-   <span data-ttu-id="83fd4-360">R4131: un'intestazione Content-Type HTTP deve contenere il valore multipart/related (che non fa distinzione fra maiuscole e minuscole) e i relativi parametri.</span><span class="sxs-lookup"><span data-stu-id="83fd4-360">R4131: An HTTP Content-Type header must have the value of multipart/related (case-insensitive) and its parameters.</span></span> <span data-ttu-id="83fd4-361">Anche i nomi dei parametri non fanno distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="83fd4-361">Parameter names are case-insensitive.</span></span> <span data-ttu-id="83fd4-362">Inoltre, l'ordine dei parametri è irrilevante.</span><span class="sxs-lookup"><span data-stu-id="83fd4-362">Parameter order is not significant.</span></span>  
  
-   <span data-ttu-id="83fd4-363">La notazione BNF completa dell'intestazione Content-Type dei messaggi MIME è riportata nella sezione 5.1 del documento RFC 2045.</span><span class="sxs-lookup"><span data-stu-id="83fd4-363">The full Backus-Naur Form (BNF) of the Content-Type header for MIME messages is listed in RFC 2045, section 5.1.</span></span>  
  
-   <span data-ttu-id="83fd4-364">R4132: un'intestazione Content-Type HTTP deve contenere un parametro di tipo avente il valore `application/xop+xml` compreso fra virgolette doppie.</span><span class="sxs-lookup"><span data-stu-id="83fd4-364">R4132: An HTTP Content-Type header must have a type parameter with the value `application/xop+xml` enclosed in double quotation marks.</span></span>  
  
 <span data-ttu-id="83fd4-365">Anche la necessità di utilizzare le virgolette doppie non è esplicita in RFC 2387, il testo osserva che molto probabilmente tutti i parametri di tipo di supporto multipart/related contengono caratteri riservati, ad esempio "\@" o "/" e pertanto richiede le virgolette doppie contrassegni.</span><span class="sxs-lookup"><span data-stu-id="83fd4-365">While the requirement to use double quotation marks is not explicit in RFC 2387, the text observes that all of the multipart/related media type parameters most likely contain reserved characters like "\@" or "/" and therefore need double quotation marks.</span></span>  
  
-   <span data-ttu-id="83fd4-366">R4133: un'intestazione Content-Type HTTP deve presentare un parametro start con il valore dell'intestazione Content-ID della parte MIME contenente l'elemento SOAP 1.x Envelope, racchiuso fra virgolette doppie.</span><span class="sxs-lookup"><span data-stu-id="83fd4-366">R4133: An HTTP Content-Type header should have a start parameter with the value of the Content-ID header of the MIME part that contains the SOAP 1.x Envelope, enclosed in double quotation marks.</span></span> <span data-ttu-id="83fd4-367">Se tale parametro viene omesso, la SOAP 1.x envelope deve essere inclusa nella prima parte MIME.</span><span class="sxs-lookup"><span data-stu-id="83fd4-367">If the start parameter is omitted, the first MIME part must contain the SOAP 1.x Envelope.</span></span>  
  
-   <span data-ttu-id="83fd4-368">R4134: un'intestazione Content-Type HTTP di un messaggio con codifica SOAP 1.1 MTOM deve includere il parametro start-info con il valore text/xml racchiuso fra virgolette doppie.</span><span class="sxs-lookup"><span data-stu-id="83fd4-368">R4134: An HTTP Content-Type header for a SOAP 1.1 MTOM encoded message must include the start-info parameter with the value of text/xml, enclosed in double quotation marks.</span></span>  
  
-   <span data-ttu-id="83fd4-369">R4135: un'intestazione Content-Type HTTP di un messaggio con codifica SOAP 1.2 MTOM deve includere il parametro start-info con il valore `application/soap+xml` racchiuso fra virgolette doppie.</span><span class="sxs-lookup"><span data-stu-id="83fd4-369">R4135: An HTTP Content-Type header for a SOAP 1.2 MTOM-encoded message must include the start-info parameter with the value of `application/soap+xml`, enclosed in double quotation marks.</span></span>  
  
-   <span data-ttu-id="83fd4-370">R4136: un'intestazione Content-Type HTTP di un messaggio con codifica SOAP 1.x MTOM deve contenere un parametro boundary il cui valore (racchiuso fra virgolette doppie) corrisponda al formato BNF del limite MIME definito nella sezione 5.1.1 del documento RFC 2046.</span><span class="sxs-lookup"><span data-stu-id="83fd4-370">R4136: HTTP Content-Type header for a SOAP 1.x MTOM-encoded message must have the boundary parameter with the value (enclosed in double quotation marks) that matches the MIME boundary BNF defined in RFC 2046, section 5.1.1</span></span>  
  
    ```  
    boundary := 0*69<bchars> bcharsnospace   
    bchars := bcharsnospace / " "   
    bcharsnospace :=    DIGIT / ALPHA / "'" / "(" / ")" / "+"   
                        / "_" / "," / "-" / "." / "/" / ":" / "=" / "?"  
    ```  
  
     <span data-ttu-id="83fd4-371">Esempi:</span><span class="sxs-lookup"><span data-stu-id="83fd4-371">Examples:</span></span>  
  
     <span data-ttu-id="83fd4-372">CORRETTO</span><span class="sxs-lookup"><span data-stu-id="83fd4-372">CORRECT</span></span>  
  
    ```  
    Content-Type: multipart/related; type="application/xop+xml";start=" <part0@tempuri.org>";boundary="uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=1";start-info="text/xml"  
    ```  
  
     <span data-ttu-id="83fd4-373">CORRETTO</span><span class="sxs-lookup"><span data-stu-id="83fd4-373">CORRECT</span></span>  
  
    ```  
    Content-Type: Multipart/Related; type="application/xop+xml";start-info="text/xml";boundary="uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=1"  
    ```  
  
     <span data-ttu-id="83fd4-374">NON CORRETTO</span><span class="sxs-lookup"><span data-stu-id="83fd4-374">INCORRECT</span></span>  
  
    ```  
    Content-Type: Multipart/Related; type=application/xop+xml;start=" <part0@tempuri.org>";start-info="text/xml";boundary="uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=1"   
    ```  
  
#### <a name="infoset-mime-part"></a><span data-ttu-id="83fd4-375">Parte MIME InfoSet</span><span class="sxs-lookup"><span data-stu-id="83fd4-375">Infoset MIME Part</span></span>  
 <span data-ttu-id="83fd4-376">La SOAP 1.x envelope è incapsulata come parte radice del pacchetto XOP MIME e spesso viene detta "parte `infoset`".</span><span class="sxs-lookup"><span data-stu-id="83fd4-376">The SOAP 1.x Envelope is encapsulated as a root part of the XOP MIME package and is often called the `infoset` part.</span></span>  
  
-   <span data-ttu-id="83fd4-377">R4141: la SOAP 1.x envelope deve essere incapsulata come parte radice del pacchetto XOP MIME, detto "parte `infoset`", a cui si fa riferimento nell'intestazione Content-Type HTTP.</span><span class="sxs-lookup"><span data-stu-id="83fd4-377">R4141: The SOAP 1.x Envelope must be encapsulated as a root part of the XOP MIME package, called the `infoset` part and referenced from the HTTP Content-Type.</span></span>  
  
-   <span data-ttu-id="83fd4-378">R4142: la parte `Infoset` SOAP deve contenere le intestazioni MIME seguenti: `Content-ID`, `Content-Transfer-Encoding` e `Content-Type`.</span><span class="sxs-lookup"><span data-stu-id="83fd4-378">R4142: The SOAP `Infoset` part must include the following MIME headers: `Content-ID`, `Content-Transfer-Encoding`, and `Content-Type`.</span></span>  
  
 <span data-ttu-id="83fd4-379">Il formato dell'intestazione Content-ID è definito nel documento RFC 2045 come</span><span class="sxs-lookup"><span data-stu-id="83fd4-379">The format of the Content-ID header is defined by RFC 2045 as</span></span>  
  
```  
"Content-ID" ":" msg-id  
```  
  
 <span data-ttu-id="83fd4-380">in cui l'elemento `msg-id` è definito nel documento RFC 2822 (che sostituisce il documento RFC 822, a cui si fa riferimento nel documento RFC 2045) come:</span><span class="sxs-lookup"><span data-stu-id="83fd4-380">where `msg-id` is defined in RFC 2822 (that supersedes RFC 822, referenced in RFC 2045) as:</span></span>  
  
```  
msg-id    =       [CFWS] "<" id-left "@" id-right ">" [CFWS]  
```  
  
 <span data-ttu-id="83fd4-381">e in modo efficace un indirizzo di posta elettronica è incluso all'interno di "\<" e ">".</span><span class="sxs-lookup"><span data-stu-id="83fd4-381">and is effectively an email address enclosed within "\<" and  ">".</span></span> <span data-ttu-id="83fd4-382">Il prefisso e il suffisso `[CFWS]` sono stati aggiunti nel documento RFC 2822 per contenere commenti e non devono essere utilizzati per mantenere l'interoperabilità.</span><span class="sxs-lookup"><span data-stu-id="83fd4-382">The `[CFWS]` prefix and suffix were added in RFC 2822 to carry comments and should not be used to preserve interoperability.</span></span>  
  
 <span data-ttu-id="83fd4-383">R4143: il valore dell'intestazione Content-ID della parte MIME InfoSet deve attenersi alle regole di definizione dell'elemento `msg-id` indicate nel documento RFC 2822, omettendo le parti `[CFWS]` di prefisso e suffisso.</span><span class="sxs-lookup"><span data-stu-id="83fd4-383">R4143: The value of the Content-ID header for the Infoset MIME part must follow `msg-id` production from RFC 2822 with the `[CFWS]` prefix and suffix parts omitted.</span></span>  
  
 <span data-ttu-id="83fd4-384">Molte implementazioni MIME ridotti i requisiti per il valore racchiuso tra parentesi "\<" e ">" per essere un indirizzo di posta elettronica e usati `absoluteURI` racchiusa tra "\<", ">" oltre all'indirizzo di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="83fd4-384">A number of MIME implementations relaxed requirements for the value enclosed within "\<" and ">" to be an email address and used `absoluteURI` enclosed in "\<" , ">" in addition to the email address.</span></span> <span data-ttu-id="83fd4-385">Questa versione di WCF utilizza i valori dell'intestazione MIME Content-ID nel formato:</span><span class="sxs-lookup"><span data-stu-id="83fd4-385">This version of WCF uses values of the Content-ID MIME header of the form:</span></span>  
  
```  
Content-ID: <http://tempuri.org/0>   
```  
  
 <span data-ttu-id="83fd4-386">R4144: i processori MTOM devono accettare valori di intestazione Content-ID corrispondenti all'elemento `msg-id` con requisiti ridotti riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="83fd4-386">R4144: MTOM processors should accept Content-ID header values that match the following relaxed `msg-id`.</span></span>  
  
```  
msg-id-relaxed =     [CFWS] "<" (absoluteURI | mail-address) ">" [CFWS]  
mail-address   =     id-left "@" id-right  
```  
  
 <span data-ttu-id="83fd4-387">Il protocollo MIME (RFC 2045) fornisce l'intestazione Content-Transfer-Encoding per comunicare la codifica del contenuto della parte MIME.</span><span class="sxs-lookup"><span data-stu-id="83fd4-387">MIME (RFC 2045) provides the Content-Transfer-Encoding header to communicate encoding of the content of the MIME part.</span></span> <span data-ttu-id="83fd4-388">L'impostazione predefinita dell'intestazione Content-Transfer-Encoding è una codifica a 7 bit, che tuttavia per la maggior parte dei messaggi SOAP risulta inadatta. Pertanto, tale intestazione è necessaria per garantire una maggiore interoperabilità:</span><span class="sxs-lookup"><span data-stu-id="83fd4-388">The default defined for Content-Transfer-Encoding is 7-bit, which is not suitable for most SOAP messages, so the Content-Transfer-Encoding header is needed for greater interoperability:</span></span>  
  
-   <span data-ttu-id="83fd4-389">R4145: la parte SOAP InfoSet deve contenere l'intestazione Content-Transfer-Encoding.</span><span class="sxs-lookup"><span data-stu-id="83fd4-389">R4145: The SOAP Infoset part must contain the Content-Transfer-Encoding header.</span></span>  
  
-   <span data-ttu-id="83fd4-390">R4146: se la codifica dei caratteri della SOAP envelope è UTF-8, il valore dell'intestazione Content-Transfer-Encoding deve corrispondere a una codifica a 8 bit.</span><span class="sxs-lookup"><span data-stu-id="83fd4-390">R4146: If the SOAP Envelope character encoding is UTF-8, the value of the Content-Transfer-Encoding header must be 8-bit.</span></span>  
  
-   <span data-ttu-id="83fd4-391">R4147: se la codifica dei caratteri della SOAP envelope è UTF-16, il valore dell'intestazione Content-Transfer-Encoding deve corrispondere a una codifica binaria.</span><span class="sxs-lookup"><span data-stu-id="83fd4-391">R4147: If the SOAP Envelope character encoding is UTF-16, the value of the Content-Transfer-Encoding header must be binary.</span></span>  
  
-   <span data-ttu-id="83fd4-392">Secondo quanto indicato nella sezione 5 di [XOP]:</span><span class="sxs-lookup"><span data-stu-id="83fd4-392">According to [XOP] section 5,</span></span>  
  
-   <span data-ttu-id="83fd4-393">R4148: La parte SOAP1.1 Infoset deve contenere l'intestazione Content-Type con tipo di supporto application/xop + xml e parametri di tipo = "text/xml" e charset</span><span class="sxs-lookup"><span data-stu-id="83fd4-393">R4148: SOAP1.1 Infoset part must contain Content-Type header with media type application/xop+xml and parameters type="text/xml" and charset</span></span>  
  
    ```  
    Content-Type: application/xop+xml;  
                  charset=utf-8;type="text/xml"  
    ```  
  
-   <span data-ttu-id="83fd4-394">R4149: La parte SOAP 1.2 Infoset deve contenere l'intestazione Content-Type con tipo di supporto `application/xop+xml` e parametri di tipo = "`application/soap+xml`" e `charset`.</span><span class="sxs-lookup"><span data-stu-id="83fd4-394">R4149: The SOAP 1.2 Infoset part must contain the Content-Type header with media type `application/xop+xml` and parameters type="`application/soap+xml`" and `charset`.</span></span>  
  
    ```  
    Content-Type: application/xop+xml;  
                  charset=utf-8;type="application/soap+xml"  
    ```  
  
     <span data-ttu-id="83fd4-395">Benché XOP consenta di definire il parametro `charset` di `application/xop+xml` come facoltativo, tale parametro è necessario per l'interoperabilità, analogamente al requisito di BP 1.1 relativo al parametro `charset` del tipo di supporto `text/xml`.</span><span class="sxs-lookup"><span data-stu-id="83fd4-395">While XOP defines the `charset` parameter for `application/xop+xml` to be optional, it is needed for interoperability similar to the BP 1.1 requirement on the `charset` parameter for the `text/xml` media type.</span></span>  
  
-   <span data-ttu-id="83fd4-396">R41410: i parametri `type` e `charset` devono essere presenti nell'intestazione Content-Type della parte SOAP 1.x InfoSet.</span><span class="sxs-lookup"><span data-stu-id="83fd4-396">R41410: The `type` and `charset` parameters must be present on the Content-Type header of the SOAP 1.x Infoset part.</span></span>  
  
#### <a name="wcf-endpoint-support-for-mtom"></a><span data-ttu-id="83fd4-397">Supporto degli endpoint WCF per MTOM</span><span class="sxs-lookup"><span data-stu-id="83fd4-397">WCF Endpoint Support for MTOM</span></span>  
 <span data-ttu-id="83fd4-398">Lo scopo del meccanismo MTOM è codificare un messaggio SOAP allo scopo di ottimizzare i dati codificati in base 64.</span><span class="sxs-lookup"><span data-stu-id="83fd4-398">The purpose of MTOM is to encode a SOAP message to optimize base64-encoded data.</span></span> <span data-ttu-id="83fd4-399">Segue un elenco di vincoli:</span><span class="sxs-lookup"><span data-stu-id="83fd4-399">The following is a list of constraints:</span></span>  
  
-   <span data-ttu-id="83fd4-400">R4151: qualsiasi voce di informazioni sugli elementi contenente dati con codifica in base 64 può essere ottimizzata.</span><span class="sxs-lookup"><span data-stu-id="83fd4-400">R4151: Any element information item that contains base64-encoded data may be optimized.</span></span>  
  
-   <span data-ttu-id="83fd4-401">B4152: WCF consente di ottimizzare le informazioni sugli elementi che contengono dati con codifica base64 e superare i 1024 byte in lunghezza.</span><span class="sxs-lookup"><span data-stu-id="83fd4-401">B4152: WCF optimizes element information items that contain base64-encoded data and exceed 1024 bytes in length.</span></span>  
  
 <span data-ttu-id="83fd4-402">Un endpoint WCF configurato per utilizzare il meccanismo MTOM inviano sempre i messaggi con codifica MTOM.</span><span class="sxs-lookup"><span data-stu-id="83fd4-402">A WCF endpoint configured to use MTOM will always send MTOM-encoded messages.</span></span> <span data-ttu-id="83fd4-403">Anche se nessuna parte soddisfa i criteri previsti, il messaggio viene comunque considerato come messaggio con codifica MTOM, serializzato come pacchetto MIME e avente una sola parte MIME contenente la SOAP envelope.</span><span class="sxs-lookup"><span data-stu-id="83fd4-403">Even if no parts meet the required criteria, the message is still MTOM-encoded (serialized as a MIME package with a single MIME part containing the SOAP envelope).</span></span>  
  
### <a name="ws-policy-assertion-for-mtom"></a><span data-ttu-id="83fd4-404">Asserzione di WS-Policy relativa a MTOM</span><span class="sxs-lookup"><span data-stu-id="83fd4-404">WS-Policy Assertion for MTOM</span></span>  
 <span data-ttu-id="83fd4-405">WCF utilizza l'asserzione di criteri seguenti per indicare l'utilizzo del meccanismo MTOM dall'endpoint:</span><span class="sxs-lookup"><span data-stu-id="83fd4-405">WCF uses the following policy assertion to indicate MTOM usage by endpoint:</span></span>  
  
```xml  
<wsoma:OptimizedMimeSerialization ... />  
```  
  
-   <span data-ttu-id="83fd4-406">R4211: l'asserzione di criteri precedente contiene un soggetto dei criteri di endpoint e impone che tutti i messaggi inviati all'endpoint e provenienti da quest'ultimo vengano ottimizzati tramite il meccanismo MTOM.</span><span class="sxs-lookup"><span data-stu-id="83fd4-406">R4211: The preceding policy assertion has an Endpoint Policy Subject and specifies that all messages sent to and received from the endpoint must be optimized using MTOM.</span></span>  
  
-   <span data-ttu-id="83fd4-407">B4212: Quando configurato per utilizzare l'ottimizzazione MTOM, un endpoint WCF aggiunge un'asserzione di criteri MTOM al criterio associato all'oggetto corrispondente `wsdl:binding`.</span><span class="sxs-lookup"><span data-stu-id="83fd4-407">B4212: When configured to use MTOM optimization, an WCF endpoint adds an MTOM Policy assertion to the policy attached to the corresponding `wsdl:binding`.</span></span>  
  
### <a name="composition-with-ws-security"></a><span data-ttu-id="83fd4-408">Integrazione con WS-Security</span><span class="sxs-lookup"><span data-stu-id="83fd4-408">Composition with WS-Security</span></span>  
 <span data-ttu-id="83fd4-409">MTOM è un meccanismo di codifica che è simile a `text/xml` e XML binario WCF.</span><span class="sxs-lookup"><span data-stu-id="83fd4-409">MTOM is an encoding mechanism that is similar to `text/xml` and WCF Binary XML.</span></span> <span data-ttu-id="83fd4-410">Il meccanismo MTOM può integrarsi perfettamente con il protocollo WS-Security e gli altri protocolli WS - \*: un messaggio protetto mediante il protocollo WS-Security può infatti essere ottimizzato tramite MTOM.</span><span class="sxs-lookup"><span data-stu-id="83fd4-410">MTOM offers natural composition with WS-Security and other WS-\* protocols: a message secured using WS-Security can be optimized using MTOM.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="83fd4-411">Esempi</span><span class="sxs-lookup"><span data-stu-id="83fd4-411">Examples</span></span>  
  
#### <a name="wcf-soap-11-message-encoded-using-mtom"></a><span data-ttu-id="83fd4-412">Esempio di messaggio WCF SOAP 1.1 codificato tramite MTOM</span><span class="sxs-lookup"><span data-stu-id="83fd4-412">WCF SOAP 1.1 Message Encoded Using MTOM</span></span>  
  
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
  
#### <a name="wcf-secure-soap-12-message-encoded-using-mtom"></a><span data-ttu-id="83fd4-413">Esempio di messaggio WCF Secure SOAP 1.2 codificato tramite MTOM</span><span class="sxs-lookup"><span data-stu-id="83fd4-413">WCF Secure SOAP 1.2 Message Encoded Using MTOM</span></span>  
 <span data-ttu-id="83fd4-414">Questo esempio illustra la codifica tramite MTOM e SOAP 1.2 di un messaggio protetto mediante WS-Security.</span><span class="sxs-lookup"><span data-stu-id="83fd4-414">In this example, a message is encoded using MTOM and SOAP 1.2 that is protected using WS-Security.</span></span> <span data-ttu-id="83fd4-415">Le parti binarie identificate per la codifica sono il contenuto del token `BinarySecurityToken`, il valore `CipherValue` dell'elemento `EncryptedData` che corrisponde alla firma crittografata e il corpo crittografato.</span><span class="sxs-lookup"><span data-stu-id="83fd4-415">The binary parts identified for encoding are the contents of the `BinarySecurityToken`, `CipherValue` of the `EncryptedData` corresponding to the encrypted signature and encrypted body.</span></span> <span data-ttu-id="83fd4-416">Si noti che il `CipherValue` del `EncryptedKey` non identificata per l'ottimizzazione da WCF, poiché la sua lunghezza è inferiore a 1024 byte.</span><span class="sxs-lookup"><span data-stu-id="83fd4-416">Note that the `CipherValue` of the `EncryptedKey` was not identified for optimization by WCF, because its length is less then 1024 bytes.</span></span>  
  
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
