---
title: Protocollo Reliable Messaging versione 1.0
ms.date: 03/30/2017
ms.assetid: a5509a5c-de24-4bc2-9a48-19138055dcce
ms.openlocfilehash: ef45df0f1cae1f20cf34d07d154baee2cad34b29
ms.sourcegitcommit: ee5b798427f81237a3c23d1fd81fff7fdc21e8d3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/28/2020
ms.locfileid: "84143445"
---
# <a name="reliable-messaging-protocol-version-10"></a><span data-ttu-id="2dc6d-102">Protocollo Reliable Messaging versione 1.0</span><span class="sxs-lookup"><span data-stu-id="2dc6d-102">Reliable Messaging Protocol version 1.0</span></span>

<span data-ttu-id="2dc6d-103">In questo argomento vengono illustrati i dettagli di implementazione di Windows Communication Foundation (WCF) per il protocollo WS-Reliable Messaging February 2005 (versione 1,0) necessario per l'interoperabilità tramite il trasporto HTTP.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-103">This topic covers Windows Communication Foundation (WCF) implementation details for the WS-Reliable Messaging February 2005 (version 1.0) protocol necessary for interoperation using the HTTP transport.</span></span> <span data-ttu-id="2dc6d-104">WCF segue la specifica WS-Reliable Messaging con i vincoli e i chiarimenti illustrati in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-104">WCF follows the WS-Reliable Messaging specification with the constraints and clarifications explained in this topic.</span></span> <span data-ttu-id="2dc6d-105">Si noti che il protocollo WS-ReliableMessaging versione 1,0 viene implementato a partire da WinFX.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-105">Note that the WS-ReliableMessaging version 1.0 protocol is implemented starting with the WinFX.</span></span>

<span data-ttu-id="2dc6d-106">Il protocollo WS-Reliable Messaging 2005 viene implementato in WCF da <xref:System.ServiceModel.Channels.ReliableSessionBindingElement> .</span><span class="sxs-lookup"><span data-stu-id="2dc6d-106">The WS-Reliable Messaging February 2005 protocol is implemented in WCF by the <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>.</span></span>

<span data-ttu-id="2dc6d-107">Per comodità, nell'argomento vengono utilizzati i ruoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="2dc6d-107">For convenience, the topic uses the following roles:</span></span>

- <span data-ttu-id="2dc6d-108">Iniziatore: il client che avvia la creazione della sequenza di WS-Reliable Message.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-108">Initiator: the client that initiates WS-Reliable Message sequence creation</span></span>

- <span data-ttu-id="2dc6d-109">Risponditore: il servizio che riceve le richieste dell'iniziatore.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-109">Responder: the service that receives the initiator's requests</span></span>

<span data-ttu-id="2dc6d-110">In questo documento vengono utilizzati i prefissi e gli spazi dei nomi riportati nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-110">This document uses the prefixes and namespaces in the following table.</span></span>

|<span data-ttu-id="2dc6d-111">Prefisso</span><span class="sxs-lookup"><span data-stu-id="2dc6d-111">Prefix</span></span>|<span data-ttu-id="2dc6d-112">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="2dc6d-112">Namespace</span></span>|
|------------|---------------|
|<span data-ttu-id="2dc6d-113">wsrm</span><span class="sxs-lookup"><span data-stu-id="2dc6d-113">wsrm</span></span>|`http://schemas.xmlsoap.org/ws/2005/02/rm`|
|<span data-ttu-id="2dc6d-114">netrm</span><span class="sxs-lookup"><span data-stu-id="2dc6d-114">netrm</span></span>|`http://schemas.microsoft.com/ws/2006/05/rm`|
|<span data-ttu-id="2dc6d-115">s</span><span class="sxs-lookup"><span data-stu-id="2dc6d-115">s</span></span>|`http://www.w3.org/2003/05/soap-envelope`|
|<span data-ttu-id="2dc6d-116">wsa</span><span class="sxs-lookup"><span data-stu-id="2dc6d-116">wsa</span></span>|`http://schemas.xmlsoap.org/ws/2005/08/addressing|
|<span data-ttu-id="2dc6d-117">wsse</span><span class="sxs-lookup"><span data-stu-id="2dc6d-117">wsse</span></span>|`http://docs.oasis-open.org/wss/2004/01/oasis-200401-wssecurity-secext-1.0.xsd`|

## <a name="messaging"></a><span data-ttu-id="2dc6d-118">Messaggistica</span><span class="sxs-lookup"><span data-stu-id="2dc6d-118">Messaging</span></span>

### <a name="sequence-establishment-messages"></a><span data-ttu-id="2dc6d-119">Messaggi di definizione sequenza</span><span class="sxs-lookup"><span data-stu-id="2dc6d-119">Sequence Establishment Messages</span></span>

<span data-ttu-id="2dc6d-120">WCF implementa `CreateSequence` `CreateSequenceResponse` i messaggi e per stabilire una sequenza di messaggi affidabile.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-120">WCF implements `CreateSequence` and `CreateSequenceResponse` messages to establish a reliable message sequence.</span></span> <span data-ttu-id="2dc6d-121">Si applicano i vincoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="2dc6d-121">The following constraints apply:</span></span>

- <span data-ttu-id="2dc6d-122">B1101: l'iniziatore WCF non genera l'elemento Expires facoltativo nel `CreateSequence` messaggio o, nei casi in cui il `CreateSequence` messaggio contiene un `Offer` elemento, l'elemento facoltativo `Expires` nell' `Offer` elemento.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-122">B1101: The WCF Initiator does not generate the optional Expires element in the `CreateSequence` message or, in the cases when the `CreateSequence` message contains an `Offer` element, the optional `Expires` element in the `Offer` element.</span></span>

- <span data-ttu-id="2dc6d-123">B1102: quando si accede al `CreateSequence` messaggio, WCF `Responder` Invia e riceve entrambi `Expires` gli elementi, se esistenti, ma non ne utilizza i valori.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-123">B1102: When accessing the `CreateSequence` message, the WCF`Responder` sends and receives both `Expires` elements if they exist, but does not use their values.</span></span>

<span data-ttu-id="2dc6d-124">Con il protocollo WS-ReliableMessaging viene introdotto il meccanismo `Offer` che consente di stabilire le due sequenze correlate opposte che formano una sessione.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-124">WS-Reliable Messaging introduces the `Offer` mechanism to establish the two converse correlated sequences that form a session.</span></span>

- <span data-ttu-id="2dc6d-125">R1103: se `CreateSequence` contiene un elemento `Offer`, il risponditore Reliable Messaging deve accettare la sequenza e rispondere con `CreateSequenceResponse` contenente un elemento `wsrm:Accept`, formando due sequenze correlate opposte, oppure rifiutare la richiesta `CreateSequence`.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-125">R1103: If `CreateSequence` contains an `Offer` element, the Reliable Messaging Responder must either accept the sequence and respond with `CreateSequenceResponse` that contains a `wsrm:Accept` element, forming two correlated converse sequences or reject the `CreateSequence` request.</span></span>

- <span data-ttu-id="2dc6d-126">R1104: i messaggi `SequenceAcknowledgement` e dell'applicazione in transito sulla sequenza opposta devono essere inviati al riferimento endpoint `ReplyTo` di `CreateSequence`.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-126">R1104: `SequenceAcknowledgement` and application messages flowing on converse sequence must be sent to the `ReplyTo` endpoint reference of the `CreateSequence`.</span></span>

- <span data-ttu-id="2dc6d-127">R1105: i riferimenti endpoint `AcksTo` e `ReplyTo` in `CreateSequence` devono presentare valori indirizzo che corrispondano all'ottetto.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-127">R1105: `AcksTo` and `ReplyTo` endpoint references in the `CreateSequence` must have address values that match the octet-wise.</span></span>

  <span data-ttu-id="2dc6d-128">Il risponditore WCF verifica che la parte URI di `AcksTo` e `ReplyTo` EPRs sia identica prima di creare una sequenza.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-128">The WCF Responder verifies that the URI portion of the `AcksTo` and `ReplyTo` EPRs are identical before creating a sequence.</span></span>

