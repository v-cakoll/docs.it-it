---
title: Protocollo Reliable Messaging versione 1,1
ms.date: 03/30/2017
ms.assetid: 0da47b82-f8eb-42da-8bfe-e56ce7ba6f59
ms.openlocfilehash: 8ff02bc6953ec1e5030dd0b592a352b7e23ab0d6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33496958"
---
# <a name="reliable-messaging-protocol-version-11"></a><span data-ttu-id="c8dcc-102">Protocollo Reliable Messaging versione 1,1</span><span class="sxs-lookup"><span data-stu-id="c8dcc-102">Reliable Messaging Protocol version 1.1</span></span>
<span data-ttu-id="c8dcc-103">In questo argomento vengono illustrati i dettagli di implementazione di Windows Communication Foundation (WCF) per WS-ReliableMessaging protocollo febbraio 2007 (versione 1.1) necessario per l'interoperatività con il trasporto HTTP.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-103">This topic covers Windows Communication Foundation (WCF) implementation details for the WS-ReliableMessaging February 2007 (version 1.1) protocol necessary for interoperation using the HTTP transport.</span></span> <span data-ttu-id="c8dcc-104">WCF segue la specifica WS-ReliableMessaging con i vincoli e i chiarimenti illustrati in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-104">WCF follows the WS-ReliableMessaging specification with the constraints and clarifications explained in this topic.</span></span> <span data-ttu-id="c8dcc-105">Si noti che il protocollo di versione 1.1 di WS-ReliableMessaging viene implementato a partire dal [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c8dcc-105">Note that the WS-ReliableMessaging version 1.1 protocol is implemented starting with the [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)].</span></span>  
  
 <span data-ttu-id="c8dcc-106">Il protocollo WS-ReliableMessaging febbraio 2007 protocollo è implementato in WCF per il <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-106">The WS-ReliableMessaging February 2007 protocol is implemented in WCF by the <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>.</span></span>  
  
 <span data-ttu-id="c8dcc-107">Per comodità, nell'argomento vengono utilizzati i ruoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="c8dcc-107">For convenience, the topic uses the following roles:</span></span>  
  
-   <span data-ttu-id="c8dcc-108">Iniziatore: il client che inizia la creazione della sequenza di WS-Reliable Message.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-108">Initiator: The client that initiates WS-Reliable Message sequence creation.</span></span>  
  
-   <span data-ttu-id="c8dcc-109">Risponditore: il servizio che riceve le richieste dell'iniziatore.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-109">Responder: The service that receives the initiator's requests.</span></span>  
  
 <span data-ttu-id="c8dcc-110">In questo documento vengono utilizzati i prefissi e gli spazi dei nomi riportati nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-110">This document uses the prefixes and namespaces in the following table.</span></span>  
  
|<span data-ttu-id="c8dcc-111">Prefisso</span><span class="sxs-lookup"><span data-stu-id="c8dcc-111">Prefix</span></span>|<span data-ttu-id="c8dcc-112">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="c8dcc-112">Namespace</span></span>|  
|-|-|  
|<span data-ttu-id="c8dcc-113">wsrm</span><span class="sxs-lookup"><span data-stu-id="c8dcc-113">wsrm</span></span>|http://docs.oasis-open.org/ws-rx/wsrm/200702|  
|<span data-ttu-id="c8dcc-114">netrm</span><span class="sxs-lookup"><span data-stu-id="c8dcc-114">netrm</span></span>|http://schemas.microsoft.com/ws/2006/05/rm|  
|<span data-ttu-id="c8dcc-115">s</span><span class="sxs-lookup"><span data-stu-id="c8dcc-115">s</span></span>|http://www.w3.org/2003/05/soap-envelope|  
|<span data-ttu-id="c8dcc-116">wsa</span><span class="sxs-lookup"><span data-stu-id="c8dcc-116">wsa</span></span>|http://schemas.xmlsoap.org/ws/2005/08/addressing|  
|<span data-ttu-id="c8dcc-117">wsse</span><span class="sxs-lookup"><span data-stu-id="c8dcc-117">wsse</span></span>|http://docs.oasis-open.org/wss/2004/01/oasis-200401-wssecurity-secext-1.0.xsd|  
|<span data-ttu-id="c8dcc-118">wsrmp</span><span class="sxs-lookup"><span data-stu-id="c8dcc-118">wsrmp</span></span>|http://docs.oasis-open.org/ws-rx/wsrmp/200702|  
|<span data-ttu-id="c8dcc-119">netrmp</span><span class="sxs-lookup"><span data-stu-id="c8dcc-119">netrmp</span></span>|http://schemas.microsoft.com/ws-rx/wsrmp/200702|  
|<span data-ttu-id="c8dcc-120">wsp</span><span class="sxs-lookup"><span data-stu-id="c8dcc-120">wsp</span></span>|<span data-ttu-id="c8dcc-121">(WS-Policy 1.2 o WS-Policy 1.5)</span><span class="sxs-lookup"><span data-stu-id="c8dcc-121">(Either WS-Policy 1.2 or WS-Policy 1.5)</span></span>|  
  
## <a name="messaging"></a><span data-ttu-id="c8dcc-122">Messaggistica</span><span class="sxs-lookup"><span data-stu-id="c8dcc-122">Messaging</span></span>  
  
### <a name="sequence-creation"></a><span data-ttu-id="c8dcc-123">Creazione sequenza</span><span class="sxs-lookup"><span data-stu-id="c8dcc-123">Sequence Creation</span></span>  
 <span data-ttu-id="c8dcc-124">Implementa WCF `CreateSequence` e `CreateSequenceResponse` di sequenza dei messaggi per stabilire una messaggistica affidabile.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-124">WCF implements `CreateSequence` and `CreateSequenceResponse` messages to establish a reliable messaging sequence.</span></span> <span data-ttu-id="c8dcc-125">Si applicano i vincoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="c8dcc-125">The following constraints apply:</span></span>  
  
-   <span data-ttu-id="c8dcc-126">B1101: L'iniziatore WCF utilizza lo stesso riferimento dell'endpoint come le `CreateSequence` del messaggio `ReplyTo`, `AcksTo` e `Offer/Endpoint`.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-126">B1101: The WCF Initiator uses the same endpoint reference as the `CreateSequence` message’s `ReplyTo`, `AcksTo` and `Offer/Endpoint`.</span></span>  
  
-   <span data-ttu-id="c8dcc-127">R1102: i riferimenti degli endpoint `AcksTo`, `ReplyTo` e `Offer/Endpoint` nel messaggio `CreateSequence` devono avere valori di indirizzo con rappresentazioni di stringa identiche in modo che corrispondano all'ottetto.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-127">R1102: The `AcksTo`, `ReplyTo` and `Offer/Endpoint` endpoint references in the `CreateSequence` message must have address values with identical string representations such that they match the octet-wise.</span></span>  
  
    -   <span data-ttu-id="c8dcc-128">Il risponditore WCF verifica che le parti URI del `AcksTo`, `ReplyTo` e `Endpoint` i riferimenti all'endpoint sono identiche prima di creare una sequenza.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-128">The WCF Responder verifies that the URI portion of the `AcksTo`, `ReplyTo` and `Endpoint` endpoint references are identical before creating a sequence.</span></span>  
  
-   <span data-ttu-id="c8dcc-129">R1103: i riferimenti degli endpoint `AcksTo`, `ReplyTo` e `Offer/Endpoint` nel messaggio `CreateSequence` devono avere lo stesso set di parametri di riferimento.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-129">R1103: The `AcksTo`, `ReplyTo` and `Offer/Endpoint` endpoint references in the `CreateSequence` message should have the same set of reference parameters.</span></span>  
  
    -   <span data-ttu-id="c8dcc-130">WCF non impone, ma presuppone che fanno riferimento a parametri del `AcksTo`, `ReplyTo` e `Offer/Endpoint` fa riferimento a endpoint in `CreateSequence` siano identici e utilizza i parametri di riferimento dal `ReplyTo` riferimento dell'endpoint per acknowledgement e messaggi in sequenza opposta.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-130">WCF does not enforce, but assumes that reference parameters of the `AcksTo`, `ReplyTo` and `Offer/Endpoint` endpoint references on `CreateSequence` are identical and uses reference parameters from the `ReplyTo` endpoint reference for acknowledgements and converse sequence messages.</span></span>  
  
-   <span data-ttu-id="c8dcc-131">B1104: L'iniziatore WCF non genera facoltativo `Expires` oppure `Offer/Expires` elemento il `CreateSequence` messaggio.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-131">B1104: The WCF Initiator does not generate the optional `Expires` or `Offer/Expires` element in the `CreateSequence` message.</span></span>  
  
-   <span data-ttu-id="c8dcc-132">B1105: Quando si accede al `CreateSequence` messaggio, il risponditore WCF utilizza il `Expires` valore nel `CreateSequence` come elemento il `Expires` valore il `CreateSequenceResponse` elemento.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-132">B1105: When accessing the `CreateSequence` message, the WCF Responder uses the `Expires` value in the `CreateSequence` element as the `Expires` value in the `CreateSequenceResponse` element.</span></span> <span data-ttu-id="c8dcc-133">In caso contrario, il risponditore WCF legge e ignora il `Expires` e `Offer/Expires` valori.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-133">Otherwise, the WCF Responder reads and ignores the `Expires` and `Offer/Expires` values.</span></span>  
  
