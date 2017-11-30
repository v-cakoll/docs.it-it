---
title: Protocolli di messaggistica
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5b20bca7-87b3-4c8f-811b-f215b5987104
caps.latest.revision: "14"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 4052971746086061cb2ed091bd13c962318b2d89
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="messaging-protocols"></a><span data-ttu-id="b6e1c-102">Protocolli di messaggistica</span><span class="sxs-lookup"><span data-stu-id="b6e1c-102">Messaging Protocols</span></span>
<span data-ttu-id="b6e1c-103">Lo stack di canali di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] utilizza canali di codifica e di trasporto per trasformare le rappresentazioni interne dei messaggi nel relativo formato di trasmissione e quindi per inviare i dati così ottenuti mediante un trasporto specifico.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-103">The [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] channel stack employs encoding and transport channels to transform internal message representation into its wire format and send it by using a particular transport.</span></span> <span data-ttu-id="b6e1c-104">Il trasporto più comunemente utilizzato per garantire l'interoperabilità dei servizi Web è il protocollo HTTP, mentre le codifiche utilizzate dai servizi Web sono in genere SOAP 1.1 basato su XML, SOAP 1.2 e il protocollo MTOM (Message Transmission Optimization Mechanism, meccanismo di ottimizzazione della trasmissione dei messaggi).</span><span class="sxs-lookup"><span data-stu-id="b6e1c-104">The most common transport used for Web services interoperability is HTTP, and the most common encodings used by Web services are XML-based SOAP 1.1, SOAP 1.2, and Message Transmission Optimization Mechanism (MTOM).</span></span>  
  
 <span data-ttu-id="b6e1c-105">Questo argomento descrive i dettagli di implementazione di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] relativi ai protocolli elencati di seguito utilizzati dalla classe <xref:System.ServiceModel.Channels.HttpTransportBindingElement>. Nota: la documentazione seguente potrebbe essere in inglese.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-105">This topic covers [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] implementation details for the following protocols employed by <xref:System.ServiceModel.Channels.HttpTransportBindingElement>.</span></span>  
  
|<span data-ttu-id="b6e1c-106">Specifica/documento</span><span class="sxs-lookup"><span data-stu-id="b6e1c-106">Specification/document</span></span>|<span data-ttu-id="b6e1c-107">Collegamento</span><span class="sxs-lookup"><span data-stu-id="b6e1c-107">Link</span></span>|  
|-----------------------------|----------|  
|<span data-ttu-id="b6e1c-108">HTTP 1.1</span><span class="sxs-lookup"><span data-stu-id="b6e1c-108">HTTP 1.1</span></span>|<span data-ttu-id="b6e1c-109">http://www.ietf.org/rfc/rfc2616.txt</span><span class="sxs-lookup"><span data-stu-id="b6e1c-109">http://www.ietf.org/rfc/rfc2616.txt</span></span>|  
|<span data-ttu-id="b6e1c-110">Associazione SOAP 1,1 HTTP</span><span class="sxs-lookup"><span data-stu-id="b6e1c-110">SOAP 1.1 HTTP Binding</span></span>|<span data-ttu-id="b6e1c-111">http://www.w3.org/TR/2000/NOTE-SOAP-20000508/, sezione 7</span><span class="sxs-lookup"><span data-stu-id="b6e1c-111">http://www.w3.org/TR/2000/NOTE-SOAP-20000508/, Section 7</span></span>|  
|<span data-ttu-id="b6e1c-112">Associazione SOAP 1,2 HTTP</span><span class="sxs-lookup"><span data-stu-id="b6e1c-112">SOAP 1.2 HTTP Binding</span></span>|<span data-ttu-id="b6e1c-113">http://www.w3.org/TR/soap12-part2/, sezione 7</span><span class="sxs-lookup"><span data-stu-id="b6e1c-113">http://www.w3.org/TR/soap12-part2/, Section 7</span></span>|  
  
 <span data-ttu-id="b6e1c-114">Questo argomento descrive i dettagli di implementazione di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] relativi ai protocolli elencati di seguito utilizzati dalle classi <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement> e <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>. Nota: la documentazione seguente potrebbe essere in inglese.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-114">This topic covers [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] implementation details for the following protocols  that <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement> and <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement> employ.</span></span>  
  
|<span data-ttu-id="b6e1c-115">Specifica/documento</span><span class="sxs-lookup"><span data-stu-id="b6e1c-115">Specification/Document</span></span>|<span data-ttu-id="b6e1c-116">Collegamento</span><span class="sxs-lookup"><span data-stu-id="b6e1c-116">Link</span></span>|  
|-----------------------------|----------|  
|<span data-ttu-id="b6e1c-117">XML</span><span class="sxs-lookup"><span data-stu-id="b6e1c-117">XML</span></span>|<span data-ttu-id="b6e1c-118">http://www.w3.org/TR/REC-xml</span><span class="sxs-lookup"><span data-stu-id="b6e1c-118">http://www.w3.org/TR/REC-xml</span></span>|  
|<span data-ttu-id="b6e1c-119">SOAP 1,1</span><span class="sxs-lookup"><span data-stu-id="b6e1c-119">SOAP 1.1</span></span>|<span data-ttu-id="b6e1c-120">http://www.w3.org/TR/2000/NOTE-SOAP-20000508/</span><span class="sxs-lookup"><span data-stu-id="b6e1c-120">http://www.w3.org/TR/2000/NOTE-SOAP-20000508/</span></span>|  
|<span data-ttu-id="b6e1c-121">SOAP 1.2 Core</span><span class="sxs-lookup"><span data-stu-id="b6e1c-121">SOAP 1.2 Core</span></span>|<span data-ttu-id="b6e1c-122">http://www.w3.org/TR/soap12-part1/</span><span class="sxs-lookup"><span data-stu-id="b6e1c-122">http://www.w3.org/TR/soap12-part1/</span></span>|  
|<span data-ttu-id="b6e1c-123">WS-Addressing 2004/08</span><span class="sxs-lookup"><span data-stu-id="b6e1c-123">WS-Addressing 2004/08</span></span>|<span data-ttu-id="b6e1c-124">http://www.w3.org/Submission/2004/SUBM-ws-addressing-20040810/</span><span class="sxs-lookup"><span data-stu-id="b6e1c-124">http://www.w3.org/Submission/2004/SUBM-ws-addressing-20040810/</span></span>|  
|<span data-ttu-id="b6e1c-125">W3C Web Services Addressing 1.0 - Core</span><span class="sxs-lookup"><span data-stu-id="b6e1c-125">W3C Web Services Addressing 1.0 - Core</span></span>|<span data-ttu-id="b6e1c-126">http://www.w3.org/TR/2006/REC-ws-addr-core-20060509</span><span class="sxs-lookup"><span data-stu-id="b6e1c-126">http://www.w3.org/TR/2006/REC-ws-addr-core-20060509</span></span>|  
|<span data-ttu-id="b6e1c-127">W3C Web Services Addressing 1.0 - SOAP Binding</span><span class="sxs-lookup"><span data-stu-id="b6e1c-127">W3C Web Services Addressing 1.0 - SOAP Binding</span></span>|<span data-ttu-id="b6e1c-128">http://www.w3.org/TR/2006/REC-ws-addr-soap-20060509</span><span class="sxs-lookup"><span data-stu-id="b6e1c-128">http://www.w3.org/TR/2006/REC-ws-addr-soap-20060509</span></span>|  
|<span data-ttu-id="b6e1c-129">W3C Web Services Addressing 1.0 con associazione WSDL</span><span class="sxs-lookup"><span data-stu-id="b6e1c-129">W3C Web Services Addressing 1.0 - WSDL Binding</span></span>|<span data-ttu-id="b6e1c-130">http://www.w3.org/TR/2006/CR-ws-addr-wsdl-20060529/</span><span class="sxs-lookup"><span data-stu-id="b6e1c-130">http://www.w3.org/TR/2006/CR-ws-addr-wsdl-20060529/</span></span>|  
<span data-ttu-id="b6e1c-131">W3C Web Services Addressing 1.0 - Metadata</span><span class="sxs-lookup"><span data-stu-id="b6e1c-131">W3C Web Services Addressing 1.0 - Metadata</span></span>|<span data-ttu-id="b6e1c-132">http://www.w3.org/TR/ws-addr-metadata/</span><span class="sxs-lookup"><span data-stu-id="b6e1c-132">http://www.w3.org/TR/ws-addr-metadata/</span></span>|  
|<span data-ttu-id="b6e1c-133">WSDL SOAP1.1 Binding</span><span class="sxs-lookup"><span data-stu-id="b6e1c-133">WSDL SOAP1.1 Binding</span></span>|<span data-ttu-id="b6e1c-134">http://www.w3.org/TR/wsdl/</span><span class="sxs-lookup"><span data-stu-id="b6e1c-134">http://www.w3.org/TR/wsdl/</span></span>|  
|<span data-ttu-id="b6e1c-135">WSDL SOAP1.2 Binding</span><span class="sxs-lookup"><span data-stu-id="b6e1c-135">WSDL SOAP1.2 Binding</span></span>|<span data-ttu-id="b6e1c-136">http://www.w3.org/Submission/wsdl11soap12/</span><span class="sxs-lookup"><span data-stu-id="b6e1c-136">http://www.w3.org/Submission/wsdl11soap12/</span></span>|  
  
 <span data-ttu-id="b6e1c-137">Questo argomento descrive i dettagli di implementazione di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] relativi ai protocolli elencati di seguito utilizzati dalla classe <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>. Nota: la documentazione seguente potrebbe essere in inglese.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-137">This topic covers [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] implementation details for the following protocols that <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement> employs.</span></span>  
  
|<span data-ttu-id="b6e1c-138">Specifica/documento</span><span class="sxs-lookup"><span data-stu-id="b6e1c-138">Specification/document</span></span>|<span data-ttu-id="b6e1c-139">Collegamento</span><span class="sxs-lookup"><span data-stu-id="b6e1c-139">Link</span></span>|  
|-----------------------------|----------|  
|<span data-ttu-id="b6e1c-140">XOP</span><span class="sxs-lookup"><span data-stu-id="b6e1c-140">XOP</span></span>|<span data-ttu-id="b6e1c-141">http://www.w3.org/TR/xop10/</span><span class="sxs-lookup"><span data-stu-id="b6e1c-141">http://www.w3.org/TR/xop10/</span></span>|  
|<span data-ttu-id="b6e1c-142">Associazione MTOM SOAP 1.2</span><span class="sxs-lookup"><span data-stu-id="b6e1c-142">MTOM + SOAP 1.2 Binding</span></span>|<span data-ttu-id="b6e1c-143">http://www.w3.org/TR/soap12-mtom/</span><span class="sxs-lookup"><span data-stu-id="b6e1c-143">http://www.w3.org/TR/soap12-mtom/</span></span>|  
|<span data-ttu-id="b6e1c-144">MTOM SOAP 1.1 Binding</span><span class="sxs-lookup"><span data-stu-id="b6e1c-144">MTOM SOAP 1.1 Binding</span></span>|<span data-ttu-id="b6e1c-145">http://www.w3.org/Submission/soap11mtom10/</span><span class="sxs-lookup"><span data-stu-id="b6e1c-145">http://www.w3.org/Submission/soap11mtom10/</span></span>|  
|<span data-ttu-id="b6e1c-146">Asserzione di WS-Policy relativa a MTOM</span><span class="sxs-lookup"><span data-stu-id="b6e1c-146">MTOM WS-Policy Assertion</span></span>|<span data-ttu-id="b6e1c-147">http://www.w3.org/Submission/2006/SUBM-WS-MTOMPolicy-20061101/.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-147">http://www.w3.org/Submission/2006/SUBM-WS-MTOMPolicy-20061101/.</span></span>|  
  
 <span data-ttu-id="b6e1c-148">In questo argomento vengono utilizzati gli spazi dei nomi XML e i relativi prefissi associati seguenti.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-148">The following XML namespaces and associated prefixes are used throughout this topic.</span></span>  
  
