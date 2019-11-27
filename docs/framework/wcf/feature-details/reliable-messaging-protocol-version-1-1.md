---
title: Protocollo Reliable Messaging versione 1,1
ms.date: 03/30/2017
ms.assetid: 0da47b82-f8eb-42da-8bfe-e56ce7ba6f59
ms.openlocfilehash: 9320787317131f42c4a82c6114a16fdea87567f4
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283303"
---
# <a name="reliable-messaging-protocol-version-11"></a><span data-ttu-id="7e94f-102">Protocollo Reliable Messaging versione 1,1</span><span class="sxs-lookup"><span data-stu-id="7e94f-102">Reliable Messaging Protocol version 1.1</span></span>

<span data-ttu-id="7e94f-103">In questo argomento vengono illustrati i dettagli di implementazione di Windows Communication Foundation (WCF) per il protocollo WS-ReliableMessaging febbraio 2007 (versione 1,1) necessario per l'interoperatività utilizzando il trasporto HTTP.</span><span class="sxs-lookup"><span data-stu-id="7e94f-103">This topic covers Windows Communication Foundation (WCF) implementation details for the WS-ReliableMessaging February 2007 (version 1.1) protocol necessary for interoperation using the HTTP transport.</span></span> <span data-ttu-id="7e94f-104">WCF segue la specifica WS-ReliableMessaging con i vincoli e i chiarimenti illustrati in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="7e94f-104">WCF follows the WS-ReliableMessaging specification with the constraints and clarifications explained in this topic.</span></span> <span data-ttu-id="7e94f-105">Si noti che il protocollo WS-ReliableMessaging versione 1,1 viene implementato a partire da .NET Framework 3,5.</span><span class="sxs-lookup"><span data-stu-id="7e94f-105">Note that the WS-ReliableMessaging version 1.1 protocol is implemented starting with .NET Framework 3.5.</span></span>

<span data-ttu-id="7e94f-106">Il protocollo WS-ReliableMessaging di febbraio 2007 viene implementato in WCF dalla <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="7e94f-106">The WS-ReliableMessaging February 2007 protocol is implemented in WCF by the <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>.</span></span>

<span data-ttu-id="7e94f-107">Per comodità, nell'argomento vengono utilizzati i ruoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="7e94f-107">For convenience, the topic uses the following roles:</span></span>

- <span data-ttu-id="7e94f-108">Iniziatore: il client che inizia la creazione della sequenza di WS-Reliable Message.</span><span class="sxs-lookup"><span data-stu-id="7e94f-108">Initiator: The client that initiates WS-Reliable Message sequence creation.</span></span>

- <span data-ttu-id="7e94f-109">Risponditore: il servizio che riceve le richieste dell'iniziatore.</span><span class="sxs-lookup"><span data-stu-id="7e94f-109">Responder: The service that receives the initiator's requests.</span></span>

 <span data-ttu-id="7e94f-110">In questo documento vengono utilizzati i prefissi e gli spazi dei nomi riportati nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="7e94f-110">This document uses the prefixes and namespaces in the following table.</span></span>

|<span data-ttu-id="7e94f-111">Prefisso</span><span class="sxs-lookup"><span data-stu-id="7e94f-111">Prefix</span></span>|<span data-ttu-id="7e94f-112">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="7e94f-112">Namespace</span></span>|
|-|-|
|<span data-ttu-id="7e94f-113">wsrm</span><span class="sxs-lookup"><span data-stu-id="7e94f-113">wsrm</span></span>|http://docs.oasis-open.org/ws-rx/wsrm/200702|
|<span data-ttu-id="7e94f-114">netrm</span><span class="sxs-lookup"><span data-stu-id="7e94f-114">netrm</span></span>|http://schemas.microsoft.com/ws/2006/05/rm|
|<span data-ttu-id="7e94f-115">s</span><span class="sxs-lookup"><span data-stu-id="7e94f-115">s</span></span>|http://www.w3.org/2003/05/soap-envelope|
|<span data-ttu-id="7e94f-116">wsa</span><span class="sxs-lookup"><span data-stu-id="7e94f-116">wsa</span></span>|http://schemas.xmlsoap.org/ws/2005/08/addressing|
|<span data-ttu-id="7e94f-117">wsse</span><span class="sxs-lookup"><span data-stu-id="7e94f-117">wsse</span></span>|http://docs.oasis-open.org/wss/2004/01/oasis-200401-wssecurity-secext-1.0.xsd|
|<span data-ttu-id="7e94f-118">wsrmp</span><span class="sxs-lookup"><span data-stu-id="7e94f-118">wsrmp</span></span>|http://docs.oasis-open.org/ws-rx/wsrmp/200702|
|<span data-ttu-id="7e94f-119">netrmp</span><span class="sxs-lookup"><span data-stu-id="7e94f-119">netrmp</span></span>|http://schemas.microsoft.com/ws-rx/wsrmp/200702|
|<span data-ttu-id="7e94f-120">wsp</span><span class="sxs-lookup"><span data-stu-id="7e94f-120">wsp</span></span>|<span data-ttu-id="7e94f-121">(WS-Policy 1.2 o WS-Policy 1.5)</span><span class="sxs-lookup"><span data-stu-id="7e94f-121">(Either WS-Policy 1.2 or WS-Policy 1.5)</span></span>|

## <a name="messaging"></a><span data-ttu-id="7e94f-122">Messaggistica</span><span class="sxs-lookup"><span data-stu-id="7e94f-122">Messaging</span></span>

### <a name="sequence-creation"></a><span data-ttu-id="7e94f-123">Creazione sequenza</span><span class="sxs-lookup"><span data-stu-id="7e94f-123">Sequence Creation</span></span>

<span data-ttu-id="7e94f-124">WCF implementa `CreateSequence` e `CreateSequenceResponse` messaggi per stabilire una sequenza di messaggistica affidabile.</span><span class="sxs-lookup"><span data-stu-id="7e94f-124">WCF implements `CreateSequence` and `CreateSequenceResponse` messages to establish a reliable messaging sequence.</span></span> <span data-ttu-id="7e94f-125">Si applicano i vincoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="7e94f-125">The following constraints apply:</span></span>

- <span data-ttu-id="7e94f-126">B1101: l'iniziatore WCF usa lo stesso riferimento all'endpoint dell'`ReplyTo`, `AcksTo` e `Offer/Endpoint`del messaggio di `CreateSequence`.</span><span class="sxs-lookup"><span data-stu-id="7e94f-126">B1101: The WCF Initiator uses the same endpoint reference as the `CreateSequence` message’s `ReplyTo`, `AcksTo` and `Offer/Endpoint`.</span></span>

- <span data-ttu-id="7e94f-127">R1102: i riferimenti degli endpoint `AcksTo`, `ReplyTo` e `Offer/Endpoint` nel messaggio `CreateSequence` devono avere valori di indirizzo con rappresentazioni di stringa identiche in modo che corrispondano all'ottetto.</span><span class="sxs-lookup"><span data-stu-id="7e94f-127">R1102: The `AcksTo`, `ReplyTo` and `Offer/Endpoint` endpoint references in the `CreateSequence` message must have address values with identical string representations such that they match the octet-wise.</span></span>

  - <span data-ttu-id="7e94f-128">Il risponditore WCF verifica che la parte URI dei riferimenti all'endpoint `AcksTo`, `ReplyTo` e `Endpoint` sia identica prima di creare una sequenza.</span><span class="sxs-lookup"><span data-stu-id="7e94f-128">The WCF Responder verifies that the URI portion of the `AcksTo`, `ReplyTo` and `Endpoint` endpoint references are identical before creating a sequence.</span></span>

- <span data-ttu-id="7e94f-129">R1103: i riferimenti degli endpoint `AcksTo`, `ReplyTo` e `Offer/Endpoint` nel messaggio `CreateSequence` devono avere lo stesso set di parametri per riferimento.</span><span class="sxs-lookup"><span data-stu-id="7e94f-129">R1103: The `AcksTo`, `ReplyTo` and `Offer/Endpoint` endpoint references in the `CreateSequence` message should have the same set of reference parameters.</span></span>

  - <span data-ttu-id="7e94f-130">WCF non impone, ma presuppone che i parametri di riferimento dei riferimenti a `AcksTo`, `ReplyTo` e `Offer/Endpoint` endpoint su `CreateSequence` siano identici e utilizzino i parametri di riferimento del riferimento dell'endpoint di `ReplyTo` per i messaggi di conferma e di sequenza opposta.</span><span class="sxs-lookup"><span data-stu-id="7e94f-130">WCF does not enforce, but assumes that reference parameters of the `AcksTo`, `ReplyTo` and `Offer/Endpoint` endpoint references on `CreateSequence` are identical and uses reference parameters from the `ReplyTo` endpoint reference for acknowledgements and converse sequence messages.</span></span>

- <span data-ttu-id="7e94f-131">B1104: l'iniziatore WCF non genera l'elemento facoltativo `Expires` o `Offer/Expires` nel messaggio `CreateSequence`.</span><span class="sxs-lookup"><span data-stu-id="7e94f-131">B1104: The WCF Initiator does not generate the optional `Expires` or `Offer/Expires` element in the `CreateSequence` message.</span></span>

- <span data-ttu-id="7e94f-132">B1105: quando si accede al messaggio `CreateSequence`, il risponditore WCF usa il valore `Expires` nell'elemento `CreateSequence` come valore `Expires` nell'elemento `CreateSequenceResponse`.</span><span class="sxs-lookup"><span data-stu-id="7e94f-132">B1105: When accessing the `CreateSequence` message, the WCF Responder uses the `Expires` value in the `CreateSequence` element as the `Expires` value in the `CreateSequenceResponse` element.</span></span> <span data-ttu-id="7e94f-133">In caso contrario, il risponditore WCF legge e ignora i valori `Expires` e `Offer/Expires`.</span><span class="sxs-lookup"><span data-stu-id="7e94f-133">Otherwise, the WCF Responder reads and ignores the `Expires` and `Offer/Expires` values.</span></span>

- <span data-ttu-id="7e94f-134">B1106: quando si accede al `CreateSequenceResponse` messaggio, l'iniziatore WCF legge il valore facoltativo `Expires` ma non lo usa.</span><span class="sxs-lookup"><span data-stu-id="7e94f-134">B1106: When accessing the `CreateSequenceResponse` message, the WCF Initiator reads the optional `Expires` value but does not use it.</span></span>

