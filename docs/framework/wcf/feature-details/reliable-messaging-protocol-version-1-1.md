---
title: Protocollo Reliable Messaging versione 1,1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0da47b82-f8eb-42da-8bfe-e56ce7ba6f59
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 586e26825bd01947706bb26061ef1b8879fecb4c
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="reliable-messaging-protocol-version-11"></a><span data-ttu-id="45385-102">Protocollo Reliable Messaging versione 1,1</span><span class="sxs-lookup"><span data-stu-id="45385-102">Reliable Messaging Protocol version 1.1</span></span>
<span data-ttu-id="45385-103">In questo argomento vengono illustrati i dettagli di implementazione di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] per il protocollo WS-ReliableMessaging di febbraio 2007 (versione 1.1) necessario per l'interoperatività con il trasporto HTTP.</span><span class="sxs-lookup"><span data-stu-id="45385-103">This topic covers [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] implementation details for the WS-ReliableMessaging February 2007 (version 1.1) protocol necessary for interoperation using the HTTP transport.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="45385-104"> segue la specifica WS-ReliableMessaging con i vincoli e i chiarimenti illustrati in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="45385-104"> follows the WS-ReliableMessaging specification with the constraints and clarifications explained in this topic.</span></span> <span data-ttu-id="45385-105">Si noti che il protocollo di versione 1.1 di WS-ReliableMessaging viene implementato a partire dal [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="45385-105">Note that the WS-ReliableMessaging version 1.1 protocol is implemented starting with the [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)].</span></span>  
  
 <span data-ttu-id="45385-106">Il protocollo WS-ReliableMessaging (febbraio 2007) viene implementato in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] da <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="45385-106">The WS-ReliableMessaging February 2007 protocol is implemented in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] by the <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>.</span></span>  
  
 <span data-ttu-id="45385-107">Per comodità, nell'argomento vengono utilizzati i ruoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="45385-107">For convenience, the topic uses the following roles:</span></span>  
  
-   <span data-ttu-id="45385-108">Iniziatore: il client che inizia la creazione della sequenza di WS-Reliable Message.</span><span class="sxs-lookup"><span data-stu-id="45385-108">Initiator: The client that initiates WS-Reliable Message sequence creation.</span></span>  
  
-   <span data-ttu-id="45385-109">Risponditore: il servizio che riceve le richieste dell'iniziatore.</span><span class="sxs-lookup"><span data-stu-id="45385-109">Responder: The service that receives the initiator's requests.</span></span>  
  
 <span data-ttu-id="45385-110">In questo documento vengono utilizzati i prefissi e gli spazi dei nomi riportati nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="45385-110">This document uses the prefixes and namespaces in the following table.</span></span>  
  
|<span data-ttu-id="45385-111">Prefisso</span><span class="sxs-lookup"><span data-stu-id="45385-111">Prefix</span></span>|<span data-ttu-id="45385-112">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="45385-112">Namespace</span></span>|  
|-|-|  
|<span data-ttu-id="45385-113">wsrm</span><span class="sxs-lookup"><span data-stu-id="45385-113">wsrm</span></span>|<span data-ttu-id="45385-114">http://docs.oasis-open.org/ws-rx/wsrm/200702</span><span class="sxs-lookup"><span data-stu-id="45385-114">http://docs.oasis-open.org/ws-rx/wsrm/200702</span></span>|  
|<span data-ttu-id="45385-115">netrm</span><span class="sxs-lookup"><span data-stu-id="45385-115">netrm</span></span>|<span data-ttu-id="45385-116">http://schemas.microsoft.com/ws/2006/05/rm</span><span class="sxs-lookup"><span data-stu-id="45385-116">http://schemas.microsoft.com/ws/2006/05/rm</span></span>|  
|<span data-ttu-id="45385-117">s</span><span class="sxs-lookup"><span data-stu-id="45385-117">s</span></span>|<span data-ttu-id="45385-118">http://www.w3.org/2003/05/soap-envelope</span><span class="sxs-lookup"><span data-stu-id="45385-118">http://www.w3.org/2003/05/soap-envelope</span></span>|  
|<span data-ttu-id="45385-119">wsa</span><span class="sxs-lookup"><span data-stu-id="45385-119">wsa</span></span>|<span data-ttu-id="45385-120">http://schemas.xmlsoap.org/ws/2005/08/addressing</span><span class="sxs-lookup"><span data-stu-id="45385-120">http://schemas.xmlsoap.org/ws/2005/08/addressing</span></span>|  
|<span data-ttu-id="45385-121">wsse</span><span class="sxs-lookup"><span data-stu-id="45385-121">wsse</span></span>|<span data-ttu-id="45385-122">http://docs.oasis-open.org/wss/2004/01/oasis-200401-wssecurity-secext-1.0.xsd</span><span class="sxs-lookup"><span data-stu-id="45385-122">http://docs.oasis-open.org/wss/2004/01/oasis-200401-wssecurity-secext-1.0.xsd</span></span>|  
|<span data-ttu-id="45385-123">wsrmp</span><span class="sxs-lookup"><span data-stu-id="45385-123">wsrmp</span></span>|<span data-ttu-id="45385-124">http://docs.oasis-open.org/ws-rx/wsrmp/200702</span><span class="sxs-lookup"><span data-stu-id="45385-124">http://docs.oasis-open.org/ws-rx/wsrmp/200702</span></span>|  
|<span data-ttu-id="45385-125">netrmp</span><span class="sxs-lookup"><span data-stu-id="45385-125">netrmp</span></span>|<span data-ttu-id="45385-126">http://schemas.microsoft.com/ws-rx/wsrmp/200702</span><span class="sxs-lookup"><span data-stu-id="45385-126">http://schemas.microsoft.com/ws-rx/wsrmp/200702</span></span>|  
|<span data-ttu-id="45385-127">wsp</span><span class="sxs-lookup"><span data-stu-id="45385-127">wsp</span></span>|<span data-ttu-id="45385-128">(WS-Policy 1.2 o WS-Policy 1.5)</span><span class="sxs-lookup"><span data-stu-id="45385-128">(Either WS-Policy 1.2 or WS-Policy 1.5)</span></span>|  
  
## <a name="messaging"></a><span data-ttu-id="45385-129">Messaggistica</span><span class="sxs-lookup"><span data-stu-id="45385-129">Messaging</span></span>  
  
### <a name="sequence-creation"></a><span data-ttu-id="45385-130">Creazione sequenza</span><span class="sxs-lookup"><span data-stu-id="45385-130">Sequence Creation</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="45385-131"> implementa i messaggi `CreateSequence` e `CreateSequenceResponse` per stabilire una sequenza di messaggistica affidabile.</span><span class="sxs-lookup"><span data-stu-id="45385-131"> implements `CreateSequence` and `CreateSequenceResponse` messages to establish a reliable messaging sequence.</span></span> <span data-ttu-id="45385-132">Si applicano i vincoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="45385-132">The following constraints apply:</span></span>  
  
-   <span data-ttu-id="45385-133">B1101: l'iniziatore [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] utilizza lo stesso riferimento dell'endpoint di `CreateSequence`, `ReplyTo` e `AcksTo` del messaggio `Offer/Endpoint`.</span><span class="sxs-lookup"><span data-stu-id="45385-133">B1101: The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator uses the same endpoint reference as the `CreateSequence` message’s `ReplyTo`, `AcksTo` and `Offer/Endpoint`.</span></span>  
  
-   <span data-ttu-id="45385-134">R1102: i riferimenti degli endpoint `AcksTo`, `ReplyTo` e `Offer/Endpoint` nel messaggio `CreateSequence` devono avere valori di indirizzo con rappresentazioni di stringa identiche in modo che corrispondano all'ottetto.</span><span class="sxs-lookup"><span data-stu-id="45385-134">R1102: The `AcksTo`, `ReplyTo` and `Offer/Endpoint` endpoint references in the `CreateSequence` message must have address values with identical string representations such that they match the octet-wise.</span></span>  
  
    -   <span data-ttu-id="45385-135">Prima di creare una sequenza , il risponditore [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] verifica che la parte URI dei riferimenti degli endpoint `AcksTo`, `ReplyTo` e `Endpoint` siano identiche.</span><span class="sxs-lookup"><span data-stu-id="45385-135">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder verifies that the URI portion of the `AcksTo`, `ReplyTo` and `Endpoint` endpoint references are identical before creating a sequence.</span></span>  
  
-   <span data-ttu-id="45385-136">R1103: i riferimenti degli endpoint `AcksTo`, `ReplyTo` e `Offer/Endpoint` nel messaggio `CreateSequence` devono avere lo stesso set di parametri di riferimento.</span><span class="sxs-lookup"><span data-stu-id="45385-136">R1103: The `AcksTo`, `ReplyTo` and `Offer/Endpoint` endpoint references in the `CreateSequence` message should have the same set of reference parameters.</span></span>  
  
    -   [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="45385-137"> non impone, ma presuppone che i parametri di riferimento dei riferimenti degli endpoint `AcksTo`, `ReplyTo` e `Offer/Endpoint` in `CreateSequence` siano identici e utilizza i parametri di riferimento dal riferimento dell'endpoint `ReplyTo` per acknowledgement e messaggi in sequenza opposta.</span><span class="sxs-lookup"><span data-stu-id="45385-137"> does not enforce, but assumes that reference parameters of the `AcksTo`, `ReplyTo` and `Offer/Endpoint` endpoint references on `CreateSequence` are identical and uses reference parameters from the `ReplyTo` endpoint reference for acknowledgements and converse sequence messages.</span></span>  
  
-   <span data-ttu-id="45385-138">B1104: l'iniziatore [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] non genera l'elemento facoltativo `Expires` o `Offer/Expires` nel messaggio `CreateSequence`.</span><span class="sxs-lookup"><span data-stu-id="45385-138">B1104: The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator does not generate the optional `Expires` or `Offer/Expires` element in the `CreateSequence` message.</span></span>  
  
-   <span data-ttu-id="45385-139">B1105: quando si accede al messaggio `CreateSequence`, il risponditore [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] utilizza il valore `Expires` dell'elemento `CreateSequence` come valore `Expires` dell'elemento `CreateSequenceResponse`.</span><span class="sxs-lookup"><span data-stu-id="45385-139">B1105: When accessing the `CreateSequence` message, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder uses the `Expires` value in the `CreateSequence` element as the `Expires` value in the `CreateSequenceResponse` element.</span></span> <span data-ttu-id="45385-140">In caso contrario, il risponditore [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] legge e ignora i valori `Expires` e `Offer/Expires`.</span><span class="sxs-lookup"><span data-stu-id="45385-140">Otherwise, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder reads and ignores the `Expires` and `Offer/Expires` values.</span></span>  
  
-   <span data-ttu-id="45385-141">B1106: quando si accede al messaggio `CreateSequenceResponse`, l'iniziatore [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] legge il valore facoltativo `Expires`, ma non lo utilizza.</span><span class="sxs-lookup"><span data-stu-id="45385-141">B1106: When accessing the `CreateSequenceResponse` message, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator reads the optional `Expires` value but does not use it.</span></span>  
  
-   <span data-ttu-id="45385-142">B1107: l'iniziatore e il risponditore [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generano sempre l'elemento facoltativo `IncompleteSequenceBehavior` negli elementi `CreateSequence/Offer` e `CreateSequenceResponse`.</span><span class="sxs-lookup"><span data-stu-id="45385-142">B1107: The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator and Responder always generate the optional `IncompleteSequenceBehavior` element in the `CreateSequence/Offer` and `CreateSequenceResponse` elements.</span></span>  
  
-   <span data-ttu-id="45385-143">B1108: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] utilizza solo i valori `DiscardFollowingFirstGap` e `NoDiscard` nell'elemento `IncompleteSequenceBehavior`.</span><span class="sxs-lookup"><span data-stu-id="45385-143">B1108: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] uses only the `DiscardFollowingFirstGap` and `NoDiscard` values in the `IncompleteSequenceBehavior` element.</span></span>  
  
    -   <span data-ttu-id="45385-144">WS-ReliableMessaging utilizza il meccanismo `Offer` per stabilire le due sequenze correlate opposte che formano una sessione.</span><span class="sxs-lookup"><span data-stu-id="45385-144">WS-ReliableMessaging utilizes the `Offer` mechanism to establish the two converse correlated sequences that form a session.</span></span>  
  