|<span data-ttu-id="b6e1c-149">Prefisso</span><span class="sxs-lookup"><span data-stu-id="b6e1c-149">Prefix</span></span>|<span data-ttu-id="b6e1c-150">URI (Uniform Resource Identifier) dello spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="b6e1c-150">Namespace Uniform Resource Identifier (URI)</span></span>|  
|------------|---------------------------------------------------|  
|<span data-ttu-id="b6e1c-151">s11</span><span class="sxs-lookup"><span data-stu-id="b6e1c-151">s11</span></span>|<span data-ttu-id="b6e1c-152">http://schemas.xmlsoap.org/soap/envelope</span><span class="sxs-lookup"><span data-stu-id="b6e1c-152">http://schemas.xmlsoap.org/soap/envelope</span></span>|  
|<span data-ttu-id="b6e1c-153">s12</span><span class="sxs-lookup"><span data-stu-id="b6e1c-153">s12</span></span>|<span data-ttu-id="b6e1c-154">http://www.w3.org/2003/05/soap-envelope</span><span class="sxs-lookup"><span data-stu-id="b6e1c-154">http://www.w3.org/2003/05/soap-envelope</span></span>|  
|<span data-ttu-id="b6e1c-155">wsa</span><span class="sxs-lookup"><span data-stu-id="b6e1c-155">wsa</span></span>|<span data-ttu-id="b6e1c-156">http://www.w3.org/2004/08/Addressing</span><span class="sxs-lookup"><span data-stu-id="b6e1c-156">http://www.w3.org/2004/08/addressing</span></span>|  
|<span data-ttu-id="b6e1c-157">wsam</span><span class="sxs-lookup"><span data-stu-id="b6e1c-157">wsam</span></span>|<span data-ttu-id="b6e1c-158">http://www.w3.org/2007/05/addressing/metadata</span><span class="sxs-lookup"><span data-stu-id="b6e1c-158">http://www.w3.org/2007/05/addressing/metadata</span></span>|  
|<span data-ttu-id="b6e1c-159">wsap</span><span class="sxs-lookup"><span data-stu-id="b6e1c-159">wsap</span></span>|<span data-ttu-id="b6e1c-160">http://schemas.xmlsoap.org/ws/2004/09/policy/addressing</span><span class="sxs-lookup"><span data-stu-id="b6e1c-160">http://schemas.xmlsoap.org/ws/2004/09/policy/addressing</span></span>|  
|<span data-ttu-id="b6e1c-161">wsa10</span><span class="sxs-lookup"><span data-stu-id="b6e1c-161">wsa10</span></span>|<span data-ttu-id="b6e1c-162">http://www.w3.org/2005/08/addressing</span><span class="sxs-lookup"><span data-stu-id="b6e1c-162">http://www.w3.org/2005/08/addressing</span></span>|  
|<span data-ttu-id="b6e1c-163">wsaw10</span><span class="sxs-lookup"><span data-stu-id="b6e1c-163">wsaw10</span></span>|<span data-ttu-id="b6e1c-164">http://www.w3.org/2006/05/addressing/wsdl</span><span class="sxs-lookup"><span data-stu-id="b6e1c-164">http://www.w3.org/2006/05/addressing/wsdl</span></span>|  
|<span data-ttu-id="b6e1c-165">xop</span><span class="sxs-lookup"><span data-stu-id="b6e1c-165">xop</span></span>|<span data-ttu-id="b6e1c-166">http://www.w3.org/2004/08/xop/include</span><span class="sxs-lookup"><span data-stu-id="b6e1c-166">http://www.w3.org/2004/08/xop/include</span></span>|  
|<span data-ttu-id="b6e1c-167">xmime</span><span class="sxs-lookup"><span data-stu-id="b6e1c-167">xmime</span></span>|<span data-ttu-id="b6e1c-168">http://www.w3.org/2004/06/xmlmime</span><span class="sxs-lookup"><span data-stu-id="b6e1c-168">http://www.w3.org/2004/06/xmlmime</span></span><br /><br /> <span data-ttu-id="b6e1c-169">http://www.w3.org/2005/05/xmlmime</span><span class="sxs-lookup"><span data-stu-id="b6e1c-169">http://www.w3.org/2005/05/xmlmime</span></span>|  
<span data-ttu-id="b6e1c-170">punto di distribuzione</span><span class="sxs-lookup"><span data-stu-id="b6e1c-170">dp</span></span>|<span data-ttu-id="b6e1c-171">http://schemas.microsoft.com/net/2006/06/duplex</span><span class="sxs-lookup"><span data-stu-id="b6e1c-171">http://schemas.microsoft.com/net/2006/06/duplex</span></span>|  
  
## <a name="soap-11-and-soap-12"></a><span data-ttu-id="b6e1c-172">SOAP 1.1 e SOAP 1.2</span><span class="sxs-lookup"><span data-stu-id="b6e1c-172">SOAP 1.1 and SOAP 1.2</span></span>  
  
### <a name="envelope-and-processing-model"></a><span data-ttu-id="b6e1c-173">Modello di elaborazione della envelope</span><span class="sxs-lookup"><span data-stu-id="b6e1c-173">Envelope and Processing Model</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="b6e1c-174"> implementa l'elaborazione della SOAP 1.1 envelope attenendosi alle specifiche Basic Profile 1.1 (BP11) e Basic Profile 1.0 (SSBP10).</span><span class="sxs-lookup"><span data-stu-id="b6e1c-174"> implements SOAP 1.1 envelope processing following Basic Profile 1.1 (BP11) and Basic Profile 1.0 (SSBP10).</span></span> <span data-ttu-id="b6e1c-175">L'elaborazione della SOAP 1.2 envelope viene implementata attenendosi alla specifica SOAP12-Part1.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-175">SOAP 1.2 Envelope processing is implemented following SOAP12-Part1.</span></span>  
  
 <span data-ttu-id="b6e1c-176">Contenuto della sezione vengono descritte alcune scelte di implementazione previste in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] relativamente alle specifiche BP11 e SOAP12-Part1.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-176">This section explains certain implementation choices taken by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] with regard to BP11 and SOAP12-Part1.</span></span>  
  
#### <a name="mandatory-header-processing"></a><span data-ttu-id="b6e1c-177">Elaborazione obbligatoria delle intestazioni</span><span class="sxs-lookup"><span data-stu-id="b6e1c-177">Mandatory Header Processing</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="b6e1c-178"> elabora le intestazioni `mustUnderstand` attenendosi alle regole descritte nelle specifiche SOAP 1.1 e SOAP 1.2, con le variazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-178"> follows rules for processing headers marked `mustUnderstand` described in the SOAP 1.1 and SOAP 1.2 specifications, with the following variations.</span></span>  
  
 <span data-ttu-id="b6e1c-179">Un messaggio che viene inserito nello stack di canali di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] viene elaborato da canali specifici configurati in base ai relativi elementi di associazione, ad esempio gli elementi relativi alla codifica dei messaggi di testo, alla sicurezza, alla messaggistica affidabile e alle transazioni.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-179">A message that enters the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] channel stack is processed by individual channels configured by associated binding elements, for example, Text Message Encoding, Security, Reliable Messaging, and Transactions.</span></span> <span data-ttu-id="b6e1c-180">Ogni canale riconosce le intestazioni dallo spazio dei nomi associato e le contrassegna come riconosciute.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-180">Each channel recognizes headers from the associated namespace and marks them as understood.</span></span> <span data-ttu-id="b6e1c-181">Dopo l'inserimento di un messaggio nel dispatcher, il formattatore dell'operazione legge le intestazioni previste dal contratto di messaggio/operazione corrispondente e le contrassegna come riconosciute.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-181">Once a message enters the dispatcher, the operation formatter reads headers expected by the corresponding message/operation contract and marks them understood.</span></span> <span data-ttu-id="b6e1c-182">Quindi, il dispatcher verifica se esistono intestazioni non riconosciute ma la cui intestazione `mustUnderstand` richiede il riconoscimento e, in tal caso, genera un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-182">Then the dispatcher verifies whether any remaining headers are not understood but marked as `mustUnderstand` and throws an exception.</span></span> <span data-ttu-id="b6e1c-183">I messaggi che contengono intestazioni `mustUnderstand` indirizzate al destinatario non vengono elaborati dal codice dell'applicazione di destinazione.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-183">Messages that contain `mustUnderstand` headers that are targeted at the recipient are not processed by recipient application code.</span></span>  
  
 <span data-ttu-id="b6e1c-184">Questo tipo di elaborazione a livelli consente la separazione fra i livelli di infrastruttura e livelli di applicazione del nodo SOAP:</span><span class="sxs-lookup"><span data-stu-id="b6e1c-184">Such layered processing allows for separation between infrastructure layers and application layers of the SOAP node:</span></span>  
  
-   <span data-ttu-id="b6e1c-185">B1111: le intestazioni non riconosciute vengono rilevate dopo l'elaborazione del messaggio da parte dello stack di canali dell'infrastruttura di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ma prima dell'elaborazione del messaggio da parte dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="b6e1c-185">B1111: Headers that are not understood are detected after the message is processed by the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] infrastructure channel stack, but before it is processed by application</span></span>  
  
     <span data-ttu-id="b6e1c-186">Il valore dell'intestazione `mustUnderstand` differisce tra SOAP 1.1 e SOAP 1.2.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-186">The `mustUnderstand` header value differs between SOAP 1.1 and SOAP 1.2.</span></span> <span data-ttu-id="b6e1c-187">Basic Profile 1.1 richiede che il valore di `mustUnderstand` sia 0 o 1 per i messaggi SOAP 1.1.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-187">Basic Profile 1.1 requires that the `mustUnderstand` value be 0 or 1 for SOAP 1.1 messages.</span></span> <span data-ttu-id="b6e1c-188">La specifica di SOAP 1.2, oltre ai valori 0 e 1, prevede inoltre i valori `false` e `true`. Tuttavia, tale specifica consiglia di applicare una rappresentazione canonica dei valori `xs:boolean`, ovvero `false` e `true`.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-188">SOAP 1.2 allows 0, 1, `false`, and `true` as values, but recommends emitting a canonical representation of `xs:boolean` values (`false`, `true`).</span></span>  
  
-   <span data-ttu-id="b6e1c-189">B1112: in entrambe le versioni 1.1 e 1.2 della SOAP envelope, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] genera i valori 0 e 1 per `mustUnderstand`.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-189">B1112: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] emits `mustUnderstand` values 0 and 1 for both SOAP 1.1 and SOAP 1.2 versions of the SOAP envelope.</span></span> <span data-ttu-id="b6e1c-190">Inoltre, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] accetta l'intero spazio dei valori `xs:boolean` per l'intestazione `mustUnderstand`, ovvero, 0, 1, `false` e `true`.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-190">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] accepts the entire value space of `xs:boolean` for the `mustUnderstand` header (0, 1, `false`, `true`)</span></span>  
  
#### <a name="soap-faults"></a><span data-ttu-id="b6e1c-191">Errori SOAP</span><span class="sxs-lookup"><span data-stu-id="b6e1c-191">SOAP Faults</span></span>  
 <span data-ttu-id="b6e1c-192">L'elenco seguente contiene le implementazioni degli errori SOAP specifiche di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b6e1c-192">The following is a list of [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-specific SOAP fault implementations.</span></span>  
  
-   <span data-ttu-id="b6e1c-193">B2121: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] restituisce i seguenti codici di errore SOAP 1.1: `s11:mustUnderstand`, `s11:Client`, e `s11:Server`.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-193">B2121: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] returns the following SOAP 1.1 Fault Codes: `s11:mustUnderstand`, `s11:Client`, and `s11:Server`.</span></span>  
  
-   <span data-ttu-id="b6e1c-194">B2122: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] restituisce i codici di errore SOAP 1.2 seguenti: `s12:MustUnderstand`, `s12:Sender`e `s12:Receiver`.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-194">B2122: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] returns the following SOAP 1.2 Fault Codes: `s12:MustUnderstand`, `s12:Sender`, and `s12:Receiver`.</span></span>  
  
### <a name="http-binding"></a><span data-ttu-id="b6e1c-195">Associazione HTTP</span><span class="sxs-lookup"><span data-stu-id="b6e1c-195">HTTP Binding</span></span>  
  
#### <a name="soap-11-http-binding"></a><span data-ttu-id="b6e1c-196">Associazione SOAP 1,1 HTTP</span><span class="sxs-lookup"><span data-stu-id="b6e1c-196">SOAP 1.1 HTTP Binding</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="b6e1c-197"> implementa l'associazione SOAP 1.1 HTTP attenendosi alla sezione 3.4 della specifica Basic Profile 1.1, con le precisazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b6e1c-197"> implements SOAP1.1 HTTP binding following the Basic Profile 1.1 specification section 3.4 with the following clarifications:</span></span>  
  
-   <span data-ttu-id="b6e1c-198">B2211: il servizio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] non implementa il reindirizzamento di richieste HTTP POST.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-198">B2211: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service does not implement redirection of HTTP POST requests.</span></span>  
  
-   <span data-ttu-id="b6e1c-199">B2212: i client [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] supportano i cookie HTTP in conformità alla sezione 3.4.8.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-199">B2212: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] clients support HTTP Cookies in accordance with 3.4.8.</span></span>  
  
#### <a name="soap-12-http-binding"></a><span data-ttu-id="b6e1c-200">Associazione SOAP 1,2 HTTP</span><span class="sxs-lookup"><span data-stu-id="b6e1c-200">SOAP 1.2 HTTP Binding</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="b6e1c-201"> implementa l'associazione SOAP 1.2 HTTP attenendosi alla specifica SOAP 1.2-part 2 (SOAP12Part2), con le precisazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b6e1c-201"> implements SOAP 1.2 HTTP binding as described in the SOAP 1.2-part 2 (SOAP12Part2) specification with the following clarifications.</span></span>  
  
 <span data-ttu-id="b6e1c-202">SOAP 1.2 introduce un nuovo parametro Action facoltativo per il tipo di supporto `application/soap+xml`.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-202">SOAP 1.2 introduced an optional action parameter for the `application/soap+xml` media type.</span></span> <span data-ttu-id="b6e1c-203">Questo parametro è utile per ottimizzare l'invio dei messaggi in quanto elimina l'esigenza di analizzare il corpo del messaggio SOAP quando non si utilizza la specifica WS-Addressing.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-203">This parameter is useful to optimize message dispatch without requiring that the body of the SOAP message be parsed when WS-Addressing is not used.</span></span>  
  
-   <span data-ttu-id="b6e1c-204">R2221: il parametro Action `application/soap+xml`, quando presente in una richiesta SOAP 1.2, deve corrispondere all'attributo `soapAction` dell'elemento `wsoap12:operation` contenuto nell'associazione WSDL corrispondente.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-204">R2221: The `application/soap+xml` action parameter, when present on a SOAP 1.2 request, must match the `soapAction` attribute on the `wsoap12:operation` element inside the corresponding WSDL binding.</span></span>  
  
