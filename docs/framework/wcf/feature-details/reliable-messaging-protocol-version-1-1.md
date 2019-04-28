---
title: Protocollo Reliable Messaging versione 1,1
ms.date: 03/30/2017
ms.assetid: 0da47b82-f8eb-42da-8bfe-e56ce7ba6f59
ms.openlocfilehash: 6b8732e0b48797c219b53bb8bf70e1ba57e25c42
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61933991"
---
# <a name="reliable-messaging-protocol-version-11"></a><span data-ttu-id="a38a8-102">Protocollo Reliable Messaging versione 1,1</span><span class="sxs-lookup"><span data-stu-id="a38a8-102">Reliable Messaging Protocol version 1.1</span></span>
<span data-ttu-id="a38a8-103">In questo argomento vengono descritti i dettagli di implementazione Windows Communication Foundation (WCF) per il WS-ReliableMessaging protocollo febbraio 2007 (versione 1.1) necessario per l'interoperatività con il trasporto HTTP.</span><span class="sxs-lookup"><span data-stu-id="a38a8-103">This topic covers Windows Communication Foundation (WCF) implementation details for the WS-ReliableMessaging February 2007 (version 1.1) protocol necessary for interoperation using the HTTP transport.</span></span> <span data-ttu-id="a38a8-104">WCF conforme alla specifica WS-ReliableMessaging con i vincoli e i chiarimenti illustrati in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="a38a8-104">WCF follows the WS-ReliableMessaging specification with the constraints and clarifications explained in this topic.</span></span> <span data-ttu-id="a38a8-105">Si noti che il protocollo versione 1.1 WS-ReliableMessaging viene implementato a partire dal [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a38a8-105">Note that the WS-ReliableMessaging version 1.1 protocol is implemented starting with the [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)].</span></span>  
  
 <span data-ttu-id="a38a8-106">Il WS-ReliableMessaging febbraio 2007 protocollo viene implementato in WCF per il <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="a38a8-106">The WS-ReliableMessaging February 2007 protocol is implemented in WCF by the <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>.</span></span>  
  
 <span data-ttu-id="a38a8-107">Per comodità, nell'argomento vengono utilizzati i ruoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="a38a8-107">For convenience, the topic uses the following roles:</span></span>  
  
-   <span data-ttu-id="a38a8-108">Iniziatore: Il client che avvia la creazione della sequenza di WS-Reliable Message.</span><span class="sxs-lookup"><span data-stu-id="a38a8-108">Initiator: The client that initiates WS-Reliable Message sequence creation.</span></span>  
  
-   <span data-ttu-id="a38a8-109">Risponditore: Il servizio che riceve le richieste dell'iniziatore.</span><span class="sxs-lookup"><span data-stu-id="a38a8-109">Responder: The service that receives the initiator's requests.</span></span>  
  
 <span data-ttu-id="a38a8-110">In questo documento vengono utilizzati i prefissi e gli spazi dei nomi riportati nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="a38a8-110">This document uses the prefixes and namespaces in the following table.</span></span>  
  
|<span data-ttu-id="a38a8-111">Prefisso</span><span class="sxs-lookup"><span data-stu-id="a38a8-111">Prefix</span></span>|<span data-ttu-id="a38a8-112">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="a38a8-112">Namespace</span></span>|  
|-|-|  
|<span data-ttu-id="a38a8-113">wsrm</span><span class="sxs-lookup"><span data-stu-id="a38a8-113">wsrm</span></span>|http://docs.oasis-open.org/ws-rx/wsrm/200702|  
|<span data-ttu-id="a38a8-114">netrm</span><span class="sxs-lookup"><span data-stu-id="a38a8-114">netrm</span></span>|http://schemas.microsoft.com/ws/2006/05/rm|  
|<span data-ttu-id="a38a8-115">s</span><span class="sxs-lookup"><span data-stu-id="a38a8-115">s</span></span>|http://www.w3.org/2003/05/soap-envelope|  
|<span data-ttu-id="a38a8-116">wsa</span><span class="sxs-lookup"><span data-stu-id="a38a8-116">wsa</span></span>|http://schemas.xmlsoap.org/ws/2005/08/addressing|  
|<span data-ttu-id="a38a8-117">wsse</span><span class="sxs-lookup"><span data-stu-id="a38a8-117">wsse</span></span>|http://docs.oasis-open.org/wss/2004/01/oasis-200401-wssecurity-secext-1.0.xsd|  
|<span data-ttu-id="a38a8-118">wsrmp</span><span class="sxs-lookup"><span data-stu-id="a38a8-118">wsrmp</span></span>|http://docs.oasis-open.org/ws-rx/wsrmp/200702|  
|<span data-ttu-id="a38a8-119">netrmp</span><span class="sxs-lookup"><span data-stu-id="a38a8-119">netrmp</span></span>|http://schemas.microsoft.com/ws-rx/wsrmp/200702|  
|<span data-ttu-id="a38a8-120">wsp</span><span class="sxs-lookup"><span data-stu-id="a38a8-120">wsp</span></span>|<span data-ttu-id="a38a8-121">(WS-Policy 1.2 o WS-Policy 1.5)</span><span class="sxs-lookup"><span data-stu-id="a38a8-121">(Either WS-Policy 1.2 or WS-Policy 1.5)</span></span>|  
  
## <a name="messaging"></a><span data-ttu-id="a38a8-122">Messaggistica</span><span class="sxs-lookup"><span data-stu-id="a38a8-122">Messaging</span></span>  
  
### <a name="sequence-creation"></a><span data-ttu-id="a38a8-123">Creazione sequenza</span><span class="sxs-lookup"><span data-stu-id="a38a8-123">Sequence Creation</span></span>  
 <span data-ttu-id="a38a8-124">WCF implementa `CreateSequence` e `CreateSequenceResponse` di sequenza dei messaggi per stabilire una messaggistica affidabile.</span><span class="sxs-lookup"><span data-stu-id="a38a8-124">WCF implements `CreateSequence` and `CreateSequenceResponse` messages to establish a reliable messaging sequence.</span></span> <span data-ttu-id="a38a8-125">Si applicano i vincoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="a38a8-125">The following constraints apply:</span></span>  
  
-   <span data-ttu-id="a38a8-126">B1101: L'iniziatore WCF Usa lo stesso riferimento dell'endpoint come le `CreateSequence` del messaggio `ReplyTo`, `AcksTo` e `Offer/Endpoint`.</span><span class="sxs-lookup"><span data-stu-id="a38a8-126">B1101: The WCF Initiator uses the same endpoint reference as the `CreateSequence` message’s `ReplyTo`, `AcksTo` and `Offer/Endpoint`.</span></span>  
  
-   <span data-ttu-id="a38a8-127">R1102: Il `AcksTo`, `ReplyTo` e `Offer/Endpoint` riferimenti degli endpoint nel `CreateSequence` messaggio deve presentare valori indirizzo con rappresentazioni di stringa identiche in modo che corrispondano all'ottetto.</span><span class="sxs-lookup"><span data-stu-id="a38a8-127">R1102: The `AcksTo`, `ReplyTo` and `Offer/Endpoint` endpoint references in the `CreateSequence` message must have address values with identical string representations such that they match the octet-wise.</span></span>  
  
    -   <span data-ttu-id="a38a8-128">Il risponditore WCF verifica che la parte URI del `AcksTo`, `ReplyTo` e `Endpoint` riferimenti a endpoint sono identici prima di creare una sequenza.</span><span class="sxs-lookup"><span data-stu-id="a38a8-128">The WCF Responder verifies that the URI portion of the `AcksTo`, `ReplyTo` and `Endpoint` endpoint references are identical before creating a sequence.</span></span>  
  
-   <span data-ttu-id="a38a8-129">R1103: Il `AcksTo`, `ReplyTo` e `Offer/Endpoint` riferimenti degli endpoint nel `CreateSequence` messaggio deve avere lo stesso set di parametri per riferimento.</span><span class="sxs-lookup"><span data-stu-id="a38a8-129">R1103: The `AcksTo`, `ReplyTo` and `Offer/Endpoint` endpoint references in the `CreateSequence` message should have the same set of reference parameters.</span></span>  
  
    -   <span data-ttu-id="a38a8-130">WCF non impone, ma presuppone che fanno riferimento a parametri del `AcksTo`, `ReplyTo` e `Offer/Endpoint` fa riferimento a endpoint in `CreateSequence` siano identici e utilizza i parametri di riferimento dal `ReplyTo` riferimento dell'endpoint per acknowledgement e messaggi in sequenza opposta.</span><span class="sxs-lookup"><span data-stu-id="a38a8-130">WCF does not enforce, but assumes that reference parameters of the `AcksTo`, `ReplyTo` and `Offer/Endpoint` endpoint references on `CreateSequence` are identical and uses reference parameters from the `ReplyTo` endpoint reference for acknowledgements and converse sequence messages.</span></span>  
  
-   <span data-ttu-id="a38a8-131">B1104: L'iniziatore di WCF non genera facoltativo `Expires` o `Offer/Expires` elemento il `CreateSequence` messaggio.</span><span class="sxs-lookup"><span data-stu-id="a38a8-131">B1104: The WCF Initiator does not generate the optional `Expires` or `Offer/Expires` element in the `CreateSequence` message.</span></span>  
  
-   <span data-ttu-id="a38a8-132">B1105: Quando si accede al `CreateSequence` messaggio, quest'ultimo WCF utilizza il `Expires` valore nel `CreateSequence` elemento come il `Expires` valore nel `CreateSequenceResponse` elemento.</span><span class="sxs-lookup"><span data-stu-id="a38a8-132">B1105: When accessing the `CreateSequence` message, the WCF Responder uses the `Expires` value in the `CreateSequence` element as the `Expires` value in the `CreateSequenceResponse` element.</span></span> <span data-ttu-id="a38a8-133">In caso contrario, il risponditore WCF legge e ignora le `Expires` e `Offer/Expires` valori.</span><span class="sxs-lookup"><span data-stu-id="a38a8-133">Otherwise, the WCF Responder reads and ignores the `Expires` and `Offer/Expires` values.</span></span>  
  
-   <span data-ttu-id="a38a8-134">B1106: Quando si accede al `CreateSequenceResponse` messaggio, l'iniziatore WCF legge facoltativo `Expires` valore ma non lo utilizza.</span><span class="sxs-lookup"><span data-stu-id="a38a8-134">B1106: When accessing the `CreateSequenceResponse` message, the WCF Initiator reads the optional `Expires` value but does not use it.</span></span>  
  