- <span data-ttu-id="7e94f-135">B1107: l'iniziatore WCF e il risponditore generano sempre l'elemento facoltativo `IncompleteSequenceBehavior` negli elementi `CreateSequence/Offer` e `CreateSequenceResponse`.</span><span class="sxs-lookup"><span data-stu-id="7e94f-135">B1107: The WCF Initiator and Responder always generate the optional `IncompleteSequenceBehavior` element in the `CreateSequence/Offer` and `CreateSequenceResponse` elements.</span></span>

- <span data-ttu-id="7e94f-136">B1108: WCF usa solo i valori `DiscardFollowingFirstGap` e `NoDiscard` nell'elemento `IncompleteSequenceBehavior`.</span><span class="sxs-lookup"><span data-stu-id="7e94f-136">B1108: WCF uses only the `DiscardFollowingFirstGap` and `NoDiscard` values in the `IncompleteSequenceBehavior` element.</span></span>

  - <span data-ttu-id="7e94f-137">WS-ReliableMessaging utilizza il meccanismo `Offer` per stabilire le due sequenze correlate opposte che formano una sessione.</span><span class="sxs-lookup"><span data-stu-id="7e94f-137">WS-ReliableMessaging utilizes the `Offer` mechanism to establish the two converse correlated sequences that form a session.</span></span>

- <span data-ttu-id="7e94f-138">B1109: se `CreateSequence` contiene un elemento `Offer`, il risponditore WCF rifiuterà la sequenza offerta rispondendo a un `CreateSequenceResponse` senza un elemento `Accept`.</span><span class="sxs-lookup"><span data-stu-id="7e94f-138">B1109: If `CreateSequence` contains an `Offer` element, the one way WCF Responder rejects the offered sequence by responding with a `CreateSequenceResponse` without an `Accept` element.</span></span>

- <span data-ttu-id="7e94f-139">B1110: se un risponditore Reliable Messaging rifiuta la sequenza offerta, l'iniziatore WCF genera errori nella sequenza appena stabilita.</span><span class="sxs-lookup"><span data-stu-id="7e94f-139">B1110: If a Reliable Messaging Responder rejects the offered sequence, the WCF Initiator faults the newly established sequence.</span></span>

- <span data-ttu-id="7e94f-140">B1111: se `CreateSequence` non contiene un elemento `Offer`, il risponditore WCF bidirezionale respinge la sequenza offerta rispondendo con un errore di `CreateSequenceRefused`.</span><span class="sxs-lookup"><span data-stu-id="7e94f-140">B1111: If `CreateSequence` does not contain an `Offer` element, the two-way WCF Responder rejects the offered sequence by responding with a `CreateSequenceRefused` fault.</span></span>

- <span data-ttu-id="7e94f-141">R1112: quando vengono stabilite due sequenze opposte utilizzando il meccanismo `Offer`, la proprietà `[address]` del riferimento dell'endpoint `CreateSequenceResponse/Accept/AcksTo` deve corrispondere all'URI di destinazione del messaggio `CreateSequence`, byte per byte.</span><span class="sxs-lookup"><span data-stu-id="7e94f-141">R1112: When two converse sequences are established using the `Offer` mechanism, the `[address]` property of the `CreateSequenceResponse/Accept/AcksTo` endpoint reference must match the destination URI of the `CreateSequence` message byte for byte.</span></span>

- <span data-ttu-id="7e94f-142">R1113: quando vengono stabilite due sequenze opposte utilizzando il meccanismo `Offer`, tutti i messaggi su entrambe le sequenze dall'iniziatore al risponditore devono essere inviati allo stesso riferimento dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="7e94f-142">R1113: When two converse sequences are established using the `Offer` mechanism, all messages on both sequences flowing from the Initiator to the Responder must be sent to the same endpoint reference.</span></span>

<span data-ttu-id="7e94f-143">WCF utilizza WS-ReliableMessaging per stabilire sessioni affidabili tra l'iniziatore e il risponditore.</span><span class="sxs-lookup"><span data-stu-id="7e94f-143">WCF uses WS-ReliableMessaging to establish reliable sessions between the Initiator and the Responder.</span></span> <span data-ttu-id="7e94f-144">L'implementazione WCF WS-ReliableMessaging fornisce una sessione affidabile per modelli di messaggistica unidirezionali, Request/Reply e full duplex.</span><span class="sxs-lookup"><span data-stu-id="7e94f-144">The WCF WS-ReliableMessaging implementation provides a reliable session for one-way, request-reply and full duplex messaging patterns.</span></span> <span data-ttu-id="7e94f-145">Il meccanismo `Offer` di WS-Reliable Messaging in `CreateSequence` e `CreateSequenceResponse` consente di stabilire due sequenze opposte correlate e fornisce un protocollo della sessione idoneo per tutti gli endpoint del messaggio.</span><span class="sxs-lookup"><span data-stu-id="7e94f-145">The WS-ReliableMessaging `Offer` mechanism on `CreateSequence` and `CreateSequenceResponse` lets you establish two correlated converse sequences and provides a session protocol that is suitable for all message endpoints.</span></span> <span data-ttu-id="7e94f-146">Poiché WCF fornisce una garanzia di sicurezza per tale sessione, inclusa la protezione end-to-end per l'integrità della sessione, è consigliabile assicurarsi che i messaggi destinati alla stessa parte arrivino alla stessa destinazione.</span><span class="sxs-lookup"><span data-stu-id="7e94f-146">Because WCF provides a security guarantee for such a session including end-to-end protection for session integrity, it is practical to ensure that messages intended for the same party arrive at the same destination.</span></span> <span data-ttu-id="7e94f-147">Ciò consente anche il "piggy-backing" degli acknowledgement della sequenza sui messaggi dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="7e94f-147">This also allows "piggy-backing" of sequence acknowledgements on application messages.</span></span> <span data-ttu-id="7e94f-148">Pertanto, i vincoli R1102, R1112 e R1113 si applicano a WCF.</span><span class="sxs-lookup"><span data-stu-id="7e94f-148">Therefore, constraints R1102, R1112, and R1113 apply to WCF.</span></span>

<span data-ttu-id="7e94f-149">Esempio di un messaggio `CreateSequence`.</span><span class="sxs-lookup"><span data-stu-id="7e94f-149">An example of a `CreateSequence` message.</span></span>

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

<span data-ttu-id="7e94f-150">Esempio di un messaggio `CreateSequenceResponse`.</span><span class="sxs-lookup"><span data-stu-id="7e94f-150">An example of a `CreateSequenceResponse` message.</span></span>

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

### <a name="closing-a-sequence"></a><span data-ttu-id="7e94f-151">Chiusura di una sequenza</span><span class="sxs-lookup"><span data-stu-id="7e94f-151">Closing a Sequence</span></span>

<span data-ttu-id="7e94f-152">WCF utilizza i messaggi `CloseSequence` e `CloseSequenceResponse` per l'arresto di un'origine di messaggistica affidabile avviata.</span><span class="sxs-lookup"><span data-stu-id="7e94f-152">WCF uses the `CloseSequence` and `CloseSequenceResponse` messages for a Reliable Messaging source-initiated shutdown.</span></span> <span data-ttu-id="7e94f-153">La destinazione di messaggistica affidabile WCF non avvia l'arresto e l'origine della messaggistica affidabile WCF non supporta l'arresto avviato da una destinazione di messaggistica affidabile.</span><span class="sxs-lookup"><span data-stu-id="7e94f-153">The WCF Reliable Messaging destination does not initiate shutdown and the WCF Reliable Messaging source does not support a Reliable Messaging destination-initiated shutdown.</span></span> <span data-ttu-id="7e94f-154">Si applicano i vincoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="7e94f-154">The following constraints apply:</span></span>

- <span data-ttu-id="7e94f-155">B1201: l'origine della messaggistica affidabile WCF invia sempre un messaggio di `CloseSequence` per arrestare la sequenza.</span><span class="sxs-lookup"><span data-stu-id="7e94f-155">B1201: The WCF Reliable Messaging source always sends a `CloseSequence` message to shut down the sequence.</span></span>

- <span data-ttu-id="7e94f-156">B1202: l'origine di Reliable Messaging attende l'acknowledgment dell'intera serie di messaggi della sequenza prima di inviare il messaggio `CloseSequence`.</span><span class="sxs-lookup"><span data-stu-id="7e94f-156">B1202: The Reliable Messaging source waits for acknowledgement of the full range of sequence messages before sending the `CloseSequence` message.</span></span>

- <span data-ttu-id="7e94f-157">B1203: l'origine di Reliable Messaging include sempre l'elemento facoltativo `LastMsgNumber`. Non lo include se la sequenza non contiene messaggi.</span><span class="sxs-lookup"><span data-stu-id="7e94f-157">B1203: The Reliable Messaging source always includes the optional `LastMsgNumber` element unless the sequence does not contain messages.</span></span>

- <span data-ttu-id="7e94f-158">R1204: la destinazione di Reliable Messaging non deve iniziare l'arresto inviando un messaggio `CloseSequence`.</span><span class="sxs-lookup"><span data-stu-id="7e94f-158">R1204: The Reliable Messaging destination must not initiate shutdown by sending a `CloseSequence` message.</span></span>

- <span data-ttu-id="7e94f-159">B1205: dopo la ricezione di un messaggio di `CloseSequence`, l'origine della messaggistica affidabile WCF considera la sequenza incompleta e invia un errore.</span><span class="sxs-lookup"><span data-stu-id="7e94f-159">B1205: Upon receiving a `CloseSequence` message, the WCF Reliable Messaging source considers the sequence incomplete and sends a fault.</span></span>

 <span data-ttu-id="7e94f-160">Esempio di un messaggio `CloseSequence`.</span><span class="sxs-lookup"><span data-stu-id="7e94f-160">An example of a `CloseSequence` message.</span></span>

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
```

<span data-ttu-id="7e94f-161">Messaggio `CloseSequenceResponse` di esempio:</span><span class="sxs-lookup"><span data-stu-id="7e94f-161">Example `CloseSequenceResponse` message:</span></span>

```xml
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

### <a name="sequence-termination"></a><span data-ttu-id="7e94f-162">Terminazione della sequenza</span><span class="sxs-lookup"><span data-stu-id="7e94f-162">Sequence Termination</span></span>