-   <span data-ttu-id="45385-145">B1109: se `CreateSequence` contiene un elemento `Offer`, il risponditore unidirezionale [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] respinge la sequenza offerta rispondendo con un `CreateSequenceResponse` senza un elemento `Accept`.</span><span class="sxs-lookup"><span data-stu-id="45385-145">B1109: If `CreateSequence` contains an `Offer` element, the one way [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder rejects the offered sequence by responding with a `CreateSequenceResponse` without an `Accept` element.</span></span>  
  
-   <span data-ttu-id="45385-146">B1110: se un risponditore Reliable Messaging respinge la sequenza offerta, l'iniziatore [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] genera errori nella sequenza appena stabilita.</span><span class="sxs-lookup"><span data-stu-id="45385-146">B1110: If a Reliable Messaging Responder rejects the offered sequence, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator faults the newly established sequence.</span></span>  
  
-   <span data-ttu-id="45385-147">B1111: se `CreateSequence` non contiene un elemento `Offer`, il risponditore bidirezionale [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] respinge la sequenza offerta rispondendo con un errore `CreateSequenceRefused`.</span><span class="sxs-lookup"><span data-stu-id="45385-147">B1111: If `CreateSequence` does not contain an `Offer` element, the two-way [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder rejects the offered sequence by responding with a `CreateSequenceRefused` fault.</span></span>  
  
-   <span data-ttu-id="45385-148">R1112: quando vengono stabilite due sequenze opposte utilizzando il meccanismo `Offer`, la proprietà `[address]` del riferimento dell'endpoint `CreateSequenceResponse/Accept/AcksTo` deve corrispondere all'URI di destinazione del messaggio `CreateSequence`, byte per byte.</span><span class="sxs-lookup"><span data-stu-id="45385-148">R1112: When two converse sequences are established using the `Offer` mechanism, the `[address]` property of the `CreateSequenceResponse/Accept/AcksTo` endpoint reference must match the destination URI of the `CreateSequence` message byte for byte.</span></span>  
  
-   <span data-ttu-id="45385-149">R1113: quando vengono stabilite due sequenze opposte utilizzando il meccanismo `Offer`, tutti i messaggi su entrambe le sequenze dall'iniziatore al risponditore devono essere inviati allo stesso riferimento dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="45385-149">R1113: When two converse sequences are established using the `Offer` mechanism, all messages on both sequences flowing from the Initiator to the Responder must be sent to the same endpoint reference.</span></span>  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="45385-150"> utilizza WS-ReliableMessaging per stabilire sessioni affidabili tra l'iniziatore e il risponditore.</span><span class="sxs-lookup"><span data-stu-id="45385-150"> uses WS-ReliableMessaging to establish reliable sessions between the Initiator and the Responder.</span></span> <span data-ttu-id="45385-151">L'implementazione di WS-ReliableMessaging di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] offre una sessione affidabile per modelli di messaggistica unidirezionali, request/reply e full duplex.</span><span class="sxs-lookup"><span data-stu-id="45385-151">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] WS-ReliableMessaging implementation provides a reliable session for one-way, request-reply and full duplex messaging patterns.</span></span> <span data-ttu-id="45385-152">Il meccanismo `Offer` di WS-Reliable Messaging in `CreateSequence` e `CreateSequenceResponse` consente di stabilire due sequenze opposte correlate e fornisce un protocollo della sessione idoneo per tutti gli endpoint del messaggio.</span><span class="sxs-lookup"><span data-stu-id="45385-152">The WS-ReliableMessaging `Offer` mechanism on `CreateSequence` and `CreateSequenceResponse` lets you establish two correlated converse sequences and provides a session protocol that is suitable for all message endpoints.</span></span> <span data-ttu-id="45385-153">Dato che [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] fornisce una garanzia di sicurezza per tale sessione, inclusa la protezione end-to-end per l'integrità della sessione, è consigliabile assicurarsi che i messaggi destinati alla stessa parte arrivino alla stessa destinazione.</span><span class="sxs-lookup"><span data-stu-id="45385-153">Because [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] provides a security guarantee for such a session including end-to-end protection for session integrity, it is practical to ensure that messages intended for the same party arrive at the same destination.</span></span> <span data-ttu-id="45385-154">Ciò consente anche il "piggy-backing" degli acknowledgement della sequenza sui messaggi dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="45385-154">This also allows "piggy-backing" of sequence acknowledgements on application messages.</span></span> <span data-ttu-id="45385-155">Pertanto, applicano vincoli R1102 R1112 e R1113 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="45385-155">Therefore, constraints R1102, R1112, and R1113 apply to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span>  
  
 <span data-ttu-id="45385-156">Esempio di un messaggio `CreateSequence`.</span><span class="sxs-lookup"><span data-stu-id="45385-156">An example of a `CreateSequence` message.</span></span>  
  
```xml  
<s:Envelope>  
  <s:Header>  
    <wsa:Action s:mustUnderstand="1">http://docs.oasis-open.org/ws-rx/wsrm/200702/CreateSequence</wsa:Action>  
    <wsa:MessageID>urn:uuid:949cca61-8813-42ff-ab33-18d9e3fa82fa</wsa:MessageID>  
    <wsa:ReplyTo>  
        <wsa:Address>http://Business456.com/clientA</wsa:Address>   
    </wsa:ReplyTo>  
    <wsa:To s:mustUnderstand="1">http://BusinessABC.com/serviceA</wsa:To>  
  </s:Header>  
  <s:Body>  
    <wsrm:CreateSequence>  
      <wsrm:AcksTo>  
        <wsa:Address>http://Business456.com/clientA</wsa:Address>  
      </wsrm:AcksTo>  
      <wsrm:Offer>  
        <wsrm:Identifier>urn:uuid:066b4730-fc82-458a-a5c1-210be4fb4e4e</wsrm:Identifier>  
        <wsrm:Endpoint>  
          <wsa:Address>http://Business456.com/clientA</wsa:Address>  
        </wsrm:Endpoint>  
        <wsrm:IncompleteSequenceBehavior>DiscardFollowingFirstGap</wsrm:IncompleteSequenceBehavior>  
      </wsrm:Offer>  
    </wsrm:CreateSequence>  
  </s:Body>  
</s:Envelope>  
```  
  
 <span data-ttu-id="45385-157">Esempio di un messaggio `CreateSequenceResponse`.</span><span class="sxs-lookup"><span data-stu-id="45385-157">An example of a `CreateSequenceResponse` message.</span></span>  
  
```xml  
<s:Envelope>  
  <s:Header>  
    <wsa:Action s:mustUnderstand="1">http://docs.oasis-open.org/ws-rx/wsrm/200702/CreateSequenceResponse</wsa:Action>  
    <wsa:RelatesTo>urn:uuid:949cca61-8813-42ff-ab33-18d9e3fa82fa</wsa:RelatesTo>  
    <wsa:To s:mustUnderstand="1">http://Business456.com/clientA</wsa:To>  
  </s:Header>  
  <s:Body>  
    <wsrm:CreateSequenceResponse>  
      <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
      <wsrm:IncompleteSequenceBehavior>DiscardFollowingFirstGap</wsrm:IncompleteSequenceBehavior>  
      <wsrm:Accept>  
        <wsrm:AcksTo>  
          <wsa:Address>http://BusinessABC.com/serviceA</wsa:Address>  
        </wsrm:AcksTo>  
      </wsrm:Accept>  
    </wsrm:CreateSequenceResponse>  
  </s:Body>  
</s:Envelope>  
```  
  
### <a name="closing-a-sequence"></a><span data-ttu-id="45385-158">Chiusura di una sequenza</span><span class="sxs-lookup"><span data-stu-id="45385-158">Closing a Sequence</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="45385-159"> utilizza i messaggi `CloseSequence` e `CloseSequenceResponse` per un arresto iniziato dall'origine di Reliable Messaging.</span><span class="sxs-lookup"><span data-stu-id="45385-159"> uses the `CloseSequence` and `CloseSequenceResponse` messages for a Reliable Messaging source-initiated shutdown.</span></span> <span data-ttu-id="45385-160">La destinazione di Reliable Messaging di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] non inizia l'arresto e l'origine di Reliable Messaging di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] non supporta un arresto iniziato dalla destinazione di Reliable Messaging.</span><span class="sxs-lookup"><span data-stu-id="45385-160">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Reliable Messaging destination does not initiate shutdown and the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Reliable Messaging source does not support a Reliable Messaging destination-initiated shutdown.</span></span> <span data-ttu-id="45385-161">Si applicano i vincoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="45385-161">The following constraints apply:</span></span>  
  
-   <span data-ttu-id="45385-162">B1201: l'origine di Reliable Messaging di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] invia sempre un messaggio `CloseSequence` per chiudere la sequenza.</span><span class="sxs-lookup"><span data-stu-id="45385-162">B1201: The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Reliable Messaging source always sends a `CloseSequence` message to shut down the sequence.</span></span>  
  
-   <span data-ttu-id="45385-163">B1202: l'origine di Reliable Messaging attende l'acknowledgment dell'intera serie di messaggi della sequenza prima di inviare il messaggio `CloseSequence`.</span><span class="sxs-lookup"><span data-stu-id="45385-163">B1202: The Reliable Messaging source waits for acknowledgement of the full range of sequence messages before sending the `CloseSequence` message.</span></span>  
  
-   <span data-ttu-id="45385-164">B1203: l'origine di Reliable Messaging include sempre l'elemento facoltativo `LastMsgNumber`. Non lo include se la sequenza non contiene messaggi.</span><span class="sxs-lookup"><span data-stu-id="45385-164">B1203: The Reliable Messaging source always includes the optional `LastMsgNumber` element unless the sequence does not contain messages.</span></span>  
  
-   <span data-ttu-id="45385-165">R1204: la destinazione di Reliable Messaging non deve iniziare l'arresto inviando un messaggio `CloseSequence`.</span><span class="sxs-lookup"><span data-stu-id="45385-165">R1204: The Reliable Messaging destination must not initiate shutdown by sending a `CloseSequence` message.</span></span>  
  
-   <span data-ttu-id="45385-166">B1205: al ricevimento di un messaggio `CloseSequence`, l'origine di Reliable Messaging di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] considera la sequenza incompleta e invia un errore.</span><span class="sxs-lookup"><span data-stu-id="45385-166">B1205: Upon receiving a `CloseSequence` message, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Reliable Messaging source considers the sequence incomplete and sends a fault.</span></span>  
  
 <span data-ttu-id="45385-167">Esempio di un messaggio `CloseSequence`.</span><span class="sxs-lookup"><span data-stu-id="45385-167">An example of a `CloseSequence` message.</span></span>  
  
```xml  
<s:Envelope>  
  <s:Header>  
    <wsa:Action s:mustUnderstand="1">http://docs.oasis-open.org/ws-rx/wsrm/200702/CloseSequence</wsa:Action>  
    <wsa:MessageID>urn:uuid:6ce1d4c3-e1c1-474f-a8c9-4210e37f7877</wsa:MessageID>  
    <wsa:ReplyTo>  
      <wsa:Address>http://Business456.com/clientA</wsa:Address>  
    </wsa:ReplyTo>  
    <wsa:To s:mustUnderstand="1">http://BusinessABC.com/serviceA</wsa:To>  
  </s:Header>  
  <s:Body>  
    <wsrm:CloseSequence>  
      <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
      <wsrm:LastMsgNumber>30</wsrm:LastMsgNumber>  
    </wsrm:CloseSequence>  
  </s:Body>  
</s:Envelope>  
Example CloseSequenceResponse message:  
<s:Envelope>  
  <s:Header>  
    <wsrm:SequenceAcknowledgement>  
      <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
      <wsrm:AcknowledgementRange Lower="1" Upper="30"></wsrm:AcknowledgementRange>  
      <wsrm:Final></wsrm:Final>  
      <netrm:BufferRemaining>8</netrm:BufferRemaining>  
    </wsrm:SequenceAcknowledgement>  
    <wsa:Action s:mustUnderstand="1">http://docs.oasis-open.org/ws-rx/wsrm/200702/CloseSequenceResponse</wsa:Action>  
    <wsa:RelatesTo>urn:uuid:6ce1d4c3-e1c1-474f-a8c9-4210e37f7877</wsa:RelatesTo>  
    <wsa:To s:mustUnderstand="1">http://Business456.com/clientA</wsa:To>  
  </s:Header>  
  <s:Body>  
    <wsrm:CloseSequenceResponse>  
      <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
    </wsrm:CloseSequenceResponse>  
  </s:Body>  
</s:Envelope>  
```  
  
### <a name="sequence-termination"></a><span data-ttu-id="45385-168">Terminazione della sequenza</span><span class="sxs-lookup"><span data-stu-id="45385-168">Sequence Termination</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="45385-169"> utilizza principalmente l'handshake `TerminateSequence/TerminateSequenceResponse` al completamento dell'handshake `CloseSequence/CloseSequenceResponse`.</span><span class="sxs-lookup"><span data-stu-id="45385-169"> primarily uses the `TerminateSequence/TerminateSequenceResponse` handshake after completing the `CloseSequence/CloseSequenceResponse` handshake.</span></span> <span data-ttu-id="45385-170">La destinazione di Reliable Messaging di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] non inizia la terminazione e l'origine di Reliable Messaging non supporta una terminazione iniziata dalla destinazione di Reliable Messaging.</span><span class="sxs-lookup"><span data-stu-id="45385-170">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Reliable Messaging destination does not initiate termination and the Reliable Messaging source does not support a Reliable Messaging destination-initiated termination.</span></span> <span data-ttu-id="45385-171">Si applicano i vincoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="45385-171">The following constraints apply:</span></span>  
  
-   <span data-ttu-id="45385-172">B1301: l'iniziatore [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] invia il messaggio `TerminateSequence` solo al completamento corretto dell'handshake `CloseSequence/CloseSequenceResponse`.</span><span class="sxs-lookup"><span data-stu-id="45385-172">B1301: The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator only sends the `TerminateSequence` message after the successful completion of the `CloseSequence/CloseSequenceResponse` handshake.</span></span>  
  
-   <span data-ttu-id="45385-173">R1302: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] controlla che l'elemento `LastMsgNumber` sia coerente in tutti i messaggi `CloseSequence` e `TerminateSequence` per una data sequenza.</span><span class="sxs-lookup"><span data-stu-id="45385-173">R1302: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] validates that the `LastMsgNumber` element is consistent across all `CloseSequence` and `TerminateSequence` messages for a given sequence.</span></span> <span data-ttu-id="45385-174">Ciò significa che `LastMsgNumber` o non è presente in tutti i messaggi `CloseSequence` e `TerminateSequence`, o è presente e identico in tutti i messaggi `CloseSequence` e `TerminateSequence`.</span><span class="sxs-lookup"><span data-stu-id="45385-174">This means that `LastMsgNumber` is either not present on all `CloseSequence` and `TerminateSequence` messages, or it is present and identical on all `CloseSequence` and `TerminateSequence` messages.</span></span>  
  
-   <span data-ttu-id="45385-175">B1303: al ricevimento di un messaggio `TerminateSequence` dopo l'handshake `CloseSequence/CloseSequenceResponse`, la destinazione di Reliable Messaging risponde con un messaggio `TerminateSequenceResponse`.</span><span class="sxs-lookup"><span data-stu-id="45385-175">B1303: When receiving a `TerminateSequence` message after the `CloseSequence/CloseSequenceResponse` handshake, the Reliable Messaging destination responds with a `TerminateSequenceResponse` message.</span></span> <span data-ttu-id="45385-176">Poiché l'origine di Reliable Messaging dispone dell'acknowledgement finale prima dell'invio del messaggio `TerminateSequence`, la destinazione di Reliable Messaging è a conoscenza della fine della sequenza e richiede immediatamente le risorse.</span><span class="sxs-lookup"><span data-stu-id="45385-176">Because the Reliable Messaging source has the final acknowledgement before sending the `TerminateSequence` message, the Reliable Messaging destination knows without doubt that the sequence ends, and reclaims resources immediately.</span></span>  
  
-   <span data-ttu-id="45385-177">B1304: se viene ricevuto un messaggio `TerminateSequence` prima dell'handshake `CloseSequence/CloseSequenceResponse`, la destinazione di Reliable Messaging di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] risponde con un messaggio `TerminateSequenceResponse`.</span><span class="sxs-lookup"><span data-stu-id="45385-177">B1304: When receiving a `TerminateSequence` message prior to the `CloseSequence/CloseSequenceResponse` handshake, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Reliable Messaging destination responds with a `TerminateSequenceResponse` message.</span></span> <span data-ttu-id="45385-178">Se la destinazione di Reliable Messaging stabilisce che non vi sono incoerenze nella sequenza, attende per il periodo di tempo specificato dalla destinazione dell'applicazione prima di richiedere le risorse, per offrire al client la possibilità di ricevere l'acknowledgement finale.</span><span class="sxs-lookup"><span data-stu-id="45385-178">If the Reliable Messaging destination determines that there are no inconsistencies in the sequence, the Reliable Messaging destination waits for an application destination-specified time before reclaiming resources, to allow the client the chance to receive the final acknowledgement.</span></span> <span data-ttu-id="45385-179">In caso contrario, la destinazione di Reliable Messaging richiede immediatamente le risorse e indica alla destinazione dell'applicazione che la sequenza termina in modo dubbio generando l'evento `Faulted`.</span><span class="sxs-lookup"><span data-stu-id="45385-179">Otherwise, the Reliable Messaging destination reclaims resources immediately and indicates to the application destination that the sequence ends with doubt by raising the `Faulted` event.</span></span>  
  
 <span data-ttu-id="45385-180">Esempio di un messaggio `TerminateSequence`.</span><span class="sxs-lookup"><span data-stu-id="45385-180">An example of a `TerminateSequence` message.</span></span>  
  
```xml  
<s:Envelope>  
  <s:Header>  
    <wsa:Action s:mustUnderstand="1">http://docs.oasis-open.org/ws-rx/wsrm/200702/TerminateSequence</wsa:Action>  
    <wsa:MessageID>urn:uuid:3597a398-4f3c-40f4-9335-8f1515572fdf</wsa:MessageID>  
    <wsa:ReplyTo>  
      <wsa:Address>http://Business456.com/clientA</wsa:Address>  
    </wsa:ReplyTo>  
    <wsa:To s:mustUnderstand="1">http://BusinessABC.com/serviceA</wsa:To>  
  </s:Header>  
  <s:Body>  
    <wsrm:TerminateSequence>  
      <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
      <wsrm:LastMsgNumber>30</wsrm:LastMsgNumber>  
      </wsrm:TerminateSequence>  
  </s:Body>  
</s:Envelope>  
Example TerminateSequenceResponse message:  
<s:Envelope>  
  <s:Header>  
    <wsrm:SequenceAcknowledgement>  
      <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
      <wsrm:AcknowledgementRange Lower="1" Upper="30"></wsrm:AcknowledgementRange>  
      <wsrm:Final></wsrm:Final>  
      <netrm:BufferRemaining>8</netrm:BufferRemaining>  
    </wsrm:SequenceAcknowledgement>  
    <wsa:Action s:mustUnderstand="1">http://docs.oasis-open.org/ws-rx/wsrm/200702/TerminateSequenceResponse</wsa:Action>  
    <wsa:RelatesTo>urn:uuid:3597a398-4f3c-40f4-9335-8f1515572fdf</wsa:RelatesTo>  
    <wsa:To s:mustUnderstand="1">://Business456.com/clientA</wsa:To>  
  </s:Header>  
  <s:Body>  
    <wsrm:TerminateSequenceResponse>  
      <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
    </wsrm:TerminateSequenceResponse>  
  </s:Body>  
</s:Envelope>  
```  
  
### <a name="sequences"></a><span data-ttu-id="45385-181">Sequenze</span><span class="sxs-lookup"><span data-stu-id="45385-181">Sequences</span></span>  
 <span data-ttu-id="45385-182">Di seguito è riportato un elenco di vincoli che si applicano alle sequenze:</span><span class="sxs-lookup"><span data-stu-id="45385-182">The following is a list of constraints that apply to sequences:</span></span>  
  
-   <span data-ttu-id="45385-183">B1401:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] genera l'errore e accede a numeri di sequenza non superiori a `xs:long`del valore inclusivo massimo, 9223372036854775807.</span><span class="sxs-lookup"><span data-stu-id="45385-183">B1401:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generates and accesses sequence numbers no higher than `xs:long`’s maximum inclusive value, 9223372036854775807.</span></span>  
  
 <span data-ttu-id="45385-184">Esempio di intestazione `Sequence`.</span><span class="sxs-lookup"><span data-stu-id="45385-184">An example of a `Sequence` header.</span></span>  
  