-   <span data-ttu-id="a38a8-135">B1107: L'iniziatore di WCF e il risponditore generano sempre l'opzione facoltativa `IncompleteSequenceBehavior` elemento il `CreateSequence/Offer` e `CreateSequenceResponse` elementi.</span><span class="sxs-lookup"><span data-stu-id="a38a8-135">B1107: The WCF Initiator and Responder always generate the optional `IncompleteSequenceBehavior` element in the `CreateSequence/Offer` and `CreateSequenceResponse` elements.</span></span>  
  
-   <span data-ttu-id="a38a8-136">B1108: WCF Usa solo il `DiscardFollowingFirstGap` e `NoDiscard` i valori di `IncompleteSequenceBehavior` elemento.</span><span class="sxs-lookup"><span data-stu-id="a38a8-136">B1108: WCF uses only the `DiscardFollowingFirstGap` and `NoDiscard` values in the `IncompleteSequenceBehavior` element.</span></span>  
  
    -   <span data-ttu-id="a38a8-137">WS-ReliableMessaging utilizza il meccanismo `Offer` per stabilire le due sequenze correlate opposte che formano una sessione.</span><span class="sxs-lookup"><span data-stu-id="a38a8-137">WS-ReliableMessaging utilizes the `Offer` mechanism to establish the two converse correlated sequences that form a session.</span></span>  
  
-   <span data-ttu-id="a38a8-138">B1109: Se `CreateSequence` contiene un `Offer` elemento, il risponditore WCF unidirezionale respinge la sequenza offerta rispondendo con un `CreateSequenceResponse` senza un' `Accept` elemento.</span><span class="sxs-lookup"><span data-stu-id="a38a8-138">B1109: If `CreateSequence` contains an `Offer` element, the one way WCF Responder rejects the offered sequence by responding with a `CreateSequenceResponse` without an `Accept` element.</span></span>  
  
-   <span data-ttu-id="a38a8-139">B1110: Se un risponditore Reliable Messaging respinge la sequenza offerta, l'iniziatore WCF gli errori nella sequenza appena stabilita.</span><span class="sxs-lookup"><span data-stu-id="a38a8-139">B1110: If a Reliable Messaging Responder rejects the offered sequence, the WCF Initiator faults the newly established sequence.</span></span>  
  
-   <span data-ttu-id="a38a8-140">B1111: Se `CreateSequence` non contiene un `Offer` elemento, il risponditore bidirezionale di WCF respinge la sequenza offerta rispondendo con un `CreateSequenceRefused` fault.</span><span class="sxs-lookup"><span data-stu-id="a38a8-140">B1111: If `CreateSequence` does not contain an `Offer` element, the two-way WCF Responder rejects the offered sequence by responding with a `CreateSequenceRefused` fault.</span></span>  
  
-   <span data-ttu-id="a38a8-141">R1112: Quando vengono stabilite due sequenze opposte utilizzando il `Offer` meccanismo, il `[address]` proprietà delle `CreateSequenceResponse/Accept/AcksTo` riferimento dell'endpoint deve corrispondere all'URI di destinazione del `CreateSequence` byte di messaggi per byte.</span><span class="sxs-lookup"><span data-stu-id="a38a8-141">R1112: When two converse sequences are established using the `Offer` mechanism, the `[address]` property of the `CreateSequenceResponse/Accept/AcksTo` endpoint reference must match the destination URI of the `CreateSequence` message byte for byte.</span></span>  
  
-   <span data-ttu-id="a38a8-142">R1113: Quando vengono stabilite due sequenze opposte utilizzando il `Offer` meccanismo, tutti i messaggi su entrambe le sequenze dall'iniziatore al risponditore devono essere inviati allo stesso riferimento dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="a38a8-142">R1113: When two converse sequences are established using the `Offer` mechanism, all messages on both sequences flowing from the Initiator to the Responder must be sent to the same endpoint reference.</span></span>  
  
 <span data-ttu-id="a38a8-143">WCF Usa WS-ReliableMessaging per stabilire sessioni affidabili tra l'iniziatore e risponditore.</span><span class="sxs-lookup"><span data-stu-id="a38a8-143">WCF uses WS-ReliableMessaging to establish reliable sessions between the Initiator and the Responder.</span></span> <span data-ttu-id="a38a8-144">L'implementazione WCF WS-ReliableMessaging fornisce una sessione affidabile per unidirezionali, request / reply e full duplex modelli di messaggistica.</span><span class="sxs-lookup"><span data-stu-id="a38a8-144">The WCF WS-ReliableMessaging implementation provides a reliable session for one-way, request-reply and full duplex messaging patterns.</span></span> <span data-ttu-id="a38a8-145">Il meccanismo `Offer` di WS-Reliable Messaging in `CreateSequence` e `CreateSequenceResponse` consente di stabilire due sequenze opposte correlate e fornisce un protocollo della sessione idoneo per tutti gli endpoint del messaggio.</span><span class="sxs-lookup"><span data-stu-id="a38a8-145">The WS-ReliableMessaging `Offer` mechanism on `CreateSequence` and `CreateSequenceResponse` lets you establish two correlated converse sequences and provides a session protocol that is suitable for all message endpoints.</span></span> <span data-ttu-id="a38a8-146">Poiché WCF fornisce una garanzia di sicurezza per tale sessione, inclusa la protezione end-to-end per l'integrità della sessione, è consigliabile assicurarsi che i messaggi destinati alla stessa parte arrivino alla stessa destinazione.</span><span class="sxs-lookup"><span data-stu-id="a38a8-146">Because WCF provides a security guarantee for such a session including end-to-end protection for session integrity, it is practical to ensure that messages intended for the same party arrive at the same destination.</span></span> <span data-ttu-id="a38a8-147">Ciò consente anche il "piggy-backing" degli acknowledgement della sequenza sui messaggi dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a38a8-147">This also allows "piggy-backing" of sequence acknowledgements on application messages.</span></span> <span data-ttu-id="a38a8-148">Pertanto, si applicano vincoli R1102 R1112 e R1113 a WCF.</span><span class="sxs-lookup"><span data-stu-id="a38a8-148">Therefore, constraints R1102, R1112, and R1113 apply to WCF.</span></span>  
  
 <span data-ttu-id="a38a8-149">Esempio di un messaggio `CreateSequence`.</span><span class="sxs-lookup"><span data-stu-id="a38a8-149">An example of a `CreateSequence` message.</span></span>  
  
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
  
 <span data-ttu-id="a38a8-150">Esempio di un messaggio `CreateSequenceResponse`.</span><span class="sxs-lookup"><span data-stu-id="a38a8-150">An example of a `CreateSequenceResponse` message.</span></span>  
  
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
  
### <a name="closing-a-sequence"></a><span data-ttu-id="a38a8-151">Chiusura di una sequenza</span><span class="sxs-lookup"><span data-stu-id="a38a8-151">Closing a Sequence</span></span>  
 <span data-ttu-id="a38a8-152">WCF Usa il `CloseSequence` e `CloseSequenceResponse` messaggi per un arresto iniziato dall'origine di Reliable Messaging.</span><span class="sxs-lookup"><span data-stu-id="a38a8-152">WCF uses the `CloseSequence` and `CloseSequenceResponse` messages for a Reliable Messaging source-initiated shutdown.</span></span> <span data-ttu-id="a38a8-153">La destinazione di Reliable Messaging di WCF non inizia l'arresto e l'origine di Reliable Messaging di WCF non supporta un arresto iniziato dalla destinazione di Reliable Messaging.</span><span class="sxs-lookup"><span data-stu-id="a38a8-153">The WCF Reliable Messaging destination does not initiate shutdown and the WCF Reliable Messaging source does not support a Reliable Messaging destination-initiated shutdown.</span></span> <span data-ttu-id="a38a8-154">Si applicano i vincoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="a38a8-154">The following constraints apply:</span></span>  
  
-   <span data-ttu-id="a38a8-155">B1201: L'origine di Reliable Messaging di WCF invia sempre un `CloseSequence` messaggio per chiudere la sequenza.</span><span class="sxs-lookup"><span data-stu-id="a38a8-155">B1201: The WCF Reliable Messaging source always sends a `CloseSequence` message to shut down the sequence.</span></span>  
  
-   <span data-ttu-id="a38a8-156">B1202: L'origine di Reliable Messaging attende acknowledgement dell'intera serie di messaggi della sequenza prima di inviare il `CloseSequence` messaggio.</span><span class="sxs-lookup"><span data-stu-id="a38a8-156">B1202: The Reliable Messaging source waits for acknowledgement of the full range of sequence messages before sending the `CloseSequence` message.</span></span>  
  
-   <span data-ttu-id="a38a8-157">B1203: L'origine di Reliable Messaging include sempre l'opzione facoltativa `LastMsgNumber` elemento, a meno che la sequenza non contiene messaggi.</span><span class="sxs-lookup"><span data-stu-id="a38a8-157">B1203: The Reliable Messaging source always includes the optional `LastMsgNumber` element unless the sequence does not contain messages.</span></span>  
  
-   <span data-ttu-id="a38a8-158">R1204: La destinazione di Reliable Messaging non deve avviare l'arresto inviando un `CloseSequence` messaggio.</span><span class="sxs-lookup"><span data-stu-id="a38a8-158">R1204: The Reliable Messaging destination must not initiate shutdown by sending a `CloseSequence` message.</span></span>  
  
-   <span data-ttu-id="a38a8-159">B1205: Al momento della ricezione un `CloseSequence` messaggio, l'origine di Reliable Messaging di WCF considera la sequenza incompleta e invia un errore.</span><span class="sxs-lookup"><span data-stu-id="a38a8-159">B1205: Upon receiving a `CloseSequence` message, the WCF Reliable Messaging source considers the sequence incomplete and sends a fault.</span></span>  
  
 <span data-ttu-id="a38a8-160">Esempio di un messaggio `CloseSequence`.</span><span class="sxs-lookup"><span data-stu-id="a38a8-160">An example of a `CloseSequence` message.</span></span>  
  
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
  