-   <span data-ttu-id="c8dcc-134">B1106: Quando si accede ai `CreateSequenceResponse` messaggio, l'iniziatore WCF legge facoltativo `Expires` valore ma non verranno utilizzate.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-134">B1106: When accessing the `CreateSequenceResponse` message, the WCF Initiator reads the optional `Expires` value but does not use it.</span></span>  
  
-   <span data-ttu-id="c8dcc-135">B1107: L'iniziatore WCF e il risponditore genera sempre l'opzione facoltativa `IncompleteSequenceBehavior` elemento il `CreateSequence/Offer` e `CreateSequenceResponse` elementi.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-135">B1107: The WCF Initiator and Responder always generate the optional `IncompleteSequenceBehavior` element in the `CreateSequence/Offer` and `CreateSequenceResponse` elements.</span></span>  
  
-   <span data-ttu-id="c8dcc-136">B1108: WCF Usa solo il `DiscardFollowingFirstGap` e `NoDiscard` i valori di `IncompleteSequenceBehavior` elemento.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-136">B1108: WCF uses only the `DiscardFollowingFirstGap` and `NoDiscard` values in the `IncompleteSequenceBehavior` element.</span></span>  
  
    -   <span data-ttu-id="c8dcc-137">WS-ReliableMessaging utilizza il meccanismo `Offer` per stabilire le due sequenze correlate opposte che formano una sessione.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-137">WS-ReliableMessaging utilizes the `Offer` mechanism to establish the two converse correlated sequences that form a session.</span></span>  
  
-   <span data-ttu-id="c8dcc-138">B1109: Se `CreateSequence` contiene un `Offer` elemento, il risponditore WCF unidirezionale respinge la sequenza offerta rispondendo con un `CreateSequenceResponse` senza un `Accept` elemento.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-138">B1109: If `CreateSequence` contains an `Offer` element, the one way WCF Responder rejects the offered sequence by responding with a `CreateSequenceResponse` without an `Accept` element.</span></span>  
  
-   <span data-ttu-id="c8dcc-139">B1110: Se un risponditore Reliable Messaging respinge la sequenza offerta, l'iniziatore WCF si verifica un errore nella sequenza appena stabilita.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-139">B1110: If a Reliable Messaging Responder rejects the offered sequence, the WCF Initiator faults the newly established sequence.</span></span>  
  
-   <span data-ttu-id="c8dcc-140">B1111: Se `CreateSequence` non contiene un `Offer` elemento, il risponditore bidirezionale di WCF respinge la sequenza offerta rispondendo con un `CreateSequenceRefused` fault.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-140">B1111: If `CreateSequence` does not contain an `Offer` element, the two-way WCF Responder rejects the offered sequence by responding with a `CreateSequenceRefused` fault.</span></span>  
  
-   <span data-ttu-id="c8dcc-141">R1112: quando vengono stabilite due sequenze opposte utilizzando il meccanismo `Offer`, la proprietà `[address]` del riferimento dell'endpoint `CreateSequenceResponse/Accept/AcksTo` deve corrispondere all'URI di destinazione del messaggio `CreateSequence`, byte per byte.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-141">R1112: When two converse sequences are established using the `Offer` mechanism, the `[address]` property of the `CreateSequenceResponse/Accept/AcksTo` endpoint reference must match the destination URI of the `CreateSequence` message byte for byte.</span></span>  
  
-   <span data-ttu-id="c8dcc-142">R1113: quando vengono stabilite due sequenze opposte utilizzando il meccanismo `Offer`, tutti i messaggi su entrambe le sequenze dall'iniziatore al risponditore devono essere inviati allo stesso riferimento dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-142">R1113: When two converse sequences are established using the `Offer` mechanism, all messages on both sequences flowing from the Initiator to the Responder must be sent to the same endpoint reference.</span></span>  
  
 <span data-ttu-id="c8dcc-143">WCF utilizza WS-ReliableMessaging per stabilire sessioni affidabili tra l'iniziatore e il risponditore.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-143">WCF uses WS-ReliableMessaging to establish reliable sessions between the Initiator and the Responder.</span></span> <span data-ttu-id="c8dcc-144">L'implementazione WCF WS-ReliableMessaging offre una sessione affidabile per unidirezionali, request/reply e full duplex modelli di messaggistica.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-144">The WCF WS-ReliableMessaging implementation provides a reliable session for one-way, request-reply and full duplex messaging patterns.</span></span> <span data-ttu-id="c8dcc-145">Il meccanismo `Offer` di WS-Reliable Messaging in `CreateSequence` e `CreateSequenceResponse` consente di stabilire due sequenze opposte correlate e fornisce un protocollo della sessione idoneo per tutti gli endpoint del messaggio.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-145">The WS-ReliableMessaging `Offer` mechanism on `CreateSequence` and `CreateSequenceResponse` lets you establish two correlated converse sequences and provides a session protocol that is suitable for all message endpoints.</span></span> <span data-ttu-id="c8dcc-146">Poiché WCF fornisce una garanzia di sicurezza per tale sessione, inclusa la protezione end-to-end per l'integrità della sessione, è consigliabile assicurarsi che i messaggi destinati alla stessa parte arrivino alla stessa destinazione.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-146">Because WCF provides a security guarantee for such a session including end-to-end protection for session integrity, it is practical to ensure that messages intended for the same party arrive at the same destination.</span></span> <span data-ttu-id="c8dcc-147">Ciò consente anche il "piggy-backing" degli acknowledgement della sequenza sui messaggi dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-147">This also allows "piggy-backing" of sequence acknowledgements on application messages.</span></span> <span data-ttu-id="c8dcc-148">Pertanto, si applicano i vincoli R1102 R1112 e R1113 a WCF.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-148">Therefore, constraints R1102, R1112, and R1113 apply to WCF.</span></span>  
  
 <span data-ttu-id="c8dcc-149">Esempio di un messaggio `CreateSequence`.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-149">An example of a `CreateSequence` message.</span></span>  
  
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
  
 <span data-ttu-id="c8dcc-150">Esempio di un messaggio `CreateSequenceResponse`.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-150">An example of a `CreateSequenceResponse` message.</span></span>  
  
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
  
### <a name="closing-a-sequence"></a><span data-ttu-id="c8dcc-151">Chiusura di una sequenza</span><span class="sxs-lookup"><span data-stu-id="c8dcc-151">Closing a Sequence</span></span>  
 <span data-ttu-id="c8dcc-152">WCF Usa il `CloseSequence` e `CloseSequenceResponse` messaggi per un arresto iniziato dall'origine di Reliable Messaging.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-152">WCF uses the `CloseSequence` and `CloseSequenceResponse` messages for a Reliable Messaging source-initiated shutdown.</span></span> <span data-ttu-id="c8dcc-153">La destinazione di Reliable Messaging di WCF non inizia l'arresto e l'origine di Reliable Messaging di WCF non supporta un arresto iniziata dalla destinazione di Reliable Messaging.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-153">The WCF Reliable Messaging destination does not initiate shutdown and the WCF Reliable Messaging source does not support a Reliable Messaging destination-initiated shutdown.</span></span> <span data-ttu-id="c8dcc-154">Si applicano i vincoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="c8dcc-154">The following constraints apply:</span></span>  
  
-   <span data-ttu-id="c8dcc-155">B1201: L'origine di Reliable Messaging di WCF invia sempre un `CloseSequence` messaggio per arrestare la sequenza.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-155">B1201: The WCF Reliable Messaging source always sends a `CloseSequence` message to shut down the sequence.</span></span>  
  
-   <span data-ttu-id="c8dcc-156">B1202: l'origine di Reliable Messaging attende l'acknowledgment dell'intera serie di messaggi della sequenza prima di inviare il messaggio `CloseSequence`.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-156">B1202: The Reliable Messaging source waits for acknowledgement of the full range of sequence messages before sending the `CloseSequence` message.</span></span>  
  
-   <span data-ttu-id="c8dcc-157">B1203: l'origine di Reliable Messaging include sempre l'elemento facoltativo `LastMsgNumber`. Non lo include se la sequenza non contiene messaggi.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-157">B1203: The Reliable Messaging source always includes the optional `LastMsgNumber` element unless the sequence does not contain messages.</span></span>  
  
-   <span data-ttu-id="c8dcc-158">R1204: la destinazione di Reliable Messaging non deve iniziare l'arresto inviando un messaggio `CloseSequence`.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-158">R1204: The Reliable Messaging destination must not initiate shutdown by sending a `CloseSequence` message.</span></span>  
  
-   <span data-ttu-id="c8dcc-159">B1205: al ricevimento un `CloseSequence` messaggio, l'origine di Reliable Messaging di WCF considera la sequenza incompleta e invia un errore.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-159">B1205: Upon receiving a `CloseSequence` message, the WCF Reliable Messaging source considers the sequence incomplete and sends a fault.</span></span>  
  
 <span data-ttu-id="c8dcc-160">Esempio di un messaggio `CloseSequence`.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-160">An example of a `CloseSequence` message.</span></span>  
  
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
  