```xml  
<wsrm:Sequence s:mustUnderstand="1">  
  <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
  <wsrm:MessageNumber>1</wsrm:MessageNumber>  
</wsrm:Sequence>  
```  
  
### <a name="request-acknowledgement"></a><span data-ttu-id="45385-185">Acknowledgement della richiesta</span><span class="sxs-lookup"><span data-stu-id="45385-185">Request Acknowledgement</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="45385-186"> utilizza l'intestazione `AckRequested` come meccanismo keep-alive.</span><span class="sxs-lookup"><span data-stu-id="45385-186"> uses the `AckRequested` header as a keep-alive mechanism.</span></span>  
  
 <span data-ttu-id="45385-187">Esempio di intestazione `AckRequested`.</span><span class="sxs-lookup"><span data-stu-id="45385-187">An example of an `AckRequested` header.</span></span>  
  
```xml  
<wsrm:AckRequested>  
  <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
</wsrm:AckRequested>  
```  
  
### <a name="sequenceacknowledgement"></a><span data-ttu-id="45385-188">SequenceAcknowledgement</span><span class="sxs-lookup"><span data-stu-id="45385-188">SequenceAcknowledgement</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="45385-189"> utilizza un meccanismo "piggy-back" per gli acknowledgement di sequenza forniti in WS-Reliable Messaging.</span><span class="sxs-lookup"><span data-stu-id="45385-189"> uses a "piggy-back" mechanism for sequence acknowledgements provided in WS-Reliable Messaging.</span></span> <span data-ttu-id="45385-190">Si applicano i vincoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="45385-190">The following constraints apply:</span></span>  
  