### <a name="sequence-termination"></a><span data-ttu-id="a38a8-161">Terminazione della sequenza</span><span class="sxs-lookup"><span data-stu-id="a38a8-161">Sequence Termination</span></span>  
 <span data-ttu-id="a38a8-162">WCF Usa principalmente la `TerminateSequence/TerminateSequenceResponse` handshake dopo aver completato la `CloseSequence/CloseSequenceResponse` handshake.</span><span class="sxs-lookup"><span data-stu-id="a38a8-162">WCF primarily uses the `TerminateSequence/TerminateSequenceResponse` handshake after completing the `CloseSequence/CloseSequenceResponse` handshake.</span></span> <span data-ttu-id="a38a8-163">La destinazione di Reliable Messaging di WCF non inizia la terminazione e l'origine di Reliable Messaging non supporta una terminazione iniziata dalla destinazione di Reliable Messaging.</span><span class="sxs-lookup"><span data-stu-id="a38a8-163">The WCF Reliable Messaging destination does not initiate termination and the Reliable Messaging source does not support a Reliable Messaging destination-initiated termination.</span></span> <span data-ttu-id="a38a8-164">Si applicano i vincoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="a38a8-164">The following constraints apply:</span></span>  
  
-   <span data-ttu-id="a38a8-165">B1301: L'iniziatore WCF invia solo il `TerminateSequence` messaggio dopo il completamento del `CloseSequence/CloseSequenceResponse` handshake.</span><span class="sxs-lookup"><span data-stu-id="a38a8-165">B1301: The WCF Initiator only sends the `TerminateSequence` message after the successful completion of the `CloseSequence/CloseSequenceResponse` handshake.</span></span>  
  
-   <span data-ttu-id="a38a8-166">R1302: WCF consente di verificare che il `LastMsgNumber` elemento sia coerenza in tutti `CloseSequence` e `TerminateSequence` messaggi per una sequenza specificata.</span><span class="sxs-lookup"><span data-stu-id="a38a8-166">R1302: WCF validates that the `LastMsgNumber` element is consistent across all `CloseSequence` and `TerminateSequence` messages for a given sequence.</span></span> <span data-ttu-id="a38a8-167">Ciò significa che `LastMsgNumber` o non è presente in tutti i messaggi `CloseSequence` e `TerminateSequence`, o è presente e identico in tutti i messaggi `CloseSequence` e `TerminateSequence`.</span><span class="sxs-lookup"><span data-stu-id="a38a8-167">This means that `LastMsgNumber` is either not present on all `CloseSequence` and `TerminateSequence` messages, or it is present and identical on all `CloseSequence` and `TerminateSequence` messages.</span></span>  
  
-   <span data-ttu-id="a38a8-168">B1303: Quando si riceve un `TerminateSequence` dei messaggi dopo il `CloseSequence/CloseSequenceResponse` handshake, la destinazione di Reliable Messaging risponde con un `TerminateSequenceResponse` messaggio.</span><span class="sxs-lookup"><span data-stu-id="a38a8-168">B1303: When receiving a `TerminateSequence` message after the `CloseSequence/CloseSequenceResponse` handshake, the Reliable Messaging destination responds with a `TerminateSequenceResponse` message.</span></span> <span data-ttu-id="a38a8-169">Poiché l'origine di Reliable Messaging dispone dell'acknowledgement finale prima dell'invio del messaggio `TerminateSequence`, la destinazione di Reliable Messaging è a conoscenza della fine della sequenza e richiede immediatamente le risorse.</span><span class="sxs-lookup"><span data-stu-id="a38a8-169">Because the Reliable Messaging source has the final acknowledgement before sending the `TerminateSequence` message, the Reliable Messaging destination knows without doubt that the sequence ends, and reclaims resources immediately.</span></span>  
  
-   <span data-ttu-id="a38a8-170">B1304: Quando si riceve un `TerminateSequence` dei messaggi nelle versioni precedenti al `CloseSequence/CloseSequenceResponse` handshake, la destinazione di WCF Reliable Messaging risponde con un `TerminateSequenceResponse` messaggio.</span><span class="sxs-lookup"><span data-stu-id="a38a8-170">B1304: When receiving a `TerminateSequence` message prior to the `CloseSequence/CloseSequenceResponse` handshake, the WCF Reliable Messaging destination responds with a `TerminateSequenceResponse` message.</span></span> <span data-ttu-id="a38a8-171">Se la destinazione di Reliable Messaging stabilisce che non vi sono incoerenze nella sequenza, attende per il periodo di tempo specificato dalla destinazione dell'applicazione prima di richiedere le risorse, per offrire al client la possibilità di ricevere l'acknowledgement finale.</span><span class="sxs-lookup"><span data-stu-id="a38a8-171">If the Reliable Messaging destination determines that there are no inconsistencies in the sequence, the Reliable Messaging destination waits for an application destination-specified time before reclaiming resources, to allow the client the chance to receive the final acknowledgement.</span></span> <span data-ttu-id="a38a8-172">In caso contrario, la destinazione di Reliable Messaging richiede immediatamente le risorse e indica alla destinazione dell'applicazione che la sequenza termina in modo dubbio generando l'evento `Faulted`.</span><span class="sxs-lookup"><span data-stu-id="a38a8-172">Otherwise, the Reliable Messaging destination reclaims resources immediately and indicates to the application destination that the sequence ends with doubt by raising the `Faulted` event.</span></span>  
  
 <span data-ttu-id="a38a8-173">Esempio di un messaggio `TerminateSequence`.</span><span class="sxs-lookup"><span data-stu-id="a38a8-173">An example of a `TerminateSequence` message.</span></span>  
  
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
  
### <a name="sequences"></a><span data-ttu-id="a38a8-174">Sequenze</span><span class="sxs-lookup"><span data-stu-id="a38a8-174">Sequences</span></span>  
 <span data-ttu-id="a38a8-175">Di seguito è riportato un elenco di vincoli che si applicano alle sequenze:</span><span class="sxs-lookup"><span data-stu-id="a38a8-175">The following is a list of constraints that apply to sequences:</span></span>  
  
-   <span data-ttu-id="a38a8-176">Genera l'errore B1401:WCF e gli accessi alla sequenza di numeri non superiori al `xs:long`del valore massimo, 9223372036854775807.</span><span class="sxs-lookup"><span data-stu-id="a38a8-176">B1401:WCF generates and accesses sequence numbers no higher than `xs:long`’s maximum inclusive value, 9223372036854775807.</span></span>  
  
 <span data-ttu-id="a38a8-177">Esempio di intestazione `Sequence`.</span><span class="sxs-lookup"><span data-stu-id="a38a8-177">An example of a `Sequence` header.</span></span>  
  
```xml  
<wsrm:Sequence s:mustUnderstand="1">  
  <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
  <wsrm:MessageNumber>1</wsrm:MessageNumber>  
</wsrm:Sequence>  
```  
  
### <a name="request-acknowledgement"></a><span data-ttu-id="a38a8-178">Acknowledgement della richiesta</span><span class="sxs-lookup"><span data-stu-id="a38a8-178">Request Acknowledgement</span></span>  
 <span data-ttu-id="a38a8-179">WCF utilizza il `AckRequested` intestazione come meccanismo keep-alive.</span><span class="sxs-lookup"><span data-stu-id="a38a8-179">WCF uses the `AckRequested` header as a keep-alive mechanism.</span></span>  
  
 <span data-ttu-id="a38a8-180">Esempio di intestazione `AckRequested`.</span><span class="sxs-lookup"><span data-stu-id="a38a8-180">An example of an `AckRequested` header.</span></span>  
  
```xml  
<wsrm:AckRequested>  
  <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
</wsrm:AckRequested>  
```  
  
### <a name="sequenceacknowledgement"></a><span data-ttu-id="a38a8-181">SequenceAcknowledgement</span><span class="sxs-lookup"><span data-stu-id="a38a8-181">SequenceAcknowledgement</span></span>  
 <span data-ttu-id="a38a8-182">WCF Usa un meccanismo "piggy-back" per gli acknowledgement di sequenza forniti in WS-Reliable Messaging.</span><span class="sxs-lookup"><span data-stu-id="a38a8-182">WCF uses a "piggy-back" mechanism for sequence acknowledgements provided in WS-Reliable Messaging.</span></span> <span data-ttu-id="a38a8-183">Si applicano i vincoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="a38a8-183">The following constraints apply:</span></span>  
  
-   <span data-ttu-id="a38a8-184">R1601: Quando vengono stabilite due sequenze opposte utilizzando il `Offer` meccanismo, il `SequenceAcknowledgement` intestazione può essere incluso nei messaggi dell'applicazione trasmesso al destinatario desiderato.</span><span class="sxs-lookup"><span data-stu-id="a38a8-184">R1601: When two converse sequences are established using the `Offer` mechanism, the `SequenceAcknowledgement` header may be included in any application message transmitted to the intended recipient.</span></span> <span data-ttu-id="a38a8-185">L'endpoint remoto deve essere in grado di accedere a un'intestazione `SequenceAcknowledgement` sottoposta a piggyback.</span><span class="sxs-lookup"><span data-stu-id="a38a8-185">The remote endpoint must be able to access a piggybacked `SequenceAcknowledgement` header.</span></span>  
  
-   <span data-ttu-id="a38a8-186">B1602: WCF non genera `SequenceAcknowledgement` intestazioni contenenti `Nack` elementi.</span><span class="sxs-lookup"><span data-stu-id="a38a8-186">B1602: WCF does not generate `SequenceAcknowledgement` headers that contain `Nack` elements.</span></span> <span data-ttu-id="a38a8-187">WCF verifica che ogni `Nack` elemento contiene un numero di sequenza, ma altrimenti ignora il `Nack` elemento e il valore.</span><span class="sxs-lookup"><span data-stu-id="a38a8-187">WCF validates that each `Nack` element contains a sequence number, but otherwise ignores the `Nack` element and value.</span></span>  
  
 <span data-ttu-id="a38a8-188">Esempio di intestazione `SequenceAcknowledgement`.</span><span class="sxs-lookup"><span data-stu-id="a38a8-188">An example of a `SequenceAcknowledgement` header.</span></span>  
  
```xml  
<wsrm:SequenceAcknowledgement>  
  <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
  <wsrm:AcknowledgementRange Lower="1" Upper="1"></wsrm:AcknowledgementRange>  
</wsrm:SequenceAcknowledgement>  
```  
  