- <span data-ttu-id="2dc6d-129">R1106: i riferimenti endpoint `AcksTo`e `ReplyTo` in `CreateSequence` devono avere lo stesso set di parametri per riferimento.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-129">R1106: `AcksTo` and `ReplyTo` Endpoint References in the `CreateSequence` should have the same set of reference parameters.</span></span>

  <span data-ttu-id="2dc6d-130">WCF non impone, ma presuppone che i [parametri di riferimento] di `AcksTo` e `ReplyTo` on `CreateSequence` siano identici e utilizzino [parametri di riferimento] dal `ReplyTo` riferimento all'endpoint per i messaggi di riconoscimento e di sequenza opposta.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-130">WCF does not enforce but assumes that [reference parameters] of `AcksTo` and `ReplyTo` on `CreateSequence` are identical and uses [reference parameters] from `ReplyTo` endpoint reference for acknowledgements and converse sequence messages.</span></span>

- <span data-ttu-id="2dc6d-131">R1107: quando vengono stabilite due sequenze opposte tramite il meccanismo `Offer`, i messaggi dell'applicazione e `SequenceAcknowledgement` in transito sulle sequenze opposte devono essere inviati al riferimento all'endpoint `ReplyTo` di `CreateSequence`.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-131">R1107: When two converse sequences are established using the `Offer` mechanism, `SequenceAcknowledgement` and application messages flowing on converse sequences must be sent to the `ReplyTo` endpoint reference of the `CreateSequence`.</span></span>

- <span data-ttu-id="2dc6d-132">R1108: quando vengono stabilite due sequenze opposte mediante il meccanismo Offer, la proprietà `[address]` dell'elemento figlio del riferimento endpoint `wsrm:AcksTo` dell'elemento `wsrm:Accept` di `CreateSequenceResponse` deve corrispondere per numero di byte all'URI di destinazione di `CreateSequence`.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-132">R1108: When two converse sequences are established using the Offer mechanism, the `[address]` property of the `wsrm:AcksTo` Endpoint Reference child element of the `wsrm:Accept` element of the `CreateSequenceResponse` must match byte-wise the destination URI of the `CreateSequence`.</span></span>

- <span data-ttu-id="2dc6d-133">R1109: quando vengono stabilite due sequenze opposte tramite il meccanismo `Offer`, i messaggi inviati dall'iniziatore e gli acknowledgement a tali messaggi da parte del risponditore devono essere inviati allo stesso riferimento all'endpoint.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-133">R1109: When two converse sequences are established using the `Offer` mechanism, messages sent by initiator and acknowledgements to messages by responder must be sent to the same Endpoint Reference.</span></span>

  <span data-ttu-id="2dc6d-134">WCF utilizza WS-Reliable Messaging per stabilire sessioni affidabili tra l'iniziatore e il risponditore.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-134">WCF uses WS-Reliable Messaging to establish reliable sessions between the Initiator and Responder.</span></span> <span data-ttu-id="2dc6d-135">L'implementazione WS-Reliable Messaging di WCF fornisce una sessione affidabile per modelli di messaggistica unidirezionali, Request/Reply e full duplex.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-135">WCF's WS-Reliable Messaging implementation provides reliable session for one-way, request-reply and full duplex messaging patterns.</span></span> <span data-ttu-id="2dc6d-136">Il meccanismo WS-Reliable Messaging `Offer` in `CreateSequence` / `CreateSequenceResponse` consente di stabilire due sequenze opposte correlate e fornisce un protocollo di sessione adatto a tutti gli endpoint del messaggio.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-136">The WS-Reliable Messaging `Offer` mechanism on `CreateSequence`/`CreateSequenceResponse` lets you establish two correlated converse sequences, and provides a session protocol that is suitable for all message endpoints.</span></span> <span data-ttu-id="2dc6d-137">Poiché WCF fornisce una garanzia di sicurezza per tale sessione, inclusa la protezione end-to-end per l'integrità della sessione, è consigliabile assicurarsi che i messaggi destinati alla stessa parte arrivino alla stessa destinazione.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-137">Because WCF provides a security guarantee for such a session including end-to-end protection for session integrity, it is practical to ensure messages intended to the same party are arriving at the same destination.</span></span> <span data-ttu-id="2dc6d-138">Ciò consente anche il "piggy-backing" degli acknowledgement della sequenza sui messaggi dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-138">This also allows piggy-backing of sequence acknowledgements on application messages.</span></span> <span data-ttu-id="2dc6d-139">Pertanto, i vincoli R1104, R1105 e R1108 si applicano a WCF.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-139">Therefore, constraints R1104, R1105, and R1108 apply to WCF.</span></span>

<span data-ttu-id="2dc6d-140">Esempio di un messaggio `CreateSequence`.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-140">An example of a `CreateSequence` message.</span></span>

```xml
<s:Envelope>
  <s:Header>
    <a:Action s:mustUnderstand="1">
      http://schemas.xmlsoap.org/ws/2005/02/rm/CreateSequence
    </a:Action>
    <a:ReplyTo>
      <a:Address>
         http://Business456.com/clientA
      </a:Address>
    </a:ReplyTo>
    <a:MessageID>
      urn:uuid:addabbbf-60cb-44d3-8c5b-9e0841629a36
    </a:MessageID>
    <a:To s:mustUnderstand="1">
      http://Business456.com/clientA
    </a:To>
  </s:Header>
  <s:Body>
    <wsrm:CreateSequence>
      <wsrm:AcksTo>
       <wsa:Address>
         http://Business456.com/clientA
       </wsa:Address>
     </wsrm:AcksTo>
     <wsrm:Offer>
      <wsrm:Identifier>
        urn:uuid:0afb8d36-bf26-4776-b8cf-8c91fddb5496
      </wsrm:Identifier>
     </wsrm:Offer>
   </wsrm:CreateSequence>
  </s:Body>
</s:Envelope>
```

 <span data-ttu-id="2dc6d-141">Esempio di un messaggio `CreateSequenceResponse`.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-141">An example of a `CreateSequenceResponse` message.</span></span>

```xml
<s:Envelope>
  <s:Header>
    <a:Action s:mustUnderstand="1">
      http://schemas.xmlsoap.org/ws/2005/02/rm/CreateSequenceResponse
    </a:Action>
    <a:RelatesTo>
      urn:uuid:addabbbf-60cb-44d3-8c5b-9e0841629a36
    </a:RelatesTo>
    <a:To s:mustUnderstand="1">
      http://Business456.com/clientA
    </a:To>
  </s:Header>
  <s:Body>
   <wsrm:CreateSequenceResponse>
    <Identifier>
     urn:uuid:eea0a36c-b38a-43e8-8c76-2fabe2d76386
    </Identifier>
    <Accept>
    <AcksTo>
      <a:Address>
        http://BusinessABC.com/serviceA
      </a:Address>
    </AcksTo>
    </Accept>
   </wsrm:CreateSequenceResponse>
  </s:Body>
</s:Envelope>
```

### <a name="sequence"></a><span data-ttu-id="2dc6d-142">Sequenza</span><span class="sxs-lookup"><span data-stu-id="2dc6d-142">Sequence</span></span>

<span data-ttu-id="2dc6d-143">Di seguito è riportato un elenco di vincoli che si applicano alle sequenze:</span><span class="sxs-lookup"><span data-stu-id="2dc6d-143">The following is a list of constraints that apply to sequences:</span></span>

- <span data-ttu-id="2dc6d-144">B1201: WCF genera e accede ai numeri di sequenza non più elevati del `xs:long` valore inclusivo massimo, 9223372036854775807.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-144">B1201:WCF generates and accesses sequence numbers no higher than `xs:long`’s maximum inclusive value, 9223372036854775807.</span></span>