-   <span data-ttu-id="b6e1c-205">R2222: il parametro Action `application/soap+xml`, quando presente in un messaggio SOAP 1.2, deve corrispondere all'elemento `wsa:Action` quando si utilizza la specifica WS-Addressing 2004/08 o la specifica WS-Addressing 1.0.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-205">R2222: The `application/soap+xml` action parameter, when present on a SOAP 1.2 message, must match `wsa:Action` when WS-Addressing 2004/08 or WS-Addressing 1.0 are used.</span></span>  
  
 <span data-ttu-id="b6e1c-206">Quando la specifica WS-Addressing è disabilitata e in una richiesta in ingresso non è incluso alcun parametro Action, il parametro `Action` del messaggio viene considerato come non specificato.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-206">When WS-Addressing is disabled and an incoming request does not contain an action parameter, message `Action` is considered not specified.</span></span>  
  
## <a name="ws-addressing"></a><span data-ttu-id="b6e1c-207">WS-Addressing</span><span class="sxs-lookup"><span data-stu-id="b6e1c-207">WS-Addressing</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="b6e1c-208"> consente di implementare 3 versioni di WS-Addressing:</span><span class="sxs-lookup"><span data-stu-id="b6e1c-208"> implements 3 versions of WS-Addressing:</span></span>  
  
-   <span data-ttu-id="b6e1c-209">WS-Addressing 2004/08</span><span class="sxs-lookup"><span data-stu-id="b6e1c-209">WS-Addressing 2004/08</span></span>  
  
-   <span data-ttu-id="b6e1c-210">Specifica di base di W3C Web Services Addressing 1.0 (ADDR10-CORE) e associazione SOAP (ADDR10-SOAP)</span><span class="sxs-lookup"><span data-stu-id="b6e1c-210">W3C Web Services Addressing 1.0 Core  (ADDR10-CORE) and SOAP Binding (ADDR10-SOAP)</span></span>  
  
-   <span data-ttu-id="b6e1c-211">WS-Addressing 1.0 - Metadata</span><span class="sxs-lookup"><span data-stu-id="b6e1c-211">WS-Addressing 1.0 - Metadata</span></span>  
  
### <a name="endpoint-references"></a><span data-ttu-id="b6e1c-212">Riferimenti a endpoint</span><span class="sxs-lookup"><span data-stu-id="b6e1c-212">Endpoint References</span></span>  
 <span data-ttu-id="b6e1c-213">In tutte le versioni di WS-Addressing implementate da [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] vengono utilizzati i riferimenti a endpoint per descrivere gli endpoint.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-213">All versions of WS-Addressing that [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] implements use endpoint references to describe endpoints.</span></span>  
  
#### <a name="endpoint-references-and-ws-addressing-versions"></a><span data-ttu-id="b6e1c-214">Utilizzo dei riferimenti a endpoint con le versioni di WS-Addressing</span><span class="sxs-lookup"><span data-stu-id="b6e1c-214">Endpoint References and WS-Addressing Versions</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="b6e1c-215"> implementa diversi protocolli di infrastruttura (ad esempio WS-ReliableMessaging, WS-SecureConversation e WS-Trust) che utilizzano WS-Addressing e in particolare l'elemento `EndpointReference` e la classe `W3C.WsAddressing.EndpointReferenceType`.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-215"> implements a number of the infrastructure protocols that use WS-Addressing and in particular the `EndpointReference` element and `W3C.WsAddressing.EndpointReferenceType` class (for example, WS-ReliableMessaging, WS-SecureConversation, and WS-Trust).</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="b6e1c-216"> supporta l'utilizzo di una delle due versioni di WS-Addressing con gli altri protocolli di infrastruttura.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-216"> supports the use of either version of WS-Addressing with other infrastructure protocols.</span></span> <span data-ttu-id="b6e1c-217">Per ogni endpoint di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] è consentito utilizzare una sola versione di WS-Addressing.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-217">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] endpoints support one version of WS-Addressing per endpoint.</span></span>  
  
 <span data-ttu-id="b6e1c-218">R3111: lo spazio dei nomi dell'elemento `EndpointReference` o del tipo utilizzato nei messaggi scambiati con un endpoint di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] deve corrispondere alla versione di WS-Addressing implementata da tale endpoint.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-218">For R3111, the namespace for the `EndpointReference` element or type used in messages exchanged with a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] endpoint must match the version of WS-Addressing implemented by this endpoint.</span></span>  
  
 <span data-ttu-id="b6e1c-219">Ad esempio, se un endpoint di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] implementa il protocollo WS-ReliableMessaging, l'intestazione `AcksTo` restituita da tale endpoint nella risposta `CreateSequenceResponse` utilizza la versione di WS-Addressing specificata dall'associazione `EncodingBinding` per tale endpoint.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-219">For example, if a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] endpoint implements WS-ReliableMessaging, the `AcksTo` header returned by such an endpoint inside `CreateSequenceResponse` uses the WS-Addressing version that the `EncodingBinding` element specifies for this endpoint.</span></span>  
  
#### <a name="endpoint-references-and-metadata"></a><span data-ttu-id="b6e1c-220">Utilizzo dei riferimenti a endpoint con i metadati</span><span class="sxs-lookup"><span data-stu-id="b6e1c-220">Endpoint References and Metadata</span></span>  
 <span data-ttu-id="b6e1c-221">Diversi scenari richiedono la comunicazione di metadati o di riferimenti a metadati relativi a un dato endpoint.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-221">A number of scenarios require communicating metadata or a reference to metadata for a given endpoint.</span></span>  
  
 <span data-ttu-id="b6e1c-222">B3121: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] utilizza i meccanismi descritti nella sezione 6 della specifica MEX (WS-MetadataExchange) per includere metadati associati a riferimenti per valore o per riferimento a un determinato endpoint.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-222">B3121: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] employs mechanisms described in the WS-MetadataExchange (MEX) specification Section 6 to include metadata for endpoint references by value or by reference.</span></span>  
  
 <span data-ttu-id="b6e1c-223">Si consideri lo scenario in cui un servizio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] richiede l'autenticazione tramite un token SAML (Security Assertions Markup Language) emesso dall'emittente di token all'indirizzo http://sts.fabrikam123.com. L'endpoint [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] descrive questo requisito di autenticazione utilizzando un'asserzione `sp:IssuedToken` avente un'asserzione `sp:Issuer` annidata che punta all'emittente di token.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-223">Consider a scenario where a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service requires authentication using a Security Assertions Markup Language (SAML) token issued by the token issuer at http://sts.fabrikam123.com. The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] endpoint describes this authentication requirement by using `sp:IssuedToken` assertion with a nested `sp:Issuer` assertion pointing to the token issuer.</span></span> <span data-ttu-id="b6e1c-224">Le applicazioni client che accedono all'asserzione `sp:Issuer` devono conoscere la modalità di comunicazione con l'endpoint dell'emittente di token.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-224">Client applications that access the `sp:Issuer` assertion need to know how to communicate with the token issuer endpoint.</span></span> <span data-ttu-id="b6e1c-225">In particolare, il client deve conoscere i metadati relativi all'emittente di token.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-225">The client needs to know metadata about the token issuer.</span></span> <span data-ttu-id="b6e1c-226">Utilizzando le estensioni di metadati di riferimento a endpoint definite nel modello di scambio dei messaggi, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] fornisce un riferimento ai metadati dell'emittente di token.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-226">Using the endpoint reference metadata extensions defined in MEX, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] provides a reference to the token issuer metadata.</span></span>  
  
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
  
### <a name="message-addressing-headers"></a><span data-ttu-id="b6e1c-227">Intestazioni di indirizzamento dei messaggi</span><span class="sxs-lookup"><span data-stu-id="b6e1c-227">Message Addressing Headers</span></span>  
  
#### <a name="message-headers"></a><span data-ttu-id="b6e1c-228">Intestazioni del messaggio</span><span class="sxs-lookup"><span data-stu-id="b6e1c-228">Message Headers</span></span>  
 <span data-ttu-id="b6e1c-229">Per entrambe le versioni di WS-Addressing, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] utilizza le seguenti intestazioni del messaggio come previsto dalle specifiche `wsa:To`, `wsa:ReplyTo`, `wsa:Action`, `wsa:MessageID`, e `wsa:RelatesTo`.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-229">For both WS-Addressing versions, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] uses the following message headers as prescribed by the specifications `wsa:To`, `wsa:ReplyTo`, `wsa:Action`, `wsa:MessageID`,and `wsa:RelatesTo`.</span></span>  
  
 <span data-ttu-id="b6e1c-230">B3211: per tutte le versioni di WS-Addressing, in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] vengono rispettate, senza tuttavia crearle da zero, le intestazioni di messaggio di WS-Addressing `wsa:FaultTo` e `wsa:From`.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-230">B3211: For all WS-Addressing versions, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] honors, but does not produce out of the box, WS-Addressing message headers `wsa:FaultTo` and `wsa:From`.</span></span>  
  
 <span data-ttu-id="b6e1c-231">Le applicazioni che interagiscono con le applicazioni [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] possono aggiungere queste intestazioni di messaggio, che quindi verranno elaborate di conseguenza da [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b6e1c-231">Applications that interact with [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] applications can add these message headers and [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] will process them accordingly.</span></span>  
  
#### <a name="reference-parameters-and-properties"></a><span data-ttu-id="b6e1c-232">Parametri e proprietà dei riferimenti</span><span class="sxs-lookup"><span data-stu-id="b6e1c-232">Reference Parameters and Properties</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="b6e1c-233"> implementa l'elaborazione dei parametri e delle proprietà dei riferimenti a endpoint</span><span class="sxs-lookup"><span data-stu-id="b6e1c-233"> implements processing of endpoint reference parameters and reference p</span></span>  
  
 <span data-ttu-id="b6e1c-234">in conformità alle rispettive specifiche.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-234">roperties in accordance with respective specifications.</span></span>  
  
 <span data-ttu-id="b6e1c-235">B3221: quando configurati per utilizzare la specifica WS-Addressing 2004/08, gli endpoint di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] elaborano le proprietà dei riferimenti e i parametri dei riferimenti allo stesso modo.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-235">B3221: When configured to use WS-Addressing 2004/08, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] endpoints do not differentiate between processing Reference Properties and Reference Parameters.</span></span>  
  
### <a name="message-exchange-patterns"></a><span data-ttu-id="b6e1c-236">Modelli di scambio dei messaggi</span><span class="sxs-lookup"><span data-stu-id="b6e1c-236">Message Exchange Patterns</span></span>  
 <span data-ttu-id="b6e1c-237">La sequenza dei messaggi coinvolti nella chiamata all'operazione del servizio Web è detta il *MEP*.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-237">The sequence of messages involved in the Web service operation invocation is referred to as the *message exchange pattern*.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="b6e1c-238"> supporta i modelli di scambio dei messaggi request/reply, unidirezionale e duplex.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-238"> supports one-way, request-reply, and duplex message exchange patterns.</span></span> <span data-ttu-id="b6e1c-239">Questa sezione descrive i requisiti della specifica WS-Addressing che definiscono il modo in cui il modello di scambio dei messaggi utilizzato influisce sull'elaborazione dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-239">This section clarifies WS-Addressing requirements on message processing depending on the message exchange pattern being used.</span></span>  
  
 <span data-ttu-id="b6e1c-240">Contenuto della sezione, il richiedente invia il primo messaggio e il risponditore riceve il primo messaggio.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-240">Throughout this section, the requester sends the first message and the responder receives the first message.</span></span>  
  
#### <a name="one-way-message"></a><span data-ttu-id="b6e1c-241">Modello unidirezionale</span><span class="sxs-lookup"><span data-stu-id="b6e1c-241">One-Way Message</span></span>  
 <span data-ttu-id="b6e1c-242">Quando un endpoint di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] viene configurato per supportare messaggi aventi un determinato parametro `Action` in modo da applicare un modello unidirezionale, tale endpoint di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] si attiene ai comportamenti e ai requisiti elencati di seguito.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-242">When a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] endpoint is configured to support messages with a given `Action` to follow a one-way pattern, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] endpoint follows the following behaviors and requirements.</span></span> <span data-ttu-id="b6e1c-243">A meno che non vengano specificati diversamente, i comportamenti e le regole riguardano entrambe le versioni di WS-Addressing supportate in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="b6e1c-243">Unless otherwise specified, behaviors and rules apply for both versions of WS-Addressing supported in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]:</span></span>  
  
-   <span data-ttu-id="b6e1c-244">R3311: il richiedente deve includere gli elementi `wsa:To` e `wsa:Action` nonché le intestazioni di tutti i parametri specificati nel riferimento a endpoint.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-244">R3311: The requester must include `wsa:To`, `wsa:Action`, and headers for all reference parameters specified by the endpoint reference.</span></span> <span data-ttu-id="b6e1c-245">Quando si utilizza la specifica WS-Addressing 2004/08 e il riferimento a endpoint specifica le proprietà di riferimento [reference properties], occorre aggiungere al messaggio anche le intestazioni corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-245">When WS-Addressing 2004/08 is used and [reference properties] are specified by the endpoint reference, the corresponding headers must be added to the message too.</span></span>  
  
-   <span data-ttu-id="b6e1c-246">B3312: il richiedente può includere le intestazioni `MessageID` e `ReplyTo` e `FaultTo`.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-246">B3312: The requester may include `MessageID`, `ReplyTo`, and `FaultTo` headers.</span></span> <span data-ttu-id="b6e1c-247">Dopo essere stati ignorati dall'infrastruttura del destinatario, questi elementi vengono passati all'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-247">The receiver infrastructure will ignore them, and they will be passed to the application.</span></span>  
  