### <a name="ws-reliablemessaging-faults"></a><span data-ttu-id="a38a8-189">Errori WS-ReliableMessaging</span><span class="sxs-lookup"><span data-stu-id="a38a8-189">WS-ReliableMessaging Faults</span></span>  
 <span data-ttu-id="a38a8-190">Di seguito è riportato un elenco di vincoli che si applicano all'implementazione WCF di WS-ReliableMessaging errori.</span><span class="sxs-lookup"><span data-stu-id="a38a8-190">The following is a list of constraints that apply to the WCF implementation of WS-ReliableMessaging faults.</span></span> <span data-ttu-id="a38a8-191">Si applicano i vincoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="a38a8-191">The following constraints apply:</span></span>  
  
-   <span data-ttu-id="a38a8-192">B1701: WCF non genera `MessageNumberRollover` errori.</span><span class="sxs-lookup"><span data-stu-id="a38a8-192">B1701: WCF does not generate `MessageNumberRollover` faults.</span></span>  
  
-   <span data-ttu-id="a38a8-193">B1702: Su SOAP 1.2 quando l'endpoint del servizio raggiunge il limite di connessione e non è in grado di elaborare nuove connessioni, WCF genera nidificate `CreateSequenceRefused` codice secondario, di errore `netrm:ConnectionLimitReached`, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="a38a8-193">B1702: Over SOAP 1.2, when the service endpoint reaches its connection limit and cannot process new connections, WCF generates a nested `CreateSequenceRefused` fault subcode, `netrm:ConnectionLimitReached`, as shown in the following example.</span></span>  
  
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
  
### <a name="ws-addressing-faults"></a><span data-ttu-id="a38a8-194">Errori WS-Addressing</span><span class="sxs-lookup"><span data-stu-id="a38a8-194">WS-Addressing Faults</span></span>  
 <span data-ttu-id="a38a8-195">Poiché WS-ReliableMessaging utilizza WS-Addressing, l'implementazione WCF WS-ReliableMessaging potrebbe generare e trasmettere errori WS-Addressing.</span><span class="sxs-lookup"><span data-stu-id="a38a8-195">Because WS-ReliableMessaging uses WS-Addressing, the WCF WS-ReliableMessaging implementation may generate and transmit WS-Addressing faults.</span></span> <span data-ttu-id="a38a8-196">In questa sezione vengono trattati gli errori WS-Addressing che WCF genera e trasmette a livello di WS-ReliableMessaging in modo esplicito:</span><span class="sxs-lookup"><span data-stu-id="a38a8-196">This section covers the WS-Addressing faults that WCF explicitly generates and transmits at the WS-ReliableMessaging layer:</span></span>  
  
-   <span data-ttu-id="a38a8-197">B1801:WCF genera e trasmette il `Message Addressing Header Required` di errore quando viene soddisfatta una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a38a8-197">B1801:WCF generates and transmits the `Message Addressing Header Required` fault when one of the following is true:</span></span>  
  
    -   <span data-ttu-id="a38a8-198">In un messaggio `CreateSequence`, `CloseSequence` o `TerminateSequence` manca un'intestazione `MessageId`.</span><span class="sxs-lookup"><span data-stu-id="a38a8-198">A `CreateSequence`, `CloseSequence` or `TerminateSequence` message is missing a `MessageId` header.</span></span>  
  
    -   <span data-ttu-id="a38a8-199">In un messaggio `CreateSequence`, `CloseSequence` o `TerminateSequence` manca un'intestazione `ReplyTo`.</span><span class="sxs-lookup"><span data-stu-id="a38a8-199">A `CreateSequence`, `CloseSequence` or `TerminateSequence` message is missing a `ReplyTo` header.</span></span>  
  
    -   <span data-ttu-id="a38a8-200">In un messaggio `CreateSequenceResponse`, `CloseSequenceResponse` o `TerminateSequenceResponse` manca un'intestazione `RelatesTo`.</span><span class="sxs-lookup"><span data-stu-id="a38a8-200">A `CreateSequenceResponse`, `CloseSequenceResponse`, or `TerminateSequenceResponse` message is missing a `RelatesTo` header.</span></span>  
  
-   <span data-ttu-id="a38a8-201">B1802:WCF genera e trasmette il `Endpoint Unavailable` errore per indicare nessun endpoint in ascolto è in grado di elaborare la sequenza di base all'esame delle intestazioni di indirizzamento nel `CreateSequence` messaggio.</span><span class="sxs-lookup"><span data-stu-id="a38a8-201">B1802:WCF generates and transmits the `Endpoint Unavailable` fault to indicate there is no endpoint listening that can process the sequence based on examination of the addressing headers in the `CreateSequence` message.</span></span>  
  
## <a name="protocol-composition"></a><span data-ttu-id="a38a8-202">Composizione del protocollo</span><span class="sxs-lookup"><span data-stu-id="a38a8-202">Protocol Composition</span></span>  
  
### <a name="composition-with-ws-addressing"></a><span data-ttu-id="a38a8-203">Composizione con WS-Addressing</span><span class="sxs-lookup"><span data-stu-id="a38a8-203">Composition with WS-Addressing</span></span>  
 <span data-ttu-id="a38a8-204">WCF supporta due versioni di WS-Addressing: WS-Addressing 2004/08 [WS-ADDR] e W3C WS-Addressing 1.0 raccomandazioni [WS-ADDR-CORE] e [WS-ADDR-SOAP].</span><span class="sxs-lookup"><span data-stu-id="a38a8-204">WCF supports two versions of WS-Addressing: WS-Addressing 2004/08 [WS-ADDR] and W3C WS-Addressing 1.0 Recommendations [WS-ADDR-CORE] and [WS-ADDR-SOAP].</span></span>  
  
 <span data-ttu-id="a38a8-205">Anche se la specifica WS-ReliableMessaging menziona solo WS-Addressing 2004/08, non limita la versione WS-Addressing da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="a38a8-205">While the WS-ReliableMessaging specification mentions only WS-Addressing 2004/08, it does not restrict the WS-Addressing version to be used.</span></span> <span data-ttu-id="a38a8-206">Di seguito è riportato un elenco di vincoli che si applicano a WCF:</span><span class="sxs-lookup"><span data-stu-id="a38a8-206">The following is a list of constraints that apply to WCF:</span></span>  
  
-   <span data-ttu-id="a38a8-207">R2101: Sia WS-Addressing 2004/08 che WS-Addressing 1.0 possono essere utilizzati con WS-Reliable Messaging.</span><span class="sxs-lookup"><span data-stu-id="a38a8-207">R2101: Both WS-Addressing 2004/08 and WS-Addressing 1.0 can be used with WS-Reliable Messaging.</span></span>  
  
-   <span data-ttu-id="a38a8-208">R2102: Deve essere usata una sola versione di WS-Addressing in una data sequenza di WS-ReliableMessaging o una coppia di sequenze opposte correlate tramite il `Offer` meccanismo.</span><span class="sxs-lookup"><span data-stu-id="a38a8-208">R2102: A single version of WS-Addressing must be used throughout a given WS-ReliableMessaging sequence or a pair of converse sequences correlated by using the `Offer` mechanism.</span></span>  
  
### <a name="composition-with-soap"></a><span data-ttu-id="a38a8-209">Composizione con SOAP</span><span class="sxs-lookup"><span data-stu-id="a38a8-209">Composition with SOAP</span></span>  
 <span data-ttu-id="a38a8-210">WCF supporta l'utilizzo di SOAP 1.1 e SOAP 1.2 con WS-Reliable Messaging.</span><span class="sxs-lookup"><span data-stu-id="a38a8-210">WCF supports the use of both SOAP 1.1 and SOAP 1.2 with WS-Reliable Messaging.</span></span>  
  
### <a name="composition-with-ws-security-and-ws-secureconversation"></a><span data-ttu-id="a38a8-211">Composizione con WS-Security e WS-SecureConversation</span><span class="sxs-lookup"><span data-stu-id="a38a8-211">Composition with WS-Security and WS-SecureConversation</span></span>  
 <span data-ttu-id="a38a8-212">WCF fornisce protezione per le sequenze WS-ReliableMessaging usando sicuro trasporto (HTTPS), composizione con WS-Security e composizione con WS-SecureConversation.</span><span class="sxs-lookup"><span data-stu-id="a38a8-212">WCF provides protection for WS-ReliableMessaging sequences by using secure Transport (HTTPS), composition with WS-Security, and composition with WS-Secure Conversation.</span></span> <span data-ttu-id="a38a8-213">Il protocollo WS-Reliable Messaging 1.1, WS-Security 1.1 e il protocollo WS-SecureConversation 1.3 devono essere utilizzati insieme.</span><span class="sxs-lookup"><span data-stu-id="a38a8-213">The WS-ReliableMessaging 1.1 protocol, WS-Security 1.1 and WS-Secure Conversation 1.3 protocol should be used together.</span></span> <span data-ttu-id="a38a8-214">Di seguito è riportato un elenco di vincoli che si applicano a WCF:</span><span class="sxs-lookup"><span data-stu-id="a38a8-214">The following is a list of constraints that apply to WCF:</span></span>  
  
-   <span data-ttu-id="a38a8-215">R2301: Per proteggere l'integrità di una sequenza WS-ReliableMessaging oltre all'integrità e riservatezza dei singoli messaggi, WCF, è necessario che deve essere utilizzato WS-SecureConversation.</span><span class="sxs-lookup"><span data-stu-id="a38a8-215">R2301: To protect the integrity of a WS-ReliableMessaging sequence in addition to the integrity and confidentiality of individual messages, WCF requires that WS-Secure Conversation must be used.</span></span>  
  
-   <span data-ttu-id="a38a8-216">R2302:AWS-Secure Conversation deve essere stabilita prima di stabilire WS-ReliableMessaging sequence(s).</span><span class="sxs-lookup"><span data-stu-id="a38a8-216">R2302:AWS-Secure Conversation session must be established prior to establishing WS-ReliableMessaging sequence(s).</span></span>  
  
-   <span data-ttu-id="a38a8-217">R2303: Se la durata della sequenza WS-ReliableMessaging supera WS-Secure Conversation durata della sessione, il `SecurityContextToken` stabilito tramite WS-Secure Conversation deve essere rinnovato tramite l'associazione WS-Secure Conversation Renewal corrispondente.</span><span class="sxs-lookup"><span data-stu-id="a38a8-217">R2303: If the WS-ReliableMessaging sequence lifetime exceeds the WS-Secure Conversation session’s lifetime, the `SecurityContextToken` established by using WS-Secure Conversation must be renewed by using the corresponding WS-Secure Conversation Renewal binding.</span></span>  
  