- <span data-ttu-id="2dc6d-145">B1202: WCF genera sempre un ultimo messaggio con corpo vuoto con l'URI dell'azione `http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage` .</span><span class="sxs-lookup"><span data-stu-id="2dc6d-145">B1202:WCF always generates an empty-bodied last message with the action URI of `http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage`.</span></span>

- <span data-ttu-id="2dc6d-146">B1203: WCF riceve e recapita un messaggio con un'intestazione di sequenza che contiene un `LastMessage` elemento purché l'URI dell'azione non sia `http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage` .</span><span class="sxs-lookup"><span data-stu-id="2dc6d-146">B1203: WCF receives and delivers a message with a Sequence header that contains a `LastMessage` element as long as the action URI is not `http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage`.</span></span>

<span data-ttu-id="2dc6d-147">Esempio di intestazione di sequenza.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-147">An example of a Sequence Header.</span></span>

```xml
<wsrm:Sequence>
  <wsrm:Identifier>
    urn:uuid:addabbbf-60cb-44d3-8c5b-9e0841629a36
  </wsrm:Identifier>
  <wsrm:MessageNumber>
    10
  </wsrm:MessageNumber>
  <wsrm:LastMessage/>
 </wsrm:Sequence>
```

### <a name="ackrequested-header"></a><span data-ttu-id="2dc6d-148">Intestazione AckRequested</span><span class="sxs-lookup"><span data-stu-id="2dc6d-148">AckRequested Header</span></span>

<span data-ttu-id="2dc6d-149">WCF utilizza `AckRequested` l'intestazione come meccanismo Keep-Alive.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-149">WCF uses `AckRequested` Header as a keep-alive mechanism.</span></span> <span data-ttu-id="2dc6d-150">WCF non genera l'elemento facoltativo `MessageNumber` .</span><span class="sxs-lookup"><span data-stu-id="2dc6d-150">WCF does not generate the optional `MessageNumber` element.</span></span> <span data-ttu-id="2dc6d-151">Quando riceve un messaggio con un' `AckRequested` intestazione che contiene l' `MessageNumber` elemento, WCF ignora il `MessageNumber` valore dell'elemento, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-151">Upon receiving a message with an `AckRequested` header that contains the `MessageNumber` element, WCF ignores the `MessageNumber` element’s value, as shown in the following example.</span></span>

```xml
<wsrm:AckRequested>
  <wsrm:Identifier>
    urn:uuid:addabbbf-60cb-44d3-8c5b-9e0841629a36
  </wsrm:Identifier>
</wsrm:AckRequested>
```

### <a name="sequenceacknowledgement-header"></a><span data-ttu-id="2dc6d-152">Intestazione SequenceAcknowledgement</span><span class="sxs-lookup"><span data-stu-id="2dc6d-152">SequenceAcknowledgement Header</span></span>

<span data-ttu-id="2dc6d-153">WCF utilizza un meccanismo di Piggy-Back per i riconoscimenti di sequenza forniti in WS-Reliable Messaging.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-153">WCF uses piggy-back mechanism for sequence acknowledgements provided in WS-Reliable Messaging.</span></span>

- <span data-ttu-id="2dc6d-154">R1401: quando vengono stabilite due sequenze opposte utilizzando il meccanismo `Offer`, l'intestazione `SequenceAcknowledgement` può essere inclusa in qualsiasi messaggio dell'applicazione trasmesso al destinatario desiderato.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-154">R1401: When two converse sequences are established using the `Offer` mechanism, the `SequenceAcknowledgement` header may be included in any application message transmitted to the intended recipient.</span></span>

- <span data-ttu-id="2dc6d-155">B1402: quando WCF deve generare un riconoscimento prima di ricevere messaggi di sequenza, ad esempio per soddisfare un `AckRequested` messaggio, WCF genera un' `SequenceAcknowledgement` intestazione che contiene l'intervallo 0-0, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-155">B1402: When WCF must generate an acknowledgement prior to receiving any sequence messages (for example, to satisfy an `AckRequested` message), WCF generates a `SequenceAcknowledgement` header that contains the range 0-0, as shown in the following example.</span></span>

  ```xml
  <wsrm:SequenceAcknowledgement>
    <wsrm:Identifier>
      urn:uuid:addabbbf-60cb-44d3-8c5b-9e0841629a36
    </wsrm:Identifier>
    <wsrm:AcknowledgementRange Upper="0" Lower="0"/>
  </wsrm:SequenceAcknowledgement>
  ```

- <span data-ttu-id="2dc6d-156">B1403: WCF non genera `SequenceAcknowledgement` intestazioni contenenti un `Nack` elemento ma supporta `Nack` gli elementi.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-156">B1403: WCF does not generate `SequenceAcknowledgement` headers that contain a `Nack` element but supports `Nack` elements.</span></span>

### <a name="ws-reliablemessaging-faults"></a><span data-ttu-id="2dc6d-157">Errori WS-ReliableMessaging</span><span class="sxs-lookup"><span data-stu-id="2dc6d-157">WS-ReliableMessaging Faults</span></span>

<span data-ttu-id="2dc6d-158">Di seguito è riportato un elenco di vincoli che si applicano all'implementazione WCF degli errori WS-Reliable Messaging:</span><span class="sxs-lookup"><span data-stu-id="2dc6d-158">The following is a list of constraints that apply to the WCF implementation of WS-Reliable Messaging faults:</span></span>

- <span data-ttu-id="2dc6d-159">B1501: WCF non genera `MessageNumberRollover` errori.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-159">B1501: WCF does not generate `MessageNumberRollover` faults.</span></span>

- <span data-ttu-id="2dc6d-160">B1502: l'endpoint WCF può generare `CreateSequenceRefused` errori come descritto nella specifica.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-160">B1502:WCF endpoint may generate `CreateSequenceRefused` faults as described in the specification.</span></span>

- <span data-ttu-id="2dc6d-161">B1503: quando l'endpoint del servizio raggiunge il limite di connessione e non è in grado di elaborare nuove connessioni, WCF genera un `CreateSequenceRefused` codice di errore aggiuntivo, `netrm:ConnectionLimitReached` , come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-161">B1503:When the service endpoint reaches its connection limit and cannot process new connections, WCF generates an additional `CreateSequenceRefused` fault subcode, `netrm:ConnectionLimitReached`, as shown in the following example.</span></span>

  ```xml
  <s:Envelope>
    <s:Header>
      <wsa:Action>
        http://schemas.xmlsoap.org/ws/2005/08/addressing/fault
      </wsa:Action>
    </s:Header>
    <s:Body>
      <s:Fault>
        <s:Code>
          <s:Value>
            s:Receiver
          </s:Value>
          <s:Subcode>
            <s:Value>
              wsrm:CreateSequenceRefused
            </s:Value>
            <s:Subcode>
              <s:Value>
                netrm:ConnectionLimitReached
              </s:Value>
            </s:Subcode>
          </s:Subcode>
        </s:Code>
        <s:Reason>
          <s:Text xml:lang="en">
            [Reason]
          </s:Text>
        </s:Reason>
      </s:Fault>
    </s:Body>
  </s:Envelope>
  ```

### <a name="ws-addressing-faults"></a><span data-ttu-id="2dc6d-162">Errori WS-Addressing</span><span class="sxs-lookup"><span data-stu-id="2dc6d-162">WS-Addressing Faults</span></span>

<span data-ttu-id="2dc6d-163">Poiché WS-Reliable Messaging utilizza WS-Addressing, l'implementazione di WCF WS-Reliable Messaging può generare errori di WS-Addressing.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-163">Because WS-Reliable Messaging uses WS-Addressing, WCF WS-Reliable Messaging implementation may generate WS-Addressing faults.</span></span> <span data-ttu-id="2dc6d-164">In questa sezione vengono illustrati gli errori WS-Addressing generati in modo esplicito da WCF al livello WS-Reliable Messaging:</span><span class="sxs-lookup"><span data-stu-id="2dc6d-164">This section covers the WS-Addressing faults that WCF explicitly generates at the WS-Reliable Messaging layer:</span></span>