-   <span data-ttu-id="45385-191">R1601: Quando due sequenze vengono stabilite opposte utilizzando il `Offer` meccanismo, il `SequenceAcknowledgement` intestazione può essere incluso nei messaggi dell'applicazione trasmesso al destinatario prescelto.</span><span class="sxs-lookup"><span data-stu-id="45385-191">R1601: When two converse sequences are established using the `Offer` mechanism, the `SequenceAcknowledgement` header may be included in any application message transmitted to the intended recipient.</span></span> <span data-ttu-id="45385-192">L'endpoint remoto deve essere in grado di accedere a un'intestazione `SequenceAcknowledgement` sottoposta a piggyback.</span><span class="sxs-lookup"><span data-stu-id="45385-192">The remote endpoint must be able to access a piggybacked `SequenceAcknowledgement` header.</span></span>  
  
-   <span data-ttu-id="45385-193">B1602: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] non genera intestazioni `SequenceAcknowledgement` che contengono elementi `Nack`.</span><span class="sxs-lookup"><span data-stu-id="45385-193">B1602: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] does not generate `SequenceAcknowledgement` headers that contain `Nack` elements.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="45385-194"> verifica che ogni elemento `Nack` contenga un numero di sequenza, ma altrimenti ignora l'elemento e il valore `Nack`.</span><span class="sxs-lookup"><span data-stu-id="45385-194"> validates that each `Nack` element contains a sequence number, but otherwise ignores the `Nack` element and value.</span></span>  
  
 <span data-ttu-id="45385-195">Esempio di intestazione `SequenceAcknowledgement`.</span><span class="sxs-lookup"><span data-stu-id="45385-195">An example of a `SequenceAcknowledgement` header.</span></span>  
  
```xml  
<wsrm:SequenceAcknowledgement>  
  <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
  <wsrm:AcknowledgementRange Lower="1" Upper="1"></wsrm:AcknowledgementRange>  
</wsrm:SequenceAcknowledgement>  
```  
  
### <a name="ws-reliablemessaging-faults"></a><span data-ttu-id="45385-196">Errori WS-ReliableMessaging</span><span class="sxs-lookup"><span data-stu-id="45385-196">WS-ReliableMessaging Faults</span></span>  
 <span data-ttu-id="45385-197">Di seguito è riportato un elenco di vincoli che si applicano all'implementazione [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] di errori WS-ReliableMessaging.</span><span class="sxs-lookup"><span data-stu-id="45385-197">The following is a list of constraints that apply to the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] implementation of WS-ReliableMessaging faults.</span></span> <span data-ttu-id="45385-198">Si applicano i vincoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="45385-198">The following constraints apply:</span></span>  
  
-   <span data-ttu-id="45385-199">B1701: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] non genera `MessageNumberRollover` errori.</span><span class="sxs-lookup"><span data-stu-id="45385-199">B1701: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] does not generate `MessageNumberRollover` faults.</span></span>  
  
-   <span data-ttu-id="45385-200">B1702: su SOAP 1.2 quando l'endpoint del servizio raggiunge il limite di connessione e non è in grado di elaborare nuove connessioni, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] genera un codice secondario dell'errore `CreateSequenceRefused` annidato, `netrm:ConnectionLimitReached`, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="45385-200">B1702: Over SOAP 1.2, when the service endpoint reaches its connection limit and cannot process new connections, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generates a nested `CreateSequenceRefused` fault subcode, `netrm:ConnectionLimitReached`, as shown in the following example.</span></span>  
  
```xml  
<s:Envelope>  
  <s:Header>  
    <wsa:Action>http://docs.oasis-open.org/ws-rx/wsrm/200702/fault</wsa:Action>  
  </s:Header>  
  <s:Body>  
    <s:Fault>  
      <s:Code>  
        <s:Value>s:Receiver</s:Value>  
        <s:Subcode>  
          <s:Value>wsrm:CreateSequenceRefused</s:Value>  
          <s:Subcode>  
            <s:Value>netrm:ConnectionLimitReached</s:Value>  
          </s:Subcode>  
        </s:Subcode>  
      </s:Code>  
      <s:Reason>  
        <s:Text xml:lang="en">Server 'http://BusinessABC.com/serviceA' is too busy to process this request. Try again later.</s:Text>  
      </s:Reason>  
    </s:Fault>  
  </s:Body>  
</s:Envelope>  
```  
  
### <a name="ws-addressing-faults"></a><span data-ttu-id="45385-201">Errori WS-Addressing</span><span class="sxs-lookup"><span data-stu-id="45385-201">WS-Addressing Faults</span></span>  
 <span data-ttu-id="45385-202">Dato che WS-ReliableMessaging utilizza WS-Addressing, l'implementazione WS-ReliableMessaging di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] potrebbe generare e trasmettere errori WS-Addressing.</span><span class="sxs-lookup"><span data-stu-id="45385-202">Because WS-ReliableMessaging uses WS-Addressing, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] WS-ReliableMessaging implementation may generate and transmit WS-Addressing faults.</span></span> <span data-ttu-id="45385-203">Contenuto della sezione vengono illustrati gli errori WS-Addressing generati e trasmessi in modo esplicito da [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] a livello di WS-ReliableMessaging:</span><span class="sxs-lookup"><span data-stu-id="45385-203">This section covers the WS-Addressing faults that [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] explicitly generates and transmits at the WS-ReliableMessaging layer:</span></span>  
  
-   <span data-ttu-id="45385-204">B1801:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] genera e trasmette il `Message Addressing Header Required` di errore quando viene soddisfatta una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="45385-204">B1801:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generates and transmits the `Message Addressing Header Required` fault when one of the following is true:</span></span>  
  
    -   <span data-ttu-id="45385-205">In un messaggio `CreateSequence`, `CloseSequence` o `TerminateSequence` manca un'intestazione `MessageId`.</span><span class="sxs-lookup"><span data-stu-id="45385-205">A `CreateSequence`, `CloseSequence` or `TerminateSequence` message is missing a `MessageId` header.</span></span>  
  
    -   <span data-ttu-id="45385-206">In un messaggio `CreateSequence`, `CloseSequence` o `TerminateSequence` manca un'intestazione `ReplyTo`.</span><span class="sxs-lookup"><span data-stu-id="45385-206">A `CreateSequence`, `CloseSequence` or `TerminateSequence` message is missing a `ReplyTo` header.</span></span>  
  
    -   <span data-ttu-id="45385-207">In un messaggio `CreateSequenceResponse`, `CloseSequenceResponse` o `TerminateSequenceResponse` manca un'intestazione `RelatesTo`.</span><span class="sxs-lookup"><span data-stu-id="45385-207">A `CreateSequenceResponse`, `CloseSequenceResponse`, or `TerminateSequenceResponse` message is missing a `RelatesTo` header.</span></span>  
  
-   <span data-ttu-id="45385-208">B1802:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] genera e trasmette il `Endpoint Unavailable` errore per indicare nessun endpoint di ascolto in grado di elaborare la sequenza in base all'esame delle intestazioni di indirizzamento nel `CreateSequence` messaggio.</span><span class="sxs-lookup"><span data-stu-id="45385-208">B1802:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generates and transmits the `Endpoint Unavailable` fault to indicate there is no endpoint listening that can process the sequence based on examination of the addressing headers in the `CreateSequence` message.</span></span>  
  
## <a name="protocol-composition"></a><span data-ttu-id="45385-209">Composizione del protocollo</span><span class="sxs-lookup"><span data-stu-id="45385-209">Protocol Composition</span></span>  
  
### <a name="composition-with-ws-addressing"></a><span data-ttu-id="45385-210">Composizione con WS-Addressing</span><span class="sxs-lookup"><span data-stu-id="45385-210">Composition with WS-Addressing</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="45385-211"> supporta due versioni di WS-Addressing: WS-Addressing 2004/08 [WS-ADDR] e W3C WS-Addressing 1.0 Recommendation [WS-ADDR-CORE] e [WS-ADDR-SOAP].</span><span class="sxs-lookup"><span data-stu-id="45385-211"> supports two versions of WS-Addressing: WS-Addressing 2004/08 [WS-ADDR] and W3C WS-Addressing 1.0 Recommendations [WS-ADDR-CORE] and [WS-ADDR-SOAP].</span></span>  
  
 <span data-ttu-id="45385-212">Anche se la specifica WS-ReliableMessaging menziona solo WS-Addressing 2004/08, non limita la versione WS-Addressing da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="45385-212">While the WS-ReliableMessaging specification mentions only WS-Addressing 2004/08, it does not restrict the WS-Addressing version to be used.</span></span> <span data-ttu-id="45385-213">Di seguito è riportato un elenco di vincoli che si applicano a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="45385-213">The following is a list of constraints that apply to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]:</span></span>  
  