-   <span data-ttu-id="a38a8-218">B2304:ws-sequenza ReliableMessaging o una coppia di sequenze opposte è sempre associata a una singola sessione WS-SecureConversation.</span><span class="sxs-lookup"><span data-stu-id="a38a8-218">B2304:WS-ReliableMessaging sequence or a pair of correlated converse sequences are always bound to a single WS-SecureConversation session.</span></span>  
  
-   <span data-ttu-id="a38a8-219">R2305: Caso di composizione con WS-SecureConversation, il risponditore WCF richiede che il `CreateSequence` il messaggio contiene il `wsse:SecurityTokenReference` elemento e il `wsrm:UsesSequenceSTR` intestazione.</span><span class="sxs-lookup"><span data-stu-id="a38a8-219">R2305: When composed with WS-Secure Conversation, the WCF responder requires that the `CreateSequence` message contain the `wsse:SecurityTokenReference` element and the `wsrm:UsesSequenceSTR` header.</span></span>  
  
 <span data-ttu-id="a38a8-220">Esempio di intestazione `UsesSequenceSTR`.</span><span class="sxs-lookup"><span data-stu-id="a38a8-220">An example of a `UsesSequenceSTR` header.</span></span>  
  
```xml  
<wsrm:UsesSequenceSTR></wsrm:UsesSequenceSTR>  
```  
  
### <a name="composition-with-ssltls-sessions"></a><span data-ttu-id="a38a8-221">Composizione con sessioni SSL/TLS</span><span class="sxs-lookup"><span data-stu-id="a38a8-221">Composition with SSL/TLS sessions</span></span>  
 <span data-ttu-id="a38a8-222">WCF non supporta la composizione con sessioni SSL/TLS:</span><span class="sxs-lookup"><span data-stu-id="a38a8-222">WCF does not support composition with SSL/TLS sessions:</span></span>  
  
-   <span data-ttu-id="a38a8-223">B2401: WCF non genera il `wsrm:UsesSequenceSSL` intestazione.</span><span class="sxs-lookup"><span data-stu-id="a38a8-223">B2401: WCF does not generate the `wsrm:UsesSequenceSSL` header.</span></span>  
  
-   <span data-ttu-id="a38a8-224">R2402: Un iniziatore Reliable Messaging non deve essere inviato un `CreateSequence` dei messaggi con un `wsrm:UsesSequenceSSL` intestazione a un risponditore di WCF.</span><span class="sxs-lookup"><span data-stu-id="a38a8-224">R2402: A Reliable Messaging Initiator must not send a `CreateSequence` message with a `wsrm:UsesSequenceSSL` header to a WCF Responder.</span></span>  
  
### <a name="composition-with-ws-policy"></a><span data-ttu-id="a38a8-225">Composizione con WS-Policy</span><span class="sxs-lookup"><span data-stu-id="a38a8-225">Composition with WS-Policy</span></span>  
 <span data-ttu-id="a38a8-226">WCF supporta due versioni di WS-Policy: WS-Policy 1.2 e WS-Policy 1.5.</span><span class="sxs-lookup"><span data-stu-id="a38a8-226">WCF supports two versions of WS-Policy: WS-Policy 1.2 and WS-Policy 1.5.</span></span>  
  
## <a name="ws-reliablemessaging-ws-policy-assertion"></a><span data-ttu-id="a38a8-227">Asserzione di WS-Policy relativa a WS-ReliableMessaging</span><span class="sxs-lookup"><span data-stu-id="a38a8-227">WS-ReliableMessaging WS-Policy Assertion</span></span>  
 <span data-ttu-id="a38a8-228">WCF utilizza l'asserzione di WS-Policy WS-ReliableMessaging `wsrm:RMAssertion` per descrivere le funzionalità degli endpoint.</span><span class="sxs-lookup"><span data-stu-id="a38a8-228">WCF uses WS-ReliableMessaging WS-Policy Assertion `wsrm:RMAssertion` to describe endpoints capabilities.</span></span> <span data-ttu-id="a38a8-229">Di seguito è riportato un elenco di vincoli che si applicano a WCF:</span><span class="sxs-lookup"><span data-stu-id="a38a8-229">The following is a list of constraints that apply to WCF:</span></span>  
  
-   <span data-ttu-id="a38a8-230">B3001: WCF Allega `wsrmn:RMAssertion` asserzione WS-Policy relativa a `wsdl:binding` elementi.</span><span class="sxs-lookup"><span data-stu-id="a38a8-230">B3001: WCF attaches `wsrmn:RMAssertion` WS-Policy Assertion to `wsdl:binding` elements.</span></span> <span data-ttu-id="a38a8-231">WCF supporta i collegamenti agli `wsdl:binding` e `wsdl:port` elementi.</span><span class="sxs-lookup"><span data-stu-id="a38a8-231">WCF supports both attachments to `wsdl:binding` and `wsdl:port` elements.</span></span>  
  
-   <span data-ttu-id="a38a8-232">B3002: WCF non genera mai il `wsp:Optional` tag.</span><span class="sxs-lookup"><span data-stu-id="a38a8-232">B3002: WCF never generates the `wsp:Optional` tag.</span></span>  
  
-   <span data-ttu-id="a38a8-233">B3003: Quando si accede al `wsrmp:RMAssertion` asserzione di WS-Policy, WCF ignora il `wsp:Optional` tag e considera il criterio WS-RM come obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="a38a8-233">B3003: When accessing the `wsrmp:RMAssertion` WS-Policy Assertion, WCF ignores the `wsp:Optional` tag and treats the WS-RM policy as mandatory.</span></span>  
  
-   <span data-ttu-id="a38a8-234">R3004: Poiché WCF non esegue la composizione con sessioni SSL/TLS, WCF non accetta il criterio che specifica `wsrmp:SequenceTransportSecurity`.</span><span class="sxs-lookup"><span data-stu-id="a38a8-234">R3004: Because WCF does not compose with SSL/TLS sessions, WCF does not accept policy that specifies `wsrmp:SequenceTransportSecurity`.</span></span>  
  
-   <span data-ttu-id="a38a8-235">B3005: WCF genera sempre il `wsrmp:DeliveryAssurance` elemento.</span><span class="sxs-lookup"><span data-stu-id="a38a8-235">B3005: WCF always generates the `wsrmp:DeliveryAssurance` element.</span></span>  
  
-   <span data-ttu-id="a38a8-236">B3006: WCF consente di specificare sempre il `wsrmp:ExactlyOnce` garanzia di recapito.</span><span class="sxs-lookup"><span data-stu-id="a38a8-236">B3006: WCF always specifies the `wsrmp:ExactlyOnce` delivery assurance.</span></span>  
  
-   <span data-ttu-id="a38a8-237">B3007: WCF genera e legge le proprietà seguenti dell'asserzione WS-ReliableMessaging e fornisce il controllo su di essi in WCF`ReliableSessionBindingElement`:</span><span class="sxs-lookup"><span data-stu-id="a38a8-237">B3007: WCF generates and reads the following properties of the WS-ReliableMessaging assertion and provides control over them on the WCF`ReliableSessionBindingElement`:</span></span>  
  
    -   `netrmp:InactivityTimeout`  
  
    -   `netrmp:AcknowledgementInterval`  
  
     <span data-ttu-id="a38a8-238">Esempio di `RMAssertion`.</span><span class="sxs-lookup"><span data-stu-id="a38a8-238">An example of a `RMAssertion`.</span></span>  
  
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
  
## <a name="flow-control-ws-reliablemessaging-extension"></a><span data-ttu-id="a38a8-239">Estensione di WS-ReliableMessaging per il controllo del flusso</span><span class="sxs-lookup"><span data-stu-id="a38a8-239">Flow Control WS-ReliableMessaging Extension</span></span>  
 <span data-ttu-id="a38a8-240">WCF utilizza l'estendibilità WS-ReliableMessaging per fornire un controllo facoltativo aggiuntivo sul flusso di messaggi sequenza.</span><span class="sxs-lookup"><span data-stu-id="a38a8-240">WCF uses WS-ReliableMessaging extensibility to provide optional additional tighter control over sequence message flow.</span></span>  
  
 <span data-ttu-id="a38a8-241">Controllo di flusso viene abilitato impostando il <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.FlowControlEnabled?displayProperty=nameWithType> proprietà `true`.</span><span class="sxs-lookup"><span data-stu-id="a38a8-241">Flow control is enabled by setting the <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.FlowControlEnabled?displayProperty=nameWithType> property to `true`.</span></span> <span data-ttu-id="a38a8-242">Di seguito è riportato un elenco di vincoli che si applicano a WCF:</span><span class="sxs-lookup"><span data-stu-id="a38a8-242">The following is a list of constraints that apply to WCF:</span></span>  
  
-   <span data-ttu-id="a38a8-243">B4001: Quando è abilitata la messaggistica affidabile flusso di controllo, WCF genera un `netrm:BufferRemaining` nell'estendibilità dell'elemento dell'elemento di `SequenceAcknowledgement` intestazione, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="a38a8-243">B4001: When Reliable Messaging Flow Control is enabled, WCF generates a `netrm:BufferRemaining` element in the element extensibility of the `SequenceAcknowledgement` header, as shown in the following example.</span></span>  
  
    ```xml  
    <wsrm:SequenceAcknowledgement>  
      <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
      <wsrm:AcknowledgementRange Upper="1" Lower="1"/>             
      <netrm:BufferRemaining>8</netrm:BufferRemaining>  
    </wsrm:SequenceAcknowledgement>  
    ```  
  
-   <span data-ttu-id="a38a8-244">B4002: Anche quando la messaggistica affidabile flusso di controllo è abilitato, WCF non richiede un `netrm:BufferRemaining` elemento il `SequenceAcknowledgement` intestazione.</span><span class="sxs-lookup"><span data-stu-id="a38a8-244">B4002: Even when Reliable Messaging Flow Control is enabled, WCF does not require a `netrm:BufferRemaining` element in the `SequenceAcknowledgement` header.</span></span>  
  
-   <span data-ttu-id="a38a8-245">B4003: Destinazione di messaggistica affidabili WCF utilizza `netrm:BufferRemaining` per indicare quanti messaggi nuovi è possibile memorizzare nel buffer.</span><span class="sxs-lookup"><span data-stu-id="a38a8-245">B4003: WCF Reliable Messaging Destination uses `netrm:BufferRemaining` to indicate how many new messages it can buffer.</span></span>  
  