### <a name="sequence-termination"></a><span data-ttu-id="c8dcc-161">Terminazione della sequenza</span><span class="sxs-lookup"><span data-stu-id="c8dcc-161">Sequence Termination</span></span>  
 <span data-ttu-id="c8dcc-162">WCF Usa principalmente il `TerminateSequence/TerminateSequenceResponse` handshake dopo aver completato il `CloseSequence/CloseSequenceResponse` handshake.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-162">WCF primarily uses the `TerminateSequence/TerminateSequenceResponse` handshake after completing the `CloseSequence/CloseSequenceResponse` handshake.</span></span> <span data-ttu-id="c8dcc-163">La destinazione di Reliable Messaging di WCF non avviare la terminazione e l'origine di Reliable Messaging non supporta una terminazione iniziata dalla destinazione di Reliable Messaging.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-163">The WCF Reliable Messaging destination does not initiate termination and the Reliable Messaging source does not support a Reliable Messaging destination-initiated termination.</span></span> <span data-ttu-id="c8dcc-164">Si applicano i vincoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="c8dcc-164">The following constraints apply:</span></span>  
  
-   <span data-ttu-id="c8dcc-165">B1301: L'iniziatore WCF invia solo la `TerminateSequence` messaggio dopo il completamento dei `CloseSequence/CloseSequenceResponse` handshake.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-165">B1301: The WCF Initiator only sends the `TerminateSequence` message after the successful completion of the `CloseSequence/CloseSequenceResponse` handshake.</span></span>  
  
-   <span data-ttu-id="c8dcc-166">R1302: WCF consente di verificare che il `LastMsgNumber` elemento sia coerenza in tutti `CloseSequence` e `TerminateSequence` i messaggi per una sequenza specificata.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-166">R1302: WCF validates that the `LastMsgNumber` element is consistent across all `CloseSequence` and `TerminateSequence` messages for a given sequence.</span></span> <span data-ttu-id="c8dcc-167">Ciò significa che `LastMsgNumber` o non è presente in tutti i messaggi `CloseSequence` e `TerminateSequence`, o è presente e identico in tutti i messaggi `CloseSequence` e `TerminateSequence`.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-167">This means that `LastMsgNumber` is either not present on all `CloseSequence` and `TerminateSequence` messages, or it is present and identical on all `CloseSequence` and `TerminateSequence` messages.</span></span>  
  
-   <span data-ttu-id="c8dcc-168">B1303: al ricevimento di un messaggio `TerminateSequence` dopo l'handshake `CloseSequence/CloseSequenceResponse`, la destinazione di Reliable Messaging risponde con un messaggio `TerminateSequenceResponse`.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-168">B1303: When receiving a `TerminateSequence` message after the `CloseSequence/CloseSequenceResponse` handshake, the Reliable Messaging destination responds with a `TerminateSequenceResponse` message.</span></span> <span data-ttu-id="c8dcc-169">Poiché l'origine di Reliable Messaging dispone dell'acknowledgement finale prima dell'invio del messaggio `TerminateSequence`, la destinazione di Reliable Messaging è a conoscenza della fine della sequenza e richiede immediatamente le risorse.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-169">Because the Reliable Messaging source has the final acknowledgement before sending the `TerminateSequence` message, the Reliable Messaging destination knows without doubt that the sequence ends, and reclaims resources immediately.</span></span>  
  
-   <span data-ttu-id="c8dcc-170">B1304: Durante la ricezione di un `TerminateSequence` messaggio nelle versioni precedenti per il `CloseSequence/CloseSequenceResponse` handshake, la destinazione di Reliable Messaging di WCF risponde con un `TerminateSequenceResponse` messaggio.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-170">B1304: When receiving a `TerminateSequence` message prior to the `CloseSequence/CloseSequenceResponse` handshake, the WCF Reliable Messaging destination responds with a `TerminateSequenceResponse` message.</span></span> <span data-ttu-id="c8dcc-171">Se la destinazione di Reliable Messaging stabilisce che non vi sono incoerenze nella sequenza, attende per il periodo di tempo specificato dalla destinazione dell'applicazione prima di richiedere le risorse, per offrire al client la possibilità di ricevere l'acknowledgement finale.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-171">If the Reliable Messaging destination determines that there are no inconsistencies in the sequence, the Reliable Messaging destination waits for an application destination-specified time before reclaiming resources, to allow the client the chance to receive the final acknowledgement.</span></span> <span data-ttu-id="c8dcc-172">In caso contrario, la destinazione di Reliable Messaging richiede immediatamente le risorse e indica alla destinazione dell'applicazione che la sequenza termina in modo dubbio generando l'evento `Faulted`.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-172">Otherwise, the Reliable Messaging destination reclaims resources immediately and indicates to the application destination that the sequence ends with doubt by raising the `Faulted` event.</span></span>  
  
 <span data-ttu-id="c8dcc-173">Esempio di un messaggio `TerminateSequence`.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-173">An example of a `TerminateSequence` message.</span></span>  
  
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
  
### <a name="sequences"></a><span data-ttu-id="c8dcc-174">Sequenze</span><span class="sxs-lookup"><span data-stu-id="c8dcc-174">Sequences</span></span>  
 <span data-ttu-id="c8dcc-175">Di seguito è riportato un elenco di vincoli che si applicano alle sequenze:</span><span class="sxs-lookup"><span data-stu-id="c8dcc-175">The following is a list of constraints that apply to sequences:</span></span>  
  
-   <span data-ttu-id="c8dcc-176">Genera l'errore B1401:WCF e accessi sequenza numeri non superiori a `xs:long`del valore inclusivo massimo, 9223372036854775807.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-176">B1401:WCF generates and accesses sequence numbers no higher than `xs:long`’s maximum inclusive value, 9223372036854775807.</span></span>  
  
 <span data-ttu-id="c8dcc-177">Esempio di intestazione `Sequence`.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-177">An example of a `Sequence` header.</span></span>  
  
```xml  
<wsrm:Sequence s:mustUnderstand="1">  
  <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
  <wsrm:MessageNumber>1</wsrm:MessageNumber>  
</wsrm:Sequence>  
```  
  
### <a name="request-acknowledgement"></a><span data-ttu-id="c8dcc-178">Acknowledgement della richiesta</span><span class="sxs-lookup"><span data-stu-id="c8dcc-178">Request Acknowledgement</span></span>  
 <span data-ttu-id="c8dcc-179">WCF Usa il `AckRequested` intestazione come meccanismo keep-alive.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-179">WCF uses the `AckRequested` header as a keep-alive mechanism.</span></span>  
  
 <span data-ttu-id="c8dcc-180">Esempio di intestazione `AckRequested`.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-180">An example of an `AckRequested` header.</span></span>  
  
```xml  
<wsrm:AckRequested>  
  <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
</wsrm:AckRequested>  
```  
  
### <a name="sequenceacknowledgement"></a><span data-ttu-id="c8dcc-181">SequenceAcknowledgement</span><span class="sxs-lookup"><span data-stu-id="c8dcc-181">SequenceAcknowledgement</span></span>  
 <span data-ttu-id="c8dcc-182">WCF utilizza un meccanismo "piggy-back" per gli acknowledgement di sequenza forniti in WS-Reliable Messaging.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-182">WCF uses a "piggy-back" mechanism for sequence acknowledgements provided in WS-Reliable Messaging.</span></span> <span data-ttu-id="c8dcc-183">Si applicano i vincoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="c8dcc-183">The following constraints apply:</span></span>  
  
-   <span data-ttu-id="c8dcc-184">R1601: Quando due sequenze vengono stabilite opposte utilizzando il `Offer` meccanismo, il `SequenceAcknowledgement` intestazione può essere incluso nei messaggi dell'applicazione trasmesso al destinatario prescelto.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-184">R1601: When two converse sequences are established using the `Offer` mechanism, the `SequenceAcknowledgement` header may be included in any application message transmitted to the intended recipient.</span></span> <span data-ttu-id="c8dcc-185">L'endpoint remoto deve essere in grado di accedere a un'intestazione `SequenceAcknowledgement` sottoposta a piggyback.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-185">The remote endpoint must be able to access a piggybacked `SequenceAcknowledgement` header.</span></span>  
  
-   <span data-ttu-id="c8dcc-186">B1602: WCF non genera `SequenceAcknowledgement` intestazioni contenenti `Nack` elementi.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-186">B1602: WCF does not generate `SequenceAcknowledgement` headers that contain `Nack` elements.</span></span> <span data-ttu-id="c8dcc-187">WCF verifica che ogni `Nack` elemento contiene un numero di sequenza, ma altrimenti ignora il `Nack` elemento e valore.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-187">WCF validates that each `Nack` element contains a sequence number, but otherwise ignores the `Nack` element and value.</span></span>  
  
 <span data-ttu-id="c8dcc-188">Esempio di intestazione `SequenceAcknowledgement`.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-188">An example of a `SequenceAcknowledgement` header.</span></span>  
  
```xml  
<wsrm:SequenceAcknowledgement>  
  <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
  <wsrm:AcknowledgementRange Lower="1" Upper="1"></wsrm:AcknowledgementRange>  
</wsrm:SequenceAcknowledgement>  
```  
  