<span data-ttu-id="7e94f-163">WCF utilizza principalmente l'handshake `TerminateSequence/TerminateSequenceResponse` dopo il completamento dell'handshake di `CloseSequence/CloseSequenceResponse`.</span><span class="sxs-lookup"><span data-stu-id="7e94f-163">WCF primarily uses the `TerminateSequence/TerminateSequenceResponse` handshake after completing the `CloseSequence/CloseSequenceResponse` handshake.</span></span> <span data-ttu-id="7e94f-164">La destinazione di messaggistica affidabile WCF non avvia la terminazione e l'origine di Reliable Messaging non supporta la terminazione avviata da una destinazione di messaggistica affidabile.</span><span class="sxs-lookup"><span data-stu-id="7e94f-164">The WCF Reliable Messaging destination does not initiate termination and the Reliable Messaging source does not support a Reliable Messaging destination-initiated termination.</span></span> <span data-ttu-id="7e94f-165">Si applicano i vincoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="7e94f-165">The following constraints apply:</span></span>

- <span data-ttu-id="7e94f-166">B1301: l'iniziatore WCF invia il messaggio di `TerminateSequence` solo dopo il completamento dell'handshake del `CloseSequence/CloseSequenceResponse`.</span><span class="sxs-lookup"><span data-stu-id="7e94f-166">B1301: The WCF Initiator only sends the `TerminateSequence` message after the successful completion of the `CloseSequence/CloseSequenceResponse` handshake.</span></span>

- <span data-ttu-id="7e94f-167">R1302: WCF verifica che l'elemento `LastMsgNumber` sia coerente in tutti i messaggi di `CloseSequence` e `TerminateSequence` per una determinata sequenza.</span><span class="sxs-lookup"><span data-stu-id="7e94f-167">R1302: WCF validates that the `LastMsgNumber` element is consistent across all `CloseSequence` and `TerminateSequence` messages for a given sequence.</span></span> <span data-ttu-id="7e94f-168">Ciò significa che `LastMsgNumber` o non è presente in tutti i messaggi `CloseSequence` e `TerminateSequence`, o è presente e identico in tutti i messaggi `CloseSequence` e `TerminateSequence`.</span><span class="sxs-lookup"><span data-stu-id="7e94f-168">This means that `LastMsgNumber` is either not present on all `CloseSequence` and `TerminateSequence` messages, or it is present and identical on all `CloseSequence` and `TerminateSequence` messages.</span></span>

- <span data-ttu-id="7e94f-169">B1303: al ricevimento di un messaggio `TerminateSequence` dopo l'handshake `CloseSequence/CloseSequenceResponse`, la destinazione di Reliable Messaging risponde con un messaggio `TerminateSequenceResponse`.</span><span class="sxs-lookup"><span data-stu-id="7e94f-169">B1303: When receiving a `TerminateSequence` message after the `CloseSequence/CloseSequenceResponse` handshake, the Reliable Messaging destination responds with a `TerminateSequenceResponse` message.</span></span> <span data-ttu-id="7e94f-170">Poiché l'origine di Reliable Messaging dispone dell'acknowledgement finale prima dell'invio del messaggio `TerminateSequence`, la destinazione di Reliable Messaging è a conoscenza della fine della sequenza e richiede immediatamente le risorse.</span><span class="sxs-lookup"><span data-stu-id="7e94f-170">Because the Reliable Messaging source has the final acknowledgement before sending the `TerminateSequence` message, the Reliable Messaging destination knows without doubt that the sequence ends, and reclaims resources immediately.</span></span>

- <span data-ttu-id="7e94f-171">B1304: quando si riceve un messaggio di `TerminateSequence` prima dell'handshake `CloseSequence/CloseSequenceResponse`, la destinazione della messaggistica affidabile WCF risponde con un messaggio di `TerminateSequenceResponse`.</span><span class="sxs-lookup"><span data-stu-id="7e94f-171">B1304: When receiving a `TerminateSequence` message prior to the `CloseSequence/CloseSequenceResponse` handshake, the WCF Reliable Messaging destination responds with a `TerminateSequenceResponse` message.</span></span> <span data-ttu-id="7e94f-172">Se la destinazione di Reliable Messaging stabilisce che non vi sono incoerenze nella sequenza, attende per il periodo di tempo specificato dalla destinazione dell'applicazione prima di richiedere le risorse, per offrire al client la possibilità di ricevere l'acknowledgement finale.</span><span class="sxs-lookup"><span data-stu-id="7e94f-172">If the Reliable Messaging destination determines that there are no inconsistencies in the sequence, the Reliable Messaging destination waits for an application destination-specified time before reclaiming resources, to allow the client the chance to receive the final acknowledgement.</span></span> <span data-ttu-id="7e94f-173">In caso contrario, la destinazione di Reliable Messaging richiede immediatamente le risorse e indica alla destinazione dell'applicazione che la sequenza termina in modo dubbio generando l'evento `Faulted`.</span><span class="sxs-lookup"><span data-stu-id="7e94f-173">Otherwise, the Reliable Messaging destination reclaims resources immediately and indicates to the application destination that the sequence ends with doubt by raising the `Faulted` event.</span></span>

<span data-ttu-id="7e94f-174">Esempio di un messaggio `TerminateSequence`.</span><span class="sxs-lookup"><span data-stu-id="7e94f-174">An example of a `TerminateSequence` message.</span></span>

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
```

<span data-ttu-id="7e94f-175">Messaggio `TerminateSequenceResponse` di esempio:</span><span class="sxs-lookup"><span data-stu-id="7e94f-175">Example `TerminateSequenceResponse` message:</span></span>

```xml
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

### <a name="sequences"></a><span data-ttu-id="7e94f-176">Sequenze</span><span class="sxs-lookup"><span data-stu-id="7e94f-176">Sequences</span></span>

<span data-ttu-id="7e94f-177">Di seguito è riportato un elenco di vincoli che si applicano alle sequenze:</span><span class="sxs-lookup"><span data-stu-id="7e94f-177">The following is a list of constraints that apply to sequences:</span></span>

- <span data-ttu-id="7e94f-178">B1401: WCF genera e accede ai numeri di sequenza non superiori al valore inclusivo massimo `xs:long`, 9223372036854775807.</span><span class="sxs-lookup"><span data-stu-id="7e94f-178">B1401:WCF generates and accesses sequence numbers no higher than `xs:long`’s maximum inclusive value, 9223372036854775807.</span></span>

<span data-ttu-id="7e94f-179">Esempio di intestazione `Sequence`.</span><span class="sxs-lookup"><span data-stu-id="7e94f-179">An example of a `Sequence` header.</span></span>

```xml
<wsrm:Sequence s:mustUnderstand="1">
  <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>
  <wsrm:MessageNumber>1</wsrm:MessageNumber>
</wsrm:Sequence>
```

### <a name="request-acknowledgement"></a><span data-ttu-id="7e94f-180">Acknowledgement della richiesta</span><span class="sxs-lookup"><span data-stu-id="7e94f-180">Request Acknowledgement</span></span>

<span data-ttu-id="7e94f-181">WCF utilizza l'intestazione `AckRequested` come meccanismo Keep-Alive.</span><span class="sxs-lookup"><span data-stu-id="7e94f-181">WCF uses the `AckRequested` header as a keep-alive mechanism.</span></span>

<span data-ttu-id="7e94f-182">Esempio di intestazione `AckRequested`.</span><span class="sxs-lookup"><span data-stu-id="7e94f-182">An example of an `AckRequested` header.</span></span>

```xml
<wsrm:AckRequested>
  <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>
</wsrm:AckRequested>
```

### <a name="sequenceacknowledgement"></a><span data-ttu-id="7e94f-183">SequenceAcknowledgement</span><span class="sxs-lookup"><span data-stu-id="7e94f-183">SequenceAcknowledgement</span></span>

<span data-ttu-id="7e94f-184">WCF utilizza un meccanismo "Piggy-Back" per i riconoscimenti di sequenza forniti in WS-Reliable Messaging.</span><span class="sxs-lookup"><span data-stu-id="7e94f-184">WCF uses a "piggy-back" mechanism for sequence acknowledgements provided in WS-Reliable Messaging.</span></span> <span data-ttu-id="7e94f-185">Si applicano i vincoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="7e94f-185">The following constraints apply:</span></span>

- <span data-ttu-id="7e94f-186">R1601: quando vengono stabilite due sequenze opposte utilizzando il meccanismo di `Offer`, l'intestazione `SequenceAcknowledgement` può essere inclusa in qualsiasi messaggio dell'applicazione trasmesso al destinatario previsto.</span><span class="sxs-lookup"><span data-stu-id="7e94f-186">R1601: When two converse sequences are established using the `Offer` mechanism, the `SequenceAcknowledgement` header may be included in any application message transmitted to the intended recipient.</span></span> <span data-ttu-id="7e94f-187">L'endpoint remoto deve essere in grado di accedere a un'intestazione `SequenceAcknowledgement` sottoposta a piggyback.</span><span class="sxs-lookup"><span data-stu-id="7e94f-187">The remote endpoint must be able to access a piggybacked `SequenceAcknowledgement` header.</span></span>

- <span data-ttu-id="7e94f-188">B1602: WCF non genera intestazioni `SequenceAcknowledgement` che contengono elementi `Nack`.</span><span class="sxs-lookup"><span data-stu-id="7e94f-188">B1602: WCF does not generate `SequenceAcknowledgement` headers that contain `Nack` elements.</span></span> <span data-ttu-id="7e94f-189">WCF verifica che ogni elemento `Nack` contenga un numero di sequenza, ma altrimenti ignora l'elemento e il valore del `Nack`.</span><span class="sxs-lookup"><span data-stu-id="7e94f-189">WCF validates that each `Nack` element contains a sequence number, but otherwise ignores the `Nack` element and value.</span></span>

 <span data-ttu-id="7e94f-190">Esempio di intestazione `SequenceAcknowledgement`.</span><span class="sxs-lookup"><span data-stu-id="7e94f-190">An example of a `SequenceAcknowledgement` header.</span></span>

```xml
<wsrm:SequenceAcknowledgement>
  <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>
  <wsrm:AcknowledgementRange Lower="1" Upper="1"></wsrm:AcknowledgementRange>
</wsrm:SequenceAcknowledgement>
```

### <a name="ws-reliablemessaging-faults"></a><span data-ttu-id="7e94f-191">Errori WS-ReliableMessaging</span><span class="sxs-lookup"><span data-stu-id="7e94f-191">WS-ReliableMessaging Faults</span></span>