-   <span data-ttu-id="a38a8-246">B4004:when Reliable Messaging flusso di controllo è abilitato, l'origine di messaggistica affidabili WCF utilizza il valore di `netrm:BufferRemaining` per la trasmissione dei messaggi di limitazione.</span><span class="sxs-lookup"><span data-stu-id="a38a8-246">B4004:When Reliable Messaging Flow Control is enabled, the WCF Reliable Messaging Source uses the value of `netrm:BufferRemaining` to throttle message transmission.</span></span>  
  
-   <span data-ttu-id="a38a8-247">B4005: WCF genera `netrm:BufferRemaining` integer i valori compresi tra 0 e 4096 incluso e legge valori integer compresi tra 0 e `xs:int`del `maxInclusive` valore 214748364 incluso.</span><span class="sxs-lookup"><span data-stu-id="a38a8-247">B4005: WCF generates `netrm:BufferRemaining` integer values between 0 and 4096 inclusive, and reads integer values between 0 and `xs:int`’s `maxInclusive` value 214748364 inclusive.</span></span>  
  
## <a name="message-exchange-patterns"></a><span data-ttu-id="a38a8-248">Modelli di scambio dei messaggi</span><span class="sxs-lookup"><span data-stu-id="a38a8-248">Message Exchange Patterns</span></span>  
 <span data-ttu-id="a38a8-249">In questa sezione viene descritto il comportamento di WCF quando WS-ReliableMessaging viene usato per modelli di scambio di messaggi diversi.</span><span class="sxs-lookup"><span data-stu-id="a38a8-249">This section describes WCF's behavior when WS-ReliableMessaging is used for different Message Exchange Patterns.</span></span> <span data-ttu-id="a38a8-250">Per ogni modello di scambio di messaggi, vengono presi in considerazione i due scenari di distribuzione seguenti:</span><span class="sxs-lookup"><span data-stu-id="a38a8-250">For each Message Exchange Pattern the following two deployments scenarios are considered:</span></span>  
  
-   <span data-ttu-id="a38a8-251">Iniziatore non indirizzabile: Iniziatore si trova dietro un firewall; Risponditore può recapitare messaggi all'iniziatore solo su risposte HTTP.</span><span class="sxs-lookup"><span data-stu-id="a38a8-251">Non-Addressable Initiator: Initiator is behind a firewall; Responder can deliver messages to the Initiator only on HTTP responses.</span></span>  
  
-   <span data-ttu-id="a38a8-252">Iniziatore indirizzabile: Iniziatore e risponditore sia possibile inviare richieste HTTP. in altre parole, è possano stabilire due connessioni HTTP opposte.</span><span class="sxs-lookup"><span data-stu-id="a38a8-252">Addressable Initiator: Initiator and Responder both can be sent HTTP requests; in other words, two converse HTTP connections can be established.</span></span>  
  
### <a name="one-way-non-addressable-initiator"></a><span data-ttu-id="a38a8-253">Iniziatore unidirezionale, non indirizzabile</span><span class="sxs-lookup"><span data-stu-id="a38a8-253">One-way, Non-addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="a38a8-254">Binding</span><span class="sxs-lookup"><span data-stu-id="a38a8-254">Binding</span></span>  
 <span data-ttu-id="a38a8-255">WCF fornisce un modello di scambio di messaggi unidirezionale utilizzando una sequenza su un canale HTTP.</span><span class="sxs-lookup"><span data-stu-id="a38a8-255">WCF provides a one-way message exchange pattern using one sequence over one HTTP channel.</span></span> <span data-ttu-id="a38a8-256">WCF utilizza le richieste HTTP per trasmettere tutti i messaggi dall'iniziatore alle risposte del risponditore e di HTTP per trasmettere tutti i messaggi dal risponditore all'iniziatore.</span><span class="sxs-lookup"><span data-stu-id="a38a8-256">WCF uses HTTP requests to transmit all messages from the Initiator to the Responder and HTTP responses to transmit all messages from the Responder to the Initiator.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="a38a8-257">Scambio CreateSequence</span><span class="sxs-lookup"><span data-stu-id="a38a8-257">CreateSequence Exchange</span></span>  
 <span data-ttu-id="a38a8-258">L'iniziatore WCF trasmette una `CreateSequence` messaggio senza alcun `Offer` elemento su una richiesta HTTP e attende la `CreateSequenceResponse` messaggio sulla risposta HTTP.</span><span class="sxs-lookup"><span data-stu-id="a38a8-258">The WCF Initiator transmits a `CreateSequence` message with no `Offer` element on an HTTP request and expects the `CreateSequenceResponse` message on the HTTP response.</span></span> <span data-ttu-id="a38a8-259">Il risponditore WCF crea una sequenza e trasmette il `CreateSequenceResponse` senza alcun messaggio `Accept` elemento sulla risposta HTTP.</span><span class="sxs-lookup"><span data-stu-id="a38a8-259">The WCF Responder creates a sequence and transmits the `CreateSequenceResponse` message with no `Accept` element on the HTTP response.</span></span>  
  
#### <a name="sequenceacknowledgement"></a><span data-ttu-id="a38a8-260">SequenceAcknowledgement</span><span class="sxs-lookup"><span data-stu-id="a38a8-260">SequenceAcknowledgement</span></span>  
 <span data-ttu-id="a38a8-261">L'iniziatore WCF elabora gli acknowledgement sulla risposta di tutti i messaggi tranne il `CreateSequence` messaggi e messaggi di errore.</span><span class="sxs-lookup"><span data-stu-id="a38a8-261">The WCF Initiator processes acknowledgements on the reply of all messages except the `CreateSequence` message and fault messages.</span></span> <span data-ttu-id="a38a8-262">Il risponditore WCF trasmette sempre un acknowledgement autonomo sulla risposta HTTP a tutte le sequenze e `AckRequested` messaggi.</span><span class="sxs-lookup"><span data-stu-id="a38a8-262">The WCF Responder always transmits a stand-alone acknowledgement on the HTTP response to all sequence and `AckRequested` messages.</span></span>  
  
#### <a name="closesequence-exchange"></a><span data-ttu-id="a38a8-263">Scambio CloseSequence</span><span class="sxs-lookup"><span data-stu-id="a38a8-263">CloseSequence Exchange</span></span>  
 <span data-ttu-id="a38a8-264">L'iniziatore WCF trasmette una `CloseSequence` dei messaggi su una richiesta HTTP e attende la `CreateSequenceResponse` messaggio sulla risposta HTTP.</span><span class="sxs-lookup"><span data-stu-id="a38a8-264">The WCF Initiator transmits a `CloseSequence` message on an HTTP request and expects the `CreateSequenceResponse` message on the HTTP response.</span></span> <span data-ttu-id="a38a8-265">Il risponditore WCF trasmette il `CloseSequenceResponse` messaggio sulla risposta HTTP.</span><span class="sxs-lookup"><span data-stu-id="a38a8-265">The WCF Responder transmits the `CloseSequenceResponse` message on the HTTP response.</span></span>  
  
#### <a name="terminatesequence-exchange"></a><span data-ttu-id="a38a8-266">Scambio TerminateSequence</span><span class="sxs-lookup"><span data-stu-id="a38a8-266">TerminateSequence Exchange</span></span>  
 <span data-ttu-id="a38a8-267">L'iniziatore WCF trasmette una `TerminateSequence` dei messaggi su una richiesta HTTP e attende la `TerminateSequenceResponse` messaggio sulla risposta HTTP.</span><span class="sxs-lookup"><span data-stu-id="a38a8-267">The WCF Initiator transmits a `TerminateSequence` message on an HTTP request and expects the `TerminateSequenceResponse` message on the HTTP response.</span></span> <span data-ttu-id="a38a8-268">Il risponditore WCF trasmette il `TerminateSequenceResponse` messaggio sulla risposta HTTP.</span><span class="sxs-lookup"><span data-stu-id="a38a8-268">The WCF Responder transmits the `TerminateSequenceResponse` message on the HTTP response.</span></span>  
  
### <a name="one-way-addressable-initiator"></a><span data-ttu-id="a38a8-269">Iniziatore unidirezionale, indirizzabile</span><span class="sxs-lookup"><span data-stu-id="a38a8-269">One Way, Addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="a38a8-270">Binding</span><span class="sxs-lookup"><span data-stu-id="a38a8-270">Binding</span></span>  
 <span data-ttu-id="a38a8-271">WCF fornisce un modello di scambio di messaggi unidirezionale utilizzando una sequenza su uno in ingresso e un canale HTTP in uscita.</span><span class="sxs-lookup"><span data-stu-id="a38a8-271">WCF provides a one-way message exchange pattern using one sequence over one inbound and one outbound HTTP channel.</span></span> <span data-ttu-id="a38a8-272">WCF utilizza le richieste HTTP per trasmettere tutti i messaggi.</span><span class="sxs-lookup"><span data-stu-id="a38a8-272">WCF uses the HTTP requests to transmit all messages.</span></span> <span data-ttu-id="a38a8-273">Tutte le risposte HTTP hanno un corpo vuoto e un codice di stato HTTP 202.</span><span class="sxs-lookup"><span data-stu-id="a38a8-273">All HTTP responses have an empty body and HTTP 202 status code.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="a38a8-274">Scambio CreateSequence</span><span class="sxs-lookup"><span data-stu-id="a38a8-274">CreateSequence Exchange</span></span>  
 <span data-ttu-id="a38a8-275">L'iniziatore WCF trasmette una `CreateSequence` senza alcun messaggio `Offer` elemento su una richiesta HTTP.</span><span class="sxs-lookup"><span data-stu-id="a38a8-275">The WCF Initiator transmits a `CreateSequence` message with no `Offer` element on an HTTP request.</span></span> <span data-ttu-id="a38a8-276">Il risponditore WCF crea una sequenza e trasmette il `CreateSequenceResponse` senza alcun messaggio `Accept` elemento su una richiesta HTTP.</span><span class="sxs-lookup"><span data-stu-id="a38a8-276">The WCF Responder creates a sequence and transmits the `CreateSequenceResponse` message with no `Accept` element on an HTTP request.</span></span>  
  