### <a name="ws-reliablemessaging-faults"></a><span data-ttu-id="c8dcc-189">Errori WS-ReliableMessaging</span><span class="sxs-lookup"><span data-stu-id="c8dcc-189">WS-ReliableMessaging Faults</span></span>  
 <span data-ttu-id="c8dcc-190">Di seguito è un elenco di vincoli che si applicano all'implementazione WCF di errori WS-ReliableMessaging.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-190">The following is a list of constraints that apply to the WCF implementation of WS-ReliableMessaging faults.</span></span> <span data-ttu-id="c8dcc-191">Si applicano i vincoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="c8dcc-191">The following constraints apply:</span></span>  
  
-   <span data-ttu-id="c8dcc-192">B1701: WCF non genera `MessageNumberRollover` errori.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-192">B1701: WCF does not generate `MessageNumberRollover` faults.</span></span>  
  
-   <span data-ttu-id="c8dcc-193">B1702: Su SOAP 1.2 quando l'endpoint del servizio raggiunge il limite di connessione e non è in grado di elaborare nuove connessioni, WCF genera nidificate `CreateSequenceRefused` codice secondario, di errore `netrm:ConnectionLimitReached`, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-193">B1702: Over SOAP 1.2, when the service endpoint reaches its connection limit and cannot process new connections, WCF generates a nested `CreateSequenceRefused` fault subcode, `netrm:ConnectionLimitReached`, as shown in the following example.</span></span>  
  
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
  
### <a name="ws-addressing-faults"></a><span data-ttu-id="c8dcc-194">Errori WS-Addressing</span><span class="sxs-lookup"><span data-stu-id="c8dcc-194">WS-Addressing Faults</span></span>  
 <span data-ttu-id="c8dcc-195">Poiché il protocollo WS-ReliableMessaging utilizza WS-Addressing, l'implementazione WCF WS-Reliable Messaging potrebbe generare e trasmettere errori WS-Addressing.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-195">Because WS-ReliableMessaging uses WS-Addressing, the WCF WS-ReliableMessaging implementation may generate and transmit WS-Addressing faults.</span></span> <span data-ttu-id="c8dcc-196">In questa sezione vengono trattati gli errori WS-Addressing che WCF in modo esplicito genera e trasmette a livello del protocollo WS-ReliableMessaging:</span><span class="sxs-lookup"><span data-stu-id="c8dcc-196">This section covers the WS-Addressing faults that WCF explicitly generates and transmits at the WS-ReliableMessaging layer:</span></span>  
  
-   <span data-ttu-id="c8dcc-197">B1801:WCF genera e trasmette il `Message Addressing Header Required` di errore quando viene soddisfatta una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c8dcc-197">B1801:WCF generates and transmits the `Message Addressing Header Required` fault when one of the following is true:</span></span>  
  
    -   <span data-ttu-id="c8dcc-198">In un messaggio `CreateSequence`, `CloseSequence` o `TerminateSequence` manca un'intestazione `MessageId`.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-198">A `CreateSequence`, `CloseSequence` or `TerminateSequence` message is missing a `MessageId` header.</span></span>  
  
    -   <span data-ttu-id="c8dcc-199">In un messaggio `CreateSequence`, `CloseSequence` o `TerminateSequence` manca un'intestazione `ReplyTo`.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-199">A `CreateSequence`, `CloseSequence` or `TerminateSequence` message is missing a `ReplyTo` header.</span></span>  
  
    -   <span data-ttu-id="c8dcc-200">In un messaggio `CreateSequenceResponse`, `CloseSequenceResponse` o `TerminateSequenceResponse` manca un'intestazione `RelatesTo`.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-200">A `CreateSequenceResponse`, `CloseSequenceResponse`, or `TerminateSequenceResponse` message is missing a `RelatesTo` header.</span></span>  
  
-   <span data-ttu-id="c8dcc-201">B1802:WCF genera e trasmette il `Endpoint Unavailable` errore per indicare nessun endpoint in ascolto in grado di elaborare la sequenza in base all'esame delle intestazioni di indirizzamento nel `CreateSequence` messaggio.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-201">B1802:WCF generates and transmits the `Endpoint Unavailable` fault to indicate there is no endpoint listening that can process the sequence based on examination of the addressing headers in the `CreateSequence` message.</span></span>  
  
## <a name="protocol-composition"></a><span data-ttu-id="c8dcc-202">Composizione del protocollo</span><span class="sxs-lookup"><span data-stu-id="c8dcc-202">Protocol Composition</span></span>  
  
### <a name="composition-with-ws-addressing"></a><span data-ttu-id="c8dcc-203">Composizione con WS-Addressing</span><span class="sxs-lookup"><span data-stu-id="c8dcc-203">Composition with WS-Addressing</span></span>  
 <span data-ttu-id="c8dcc-204">WCF supporta due versioni di WS-Addressing: WS-Addressing 2004/08 [WS-ADDR] e W3C WS-Addressing 1.0 Recommendation [WS-ADDR-CORE] e [WS-ADDR-SOAP].</span><span class="sxs-lookup"><span data-stu-id="c8dcc-204">WCF supports two versions of WS-Addressing: WS-Addressing 2004/08 [WS-ADDR] and W3C WS-Addressing 1.0 Recommendations [WS-ADDR-CORE] and [WS-ADDR-SOAP].</span></span>  
  
 <span data-ttu-id="c8dcc-205">Anche se la specifica WS-ReliableMessaging menziona solo WS-Addressing 2004/08, non limita la versione WS-Addressing da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-205">While the WS-ReliableMessaging specification mentions only WS-Addressing 2004/08, it does not restrict the WS-Addressing version to be used.</span></span> <span data-ttu-id="c8dcc-206">Di seguito è un elenco di vincoli che si applicano a WCF:</span><span class="sxs-lookup"><span data-stu-id="c8dcc-206">The following is a list of constraints that apply to WCF:</span></span>  
  
-   <span data-ttu-id="c8dcc-207">R2101: sia WS-Addressing 2004/08 che WS-Addressing 1.0 possono essere utilizzati con WS-Reliable Messaging.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-207">R2101: Both WS-Addressing 2004/08 and WS-Addressing 1.0 can be used with WS-Reliable Messaging.</span></span>  
  
-   <span data-ttu-id="c8dcc-208">R2102: è necessario utilizzare una sola versione di WS-Addressing in una data sequenza di WS-Reliable Messaging o in una coppia di sequenze opposte correlate tramite il meccanismo `Offer`.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-208">R2102: A single version of WS-Addressing must be used throughout a given WS-ReliableMessaging sequence or a pair of converse sequences correlated by using the `Offer` mechanism.</span></span>  
  
### <a name="composition-with-soap"></a><span data-ttu-id="c8dcc-209">Composizione con SOAP</span><span class="sxs-lookup"><span data-stu-id="c8dcc-209">Composition with SOAP</span></span>  
 <span data-ttu-id="c8dcc-210">WCF supporta l'utilizzo di SOAP 1.1 e SOAP 1.2 con WS-Reliable Messaging.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-210">WCF supports the use of both SOAP 1.1 and SOAP 1.2 with WS-Reliable Messaging.</span></span>  
  
### <a name="composition-with-ws-security-and-ws-secureconversation"></a><span data-ttu-id="c8dcc-211">Composizione con WS-Security e WS-SecureConversation</span><span class="sxs-lookup"><span data-stu-id="c8dcc-211">Composition with WS-Security and WS-SecureConversation</span></span>  
 <span data-ttu-id="c8dcc-212">WCF fornisce la protezione per le sequenze di WS-ReliableMessaging utilizzando sicuri trasporto (HTTPS), composizione con WS-Security e composizione con WS-SecureConversation.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-212">WCF provides protection for WS-ReliableMessaging sequences by using secure Transport (HTTPS), composition with WS-Security, and composition with WS-Secure Conversation.</span></span> <span data-ttu-id="c8dcc-213">Il protocollo WS-Reliable Messaging 1.1, WS-Security 1.1 e il protocollo WS-SecureConversation 1.3 devono essere utilizzati insieme.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-213">The WS-ReliableMessaging 1.1 protocol, WS-Security 1.1 and WS-Secure Conversation 1.3 protocol should be used together.</span></span> <span data-ttu-id="c8dcc-214">Di seguito è un elenco di vincoli che si applicano a WCF:</span><span class="sxs-lookup"><span data-stu-id="c8dcc-214">The following is a list of constraints that apply to WCF:</span></span>  
  
-   <span data-ttu-id="c8dcc-215">R2301: Per proteggere l'integrità di una sequenza di WS-Reliable Messaging oltre all'integrità e riservatezza dei singoli messaggi, WCF, è necessario che è necessario utilizzare WS-Secure Conversation.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-215">R2301: To protect the integrity of a WS-ReliableMessaging sequence in addition to the integrity and confidentiality of individual messages, WCF requires that WS-Secure Conversation must be used.</span></span>  
  
-   <span data-ttu-id="c8dcc-216">R2302:AWS-Secure Conversation deve essere stabilita prima di stabilire le sequenze di WS-ReliableMessaging.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-216">R2302:AWS-Secure Conversation session must be established prior to establishing WS-ReliableMessaging sequence(s).</span></span>  
  
-   <span data-ttu-id="c8dcc-217">R2303: se la durata della sequenza di WS-Reliable Messaging supera la durata della sessione WS-SecureConversation, è necessario rinnovare il `SecurityContextToken` stabilito tramite WS-SecureConversation utilizzando l'associazione WS-Secure Conversation Renewal corrispondente.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-217">R2303: If the WS-ReliableMessaging sequence lifetime exceeds the WS-Secure Conversation session’s lifetime, the `SecurityContextToken` established by using WS-Secure Conversation must be renewed by using the corresponding WS-Secure Conversation Renewal binding.</span></span>  
  