-   <span data-ttu-id="b6e1c-248">R3313: quando si utilizza il protocollo HTTP e non viene inviato alcun messaggio sul canale di risposta HTTP, il risponditore deve inviare una risposta HTTP contenente un corpo vuoto e un codice di stato HTTP 202.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-248">R3313: When HTTP is used and no message is being sent on the HTTP response leg, the responder must send an HTTP response with an empty body and an HTTP 202 status code.</span></span>  
  
     <span data-ttu-id="b6e1c-249">Quando si utilizza il trasporto HTTP e il contratto dell'operazione dichiara un messaggio unidirezionale, la risposta HTTP può comunque essere utilizzata per l'invio di messaggi di infrastruttura. Ad esempio, la funzionalità di messaggistica affidabile può inviare un messaggio `SequenceAcknowledgement` in una risposta HTTP.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-249">When the HTTP transport is in use and the operation contract declares a message one-way, the HTTP response can still be used for sending infrastructure messages—for example, reliable messaging can send a `SequenceAcknowledgement` message on an HTTP response.</span></span>  
  
-   <span data-ttu-id="b6e1c-250">B3314: il risponditore [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] non invia alcun messaggio di errore in risposta a un messaggio unidirezionale.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-250">B3314: The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] responder does not send a fault message in response to a one-way message.</span></span>  
  
#### <a name="request-reply"></a><span data-ttu-id="b6e1c-251">Request/Reply</span><span class="sxs-lookup"><span data-stu-id="b6e1c-251">Request-Reply</span></span>  
 <span data-ttu-id="b6e1c-252">Quando un endpoint di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] viene configurato per supportare messaggi aventi un determinato parametro `Action` in modo da applicare un modello richiesta-risposta, tale endpoint di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] si attiene ai comportamenti e ai requisiti elencati di seguito.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-252">When a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] endpoint is configured for a message with a given `Action` to follow the request-reply pattern, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] endpoint follows the behaviors and requirements below.</span></span> <span data-ttu-id="b6e1c-253">A meno che non vengano specificati diversamente, i comportamenti e le regole riguardano entrambe le versioni di WS-Addressing supportate in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="b6e1c-253">Unless specified otherwise, behaviors and rules apply for both versions of WS-Addressing supported in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]:</span></span>  
  
-   <span data-ttu-id="b6e1c-254">R3321: Il richiedente deve includere nella richiesta `wsa:To`, `wsa:Action`, `wsa:MessageID`, nonché le intestazioni di tutti i parametri di riferimento o riferimento proprietà (o entrambi) specificati nel riferimento endpoint.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-254">R3321: The requester must include in the request `wsa:To`, `wsa:Action`, `wsa:MessageID`, and headers for all reference parameters or reference properties (or both) specified by the endpoint reference.</span></span>  
  
-   <span data-ttu-id="b6e1c-255">R3322: quando si utilizza la specifica WS-Addressing 2004/08, nella richiesta deve essere incluso anche l'elemento `ReplyTo`.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-255">R3322: When WS-Addressing 2004/08 is used, `ReplyTo` must also be included in the request.</span></span>  
  
-   <span data-ttu-id="b6e1c-256">R3323: se quando si utilizza la specifica WS-Addressing 1.0 la richiesta non contiene alcun elemento `ReplyTo`, tale elemento viene impostato su un riferimento a endpoint predefinito in cui la proprietà [address] è uguale a "http://www.w3.org/2005/08/addressing/anonymous".</span><span class="sxs-lookup"><span data-stu-id="b6e1c-256">R3323: When WS-Addressing 1.0 is used and `ReplyTo` is not present in the request, a default endpoint reference with the [address] property equal to "http://www.w3.org/2005/08/addressing/anonymous" is used.</span></span>  
  
-   <span data-ttu-id="b6e1c-257">R3324: Il richiedente deve includere `wsa:To`, `wsa:Action`, e `wsa:RelatesTo` intestazioni nel messaggio di risposta, nonché le intestazioni di tutti i parametri di riferimento riferimento proprietà (o entrambi) specificato per il `ReplyTo` riferimento dell'endpoint nel richiesta.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-257">R3324: The requester must include `wsa:To`, `wsa:Action`, and `wsa:RelatesTo` headers in the reply message, as well as headers for all reference parameters or reference properties (or both) specified by the `ReplyTo` endpoint reference in the request.</span></span>  
  
### <a name="web-services-addressing-faults"></a><span data-ttu-id="b6e1c-258">Errori di indirizzamento dei servizi Web</span><span class="sxs-lookup"><span data-stu-id="b6e1c-258">Web Services Addressing Faults</span></span>  
 <span data-ttu-id="b6e1c-259">R3411: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] genera gli errori seguenti definiti nella specifica WS-Addressing 2004/08.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-259">R3411: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] produces the following faults defined by WS-Addressing 2004/08.</span></span>  
  
|<span data-ttu-id="b6e1c-260">Codice</span><span class="sxs-lookup"><span data-stu-id="b6e1c-260">Code</span></span>|<span data-ttu-id="b6e1c-261">Causa</span><span class="sxs-lookup"><span data-stu-id="b6e1c-261">Cause</span></span>|  
|----------|-----------|  
|<span data-ttu-id="b6e1c-262">wsa:DestinationUnreachable</span><span class="sxs-lookup"><span data-stu-id="b6e1c-262">wsa:DestinationUnreachable</span></span>|<span data-ttu-id="b6e1c-263">Il messaggio in ingresso presenta un riferimento `ReplyTo` diverso dall'indirizzo per risposte definito per questo canale. Non esiste alcun endpoint in attesa presso l'indirizzo specificato nell'intestazione di destinazione.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-263">The message arrived with a `ReplyTo` that is different from the reply address established for this channel; there is no endpoint listening at the address specified in the To header.</span></span>|  
|<span data-ttu-id="b6e1c-264">wsa:ActionNotSupported</span><span class="sxs-lookup"><span data-stu-id="b6e1c-264">wsa:ActionNotSupported</span></span>|<span data-ttu-id="b6e1c-265">I canali dell'infrastruttura o il dispatcher associato all'endpoint non riconoscono l'azione specificata nell'intestazione `Action`.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-265">the infrastructure channels or dispatcher associated with the endpoint do not recognize the action specified in the `Action` header.</span></span>|  
  
 <span data-ttu-id="b6e1c-266">R3412: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] genera gli errori seguenti definiti nella specifica WS-Addressing 1.0.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-266">R3412: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] produces the following faults defined by WS-Addressing 1.0.</span></span>  
  
|<span data-ttu-id="b6e1c-267">Codice</span><span class="sxs-lookup"><span data-stu-id="b6e1c-267">Code</span></span>|<span data-ttu-id="b6e1c-268">Causa</span><span class="sxs-lookup"><span data-stu-id="b6e1c-268">Cause</span></span>|  
|----------|-----------|  
|<span data-ttu-id="b6e1c-269">wsa10:InvalidAddressingHeader</span><span class="sxs-lookup"><span data-stu-id="b6e1c-269">wsa10:InvalidAddressingHeader</span></span>|<span data-ttu-id="b6e1c-270">Duplicare `wsa:To`, `wsa:ReplyTo`, `wsa:From` o `wsa:MessageID`.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-270">Duplicate `wsa:To`, `wsa:ReplyTo`, `wsa:From` or `wsa:MessageID`.</span></span> <span data-ttu-id="b6e1c-271">Duplicare `wsa:RelatesTo` con lo stesso `RelationshipType`.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-271">Duplicate `wsa:RelatesTo` with the same `RelationshipType`.</span></span>|  
|<span data-ttu-id="b6e1c-272">wsa10:MessageAddressingHeaderRequired</span><span class="sxs-lookup"><span data-stu-id="b6e1c-272">wsa10:MessageAddressingHeaderRequired</span></span>|<span data-ttu-id="b6e1c-273">L'intestazione obbligatoria di indirizzamento è mancante.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-273">The required Addressing header is missing.</span></span>|  
|<span data-ttu-id="b6e1c-274">wsa10:DestinationUnreachable</span><span class="sxs-lookup"><span data-stu-id="b6e1c-274">wsa10:DestinationUnreachable</span></span>|<span data-ttu-id="b6e1c-275">Il messaggio in ingresso presenta un riferimento `ReplyTo` diverso dall'indirizzo per risposte definito per questo canale.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-275">The message arrived with a `ReplyTo` that is different from the reply address established for this channel.</span></span> <span data-ttu-id="b6e1c-276">Non esiste alcun endpoint in attesa presso l'indirizzo specificato nell'intestazione di destinazione.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-276">There is no endpoint listening at the address specified in the To header.</span></span>|  
|<span data-ttu-id="b6e1c-277">wsa10:ActionNotSupported</span><span class="sxs-lookup"><span data-stu-id="b6e1c-277">wsa10:ActionNotSupported</span></span>|<span data-ttu-id="b6e1c-278">I canali dell'infrastruttura o il dispatcher associato all'endpoint non riconoscono l'azione specificata nell'intestazione `Action`.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-278">An action specified in the `Action` header is not recognized by the infrastructure channels or dispatcher associated with the endpoint.</span></span>|  
|<span data-ttu-id="b6e1c-279">wsa10:EndpointUnavailable</span><span class="sxs-lookup"><span data-stu-id="b6e1c-279">wsa10:EndpointUnavailable</span></span>|<span data-ttu-id="b6e1c-280">Il canale RM restituisce questo errore per indicare che l'endpoint non elaborerà la sequenza basata sull'esame delle intestazioni di indirizzamento del messaggio `CreateSequence`.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-280">The RM channel sends this fault back, indicating the endpoint will not process the sequence based upon examination of the `CreateSequence` message’s addressing headers.</span></span>|  
  
 <span data-ttu-id="b6e1c-281">Il codice delle tabelle precedenti viene mappato al codice `FaultCode` in SOAP 1.1 e al codice `SubCode` (in cui il codice corrisponde al mittente) in SOAP 1.2.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-281">Code in the preceding tables maps to `FaultCode` in SOAP 1.1 and `SubCode` (with Code=Sender) in SOAP 1.2.</span></span>  
  
### <a name="wsdl-11-binding-and-ws-policy-assertions"></a><span data-ttu-id="b6e1c-282">Utilizzo di associazioni WSDL 1.1 con le asserzioni di WS-Policy</span><span class="sxs-lookup"><span data-stu-id="b6e1c-282">WSDL 1.1 Binding and WS-Policy Assertions</span></span>  
  
#### <a name="indicating-use-of-ws-addressing"></a><span data-ttu-id="b6e1c-283">Definizione dell'uso di WS-Addressing</span><span class="sxs-lookup"><span data-stu-id="b6e1c-283">Indicating Use of WS-Addressing</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="b6e1c-284"> utilizza le asserzioni di criteri per indicare il supporto di endpoint relativamente a una determinata versione di WS-Addressing.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-284"> uses policy assertions to indicate endpoint support for a particular WS-Addressing version.</span></span>  
  
 <span data-ttu-id="b6e1c-285">L'asserzione di criteri seguente contiene il soggetto dei criteri di endpoint [WS-PA] e indica che i messaggi scambiati con l'endpoint devono utilizzare la specifica WS-Addressing 2004/08.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-285">The following policy assertion has Endpoint Policy Subject [WS-PA] and indicates messages sent and received from the endpoint must use WS-Addressing 2004/08.</span></span>  
  
```xml  
<wsap:UsingAddressing />  
```  
  
 <span data-ttu-id="b6e1c-286">Questa asserzione di criteri si aggiunge alla specifica WS-Addressing 2004/08.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-286">This policy assertion augments the WS-Addressing 2004/08 specification.</span></span>  
  
 <span data-ttu-id="b6e1c-287">Tramite l'asserzione di criteri seguente viene indicato che nei messaggi inviati/ricevuti deve essere utilizzato WS-Addressing 1.0.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-287">The following policy assertion this indicates that messages sent/received must use WS-Addressing 1.0.</span></span>  
  
```xml
<wsam:Addressing/>   
```  
  
 <span data-ttu-id="b6e1c-288">Nell'asserzione di criteri seguente è incluso un soggetto dei criteri di endpoint [WS-PA] e viene indicato che nei messaggi scambiati con l'endpoint deve essere utilizzata la specifica WS-Addressing 2004/08.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-288">The following policy assertion has an Endpoint Policy Subject [WS-PA] and indicates that messages sent and received from the endpoint must use WS-Addressing 2004/08.</span></span>  
  
```xml  
<wsaw10:UsingAddressing />  
```  
  
 <span data-ttu-id="b6e1c-289">L'elemento `wsaw10:UsingAddressing` è preso in prestito da [WS-Addressing-WSDL] e viene utilizzato nel contesto di WS-Policy in conformità alla sezione 3.1.2 di tale specifica.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-289">The `wsaw10:UsingAddressing` element is borrowed from [WS-Addressing-WSDL] and is used in the context of WS-Policy in compliance with that specification, section 3.1.2.</span></span>  
  
 <span data-ttu-id="b6e1c-290">L'utilizzo dell'intestazione di indirizzamento non modifica la semantica delle associazioni WSDL 1.1 HTTP, SOAP 1.1 HTTP e SOAP 1.2 HTTP.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-290">Use of Addressing does not alter the semantics of WSDL 1.1, SOAP 1.1, and SOAP 1.2 HTTP Bindings.</span></span> <span data-ttu-id="b6e1c-291">Ad esempio, se si prevede una risposta a una richiesta inviata a un endpoint in cui vengono utilizzati WS-Addressing e l'associazione WSDL SOAP 1.x HTTP, la risposta deve essere inviata tramite la risposta HTTP.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-291">For example, if a reply is expected to a request that is sent to an endpoint that uses Addressing and WSDL SOAP 1.x HTTP binding, the reply must be sent by using the HTTP response.</span></span>  
  
 <span data-ttu-id="b6e1c-292">Per le risposte inviate tramite la risposta http, l'asserzione WS-AM è:</span><span class="sxs-lookup"><span data-stu-id="b6e1c-292">For replies sent over the http response, the WS-AM assertion is:</span></span>  
  