### <a name="duplex-addressable-initiator"></a><span data-ttu-id="a38a8-277">Iniziatore duplex, indirizzabile</span><span class="sxs-lookup"><span data-stu-id="a38a8-277">Duplex, Addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="a38a8-278">Binding</span><span class="sxs-lookup"><span data-stu-id="a38a8-278">Binding</span></span>  
 <span data-ttu-id="a38a8-279">WCF fornisce un modello di scambio di messaggi bidirezionale completamente asincrono utilizzando due sequenze su un in ingresso e un canale HTTP in uscita.</span><span class="sxs-lookup"><span data-stu-id="a38a8-279">WCF provides a fully-asynchronous, two-way message exchange pattern using two sequences over one inbound and one outbound HTTP channel.</span></span> <span data-ttu-id="a38a8-280">Questo modello di scambio può essere combinato con il modello di scambio di messaggi dell'iniziatore `Request/Reply`, `Addressable` in modo limitato.</span><span class="sxs-lookup"><span data-stu-id="a38a8-280">This message exchange pattern can be mixed with the `Request/Reply`, `Addressable` Initiator message exchange pattern in a limited way.</span></span> <span data-ttu-id="a38a8-281">WCF utilizza le richieste HTTP per trasmettere tutti i messaggi.</span><span class="sxs-lookup"><span data-stu-id="a38a8-281">WCF uses HTTP requests to transmit all messages.</span></span> <span data-ttu-id="a38a8-282">Tutte le risposte HTTP hanno un corpo vuoto e un codice di stato HTTP 202.</span><span class="sxs-lookup"><span data-stu-id="a38a8-282">All HTTP responses have an empty body and HTTP 202 status code.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="a38a8-283">Scambio CreateSequence</span><span class="sxs-lookup"><span data-stu-id="a38a8-283">CreateSequence Exchange</span></span>  
 <span data-ttu-id="a38a8-284">L'iniziatore WCF trasmette una `CreateSequence` dei messaggi con un `Offer` elemento su una richiesta HTTP.</span><span class="sxs-lookup"><span data-stu-id="a38a8-284">The WCF Initiator transmits a `CreateSequence` message with an `Offer` element on an HTTP request.</span></span> <span data-ttu-id="a38a8-285">Il risponditore WCF garantisce che il `CreateSequence` ha un `Offer` elemento, quindi crea una sequenza e trasmette le `CreateSequenceResponse` dei messaggi con un `Accept` elemento.</span><span class="sxs-lookup"><span data-stu-id="a38a8-285">The WCF Responder ensures that the `CreateSequence` has an `Offer` element, then creates a sequence and transmits the `CreateSequenceResponse` message with an `Accept` element.</span></span>  
  
#### <a name="sequence-lifetime"></a><span data-ttu-id="a38a8-286">Durata della sequenza</span><span class="sxs-lookup"><span data-stu-id="a38a8-286">Sequence Lifetime</span></span>  
 <span data-ttu-id="a38a8-287">WCF tratta le due sequenze come una sessione completamente duplex.</span><span class="sxs-lookup"><span data-stu-id="a38a8-287">WCF treats the two sequences as one fully-duplex session.</span></span>  
  
 <span data-ttu-id="a38a8-288">Dopo la generazione di un errore che origina errori in un'unica sequenza, WCF si aspetta che l'endpoint crei errori in entrambe le sequenze.</span><span class="sxs-lookup"><span data-stu-id="a38a8-288">Upon generating a fault that faults one sequence, WCF expects the remote endpoint to fault both sequences.</span></span> <span data-ttu-id="a38a8-289">Dopo la lettura di un errore che origina errori in un'unica sequenza, WCF genera un errore per entrambe le sequenze.</span><span class="sxs-lookup"><span data-stu-id="a38a8-289">Upon reading a fault that faults one sequence, WCF faults both sequences.</span></span>  
  
 <span data-ttu-id="a38a8-290">WCF è possibile chiudere la sequenza in uscita e continuare a elaborare i messaggi sulla sua sequenza in ingresso.</span><span class="sxs-lookup"><span data-stu-id="a38a8-290">WCF can close its outbound sequence and continue to process messages on its inbound sequence.</span></span> <span data-ttu-id="a38a8-291">Al contrario, WCF può elaborare la chiusura della sequenza in ingresso e continuare a inviare messaggi sulla sua sequenza in uscita.</span><span class="sxs-lookup"><span data-stu-id="a38a8-291">Conversely, WCF can process the close of the inbound sequence and continue to send messages on its outbound sequence.</span></span>  
  
### <a name="request-reply-and-one-way-non-addressable-initiator"></a><span data-ttu-id="a38a8-292">Iniziatore request/reply e unidirezionale, non indirizzabile</span><span class="sxs-lookup"><span data-stu-id="a38a8-292">Request-Reply and One-Way, Non-Addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="a38a8-293">Binding</span><span class="sxs-lookup"><span data-stu-id="a38a8-293">Binding</span></span>  
 <span data-ttu-id="a38a8-294">WCF fornisce unidirezionale e modello di scambio di messaggi request / reply utilizzando due sequenze su un canale HTTP.</span><span class="sxs-lookup"><span data-stu-id="a38a8-294">WCF provides a one-way and request-reply message exchange pattern using two sequences over one HTTP channel.</span></span> <span data-ttu-id="a38a8-295">WCF utilizza le richieste HTTP per trasmettere tutti i messaggi dall'iniziatore alle risposte del risponditore e di HTTP per trasmettere tutti i messaggi dal risponditore all'iniziatore.</span><span class="sxs-lookup"><span data-stu-id="a38a8-295">WCF uses HTTP requests to transmit all messages from the Initiator to the Responder and HTTP responses to transmit all messages from the Responder to the Initiator.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="a38a8-296">Scambio CreateSequence</span><span class="sxs-lookup"><span data-stu-id="a38a8-296">CreateSequence Exchange</span></span>  
 <span data-ttu-id="a38a8-297">L'iniziatore WCF trasmette una `CreateSequence` dei messaggi con un `Offer` elemento su una richiesta HTTP e attende la `CreateSequenceResponse` messaggio sulla risposta HTTP.</span><span class="sxs-lookup"><span data-stu-id="a38a8-297">The WCF Initiator transmits a `CreateSequence` message with an `Offer` element on an HTTP request and expects the `CreateSequenceResponse` message on the HTTP response.</span></span> <span data-ttu-id="a38a8-298">Il risponditore WCF crea una sequenza e trasmette il `CreateSequenceResponse` dei messaggi con un `Accept` elemento sulla risposta HTTP.</span><span class="sxs-lookup"><span data-stu-id="a38a8-298">The WCF Responder creates a sequence and transmits the `CreateSequenceResponse` message with an `Accept` element on the HTTP response.</span></span>  
  
#### <a name="one-way-message"></a><span data-ttu-id="a38a8-299">Messaggio unidirezionale</span><span class="sxs-lookup"><span data-stu-id="a38a8-299">One-way Message</span></span>  
 <span data-ttu-id="a38a8-300">Per completare correttamente uno scambio di messaggi unidirezionale, l'iniziatore WCF trasmette un messaggio della sequenza di richiesta sulla richiesta HTTP e riceve un autonomo `SequenceAcknowledgement` messaggio sulla risposta HTTP.</span><span class="sxs-lookup"><span data-stu-id="a38a8-300">To complete a one-way message exchange successfully, the WCF Initiator transmits a request sequence message on the HTTP request and receives a standalone `SequenceAcknowledgement` message on the HTTP response.</span></span> <span data-ttu-id="a38a8-301">`SequenceAcknowledgement` deve riconoscere il messaggio trasmesso.</span><span class="sxs-lookup"><span data-stu-id="a38a8-301">The `SequenceAcknowledgement` must acknowledge the message transmitted.</span></span>  
  
 <span data-ttu-id="a38a8-302">Il risponditore WCF può rispondere alla richiesta con un acknowledgement, un errore o una risposta con un corpo vuoto e un codice di stato HTTP 202.</span><span class="sxs-lookup"><span data-stu-id="a38a8-302">The WCF Responder may reply to the request with an acknowledgement, a fault, or a response with an empty body and HTTP 202 status code.</span></span>  
  
#### <a name="two-way-messages"></a><span data-ttu-id="a38a8-303">Messaggi bidirezionali</span><span class="sxs-lookup"><span data-stu-id="a38a8-303">Two Way Messages</span></span>  
 <span data-ttu-id="a38a8-304">Per completare correttamente un protocollo di scambio di messaggi bidirezionale, l'iniziatore WCF trasmette un messaggio della sequenza di richiesta sulla richiesta HTTP e riceve un messaggio della sequenza di risposta sulla risposta HTTP.</span><span class="sxs-lookup"><span data-stu-id="a38a8-304">To complete a two way message exchange protocol successfully, the WCF Initiator transmits a request sequence message on the HTTP request and receives a reply sequence message on the HTTP response.</span></span> <span data-ttu-id="a38a8-305">La risposta deve contenere un `SequenceAcknowledgement` che riconosce che il messaggio della sequenza di richiesta è stato trasmesso.</span><span class="sxs-lookup"><span data-stu-id="a38a8-305">The response must carry a `SequenceAcknowledgement` acknowledging the request sequence message transmitted.</span></span>  
  
 <span data-ttu-id="a38a8-306">Il risponditore WCF può rispondere alla richiesta con una risposta dell'applicazione, un errore o una risposta con un corpo vuoto e un codice di stato HTTP 202.</span><span class="sxs-lookup"><span data-stu-id="a38a8-306">The WCF Responder may reply to the request with an application reply, a fault or a response with an empty body and HTTP 202 status code.</span></span>  
  
 <span data-ttu-id="a38a8-307">A causa della presenza di messaggi unidirezionali e del tempo delle risposte dell'applicazione, il numero di sequenza del messaggio della sequenza di richiesta e il numero di sequenza del messaggio di risposta non hanno alcuna correlazione.</span><span class="sxs-lookup"><span data-stu-id="a38a8-307">Because of the presence of one-way messages and the timing of application replies, the request sequence message’s sequence number and the response message’s sequence number have no correlation.</span></span>  
  