- <span data-ttu-id="2dc6d-165">B1601: WCF genera l'intestazione di indirizzamento dei messaggi di errore necessaria quando si verifica una delle condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2dc6d-165">B1601:WCF generates the fault Message Addressing Header Required when one of the following is true:</span></span>

  - <span data-ttu-id="2dc6d-166">In un messaggio mancano un'intestazione `Sequence` e un'intestazione `Action`.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-166">A message is missing a `Sequence` header and an `Action` header.</span></span>

  - <span data-ttu-id="2dc6d-167">In un messaggio `CreateSequence` manca un'intestazione `MessageId`.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-167">A `CreateSequence` message is missing a `MessageId` header.</span></span>

  - <span data-ttu-id="2dc6d-168">In un messaggio `CreateSequence` manca un'intestazione `ReplyTo`.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-168">A `CreateSequence` message is missing a `ReplyTo` header.</span></span>

- <span data-ttu-id="2dc6d-169">B1602: WCF genera l'azione di errore non supportata in risposta a un messaggio in cui manca un' `Sequence` intestazione e ha un' `Action` intestazione non riconosciuta nella specifica WS-Reliable Messaging.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-169">B1602:WCF generates the fault Action Not Supported in reply to a message that is missing a `Sequence` header and has an `Action` header that is not a recognized in the WS-Reliable Messaging specification.</span></span>

- <span data-ttu-id="2dc6d-170">B1603: WCF genera l'endpoint di errore non disponibile per indicare che l'endpoint non elabora la sequenza in base all'esame delle `CreateSequence` intestazioni di indirizzamento del messaggio.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-170">B1603:WCF generates the fault Endpoint Unavailable to indicate that the endpoint does not process the sequence based upon examination of the `CreateSequence` message’s addressing headers.</span></span>

## <a name="protocol-composition"></a><span data-ttu-id="2dc6d-171">Composizione del protocollo</span><span class="sxs-lookup"><span data-stu-id="2dc6d-171">Protocol Composition</span></span>

### <a name="composition-with-ws-addressing"></a><span data-ttu-id="2dc6d-172">Composizione con WS-Addressing</span><span class="sxs-lookup"><span data-stu-id="2dc6d-172">Composition with WS-Addressing</span></span>

<span data-ttu-id="2dc6d-173">WCF supporta due versioni di WS-Addressing: WS-Addressing 2004/08 [WS-ADDR] e W3C WS-Addressing 1,0 raccomandazioni [WS-ADDR-CORE] e [WS-ADDR-SOAP].</span><span class="sxs-lookup"><span data-stu-id="2dc6d-173">WCF supports two versions of WS-Addressing: WS-Addressing 2004/08 [WS-ADDR] and W3C WS-Addressing 1.0 Recommendations [WS-ADDR-CORE] and [WS-ADDR-SOAP].</span></span>

<span data-ttu-id="2dc6d-174">Anche se la specifica WS-Reliable Messaging menziona solo WS-Addressing 2004/08, non limita la versione WS-Addressing da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-174">While the WS-Reliable Messaging specification mentions only WS-Addressing 2004/08, it does not restrict the WS-Addressing version to be used.</span></span> <span data-ttu-id="2dc6d-175">Di seguito è riportato un elenco di vincoli che si applicano a WCF:</span><span class="sxs-lookup"><span data-stu-id="2dc6d-175">The following is a list of constraints that apply to WCF:</span></span>

- <span data-ttu-id="2dc6d-176">R2101:sia WS-Addressing 2004/08 che WS-Addressing 1.0 possono essere utilizzati con WS-Reliable Messaging.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-176">R2101:Both WS-Addressing 2004/08 and WS-Addressing 1.0 can be used with WS-Reliable Messaging.</span></span>

- <span data-ttu-id="2dc6d-177">R2102: è necessario utilizzare una sola versione di WS-Addressing in una determinata sequenza di WS-Reliable Messaging o in una coppia di sequenze opposte correlate tramite il `wsrm:Offer` meccanismo.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-177">R2102:A single version of WS-Addressing must be used throughout a given WS-Reliable Messaging sequence or a pair of converse sequences correlated by using the `wsrm:Offer` mechanism.</span></span>

### <a name="composition-with-soap"></a><span data-ttu-id="2dc6d-178">Composizione con SOAP</span><span class="sxs-lookup"><span data-stu-id="2dc6d-178">Composition with SOAP</span></span>

<span data-ttu-id="2dc6d-179">WCF supporta l'utilizzo di SOAP 1,1 e SOAP 1,2 con WS-Reliable Messaging.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-179">WCF supports use of both SOAP 1.1 and SOAP 1.2 with WS-Reliable Messaging.</span></span>

### <a name="composition-with-ws-security-and-ws-secureconversation"></a><span data-ttu-id="2dc6d-180">Composizione con WS-Security e WS-SecureConversation</span><span class="sxs-lookup"><span data-stu-id="2dc6d-180">Composition with WS-Security and WS-SecureConversation</span></span>

<span data-ttu-id="2dc6d-181">WCF fornisce la protezione per le sequenze WS-Reliable Messaging usando il trasporto sicuro (HTTPS), la composizione con WS-Security e la composizione con WS-Secure Conversation.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-181">WCF provides protection for WS-Reliable Messaging sequences by using secure Transport (HTTPS), composition with WS-Security, and composition with WS-Secure Conversation.</span></span> <span data-ttu-id="2dc6d-182">Di seguito è riportato un elenco di vincoli che si applicano a WCF:</span><span class="sxs-lookup"><span data-stu-id="2dc6d-182">The following is a list of constraints that apply to WCF:</span></span>

- <span data-ttu-id="2dc6d-183">R2301: per proteggere l'integrità di una sequenza di WS-Reliable Messaging oltre all'integrità e alla riservatezza dei singoli messaggi, WCF richiede che sia necessario usare WS-Secure Conversation.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-183">R2301:To protect the integrity of a WS-Reliable Messaging sequence in addition to the integrity and confidentiality of individual messages, WCF requires that WS-Secure Conversation must be used.</span></span>

- <span data-ttu-id="2dc6d-184">R2302:prima di stabilire la/e sequenza/e di WS-Reliable Messaging, è necessario stabilire una sessione WS-SecureConversation.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-184">R2302:AWS-Secure Conversation session must be established prior to establishing WS-Reliable Messaging sequence(s).</span></span>

- <span data-ttu-id="2dc6d-185">R2303: se la durata della sequenza di WS-Reliable Messaging supera la durata della sessione WS-SecureConversation, è necessario rinnovare il `SecurityContextToken` stabilito tramite WS-SecureConversation utilizzando l'associazione WS-Secure Conversation Renewal corrispondente.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-185">R2303: If the WS-Reliable Messaging sequence lifetime exceeds the WS-Secure Conversation session’s lifetime, the `SecurityContextToken` established by using WS-Secure Conversation must be renewed by using the corresponding WS-Secure Conversation Renewal binding.</span></span>

- <span data-ttu-id="2dc6d-186">B2304: la sequenza di WS-Reliable Messaging o una coppia di sequenze opposte correlate sono sempre associate a una singola sessione WS-SecureConversation.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-186">B2304:WS-Reliable Messaging sequence or a pair of correlated converse sequences are always bound to a single WS-SecureConversation session.</span></span>

  <span data-ttu-id="2dc6d-187">L'origine WCF genera l' `wsse:SecurityTokenReference` elemento nella sezione di estendibilità degli elementi del `CreateSequence` messaggio.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-187">The WCF source generates the `wsse:SecurityTokenReference` element in the element extensibility section of the `CreateSequence` message.</span></span>