```xml  
<wsam:AnonymousResponses/>  
```  
  
 <span data-ttu-id="b6e1c-293">L'asserzione di criteri completa potrebbe essere simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="b6e1c-293">The complete policy assertion might look like this:</span></span>  
  
```xml  
<wsam:Addressing>  
    <wsp:Policy>  
        <wsam:AnonymousResponses />   
    </wsp:Policy>  
</wsam:Addressing>  
```  
  
 <span data-ttu-id="b6e1c-294">Tuttavia, sono presenti modelli di scambio dei messaggi che traggono profitto dalla presenza di due connessioni HTTP opposte indipendenti stabilite tra il richiedente e il risponditore, ad esempio i messaggi unidirezionali non richiesti inviati dal risponditore.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-294">However, there are message exchange patterns that benefit from having two independent converse HTTP connections established between the requester and the responder, for example, unsolicited one-way messages sent by the responder.</span></span>  
  
 <span data-ttu-id="b6e1c-295">In [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] è disponibile una funzionalità grazie alle quale due canali di trasporto sottostanti possono formare un canale duplex composito in cui un canale viene utilizzato per i messaggi di input e l'altro per quelli di output.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-295">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] offers a feature by which two underlying transport channels can form a Composite Duplex channel, where one channel is used for input messages and the other is used for output messages.</span></span> <span data-ttu-id="b6e1c-296">Nel caso del trasporto HTTP, il modello duplex composito offre due connessioni HTTP opposte.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-296">In the case of the HTTP Transport, Composite Duplex provides two converse HTTP connections.</span></span> <span data-ttu-id="b6e1c-297">Il richiedente utilizza una connessione per inviare i messaggi al risponditore, mentre quest'ultimo utilizza l'altra connessione per inviare i messaggi di risposta al richiedente.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-297">The requester uses one connection to send messages to the responder, and the responder uses the other to send messages back to the requester.</span></span>  
  
 <span data-ttu-id="b6e1c-298">Per le risposte inviate tramite richieste http distinte, l'asserzione ws-am è:</span><span class="sxs-lookup"><span data-stu-id="b6e1c-298">For replies sent over separate http requests, the ws-am assertion is</span></span>  
  
```xml  
<wsam:NonAnonymousResponses/>  
```  
  
 <span data-ttu-id="b6e1c-299">L'asserzione di criteri completa potrebbe essere simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="b6e1c-299">The complete policy assertion might look like this:</span></span>  
  
```xml  
<wsam:Addressing>  
    <wsp:Policy>  
      <wsam:NonAnonymousResponses />   
   </wsp:Policy>  
  </wsam:Addressing>  
```  
  
 <span data-ttu-id="b6e1c-300">Per l'utilizzo dell'asserzione seguente che presenta il soggetto dei criteri di endpoint [WS-PA] negli endpoint in cui vengono utilizzate le associazioni SOAP 1.x HTTP WSDL 1.1 sono richieste due connessioni HTTP opposte e distinte da utilizzare rispettivamente per i messaggi dal richiedente al risponditore e dal risponditore al richiedente.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-300">Use of the following assertion that has Endpoint Policy Subject [WS-PA] on endpoints that use WSDL 1.1 SOAP 1.x HTTP bindings requires two separate converse HTTP connections to be used for messages flowing from requester to responder and responder to requester, respectively.</span></span>  
  
```xml  
<cdp:CompositeDuplex/>  
```  
  
 <span data-ttu-id="b6e1c-301">L'istruzione precedente comporta i requisiti seguenti per l'intestazione `wsa:ReplyTo` dei messaggi di richiesta:</span><span class="sxs-lookup"><span data-stu-id="b6e1c-301">The previous statement leads to the following requirements on the `wsa:ReplyTo` header for request messages:</span></span>  
  
-   <span data-ttu-id="b6e1c-302">R3514: se l'endpoint utilizza un'associazione WSDL 1.1 SOAP 1.x HTTP e dispone di un'alternativa criteri avente un'asserzione `ReplyTo` o un'asserzione `[address]` associata a un elemento `wsap10:UsingAddressing`, i messaggi di richiesta inviati a un endpoint devono presentare un'intestazione `wsap:UsingAddressing` in cui la proprietà `cdp:CompositeDuplex` sia diversa da "http://www.w3.org/2005/08/addressing/anonymous".</span><span class="sxs-lookup"><span data-stu-id="b6e1c-302">R3514: Request messages sent to an endpoint must have a `ReplyTo` header with the `[address]` property not equal to "http://www.w3.org/2005/08/addressing/anonymous" if the endpoint uses a WSDL 1.1 SOAP 1.x HTTP binding and has a policy alternative with a `wsap10:UsingAddressing` or `wsap:UsingAddressing` assertion coupled with `cdp:CompositeDuplex` attached.</span></span>  
  
-   <span data-ttu-id="b6e1c-303">R3515: se l'endpoint utilizza un'associazione WSDL 1.1 SOAP 1.x HTTP e dispone di un'alternativa criteri avente un'asserzione `ReplyTo` senza alcuna asserzione `[address]` associata, i messaggi di richiesta inviati a un endpoint non devono presentare alcuna intestazione `ReplyTo` oppure devono presentare un'intestazione `wsap10:UsingAddressing` in cui la proprietà `cdp:CompositeDuplex` sia uguale a "http://www.w3.org/2005/08/addressing/anonymous".</span><span class="sxs-lookup"><span data-stu-id="b6e1c-303">R3515: Request messages sent to an endpoint must have a `ReplyTo` header with the `[address]` property equal to "http://www.w3.org/2005/08/addressing/anonymous", or not have a `ReplyTo` header at all, if the endpoint uses a WSDL 1.1 SOAP 1.x HTTP binding and has a policy alternative with `wsap10:UsingAddressing` assertion and no `cdp:CompositeDuplex` assertion attached.</span></span>  
  
-   <span data-ttu-id="b6e1c-304">R3516: se l'endpoint utilizza un'associazione WSDL 1.1 SOAP 1.x HTTP e dispone di un'alternativa criteri avente un'asserzione `ReplyTo` e nessun elemento `[address]` associato, i messaggi di richiesta inviati a un endpoint devono presentare un'intestazione `wsap:UsingAddressing` in cui la proprietà `cdp:CompositeDuplex` sia uguale a "http://www.w3.org/2005/08/addressing/anonymous".</span><span class="sxs-lookup"><span data-stu-id="b6e1c-304">R3516: Request messages sent to an endpoint must have a `ReplyTo` header with an `[address]` property equal to "http://www.w3.org/2005/08/addressing/anonymous" if the endpoint uses a WSDL 1.1 SOAP 1.x HTTP binding and has a policy alternative with `wsap:UsingAddressing` assertion and no `cdp:CompositeDuplex` assertion attached.</span></span>  
  
 <span data-ttu-id="b6e1c-305">La specifica WS-Addressing WSDL tenta di descrivere associazioni del protocollo simili introducendo un elemento `<wsaw:Anonymous/>` con tre valori testuali (obbligatorio, facoltativo e proibito) per indicare requisiti nell'intestazione `wsa:ReplyTo` (sezione 3.2).</span><span class="sxs-lookup"><span data-stu-id="b6e1c-305">The WS-addressing WSDL specification attempts to describe similar protocol bindings by introducing an element `<wsaw:Anonymous/>` with three textual values (required, optional, and prohibited) to indicate requirements on the `wsa:ReplyTo` header (section 3.2).</span></span> <span data-ttu-id="b6e1c-306">Sfortunatamente, tale definizione dell'elemento non è utilizzabile in modo specifico nel contesto di WS-Policy, perché richiede estensioni specifiche di dominio per supportare l'intersezione di alternative che utilizzano tale elemento come asserzione.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-306">Unfortunately, such element definition is not particularly usable as an assertion in the context of WS-Policy, because it requires domain-specific extensions to support the intersection of alternatives using such an element as an assertion.</span></span> <span data-ttu-id="b6e1c-307">A differenza del comportamento di endpoint in transito, che rende il valore dell'intestazione `ReplyTo` specifico del trasporto HTTP, il suddetto elemento indica questo valore senza associarlo a un determinato protocollo.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-307">Such element definition also indicates the value of the `ReplyTo` header as opposed to the endpoint behavior on the wire, which makes it specific to HTTP transport.</span></span>  
  
#### <a name="action-definition"></a><span data-ttu-id="b6e1c-308">Definizione dell'attributo Action</span><span class="sxs-lookup"><span data-stu-id="b6e1c-308">Action Definition</span></span>  
 <span data-ttu-id="b6e1c-309">La specifica WS-Addressing 2004/08 definisce un attributo `wsa:Action` per gli elementi `wsdl:portType/wsdl:operation/[wsdl:input | wsdl:output | wsdl:fault]`.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-309">WS-Addressing 2004/08 defines a `wsa:Action` attribute for the `wsdl:portType/wsdl:operation/[wsdl:input | wsdl:output | wsdl:fault]` elements.</span></span> <span data-ttu-id="b6e1c-310">L'associazione WS-Addressing 1.0 WSDL (WS-ADDR10-WSDL) definisce un attributo simile, ovvero `wsaw10:Action`.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-310">WS-Addressing 1.0 WSDL Binding (WS-ADDR10-WSDL) defines a similar attribute, `wsaw10:Action`.</span></span>  
  
 <span data-ttu-id="b6e1c-311">L'unica differenza consiste nella semantica del modello Action predefinito, descritta rispettivamente nella sezione 3.3.2 della specifica WS-ADDR e nella sezione 4.4.4 della specifica WS-ADDR10-WSDL.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-311">The only difference between the two is the default Action pattern semantics described in section 3.3.2 of WS-ADDR and section 4.4.4 of WS-ADDR10-WSDL, respectively.</span></span>  
  
 <span data-ttu-id="b6e1c-312">È ammissibile avere due endpoint aventi lo stesso attributo `portType` (ossia lo stesso contratto, usando la terminologia di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]) ma versioni diverse di WS-Addressing.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-312">It is a reasonable to have two endpoints that share the same `portType` (or contract, in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] terminology) but using different versions of WS-Addressing.</span></span> <span data-ttu-id="b6e1c-313">Tuttavia, se l'attributo Action è definito dall'attributo `portType` e deve essere condiviso da tutti gli endpoint che implementano l'attributo `portType`, risulta impossibile supportare entrambi i modelli Action predefiniti.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-313">But given that Action is defined by the `portType` and should not change across the endpoints that implement the `portType`, it becomes impossible to support both default action patterns.</span></span>  
  
 <span data-ttu-id="b6e1c-314">Per risolvere questa problematica, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] supporta una sola versione dell'attributo `Action`.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-314">To resolve this controversy, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] supports a single version of the `Action` attribute.</span></span>  
  
 <span data-ttu-id="b6e1c-315">B3521: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] utilizza l'attributo `wsaw10:Action` degli elementi `wsdl:portType/wsdl:operation/[wsdl:input | wsdl:output | wsdl:fault]` in conformità alla specifica WS-ADDR10-WSDL per determinare l'URI dell'attributo `Action` relativo ai messaggi corrispondenti indipendentemente dalla versione di WS-Addressing utilizzata dall'endpoint.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-315">B3521: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] uses the `wsaw10:Action` attribute on `wsdl:portType/wsdl:operation/[wsdl:input | wsdl:output | wsdl:fault]` elements as defined in WS-ADDR10-WSDL to determine the `Action` URI for the corresponding messages irrespective of the WS-Addressing version used by the endpoint.</span></span>  
  
#### <a name="use-endpoint-reference-inside-wsdl-port"></a><span data-ttu-id="b6e1c-316">Utilizzare il riferimento a endpoint nell'elemento wsdl:port</span><span class="sxs-lookup"><span data-stu-id="b6e1c-316">Use Endpoint Reference Inside WSDL Port</span></span>  
 <span data-ttu-id="b6e1c-317">La sezione 4.1 di WS-ADDR10-WSDL estende l'elemento `wsdl:port` per includere l'elemento figlio `<wsa10:EndpointReference…/>` allo scopo di descrivere l'endpoint in termini di WS-Addressing.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-317">WS-ADDR10-WSDL section 4.1 extends the `wsdl:port` element to include the `<wsa10:EndpointReference…/>` child element to describe the endpoint in WS-Addressing terms.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="b6e1c-318"> estende questa utilità in WS-Addressing 2004/08, consentendo di visualizzare `<wsa:EndpointReference…/>` come elemento figlio di `wsdl:port`.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-318"> expands this utility on WS-Addressing 2004/08, allowing `<wsa:EndpointReference…/>` to appear as a child element of `wsdl:port`.</span></span>  
  
-   <span data-ttu-id="b6e1c-319">R3531: se a un endpoint è associata un'alternativa criteri avente un'asserzione di criteri `<wsaw10:UsingAddressing/>`, l'elemento `wsdl:port` corrispondente può contenere un elemento figlio `<wsa10:EndpointReference …/>`.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-319">R3531: If an endpoint has an attached policy alternative with a `<wsaw10:UsingAddressing/>` policy assertion, the corresponding `wsdl:port` element can contain a child element `<wsa10:EndpointReference …/>`.</span></span>  
  
-   <span data-ttu-id="b6e1c-320">R3532: Se un `wsdl:port` contiene un elemento figlio `<wsa10:EndpointReference …/>`, `wsa10:EndpointReference/wsa10:Address` valore dell'elemento figlio deve corrispondere al valore del `@address` attributo di pari livello `wsdl:port` / `wsdl:location` elemento.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-320">R3532: If a `wsdl:port` contains a child element `<wsa10:EndpointReference …/>`, the `wsa10:EndpointReference/wsa10:Address` child element value must match the value of the `@address` attribute of the sibling `wsdl:port`/`wsdl:location` element.</span></span>  
  