<span data-ttu-id="7e94f-192">Di seguito è riportato un elenco di vincoli che si applicano all'implementazione WCF degli errori di WS-ReliableMessaging.</span><span class="sxs-lookup"><span data-stu-id="7e94f-192">The following is a list of constraints that apply to the WCF implementation of WS-ReliableMessaging faults.</span></span> <span data-ttu-id="7e94f-193">Si applicano i vincoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="7e94f-193">The following constraints apply:</span></span>

- <span data-ttu-id="7e94f-194">B1701: WCF non genera errori di `MessageNumberRollover`.</span><span class="sxs-lookup"><span data-stu-id="7e94f-194">B1701: WCF does not generate `MessageNumberRollover` faults.</span></span>

- <span data-ttu-id="7e94f-195">B1702: tramite SOAP 1,2, quando l'endpoint del servizio raggiunge il limite di connessione e non è in grado di elaborare nuove connessioni, WCF genera un codice Sub`CreateSequenceRefused` di errore annidato, `netrm:ConnectionLimitReached`, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="7e94f-195">B1702: Over SOAP 1.2, when the service endpoint reaches its connection limit and cannot process new connections, WCF generates a nested `CreateSequenceRefused` fault subcode, `netrm:ConnectionLimitReached`, as shown in the following example.</span></span>

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

### <a name="ws-addressing-faults"></a><span data-ttu-id="7e94f-196">Errori WS-Addressing</span><span class="sxs-lookup"><span data-stu-id="7e94f-196">WS-Addressing Faults</span></span>

<span data-ttu-id="7e94f-197">Poiché WS-ReliableMessaging utilizza WS-Addressing, l'implementazione di WCF WS-ReliableMessaging può generare e trasmettere errori di WS-Addressing.</span><span class="sxs-lookup"><span data-stu-id="7e94f-197">Because WS-ReliableMessaging uses WS-Addressing, the WCF WS-ReliableMessaging implementation may generate and transmit WS-Addressing faults.</span></span> <span data-ttu-id="7e94f-198">In questa sezione vengono illustrati gli errori WS-Addressing che WCF genera e trasmette in modo esplicito a livello di WS-ReliableMessaging:</span><span class="sxs-lookup"><span data-stu-id="7e94f-198">This section covers the WS-Addressing faults that WCF explicitly generates and transmits at the WS-ReliableMessaging layer:</span></span>

- <span data-ttu-id="7e94f-199">B1801: WCF genera e trasmette l'errore `Message Addressing Header Required` quando si verifica una delle condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7e94f-199">B1801:WCF generates and transmits the `Message Addressing Header Required` fault when one of the following is true:</span></span>

  - <span data-ttu-id="7e94f-200">In un messaggio `CreateSequence`, `CloseSequence` o `TerminateSequence` manca un'intestazione `MessageId`.</span><span class="sxs-lookup"><span data-stu-id="7e94f-200">A `CreateSequence`, `CloseSequence` or `TerminateSequence` message is missing a `MessageId` header.</span></span>

  - <span data-ttu-id="7e94f-201">In un messaggio `CreateSequence`, `CloseSequence` o `TerminateSequence` manca un'intestazione `ReplyTo`.</span><span class="sxs-lookup"><span data-stu-id="7e94f-201">A `CreateSequence`, `CloseSequence` or `TerminateSequence` message is missing a `ReplyTo` header.</span></span>

  - <span data-ttu-id="7e94f-202">In un messaggio `CreateSequenceResponse`, `CloseSequenceResponse` o `TerminateSequenceResponse` manca un'intestazione `RelatesTo`.</span><span class="sxs-lookup"><span data-stu-id="7e94f-202">A `CreateSequenceResponse`, `CloseSequenceResponse`, or `TerminateSequenceResponse` message is missing a `RelatesTo` header.</span></span>

- <span data-ttu-id="7e94f-203">B1802: WCF genera e trasmette l'errore `Endpoint Unavailable` per indicare che non è presente alcun endpoint in ascolto in grado di elaborare la sequenza in base all'esame delle intestazioni di indirizzamento nel messaggio di `CreateSequence`.</span><span class="sxs-lookup"><span data-stu-id="7e94f-203">B1802:WCF generates and transmits the `Endpoint Unavailable` fault to indicate there is no endpoint listening that can process the sequence based on examination of the addressing headers in the `CreateSequence` message.</span></span>

## <a name="protocol-composition"></a><span data-ttu-id="7e94f-204">Composizione del protocollo</span><span class="sxs-lookup"><span data-stu-id="7e94f-204">Protocol Composition</span></span>

### <a name="composition-with-ws-addressing"></a><span data-ttu-id="7e94f-205">Composizione con WS-Addressing</span><span class="sxs-lookup"><span data-stu-id="7e94f-205">Composition with WS-Addressing</span></span>

<span data-ttu-id="7e94f-206">WCF supporta due versioni di WS-Addressing: WS-Addressing 2004/08 [WS-ADDR] e W3C WS-Addressing 1,0 raccomandazioni [WS-ADDR-CORE] e [WS-ADDR-SOAP].</span><span class="sxs-lookup"><span data-stu-id="7e94f-206">WCF supports two versions of WS-Addressing: WS-Addressing 2004/08 [WS-ADDR] and W3C WS-Addressing 1.0 Recommendations [WS-ADDR-CORE] and [WS-ADDR-SOAP].</span></span>

<span data-ttu-id="7e94f-207">Anche se la specifica WS-ReliableMessaging menziona solo WS-Addressing 2004/08, non limita la versione WS-Addressing da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="7e94f-207">While the WS-ReliableMessaging specification mentions only WS-Addressing 2004/08, it does not restrict the WS-Addressing version to be used.</span></span> <span data-ttu-id="7e94f-208">Di seguito è riportato un elenco di vincoli che si applicano a WCF:</span><span class="sxs-lookup"><span data-stu-id="7e94f-208">The following is a list of constraints that apply to WCF:</span></span>

- <span data-ttu-id="7e94f-209">R2101: sia WS-Addressing 2004/08 che WS-Addressing 1.0 possono essere utilizzati con WS-Reliable Messaging.</span><span class="sxs-lookup"><span data-stu-id="7e94f-209">R2101: Both WS-Addressing 2004/08 and WS-Addressing 1.0 can be used with WS-Reliable Messaging.</span></span>

- <span data-ttu-id="7e94f-210">R2102: è necessario utilizzare una sola versione di WS-Addressing in una data sequenza di WS-Reliable Messaging o in una coppia di sequenze opposte correlate tramite il meccanismo `Offer`.</span><span class="sxs-lookup"><span data-stu-id="7e94f-210">R2102: A single version of WS-Addressing must be used throughout a given WS-ReliableMessaging sequence or a pair of converse sequences correlated by using the `Offer` mechanism.</span></span>

### <a name="composition-with-soap"></a><span data-ttu-id="7e94f-211">Composizione con SOAP</span><span class="sxs-lookup"><span data-stu-id="7e94f-211">Composition with SOAP</span></span>

<span data-ttu-id="7e94f-212">WCF supporta l'utilizzo di SOAP 1,1 e SOAP 1,2 con WS-Reliable Messaging.</span><span class="sxs-lookup"><span data-stu-id="7e94f-212">WCF supports the use of both SOAP 1.1 and SOAP 1.2 with WS-Reliable Messaging.</span></span>

### <a name="composition-with-ws-security-and-ws-secureconversation"></a><span data-ttu-id="7e94f-213">Composizione con WS-Security e WS-SecureConversation</span><span class="sxs-lookup"><span data-stu-id="7e94f-213">Composition with WS-Security and WS-SecureConversation</span></span>

<span data-ttu-id="7e94f-214">WCF fornisce la protezione per le sequenze WS-ReliableMessaging tramite trasporto protetto (HTTPS), composizione con WS-Security e composizione con WS-Secure Conversation.</span><span class="sxs-lookup"><span data-stu-id="7e94f-214">WCF provides protection for WS-ReliableMessaging sequences by using secure Transport (HTTPS), composition with WS-Security, and composition with WS-Secure Conversation.</span></span> <span data-ttu-id="7e94f-215">Il protocollo WS-Reliable Messaging 1.1, WS-Security 1.1 e il protocollo WS-SecureConversation 1.3 devono essere utilizzati insieme.</span><span class="sxs-lookup"><span data-stu-id="7e94f-215">The WS-ReliableMessaging 1.1 protocol, WS-Security 1.1 and WS-Secure Conversation 1.3 protocol should be used together.</span></span> <span data-ttu-id="7e94f-216">Di seguito è riportato un elenco di vincoli che si applicano a WCF:</span><span class="sxs-lookup"><span data-stu-id="7e94f-216">The following is a list of constraints that apply to WCF:</span></span>

- <span data-ttu-id="7e94f-217">R2301: per proteggere l'integrità di una sequenza di WS-ReliableMessaging oltre all'integrità e alla riservatezza dei singoli messaggi, WCF richiede l'utilizzo di WS-Secure Conversation.</span><span class="sxs-lookup"><span data-stu-id="7e94f-217">R2301: To protect the integrity of a WS-ReliableMessaging sequence in addition to the integrity and confidentiality of individual messages, WCF requires that WS-Secure Conversation must be used.</span></span>

- <span data-ttu-id="7e94f-218">R2302: prima di stabilire la(e) sequenza(e) di WS-Reliable Messaging, è necessario stabilire una sessione WS-SecureConversation.</span><span class="sxs-lookup"><span data-stu-id="7e94f-218">R2302:AWS-Secure Conversation session must be established prior to establishing WS-ReliableMessaging sequence(s).</span></span>

- <span data-ttu-id="7e94f-219">R2303: se la durata della sequenza di WS-Reliable Messaging supera la durata della sessione WS-SecureConversation, è necessario rinnovare il `SecurityContextToken` stabilito tramite WS-SecureConversation utilizzando l'associazione WS-Secure Conversation Renewal corrispondente.</span><span class="sxs-lookup"><span data-stu-id="7e94f-219">R2303: If the WS-ReliableMessaging sequence lifetime exceeds the WS-Secure Conversation session’s lifetime, the `SecurityContextToken` established by using WS-Secure Conversation must be renewed by using the corresponding WS-Secure Conversation Renewal binding.</span></span>