- <span data-ttu-id="2dc6d-188">R2305: se composto con WS-Secure Conversation, un `CreateSequence` messaggio deve contenere l' `wsse:SecurityTokenReference` elemento.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-188">R2305:When composed with WS-Secure Conversation, a `CreateSequence` message must contain the `wsse:SecurityTokenReference` element.</span></span>

## <a name="ws-reliable-messaging-ws-policy-assertion"></a><span data-ttu-id="2dc6d-189">Asserzione di WS-Policy relativa a WS-Reliable Messaging</span><span class="sxs-lookup"><span data-stu-id="2dc6d-189">WS-Reliable Messaging WS-Policy Assertion</span></span>

<span data-ttu-id="2dc6d-190">WCF usa l'asserzione WS-Policy WS-Reliable Messaging `wsrm:RMAssertion` per descrivere le funzionalità degli endpoint.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-190">WCF uses WS-Reliable Messaging WS-Policy Assertion `wsrm:RMAssertion` to describe endpoints capabilities.</span></span> <span data-ttu-id="2dc6d-191">Di seguito è riportato un elenco di vincoli che si applicano a WCF:</span><span class="sxs-lookup"><span data-stu-id="2dc6d-191">The following is a list of constraints that apply to WCF:</span></span>

- <span data-ttu-id="2dc6d-192">B3001: WCF connette l' `wsrm:RMAssertion` asserzione WS-Policy agli `wsdl:binding` elementi.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-192">B3001: WCF attaches `wsrm:RMAssertion` WS-Policy Assertion to `wsdl:binding` elements.</span></span> <span data-ttu-id="2dc6d-193">WCF supporta entrambi gli allegati `wsdl:binding` agli `wsdl:port` elementi e.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-193">WCF supports both attachments to `wsdl:binding` and `wsdl:port` elements.</span></span>

- <span data-ttu-id="2dc6d-194">B3002: WCF supporta le proprietà facoltative seguenti dell'asserzione WS-Reliable Messaging e ne fornisce il controllo su WCF `ReliableMessagingBindingElement` :</span><span class="sxs-lookup"><span data-stu-id="2dc6d-194">B3002: WCF supports the following optional properties of WS-Reliable Messaging assertion and provides control over them on the WCF`ReliableMessagingBindingElement`:</span></span>

  - `wsrm:InactivityTimeout`

  - `wsrm:AcknowledgementInterval`

  <span data-ttu-id="2dc6d-195">Di seguito è riportato un esempio.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-195">The following is an example.</span></span>

  ```xml
  <wsrm:RMAssertion>
    <wsrm:InactivityTimeout Milliseconds="600000" />
    <wsrm:AcknowledgementInterval Milliseconds="200" />
  </wsrm:RMAssertion>
  ```

## <a name="flow-control-ws-reliable-messaging-extension"></a><span data-ttu-id="2dc6d-196">Estensione di WS-Reliable Messaging per il controllo del flusso</span><span class="sxs-lookup"><span data-stu-id="2dc6d-196">Flow Control WS-Reliable Messaging Extension</span></span>

<span data-ttu-id="2dc6d-197">WCF utilizza l'estensibilità WS-Reliable Messaging per offrire un controllo facoltativo aggiuntivo più rigido sul flusso di messaggi della sequenza.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-197">WCF uses WS-Reliable Messaging extensibility to provide optional additional tighter control over sequence message flow.</span></span>

<span data-ttu-id="2dc6d-198">Il controllo di flusso viene abilitato impostando la <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.FlowControlEnabled?displayProperty=nameWithType> proprietà su `true` .</span><span class="sxs-lookup"><span data-stu-id="2dc6d-198">Flow control is enabled by setting the <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.FlowControlEnabled?displayProperty=nameWithType> property to `true`.</span></span> <span data-ttu-id="2dc6d-199">Di seguito è riportato un elenco di vincoli che si applicano a WCF:</span><span class="sxs-lookup"><span data-stu-id="2dc6d-199">The following is a list of constraints that apply to WCF:</span></span>

- <span data-ttu-id="2dc6d-200">B4001: quando è abilitato il controllo di flusso di Reliable Messaging, WCF genera un `netrm:BufferRemaining` elemento nell'estendibilità dell'elemento dell' `SequenceAcknowledgement` intestazione.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-200">B4001: When Reliable Messaging Flow Control is enabled, WCF generates a `netrm:BufferRemaining` element in the element extensibility of the `SequenceAcknowledgement` header.</span></span>

- <span data-ttu-id="2dc6d-201">B4002: quando è abilitato il controllo di flusso di Reliable Messaging, WCF non richiede `netrm:BufferRemaining` che un elemento sia presente nell' `SequenceAcknowledgement` intestazione, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-201">B4002: When Reliable Messaging Flow Control is enabled, WCF does not require a `netrm:BufferRemaining` element to be present in `SequenceAcknowledgement` header, as shown in the following example.</span></span>

  ```xml
  <wsrm:SequenceAcknowledgement>
    <wsrm:Identifier>
      http://fabrikam123.com/abc
    </wsrm:Identifier>
    <wsrm:AcknowledgementRange Upper="1" Lower="1"/>
    <netrm:BufferRemaining>
      8
    </netrm:BufferRemaining>
  </wsrm:SequenceAcknowledgement>
  ```

- <span data-ttu-id="2dc6d-202">B4003: WCF USA `netrm:BufferRemaining` per indicare il numero di nuovi messaggi che la destinazione della messaggistica affidabile può memorizzare nel buffer.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-202">B4003: WCF uses `netrm:BufferRemaining` to indicate how many new messages the Reliable Messaging Destination can buffer.</span></span>

- <span data-ttu-id="2dc6d-203">B4004: il servizio WCF Reliable Messaging limita il numero di messaggi trasmessi quando l'applicazione di destinazione di Reliable Messaging non può ricevere rapidamente messaggi.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-203">B4004:The WCF Reliable Messaging Service throttles the number of messages transmitted when the Reliable Messaging destination application cannot receive messages quickly.</span></span> <span data-ttu-id="2dc6d-204">La destinazione Reliable Messaging memorizza nel buffer messaggi e il valore dell'elemento scende a 0.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-204">The Reliable Messaging destination buffers messages and the element’s value drops to 0.</span></span>

- <span data-ttu-id="2dc6d-205">B4005: WCF genera `netrm:BufferRemaining` valori integer compresi tra 0 e 4096 inclusivi e legge i valori integer compresi tra 0 e `xs:int` il `maxInclusive` valore 214748364 inclusi.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-205">B4005: WCF generates `netrm:BufferRemaining` integer values between 0 and 4096 inclusive, and reads integer values between 0 and `xs:int`’s `maxInclusive` value 214748364 inclusive.</span></span>

## <a name="message-exchange-patterns"></a><span data-ttu-id="2dc6d-206">Modelli di scambio dei messaggi</span><span class="sxs-lookup"><span data-stu-id="2dc6d-206">Message Exchange Patterns</span></span>

<span data-ttu-id="2dc6d-207">In questa sezione viene descritto il comportamento di WCF quando WS-Reliable Messaging viene utilizzato per modelli di scambio di messaggi diversi.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-207">This section describes WCF's behavior when WS-Reliable Messaging is used for different Message Exchange Patterns.</span></span> <span data-ttu-id="2dc6d-208">Per ogni modello di scambio di messaggi, vengono presi in considerazione i due scenari di distribuzione seguenti:</span><span class="sxs-lookup"><span data-stu-id="2dc6d-208">For each Message Exchange Pattern the following two deployments scenarios are considered:</span></span>

- <span data-ttu-id="2dc6d-209">Iniziatore non indirizzabile: l'iniziatore si trova dietro a un firewall; il risponditore può recapitare messaggi all'iniziatore solo su risposte HTTP.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-209">Non-Addressable Initiator: Initiator is behind firewall; Responder can deliver messages to Initiator only on HTTP responses.</span></span>