-   <span data-ttu-id="45385-214">R2101: sia WS-Addressing 2004/08 che WS-Addressing 1.0 possono essere utilizzati con WS-Reliable Messaging.</span><span class="sxs-lookup"><span data-stu-id="45385-214">R2101: Both WS-Addressing 2004/08 and WS-Addressing 1.0 can be used with WS-Reliable Messaging.</span></span>  
  
-   <span data-ttu-id="45385-215">R2102: è necessario utilizzare una sola versione di WS-Addressing in una data sequenza di WS-Reliable Messaging o in una coppia di sequenze opposte correlate tramite il meccanismo `Offer`.</span><span class="sxs-lookup"><span data-stu-id="45385-215">R2102: A single version of WS-Addressing must be used throughout a given WS-ReliableMessaging sequence or a pair of converse sequences correlated by using the `Offer` mechanism.</span></span>  
  
### <a name="composition-with-soap"></a><span data-ttu-id="45385-216">Composizione con SOAP</span><span class="sxs-lookup"><span data-stu-id="45385-216">Composition with SOAP</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="45385-217"> supporta l'utilizzo sia di SOAP 1.1 che di SOAP 1.2 con WS-Reliable Messaging.</span><span class="sxs-lookup"><span data-stu-id="45385-217"> supports the use of both SOAP 1.1 and SOAP 1.2 with WS-Reliable Messaging.</span></span>  
  
### <a name="composition-with-ws-security-and-ws-secureconversation"></a><span data-ttu-id="45385-218">Composizione con WS-Security e WS-SecureConversation</span><span class="sxs-lookup"><span data-stu-id="45385-218">Composition with WS-Security and WS-SecureConversation</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="45385-219"> fornisce protezione per le sequenze di WS-Reliable Messaging utilizzando trasporto protetto (HTTPS), composizione con WS-Security e composizione con WS-SecureConversation.</span><span class="sxs-lookup"><span data-stu-id="45385-219"> provides protection for WS-ReliableMessaging sequences by using secure Transport (HTTPS), composition with WS-Security, and composition with WS-Secure Conversation.</span></span> <span data-ttu-id="45385-220">Il protocollo WS-Reliable Messaging 1.1, WS-Security 1.1 e il protocollo WS-SecureConversation 1.3 devono essere utilizzati insieme.</span><span class="sxs-lookup"><span data-stu-id="45385-220">The WS-ReliableMessaging 1.1 protocol, WS-Security 1.1 and WS-Secure Conversation 1.3 protocol should be used together.</span></span> <span data-ttu-id="45385-221">Di seguito è riportato un elenco di vincoli che si applicano a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="45385-221">The following is a list of constraints that apply to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]:</span></span>  
  
-   <span data-ttu-id="45385-222">R2301: per proteggere l'integrità di una sequenza di WS-Reliable Messaging oltre all'integrità e alla riservatezza dei singoli messaggi, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] richiede l'utilizzo di WS-SecureConversation.</span><span class="sxs-lookup"><span data-stu-id="45385-222">R2301: To protect the integrity of a WS-ReliableMessaging sequence in addition to the integrity and confidentiality of individual messages, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] requires that WS-Secure Conversation must be used.</span></span>  
  
-   <span data-ttu-id="45385-223">R2302:AWS-Secure Conversation deve essere stabilita prima di stabilire le sequenze di WS-ReliableMessaging.</span><span class="sxs-lookup"><span data-stu-id="45385-223">R2302:AWS-Secure Conversation session must be established prior to establishing WS-ReliableMessaging sequence(s).</span></span>  
  
-   <span data-ttu-id="45385-224">R2303: se la durata della sequenza di WS-Reliable Messaging supera la durata della sessione WS-SecureConversation, è necessario rinnovare il `SecurityContextToken` stabilito tramite WS-SecureConversation utilizzando l'associazione WS-Secure Conversation Renewal corrispondente.</span><span class="sxs-lookup"><span data-stu-id="45385-224">R2303: If the WS-ReliableMessaging sequence lifetime exceeds the WS-Secure Conversation session’s lifetime, the `SecurityContextToken` established by using WS-Secure Conversation must be renewed by using the corresponding WS-Secure Conversation Renewal binding.</span></span>  
  
-   <span data-ttu-id="45385-225">B2304:ws-sequenza ReliableMessaging o una coppia di sequenze opposte sono sempre associate a una singola sessione WS-SecureConversation.</span><span class="sxs-lookup"><span data-stu-id="45385-225">B2304:WS-ReliableMessaging sequence or a pair of correlated converse sequences are always bound to a single WS-SecureConversation session.</span></span>  
  
-   <span data-ttu-id="45385-226">R2305: in caso di composizione con WS-SecureConversation, il risponditore [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] richiede che il messaggio `CreateSequence` contenga l'elemento `wsse:SecurityTokenReference` e l'intestazione `wsrm:UsesSequenceSTR`.</span><span class="sxs-lookup"><span data-stu-id="45385-226">R2305: When composed with WS-Secure Conversation, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] responder requires that the `CreateSequence` message contain the `wsse:SecurityTokenReference` element and the `wsrm:UsesSequenceSTR` header.</span></span>  
  
 <span data-ttu-id="45385-227">Esempio di intestazione `UsesSequenceSTR`.</span><span class="sxs-lookup"><span data-stu-id="45385-227">An example of a `UsesSequenceSTR` header.</span></span>  
  
```xml  
<wsrm:UsesSequenceSTR></wsrm:UsesSequenceSTR>  
```  
  
### <a name="composition-with-ssltls-sessions"></a><span data-ttu-id="45385-228">Composizione con sessioni SSL/TLS</span><span class="sxs-lookup"><span data-stu-id="45385-228">Composition with SSL/TLS sessions</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="45385-229"> non supporta la composizione con sessioni SSL/TLS:</span><span class="sxs-lookup"><span data-stu-id="45385-229"> does not support composition with SSL/TLS sessions:</span></span>  
  
-   <span data-ttu-id="45385-230">B2401: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] non genera l'intestazione `wsrm:UsesSequenceSSL`.</span><span class="sxs-lookup"><span data-stu-id="45385-230">B2401: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] does not generate the `wsrm:UsesSequenceSSL` header.</span></span>  
  
-   <span data-ttu-id="45385-231">R2402: un iniziatore Reliable Messaging non deve inviare un messaggio `CreateSequence` con l'intestazione `wsrm:UsesSequenceSSL` a un risponditore [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="45385-231">R2402: A Reliable Messaging Initiator must not send a `CreateSequence` message with a `wsrm:UsesSequenceSSL` header to a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder.</span></span>  
  
### <a name="composition-with-ws-policy"></a><span data-ttu-id="45385-232">Composizione con WS-Policy</span><span class="sxs-lookup"><span data-stu-id="45385-232">Composition with WS-Policy</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="45385-233"> supporta due versioni di WS-Policy: WS-Policy 1.2 e WS-Policy 1.5.</span><span class="sxs-lookup"><span data-stu-id="45385-233"> supports two versions of WS-Policy: WS-Policy 1.2 and WS-Policy 1.5.</span></span>  
  
## <a name="ws-reliablemessaging-ws-policy-assertion"></a><span data-ttu-id="45385-234">Asserzione di WS-Policy relativa a WS-ReliableMessaging</span><span class="sxs-lookup"><span data-stu-id="45385-234">WS-ReliableMessaging WS-Policy Assertion</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="45385-235"> utilizza l'asserzione di WS-Policy `wsrm:RMAssertion` relativa a WS-ReliableMessaging per descrivere le funzionalità degli endpoint.</span><span class="sxs-lookup"><span data-stu-id="45385-235"> uses WS-ReliableMessaging WS-Policy Assertion `wsrm:RMAssertion` to describe endpoints capabilities.</span></span> <span data-ttu-id="45385-236">Di seguito è riportato un elenco di vincoli che si applicano a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="45385-236">The following is a list of constraints that apply to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]:</span></span>  
  
-   <span data-ttu-id="45385-237">B3001: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] collega l'asserzione di WS-Policy `wsrmn:RMAssertion` agli elementi `wsdl:binding`.</span><span class="sxs-lookup"><span data-stu-id="45385-237">B3001: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] attaches `wsrmn:RMAssertion` WS-Policy Assertion to `wsdl:binding` elements.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="45385-238"> supporta i collegamenti agli elementi `wsdl:binding` e `wsdl:port`.</span><span class="sxs-lookup"><span data-stu-id="45385-238"> supports both attachments to `wsdl:binding` and `wsdl:port` elements.</span></span>  
  
-   <span data-ttu-id="45385-239">B3002: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] non genera mai il tag `wsp:Optional`.</span><span class="sxs-lookup"><span data-stu-id="45385-239">B3002: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] never generates the `wsp:Optional` tag.</span></span>  
  
-   <span data-ttu-id="45385-240">B3003: quando si accede all'asserzione di WS-Policy `wsrmp:RMAssertion`, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ignora il tag `wsp:Optional` e considera obbligatorio il criterio WS-RM.</span><span class="sxs-lookup"><span data-stu-id="45385-240">B3003: When accessing the `wsrmp:RMAssertion` WS-Policy Assertion, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ignores the `wsp:Optional` tag and treats the WS-RM policy as mandatory.</span></span>  
  
-   <span data-ttu-id="45385-241">R3004: poiché [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] non esegue la composizione con sessioni SSL/TLS, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] non accetta il criterio che specifica `wsrmp:SequenceTransportSecurity`.</span><span class="sxs-lookup"><span data-stu-id="45385-241">R3004: Because [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] does not compose with SSL/TLS sessions, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] does not accept policy that specifies `wsrmp:SequenceTransportSecurity`.</span></span>  
  
-   <span data-ttu-id="45385-242">B3005: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] genera sempre l'elemento `wsrmp:DeliveryAssurance`.</span><span class="sxs-lookup"><span data-stu-id="45385-242">B3005: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] always generates the `wsrmp:DeliveryAssurance` element.</span></span>  
  
-   <span data-ttu-id="45385-243">B3006: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] specifica sempre la garanzia di recapito `wsrmp:ExactlyOnce`.</span><span class="sxs-lookup"><span data-stu-id="45385-243">B3006: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] always specifies the `wsrmp:ExactlyOnce` delivery assurance.</span></span>  
  