- <span data-ttu-id="7e94f-220">B2304: la sequenza WS-ReliableMessaging o una coppia di sequenze opposte sono sempre associate a una singola sessione WS-SecureConversation.</span><span class="sxs-lookup"><span data-stu-id="7e94f-220">B2304:WS-ReliableMessaging sequence or a pair of correlated converse sequences are always bound to a single WS-SecureConversation session.</span></span>

- <span data-ttu-id="7e94f-221">R2305: se composto con WS-Secure Conversation, il risponditore WCF richiede che il messaggio di `CreateSequence` contenga l'elemento `wsse:SecurityTokenReference` e l'intestazione `wsrm:UsesSequenceSTR`.</span><span class="sxs-lookup"><span data-stu-id="7e94f-221">R2305: When composed with WS-Secure Conversation, the WCF responder requires that the `CreateSequence` message contain the `wsse:SecurityTokenReference` element and the `wsrm:UsesSequenceSTR` header.</span></span>

 <span data-ttu-id="7e94f-222">Esempio di intestazione `UsesSequenceSTR`.</span><span class="sxs-lookup"><span data-stu-id="7e94f-222">An example of a `UsesSequenceSTR` header.</span></span>

```xml
<wsrm:UsesSequenceSTR></wsrm:UsesSequenceSTR>
```

### <a name="composition-with-ssltls-sessions"></a><span data-ttu-id="7e94f-223">Composizione con sessioni SSL/TLS</span><span class="sxs-lookup"><span data-stu-id="7e94f-223">Composition with SSL/TLS sessions</span></span>

<span data-ttu-id="7e94f-224">WCF non supporta la composizione con sessioni SSL/TLS:</span><span class="sxs-lookup"><span data-stu-id="7e94f-224">WCF does not support composition with SSL/TLS sessions:</span></span>

- <span data-ttu-id="7e94f-225">B2401: WCF non genera l'intestazione `wsrm:UsesSequenceSSL`.</span><span class="sxs-lookup"><span data-stu-id="7e94f-225">B2401: WCF does not generate the `wsrm:UsesSequenceSSL` header.</span></span>

- <span data-ttu-id="7e94f-226">R2402: un iniziatore di messaggistica affidabile non deve inviare un messaggio di `CreateSequence` con un'intestazione `wsrm:UsesSequenceSSL` a un risponditore WCF.</span><span class="sxs-lookup"><span data-stu-id="7e94f-226">R2402: A Reliable Messaging Initiator must not send a `CreateSequence` message with a `wsrm:UsesSequenceSSL` header to a WCF Responder.</span></span>

### <a name="composition-with-ws-policy"></a><span data-ttu-id="7e94f-227">Composizione con WS-Policy</span><span class="sxs-lookup"><span data-stu-id="7e94f-227">Composition with WS-Policy</span></span>

<span data-ttu-id="7e94f-228">WCF supporta due versioni di WS-Policy: WS-Policy 1,2 e WS-Policy 1,5.</span><span class="sxs-lookup"><span data-stu-id="7e94f-228">WCF supports two versions of WS-Policy: WS-Policy 1.2 and WS-Policy 1.5.</span></span>

## <a name="ws-reliablemessaging-ws-policy-assertion"></a><span data-ttu-id="7e94f-229">Asserzione di WS-Policy relativa a WS-ReliableMessaging</span><span class="sxs-lookup"><span data-stu-id="7e94f-229">WS-ReliableMessaging WS-Policy Assertion</span></span>

<span data-ttu-id="7e94f-230">WCF usa l'asserzione WS-Policy di WS-ReliableMessaging `wsrm:RMAssertion` per descrivere le funzionalità degli endpoint.</span><span class="sxs-lookup"><span data-stu-id="7e94f-230">WCF uses WS-ReliableMessaging WS-Policy Assertion `wsrm:RMAssertion` to describe endpoints capabilities.</span></span> <span data-ttu-id="7e94f-231">Di seguito è riportato un elenco di vincoli che si applicano a WCF:</span><span class="sxs-lookup"><span data-stu-id="7e94f-231">The following is a list of constraints that apply to WCF:</span></span>

- <span data-ttu-id="7e94f-232">B3001: WCF connette `wsrmn:RMAssertion` asserzione WS-Policy agli elementi `wsdl:binding`.</span><span class="sxs-lookup"><span data-stu-id="7e94f-232">B3001: WCF attaches `wsrmn:RMAssertion` WS-Policy Assertion to `wsdl:binding` elements.</span></span> <span data-ttu-id="7e94f-233">WCF supporta entrambi gli allegati per `wsdl:binding` e `wsdl:port` elementi.</span><span class="sxs-lookup"><span data-stu-id="7e94f-233">WCF supports both attachments to `wsdl:binding` and `wsdl:port` elements.</span></span>

- <span data-ttu-id="7e94f-234">B3002: WCF non genera mai il tag `wsp:Optional`.</span><span class="sxs-lookup"><span data-stu-id="7e94f-234">B3002: WCF never generates the `wsp:Optional` tag.</span></span>

- <span data-ttu-id="7e94f-235">B3003: quando si accede al `wsrmp:RMAssertion` asserzione WS-Policy, WCF ignora il tag `wsp:Optional` e considera i criteri WS-RM come obbligatori.</span><span class="sxs-lookup"><span data-stu-id="7e94f-235">B3003: When accessing the `wsrmp:RMAssertion` WS-Policy Assertion, WCF ignores the `wsp:Optional` tag and treats the WS-RM policy as mandatory.</span></span>

- <span data-ttu-id="7e94f-236">R3004: poiché WCF non compone con sessioni SSL/TLS, WCF non accetta criteri che specificano `wsrmp:SequenceTransportSecurity`.</span><span class="sxs-lookup"><span data-stu-id="7e94f-236">R3004: Because WCF does not compose with SSL/TLS sessions, WCF does not accept policy that specifies `wsrmp:SequenceTransportSecurity`.</span></span>

- <span data-ttu-id="7e94f-237">B3005: WCF genera sempre l'elemento `wsrmp:DeliveryAssurance`.</span><span class="sxs-lookup"><span data-stu-id="7e94f-237">B3005: WCF always generates the `wsrmp:DeliveryAssurance` element.</span></span>

- <span data-ttu-id="7e94f-238">B3006: WCF specifica sempre la garanzia di recapito `wsrmp:ExactlyOnce`.</span><span class="sxs-lookup"><span data-stu-id="7e94f-238">B3006: WCF always specifies the `wsrmp:ExactlyOnce` delivery assurance.</span></span>

- <span data-ttu-id="7e94f-239">B3007: WCF genera e legge le seguenti proprietà dell'asserzione WS-ReliableMessaging e ne fornisce il controllo sul`ReliableSessionBindingElement`WCF:</span><span class="sxs-lookup"><span data-stu-id="7e94f-239">B3007: WCF generates and reads the following properties of the WS-ReliableMessaging assertion and provides control over them on the WCF`ReliableSessionBindingElement`:</span></span>

  - `netrmp:InactivityTimeout`

  - `netrmp:AcknowledgementInterval`

  <span data-ttu-id="7e94f-240">Esempio di `RMAssertion`.</span><span class="sxs-lookup"><span data-stu-id="7e94f-240">An example of a `RMAssertion`.</span></span>

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

## <a name="flow-control-ws-reliablemessaging-extension"></a><span data-ttu-id="7e94f-241">Estensione di WS-ReliableMessaging per il controllo del flusso</span><span class="sxs-lookup"><span data-stu-id="7e94f-241">Flow Control WS-ReliableMessaging Extension</span></span>

<span data-ttu-id="7e94f-242">WCF utilizza l'estendibilità di WS-ReliableMessaging per fornire un controllo facoltativo aggiuntivo più rigido sul flusso di messaggi della sequenza.</span><span class="sxs-lookup"><span data-stu-id="7e94f-242">WCF uses WS-ReliableMessaging extensibility to provide optional additional tighter control over sequence message flow.</span></span>

<span data-ttu-id="7e94f-243">Il controllo di flusso viene abilitato impostando la proprietà <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.FlowControlEnabled?displayProperty=nameWithType> su `true`.</span><span class="sxs-lookup"><span data-stu-id="7e94f-243">Flow control is enabled by setting the <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.FlowControlEnabled?displayProperty=nameWithType> property to `true`.</span></span> <span data-ttu-id="7e94f-244">Di seguito è riportato un elenco di vincoli che si applicano a WCF:</span><span class="sxs-lookup"><span data-stu-id="7e94f-244">The following is a list of constraints that apply to WCF:</span></span>

- <span data-ttu-id="7e94f-245">B4001: quando è abilitato il controllo di flusso di Reliable Messaging, WCF genera un elemento `netrm:BufferRemaining` nell'estensibilità degli elementi dell'intestazione `SequenceAcknowledgement`, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="7e94f-245">B4001: When Reliable Messaging Flow Control is enabled, WCF generates a `netrm:BufferRemaining` element in the element extensibility of the `SequenceAcknowledgement` header, as shown in the following example.</span></span>

  ```xml
  <wsrm:SequenceAcknowledgement>
    <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>
    <wsrm:AcknowledgementRange Upper="1" Lower="1"/>
    <netrm:BufferRemaining>8</netrm:BufferRemaining>
  </wsrm:SequenceAcknowledgement>
  ```

- <span data-ttu-id="7e94f-246">B4002: anche quando è abilitato il controllo del flusso di messaggistica affidabile, WCF non richiede un elemento `netrm:BufferRemaining` nell'intestazione `SequenceAcknowledgement`.</span><span class="sxs-lookup"><span data-stu-id="7e94f-246">B4002: Even when Reliable Messaging Flow Control is enabled, WCF does not require a `netrm:BufferRemaining` element in the `SequenceAcknowledgement` header.</span></span>

- <span data-ttu-id="7e94f-247">B4003: la destinazione di messaggistica affidabile WCF USA `netrm:BufferRemaining` per indicare il numero di nuovi messaggi che possono essere memorizzati nel buffer.</span><span class="sxs-lookup"><span data-stu-id="7e94f-247">B4003: WCF Reliable Messaging Destination uses `netrm:BufferRemaining` to indicate how many new messages it can buffer.</span></span>

- <span data-ttu-id="7e94f-248">B4004: quando è abilitato il controllo di flusso di Reliable Messaging, l'origine della messaggistica affidabile WCF usa il valore di `netrm:BufferRemaining` per limitare la trasmissione dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="7e94f-248">B4004:When Reliable Messaging Flow Control is enabled, the WCF Reliable Messaging Source uses the value of `netrm:BufferRemaining` to throttle message transmission.</span></span>