-   <span data-ttu-id="c8dcc-218">B2304:ws-sequenza ReliableMessaging o una coppia di sequenze opposte sono sempre associate a una singola sessione WS-SecureConversation.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-218">B2304:WS-ReliableMessaging sequence or a pair of correlated converse sequences are always bound to a single WS-SecureConversation session.</span></span>  
  
-   <span data-ttu-id="c8dcc-219">R2305: Caso di composizione con WS-SecureConversation, il risponditore WCF richiede che il `CreateSequence` messaggio contiene il `wsse:SecurityTokenReference` elemento e il `wsrm:UsesSequenceSTR` intestazione.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-219">R2305: When composed with WS-Secure Conversation, the WCF responder requires that the `CreateSequence` message contain the `wsse:SecurityTokenReference` element and the `wsrm:UsesSequenceSTR` header.</span></span>  
  
 <span data-ttu-id="c8dcc-220">Esempio di intestazione `UsesSequenceSTR`.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-220">An example of a `UsesSequenceSTR` header.</span></span>  
  
```xml  
<wsrm:UsesSequenceSTR></wsrm:UsesSequenceSTR>  
```  
  
### <a name="composition-with-ssltls-sessions"></a><span data-ttu-id="c8dcc-221">Composizione con sessioni SSL/TLS</span><span class="sxs-lookup"><span data-stu-id="c8dcc-221">Composition with SSL/TLS sessions</span></span>  
 <span data-ttu-id="c8dcc-222">WCF non supporta la composizione con sessioni SSL/TLS:</span><span class="sxs-lookup"><span data-stu-id="c8dcc-222">WCF does not support composition with SSL/TLS sessions:</span></span>  
  
-   <span data-ttu-id="c8dcc-223">B2401: WCF non genera la `wsrm:UsesSequenceSSL` intestazione.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-223">B2401: WCF does not generate the `wsrm:UsesSequenceSSL` header.</span></span>  
  
-   <span data-ttu-id="c8dcc-224">R2402: Un iniziatore Reliable Messaging non deve essere inviato un `CreateSequence` dei messaggi con un `wsrm:UsesSequenceSSL` intestazione a un risponditore WCF.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-224">R2402: A Reliable Messaging Initiator must not send a `CreateSequence` message with a `wsrm:UsesSequenceSSL` header to a WCF Responder.</span></span>  
  
### <a name="composition-with-ws-policy"></a><span data-ttu-id="c8dcc-225">Composizione con WS-Policy</span><span class="sxs-lookup"><span data-stu-id="c8dcc-225">Composition with WS-Policy</span></span>  
 <span data-ttu-id="c8dcc-226">WCF supporta due versioni di WS-Policy: WS-Policy 1.2 e WS-Policy 1.5.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-226">WCF supports two versions of WS-Policy: WS-Policy 1.2 and WS-Policy 1.5.</span></span>  
  
## <a name="ws-reliablemessaging-ws-policy-assertion"></a><span data-ttu-id="c8dcc-227">Asserzione di WS-Policy relativa a WS-ReliableMessaging</span><span class="sxs-lookup"><span data-stu-id="c8dcc-227">WS-ReliableMessaging WS-Policy Assertion</span></span>  
 <span data-ttu-id="c8dcc-228">WCF utilizza l'asserzione di WS-Policy WS-ReliableMessaging `wsrm:RMAssertion` per descrivere le funzionalità degli endpoint.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-228">WCF uses WS-ReliableMessaging WS-Policy Assertion `wsrm:RMAssertion` to describe endpoints capabilities.</span></span> <span data-ttu-id="c8dcc-229">Di seguito è un elenco di vincoli che si applicano a WCF:</span><span class="sxs-lookup"><span data-stu-id="c8dcc-229">The following is a list of constraints that apply to WCF:</span></span>  
  
-   <span data-ttu-id="c8dcc-230">B3001: WCF Allega `wsrmn:RMAssertion` asserzione WS-Policy relativa a `wsdl:binding` elementi.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-230">B3001: WCF attaches `wsrmn:RMAssertion` WS-Policy Assertion to `wsdl:binding` elements.</span></span> <span data-ttu-id="c8dcc-231">WCF supporta i collegamenti agli `wsdl:binding` e `wsdl:port` elementi.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-231">WCF supports both attachments to `wsdl:binding` and `wsdl:port` elements.</span></span>  
  
-   <span data-ttu-id="c8dcc-232">B3002: WCF non lo genera mai il `wsp:Optional` tag.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-232">B3002: WCF never generates the `wsp:Optional` tag.</span></span>  
  
-   <span data-ttu-id="c8dcc-233">B3003: Quando si accede ai `wsrmp:RMAssertion` asserzione di WS-Policy, WCF ignora il `wsp:Optional` tag e considera obbligatorio il criterio WS-RM.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-233">B3003: When accessing the `wsrmp:RMAssertion` WS-Policy Assertion, WCF ignores the `wsp:Optional` tag and treats the WS-RM policy as mandatory.</span></span>  
  
-   <span data-ttu-id="c8dcc-234">R3004: Poiché WCF non esegue la composizione con sessioni SSL/TLS, WCF non accetta il criterio che specifica `wsrmp:SequenceTransportSecurity`.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-234">R3004: Because WCF does not compose with SSL/TLS sessions, WCF does not accept policy that specifies `wsrmp:SequenceTransportSecurity`.</span></span>  
  
-   <span data-ttu-id="c8dcc-235">B3005: WCF genera sempre il `wsrmp:DeliveryAssurance` elemento.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-235">B3005: WCF always generates the `wsrmp:DeliveryAssurance` element.</span></span>  
  
-   <span data-ttu-id="c8dcc-236">B3006: WCF specifica sempre la `wsrmp:ExactlyOnce` garanzia di recapito.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-236">B3006: WCF always specifies the `wsrmp:ExactlyOnce` delivery assurance.</span></span>  
  
-   <span data-ttu-id="c8dcc-237">B3007: WCF genera e legge le proprietà seguenti dell'asserzione WS-ReliableMessaging e fornisce controllo su di essi in WCF`ReliableSessionBindingElement`:</span><span class="sxs-lookup"><span data-stu-id="c8dcc-237">B3007: WCF generates and reads the following properties of the WS-ReliableMessaging assertion and provides control over them on the WCF`ReliableSessionBindingElement`:</span></span>  
  
    -   `netrmp:InactivityTimeout`  
  
    -   `netrmp:AcknowledgementInterval`  
  
     <span data-ttu-id="c8dcc-238">Esempio di `RMAssertion`.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-238">An example of a `RMAssertion`.</span></span>  
  
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
  
## <a name="flow-control-ws-reliablemessaging-extension"></a><span data-ttu-id="c8dcc-239">Estensione di WS-ReliableMessaging per il controllo del flusso</span><span class="sxs-lookup"><span data-stu-id="c8dcc-239">Flow Control WS-ReliableMessaging Extension</span></span>  
 <span data-ttu-id="c8dcc-240">WCF utilizza l'estendibilità di WS-ReliableMessaging per fornire un controllo facoltativo aggiuntivo sul flusso di messaggi di sequenza.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-240">WCF uses WS-ReliableMessaging extensibility to provide optional additional tighter control over sequence message flow.</span></span>  
  
 <span data-ttu-id="c8dcc-241">Controllo di flusso viene abilitato impostando il `ReliableSessionBindingElement`del `FlowControlEnabled``boolean` proprietà `true`.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-241">Flow control is enabled by setting the `ReliableSessionBindingElement`’s `FlowControlEnabled``boolean` property to `true`.</span></span> <span data-ttu-id="c8dcc-242">Di seguito è un elenco di vincoli che si applicano a WCF:</span><span class="sxs-lookup"><span data-stu-id="c8dcc-242">The following is a list of constraints that apply to WCF:</span></span>  
  
-   <span data-ttu-id="c8dcc-243">B4001: Quando è abilitata la messaggistica affidabile flusso di controllo, WCF genera una `netrm:BufferRemaining` elemento nell'estendibilità dell'elemento di `SequenceAcknowledgement` intestazione, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-243">B4001: When Reliable Messaging Flow Control is enabled, WCF generates a `netrm:BufferRemaining` element in the element extensibility of the `SequenceAcknowledgement` header, as shown in the following example.</span></span>  
  
    ```xml  
    <wsrm:SequenceAcknowledgement>  
      <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
      <wsrm:AcknowledgementRange Upper="1" Lower="1"/>             
      <netrm:BufferRemaining>8</netrm:BufferRemaining>  
    </wsrm:SequenceAcknowledgement>  
    ```  
  
-   <span data-ttu-id="c8dcc-244">B4002: Anche quando la messaggistica affidabile flusso di controllo è abilitato, WCF non richiede un `netrm:BufferRemaining` elemento di `SequenceAcknowledgement` intestazione.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-244">B4002: Even when Reliable Messaging Flow Control is enabled, WCF does not require a `netrm:BufferRemaining` element in the `SequenceAcknowledgement` header.</span></span>  
  