-   <span data-ttu-id="45385-244">B3007: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] genera e legge le proprietà seguenti dell'asserzione WS-ReliableMessaging e fornisce un controllo su di esse in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]`ReliableSessionBindingElement`:</span><span class="sxs-lookup"><span data-stu-id="45385-244">B3007: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generates and reads the following properties of the WS-ReliableMessaging assertion and provides control over them on the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]`ReliableSessionBindingElement`:</span></span>  
  
    -   `netrmp:InactivityTimeout`  
  
    -   `netrmp:AcknowledgementInterval`  
  
     <span data-ttu-id="45385-245">Esempio di `RMAssertion`.</span><span class="sxs-lookup"><span data-stu-id="45385-245">An example of a `RMAssertion`.</span></span>  
  
    ```xml  
    <wsrmp:RMAssertion>  
      <wsp:Policy>  
        <wsrmp:SequenceSTR/>  
        <wsrmp:DeliveryAssurance>  
          <wsp:Policy>  
            <wsrmp:ExactlyOnce/>  
            <wsrmp:InOrder/>  
          </wsp:Policy>  
        </wsrmp:DeliveryAssurance>  
      </wsp:Policy>  
      <netrmp:InactivityTimeout Milliseconds="600000"/>  
      <netrmp:AcknowledgementInterval Milliseconds="200"/>  
    </wsrmp:RMAssertion>  
    ```  
  
## <a name="flow-control-ws-reliablemessaging-extension"></a><span data-ttu-id="45385-246">Estensione di WS-ReliableMessaging per il controllo del flusso</span><span class="sxs-lookup"><span data-stu-id="45385-246">Flow Control WS-ReliableMessaging Extension</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="45385-247"> utilizza l'estendibilità di WS-ReliableMessaging per offrire un controllo facoltativo aggiuntivo più rigido sul flusso di messaggi della sequenza.</span><span class="sxs-lookup"><span data-stu-id="45385-247"> uses WS-ReliableMessaging extensibility to provide optional additional tighter control over sequence message flow.</span></span>  
  
 <span data-ttu-id="45385-248">Controllo di flusso viene abilitato impostando il `ReliableSessionBindingElement`del `FlowControlEnabled``boolean` proprietà `true`.</span><span class="sxs-lookup"><span data-stu-id="45385-248">Flow control is enabled by setting the `ReliableSessionBindingElement`’s `FlowControlEnabled``boolean` property to `true`.</span></span> <span data-ttu-id="45385-249">Di seguito è riportato un elenco di vincoli che si applicano a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="45385-249">The following is a list of constraints that apply to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]:</span></span>  
  
-   <span data-ttu-id="45385-250">B4001: quando il controllo di flusso di Reliable Messaging è attivato, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] genera un elemento `netrm:BufferRemaining` nell'estendibilità dell'elemento dell'intestazione `SequenceAcknowledgement`, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="45385-250">B4001: When Reliable Messaging Flow Control is enabled, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generates a `netrm:BufferRemaining` element in the element extensibility of the `SequenceAcknowledgement` header, as shown in the following example.</span></span>  
  
    ```xml  
    <wsrm:SequenceAcknowledgement>  
      <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
      <wsrm:AcknowledgementRange Upper="1" Lower="1"/>             
      <netrm:BufferRemaining>8</netrm:BufferRemaining>  
    </wsrm:SequenceAcknowledgement>  
    ```  
  
-   <span data-ttu-id="45385-251">B4002: anche quando il controllo di flusso di Reliable Messaging è attivato, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] non richiede un elemento `netrm:BufferRemaining` nell'intestazione `SequenceAcknowledgement`.</span><span class="sxs-lookup"><span data-stu-id="45385-251">B4002: Even when Reliable Messaging Flow Control is enabled, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] does not require a `netrm:BufferRemaining` element in the `SequenceAcknowledgement` header.</span></span>  
  
-   <span data-ttu-id="45385-252">B4003: la destinazione di Reliable Messaging di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] utilizza `netrm:BufferRemaining` per indicare quanti messaggi nuovi è in grado di memorizzare nel buffer.</span><span class="sxs-lookup"><span data-stu-id="45385-252">B4003: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Reliable Messaging Destination uses `netrm:BufferRemaining` to indicate how many new messages it can buffer.</span></span>  
  
-   <span data-ttu-id="45385-253">B4004:when affidabili di messaggistica flusso di controllo è abilitato, il [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] origine di Reliable Messaging utilizza il valore di `netrm:BufferRemaining` per la trasmissione dei messaggi di limitazione.</span><span class="sxs-lookup"><span data-stu-id="45385-253">B4004:When Reliable Messaging Flow Control is enabled, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Reliable Messaging Source uses the value of `netrm:BufferRemaining` to throttle message transmission.</span></span>  
  
-   <span data-ttu-id="45385-254">B4005: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] genera valori integer `netrm:BufferRemaining` tra 0 e 4096 incluso e legge valori integer tra 0 e il valore `xs:int` di `maxInclusive`, 214748364 incluso.</span><span class="sxs-lookup"><span data-stu-id="45385-254">B4005: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generates `netrm:BufferRemaining` integer values between 0 and 4096 inclusive, and reads integer values between 0 and `xs:int`’s `maxInclusive` value 214748364 inclusive.</span></span>  
  
## <a name="message-exchange-patterns"></a><span data-ttu-id="45385-255">Modelli di scambio dei messaggi</span><span class="sxs-lookup"><span data-stu-id="45385-255">Message Exchange Patterns</span></span>  
 <span data-ttu-id="45385-256">Contenuto della sezione viene illustrato il comportamento di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] quando WS-ReliableMessaging è utilizzato per modelli di scambio di messaggi diversi.</span><span class="sxs-lookup"><span data-stu-id="45385-256">This section describes [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]'s behavior when WS-ReliableMessaging is used for different Message Exchange Patterns.</span></span> <span data-ttu-id="45385-257">Per ogni modello di scambio di messaggi, vengono presi in considerazione i due scenari di distribuzione seguenti:</span><span class="sxs-lookup"><span data-stu-id="45385-257">For each Message Exchange Pattern the following two deployments scenarios are considered:</span></span>  
  
-   <span data-ttu-id="45385-258">Iniziatore non indirizzabile: l'iniziatore si trova dietro a un firewall; il risponditore può recapitare messaggi all'iniziatore solo su risposte HTTP.</span><span class="sxs-lookup"><span data-stu-id="45385-258">Non-Addressable Initiator: Initiator is behind a firewall; Responder can deliver messages to the Initiator only on HTTP responses.</span></span>  
  
-   <span data-ttu-id="45385-259">Iniziatore indirizzabile: le richieste HTTP possono essere inviate sia all'iniziatore che al risponditore. In altre parole, è possibile stabilire due connessioni HTTP opposte.</span><span class="sxs-lookup"><span data-stu-id="45385-259">Addressable Initiator: Initiator and Responder both can be sent HTTP requests; in other words, two converse HTTP connections can be established.</span></span>  
  
### <a name="one-way-non-addressable-initiator"></a><span data-ttu-id="45385-260">Iniziatore unidirezionale, non indirizzabile</span><span class="sxs-lookup"><span data-stu-id="45385-260">One-way, Non-addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="45385-261">Binding</span><span class="sxs-lookup"><span data-stu-id="45385-261">Binding</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="45385-262"> fornisce un modello unidirezionale di scambio di messaggi che utilizza una sola sequenza in un solo canale HTTP.</span><span class="sxs-lookup"><span data-stu-id="45385-262"> provides a one-way message exchange pattern using one sequence over one HTTP channel.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="45385-263"> utilizza le richieste HTTP per trasmettere tutti i messaggi dall'iniziatore al risponditore e le risposte HTTP per trasmettere tutti i messaggi dal risponditore all'iniziatore.</span><span class="sxs-lookup"><span data-stu-id="45385-263"> uses HTTP requests to transmit all messages from the Initiator to the Responder and HTTP responses to transmit all messages from the Responder to the Initiator.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="45385-264">Scambio CreateSequence</span><span class="sxs-lookup"><span data-stu-id="45385-264">CreateSequence Exchange</span></span>  
 <span data-ttu-id="45385-265">L'iniziatore [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] trasmette un messaggio `CreateSequence` senza alcun elemento `Offer` su una richiesta HTTP e attende il messaggio `CreateSequenceResponse` sulla risposta HTTP.</span><span class="sxs-lookup"><span data-stu-id="45385-265">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator transmits a `CreateSequence` message with no `Offer` element on an HTTP request and expects the `CreateSequenceResponse` message on the HTTP response.</span></span> <span data-ttu-id="45385-266">Il risponditore [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] crea una sequenza e trasmette il messaggio `CreateSequenceResponse` senza alcun elemento `Accept` sulla risposta HTTP.</span><span class="sxs-lookup"><span data-stu-id="45385-266">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder creates a sequence and transmits the `CreateSequenceResponse` message with no `Accept` element on the HTTP response.</span></span>  
  
#### <a name="sequenceacknowledgement"></a><span data-ttu-id="45385-267">SequenceAcknowledgement</span><span class="sxs-lookup"><span data-stu-id="45385-267">SequenceAcknowledgement</span></span>  
 <span data-ttu-id="45385-268">L'iniziatore [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] elabora gli acknowledgement sulla risposta di tutti i messaggi tranne il messaggio `CreateSequence` e i messaggi di errore.</span><span class="sxs-lookup"><span data-stu-id="45385-268">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator processes acknowledgements on the reply of all messages except the `CreateSequence` message and fault messages.</span></span> <span data-ttu-id="45385-269">Il risponditore [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] trasmette sempre un acknowledgement autonomo sulla risposta HTTP a tutte le sequenze e ai messaggi `AckRequested`.</span><span class="sxs-lookup"><span data-stu-id="45385-269">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder always transmits a stand-alone acknowledgement on the HTTP response to all sequence and `AckRequested` messages.</span></span>  
  
#### <a name="closesequence-exchange"></a><span data-ttu-id="45385-270">Scambio CloseSequence</span><span class="sxs-lookup"><span data-stu-id="45385-270">CloseSequence Exchange</span></span>  
 <span data-ttu-id="45385-271">L'iniziatore [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] trasmette un messaggio `CloseSequence` su una richiesta HTTP e attende il messaggio `CreateSequenceResponse` sulla risposta HTTP.</span><span class="sxs-lookup"><span data-stu-id="45385-271">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator transmits a `CloseSequence` message on an HTTP request and expects the `CreateSequenceResponse` message on the HTTP response.</span></span> <span data-ttu-id="45385-272">Il risponditore [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] trasmette il messaggio `CloseSequenceResponse` sulla risposta HTTP.</span><span class="sxs-lookup"><span data-stu-id="45385-272">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder transmits the `CloseSequenceResponse` message on the HTTP response.</span></span>  
  
#### <a name="terminatesequence-exchange"></a><span data-ttu-id="45385-273">Scambio TerminateSequence</span><span class="sxs-lookup"><span data-stu-id="45385-273">TerminateSequence Exchange</span></span>  
 <span data-ttu-id="45385-274">L'iniziatore [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] trasmette un messaggio `TerminateSequence` su una richiesta HTTP e attende il messaggio `TerminateSequenceResponse` sulla risposta HTTP.</span><span class="sxs-lookup"><span data-stu-id="45385-274">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator transmits a `TerminateSequence` message on an HTTP request and expects the `TerminateSequenceResponse` message on the HTTP response.</span></span> <span data-ttu-id="45385-275">Il risponditore [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] trasmette il messaggio `TerminateSequenceResponse` sulla risposta HTTP.</span><span class="sxs-lookup"><span data-stu-id="45385-275">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder transmits the `TerminateSequenceResponse` message on the HTTP response.</span></span>  
  