- <span data-ttu-id="7e94f-249">B4005: WCF genera `netrm:BufferRemaining` valori integer compresi tra 0 e 4096 inclusi e legge i valori interi compresi tra 0 e il valore `maxInclusive` di `xs:int`214748364 inclusi.</span><span class="sxs-lookup"><span data-stu-id="7e94f-249">B4005: WCF generates `netrm:BufferRemaining` integer values between 0 and 4096 inclusive, and reads integer values between 0 and `xs:int`’s `maxInclusive` value 214748364 inclusive.</span></span>

## <a name="message-exchange-patterns"></a><span data-ttu-id="7e94f-250">Modelli di scambio dei messaggi</span><span class="sxs-lookup"><span data-stu-id="7e94f-250">Message Exchange Patterns</span></span>

<span data-ttu-id="7e94f-251">In questa sezione viene descritto il comportamento di WCF quando WS-ReliableMessaging viene utilizzato per modelli di scambio di messaggi diversi.</span><span class="sxs-lookup"><span data-stu-id="7e94f-251">This section describes WCF's behavior when WS-ReliableMessaging is used for different Message Exchange Patterns.</span></span> <span data-ttu-id="7e94f-252">Per ogni modello di scambio di messaggi, vengono presi in considerazione i due scenari di distribuzione seguenti:</span><span class="sxs-lookup"><span data-stu-id="7e94f-252">For each Message Exchange Pattern the following two deployments scenarios are considered:</span></span>

- <span data-ttu-id="7e94f-253">Iniziatore non indirizzabile: l'iniziatore si trova dietro a un firewall; il risponditore può recapitare messaggi all'iniziatore solo su risposte HTTP.</span><span class="sxs-lookup"><span data-stu-id="7e94f-253">Non-Addressable Initiator: Initiator is behind a firewall; Responder can deliver messages to the Initiator only on HTTP responses.</span></span>

- <span data-ttu-id="7e94f-254">Iniziatore indirizzabile: le richieste HTTP possono essere inviate sia all'iniziatore che al risponditore. In altre parole, è possibile stabilire due connessioni HTTP opposte.</span><span class="sxs-lookup"><span data-stu-id="7e94f-254">Addressable Initiator: Initiator and Responder both can be sent HTTP requests; in other words, two converse HTTP connections can be established.</span></span>

### <a name="one-way-non-addressable-initiator"></a><span data-ttu-id="7e94f-255">Iniziatore unidirezionale, non indirizzabile</span><span class="sxs-lookup"><span data-stu-id="7e94f-255">One-way, Non-addressable Initiator</span></span>

#### <a name="binding"></a><span data-ttu-id="7e94f-256">Binding</span><span class="sxs-lookup"><span data-stu-id="7e94f-256">Binding</span></span>

<span data-ttu-id="7e94f-257">WCF fornisce un modello di scambio di messaggi unidirezionale utilizzando una sequenza su un canale HTTP.</span><span class="sxs-lookup"><span data-stu-id="7e94f-257">WCF provides a one-way message exchange pattern using one sequence over one HTTP channel.</span></span> <span data-ttu-id="7e94f-258">WCF utilizza le richieste HTTP per trasmettere tutti i messaggi dall'iniziatore alle risposte del risponditore e HTTP per trasmettere tutti i messaggi dal risponditore all'iniziatore.</span><span class="sxs-lookup"><span data-stu-id="7e94f-258">WCF uses HTTP requests to transmit all messages from the Initiator to the Responder and HTTP responses to transmit all messages from the Responder to the Initiator.</span></span>

#### <a name="createsequence-exchange"></a><span data-ttu-id="7e94f-259">Scambio CreateSequence</span><span class="sxs-lookup"><span data-stu-id="7e94f-259">CreateSequence Exchange</span></span>

<span data-ttu-id="7e94f-260">L'iniziatore WCF trasmette un messaggio di `CreateSequence` senza `Offer` elemento su una richiesta HTTP e attende il `CreateSequenceResponse` messaggio sulla risposta HTTP.</span><span class="sxs-lookup"><span data-stu-id="7e94f-260">The WCF Initiator transmits a `CreateSequence` message with no `Offer` element on an HTTP request and expects the `CreateSequenceResponse` message on the HTTP response.</span></span> <span data-ttu-id="7e94f-261">Il risponditore WCF crea una sequenza e trasmette il messaggio `CreateSequenceResponse` senza `Accept` elemento sulla risposta HTTP.</span><span class="sxs-lookup"><span data-stu-id="7e94f-261">The WCF Responder creates a sequence and transmits the `CreateSequenceResponse` message with no `Accept` element on the HTTP response.</span></span>

#### <a name="sequenceacknowledgement"></a><span data-ttu-id="7e94f-262">SequenceAcknowledgement</span><span class="sxs-lookup"><span data-stu-id="7e94f-262">SequenceAcknowledgement</span></span>

<span data-ttu-id="7e94f-263">L'iniziatore WCF elabora i riconoscimenti della risposta di tutti i messaggi ad eccezione dei messaggi di errore e di messaggio `CreateSequence`.</span><span class="sxs-lookup"><span data-stu-id="7e94f-263">The WCF Initiator processes acknowledgements on the reply of all messages except the `CreateSequence` message and fault messages.</span></span> <span data-ttu-id="7e94f-264">Il risponditore WCF trasmette sempre un riconoscimento autonomo sulla risposta HTTP a tutti i messaggi Sequence e `AckRequested`.</span><span class="sxs-lookup"><span data-stu-id="7e94f-264">The WCF Responder always transmits a stand-alone acknowledgement on the HTTP response to all sequence and `AckRequested` messages.</span></span>

#### <a name="closesequence-exchange"></a><span data-ttu-id="7e94f-265">Scambio CloseSequence</span><span class="sxs-lookup"><span data-stu-id="7e94f-265">CloseSequence Exchange</span></span>

<span data-ttu-id="7e94f-266">L'iniziatore WCF trasmette un messaggio di `CloseSequence` su una richiesta HTTP e attende il messaggio di `CreateSequenceResponse` sulla risposta HTTP.</span><span class="sxs-lookup"><span data-stu-id="7e94f-266">The WCF Initiator transmits a `CloseSequence` message on an HTTP request and expects the `CreateSequenceResponse` message on the HTTP response.</span></span> <span data-ttu-id="7e94f-267">Il risponditore WCF trasmette il messaggio `CloseSequenceResponse` sulla risposta HTTP.</span><span class="sxs-lookup"><span data-stu-id="7e94f-267">The WCF Responder transmits the `CloseSequenceResponse` message on the HTTP response.</span></span>

#### <a name="terminatesequence-exchange"></a><span data-ttu-id="7e94f-268">Scambio TerminateSequence</span><span class="sxs-lookup"><span data-stu-id="7e94f-268">TerminateSequence Exchange</span></span>

<span data-ttu-id="7e94f-269">L'iniziatore WCF trasmette un messaggio di `TerminateSequence` su una richiesta HTTP e attende il messaggio di `TerminateSequenceResponse` sulla risposta HTTP.</span><span class="sxs-lookup"><span data-stu-id="7e94f-269">The WCF Initiator transmits a `TerminateSequence` message on an HTTP request and expects the `TerminateSequenceResponse` message on the HTTP response.</span></span> <span data-ttu-id="7e94f-270">Il risponditore WCF trasmette il messaggio `TerminateSequenceResponse` sulla risposta HTTP.</span><span class="sxs-lookup"><span data-stu-id="7e94f-270">The WCF Responder transmits the `TerminateSequenceResponse` message on the HTTP response.</span></span>

### <a name="one-way-addressable-initiator"></a><span data-ttu-id="7e94f-271">Iniziatore unidirezionale, indirizzabile</span><span class="sxs-lookup"><span data-stu-id="7e94f-271">One Way, Addressable Initiator</span></span>

#### <a name="binding"></a><span data-ttu-id="7e94f-272">Binding</span><span class="sxs-lookup"><span data-stu-id="7e94f-272">Binding</span></span>

<span data-ttu-id="7e94f-273">WCF fornisce un modello di scambio di messaggi unidirezionale utilizzando una sequenza su un canale HTTP in ingresso e uno in uscita.</span><span class="sxs-lookup"><span data-stu-id="7e94f-273">WCF provides a one-way message exchange pattern using one sequence over one inbound and one outbound HTTP channel.</span></span> <span data-ttu-id="7e94f-274">WCF utilizza le richieste HTTP per trasmettere tutti i messaggi.</span><span class="sxs-lookup"><span data-stu-id="7e94f-274">WCF uses the HTTP requests to transmit all messages.</span></span> <span data-ttu-id="7e94f-275">Tutte le risposte HTTP hanno un corpo vuoto e un codice di stato HTTP 202.</span><span class="sxs-lookup"><span data-stu-id="7e94f-275">All HTTP responses have an empty body and HTTP 202 status code.</span></span>

#### <a name="createsequence-exchange"></a><span data-ttu-id="7e94f-276">Scambio CreateSequence</span><span class="sxs-lookup"><span data-stu-id="7e94f-276">CreateSequence Exchange</span></span>

<span data-ttu-id="7e94f-277">L'iniziatore WCF trasmette un messaggio `CreateSequence` senza `Offer` elemento su una richiesta HTTP.</span><span class="sxs-lookup"><span data-stu-id="7e94f-277">The WCF Initiator transmits a `CreateSequence` message with no `Offer` element on an HTTP request.</span></span> <span data-ttu-id="7e94f-278">Il risponditore WCF crea una sequenza e trasmette il messaggio `CreateSequenceResponse` senza `Accept` elemento su una richiesta HTTP.</span><span class="sxs-lookup"><span data-stu-id="7e94f-278">The WCF Responder creates a sequence and transmits the `CreateSequenceResponse` message with no `Accept` element on an HTTP request.</span></span>

### <a name="duplex-addressable-initiator"></a><span data-ttu-id="7e94f-279">Iniziatore duplex, indirizzabile</span><span class="sxs-lookup"><span data-stu-id="7e94f-279">Duplex, Addressable Initiator</span></span>

#### <a name="binding"></a><span data-ttu-id="7e94f-280">Binding</span><span class="sxs-lookup"><span data-stu-id="7e94f-280">Binding</span></span>