#### <a name="retrying-replies"></a><span data-ttu-id="a38a8-308">Nuovi tentativi di risposte</span><span class="sxs-lookup"><span data-stu-id="a38a8-308">Retrying Replies</span></span>  
 <span data-ttu-id="a38a8-309">WCF si fonda sulla correlazione request / reply HTTP per la correlazione del protocollo di scambio messaggi bidirezionale.</span><span class="sxs-lookup"><span data-stu-id="a38a8-309">WCF relies on HTTP request-reply correlation for two-way message exchange protocol correlation.</span></span> <span data-ttu-id="a38a8-310">Per questo motivo, l'iniziatore di WCF non smette di tentare un messaggio della sequenza di richiesta quando tale messaggio viene riconosciuto, ma piuttosto quando la risposta HTTP contiene un `SequenceAcknowledgement`, risposta dell'applicazione o un errore.</span><span class="sxs-lookup"><span data-stu-id="a38a8-310">Because of this, the WCF Initiator does not stop retrying a request sequence message when the request sequence message is acknowledged but rather when the HTTP response carries a `SequenceAcknowledgement`, application reply, or fault.</span></span> <span data-ttu-id="a38a8-311">Il risponditore WCF Ritenta le risposte sulla risposta HTTP della richiesta a cui è correlata la risposta.</span><span class="sxs-lookup"><span data-stu-id="a38a8-311">The WCF Responder retries replies on the HTTP response of the request to which the reply is correlated.</span></span>  
  
#### <a name="closesequence-exchange"></a><span data-ttu-id="a38a8-312">Scambio CloseSequence</span><span class="sxs-lookup"><span data-stu-id="a38a8-312">CloseSequence Exchange</span></span>  
 <span data-ttu-id="a38a8-313">Dopo la ricezione di tutti i messaggi della sequenza di risposta e gli acknowledgement per tutti i messaggi di sequenza di richiesta unidirezionale, l'iniziatore WCF trasmette una `CloseSequence` del messaggio per la sequenza di richiesta su una richiesta HTTP e attende la `CloseSequenceResponse` sulla risposta HTTP.</span><span class="sxs-lookup"><span data-stu-id="a38a8-313">After receiving all reply sequence messages and acknowledgements for all one way request sequence messages, the WCF Initiator transmits a `CloseSequence` message for the request sequence on an HTTP request and expects the `CloseSequenceResponse` on the HTTP response.</span></span>  
  
 <span data-ttu-id="a38a8-314">Se la sequenza di richiesta viene chiusa in modo implicito, viene chiusa anche la sequenza di risposta.</span><span class="sxs-lookup"><span data-stu-id="a38a8-314">Closing the request sequence implicitly closes the reply sequence.</span></span> <span data-ttu-id="a38a8-315">Ciò significa che l'iniziatore WCF include finale della sequenza di risposta `SequenceAcknowledgement` nella `CloseSequence` messaggio e la sequenza di risposta non ha un `CloseSequence` exchange.</span><span class="sxs-lookup"><span data-stu-id="a38a8-315">This means the WCF Initiator includes the reply sequence’s Final `SequenceAcknowledgement` on the `CloseSequence` message and the reply sequence does not have a `CloseSequence` exchange.</span></span>  
  
 <span data-ttu-id="a38a8-316">Il risponditore WCF assicura tutte le risposte vengano riconosciute e trasmette il `CloseSequenceResponse` messaggio sulla risposta HTTP.</span><span class="sxs-lookup"><span data-stu-id="a38a8-316">The WCF Responder ensures all replies are acknowledged and transmits the `CloseSequenceResponse` message on the HTTP response.</span></span>  
  
#### <a name="terminatesequence-exchange"></a><span data-ttu-id="a38a8-317">Scambio TerminateSequence</span><span class="sxs-lookup"><span data-stu-id="a38a8-317">TerminateSequence Exchange</span></span>  
 <span data-ttu-id="a38a8-318">Dopo avere ricevuto il `CloseSequenceResponse` messaggio, l'iniziatore WCF trasmette una `TerminateSequence` del messaggio per la sequenza di richiesta su una richiesta HTTP e attende la `TerminateSequenceResponse` sulla risposta HTTP.</span><span class="sxs-lookup"><span data-stu-id="a38a8-318">After receiving the `CloseSequenceResponse` message, the WCF Initiator transmits a `TerminateSequence` message for the request sequence on an HTTP request and expects the `TerminateSequenceResponse` on the HTTP response.</span></span>  
  
 <span data-ttu-id="a38a8-319">Analogamente allo scambio `CloseSequence`, la terminazione della sequenza di richiesta in modo implicito termina la sequenza di risposta.</span><span class="sxs-lookup"><span data-stu-id="a38a8-319">Like the `CloseSequence` exchange, terminating the request sequence implicitly terminates the reply sequence.</span></span> <span data-ttu-id="a38a8-320">Ciò significa che l'iniziatore WCF include finale della sequenza di risposta `SequenceAcknowledgement` nella `TerminateSequence` messaggio e la sequenza di risposta non ha un `TerminateSequence` exchange.</span><span class="sxs-lookup"><span data-stu-id="a38a8-320">This means the WCF Initiator includes the reply sequence’s final `SequenceAcknowledgement` on the `TerminateSequence` message and the reply sequence does not have a `TerminateSequence` exchange.</span></span>  
  
 <span data-ttu-id="a38a8-321">Il risponditore WCF trasmette il `TerminateSequenceResponse` messaggio sulla risposta HTTP.</span><span class="sxs-lookup"><span data-stu-id="a38a8-321">The WCF Responder transmits the `TerminateSequenceResponse` message on the HTTP response.</span></span>  
  
### <a name="requestreply-addressable-initiator"></a><span data-ttu-id="a38a8-322">Iniziatore request/reply, indirizzabile</span><span class="sxs-lookup"><span data-stu-id="a38a8-322">Request/Reply, Addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="a38a8-323">Binding</span><span class="sxs-lookup"><span data-stu-id="a38a8-323">Binding</span></span>  
 <span data-ttu-id="a38a8-324">WCF fornisce un modello di scambio di messaggi request / reply utilizzando due sequenze su un in ingresso e un canale HTTP in uscita.</span><span class="sxs-lookup"><span data-stu-id="a38a8-324">WCF provides a request-reply message exchange pattern using two sequences over one inbound and one outbound HTTP channel.</span></span> <span data-ttu-id="a38a8-325">Questo modello di scambio può essere combinato con il modello di scambio di messaggi dell'iniziatore `Duplex, Addressable` in modo limitato.</span><span class="sxs-lookup"><span data-stu-id="a38a8-325">This message exchange pattern can be mixed with the `Duplex, Addressable` Initiator message exchange pattern in a limited way.</span></span> <span data-ttu-id="a38a8-326">WCF utilizza le richieste HTTP per trasmettere tutti i messaggi.</span><span class="sxs-lookup"><span data-stu-id="a38a8-326">WCF uses the HTTP requests to transmit all messages.</span></span> <span data-ttu-id="a38a8-327">Tutte le risposte HTTP hanno un corpo vuoto e un codice di stato HTTP 202.</span><span class="sxs-lookup"><span data-stu-id="a38a8-327">All HTTP responses have an empty body and HTTP 202 status code.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="a38a8-328">Scambio CreateSequence</span><span class="sxs-lookup"><span data-stu-id="a38a8-328">CreateSequence Exchange</span></span>  
 <span data-ttu-id="a38a8-329">L'iniziatore WCF trasmette una `CreateSequence` dei messaggi con un `Offer` elemento su una richiesta HTTP.</span><span class="sxs-lookup"><span data-stu-id="a38a8-329">The WCF Initiator transmits a `CreateSequence` message with an `Offer` element on an HTTP request.</span></span> <span data-ttu-id="a38a8-330">Il risponditore WCF garantisce che il `CreateSequence` ha un `Offer` elemento, quindi crea una sequenza e trasmette le `CreateSequenceResponse` dei messaggi con un `Accept` elemento.</span><span class="sxs-lookup"><span data-stu-id="a38a8-330">The WCF Responder ensures that the `CreateSequence` has an `Offer` element then creates a sequence and transmits the `CreateSequenceResponse` message with an `Accept` element.</span></span>  
  
#### <a name="requestreply-correlation"></a><span data-ttu-id="a38a8-331">Correlazione request/reply</span><span class="sxs-lookup"><span data-stu-id="a38a8-331">Request/Reply Correlation</span></span>  
 <span data-ttu-id="a38a8-332">Quanto riportato di seguito si applica a tutte le richieste e le risposte correlate:</span><span class="sxs-lookup"><span data-stu-id="a38a8-332">The following applies to all correlated requests and replies:</span></span>  
  
-   <span data-ttu-id="a38a8-333">WCF garantisce tutti applicazione richiesta messaggi presentino un `ReplyTo` riferimento all'endpoint e un `MessageId`.</span><span class="sxs-lookup"><span data-stu-id="a38a8-333">WCF ensures all application request messages bear a `ReplyTo` endpoint reference and a `MessageId`.</span></span>  
  
-   <span data-ttu-id="a38a8-334">WCF si applica il riferimento all'endpoint locale come ogni messaggio di richiesta dell'applicazione `ReplyTo`.</span><span class="sxs-lookup"><span data-stu-id="a38a8-334">WCF applies the local endpoint reference as each application request message’s `ReplyTo`.</span></span> <span data-ttu-id="a38a8-335">Il riferimento dell'endpoint locale è `CreateSequence` del messaggio `ReplyTo` per l'iniziatore e `CreateSequence` del messaggio `To` per il risponditore.</span><span class="sxs-lookup"><span data-stu-id="a38a8-335">The local endpoint reference is the `CreateSequence` message’s `ReplyTo` for the Initiator and the `CreateSequence` message’s `To` for the Responder.</span></span>  
  
-   <span data-ttu-id="a38a8-336">WCF garantisce i messaggi di tale richiesta in ingresso presentino un `MessageId` e un `ReplyTo`.</span><span class="sxs-lookup"><span data-stu-id="a38a8-336">WCF ensures that incoming request messages bear a `MessageId` and a `ReplyTo`.</span></span>  
  
-   <span data-ttu-id="a38a8-337">WCF garantisce la `ReplyTo` URI dei riferimenti endpoint di tutti i messaggi di richiesta dell'applicazione corrisponda al riferimento all'endpoint locale come definito in precedenza.</span><span class="sxs-lookup"><span data-stu-id="a38a8-337">WCF ensures the `ReplyTo` endpoint reference’s URI of all application request messages match the local endpoint reference as defined earlier.</span></span>  
  
-   <span data-ttu-id="a38a8-338">WCF garantisce che tutte le risposte contengano `RelatesTo` e `To` le intestazioni `wsa` tipo le regole di correlazione request/reply.</span><span class="sxs-lookup"><span data-stu-id="a38a8-338">WCF ensures that all replies bear the correct `RelatesTo` and `To` headers following `wsa` request/reply correlation rules.</span></span>