- <span data-ttu-id="2dc6d-210">Iniziatore indirizzabile: le richieste HTTP possono essere inviate sia all'iniziatore che al risponditore. In altre parole, è possibile stabilire due connessioni HTTP opposte.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-210">Addressable Initiator: Initiator and Responder both can be sent HTTP requests; in other words, two converse HTTP connections can be established.</span></span>

### <a name="one-way-non-addressable-initiator"></a><span data-ttu-id="2dc6d-211">Iniziatore unidirezionale, non indirizzabile</span><span class="sxs-lookup"><span data-stu-id="2dc6d-211">One-way, Non-addressable Initiator</span></span>

#### <a name="binding"></a><span data-ttu-id="2dc6d-212">Associazione</span><span class="sxs-lookup"><span data-stu-id="2dc6d-212">Binding</span></span>

<span data-ttu-id="2dc6d-213">WCF fornisce un modello di scambio di messaggi unidirezionale utilizzando una sequenza su un canale HTTP.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-213">WCF provides a one-way message exchange pattern using one sequence over one HTTP channel.</span></span> <span data-ttu-id="2dc6d-214">WCF usa le richieste HTTP per trasmettere tutti i messaggi da RMS a RMD e la risposta HTTP per trasmettere tutti i messaggi da RMD a RMS.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-214">WCF uses the HTTP requests to transmit all messages from the RMS to the RMD and the HTTP response to transmit all messages from the RMD to the RMS.</span></span>

#### <a name="createsequence-exchange"></a><span data-ttu-id="2dc6d-215">Scambio CreateSequence</span><span class="sxs-lookup"><span data-stu-id="2dc6d-215">CreateSequence Exchange</span></span>

<span data-ttu-id="2dc6d-216">L'iniziatore WCF genera un `CreateSequence` messaggio senza alcuna offerta.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-216">The WCF Initiator generates a `CreateSequence` message with no offer.</span></span> <span data-ttu-id="2dc6d-217">Il risponditore WCF garantisce che `CreateSequence` non abbia un'offerta prima di creare una sequenza.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-217">The WCF Responder ensures the `CreateSequence` has no offer before creating a sequence.</span></span> <span data-ttu-id="2dc6d-218">Il risponditore WCF risponde alla `CreateSequence` richiesta con un `CreateSequenceResponse` messaggio.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-218">The WCF Responder replies to the `CreateSequence` request with a `CreateSequenceResponse` message.</span></span>

#### <a name="sequenceacknowledgement"></a><span data-ttu-id="2dc6d-219">SequenceAcknowledgement</span><span class="sxs-lookup"><span data-stu-id="2dc6d-219">SequenceAcknowledgement</span></span>

<span data-ttu-id="2dc6d-220">L'iniziatore WCF elabora i riconoscimenti della risposta di tutti i messaggi ad eccezione dei `CreateSequence` messaggi di errore e di messaggio.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-220">The WCF Initiator processes acknowledgements on the reply of all messages except the `CreateSequence` message and fault messages.</span></span> <span data-ttu-id="2dc6d-221">Il risponditore WCF genera sempre un riconoscimento autonomo nella risposta alla sequenza e ai `AckRequested` messaggi.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-221">The WCF Responder always generates a stand-alone acknowledgement in the response to both sequence and `AckRequested` messages.</span></span>

#### <a name="terminatesequence-message"></a><span data-ttu-id="2dc6d-222">Messaggio TerminateSequence</span><span class="sxs-lookup"><span data-stu-id="2dc6d-222">TerminateSequence message</span></span>

<span data-ttu-id="2dc6d-223">WCF `TerminateSequence` viene considerato come un'operazione unidirezionale, ovvero la risposta http ha un corpo vuoto e un codice di stato HTTP 202.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-223">WCF treats `TerminateSequence` as a one-way operation, meaning the HTTP response has an empty body and HTTP 202 status code.</span></span>

### <a name="one-way-addressable-initiator"></a><span data-ttu-id="2dc6d-224">Iniziatore unidirezionale, indirizzabile</span><span class="sxs-lookup"><span data-stu-id="2dc6d-224">One Way, Addressable Initiator</span></span>

#### <a name="binding"></a><span data-ttu-id="2dc6d-225">Associazione</span><span class="sxs-lookup"><span data-stu-id="2dc6d-225">Binding</span></span>

<span data-ttu-id="2dc6d-226">WCF fornisce un modello di scambio di messaggi unidirezionale utilizzando una sequenza su un canale HTTP in ingresso e in uscita.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-226">WCF provides a one-way message exchange pattern using one sequence over an inbound and an outbound Http channel.</span></span> <span data-ttu-id="2dc6d-227">WCF utilizza le richieste HTTP per trasmettere tutti i messaggi.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-227">WCF uses the HTTP requests to transmit all messages.</span></span> <span data-ttu-id="2dc6d-228">Tutte le risposte HTTP hanno un corpo vuoto e un codice di stato HTTP 202.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-228">All HTTP responses have an empty body and HTTP 202 status code.</span></span>

#### <a name="createsequence-exchange"></a><span data-ttu-id="2dc6d-229">Scambio CreateSequence</span><span class="sxs-lookup"><span data-stu-id="2dc6d-229">CreateSequence Exchange</span></span>

<span data-ttu-id="2dc6d-230">L'iniziatore WCF genera un `CreateSequence` messaggio senza alcuna offerta.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-230">The WCF Initiator generates a `CreateSequence` message with no offer.</span></span> <span data-ttu-id="2dc6d-231">Il risponditore WCF garantisce che `CreateSequence` non abbia un'offerta prima di creare una sequenza.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-231">The WCF Responder ensures that the `CreateSequence` has no offer before creating a sequence.</span></span> <span data-ttu-id="2dc6d-232">Il risponditore WCF trasmette il `CreateSequenceResponse` messaggio su una richiesta http risolta con il `ReplyTo` riferimento all'endpoint.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-232">The WCF Responder transmits the `CreateSequenceResponse` message on an HTTP request addressed with the `ReplyTo` endpoint reference.</span></span>

### <a name="duplex-addressable-initiator"></a><span data-ttu-id="2dc6d-233">Iniziatore duplex, indirizzabile</span><span class="sxs-lookup"><span data-stu-id="2dc6d-233">Duplex, Addressable Initiator</span></span>

#### <a name="binding"></a><span data-ttu-id="2dc6d-234">Associazione</span><span class="sxs-lookup"><span data-stu-id="2dc6d-234">Binding</span></span>

<span data-ttu-id="2dc6d-235">WCF fornisce un modello di scambio di messaggi bidirezionale completamente asincrono utilizzando due sequenze su un canale HTTP in ingresso e in uscita.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-235">WCF provides a fully asynchronous two-way message exchange pattern using two sequences over an inbound and an outbound HTTP channel.</span></span> <span data-ttu-id="2dc6d-236">WCF utilizza le richieste HTTP per trasmettere tutti i messaggi.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-236">WCF uses the HTTP requests to transmit all messages.</span></span> <span data-ttu-id="2dc6d-237">Tutte le risposte HTTP hanno un corpo vuoto e un codice di stato HTTP 202.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-237">All HTTP responses have an empty body and HTTP 202 status code.</span></span>

#### <a name="createsequence-exchange"></a><span data-ttu-id="2dc6d-238">Scambio CreateSequence</span><span class="sxs-lookup"><span data-stu-id="2dc6d-238">CreateSequence Exchange</span></span>