<span data-ttu-id="7e94f-281">WCF fornisce un modello di scambio di messaggi bidirezionale completamente asincrono utilizzando due sequenze su un canale HTTP in ingresso e uno in uscita.</span><span class="sxs-lookup"><span data-stu-id="7e94f-281">WCF provides a fully-asynchronous, two-way message exchange pattern using two sequences over one inbound and one outbound HTTP channel.</span></span> <span data-ttu-id="7e94f-282">Questo modello di scambio può essere combinato con il modello di scambio di messaggi dell'iniziatore `Request/Reply`, `Addressable` in modo limitato.</span><span class="sxs-lookup"><span data-stu-id="7e94f-282">This message exchange pattern can be mixed with the `Request/Reply`, `Addressable` Initiator message exchange pattern in a limited way.</span></span> <span data-ttu-id="7e94f-283">WCF utilizza le richieste HTTP per trasmettere tutti i messaggi.</span><span class="sxs-lookup"><span data-stu-id="7e94f-283">WCF uses HTTP requests to transmit all messages.</span></span> <span data-ttu-id="7e94f-284">Tutte le risposte HTTP hanno un corpo vuoto e un codice di stato HTTP 202.</span><span class="sxs-lookup"><span data-stu-id="7e94f-284">All HTTP responses have an empty body and HTTP 202 status code.</span></span>

#### <a name="createsequence-exchange"></a><span data-ttu-id="7e94f-285">Scambio CreateSequence</span><span class="sxs-lookup"><span data-stu-id="7e94f-285">CreateSequence Exchange</span></span>

<span data-ttu-id="7e94f-286">L'iniziatore WCF trasmette un messaggio di `CreateSequence` con un elemento `Offer` su una richiesta HTTP.</span><span class="sxs-lookup"><span data-stu-id="7e94f-286">The WCF Initiator transmits a `CreateSequence` message with an `Offer` element on an HTTP request.</span></span> <span data-ttu-id="7e94f-287">Il risponditore WCF garantisce che il `CreateSequence` disponga di un elemento `Offer`, quindi crea una sequenza e trasmette il messaggio `CreateSequenceResponse` con un elemento `Accept`.</span><span class="sxs-lookup"><span data-stu-id="7e94f-287">The WCF Responder ensures that the `CreateSequence` has an `Offer` element, then creates a sequence and transmits the `CreateSequenceResponse` message with an `Accept` element.</span></span>

#### <a name="sequence-lifetime"></a><span data-ttu-id="7e94f-288">Durata della sequenza</span><span class="sxs-lookup"><span data-stu-id="7e94f-288">Sequence Lifetime</span></span>

<span data-ttu-id="7e94f-289">WCF tratta le due sequenze come una sessione completamente duplex.</span><span class="sxs-lookup"><span data-stu-id="7e94f-289">WCF treats the two sequences as one fully-duplex session.</span></span>

<span data-ttu-id="7e94f-290">Quando si genera un errore che genera errori in una sequenza, WCF prevede che l'endpoint remoto errori entrambe le sequenze.</span><span class="sxs-lookup"><span data-stu-id="7e94f-290">Upon generating a fault that faults one sequence, WCF expects the remote endpoint to fault both sequences.</span></span> <span data-ttu-id="7e94f-291">Durante la lettura di un errore che genera errori in una sequenza, WCF genera errori in entrambe le sequenze.</span><span class="sxs-lookup"><span data-stu-id="7e94f-291">Upon reading a fault that faults one sequence, WCF faults both sequences.</span></span>

<span data-ttu-id="7e94f-292">WCF può chiudere la sequenza in uscita e continuare a elaborare i messaggi sulla relativa sequenza in ingresso.</span><span class="sxs-lookup"><span data-stu-id="7e94f-292">WCF can close its outbound sequence and continue to process messages on its inbound sequence.</span></span> <span data-ttu-id="7e94f-293">Viceversa, WCF può elaborare la chiusura della sequenza in ingresso e continuare a inviare messaggi sulla relativa sequenza in uscita.</span><span class="sxs-lookup"><span data-stu-id="7e94f-293">Conversely, WCF can process the close of the inbound sequence and continue to send messages on its outbound sequence.</span></span>

### <a name="request-reply-and-one-way-non-addressable-initiator"></a><span data-ttu-id="7e94f-294">Iniziatore request/reply e unidirezionale, non indirizzabile</span><span class="sxs-lookup"><span data-stu-id="7e94f-294">Request-Reply and One-Way, Non-Addressable Initiator</span></span>

#### <a name="binding"></a><span data-ttu-id="7e94f-295">Binding</span><span class="sxs-lookup"><span data-stu-id="7e94f-295">Binding</span></span>

<span data-ttu-id="7e94f-296">WCF fornisce un modello di scambio di messaggi unidirezionale e Request/Reply utilizzando due sequenze su un canale HTTP.</span><span class="sxs-lookup"><span data-stu-id="7e94f-296">WCF provides a one-way and request-reply message exchange pattern using two sequences over one HTTP channel.</span></span> <span data-ttu-id="7e94f-297">WCF utilizza le richieste HTTP per trasmettere tutti i messaggi dall'iniziatore alle risposte del risponditore e HTTP per trasmettere tutti i messaggi dal risponditore all'iniziatore.</span><span class="sxs-lookup"><span data-stu-id="7e94f-297">WCF uses HTTP requests to transmit all messages from the Initiator to the Responder and HTTP responses to transmit all messages from the Responder to the Initiator.</span></span>

#### <a name="createsequence-exchange"></a><span data-ttu-id="7e94f-298">Scambio CreateSequence</span><span class="sxs-lookup"><span data-stu-id="7e94f-298">CreateSequence Exchange</span></span>

<span data-ttu-id="7e94f-299">L'iniziatore WCF trasmette un messaggio di `CreateSequence` con un elemento `Offer` su una richiesta HTTP e attende il messaggio di `CreateSequenceResponse` sulla risposta HTTP.</span><span class="sxs-lookup"><span data-stu-id="7e94f-299">The WCF Initiator transmits a `CreateSequence` message with an `Offer` element on an HTTP request and expects the `CreateSequenceResponse` message on the HTTP response.</span></span> <span data-ttu-id="7e94f-300">Il risponditore WCF crea una sequenza e trasmette il messaggio di `CreateSequenceResponse` con un elemento `Accept` sulla risposta HTTP.</span><span class="sxs-lookup"><span data-stu-id="7e94f-300">The WCF Responder creates a sequence and transmits the `CreateSequenceResponse` message with an `Accept` element on the HTTP response.</span></span>

#### <a name="one-way-message"></a><span data-ttu-id="7e94f-301">Messaggio unidirezionale</span><span class="sxs-lookup"><span data-stu-id="7e94f-301">One-way Message</span></span>

<span data-ttu-id="7e94f-302">Per completare correttamente uno scambio di messaggi unidirezionale, l'iniziatore WCF trasmette un messaggio della sequenza di richiesta sulla richiesta HTTP e riceve un messaggio di `SequenceAcknowledgement` autonomo sulla risposta HTTP.</span><span class="sxs-lookup"><span data-stu-id="7e94f-302">To complete a one-way message exchange successfully, the WCF Initiator transmits a request sequence message on the HTTP request and receives a standalone `SequenceAcknowledgement` message on the HTTP response.</span></span> <span data-ttu-id="7e94f-303">`SequenceAcknowledgement` deve riconoscere il messaggio trasmesso.</span><span class="sxs-lookup"><span data-stu-id="7e94f-303">The `SequenceAcknowledgement` must acknowledge the message transmitted.</span></span>

<span data-ttu-id="7e94f-304">Il risponditore WCF può rispondere alla richiesta con un riconoscimento, un errore o una risposta con un corpo vuoto e un codice di stato HTTP 202.</span><span class="sxs-lookup"><span data-stu-id="7e94f-304">The WCF Responder may reply to the request with an acknowledgement, a fault, or a response with an empty body and HTTP 202 status code.</span></span>

#### <a name="two-way-messages"></a><span data-ttu-id="7e94f-305">Messaggi bidirezionali</span><span class="sxs-lookup"><span data-stu-id="7e94f-305">Two Way Messages</span></span>

<span data-ttu-id="7e94f-306">Per completare correttamente un protocollo di scambio di messaggi bidirezionale, l'iniziatore WCF trasmette un messaggio della sequenza di richiesta sulla richiesta HTTP e riceve un messaggio della sequenza di risposta nella risposta HTTP.</span><span class="sxs-lookup"><span data-stu-id="7e94f-306">To complete a two way message exchange protocol successfully, the WCF Initiator transmits a request sequence message on the HTTP request and receives a reply sequence message on the HTTP response.</span></span> <span data-ttu-id="7e94f-307">La risposta deve contenere un `SequenceAcknowledgement` che riconosce che il messaggio della sequenza di richiesta è stato trasmesso.</span><span class="sxs-lookup"><span data-stu-id="7e94f-307">The response must carry a `SequenceAcknowledgement` acknowledging the request sequence message transmitted.</span></span>

<span data-ttu-id="7e94f-308">Il risponditore WCF può rispondere alla richiesta con una risposta dell'applicazione, un errore o una risposta con un corpo vuoto e un codice di stato HTTP 202.</span><span class="sxs-lookup"><span data-stu-id="7e94f-308">The WCF Responder may reply to the request with an application reply, a fault or a response with an empty body and HTTP 202 status code.</span></span>

<span data-ttu-id="7e94f-309">A causa della presenza di messaggi unidirezionali e del tempo delle risposte dell'applicazione, il numero di sequenza del messaggio della sequenza di richiesta e il numero di sequenza del messaggio di risposta non hanno alcuna correlazione.</span><span class="sxs-lookup"><span data-stu-id="7e94f-309">Because of the presence of one-way messages and the timing of application replies, the request sequence message’s sequence number and the response message’s sequence number have no correlation.</span></span>

#### <a name="retrying-replies"></a><span data-ttu-id="7e94f-310">Nuovi tentativi di risposte</span><span class="sxs-lookup"><span data-stu-id="7e94f-310">Retrying Replies</span></span>