### <a name="one-way-addressable-initiator"></a><span data-ttu-id="45385-276">Iniziatore unidirezionale, indirizzabile</span><span class="sxs-lookup"><span data-stu-id="45385-276">One Way, Addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="45385-277">Binding</span><span class="sxs-lookup"><span data-stu-id="45385-277">Binding</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="45385-278"> fornisce un modello unidirezionale di scambio di messaggi che utilizza una sola sequenza su un canale HTTP in ingresso e uno in uscita.</span><span class="sxs-lookup"><span data-stu-id="45385-278"> provides a one-way message exchange pattern using one sequence over one inbound and one outbound HTTP channel.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="45385-279"> utilizza le richieste HTTP per trasmettere tutti i messaggi.</span><span class="sxs-lookup"><span data-stu-id="45385-279"> uses the HTTP requests to transmit all messages.</span></span> <span data-ttu-id="45385-280">Tutte le risposte HTTP hanno un corpo vuoto e un codice di stato HTTP 202.</span><span class="sxs-lookup"><span data-stu-id="45385-280">All HTTP responses have an empty body and HTTP 202 status code.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="45385-281">Scambio CreateSequence</span><span class="sxs-lookup"><span data-stu-id="45385-281">CreateSequence Exchange</span></span>  
 <span data-ttu-id="45385-282">L'iniziatore [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] trasmette un messaggio `CreateSequence` senza alcun elemento `Offer` su una richiesta HTTP.</span><span class="sxs-lookup"><span data-stu-id="45385-282">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator transmits a `CreateSequence` message with no `Offer` element on an HTTP request.</span></span> <span data-ttu-id="45385-283">Il risponditore [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] crea una sequenza e trasmette il messaggio `CreateSequenceResponse` senza alcun elemento `Accept` su una richiesta HTTP.</span><span class="sxs-lookup"><span data-stu-id="45385-283">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder creates a sequence and transmits the `CreateSequenceResponse` message with no `Accept` element on an HTTP request.</span></span>  
  
### <a name="duplex-addressable-initiator"></a><span data-ttu-id="45385-284">Iniziatore duplex, indirizzabile</span><span class="sxs-lookup"><span data-stu-id="45385-284">Duplex, Addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="45385-285">Binding</span><span class="sxs-lookup"><span data-stu-id="45385-285">Binding</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="45385-286"> fornisce un modello di scambio di messaggi bidirezionale completamente asincrono utilizzando due sequenze su un canale HTTP in ingresso e su uno in uscita.</span><span class="sxs-lookup"><span data-stu-id="45385-286"> provides a fully-asynchronous, two-way message exchange pattern using two sequences over one inbound and one outbound HTTP channel.</span></span> <span data-ttu-id="45385-287">Questo modello di scambio può essere combinato con il modello di scambio di messaggi dell'iniziatore `Request/Reply`, `Addressable` in modo limitato.</span><span class="sxs-lookup"><span data-stu-id="45385-287">This message exchange pattern can be mixed with the `Request/Reply`, `Addressable` Initiator message exchange pattern in a limited way.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="45385-288"> utilizza le richieste HTTP per trasmettere tutti i messaggi.</span><span class="sxs-lookup"><span data-stu-id="45385-288"> uses HTTP requests to transmit all messages.</span></span> <span data-ttu-id="45385-289">Tutte le risposte HTTP hanno un corpo vuoto e un codice di stato HTTP 202.</span><span class="sxs-lookup"><span data-stu-id="45385-289">All HTTP responses have an empty body and HTTP 202 status code.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="45385-290">Scambio CreateSequence</span><span class="sxs-lookup"><span data-stu-id="45385-290">CreateSequence Exchange</span></span>  
 <span data-ttu-id="45385-291">L'iniziatore [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] trasmette un messaggio `CreateSequence` con un elemento `Offer` su una richiesta HTTP.</span><span class="sxs-lookup"><span data-stu-id="45385-291">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator transmits a `CreateSequence` message with an `Offer` element on an HTTP request.</span></span> <span data-ttu-id="45385-292">Il risponditore [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] controlla che `CreateSequence` abbia un elemento `Offer`, quindi crea una sequenza e trasmette il messaggio `CreateSequenceResponse` con un elemento `Accept`.</span><span class="sxs-lookup"><span data-stu-id="45385-292">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder ensures that the `CreateSequence` has an `Offer` element, then creates a sequence and transmits the `CreateSequenceResponse` message with an `Accept` element.</span></span>  
  
#### <a name="sequence-lifetime"></a><span data-ttu-id="45385-293">Durata della sequenza</span><span class="sxs-lookup"><span data-stu-id="45385-293">Sequence Lifetime</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="45385-294"> tratta le due sequenze come una sessione completamente duplex.</span><span class="sxs-lookup"><span data-stu-id="45385-294"> treats the two sequences as one fully-duplex session.</span></span>  
  
 <span data-ttu-id="45385-295">Dopo la generazione di un errore che origina errori in una sequenza, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] si aspetta che l'endpoint crei errori in entrambe le sequenze.</span><span class="sxs-lookup"><span data-stu-id="45385-295">Upon generating a fault that faults one sequence, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] expects the remote endpoint to fault both sequences.</span></span> <span data-ttu-id="45385-296">Dopo la lettura di un errore che origina errori in una sequenza, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] crea errori in entrambe le sequenze.</span><span class="sxs-lookup"><span data-stu-id="45385-296">Upon reading a fault that faults one sequence, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] faults both sequences.</span></span>  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="45385-297"> può chiudere la sequenza in uscita e continuare a elaborare i messaggi sulla sua sequenza in ingresso.</span><span class="sxs-lookup"><span data-stu-id="45385-297"> can close its outbound sequence and continue to process messages on its inbound sequence.</span></span> <span data-ttu-id="45385-298">Per contro, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] può elaborare la chiusura della sequenza in ingresso e continuare a inviare i messaggi sulla sua sequenza in uscita.</span><span class="sxs-lookup"><span data-stu-id="45385-298">Conversely, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] can process the close of the inbound sequence and continue to send messages on its outbound sequence.</span></span>  
  
### <a name="request-reply-and-one-way-non-addressable-initiator"></a><span data-ttu-id="45385-299">Iniziatore request/reply e unidirezionale, non indirizzabile</span><span class="sxs-lookup"><span data-stu-id="45385-299">Request-Reply and One-Way, Non-Addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="45385-300">Binding</span><span class="sxs-lookup"><span data-stu-id="45385-300">Binding</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="45385-301"> fornisce un modello di scambio di messaggi request/reply e unidirezionale che utilizza due sequenze su un canale HTTP.</span><span class="sxs-lookup"><span data-stu-id="45385-301"> provides a one-way and request-reply message exchange pattern using two sequences over one HTTP channel.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="45385-302"> utilizza le richieste HTTP per trasmettere tutti i messaggi dall'iniziatore al risponditore e le risposte HTTP per trasmettere tutti i messaggi dal risponditore all'iniziatore.</span><span class="sxs-lookup"><span data-stu-id="45385-302"> uses HTTP requests to transmit all messages from the Initiator to the Responder and HTTP responses to transmit all messages from the Responder to the Initiator.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="45385-303">Scambio CreateSequence</span><span class="sxs-lookup"><span data-stu-id="45385-303">CreateSequence Exchange</span></span>  
 <span data-ttu-id="45385-304">L'iniziatore [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] trasmette un messaggio `CreateSequence` con un elemento `Offer` su una richiesta HTTP e attende il messaggio `CreateSequenceResponse` sulla risposta HTTP.</span><span class="sxs-lookup"><span data-stu-id="45385-304">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator transmits a `CreateSequence` message with an `Offer` element on an HTTP request and expects the `CreateSequenceResponse` message on the HTTP response.</span></span> <span data-ttu-id="45385-305">Il risponditore [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] crea una sequenza e trasmette il messaggio `CreateSequenceResponse` con un elemento `Accept` sulla risposta HTTP.</span><span class="sxs-lookup"><span data-stu-id="45385-305">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder creates a sequence and transmits the `CreateSequenceResponse` message with an `Accept` element on the HTTP response.</span></span>  
  
#### <a name="one-way-message"></a><span data-ttu-id="45385-306">Messaggio unidirezionale</span><span class="sxs-lookup"><span data-stu-id="45385-306">One-way Message</span></span>  
 <span data-ttu-id="45385-307">Per completare correttamente uno scambio di messaggi unidirezionale, l'iniziatore [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] trasmette un messaggio della sequenza di richiesta sulla richiesta HTTP e riceve un messaggio `SequenceAcknowledgement` autonomo sulla risposta HTTP.</span><span class="sxs-lookup"><span data-stu-id="45385-307">To complete a one-way message exchange successfully, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator transmits a request sequence message on the HTTP request and receives a standalone `SequenceAcknowledgement` message on the HTTP response.</span></span> <span data-ttu-id="45385-308">`SequenceAcknowledgement` deve riconoscere il messaggio trasmesso.</span><span class="sxs-lookup"><span data-stu-id="45385-308">The `SequenceAcknowledgement` must acknowledge the message transmitted.</span></span>  
  
 <span data-ttu-id="45385-309">Il risponditore [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] può rispondere alla richiesta con un acknowledgement, un errore o una risposta con un corpo vuoto e un codice di stato HTTP 202.</span><span class="sxs-lookup"><span data-stu-id="45385-309">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder may reply to the request with an acknowledgement, a fault, or a response with an empty body and HTTP 202 status code.</span></span>  
  
#### <a name="two-way-messages"></a><span data-ttu-id="45385-310">Messaggi bidirezionali</span><span class="sxs-lookup"><span data-stu-id="45385-310">Two Way Messages</span></span>  
 <span data-ttu-id="45385-311">Per completare correttamente un protocollo di scambio di messaggi bidirezionale, l'iniziatore [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] trasmette un messaggio della sequenza di richiesta sulla richiesta HTTP e riceve un messaggio della sequenza di risposta sulla risposta HTTP.</span><span class="sxs-lookup"><span data-stu-id="45385-311">To complete a two way message exchange protocol successfully, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator transmits a request sequence message on the HTTP request and receives a reply sequence message on the HTTP response.</span></span> <span data-ttu-id="45385-312">La risposta deve contenere un `SequenceAcknowledgement` che riconosce che il messaggio della sequenza di richiesta è stato trasmesso.</span><span class="sxs-lookup"><span data-stu-id="45385-312">The response must carry a `SequenceAcknowledgement` acknowledging the request sequence message transmitted.</span></span>  
  
 <span data-ttu-id="45385-313">Il risponditore [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] può rispondere alla richiesta con una risposta dell'applicazione, un errore o una risposta con un corpo vuoto e un codice di stato HTTP 202.</span><span class="sxs-lookup"><span data-stu-id="45385-313">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder may reply to the request with an application reply, a fault or a response with an empty body and HTTP 202 status code.</span></span>  
  
 <span data-ttu-id="45385-314">A causa della presenza di messaggi unidirezionali e del tempo delle risposte dell'applicazione, il numero di sequenza del messaggio della sequenza di richiesta e il numero di sequenza del messaggio di risposta non hanno alcuna correlazione.</span><span class="sxs-lookup"><span data-stu-id="45385-314">Because of the presence of one-way messages and the timing of application replies, the request sequence message’s sequence number and the response message’s sequence number have no correlation.</span></span>  
  