-   <span data-ttu-id="c8dcc-245">B4003: Destinazione di WCF Reliable Messaging utilizza `netrm:BufferRemaining` per indicare quanti messaggi nuovi è possibile memorizzare nel buffer.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-245">B4003: WCF Reliable Messaging Destination uses `netrm:BufferRemaining` to indicate how many new messages it can buffer.</span></span>  
  
-   <span data-ttu-id="c8dcc-246">B4004:when Reliable Messaging flusso di controllo è abilitato, l'origine di messaggistica affidabile WCF utilizza il valore di `netrm:BufferRemaining` per la trasmissione dei messaggi di limitazione.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-246">B4004:When Reliable Messaging Flow Control is enabled, the WCF Reliable Messaging Source uses the value of `netrm:BufferRemaining` to throttle message transmission.</span></span>  
  
-   <span data-ttu-id="c8dcc-247">B4005: Genera l'errore WCF `netrm:BufferRemaining` intero i valori compresi tra 0 e 4096 incluso e legge valori integer compresi tra 0 e `xs:int`del `maxInclusive` valore 214748364 incluso.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-247">B4005: WCF generates `netrm:BufferRemaining` integer values between 0 and 4096 inclusive, and reads integer values between 0 and `xs:int`’s `maxInclusive` value 214748364 inclusive.</span></span>  
  
## <a name="message-exchange-patterns"></a><span data-ttu-id="c8dcc-248">Modelli di scambio dei messaggi</span><span class="sxs-lookup"><span data-stu-id="c8dcc-248">Message Exchange Patterns</span></span>  
 <span data-ttu-id="c8dcc-249">Questa sezione descrive il comportamento di WCF quando WS-ReliableMessaging è utilizzato per modelli di scambio di messaggi diversi.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-249">This section describes WCF's behavior when WS-ReliableMessaging is used for different Message Exchange Patterns.</span></span> <span data-ttu-id="c8dcc-250">Per ogni modello di scambio di messaggi, vengono presi in considerazione i due scenari di distribuzione seguenti:</span><span class="sxs-lookup"><span data-stu-id="c8dcc-250">For each Message Exchange Pattern the following two deployments scenarios are considered:</span></span>  
  
-   <span data-ttu-id="c8dcc-251">Iniziatore non indirizzabile: l'iniziatore si trova dietro a un firewall; il risponditore può recapitare messaggi all'iniziatore solo su risposte HTTP.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-251">Non-Addressable Initiator: Initiator is behind a firewall; Responder can deliver messages to the Initiator only on HTTP responses.</span></span>  
  
-   <span data-ttu-id="c8dcc-252">Iniziatore indirizzabile: le richieste HTTP possono essere inviate sia all'iniziatore che al risponditore. In altre parole, è possibile stabilire due connessioni HTTP opposte.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-252">Addressable Initiator: Initiator and Responder both can be sent HTTP requests; in other words, two converse HTTP connections can be established.</span></span>  
  
### <a name="one-way-non-addressable-initiator"></a><span data-ttu-id="c8dcc-253">Iniziatore unidirezionale, non indirizzabile</span><span class="sxs-lookup"><span data-stu-id="c8dcc-253">One-way, Non-addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="c8dcc-254">Binding</span><span class="sxs-lookup"><span data-stu-id="c8dcc-254">Binding</span></span>  
 <span data-ttu-id="c8dcc-255">WCF fornisce un modello di scambio di messaggi unidirezionale utilizza una sola sequenza in un solo canale HTTP.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-255">WCF provides a one-way message exchange pattern using one sequence over one HTTP channel.</span></span> <span data-ttu-id="c8dcc-256">WCF utilizza le richieste HTTP per trasmettere tutti i messaggi dall'iniziatore il risponditore e le risposte HTTP per trasmettere tutti i messaggi dal risponditore all'iniziatore.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-256">WCF uses HTTP requests to transmit all messages from the Initiator to the Responder and HTTP responses to transmit all messages from the Responder to the Initiator.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="c8dcc-257">Scambio CreateSequence</span><span class="sxs-lookup"><span data-stu-id="c8dcc-257">CreateSequence Exchange</span></span>  
 <span data-ttu-id="c8dcc-258">L'iniziatore WCF trasmette un `CreateSequence` messaggio senza alcun `Offer` elemento su una richiesta HTTP e non prevede il `CreateSequenceResponse` messaggio sulla risposta HTTP.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-258">The WCF Initiator transmits a `CreateSequence` message with no `Offer` element on an HTTP request and expects the `CreateSequenceResponse` message on the HTTP response.</span></span> <span data-ttu-id="c8dcc-259">Il risponditore WCF crea una sequenza e trasmette il `CreateSequenceResponse` messaggio senza alcun `Accept` elemento sulla risposta HTTP.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-259">The WCF Responder creates a sequence and transmits the `CreateSequenceResponse` message with no `Accept` element on the HTTP response.</span></span>  
  
#### <a name="sequenceacknowledgement"></a><span data-ttu-id="c8dcc-260">SequenceAcknowledgement</span><span class="sxs-lookup"><span data-stu-id="c8dcc-260">SequenceAcknowledgement</span></span>  
 <span data-ttu-id="c8dcc-261">L'iniziatore WCF elabora gli acknowledgement sulla risposta di tutti i messaggi tranne il `CreateSequence` messaggi e messaggi di errore.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-261">The WCF Initiator processes acknowledgements on the reply of all messages except the `CreateSequence` message and fault messages.</span></span> <span data-ttu-id="c8dcc-262">Il risponditore WCF trasmette sempre un acknowledgement autonomo sulla risposta HTTP a tutte le sequenze e `AckRequested` i messaggi.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-262">The WCF Responder always transmits a stand-alone acknowledgement on the HTTP response to all sequence and `AckRequested` messages.</span></span>  
  
#### <a name="closesequence-exchange"></a><span data-ttu-id="c8dcc-263">Scambio CloseSequence</span><span class="sxs-lookup"><span data-stu-id="c8dcc-263">CloseSequence Exchange</span></span>  
 <span data-ttu-id="c8dcc-264">L'iniziatore WCF trasmette un `CloseSequence` messaggio su una richiesta HTTP e non prevede il `CreateSequenceResponse` messaggio sulla risposta HTTP.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-264">The WCF Initiator transmits a `CloseSequence` message on an HTTP request and expects the `CreateSequenceResponse` message on the HTTP response.</span></span> <span data-ttu-id="c8dcc-265">Il risponditore WCF trasmette il `CloseSequenceResponse` messaggio sulla risposta HTTP.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-265">The WCF Responder transmits the `CloseSequenceResponse` message on the HTTP response.</span></span>  
  
#### <a name="terminatesequence-exchange"></a><span data-ttu-id="c8dcc-266">Scambio TerminateSequence</span><span class="sxs-lookup"><span data-stu-id="c8dcc-266">TerminateSequence Exchange</span></span>  
 <span data-ttu-id="c8dcc-267">L'iniziatore WCF trasmette un `TerminateSequence` messaggio su una richiesta HTTP e non prevede il `TerminateSequenceResponse` messaggio sulla risposta HTTP.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-267">The WCF Initiator transmits a `TerminateSequence` message on an HTTP request and expects the `TerminateSequenceResponse` message on the HTTP response.</span></span> <span data-ttu-id="c8dcc-268">Il risponditore WCF trasmette il `TerminateSequenceResponse` messaggio sulla risposta HTTP.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-268">The WCF Responder transmits the `TerminateSequenceResponse` message on the HTTP response.</span></span>  
  
### <a name="one-way-addressable-initiator"></a><span data-ttu-id="c8dcc-269">Iniziatore unidirezionale, indirizzabile</span><span class="sxs-lookup"><span data-stu-id="c8dcc-269">One Way, Addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="c8dcc-270">Binding</span><span class="sxs-lookup"><span data-stu-id="c8dcc-270">Binding</span></span>  
 <span data-ttu-id="c8dcc-271">WCF fornisce un modello di scambio di messaggi unidirezionale utilizza una sola sequenza su uno in ingresso e un solo canale HTTP in uscita.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-271">WCF provides a one-way message exchange pattern using one sequence over one inbound and one outbound HTTP channel.</span></span> <span data-ttu-id="c8dcc-272">WCF utilizza le richieste HTTP per trasmettere tutti i messaggi.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-272">WCF uses the HTTP requests to transmit all messages.</span></span> <span data-ttu-id="c8dcc-273">Tutte le risposte HTTP hanno un corpo vuoto e un codice di stato HTTP 202.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-273">All HTTP responses have an empty body and HTTP 202 status code.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="c8dcc-274">Scambio CreateSequence</span><span class="sxs-lookup"><span data-stu-id="c8dcc-274">CreateSequence Exchange</span></span>  
 <span data-ttu-id="c8dcc-275">L'iniziatore WCF trasmette un `CreateSequence` messaggio senza alcun `Offer` elemento su una richiesta HTTP.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-275">The WCF Initiator transmits a `CreateSequence` message with no `Offer` element on an HTTP request.</span></span> <span data-ttu-id="c8dcc-276">Il risponditore WCF crea una sequenza e trasmette il `CreateSequenceResponse` messaggio senza alcun `Accept` elemento su una richiesta HTTP.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-276">The WCF Responder creates a sequence and transmits the `CreateSequenceResponse` message with no `Accept` element on an HTTP request.</span></span>  
  