<span data-ttu-id="7e94f-311">WCF si basa sulla correlazione request/reply HTTP per la correlazione tra protocolli di scambio di messaggi bidirezionali.</span><span class="sxs-lookup"><span data-stu-id="7e94f-311">WCF relies on HTTP request-reply correlation for two-way message exchange protocol correlation.</span></span> <span data-ttu-id="7e94f-312">Per questo motivo, l'iniziatore WCF non interrompe il nuovo tentativo di un messaggio della sequenza di richiesta quando il messaggio della sequenza di richiesta viene riconosciuto, ma piuttosto quando la risposta HTTP contiene un `SequenceAcknowledgement`, una risposta dell'applicazione o un errore.</span><span class="sxs-lookup"><span data-stu-id="7e94f-312">Because of this, the WCF Initiator does not stop retrying a request sequence message when the request sequence message is acknowledged but rather when the HTTP response carries a `SequenceAcknowledgement`, application reply, or fault.</span></span> <span data-ttu-id="7e94f-313">Il risponditore WCF ritenta le risposte sulla risposta HTTP della richiesta a cui è correlata la risposta.</span><span class="sxs-lookup"><span data-stu-id="7e94f-313">The WCF Responder retries replies on the HTTP response of the request to which the reply is correlated.</span></span>

#### <a name="closesequence-exchange"></a><span data-ttu-id="7e94f-314">Scambio CloseSequence</span><span class="sxs-lookup"><span data-stu-id="7e94f-314">CloseSequence Exchange</span></span>

<span data-ttu-id="7e94f-315">Dopo aver ricevuto tutti i messaggi della sequenza di risposta e i riconoscimenti per tutti i messaggi della sequenza di richiesta unidirezionale, l'iniziatore WCF trasmette un messaggio di `CloseSequence` per la sequenza di richiesta su una richiesta HTTP e prevede l'`CloseSequenceResponse` sulla risposta HTTP.</span><span class="sxs-lookup"><span data-stu-id="7e94f-315">After receiving all reply sequence messages and acknowledgements for all one way request sequence messages, the WCF Initiator transmits a `CloseSequence` message for the request sequence on an HTTP request and expects the `CloseSequenceResponse` on the HTTP response.</span></span>

<span data-ttu-id="7e94f-316">Se la sequenza di richiesta viene chiusa in modo implicito, viene chiusa anche la sequenza di risposta.</span><span class="sxs-lookup"><span data-stu-id="7e94f-316">Closing the request sequence implicitly closes the reply sequence.</span></span> <span data-ttu-id="7e94f-317">Ciò significa che l'iniziatore WCF include il `SequenceAcknowledgement` finale della sequenza di risposta sul messaggio di `CloseSequence` e che la sequenza di risposta non ha un `CloseSequence` Exchange.</span><span class="sxs-lookup"><span data-stu-id="7e94f-317">This means the WCF Initiator includes the reply sequence’s Final `SequenceAcknowledgement` on the `CloseSequence` message and the reply sequence does not have a `CloseSequence` exchange.</span></span>

<span data-ttu-id="7e94f-318">Il risponditore WCF garantisce che tutte le risposte siano riconosciute e trasmette il messaggio `CloseSequenceResponse` sulla risposta HTTP.</span><span class="sxs-lookup"><span data-stu-id="7e94f-318">The WCF Responder ensures all replies are acknowledged and transmits the `CloseSequenceResponse` message on the HTTP response.</span></span>

#### <a name="terminatesequence-exchange"></a><span data-ttu-id="7e94f-319">Scambio TerminateSequence</span><span class="sxs-lookup"><span data-stu-id="7e94f-319">TerminateSequence Exchange</span></span>

<span data-ttu-id="7e94f-320">Dopo la ricezione del messaggio di `CloseSequenceResponse`, l'iniziatore WCF trasmette un messaggio di `TerminateSequence` per la sequenza di richiesta su una richiesta HTTP e attende il `TerminateSequenceResponse` sulla risposta HTTP.</span><span class="sxs-lookup"><span data-stu-id="7e94f-320">After receiving the `CloseSequenceResponse` message, the WCF Initiator transmits a `TerminateSequence` message for the request sequence on an HTTP request and expects the `TerminateSequenceResponse` on the HTTP response.</span></span>

<span data-ttu-id="7e94f-321">Analogamente allo scambio `CloseSequence`, la terminazione della sequenza di richiesta in modo implicito termina la sequenza di risposta.</span><span class="sxs-lookup"><span data-stu-id="7e94f-321">Like the `CloseSequence` exchange, terminating the request sequence implicitly terminates the reply sequence.</span></span> <span data-ttu-id="7e94f-322">Ciò significa che l'iniziatore WCF include il `SequenceAcknowledgement` finale della sequenza di risposta sul messaggio di `TerminateSequence` e che la sequenza di risposta non ha un `TerminateSequence` Exchange.</span><span class="sxs-lookup"><span data-stu-id="7e94f-322">This means the WCF Initiator includes the reply sequence’s final `SequenceAcknowledgement` on the `TerminateSequence` message and the reply sequence does not have a `TerminateSequence` exchange.</span></span>

<span data-ttu-id="7e94f-323">Il risponditore WCF trasmette il messaggio `TerminateSequenceResponse` sulla risposta HTTP.</span><span class="sxs-lookup"><span data-stu-id="7e94f-323">The WCF Responder transmits the `TerminateSequenceResponse` message on the HTTP response.</span></span>

### <a name="requestreply-addressable-initiator"></a><span data-ttu-id="7e94f-324">Iniziatore request/reply, indirizzabile</span><span class="sxs-lookup"><span data-stu-id="7e94f-324">Request/Reply, Addressable Initiator</span></span>

#### <a name="binding"></a><span data-ttu-id="7e94f-325">Binding</span><span class="sxs-lookup"><span data-stu-id="7e94f-325">Binding</span></span>

<span data-ttu-id="7e94f-326">WCF fornisce un modello di scambio di messaggi request/reply utilizzando due sequenze su un canale HTTP in ingresso e su uno in uscita.</span><span class="sxs-lookup"><span data-stu-id="7e94f-326">WCF provides a request-reply message exchange pattern using two sequences over one inbound and one outbound HTTP channel.</span></span> <span data-ttu-id="7e94f-327">Questo modello di scambio può essere combinato con il modello di scambio di messaggi dell'iniziatore `Duplex, Addressable` in modo limitato.</span><span class="sxs-lookup"><span data-stu-id="7e94f-327">This message exchange pattern can be mixed with the `Duplex, Addressable` Initiator message exchange pattern in a limited way.</span></span> <span data-ttu-id="7e94f-328">WCF utilizza le richieste HTTP per trasmettere tutti i messaggi.</span><span class="sxs-lookup"><span data-stu-id="7e94f-328">WCF uses the HTTP requests to transmit all messages.</span></span> <span data-ttu-id="7e94f-329">Tutte le risposte HTTP hanno un corpo vuoto e un codice di stato HTTP 202.</span><span class="sxs-lookup"><span data-stu-id="7e94f-329">All HTTP responses have an empty body and HTTP 202 status code.</span></span>

#### <a name="createsequence-exchange"></a><span data-ttu-id="7e94f-330">Scambio CreateSequence</span><span class="sxs-lookup"><span data-stu-id="7e94f-330">CreateSequence Exchange</span></span>

<span data-ttu-id="7e94f-331">L'iniziatore WCF trasmette un messaggio di `CreateSequence` con un elemento `Offer` su una richiesta HTTP.</span><span class="sxs-lookup"><span data-stu-id="7e94f-331">The WCF Initiator transmits a `CreateSequence` message with an `Offer` element on an HTTP request.</span></span> <span data-ttu-id="7e94f-332">Il risponditore WCF garantisce che il `CreateSequence` disponga di un elemento `Offer` quindi crea una sequenza e trasmette il messaggio `CreateSequenceResponse` con un elemento `Accept`.</span><span class="sxs-lookup"><span data-stu-id="7e94f-332">The WCF Responder ensures that the `CreateSequence` has an `Offer` element then creates a sequence and transmits the `CreateSequenceResponse` message with an `Accept` element.</span></span>

#### <a name="requestreply-correlation"></a><span data-ttu-id="7e94f-333">Correlazione request/reply</span><span class="sxs-lookup"><span data-stu-id="7e94f-333">Request/Reply Correlation</span></span>

<span data-ttu-id="7e94f-334">Quanto riportato di seguito si applica a tutte le richieste e le risposte correlate:</span><span class="sxs-lookup"><span data-stu-id="7e94f-334">The following applies to all correlated requests and replies:</span></span>

- <span data-ttu-id="7e94f-335">WCF garantisce che tutti i messaggi di richiesta dell'applicazione contengano un riferimento `ReplyTo` endpoint e una `MessageId`.</span><span class="sxs-lookup"><span data-stu-id="7e94f-335">WCF ensures all application request messages bear a `ReplyTo` endpoint reference and a `MessageId`.</span></span>

- <span data-ttu-id="7e94f-336">WCF applica il riferimento all'endpoint locale come `ReplyTo`del messaggio di richiesta dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="7e94f-336">WCF applies the local endpoint reference as each application request message’s `ReplyTo`.</span></span> <span data-ttu-id="7e94f-337">Il riferimento dell'endpoint locale è `CreateSequence` del messaggio `ReplyTo` per l'iniziatore e `CreateSequence` del messaggio `To` per il risponditore.</span><span class="sxs-lookup"><span data-stu-id="7e94f-337">The local endpoint reference is the `CreateSequence` message’s `ReplyTo` for the Initiator and the `CreateSequence` message’s `To` for the Responder.</span></span>

- <span data-ttu-id="7e94f-338">WCF garantisce che i messaggi di richiesta in ingresso contengano un `MessageId` e una `ReplyTo`.</span><span class="sxs-lookup"><span data-stu-id="7e94f-338">WCF ensures that incoming request messages bear a `MessageId` and a `ReplyTo`.</span></span>

- <span data-ttu-id="7e94f-339">WCF garantisce che l'URI del riferimento dell'endpoint del `ReplyTo` di tutti i messaggi di richiesta dell'applicazione corrisponda al riferimento all'endpoint locale definito in precedenza.</span><span class="sxs-lookup"><span data-stu-id="7e94f-339">WCF ensures the `ReplyTo` endpoint reference’s URI of all application request messages match the local endpoint reference as defined earlier.</span></span>

- <span data-ttu-id="7e94f-340">WCF garantisce che tutte le risposte contengano le intestazioni `RelatesTo` e `To` corrette seguenti `wsa` regole di correlazione request/reply.</span><span class="sxs-lookup"><span data-stu-id="7e94f-340">WCF ensures that all replies bear the correct `RelatesTo` and `To` headers following `wsa` request/reply correlation rules.</span></span>