#### <a name="retrying-replies"></a><span data-ttu-id="45385-315">Nuovi tentativi di risposte</span><span class="sxs-lookup"><span data-stu-id="45385-315">Retrying Replies</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="45385-316"> si basa sulla correlazione request/reply HTTP per la correlazione del protocollo di scambio di messaggi bidirezionali.</span><span class="sxs-lookup"><span data-stu-id="45385-316"> relies on HTTP request-reply correlation for two-way message exchange protocol correlation.</span></span> <span data-ttu-id="45385-317">Di conseguenza, l'iniziatore [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] non smette di tentare un messaggio della sequenza di richiesta quando tale messaggio viene riconosciuto, ma piuttosto quando la risposta HTTP contiene un `SequenceAcknowledgement`, una risposta dell'applicazione o un errore.</span><span class="sxs-lookup"><span data-stu-id="45385-317">Because of this, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator does not stop retrying a request sequence message when the request sequence message is acknowledged but rather when the HTTP response carries a `SequenceAcknowledgement`, application reply, or fault.</span></span> <span data-ttu-id="45385-318">Il risponditore [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ritenta le risposte sulla risposta HTTP della richiesta alla quale è correlata la risposta.</span><span class="sxs-lookup"><span data-stu-id="45385-318">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder retries replies on the HTTP response of the request to which the reply is correlated.</span></span>  
  
#### <a name="closesequence-exchange"></a><span data-ttu-id="45385-319">Scambio CloseSequence</span><span class="sxs-lookup"><span data-stu-id="45385-319">CloseSequence Exchange</span></span>  
 <span data-ttu-id="45385-320">Dopo avere ricevuto tutti i messaggi della sequenza di risposta e gli acknowledgement per tutti i messaggi della sequenza di richiesta unidirezionali, l'iniziatore [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] trasmette un messaggio `CloseSequence` per la sequenza di richiesta su una richiesta HTTP e attende la `CloseSequenceResponse` sulla risposta HTTP.</span><span class="sxs-lookup"><span data-stu-id="45385-320">After receiving all reply sequence messages and acknowledgements for all one way request sequence messages, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator transmits a `CloseSequence` message for the request sequence on an HTTP request and expects the `CloseSequenceResponse` on the HTTP response.</span></span>  
  
 <span data-ttu-id="45385-321">Se la sequenza di richiesta viene chiusa in modo implicito, viene chiusa anche la sequenza di risposta.</span><span class="sxs-lookup"><span data-stu-id="45385-321">Closing the request sequence implicitly closes the reply sequence.</span></span> <span data-ttu-id="45385-322">Ciò significa che l'iniziatore [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] include il `SequenceAcknowledgement` finale della sequenza di risposta sul messaggio `CloseSequence` e che la sequenza di risposta non ha uno scambio `CloseSequence`.</span><span class="sxs-lookup"><span data-stu-id="45385-322">This means the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator includes the reply sequence’s Final `SequenceAcknowledgement` on the `CloseSequence` message and the reply sequence does not have a `CloseSequence` exchange.</span></span>  
  
 <span data-ttu-id="45385-323">Il risponditore [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] assicura che tutte le risposte vengano riconosciute e trasmette il messaggio `CloseSequenceResponse` sulla risposta HTTP.</span><span class="sxs-lookup"><span data-stu-id="45385-323">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder ensures all replies are acknowledged and transmits the `CloseSequenceResponse` message on the HTTP response.</span></span>  
  
#### <a name="terminatesequence-exchange"></a><span data-ttu-id="45385-324">Scambio TerminateSequence</span><span class="sxs-lookup"><span data-stu-id="45385-324">TerminateSequence Exchange</span></span>  
 <span data-ttu-id="45385-325">Dopo la ricezione del messaggio `CloseSequenceResponse`, l'iniziatore [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] trasmette un messaggio `TerminateSequence` per la sequenza di richiesta su una richiesta HTTP e attende la `TerminateSequenceResponse` sulla risposta HTTP.</span><span class="sxs-lookup"><span data-stu-id="45385-325">After receiving the `CloseSequenceResponse` message, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator transmits a `TerminateSequence` message for the request sequence on an HTTP request and expects the `TerminateSequenceResponse` on the HTTP response.</span></span>  
  
 <span data-ttu-id="45385-326">Analogamente allo scambio `CloseSequence`, la terminazione della sequenza di richiesta in modo implicito termina la sequenza di risposta.</span><span class="sxs-lookup"><span data-stu-id="45385-326">Like the `CloseSequence` exchange, terminating the request sequence implicitly terminates the reply sequence.</span></span> <span data-ttu-id="45385-327">Ciò significa che l'iniziatore [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] include il `SequenceAcknowledgement` finale della sequenza di risposta sul messaggio `TerminateSequence` e che la sequenza di risposta non ha uno scambio `TerminateSequence`.</span><span class="sxs-lookup"><span data-stu-id="45385-327">This means the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator includes the reply sequence’s final `SequenceAcknowledgement` on the `TerminateSequence` message and the reply sequence does not have a `TerminateSequence` exchange.</span></span>  
  
 <span data-ttu-id="45385-328">Il risponditore [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] trasmette il messaggio `TerminateSequenceResponse` sulla risposta HTTP.</span><span class="sxs-lookup"><span data-stu-id="45385-328">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder transmits the `TerminateSequenceResponse` message on the HTTP response.</span></span>  
  
### <a name="requestreply-addressable-initiator"></a><span data-ttu-id="45385-329">Iniziatore request/reply, indirizzabile</span><span class="sxs-lookup"><span data-stu-id="45385-329">Request/Reply, Addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="45385-330">Binding</span><span class="sxs-lookup"><span data-stu-id="45385-330">Binding</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="45385-331"> fornisce un modello di scambio di messaggi request/reply utilizzando due sequenze su un canale HTTP in ingresso e su uno in uscita.</span><span class="sxs-lookup"><span data-stu-id="45385-331"> provides a request-reply message exchange pattern using two sequences over one inbound and one outbound HTTP channel.</span></span> <span data-ttu-id="45385-332">Questo modello di scambio può essere combinato con il modello di scambio di messaggi dell'iniziatore `Duplex, Addressable` in modo limitato.</span><span class="sxs-lookup"><span data-stu-id="45385-332">This message exchange pattern can be mixed with the `Duplex, Addressable` Initiator message exchange pattern in a limited way.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="45385-333"> utilizza le richieste HTTP per trasmettere tutti i messaggi.</span><span class="sxs-lookup"><span data-stu-id="45385-333"> uses the HTTP requests to transmit all messages.</span></span> <span data-ttu-id="45385-334">Tutte le risposte HTTP hanno un corpo vuoto e un codice di stato HTTP 202.</span><span class="sxs-lookup"><span data-stu-id="45385-334">All HTTP responses have an empty body and HTTP 202 status code.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="45385-335">Scambio CreateSequence</span><span class="sxs-lookup"><span data-stu-id="45385-335">CreateSequence Exchange</span></span>  
 <span data-ttu-id="45385-336">L'iniziatore [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] trasmette un messaggio `CreateSequence` con un elemento `Offer` su una richiesta HTTP.</span><span class="sxs-lookup"><span data-stu-id="45385-336">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator transmits a `CreateSequence` message with an `Offer` element on an HTTP request.</span></span> <span data-ttu-id="45385-337">Il risponditore [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] controlla che `CreateSequence` abbia un elemento `Offer`, quindi crea una sequenza e trasmette il messaggio `CreateSequenceResponse` con un elemento `Accept`.</span><span class="sxs-lookup"><span data-stu-id="45385-337">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder ensures that the `CreateSequence` has an `Offer` element then creates a sequence and transmits the `CreateSequenceResponse` message with an `Accept` element.</span></span>  
  
#### <a name="requestreply-correlation"></a><span data-ttu-id="45385-338">Correlazione request/reply</span><span class="sxs-lookup"><span data-stu-id="45385-338">Request/Reply Correlation</span></span>  
 <span data-ttu-id="45385-339">Quanto riportato di seguito si applica a tutte le richieste e le risposte correlate:</span><span class="sxs-lookup"><span data-stu-id="45385-339">The following applies to all correlated requests and replies:</span></span>  
  
-   [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="45385-340"> controlla che tutti i messaggi di richiesta dell'applicazione contengano un riferimento all'endpoint `ReplyTo` e un `MessageId`.</span><span class="sxs-lookup"><span data-stu-id="45385-340"> ensures all application request messages bear a `ReplyTo` endpoint reference and a `MessageId`.</span></span>  
  
-   [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="45385-341"> applica il riferimento dell'endpoint locale come `ReplyTo` di ogni messaggio di richiesta dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="45385-341"> applies the local endpoint reference as each application request message’s `ReplyTo`.</span></span> <span data-ttu-id="45385-342">Il riferimento dell'endpoint locale è `CreateSequence` del messaggio `ReplyTo` per l'iniziatore e `CreateSequence` del messaggio `To` per il risponditore.</span><span class="sxs-lookup"><span data-stu-id="45385-342">The local endpoint reference is the `CreateSequence` message’s `ReplyTo` for the Initiator and the `CreateSequence` message’s `To` for the Responder.</span></span>  
  
-   [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="45385-343"> controlla che i messaggi di richiesta in entrata contengano un `MessageId` e un `ReplyTo`.</span><span class="sxs-lookup"><span data-stu-id="45385-343"> ensures that incoming request messages bear a `MessageId` and a `ReplyTo`.</span></span>  
  
-   [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="45385-344"> controlla che l'URI di riferimento dell'endpoint `ReplyTo` di tutti i messaggi di richiesta dell'applicazione corrisponda al riferimento dell'endpoint locale come definito in precedenza.</span><span class="sxs-lookup"><span data-stu-id="45385-344"> ensures the `ReplyTo` endpoint reference’s URI of all application request messages match the local endpoint reference as defined earlier.</span></span>  
  
-   [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="45385-345"> controlla che tutte le risposte contengano le intestazioni `RelatesTo` e `To`, in conformità con le regole di correlazione request/reply di  `wsa`.</span><span class="sxs-lookup"><span data-stu-id="45385-345"> ensures that all replies bear the correct `RelatesTo` and `To` headers following `wsa` request/reply correlation rules.</span></span>