### <a name="duplex-addressable-initiator"></a><span data-ttu-id="c8dcc-277">Iniziatore duplex, indirizzabile</span><span class="sxs-lookup"><span data-stu-id="c8dcc-277">Duplex, Addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="c8dcc-278">Binding</span><span class="sxs-lookup"><span data-stu-id="c8dcc-278">Binding</span></span>  
 <span data-ttu-id="c8dcc-279">WCF fornisce un modello di scambio di messaggi bidirezionale completamente asincrono usando due sequenze su uno in ingresso e un solo canale HTTP in uscita.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-279">WCF provides a fully-asynchronous, two-way message exchange pattern using two sequences over one inbound and one outbound HTTP channel.</span></span> <span data-ttu-id="c8dcc-280">Questo modello di scambio può essere combinato con il modello di scambio di messaggi dell'iniziatore `Request/Reply`, `Addressable` in modo limitato.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-280">This message exchange pattern can be mixed with the `Request/Reply`, `Addressable` Initiator message exchange pattern in a limited way.</span></span> <span data-ttu-id="c8dcc-281">WCF utilizza le richieste HTTP per trasmettere tutti i messaggi.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-281">WCF uses HTTP requests to transmit all messages.</span></span> <span data-ttu-id="c8dcc-282">Tutte le risposte HTTP hanno un corpo vuoto e un codice di stato HTTP 202.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-282">All HTTP responses have an empty body and HTTP 202 status code.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="c8dcc-283">Scambio CreateSequence</span><span class="sxs-lookup"><span data-stu-id="c8dcc-283">CreateSequence Exchange</span></span>  
 <span data-ttu-id="c8dcc-284">L'iniziatore WCF trasmette un `CreateSequence` dei messaggi con un `Offer` elemento su una richiesta HTTP.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-284">The WCF Initiator transmits a `CreateSequence` message with an `Offer` element on an HTTP request.</span></span> <span data-ttu-id="c8dcc-285">Il risponditore WCF assicura che il `CreateSequence` ha un `Offer` elemento, quindi crea una sequenza e trasmette il `CreateSequenceResponse` dei messaggi con un `Accept` elemento.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-285">The WCF Responder ensures that the `CreateSequence` has an `Offer` element, then creates a sequence and transmits the `CreateSequenceResponse` message with an `Accept` element.</span></span>  
  
#### <a name="sequence-lifetime"></a><span data-ttu-id="c8dcc-286">Durata della sequenza</span><span class="sxs-lookup"><span data-stu-id="c8dcc-286">Sequence Lifetime</span></span>  
 <span data-ttu-id="c8dcc-287">WCF tratta le due sequenze come una sessione completamente duplex.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-287">WCF treats the two sequences as one fully-duplex session.</span></span>  
  
 <span data-ttu-id="c8dcc-288">Dopo la generazione di un errore che origina errori in un'unica sequenza, WCF prevede che l'endpoint remoto errori in entrambe le sequenze.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-288">Upon generating a fault that faults one sequence, WCF expects the remote endpoint to fault both sequences.</span></span> <span data-ttu-id="c8dcc-289">Dopo la lettura di un errore che origina errori in un'unica sequenza, WCF si verifica un errore entrambe le sequenze.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-289">Upon reading a fault that faults one sequence, WCF faults both sequences.</span></span>  
  
 <span data-ttu-id="c8dcc-290">WCF è possibile chiudere la relativa sequenza in uscita e continuare a elaborare i messaggi sulla sua sequenza in ingresso.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-290">WCF can close its outbound sequence and continue to process messages on its inbound sequence.</span></span> <span data-ttu-id="c8dcc-291">Al contrario, WCF può elaborare la chiusura della sequenza in ingresso e continuare a inviare i messaggi sulla sua sequenza in uscita.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-291">Conversely, WCF can process the close of the inbound sequence and continue to send messages on its outbound sequence.</span></span>  
  
### <a name="request-reply-and-one-way-non-addressable-initiator"></a><span data-ttu-id="c8dcc-292">Iniziatore request/reply e unidirezionale, non indirizzabile</span><span class="sxs-lookup"><span data-stu-id="c8dcc-292">Request-Reply and One-Way, Non-Addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="c8dcc-293">Binding</span><span class="sxs-lookup"><span data-stu-id="c8dcc-293">Binding</span></span>  
 <span data-ttu-id="c8dcc-294">WCF fornisce unidirezionale e modello di scambio di messaggi request/reply usando due sequenze su un canale HTTP.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-294">WCF provides a one-way and request-reply message exchange pattern using two sequences over one HTTP channel.</span></span> <span data-ttu-id="c8dcc-295">WCF utilizza le richieste HTTP per trasmettere tutti i messaggi dall'iniziatore il risponditore e le risposte HTTP per trasmettere tutti i messaggi dal risponditore all'iniziatore.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-295">WCF uses HTTP requests to transmit all messages from the Initiator to the Responder and HTTP responses to transmit all messages from the Responder to the Initiator.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="c8dcc-296">Scambio CreateSequence</span><span class="sxs-lookup"><span data-stu-id="c8dcc-296">CreateSequence Exchange</span></span>  
 <span data-ttu-id="c8dcc-297">L'iniziatore WCF trasmette un `CreateSequence` dei messaggi con un `Offer` elemento su una richiesta HTTP e non prevede il `CreateSequenceResponse` messaggio sulla risposta HTTP.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-297">The WCF Initiator transmits a `CreateSequence` message with an `Offer` element on an HTTP request and expects the `CreateSequenceResponse` message on the HTTP response.</span></span> <span data-ttu-id="c8dcc-298">Il risponditore WCF crea una sequenza e trasmette il `CreateSequenceResponse` dei messaggi con un `Accept` elemento sulla risposta HTTP.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-298">The WCF Responder creates a sequence and transmits the `CreateSequenceResponse` message with an `Accept` element on the HTTP response.</span></span>  
  
#### <a name="one-way-message"></a><span data-ttu-id="c8dcc-299">Messaggio unidirezionale</span><span class="sxs-lookup"><span data-stu-id="c8dcc-299">One-way Message</span></span>  
 <span data-ttu-id="c8dcc-300">Per completare correttamente uno scambio di messaggi unidirezionale, l'iniziatore WCF trasmette un messaggio di sequenza di richiesta sulla richiesta HTTP e riceve un computer autonomo `SequenceAcknowledgement` messaggio sulla risposta HTTP.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-300">To complete a one-way message exchange successfully, the WCF Initiator transmits a request sequence message on the HTTP request and receives a standalone `SequenceAcknowledgement` message on the HTTP response.</span></span> <span data-ttu-id="c8dcc-301">`SequenceAcknowledgement` deve riconoscere il messaggio trasmesso.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-301">The `SequenceAcknowledgement` must acknowledge the message transmitted.</span></span>  
  
 <span data-ttu-id="c8dcc-302">Il risponditore WCF può rispondere alla richiesta con un acknowledgement, un errore o una risposta con un corpo vuoto e un codice di stato HTTP 202.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-302">The WCF Responder may reply to the request with an acknowledgement, a fault, or a response with an empty body and HTTP 202 status code.</span></span>  
  
#### <a name="two-way-messages"></a><span data-ttu-id="c8dcc-303">Messaggi bidirezionali</span><span class="sxs-lookup"><span data-stu-id="c8dcc-303">Two Way Messages</span></span>  
 <span data-ttu-id="c8dcc-304">Per completare correttamente un protocollo di scambio di messaggi bidirezionale, l'iniziatore WCF trasmette un messaggio della sequenza di richiesta sulla richiesta HTTP e riceve un messaggio della sequenza di risposta sulla risposta HTTP.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-304">To complete a two way message exchange protocol successfully, the WCF Initiator transmits a request sequence message on the HTTP request and receives a reply sequence message on the HTTP response.</span></span> <span data-ttu-id="c8dcc-305">La risposta deve contenere un `SequenceAcknowledgement` che riconosce che il messaggio della sequenza di richiesta è stato trasmesso.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-305">The response must carry a `SequenceAcknowledgement` acknowledging the request sequence message transmitted.</span></span>  
  
 <span data-ttu-id="c8dcc-306">Il risponditore WCF può rispondere alla richiesta con una risposta dell'applicazione, un errore o una risposta con un corpo vuoto e un codice di stato HTTP 202.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-306">The WCF Responder may reply to the request with an application reply, a fault or a response with an empty body and HTTP 202 status code.</span></span>  
  
 <span data-ttu-id="c8dcc-307">A causa della presenza di messaggi unidirezionali e del tempo delle risposte dell'applicazione, il numero di sequenza del messaggio della sequenza di richiesta e il numero di sequenza del messaggio di risposta non hanno alcuna correlazione.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-307">Because of the presence of one-way messages and the timing of application replies, the request sequence message’s sequence number and the response message’s sequence number have no correlation.</span></span>  
  