<span data-ttu-id="2dc6d-239">L'iniziatore WCF genera un `CreateSequence` messaggio con un'offerta.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-239">The WCF Initiator generates a `CreateSequence` message with an offer.</span></span> <span data-ttu-id="2dc6d-240">Il risponditore WCF garantisce che `CreateSequence` abbia un'offerta prima di creare una sequenza.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-240">The WCF Responder ensures that the `CreateSequence` has an offer before creating a sequence.</span></span> <span data-ttu-id="2dc6d-241">WCF invia la `CreateSequenceResponse` sulla richiesta HTTP indirizzata al `CreateSequence` riferimento all' `ReplyTo` endpoint di.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-241">WCF sends the `CreateSequenceResponse` on the HTTP request addressed to the `CreateSequence`’s `ReplyTo` endpoint reference.</span></span>

#### <a name="sequence-lifetime"></a><span data-ttu-id="2dc6d-242">Durata della sequenza</span><span class="sxs-lookup"><span data-stu-id="2dc6d-242">Sequence Lifetime</span></span>

<span data-ttu-id="2dc6d-243">WCF tratta le due sequenze come una sessione completamente duplex.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-243">WCF treats the two sequences as one fully duplex session.</span></span>

<span data-ttu-id="2dc6d-244">Quando si genera un errore che genera errori in una sequenza, WCF prevede che l'endpoint remoto errori entrambe le sequenze.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-244">Upon generating a fault that faults one sequence, WCF expects the remote endpoint to fault both sequences.</span></span> <span data-ttu-id="2dc6d-245">Durante la lettura di un errore che genera errori in una sequenza, WCF genera errori in entrambe le sequenze.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-245">Upon reading a fault that faults one sequence, WCF faults both sequences.</span></span>

<span data-ttu-id="2dc6d-246">WCF può chiudere la sequenza in uscita e continuare a elaborare i messaggi sulla relativa sequenza in ingresso.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-246">WCF can close its outbound sequence and continue to process messages on its inbound sequence.</span></span> <span data-ttu-id="2dc6d-247">Viceversa, WCF può elaborare la chiusura della sequenza in ingresso e continuare a inviare messaggi sulla relativa sequenza in uscita.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-247">Conversely, WCF can process the close of the inbound sequence and continue to send messages on its outbound sequence.</span></span>

### <a name="request-reply-non-addressable-initiator"></a><span data-ttu-id="2dc6d-248">Iniziatore request/reply non indirizzabile</span><span class="sxs-lookup"><span data-stu-id="2dc6d-248">Request-Reply, Non-Addressable Initiator</span></span>

#### <a name="binding"></a><span data-ttu-id="2dc6d-249">Associazione</span><span class="sxs-lookup"><span data-stu-id="2dc6d-249">Binding</span></span>

<span data-ttu-id="2dc6d-250">WCF fornisce un modello di scambio di messaggi unidirezionale e Request/Reply utilizzando due sequenze su un canale HTTP.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-250">WCF provides a one-way and request-reply message exchange pattern using two sequences over one HTTP channel.</span></span> <span data-ttu-id="2dc6d-251">WCF utilizza le richieste HTTP per trasmettere i messaggi della sequenza di richiesta e utilizza le risposte HTTP per trasmettere i messaggi della sequenza di risposta.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-251">WCF uses the HTTP requests to transmit the request sequence’s messages and uses the HTTP responses to transmit the reply sequence’s messages.</span></span>

#### <a name="createsequence-exchange"></a><span data-ttu-id="2dc6d-252">Scambio CreateSequence</span><span class="sxs-lookup"><span data-stu-id="2dc6d-252">CreateSequence Exchange</span></span>

<span data-ttu-id="2dc6d-253">L'iniziatore WCF genera un `CreateSequence` messaggio con un'offerta.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-253">The WCF Initiator generates a `CreateSequence` message with an offer.</span></span> <span data-ttu-id="2dc6d-254">Il risponditore WCF garantisce che `CreateSequence` abbia un'offerta prima di creare una sequenza.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-254">The WCF Responder ensures that the `CreateSequence` has an offer before creating a sequence.</span></span> <span data-ttu-id="2dc6d-255">Il risponditore WCF risponde alla `CreateSequence` richiesta con un `CreateSequenceResponse` messaggio.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-255">The WCF Responder replies to the `CreateSequence` request with a `CreateSequenceResponse` message.</span></span>

#### <a name="one-way-message"></a><span data-ttu-id="2dc6d-256">Messaggio unidirezionale</span><span class="sxs-lookup"><span data-stu-id="2dc6d-256">One-way Message</span></span>

<span data-ttu-id="2dc6d-257">Per completare correttamente un protocollo di scambio di messaggi unidirezionale, l'iniziatore WCF trasmette un messaggio della sequenza di richiesta sulla richiesta HTTP e riceve un messaggio autonomo `SequenceAcknowledgement` sulla risposta http.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-257">To complete a one-way message exchange protocol successfully, the WCF Initiator transmits a request sequence message on the HTTP request and receives a standalone `SequenceAcknowledgement` message on the HTTP response.</span></span> <span data-ttu-id="2dc6d-258">`SequenceAcknowledgement` deve riconoscere il messaggio trasmesso.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-258">The `SequenceAcknowledgement` must acknowledge the message transmitted.</span></span>

<span data-ttu-id="2dc6d-259">Il risponditore WCF può rispondere alla richiesta con un riconoscimento, un errore o una risposta con un corpo vuoto e un codice di stato HTTP 202.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-259">The WCF Responder can reply to the request with an acknowledgement, a fault, or a response with an empty body and HTTP 202 status code.</span></span>

#### <a name="two-way-messages"></a><span data-ttu-id="2dc6d-260">Messaggi bidirezionali</span><span class="sxs-lookup"><span data-stu-id="2dc6d-260">Two Way Messages</span></span>

<span data-ttu-id="2dc6d-261">Per completare correttamente un protocollo di scambio di messaggi bidirezionale, l'iniziatore WCF trasmette un messaggio della sequenza di richiesta sulla richiesta HTTP e riceve un messaggio della sequenza di risposta nella risposta HTTP.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-261">To complete a two way message exchange protocol successfully, the WCF Initiator transmits a request sequence message on the HTTP request and receives a reply sequence message on the HTTP response.</span></span> <span data-ttu-id="2dc6d-262">La risposta deve contenere un `SequenceAcknowledgement` che riconosce che il messaggio della sequenza di richiesta è stato trasmesso.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-262">The response must carry a `SequenceAcknowledgement` acknowledging the request sequence message transmitted.</span></span>

<span data-ttu-id="2dc6d-263">Il risponditore WCF può rispondere alla richiesta con una risposta dell'applicazione, un errore o una risposta con un corpo vuoto e un codice di stato HTTP 202.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-263">The WCF Responder can reply to the request with an application reply, a fault or a response with an empty body and HTTP 202 status code.</span></span>

<span data-ttu-id="2dc6d-264">A causa della presenza di messaggi unidirezionali e del tempo delle risposte dell'applicazione, il numero di sequenza del messaggio della sequenza di richiesta e il numero di sequenza del messaggio di risposta non hanno alcuna correlazione.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-264">Because of the presence of one-way messages and the timing of application replies, the request sequence message’s sequence number and the response message’s sequence number have no correlation.</span></span>

#### <a name="retrying-replies"></a><span data-ttu-id="2dc6d-265">Nuovi tentativi di risposte</span><span class="sxs-lookup"><span data-stu-id="2dc6d-265">Retrying Replies</span></span>

<span data-ttu-id="2dc6d-266">WCF si basa sulla correlazione request/reply HTTP per la correlazione tra protocolli di scambio di messaggi bidirezionali.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-266">WCF relies on HTTP request-reply correlation for two-way message exchange protocol correlation.</span></span> <span data-ttu-id="2dc6d-267">Per questo motivo, l'iniziatore WCF non interrompe il nuovo tentativo di un messaggio della sequenza di richiesta quando il messaggio della sequenza di richiesta viene riconosciuto, ma piuttosto quando la risposta HTTP contiene un riconoscimento, un messaggio utente o un errore.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-267">Because of this, the WCF Initiator does not stop retrying a request sequence message when the request sequence message is acknowledged but rather when the HTTP response carries an acknowledgement, user message, or fault.</span></span> <span data-ttu-id="2dc6d-268">Il risponditore WCF ritenta le risposte sulla parte della richiesta HTTP della richiesta a cui è correlata la risposta.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-268">The WCF Responder retries replies on the HTTP request leg of the request to which the reply is correlated.</span></span>