-   <span data-ttu-id="b6e1c-321">R3533: se a un endpoint è associata un'alternativa criteri avente un'asserzione di criteri `<wsap:UsingAddressing/>`, l'elemento `wsdl:port` corrispondente può contenere un elemento figlio`<wsa:EndpointReference …/>`.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-321">R3533: If an endpoint has an attached policy alternative with `<wsap:UsingAddressing/>` policy assertion, the corresponding `wsdl:port` element can contain a child element `<wsa:EndpointReference …/>`.</span></span>  
  
-   <span data-ttu-id="b6e1c-322">R3534: Se un `wsdl:port` contiene un elemento figlio `<wsa:EndpointReference …/>`, `wsa:EndpointReference/wsa:Address` valore dell'elemento figlio deve corrispondere al valore del `@address` attributo di pari livello `wsdl:port` / `wsdl:location` elemento.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-322">R3534: If a `wsdl:port` contains a child element `<wsa:EndpointReference …/>`, the `wsa:EndpointReference/wsa:Address` child element value must match the value of the `@address` attribute of the sibling `wsdl:port`/`wsdl:location` element.</span></span>  
  
### <a name="composition-with-ws-security"></a><span data-ttu-id="b6e1c-323">Integrazione con WS-Security</span><span class="sxs-lookup"><span data-stu-id="b6e1c-323">Composition with WS-Security</span></span>  
 <span data-ttu-id="b6e1c-324">Secondo le sezioni di WS-ADDR e WS-ADDR10 relative alle considerazioni sulla sicurezza, è consigliabile firmare tutte le intestazioni dei messaggi di indirizzamento insieme al corpo del messaggio, in modo da associarli fra loro.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-324">According to security consideration sections in WS-ADDR and WS-ADDR10, all addressing message headers are recommended to be signed together with the message body to bind them together.</span></span>  
  
 <span data-ttu-id="b6e1c-325">Quando si utilizza WS-Security per garantire l'integrità dei messaggi, le intestazioni dei messaggi di WS-Addressing nonché le intestazioni ottenute dai parametri o dalle proprietà del riferimento (o da entrambi) devono essere firmate insieme al corpo del messaggio.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-325">When WS-Security is used for message integrity protection, WS-Addressing message headers as well as headers resulted from reference parameters or properties (or both) must be signed together with the body of the message.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="b6e1c-326">Esempi</span><span class="sxs-lookup"><span data-stu-id="b6e1c-326">Examples</span></span>  
  
#### <a name="one-way-message"></a><span data-ttu-id="b6e1c-327">Modello unidirezionale</span><span class="sxs-lookup"><span data-stu-id="b6e1c-327">One-Way Message</span></span>  
 <span data-ttu-id="b6e1c-328">In questo scenario, il mittente invia un messaggio unidirezionale al destinatario.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-328">In this scenario, the sender sends a one-way message to the receiver.</span></span> <span data-ttu-id="b6e1c-329">Vengono utilizzate le specifiche SOAP 1.2, HTTP 1.1 e W3C WS-Addressing 1.0.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-329">SOAP 1.2, HTTP 1.1, and W3C WS-Addressing 1.0 are used.</span></span>  
  
 <span data-ttu-id="b6e1c-330">Struttura dei messaggi di richiesta: le intestazioni dei messaggi includono gli elementi `wsa10:To` e `wsa10:Action`.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-330">The Request Message Structure: The message headers include `wsa10:To` and `wsa10:Action` elements.</span></span> <span data-ttu-id="b6e1c-331">Il corpo dei messaggi include un elemento `<app:Ping>` specifico dello spazio dei nomi dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-331">The message body includes a specific `<app:Ping>` element from the application namespace.</span></span>  
  
 <span data-ttu-id="b6e1c-332">Intestazioni HTTP: La destinazione indicata in POST corrisponde all'URI specificato nella `wsa10:To` elemento.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-332">HTTP Headers: The destination in POST matches the URI in the `wsa10:To` element.</span></span>  
  
 <span data-ttu-id="b6e1c-333">L'intestazione Content-Type dispone del valore di `application/soap+xml` come richiesto da SOAP 1.2.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-333">The Content-Type header has the value of `application/soap+xml` as required by SOAP 1.2.</span></span> <span data-ttu-id="b6e1c-334">I parametri `charset` e `action` sono inclusi.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-334">Parameters `charset` and `action` are included.</span></span> <span data-ttu-id="b6e1c-335">Il parametro `action` dell'intestazione Content-Type corrisponde al valore dell'intestazione dei messaggi `wsa10:Action`.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-335">The `action` parameter of the Content-Type header matches the value of the `wsa10:Action` message header.</span></span>  
  
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
  
 <span data-ttu-id="b6e1c-336">Il destinatario fornisce con una risposta HTTP vuota e lo stato 202.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-336">The receiver responds with an empty HTTP response and status 202.</span></span> <span data-ttu-id="b6e1c-337">Un esempio della risposta HTTP:</span><span class="sxs-lookup"><span data-stu-id="b6e1c-337">An example of the HTTP response:</span></span>  
  
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
  