#### <a name="retrying-replies"></a><span data-ttu-id="c8dcc-308">Nuovi tentativi di risposte</span><span class="sxs-lookup"><span data-stu-id="c8dcc-308">Retrying Replies</span></span>  
 <span data-ttu-id="c8dcc-309">WCF si basa sulla correlazione request/reply HTTP per la correlazione di protocollo di scambio di messaggi bidirezionale.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-309">WCF relies on HTTP request-reply correlation for two-way message exchange protocol correlation.</span></span> <span data-ttu-id="c8dcc-310">Per questo motivo, l'iniziatore WCF smette di tentare un messaggio della sequenza di richiesta quando tale messaggio viene riconosciuto, ma piuttosto quando la risposta HTTP contiene un `SequenceAcknowledgement`, risposta dell'applicazione o un errore.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-310">Because of this, the WCF Initiator does not stop retrying a request sequence message when the request sequence message is acknowledged but rather when the HTTP response carries a `SequenceAcknowledgement`, application reply, or fault.</span></span> <span data-ttu-id="c8dcc-311">Il risponditore WCF Ritenta le risposte sulla risposta HTTP della richiesta a cui è correlata la risposta.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-311">The WCF Responder retries replies on the HTTP response of the request to which the reply is correlated.</span></span>  
  
#### <a name="closesequence-exchange"></a><span data-ttu-id="c8dcc-312">Scambio CloseSequence</span><span class="sxs-lookup"><span data-stu-id="c8dcc-312">CloseSequence Exchange</span></span>  
 <span data-ttu-id="c8dcc-313">Dopo la ricezione di tutti i messaggi di sequenza di risposta e gli acknowledgement per tutti i messaggi di sequenza di richiesta unidirezionali, l'iniziatore WCF trasmette un `CloseSequence` del messaggio per la sequenza di richiesta su una richiesta HTTP e non prevede il `CloseSequenceResponse` sulla risposta HTTP.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-313">After receiving all reply sequence messages and acknowledgements for all one way request sequence messages, the WCF Initiator transmits a `CloseSequence` message for the request sequence on an HTTP request and expects the `CloseSequenceResponse` on the HTTP response.</span></span>  
  
 <span data-ttu-id="c8dcc-314">Se la sequenza di richiesta viene chiusa in modo implicito, viene chiusa anche la sequenza di risposta.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-314">Closing the request sequence implicitly closes the reply sequence.</span></span> <span data-ttu-id="c8dcc-315">Ciò significa che l'iniziatore WCF include finale della sequenza di risposta `SequenceAcknowledgement` nella `CloseSequence` messaggio e la sequenza di risposta non ha un `CloseSequence` exchange.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-315">This means the WCF Initiator includes the reply sequence’s Final `SequenceAcknowledgement` on the `CloseSequence` message and the reply sequence does not have a `CloseSequence` exchange.</span></span>  
  
 <span data-ttu-id="c8dcc-316">Il risponditore WCF assicura tutte le risposte vengano riconosciute e trasmette il `CloseSequenceResponse` messaggio sulla risposta HTTP.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-316">The WCF Responder ensures all replies are acknowledged and transmits the `CloseSequenceResponse` message on the HTTP response.</span></span>  
  
#### <a name="terminatesequence-exchange"></a><span data-ttu-id="c8dcc-317">Scambio TerminateSequence</span><span class="sxs-lookup"><span data-stu-id="c8dcc-317">TerminateSequence Exchange</span></span>  
 <span data-ttu-id="c8dcc-318">Dopo avere ricevuto il `CloseSequenceResponse` messaggio, l'iniziatore WCF trasmette un `TerminateSequence` messaggio per la sequenza di richiesta su una richiesta HTTP e non prevede il `TerminateSequenceResponse` sulla risposta HTTP.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-318">After receiving the `CloseSequenceResponse` message, the WCF Initiator transmits a `TerminateSequence` message for the request sequence on an HTTP request and expects the `TerminateSequenceResponse` on the HTTP response.</span></span>  
  
 <span data-ttu-id="c8dcc-319">Analogamente allo scambio `CloseSequence`, la terminazione della sequenza di richiesta in modo implicito termina la sequenza di risposta.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-319">Like the `CloseSequence` exchange, terminating the request sequence implicitly terminates the reply sequence.</span></span> <span data-ttu-id="c8dcc-320">Ciò significa che l'iniziatore WCF include finale della sequenza di risposta `SequenceAcknowledgement` nella `TerminateSequence` messaggio e la sequenza di risposta non ha un `TerminateSequence` exchange.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-320">This means the WCF Initiator includes the reply sequence’s final `SequenceAcknowledgement` on the `TerminateSequence` message and the reply sequence does not have a `TerminateSequence` exchange.</span></span>  
  
 <span data-ttu-id="c8dcc-321">Il risponditore WCF trasmette il `TerminateSequenceResponse` messaggio sulla risposta HTTP.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-321">The WCF Responder transmits the `TerminateSequenceResponse` message on the HTTP response.</span></span>  
  
### <a name="requestreply-addressable-initiator"></a><span data-ttu-id="c8dcc-322">Iniziatore request/reply, indirizzabile</span><span class="sxs-lookup"><span data-stu-id="c8dcc-322">Request/Reply, Addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="c8dcc-323">Binding</span><span class="sxs-lookup"><span data-stu-id="c8dcc-323">Binding</span></span>  
 <span data-ttu-id="c8dcc-324">WCF fornisce un modello di scambio di messaggi request/reply usando due sequenze su uno in ingresso e un solo canale HTTP in uscita.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-324">WCF provides a request-reply message exchange pattern using two sequences over one inbound and one outbound HTTP channel.</span></span> <span data-ttu-id="c8dcc-325">Questo modello di scambio può essere combinato con il modello di scambio di messaggi dell'iniziatore `Duplex, Addressable` in modo limitato.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-325">This message exchange pattern can be mixed with the `Duplex, Addressable` Initiator message exchange pattern in a limited way.</span></span> <span data-ttu-id="c8dcc-326">WCF utilizza le richieste HTTP per trasmettere tutti i messaggi.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-326">WCF uses the HTTP requests to transmit all messages.</span></span> <span data-ttu-id="c8dcc-327">Tutte le risposte HTTP hanno un corpo vuoto e un codice di stato HTTP 202.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-327">All HTTP responses have an empty body and HTTP 202 status code.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="c8dcc-328">Scambio CreateSequence</span><span class="sxs-lookup"><span data-stu-id="c8dcc-328">CreateSequence Exchange</span></span>  
 <span data-ttu-id="c8dcc-329">L'iniziatore WCF trasmette un `CreateSequence` dei messaggi con un `Offer` elemento su una richiesta HTTP.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-329">The WCF Initiator transmits a `CreateSequence` message with an `Offer` element on an HTTP request.</span></span> <span data-ttu-id="c8dcc-330">Il risponditore WCF assicura che il `CreateSequence` ha un `Offer` elemento quindi crea una sequenza e trasmette il `CreateSequenceResponse` dei messaggi con un `Accept` elemento.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-330">The WCF Responder ensures that the `CreateSequence` has an `Offer` element then creates a sequence and transmits the `CreateSequenceResponse` message with an `Accept` element.</span></span>  
  
#### <a name="requestreply-correlation"></a><span data-ttu-id="c8dcc-331">Correlazione request/reply</span><span class="sxs-lookup"><span data-stu-id="c8dcc-331">Request/Reply Correlation</span></span>  
 <span data-ttu-id="c8dcc-332">Quanto riportato di seguito si applica a tutte le richieste e le risposte correlate:</span><span class="sxs-lookup"><span data-stu-id="c8dcc-332">The following applies to all correlated requests and replies:</span></span>  
  
-   <span data-ttu-id="c8dcc-333">WCF garantisce tendente al tutti i messaggi di richiesta dell'applicazione un `ReplyTo` riferimento dell'endpoint e un `MessageId`.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-333">WCF ensures all application request messages bear a `ReplyTo` endpoint reference and a `MessageId`.</span></span>  
  
-   <span data-ttu-id="c8dcc-334">WCF si applica il riferimento dell'endpoint locale come ogni messaggio di richiesta dell'applicazione `ReplyTo`.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-334">WCF applies the local endpoint reference as each application request message’s `ReplyTo`.</span></span> <span data-ttu-id="c8dcc-335">Il riferimento dell'endpoint locale è `CreateSequence` del messaggio `ReplyTo` per l'iniziatore e `CreateSequence` del messaggio `To` per il risponditore.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-335">The local endpoint reference is the `CreateSequence` message’s `ReplyTo` for the Initiator and the `CreateSequence` message’s `To` for the Responder.</span></span>  
  
-   <span data-ttu-id="c8dcc-336">WCF garantisce i messaggi di tale richiesta in ingresso presentino un `MessageId` e un `ReplyTo`.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-336">WCF ensures that incoming request messages bear a `MessageId` and a `ReplyTo`.</span></span>  
  
-   <span data-ttu-id="c8dcc-337">WCF garantisce la `ReplyTo` URI dei riferimenti endpoint di tutti i messaggi di richiesta dell'applicazione corrisponde al riferimento dell'endpoint locale come definito in precedenza.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-337">WCF ensures the `ReplyTo` endpoint reference’s URI of all application request messages match the local endpoint reference as defined earlier.</span></span>  
  
-   <span data-ttu-id="c8dcc-338">WCF garantisce che tutte le risposte contengano `RelatesTo` e `To` le intestazioni `wsa` tipo le regole di correlazione request/reply.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-338">WCF ensures that all replies bear the correct `RelatesTo` and `To` headers following `wsa` request/reply correlation rules.</span></span>