#### <a name="lastmessage-exchange"></a><span data-ttu-id="2dc6d-269">Scambio LastMessage</span><span class="sxs-lookup"><span data-stu-id="2dc6d-269">LastMessage Exchange</span></span>

<span data-ttu-id="2dc6d-270">L'iniziatore WCF genera e trasmette un ultimo messaggio con corpo vuoto sulla parte della richiesta HTTP.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-270">The WCF Initiator generates and transmits an empty bodied last message on the HTTP request leg.</span></span> <span data-ttu-id="2dc6d-271">WCF richiede una risposta ma ignora il messaggio di risposta effettivo.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-271">WCF requires a response but ignores the actual response message.</span></span> <span data-ttu-id="2dc6d-272">Il risponditore WCF risponde all'ultimo messaggio con corpo vuoto della sequenza di richiesta con l'ultimo messaggio con corpo vuoto della sequenza di risposta.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-272">The WCF Responder replies to the request sequence’s empty-bodied last message with the reply sequence’s empty-bodied last message.</span></span>

<span data-ttu-id="2dc6d-273">Se il risponditore WCF riceve un ultimo messaggio in cui l'URI dell'azione non è `http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage` , WCF risponde con un ultimo messaggio.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-273">If the WCF Responder receives a last message in which the action URI is not `http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage`, WCF replies with a last message.</span></span> <span data-ttu-id="2dc6d-274">Nel caso di un protocollo di scambio di messaggi bidirezionale, l'ultimo messaggio contiene il messaggio dell'applicazione; nel caso, invece, di un protocollo di scambio di messaggi unidirezionale, l'ultimo messaggio è vuoto.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-274">In the case of a two-way message exchange protocol, the last message carries the application message; in the case of a one-way message exchange protocol, the last message is empty.</span></span>

<span data-ttu-id="2dc6d-275">Il risponditore WCF non richiede un riconoscimento per l'ultimo messaggio con corpo vuoto della sequenza di risposta.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-275">The WCF Responder does not require an acknowledgement for the reply sequence’s empty-bodied last message.</span></span>

#### <a name="terminatesequence-exchange"></a><span data-ttu-id="2dc6d-276">Scambio TerminateSequence</span><span class="sxs-lookup"><span data-stu-id="2dc6d-276">TerminateSequence Exchange</span></span>

<span data-ttu-id="2dc6d-277">Quando tutte le richieste hanno ricevuto una risposta valida, l'iniziatore WCF genera e trasmette il messaggio della sequenza di richiesta `TerminateSequence` sulla parte della richiesta HTTP.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-277">When all requests have received a valid reply, the WCF Initiator generates and transmits the request sequence’s `TerminateSequence` message on the HTTP request leg.</span></span> <span data-ttu-id="2dc6d-278">WCF richiede una risposta ma ignora il messaggio di risposta effettivo.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-278">WCF requires a response but ignores the actual response message.</span></span> <span data-ttu-id="2dc6d-279">Il risponditore WCF risponde al messaggio della sequenza di richiesta `TerminateSequence` con il messaggio della sequenza di risposta `TerminateSequence` .</span><span class="sxs-lookup"><span data-stu-id="2dc6d-279">The WCF Responder replies to the request sequence’s `TerminateSequence` message with the reply sequence’s `TerminateSequence` message.</span></span>

<span data-ttu-id="2dc6d-280">In una sequenza di arresto normale, entrambi i messaggi `TerminateSequence` contengono un intervallo completo `SequenceAcknowledgement`.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-280">In a normal shutdown sequence, both `TerminateSequence` messages carry a full range `SequenceAcknowledgement`.</span></span>

### <a name="requestreply-addressable-initiator"></a><span data-ttu-id="2dc6d-281">Iniziatore request/reply, indirizzabile</span><span class="sxs-lookup"><span data-stu-id="2dc6d-281">Request/Reply, Addressable Initiator</span></span>

#### <a name="binding"></a><span data-ttu-id="2dc6d-282">Associazione</span><span class="sxs-lookup"><span data-stu-id="2dc6d-282">Binding</span></span>

<span data-ttu-id="2dc6d-283">WCF fornisce un modello di scambio di messaggi request/reply utilizzando due sequenze su un canale HTTP in ingresso e in uscita.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-283">WCF provides a request-reply message exchange pattern using two sequences over an inbound and an outbound HTTP channel.</span></span> <span data-ttu-id="2dc6d-284">WCF utilizza le richieste HTTP per trasmettere tutti i messaggi.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-284">WCF uses the HTTP requests to transmit all messages.</span></span> <span data-ttu-id="2dc6d-285">Tutte le risposte HTTP hanno un corpo vuoto e un codice di stato HTTP 202.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-285">All HTTP responses have an empty body and HTTP 202 status code.</span></span>

#### <a name="createsequence-exchange"></a><span data-ttu-id="2dc6d-286">Scambio CreateSequence</span><span class="sxs-lookup"><span data-stu-id="2dc6d-286">CreateSequence Exchange</span></span>

<span data-ttu-id="2dc6d-287">L'iniziatore WCF genera un `CreateSequence` messaggio con un'offerta.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-287">The WCF Initiator generates a `CreateSequence` message with an offer.</span></span> <span data-ttu-id="2dc6d-288">Il risponditore WCF garantisce che `CreateSequence` abbia un'offerta prima di creare una sequenza.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-288">The WCF Responder ensures that the `CreateSequence` has an offer before creating a sequence.</span></span> <span data-ttu-id="2dc6d-289">WCF invia la `CreateSequenceResponse` sulla richiesta HTTP indirizzata al `CreateSequence` riferimento all' `ReplyTo` endpoint di.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-289">WCF sends the `CreateSequenceResponse` on the HTTP request addressed to the `CreateSequence`’s `ReplyTo` endpoint reference.</span></span>

#### <a name="requestreply-correlation"></a><span data-ttu-id="2dc6d-290">Correlazione request/reply</span><span class="sxs-lookup"><span data-stu-id="2dc6d-290">Request/Reply Correlation</span></span>

<span data-ttu-id="2dc6d-291">L'iniziatore WCF garantisce che tutti i messaggi di richiesta dell'applicazione contengano un `MessageId` e un `ReplyTo` riferimento all'endpoint.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-291">The WCF Initiator ensures all application request messages bear a `MessageId` and a `ReplyTo` endpoint reference.</span></span> <span data-ttu-id="2dc6d-292">L'iniziatore WCF applica il `CreateSequence` riferimento all'endpoint del messaggio `ReplyTo` in ogni messaggio di richiesta dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-292">The WCF Initiator applies the `CreateSequence` message’s `ReplyTo` endpoint reference on each application request message.</span></span> <span data-ttu-id="2dc6d-293">Per il risponditore WCF è necessario che i messaggi di richiesta in ingresso contengano `MessageId` e `ReplyTo` .</span><span class="sxs-lookup"><span data-stu-id="2dc6d-293">The WCF Responder requires that incoming request messages bear a `MessageId` and a `ReplyTo`.</span></span> <span data-ttu-id="2dc6d-294">Il risponditore WCF garantisce che l'URI del riferimento dell'endpoint di `CreateSequence` e di tutti i messaggi di richiesta dell'applicazione siano identici.</span><span class="sxs-lookup"><span data-stu-id="2dc6d-294">The WCF Responder ensures that the endpoint reference’s URI of both the `CreateSequence` and all application request messages are identical.</span></span>