## <a name="soap-message-transmission-optimization-mechanism"></a><span data-ttu-id="b6e1c-338">SOAP MTOM</span><span class="sxs-lookup"><span data-stu-id="b6e1c-338">SOAP Message Transmission Optimization Mechanism</span></span>  
 <span data-ttu-id="b6e1c-339">Contenuto della sezione vengono forniti i dettagli di implementazione di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] relativi al meccanismo HTTP SOAP MTOM.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-339">This section describes the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] implementation details for the HTTP SOAP MTOM.</span></span> <span data-ttu-id="b6e1c-340">La tecnologia MTOM è un meccanismo di codifica dei messaggi SOAP analogo ai meccanismi tradizionali di codifica text/XML o di codifica binaria di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b6e1c-340">MTOM technology is SOAP message encoding mechanism of the same class as traditional text/XML encoding or [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Binary encoding.</span></span> <span data-ttu-id="b6e1c-341">Il meccanismo MTOM prevede le funzionalità seguenti:</span><span class="sxs-lookup"><span data-stu-id="b6e1c-341">MTOM includes the following:</span></span>  
  
-   <span data-ttu-id="b6e1c-342">Meccanismo di codifica e assemblaggio di pacchetti XML descritto da [XOP] che ottimizza le voci di informazioni XML contenenti dati binari con codifica in base 64 suddividendoli in parti binarie distinte.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-342">An XML encoding and packaging mechanism described by [XOP] that optimizes XML information items containing base64-encoded binary data into separate binary parts.</span></span>  
  
-   <span data-ttu-id="b6e1c-343">Incapsulamento MIME del pacchetto XOP che serializza l'InfoSet XML e ogni parte binaria del pacchetto XOP in una parte MIME distinta.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-343">A MIME encapsulation of the XOP package that serializes the XML Infoset and each binary part of the XOP package into a separate MIME part.</span></span>  
  
-   <span data-ttu-id="b6e1c-344">Codifica MIME XOP applicata alla SOAP 1.x envelope.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-344">A MIME XOP encoding applied to SOAP 1.x Envelope.</span></span>  
  
-   <span data-ttu-id="b6e1c-345">Associazione di trasporto HTTP.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-345">An HTTP transport binding.</span></span>  
  
 <span data-ttu-id="b6e1c-346">Benché in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] sia possibile utilizzare il meccanismo MTOM con trasporti diversi da HTTP,</span><span class="sxs-lookup"><span data-stu-id="b6e1c-346">It is possible to use MTOM with non-HTTP transports with [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span> <span data-ttu-id="b6e1c-347">quanto descritto in questo argomento si basa sul protocollo HTTP.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-347">However, in this topic we will focus on HTTP.</span></span>  
  
 <span data-ttu-id="b6e1c-348">Il formato MTOM sfrutta un numeroso set di specifiche relative al meccanismo MTOM stesso, a XOP e a MIME.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-348">The MTOM format leverages a large set of specifications covering MTOM itself, XOP, and MIME.</span></span> <span data-ttu-id="b6e1c-349">La modularità di questo set di specifiche rende piuttosto difficile ricavare in modo esatto i requisiti relativi alla semantica di formato ed elaborazione.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-349">Modularity of this specification set makes it somewhat difficult to reconstruct exact requirements on the format and processing semantics.</span></span> <span data-ttu-id="b6e1c-350">Questa sezione descrive i requisiti di formato ed elaborazione dell'associazione MTOM HTTP.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-350">This section describes the format and processing requirements for MTOM HTTP binding.</span></span>  
  
### <a name="mtom-message-encoding"></a><span data-ttu-id="b6e1c-351">Codifica dei messaggi MTOM</span><span class="sxs-lookup"><span data-stu-id="b6e1c-351">MTOM Message Encoding</span></span>  
  
#### <a name="generating-mtom-messages"></a><span data-ttu-id="b6e1c-352">Generazione di messaggi MTOM</span><span class="sxs-lookup"><span data-stu-id="b6e1c-352">Generating MTOM messages</span></span>  
 <span data-ttu-id="b6e1c-353">La sezione 3.1 di [XOP] descrive il processo di codifica di elementi XML aventi voci di informazioni sugli elementi contenenti valori in base 64 in un pacchetto XOP definito in modo astratto.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-353">The [XOP] section 3.1 describes the process of encoding XML with element information items that contain base64 values into an abstractly defined XOP package.</span></span>  
  
 <span data-ttu-id="b6e1c-354">La sequenza di passaggi seguente descrive il processo di codifica specifico del meccanismo MTOM:</span><span class="sxs-lookup"><span data-stu-id="b6e1c-354">The following sequence of steps describes the MTOM-specific encoding process:</span></span>  
  
1.  <span data-ttu-id="b6e1c-355">Verificare che la SOAP envelope da codificare non contenga alcuna voce di informazioni sugli elementi il cui attributo `[namespace name]` sia "http://www.w3.org/2004/08/xop/include" e il cui attributo `[local name]` sia `Include`.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-355">Ensure that the SOAP Envelope to be encoded contains no element information item with a `[namespace name]` of "http://www.w3.org/2004/08/xop/include" and a `[local name]` of `Include`.</span></span>  
  
2.  <span data-ttu-id="b6e1c-356">Creare un pacchetto MIME vuoto.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-356">Create an empty MIME package.</span></span>  
  
3.  <span data-ttu-id="b6e1c-357">Identificare all'interno dell'InfoSet XML originale le voci di informazioni sugli elementi da ottimizzare.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-357">Identify within the Original XML Infoset the element information items to be optimized.</span></span> <span data-ttu-id="b6e1c-358">Affinché gli elementi vengano ottimizzati, i caratteri che costituiscono l'attributo `[children]` della voce di informazioni sugli elementi devono presentare la forma canonica di `xs:base64Binary` (vedere XSD-2, 3.2.16 base64Binary) e non devono contenere spazi vuoti nella stessa riga contenente i caratteri diversi da spazio vuoto, né nella riga precedente o successiva.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-358">For the items to be optimized, the characters that make up the `[children]` of the element information item must be in the canonical form of `xs:base64Binary` (see XSD-2, 3.2.16 base64Binary) and must not contain any whitespace characters preceding, inline with, or following the non-whitespace content.</span></span>  
  
4.  <span data-ttu-id="b6e1c-359">Creare una XOP SOAP envelope uguale alla SOAP envelope originale, sostituendo tuttavia al figlio di ogni voce di informazioni sugli elementi identificato nel passaggio precedente una voce di informazioni sugli elementi `xop:Include` costruito come segue:</span><span class="sxs-lookup"><span data-stu-id="b6e1c-359">Create an XOP SOAP Envelope that is a copy of the Original SOAP Envelope, but with the children of each element information item identified in the previous step replaced by an `xop:Include` element information item constructed as follows:</span></span>  
  
    1.  <span data-ttu-id="b6e1c-360">Trasformare i caratteri sostituiti in dati binari elaborandoli come dati codificati in base 64.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-360">Transform the replaced characters into binary data by processing them as base64-encoded data.</span></span>  
  
    2.  <span data-ttu-id="b6e1c-361">Generare un valore univoco di intestazione Content-ID che soddisfi i requisiti R3133 e R3134.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-361">Generate a unique Content-ID header value that satisfies requirements R3133 and R3134.</span></span>  
  
    3.  <span data-ttu-id="b6e1c-362">Generare un'intestazione MIME Content-Transfer-Encoding con il valore in binario.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-362">Generate a Content-Transfer-Encoding MIME header with the value binary.</span></span>  
  
    4.  <span data-ttu-id="b6e1c-363">Se la voce di informazioni sugli elementi da ottimizzare (ovvero il padre [parent] della voce di informazioni sugli elementi `xop:Include` appena aggiunto) contiene una voce di informazioni sugli attributi `xmime:contentType`, generare un'intestazione Content-Type MIME con il valore dell'attributo `xmime:contentType`.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-363">If the element information item being optimized (the [parent] of the newly inserted `xop:Include` element information item) has an `xmime:contentType` attribute information item, generate a Content-Type MIME header with the value of the `xmime:contentType` attribute.</span></span>  
  
    5.  <span data-ttu-id="b6e1c-364">Generare una nuova parte MIME binaria avente un contenuto formato dagli elementi seguenti: dati binari decodificati a partire dai caratteri sostituiti elaborati come dati in base 64, intestazione Content-ID come da passaggio 4b, intestazione Content- Transfer-Encoding come da passaggio 4c e intestazione Content-Type come da passaggio 4d, se presente.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-364">Generate a new binary MIME part with content formed by binary data decoded from the replaced characters processed as base64, Content-ID header from 4b, Content- Transfer-Encoding header from 4c, Content-Type header if generated in step 4d.</span></span>  
  
    6.  <span data-ttu-id="b6e1c-365">Aggiungere un attributo `href` all'elemento `xop:Include` con il valore cid: uri derivato dal valore dell'intestazione Content-ID generato nel passaggio 4b.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-365">Add an `href` attribute to the `xop:Include` element with the value cid: uri derived from Content-ID header value generated in step 4b.</span></span> <span data-ttu-id="b6e1c-366">Rimuovere il tipo di inclusione "\<" e ">" caratteri, escape-URL la stringa restante e aggiungere il prefisso `cid:`.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-366">Remove the enclosing "\<" and ">" characters, URL-escape the remaining string, and add the prefix `cid:`.</span></span> <span data-ttu-id="b6e1c-367">La suddetta conversione, da eseguire in base ai documenti RFC1738 e RFC2396, deve riguardare almeno il set di caratteri seguente,</span><span class="sxs-lookup"><span data-stu-id="b6e1c-367">The following minimum character set is required to be escaped by RFC1738 and RFC2396.</span></span> <span data-ttu-id="b6e1c-368">ma può essere applicata anche ad altri caratteri.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-368">Other characters can be escaped.</span></span>  
  
        ```  
        Hexadecimal 00-1F , 7F, 20, "<" | ">" | "#" | "%" | <">  
        "{" | "}" | "|" | "\" | "^" | "[" | "]" | "`" | "~" | "^"  
        ```  
  
5.  <span data-ttu-id="b6e1c-369">Creare una parte MIME radice contenente la XOP SOAP envelope ottenuta nel passaggio 4.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-369">Create a root MIME part with the XOP SOAP Envelope from step 4.</span></span>  
  
6.  <span data-ttu-id="b6e1c-370">Scrivere le intestazioni HTTP, compresa l'intestazione Content-Type HTTP.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-370">Write the HTTP headers, including the HTTP Content-Type header.</span></span>  
  
7.  <span data-ttu-id="b6e1c-371">Scrivere il pacchetto MIME.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-371">Write the MIME package.</span></span>  
  
#### <a name="processing-mtom-messages"></a><span data-ttu-id="b6e1c-372">Elaborazione di messaggi MTOM</span><span class="sxs-lookup"><span data-stu-id="b6e1c-372">Processing MTOM messages</span></span>  
 <span data-ttu-id="b6e1c-373">L'elaborazione di un messaggio MTOM è l'esatto contrario del processo descritto nella sezione precedente "Generazione di messaggi MTOM":</span><span class="sxs-lookup"><span data-stu-id="b6e1c-373">Processing of an MTOM message is the exact reverse of the process described in the preceding "Generating MTOM messages" section:</span></span>  
  
1.  <span data-ttu-id="b6e1c-374">Verificare che la parte MIME radice contenga l'elemento Content-Type `application/xop+xml`.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-374">Ensure the root MIME part has the Content-Type `application/xop+xml`.</span></span>  
  
2.  <span data-ttu-id="b6e1c-375">Costruire una SOAP envelope analizzando la parte MIME radice del pacchetto come documento XML.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-375">Construct a SOAP Envelope by parsing the root MIME part of the package as an XML document.</span></span> <span data-ttu-id="b6e1c-376">La codifica dei caratteri viene determinata in base al parametro `charset` del Content-Type della parte MIME radice.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-376">Character encoding is determined by the `charset` parameter of the Content-Type of the root MIME part.</span></span>  
  
3.  <span data-ttu-id="b6e1c-377">Per ogni voce di informazioni sugli elementi della SOAP envelope costruita, che come unico membro della proprietà dei relativi figli [children] presenta una voce di informazioni sugli elementi `xop:Include`, eseguire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="b6e1c-377">For each element information item in the constructed SOAP Envelope, which has, as the sole member of its [children] property, an `xop:Include` element information item:</span></span>  
  
    1.  <span data-ttu-id="b6e1c-378">Rimuovere il prefisso `cid:` ed eseguire la conversione URI inversa di tutte le sequenze escape (RFC 2396) contenute nel valore dell'attributo `@href` dell'elemento `xop:Include`.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-378">Remove the `cid:` prefix and unescape all URI-escape sequences (RFC 2396) in the value of the `@href` attribute of the `xop:Include` element.</span></span> <span data-ttu-id="b6e1c-379">Racchiudere la stringa di risultato in "\<", ">".</span><span class="sxs-lookup"><span data-stu-id="b6e1c-379">Enclose the result string in "\<", ">".</span></span>  
  
    2.  <span data-ttu-id="b6e1c-380">Individuare la parte MIME contenente il valore dell'intestazione Content-ID corrispondente alla stringa ottenuta nel passaggio 3a.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-380">Locate the MIME part with the Content-ID header value that matches the string derived in step 3a.</span></span>  
  
    3.  <span data-ttu-id="b6e1c-381">Sostituire la voce di informazioni sugli elementi `xop:Include` contenuto nella proprietà `children` di ogni elemento contenente le voci di informazioni sugli elementi che rappresentano la codifica canonica in base 64 (vedere XSD-2, 3.2.16 base64Binary) del corpo dell'entità della parte MIME identificato nel passaggio 3b. In pratica, sostituire la voce di informazioni sugli elementi `xop:Include` con i dati ricostruiti a partire dalla parte di pacchetto.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-381">Replace the `xop:Include` element information item that appears in the `children` property of each item with the character information items that represent the canonical base64 encoding (see XSD-2, 3.2.16 base64Binary) of the entity body of the MIME part identified in step 3b (effectively replace the `xop:Include` element information item with the data reconstructed from the package part).</span></span>  
  
#### <a name="http-content-type-header"></a><span data-ttu-id="b6e1c-382">Intestazione Content-Type HTTP</span><span class="sxs-lookup"><span data-stu-id="b6e1c-382">HTTP Content-Type Header</span></span>  
 <span data-ttu-id="b6e1c-383">Segue un elenco di precisazioni in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] relative al formato dell'intestazione Content-Type HTTP di un messaggio con codifica SOAP 1.x MTOM ottenuto a partire dai requisiti dichiarati nella specifica di MTOM nonché dal meccanismo MTOM e dal documento RFC 2387.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-383">The following is a list of [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] clarifications for the format of the HTTP Content-Type header of a SOAP 1.x MTOM-encoded message derived from requirements stated in the MTOM specification itself and are derived from MTOM and RFC 2387.</span></span>  
  
-   <span data-ttu-id="b6e1c-384">R4131: un'intestazione Content-Type HTTP deve contenere il valore multipart/related (che non fa distinzione fra maiuscole e minuscole) e i relativi parametri.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-384">R4131: An HTTP Content-Type header must have the value of multipart/related (case-insensitive) and its parameters.</span></span> <span data-ttu-id="b6e1c-385">Anche i nomi dei parametri non fanno distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-385">Parameter names are case-insensitive.</span></span> <span data-ttu-id="b6e1c-386">Inoltre, l'ordine dei parametri è irrilevante.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-386">Parameter order is not significant.</span></span>  
  
-   <span data-ttu-id="b6e1c-387">Il formato BNF (Backus-Naur Form) completo dell'intestazione Content-Type dei messaggi MIME è riportato nella sezione 5.1 del documento RFC 2045.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-387">The full Backus-Naur Form (BNF) of the Content-Type header for MIME messages is listed in RFC 2045, section 5.1.</span></span>  
  
-   <span data-ttu-id="b6e1c-388">R4132: un'intestazione Content-Type HTTP deve contenere un parametro di tipo avente il valore `application/xop+xml` compreso fra virgolette doppie.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-388">R4132: An HTTP Content-Type header must have a type parameter with the value `application/xop+xml` enclosed in double quotation marks.</span></span>  
  
 <span data-ttu-id="b6e1c-389">La necessità di utilizzare le virgolette doppie non è esplicita nel documento RFC 2387, il testo osserva che tutti i parametri più probabile che contengono il tipo di supporto multipart/related riservata caratteri, ad esempio "@" or "/" ed è pertanto necessario utilizzando le virgolette doppie.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-389">While the requirement to use double quotation marks is not explicit in RFC 2387, the text observes that all of the multipart/related media type parameters most likely contain reserved characters like "@" or "/" and therefore need double quotation marks.</span></span>  
  
-   <span data-ttu-id="b6e1c-390">R4133: un'intestazione Content-Type HTTP deve presentare un parametro start con il valore dell'intestazione Content-ID della parte MIME contenente l'elemento SOAP 1.x Envelope, racchiuso fra virgolette doppie.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-390">R4133: An HTTP Content-Type header should have a start parameter with the value of the Content-ID header of the MIME part that contains the SOAP 1.x Envelope, enclosed in double quotation marks.</span></span> <span data-ttu-id="b6e1c-391">Se tale parametro viene omesso, la SOAP 1.x envelope deve essere inclusa nella prima parte MIME.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-391">If the start parameter is omitted, the first MIME part must contain the SOAP 1.x Envelope.</span></span>  
  
-   <span data-ttu-id="b6e1c-392">R4134: un'intestazione Content-Type HTTP di un messaggio con codifica SOAP 1.1 MTOM deve includere il parametro start-info con il valore text/xml racchiuso fra virgolette doppie.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-392">R4134: An HTTP Content-Type header for a SOAP 1.1 MTOM encoded message must include the start-info parameter with the value of text/xml, enclosed in double quotation marks.</span></span>  
  
-   <span data-ttu-id="b6e1c-393">R4135: un'intestazione Content-Type HTTP di un messaggio con codifica SOAP 1.2 MTOM deve includere il parametro start-info con il valore `application/soap+xml` racchiuso fra virgolette doppie.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-393">R4135: An HTTP Content-Type header for a SOAP 1.2 MTOM-encoded message must include the start-info parameter with the value of `application/soap+xml`, enclosed in double quotation marks.</span></span>  
  
-   <span data-ttu-id="b6e1c-394">R4136: un'intestazione Content-Type HTTP di un messaggio con codifica SOAP 1.x MTOM deve contenere un parametro boundary il cui valore (racchiuso fra virgolette doppie) corrisponda al formato BNF del limite MIME definito nella sezione 5.1.1 del documento RFC 2046.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-394">R4136: HTTP Content-Type header for a SOAP 1.x MTOM-encoded message must have the boundary parameter with the value (enclosed in double quotation marks) that matches the MIME boundary BNF defined in RFC 2046, section 5.1.1</span></span>  
  
    ```  
    boundary := 0*69<bchars> bcharsnospace   
    bchars := bcharsnospace / " "   
    bcharsnospace :=    DIGIT / ALPHA / "'" / "(" / ")" / "+"   
                        / "_" / "," / "-" / "." / "/" / ":" / "=" / "?"  
    ```  
  
     <span data-ttu-id="b6e1c-395">Esempi:</span><span class="sxs-lookup"><span data-stu-id="b6e1c-395">Examples:</span></span>  
  
     <span data-ttu-id="b6e1c-396">CORRETTO</span><span class="sxs-lookup"><span data-stu-id="b6e1c-396">CORRECT</span></span>  
  
    ```  
    Content-Type: multipart/related; type="application/xop+xml";start=" <part0@tempuri.org>";boundary="uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=1";start-info="text/xml"  
    ```  
  
     <span data-ttu-id="b6e1c-397">CORRETTO</span><span class="sxs-lookup"><span data-stu-id="b6e1c-397">CORRECT</span></span>  
  
    ```  
    Content-Type: Multipart/Related; type="application/xop+xml";start-info="text/xml";boundary="uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=1"  
    ```  
  
     <span data-ttu-id="b6e1c-398">NON CORRETTO</span><span class="sxs-lookup"><span data-stu-id="b6e1c-398">INCORRECT</span></span>  
  
    ```  
    Content-Type: Multipart/Related; type=application/xop+xml;start=" <part0@tempuri.org>";start-info="text/xml";boundary="uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=1"   
    ```  
  
#### <a name="infoset-mime-part"></a><span data-ttu-id="b6e1c-399">Parte MIME InfoSet</span><span class="sxs-lookup"><span data-stu-id="b6e1c-399">Infoset MIME Part</span></span>  
 <span data-ttu-id="b6e1c-400">La SOAP 1.x envelope è incapsulata come parte radice del pacchetto XOP MIME e spesso viene detta "parte `infoset`".</span><span class="sxs-lookup"><span data-stu-id="b6e1c-400">The SOAP 1.x Envelope is encapsulated as a root part of the XOP MIME package and is often called the `infoset` part.</span></span>  
  
-   <span data-ttu-id="b6e1c-401">R4141: la SOAP 1.x envelope deve essere incapsulata come parte radice del pacchetto XOP MIME, detto "parte `infoset`", a cui si fa riferimento nell'intestazione Content-Type HTTP.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-401">R4141: The SOAP 1.x Envelope must be encapsulated as a root part of the XOP MIME package, called the `infoset` part and referenced from the HTTP Content-Type.</span></span>  
  
-   <span data-ttu-id="b6e1c-402">R4142: la parte `Infoset` SOAP deve contenere le intestazioni MIME seguenti: `Content-ID`, `Content-Transfer-Encoding` e `Content-Type`.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-402">R4142: The SOAP `Infoset` part must include the following MIME headers: `Content-ID`, `Content-Transfer-Encoding`, and `Content-Type`.</span></span>  
  
 <span data-ttu-id="b6e1c-403">Il formato dell'intestazione Content-ID è definito nel documento RFC 2045 come</span><span class="sxs-lookup"><span data-stu-id="b6e1c-403">The format of the Content-ID header is defined by RFC 2045 as</span></span>  
  
```  
"Content-ID" ":" msg-id  
```  
  
 <span data-ttu-id="b6e1c-404">in cui l'elemento `msg-id` è definito nel documento RFC 2822 (che sostituisce il documento RFC 822, a cui si fa riferimento nel documento RFC 2045) come:</span><span class="sxs-lookup"><span data-stu-id="b6e1c-404">where `msg-id` is defined in RFC 2822 (that supersedes RFC 822, referenced in RFC 2045) as:</span></span>  
  
```  
msg-id    =       [CFWS] "<" id-left "@" id-right ">" [CFWS]  
```  
  
 <span data-ttu-id="b6e1c-405">e in modo efficace un indirizzo di posta elettronica incluso all'interno di "\<" e ">".</span><span class="sxs-lookup"><span data-stu-id="b6e1c-405">and is effectively an e-mail address enclosed within "\<" and  ">".</span></span> <span data-ttu-id="b6e1c-406">Il prefisso e il suffisso `[CFWS]` sono stati aggiunti nel documento RFC 2822 per contenere commenti e non devono essere utilizzati per mantenere l'interoperabilità.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-406">The `[CFWS]` prefix and suffix were added in RFC 2822 to carry comments and should not be used to preserve interoperability.</span></span>  
  
 <span data-ttu-id="b6e1c-407">R4143: il valore dell'intestazione Content-ID della parte MIME InfoSet deve attenersi alle regole di definizione dell'elemento `msg-id` indicate nel documento RFC 2822, omettendo le parti `[CFWS]` di prefisso e suffisso.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-407">R4143: The value of the Content-ID header for the Infoset MIME part must follow `msg-id` production from RFC 2822 with the `[CFWS]` prefix and suffix parts omitted.</span></span>  
  
 <span data-ttu-id="b6e1c-408">Molte implementazioni MIME ridotti i requisiti per il valore compreso fra "\<" e ">" corrisponda a un indirizzo di posta elettronica e utilizzato `absoluteURI` racchiusa tra "\<", ">" oltre all'indirizzo di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-408">A number of MIME implementations relaxed requirements for the value enclosed within "\<" and ">" to be an e-mail address and used `absoluteURI` enclosed in "\<" , ">" in addition to the e-mail address.</span></span> <span data-ttu-id="b6e1c-409">Questa versione di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] prevede che i valori dell'intestazione MIME Content-ID presentino il formato:</span><span class="sxs-lookup"><span data-stu-id="b6e1c-409">This version of [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] uses values of the Content-ID MIME header of the form:</span></span>  
  
```  
Content-ID: <http://tempuri.org/0>   
```  
  
 <span data-ttu-id="b6e1c-410">R4144: i processori MTOM devono accettare valori di intestazione Content-ID corrispondenti all'elemento `msg-id` con requisiti ridotti riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-410">R4144: MTOM processors should accept Content-ID header values that match the following relaxed `msg-id`.</span></span>  
  
```  
msg-id-relaxed =     [CFWS] "<" (absoluteURI | mail-address) ">" [CFWS]  
mail-address   =     id-left "@" id-right  
```  
  
 <span data-ttu-id="b6e1c-411">Il protocollo MIME (RFC 2045) fornisce l'intestazione Content-Transfer-Encoding per comunicare la codifica del contenuto della parte MIME.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-411">MIME (RFC 2045) provides the Content-Transfer-Encoding header to communicate encoding of the content of the MIME part.</span></span> <span data-ttu-id="b6e1c-412">L'impostazione predefinita dell'intestazione Content-Transfer-Encoding è una codifica a 7 bit, che tuttavia per la maggior parte dei messaggi SOAP risulta inadatta. Pertanto, tale intestazione è necessaria per garantire una maggiore interoperabilità:</span><span class="sxs-lookup"><span data-stu-id="b6e1c-412">The default defined for Content-Transfer-Encoding is 7-bit, which is not suitable for most SOAP messages, so the Content-Transfer-Encoding header is needed for greater interoperability:</span></span>  
  
-   <span data-ttu-id="b6e1c-413">R4145: la parte SOAP InfoSet deve contenere l'intestazione Content-Transfer-Encoding.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-413">R4145: The SOAP Infoset part must contain the Content-Transfer-Encoding header.</span></span>  
  
-   <span data-ttu-id="b6e1c-414">R4146: se la codifica dei caratteri della SOAP envelope è UTF-8, il valore dell'intestazione Content-Transfer-Encoding deve corrispondere a una codifica a 8 bit.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-414">R4146: If the SOAP Envelope character encoding is UTF-8, the value of the Content-Transfer-Encoding header must be 8-bit.</span></span>  
  
-   <span data-ttu-id="b6e1c-415">R4147: se la codifica dei caratteri della SOAP envelope è UTF-16, il valore dell'intestazione Content-Transfer-Encoding deve corrispondere a una codifica binaria.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-415">R4147: If the SOAP Envelope character encoding is UTF-16, the value of the Content-Transfer-Encoding header must be binary.</span></span>  
  
-   <span data-ttu-id="b6e1c-416">Secondo quanto indicato nella sezione 5 di [XOP]:</span><span class="sxs-lookup"><span data-stu-id="b6e1c-416">According to [XOP] section 5,</span></span>  
  
-   <span data-ttu-id="b6e1c-417">R4148: Parte SOAP 1.1 Infoset deve contenere l'intestazione Content-Type con supporto tipo application/xop + xml e parametri di tipo = "text/xml" e charset</span><span class="sxs-lookup"><span data-stu-id="b6e1c-417">R4148: SOAP1.1 Infoset part must contain Content-Type header with media type application/xop+xml and parameters type="text/xml" and charset</span></span>  
  
    ```  
    Content-Type: application/xop+xml;  
                  charset=utf-8;type="text/xml"  
    ```  
  
-   <span data-ttu-id="b6e1c-418">R4149: La parte SOAP 1.2 Infoset deve contenere l'intestazione Content-Type con tipo di supporto `application/xop+xml` i parametri e tipo = "`application/soap+xml`" e `charset`.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-418">R4149: The SOAP 1.2 Infoset part must contain the Content-Type header with media type `application/xop+xml` and parameters type="`application/soap+xml`" and `charset`.</span></span>  
  
    ```  
    Content-Type: application/xop+xml;  
                  charset=utf-8;type="application/soap+xml"  
    ```  
  
     <span data-ttu-id="b6e1c-419">Benché XOP consenta di definire il parametro `charset` di `application/xop+xml` come facoltativo, tale parametro è necessario per l'interoperabilità, analogamente al requisito di BP 1.1 relativo al parametro `charset` del tipo di supporto `text/xml`.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-419">While XOP defines the `charset` parameter for `application/xop+xml` to be optional, it is needed for interoperability similar to the BP 1.1 requirement on the `charset` parameter for the `text/xml` media type.</span></span>  
  
-   <span data-ttu-id="b6e1c-420">R41410: i parametri `type` e `charset` devono essere presenti nell'intestazione Content-Type della parte SOAP 1.x InfoSet.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-420">R41410: The `type` and `charset` parameters must be present on the Content-Type header of the SOAP 1.x Infoset part.</span></span>  
  
#### <a name="wcf-endpoint-support-for-mtom"></a><span data-ttu-id="b6e1c-421">Supporto degli endpoint WCF per MTOM</span><span class="sxs-lookup"><span data-stu-id="b6e1c-421">WCF Endpoint Support for MTOM</span></span>  
 <span data-ttu-id="b6e1c-422">Lo scopo del meccanismo MTOM è codificare un messaggio SOAP allo scopo di ottimizzare i dati codificati in base 64.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-422">The purpose of MTOM is to encode a SOAP message to optimize base64-encoded data.</span></span> <span data-ttu-id="b6e1c-423">Segue un elenco di vincoli:</span><span class="sxs-lookup"><span data-stu-id="b6e1c-423">The following is a list of constraints:</span></span>  
  
-   <span data-ttu-id="b6e1c-424">R4151: qualsiasi voce di informazioni sugli elementi contenente dati con codifica in base 64 può essere ottimizzata.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-424">R4151: Any element information item that contains base64-encoded data may be optimized.</span></span>  
  
-   <span data-ttu-id="b6e1c-425">B4152: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ottimizza le voci di informazioni sugli elementi contenenti dati con codifica in base 64 e aventi una lunghezza superiore a 1024 byte.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-425">B4152: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] optimizes element information items that contain base64-encoded data and exceed 1024 bytes in length.</span></span>  
  
 <span data-ttu-id="b6e1c-426">Un endpoint di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] configurato per utilizzare il meccanismo MTOM invia sempre messaggi con codifica MTOM.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-426">A [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] endpoint configured to use MTOM will always send MTOM-encoded messages.</span></span> <span data-ttu-id="b6e1c-427">Anche se nessuna parte soddisfa i criteri previsti, il messaggio viene comunque considerato come messaggio con codifica MTOM, serializzato come pacchetto MIME e avente una sola parte MIME contenente la SOAP envelope.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-427">Even if no parts meet the required criteria, the message is still MTOM-encoded (serialized as a MIME package with a single MIME part containing the SOAP envelope).</span></span>  
  
### <a name="ws-policy-assertion-for-mtom"></a><span data-ttu-id="b6e1c-428">Asserzione di WS-Policy relativa a MTOM</span><span class="sxs-lookup"><span data-stu-id="b6e1c-428">WS-Policy Assertion for MTOM</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="b6e1c-429"> utilizza l'asserzione di criteri seguente per indicare l'utilizzo del meccanismo MTOM in base all'endpoint:</span><span class="sxs-lookup"><span data-stu-id="b6e1c-429"> uses the following policy assertion to indicate MTOM usage by endpoint:</span></span>  
  
```xml  
<wsoma:OptimizedMimeSerialization ... />  
```  
  
-   <span data-ttu-id="b6e1c-430">R4211: l'asserzione di criteri precedente contiene un soggetto dei criteri di endpoint e impone che tutti i messaggi inviati all'endpoint e provenienti da quest'ultimo vengano ottimizzati tramite il meccanismo MTOM.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-430">R4211: The preceding policy assertion has an Endpoint Policy Subject and specifies that all messages sent to and received from the endpoint must be optimized using MTOM.</span></span>  
  
-   <span data-ttu-id="b6e1c-431">B4212: quando configurato per utilizzare l'ottimizzazione MTOM, un endpoint di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] aggiunge un'asserzione di criteri MTOM al criterio associato all'elemento `wsdl:binding` corrispondente.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-431">B4212: When configured to use MTOM optimization, an [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] endpoint adds an MTOM Policy assertion to the policy attached to the corresponding `wsdl:binding`.</span></span>  
  
### <a name="composition-with-ws-security"></a><span data-ttu-id="b6e1c-432">Integrazione con WS-Security</span><span class="sxs-lookup"><span data-stu-id="b6e1c-432">Composition with WS-Security</span></span>  
 <span data-ttu-id="b6e1c-433">MTOM è un meccanismo di codifica simile ai meccanismi di codifica `text/xml` e di codifica binaria XML di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b6e1c-433">MTOM is an encoding mechanism that is similar to `text/xml` and [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Binary XML.</span></span> <span data-ttu-id="b6e1c-434">Il meccanismo MTOM può integrarsi perfettamente con il protocollo WS-Security e gli altri protocolli WS - *: un messaggio protetto mediante il protocollo WS-Security può infatti essere ottimizzato tramite MTOM.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-434">MTOM offers natural composition with WS-Security and other WS-* protocols: a message secured using WS-Security can be optimized using MTOM.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="b6e1c-435">Esempi</span><span class="sxs-lookup"><span data-stu-id="b6e1c-435">Examples</span></span>  
  
#### <a name="wcf-soap-11-message-encoded-using-mtom"></a><span data-ttu-id="b6e1c-436">Esempio di messaggio WCF SOAP 1.1 codificato tramite MTOM</span><span class="sxs-lookup"><span data-stu-id="b6e1c-436">WCF SOAP 1.1 Message Encoded Using MTOM</span></span>  
  
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
  
#### <a name="wcf-secure-soap-12-message-encoded-using-mtom"></a><span data-ttu-id="b6e1c-437">Esempio di messaggio WCF Secure SOAP 1.2 codificato tramite MTOM</span><span class="sxs-lookup"><span data-stu-id="b6e1c-437">WCF Secure SOAP 1.2 Message Encoded Using MTOM</span></span>  
 <span data-ttu-id="b6e1c-438">Questo esempio illustra la codifica tramite MTOM e SOAP 1.2 di un messaggio protetto mediante WS-Security.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-438">In this example, a message is encoded using MTOM and SOAP 1.2 that is protected using WS-Security.</span></span> <span data-ttu-id="b6e1c-439">Le parti binarie identificate per la codifica sono il contenuto del token `BinarySecurityToken`, il valore `CipherValue` dell'elemento `EncryptedData` che corrisponde alla firma crittografata e il corpo crittografato.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-439">The binary parts identified for encoding are the contents of the `BinarySecurityToken`, `CipherValue` of the `EncryptedData` corresponding to the encrypted signature and encrypted body.</span></span> <span data-ttu-id="b6e1c-440">Si noti che `CipherValue` non considera il valore `EncryptedKey` della chiave [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] come ottimizzabile, in quanto la relativa lunghezza è inferiore a 1024 byte.</span><span class="sxs-lookup"><span data-stu-id="b6e1c-440">Note that the `CipherValue` of the `EncryptedKey` was not identified for optimization by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], because its length is less then 1024 bytes.</span></span>  
  
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
