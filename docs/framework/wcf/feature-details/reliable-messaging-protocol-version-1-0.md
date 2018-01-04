---
title: Protocollo Reliable Messaging versione 1.0
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a5509a5c-de24-4bc2-9a48-19138055dcce
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a32c16067446459817e9943c2d729a67373a0333
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="reliable-messaging-protocol-version-10"></a><span data-ttu-id="8d3bc-102">Protocollo Reliable Messaging versione 1.0</span><span class="sxs-lookup"><span data-stu-id="8d3bc-102">Reliable Messaging Protocol version 1.0</span></span>
<span data-ttu-id="8d3bc-103">In questo argomento vengono illustrati i dettagli di implementazione di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] per il protocollo WS-Reliable Messaging di febbraio 2005 (versione 1.0) necessario per l'interoperatività con il trasporto HTTP.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-103">This topic covers [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] implementation details for the WS-Reliable Messaging February 2005 (version 1.0) protocol necessary for interoperation using the HTTP transport.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="8d3bc-104"> segue la specifica WS-Reliable Messaging con i vincoli e i chiarimenti illustrati in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-104"> follows the WS-Reliable Messaging specification with the constraints and clarifications explained in this topic.</span></span> <span data-ttu-id="8d3bc-105">Si noti che il protocollo WS-Reliable Messaging versione 1.0 viene implementato a partire da [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8d3bc-105">Note that the WS-ReliableMessaging version 1.0 protocol is implemented starting with the [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)].</span></span>  
  
 <span data-ttu-id="8d3bc-106">Il protocollo WS-Reliable Messaging (febbraio 2005) viene implementato in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] da <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-106">The WS-Reliable Messaging February 2005 protocol is implemented in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] by the <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>.</span></span>  
  
 <span data-ttu-id="8d3bc-107">Per comodità, nell'argomento vengono utilizzati i ruoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="8d3bc-107">For convenience, the topic uses the following roles:</span></span>  
  
-   <span data-ttu-id="8d3bc-108">Iniziatore: il client che avvia la creazione della sequenza di WS-Reliable Message.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-108">Initiator: the client that initiates WS-Reliable Message sequence creation</span></span>  
  
-   <span data-ttu-id="8d3bc-109">Risponditore: il servizio che riceve le richieste dell'iniziatore.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-109">Responder: the service that receives the initiator's requests</span></span>  
  
 <span data-ttu-id="8d3bc-110">In questo documento vengono utilizzati i prefissi e gli spazi dei nomi riportati nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-110">This document uses the prefixes and namespaces in the following table.</span></span>  
  
|<span data-ttu-id="8d3bc-111">Prefisso</span><span class="sxs-lookup"><span data-stu-id="8d3bc-111">Prefix</span></span>|<span data-ttu-id="8d3bc-112">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="8d3bc-112">Namespace</span></span>|  
|------------|---------------|  
|<span data-ttu-id="8d3bc-113">wsrm</span><span class="sxs-lookup"><span data-stu-id="8d3bc-113">wsrm</span></span>|<span data-ttu-id="8d3bc-114">http://schemas.xmlsoap.org/ws/2005/02/rm</span><span class="sxs-lookup"><span data-stu-id="8d3bc-114">http://schemas.xmlsoap.org/ws/2005/02/rm</span></span>|  
|<span data-ttu-id="8d3bc-115">netrm</span><span class="sxs-lookup"><span data-stu-id="8d3bc-115">netrm</span></span>|<span data-ttu-id="8d3bc-116">http://schemas.microsoft.com/ws/2006/05/rm</span><span class="sxs-lookup"><span data-stu-id="8d3bc-116">http://schemas.microsoft.com/ws/2006/05/rm</span></span>|  
|<span data-ttu-id="8d3bc-117">s</span><span class="sxs-lookup"><span data-stu-id="8d3bc-117">s</span></span>|<span data-ttu-id="8d3bc-118">http://www.w3.org/2003/05/soap-envelope</span><span class="sxs-lookup"><span data-stu-id="8d3bc-118">http://www.w3.org/2003/05/soap-envelope</span></span>|  
|<span data-ttu-id="8d3bc-119">wsa</span><span class="sxs-lookup"><span data-stu-id="8d3bc-119">wsa</span></span>|<span data-ttu-id="8d3bc-120">http://schemas.xmlsoap.org/ws/2005/08/addressing</span><span class="sxs-lookup"><span data-stu-id="8d3bc-120">http://schemas.xmlsoap.org/ws/2005/08/addressing</span></span>|  
|<span data-ttu-id="8d3bc-121">wsse</span><span class="sxs-lookup"><span data-stu-id="8d3bc-121">wsse</span></span>|<span data-ttu-id="8d3bc-122">http://docs.oasis-open.org/wss/2004/01/oasis-200401-wssecurity-secext-1.0.xsd</span><span class="sxs-lookup"><span data-stu-id="8d3bc-122">http://docs.oasis-open.org/wss/2004/01/oasis-200401-wssecurity-secext-1.0.xsd</span></span>|  
  
## <a name="messaging"></a><span data-ttu-id="8d3bc-123">Messaggistica</span><span class="sxs-lookup"><span data-stu-id="8d3bc-123">Messaging</span></span>  
  
### <a name="sequence-establishment-messages"></a><span data-ttu-id="8d3bc-124">Messaggi di definizione sequenza</span><span class="sxs-lookup"><span data-stu-id="8d3bc-124">Sequence Establishment Messages</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="8d3bc-125"> implementa messaggi `CreateSequence` e `CreateSequenceResponse` per stabilire una sequenza di messaggi affidabile.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-125"> implements `CreateSequence` and `CreateSequenceResponse` messages to establish a reliable message sequence.</span></span> <span data-ttu-id="8d3bc-126">Si applicano i vincoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="8d3bc-126">The following constraints apply:</span></span>  
  
-   <span data-ttu-id="8d3bc-127">B1101: l'iniziatore [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] non genera l'elemento Expires facoltativo nel messaggio `CreateSequence` o, nei casi in cui il messaggio `CreateSequence` contiene un elemento `Offer`, l'elemento `Expires` facoltativo nell'elemento `Offer`.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-127">B1101: The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator does not generate the optional Expires element in the `CreateSequence` message or, in the cases when the `CreateSequence` message contains an `Offer` element, the optional `Expires` element in the `Offer` element.</span></span>  
  
-   <span data-ttu-id="8d3bc-128">B1102: Durante l'accesso di `CreateSequence` messaggio, il [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] `Responder` Invia e riceve entrambi `Expires` elementi se esiste, ma non utilizza i relativi valori.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-128">B1102: When accessing the `CreateSequence` message, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]`Responder` sends and receives both `Expires` elements if they exist, but does not use their values.</span></span>  
  
 <span data-ttu-id="8d3bc-129">Con il protocollo WS-ReliableMessaging viene introdotto il meccanismo `Offer` che consente di stabilire le due sequenze correlate opposte che formano una sessione.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-129">WS-Reliable Messaging introduces the `Offer` mechanism to establish the two converse correlated sequences that form a session.</span></span>  
  
-   <span data-ttu-id="8d3bc-130">R1103: se `CreateSequence` contiene un elemento `Offer`, il risponditore Reliable Messaging deve accettare la sequenza e rispondere con `CreateSequenceResponse` contenente un elemento `wsrm:Accept`, formando due sequenze correlate opposte, oppure rifiutare la richiesta `CreateSequence`.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-130">R1103: If `CreateSequence` contains an `Offer` element, the Reliable Messaging Responder must either accept the sequence and respond with `CreateSequenceResponse` that contains a `wsrm:Accept` element, forming two correlated converse sequences or reject the `CreateSequence` request.</span></span>  
  
-   <span data-ttu-id="8d3bc-131">R1104: i messaggi `SequenceAcknowledgement` e dell'applicazione in transito sulla sequenza opposta devono essere inviati al riferimento endpoint `ReplyTo` di `CreateSequence`.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-131">R1104: `SequenceAcknowledgement` and application messages flowing on converse sequence must be sent to the `ReplyTo` endpoint reference of the `CreateSequence`.</span></span>  
  
-   <span data-ttu-id="8d3bc-132">R1105: i riferimenti endpoint `AcksTo` e `ReplyTo` in `CreateSequence` devono presentare valori indirizzo che corrispondano all'ottetto.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-132">R1105: `AcksTo` and `ReplyTo` endpoint references in the `CreateSequence` must have address values that match the octet-wise.</span></span>  
  
     <span data-ttu-id="8d3bc-133">Prima di creare una sequenza , il risponditore [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] verifica che le parti URI dei riferimenti endpoint `AcksTo` e`ReplyTo` siano identiche.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-133">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder verifies that the URI portion of the `AcksTo` and `ReplyTo` EPRs are identical before creating a sequence.</span></span>  
  
-   <span data-ttu-id="8d3bc-134">R1106: i riferimenti endpoint `AcksTo`e `ReplyTo` in `CreateSequence` devono avere lo stesso set di parametri di riferimento.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-134">R1106: `AcksTo` and `ReplyTo` Endpoint References in the `CreateSequence` should have the same set of reference parameters.</span></span>  
  
     [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="8d3bc-135"> non impone, ma presuppone che i parametri di riferimento dei riferimenti endpoint `AcksTo` e `ReplyTo` in `CreateSequence` siano identici e utilizza i parametri di riferimento dal riferimento endpoint `ReplyTo` per acknowledgement e messaggi della sequenza opposta.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-135"> does not enforce but assumes that [reference parameters] of `AcksTo` and `ReplyTo` on `CreateSequence` are identical and uses [reference parameters] from `ReplyTo` endpoint reference for acknowledgements and converse sequence messages.</span></span>  
  
-   <span data-ttu-id="8d3bc-136">R1107: quando vengono stabilite due sequenze opposte tramite il meccanismo `Offer`, i messaggi dell'applicazione e `SequenceAcknowledgement` in transito sulle sequenze opposte devono essere inviati al riferimento all'endpoint `ReplyTo` di `CreateSequence`.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-136">R1107: When two converse sequences are established using the `Offer` mechanism, `SequenceAcknowledgement` and application messages flowing on converse sequences must be sent to the `ReplyTo` endpoint reference of the `CreateSequence`.</span></span>  
  
-   <span data-ttu-id="8d3bc-137">R1108: quando vengono stabilite due sequenze opposte mediante il meccanismo Offer, la proprietà `[address]` dell'elemento figlio del riferimento endpoint `wsrm:AcksTo` dell'elemento `wsrm:Accept` di `CreateSequenceResponse` deve corrispondere per numero di byte all'URI di destinazione di `CreateSequence`.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-137">R1108: When two converse sequences are established using the Offer mechanism, the `[address]` property of the `wsrm:AcksTo` Endpoint Reference child element of the `wsrm:Accept` element of the `CreateSequenceResponse` must match byte-wise the destination URI of the `CreateSequence`.</span></span>  
  
-   <span data-ttu-id="8d3bc-138">R1109: quando vengono stabilite due sequenze opposte tramite il meccanismo `Offer`, i messaggi inviati dall'iniziatore e gli acknowledgement a tali messaggi da parte del risponditore devono essere inviati allo stesso riferimento all'endpoint.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-138">R1109: When two converse sequences are established using the `Offer` mechanism, messages sent by initiator and acknowledgements to messages by responder must be sent to the same Endpoint Reference.</span></span>  
  
     [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="8d3bc-139"> utilizza WS-Reliable Messaging per stabilire sessioni affidabili tra l'iniziatore e il risponditore.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-139"> uses WS-Reliable Messaging to establish reliable sessions between the Initiator and Responder.</span></span> <span data-ttu-id="8d3bc-140">L'implementazione [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] di WS-ReliableMessaging offre una sessione affidabile per modelli di messaggistica unidirezionali, request/reply e full duplex.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-140">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]'s WS-Reliable Messaging implementation provides reliable session for one-way, request-reply and full duplex messaging patterns.</span></span> <span data-ttu-id="8d3bc-141">WS-Reliable Messaging `Offer` meccanismo `CreateSequence` / `CreateSequenceResponse` consente di stabilire due sequenze opposte correlate e fornisce un protocollo di sessione che è adatto per tutti gli endpoint del messaggio.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-141">The WS-Reliable Messaging `Offer` mechanism on `CreateSequence`/`CreateSequenceResponse` lets you establish two correlated converse sequences, and provides a session protocol that is suitable for all message endpoints.</span></span> <span data-ttu-id="8d3bc-142">Dato che [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] fornisce una garanzia di sicurezza per tale sessione, inclusa la protezione end-to-end per l'integrità della sessione, è consigliabile assicurarsi che i messaggi destinati alla stessa parte arrivino alla stessa destinazione.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-142">Because [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] provides a security guarantee for such a session including end-to-end protection for session integrity, it is practical to ensure messages intended to the same party are arriving at the same destination.</span></span> <span data-ttu-id="8d3bc-143">Ciò consente anche il "piggy-backing" degli acknowledgement della sequenza sui messaggi dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-143">This also allows piggy-backing of sequence acknowledgements on application messages.</span></span> <span data-ttu-id="8d3bc-144">A [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] si applicano pertanto i vincoli R1104, R1105 e R1108.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-144">Therefore, constraints R1104, R1105, and R1108 apply to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span>  
  
 <span data-ttu-id="8d3bc-145">Esempio di un messaggio `CreateSequence`.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-145">An example of a `CreateSequence` message.</span></span>  
  
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
  
 <span data-ttu-id="8d3bc-146">Esempio di un messaggio `CreateSequenceResponse`.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-146">An example of a `CreateSequenceResponse` message.</span></span>  
  
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
  
### <a name="sequence"></a><span data-ttu-id="8d3bc-147">Sequence</span><span class="sxs-lookup"><span data-stu-id="8d3bc-147">Sequence</span></span>  
 <span data-ttu-id="8d3bc-148">Di seguito è riportato un elenco di vincoli che si applicano alle sequenze:</span><span class="sxs-lookup"><span data-stu-id="8d3bc-148">The following is a list of constraints that apply to sequences:</span></span>  
  
-   <span data-ttu-id="8d3bc-149">B1201:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] genera l'errore e accede a numeri di sequenza non superiori a `xs:long`del valore inclusivo massimo, 9223372036854775807.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-149">B1201:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generates and accesses sequence numbers no higher than `xs:long`’s maximum inclusive value, 9223372036854775807.</span></span>  
  
-   <span data-ttu-id="8d3bc-150">B1202:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] genera sempre un corpo vuoto ultimo messaggio con l'URI dell'azione di http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-150">B1202:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] always generates an empty-bodied last message with the action URI of http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage.</span></span>  
  
-   <span data-ttu-id="8d3bc-151">B1203: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] riceve e recapita un messaggio con un'intestazione di sequenza contenente un elemento `LastMessage`, a condizione che l'URI dell'azione non sia http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-151">B1203: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] receives and delivers a message with a Sequence header that contains a `LastMessage` element as long as the action URI is not http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage.</span></span>  
  
 <span data-ttu-id="8d3bc-152">Esempio di intestazione di sequenza.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-152">An example of a Sequence Header.</span></span>  
  
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
  
### <a name="ackrequested-header"></a><span data-ttu-id="8d3bc-153">Intestazione AckRequested</span><span class="sxs-lookup"><span data-stu-id="8d3bc-153">AckRequested Header</span></span>  
 <span data-ttu-id="8d3bc-154">In [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] viene utilizzata l'intestazione `AckRequested` come meccanismo keep-alive.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-154">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] uses `AckRequested` Header as a keep-alive mechanism.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="8d3bc-155"> non genera l'elemento `MessageNumber` facoltativo.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-155"> does not generate the optional `MessageNumber` element.</span></span> <span data-ttu-id="8d3bc-156">Quando viene ricevuto un messaggio con un'intestazione `AckRequested` contenente l'elemento `MessageNumber`, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ignora il valore dell'elemento `MessageNumber`, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-156">Upon receiving a message with an `AckRequested` header that contains the `MessageNumber` element, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ignores the `MessageNumber` element’s value, as shown in the following example.</span></span>  
  
```xml  
<wsrm:AckRequested>  
  <wsrm:Identifier>  
    urn:uuid:addabbbf-60cb-44d3-8c5b-9e0841629a36  
  </wsrm:Identifier>  
</wsrm:AckRequested>  
```  
  
### <a name="sequenceacknowledgement-header"></a><span data-ttu-id="8d3bc-157">Intestazione SequenceAcknowledgement</span><span class="sxs-lookup"><span data-stu-id="8d3bc-157">SequenceAcknowledgement Header</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="8d3bc-158"> utilizza un meccanismo "piggy-back" per gli acknowledgement di sequenza disponibile nel protocollo WS-Reliable Messaging.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-158"> uses piggy-back mechanism for sequence acknowledgements provided in WS-Reliable Messaging.</span></span>  
  
-   <span data-ttu-id="8d3bc-159">R1401: quando vengono stabilite due sequenze opposte utilizzando il meccanismo `Offer`, l'intestazione `SequenceAcknowledgement` può essere inclusa in qualsiasi messaggio dell'applicazione trasmesso al destinatario desiderato.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-159">R1401: When two converse sequences are established using the `Offer` mechanism, the `SequenceAcknowledgement` header may be included in any application message transmitted to the intended recipient.</span></span>  
  
-   <span data-ttu-id="8d3bc-160">B1402: quando [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] deve generare un acknowledgement prima di ricevere qualsiasi messaggio di sequenza, ad esempio per soddisfare un messaggio `AckRequested`, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] genera un'intestazione `SequenceAcknowledgement` che contiene l'intervallo 0-0, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-160">B1402: When [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] must generate an acknowledgement prior to receiving any sequence messages (for example, to satisfy an `AckRequested` message), [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generates a `SequenceAcknowledgement` header that contains the range 0-0, as shown in the following example.</span></span>  
  
    ```xml  
    <wsrm:SequenceAcknowledgement>  
      <wsrm:Identifier>  
        urn:uuid:addabbbf-60cb-44d3-8c5b-9e0841629a36  
      </wsrm:Identifier>  
      <wsrm:AcknowledgementRange Upper="0" Lower="0"/>  
    </wsrm:SequenceAcknowledgement>  
    ```  
  
-   <span data-ttu-id="8d3bc-161">B1403: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] non genera intestazioni `SequenceAcknowledgement` che contengono un elemento `Nack`, ma supporta elementi `Nack`.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-161">B1403: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] does not generate `SequenceAcknowledgement` headers that contain a `Nack` element but supports `Nack` elements.</span></span>  
  
### <a name="ws-reliablemessaging-faults"></a><span data-ttu-id="8d3bc-162">Errori WS-ReliableMessaging</span><span class="sxs-lookup"><span data-stu-id="8d3bc-162">WS-ReliableMessaging Faults</span></span>  
 <span data-ttu-id="8d3bc-163">Di seguito è riportato un elenco di vincoli applicabili all'implementazione [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] degli errori di WS-Reliable Messaging:</span><span class="sxs-lookup"><span data-stu-id="8d3bc-163">The following is a list of constraints that apply to the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] implementation of WS-Reliable Messaging faults:</span></span>  
  
-   <span data-ttu-id="8d3bc-164">B1501: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] non genera errori `MessageNumberRollover`.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-164">B1501: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] does not generate `MessageNumberRollover` faults.</span></span>  
  
-   <span data-ttu-id="8d3bc-165">B1502:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] endpoint può generare `CreateSequenceRefused` errori come descritto nella specifica.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-165">B1502:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] endpoint may generate `CreateSequenceRefused` faults as described in the specification.</span></span>  
  
-   <span data-ttu-id="8d3bc-166">B1503:when l'endpoint del servizio raggiunge il limite di connessione e non è in grado di elaborare nuove connessioni, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] genera un ulteriore `CreateSequenceRefused` codice secondario, di errore `netrm:ConnectionLimitReached`, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-166">B1503:When the service endpoint reaches its connection limit and cannot process new connections, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generates an additional `CreateSequenceRefused` fault subcode, `netrm:ConnectionLimitReached`, as shown in the following example.</span></span>  
  
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
  
### <a name="ws-addressing-faults"></a><span data-ttu-id="8d3bc-167">Errori WS-Addressing</span><span class="sxs-lookup"><span data-stu-id="8d3bc-167">WS-Addressing Faults</span></span>  
 <span data-ttu-id="8d3bc-168">Dato che WS-Reliable Messaging utilizza WS-Addressing, l'implementazione [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] di WS-Reliable Messaging potrebbe generare errori WS-Addressing.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-168">Because WS-Reliable Messaging uses WS-Addressing, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] WS-Reliable Messaging implementation may generate WS-Addressing faults.</span></span> <span data-ttu-id="8d3bc-169">Contenuto della sezione vengono illustrati gli errori WS-Addressing generati in modo esplicito da [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] a livello di WS-ReliableMessaging:</span><span class="sxs-lookup"><span data-stu-id="8d3bc-169">This section covers the WS-Addressing faults that [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] explicitly generates at the WS-Reliable Messaging layer:</span></span>  
  
-   <span data-ttu-id="8d3bc-170">B1601:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] genera l'errore messaggio Addressing intestazione obbligatoria quando viene soddisfatta una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8d3bc-170">B1601:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generates the fault Message Addressing Header Required when one of the following is true:</span></span>  
  
    -   <span data-ttu-id="8d3bc-171">In un messaggio mancano un'intestazione `Sequence` e un'intestazione `Action`.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-171">A message is missing a `Sequence` header and an `Action` header.</span></span>  
  
    -   <span data-ttu-id="8d3bc-172">In un messaggio `CreateSequence` manca un'intestazione `MessageId`.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-172">A `CreateSequence` message is missing a `MessageId` header.</span></span>  
  
    -   <span data-ttu-id="8d3bc-173">In un messaggio `CreateSequence` manca un'intestazione `ReplyTo`.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-173">A `CreateSequence` message is missing a `ReplyTo` header.</span></span>  
  
-   <span data-ttu-id="8d3bc-174">B1602:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] genera l'errore non sono supportate azioni in risposta a un messaggio in cui Manca un `Sequence` intestazione e ha un `Action` intestazione che non è un riconosciuto nella specifica WS-Reliable Messaging.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-174">B1602:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generates the fault Action Not Supported in reply to a message that is missing a `Sequence` header and has an `Action` header that is not a recognized in the WS-Reliable Messaging specification.</span></span>  
  
-   <span data-ttu-id="8d3bc-175">B1603:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] genera l'errore Endpoint disponibile per indicare che l'endpoint non elabora la sequenza basata sull'esame del `CreateSequence` intestazioni di indirizzamento del messaggio.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-175">B1603:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generates the fault Endpoint Unavailable to indicate that the endpoint does not process the sequence based upon examination of the `CreateSequence` message’s addressing headers.</span></span>  
  
## <a name="protocol-composition"></a><span data-ttu-id="8d3bc-176">Composizione del protocollo</span><span class="sxs-lookup"><span data-stu-id="8d3bc-176">Protocol Composition</span></span>  
  
### <a name="composition-with-ws-addressing"></a><span data-ttu-id="8d3bc-177">Composizione con WS-Addressing</span><span class="sxs-lookup"><span data-stu-id="8d3bc-177">Composition with WS-Addressing</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="8d3bc-178"> supporta due versioni di WS-Addressing: WS-Addressing 2004/08 [WS-ADDR] e W3C WS-Addressing 1.0 Recommendation [WS-ADDR-CORE] e [WS-ADDR-SOAP].</span><span class="sxs-lookup"><span data-stu-id="8d3bc-178"> supports two versions of WS-Addressing: WS-Addressing 2004/08 [WS-ADDR] and W3C WS-Addressing 1.0 Recommendations [WS-ADDR-CORE] and [WS-ADDR-SOAP].</span></span>  
  
 <span data-ttu-id="8d3bc-179">Anche se la specifica WS-Reliable Messaging menziona solo WS-Addressing 2004/08, non limita la versione WS-Addressing da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-179">While the WS-Reliable Messaging specification mentions only WS-Addressing 2004/08, it does not restrict the WS-Addressing version to be used.</span></span> <span data-ttu-id="8d3bc-180">Di seguito è riportato un elenco di vincoli che si applicano a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="8d3bc-180">The following is a list of constraints that apply to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]:</span></span>  
  
-   <span data-ttu-id="8d3bc-181">R2101: sia WS-Addressing 2004/08 che WS-Addressing 1.0 possono essere utilizzati con WS-Reliable Messaging.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-181">R2101:Both WS-Addressing 2004/08 and WS-Addressing 1.0 can be used with WS-Reliable Messaging.</span></span>  
  
-   <span data-ttu-id="8d3bc-182">R2102:A singola versione di WS-Addressing da utilizzare in una determinata sequenza di WS-Reliable Messaging o una coppia di sequenze opposte correlate tramite il `wsrm:Offer` meccanismo.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-182">R2102:A single version of WS-Addressing must be used throughout a given WS-Reliable Messaging sequence or a pair of converse sequences correlated by using the `wsrm:Offer` mechanism.</span></span>  
  
### <a name="composition-with-soap"></a><span data-ttu-id="8d3bc-183">Composizione con SOAP</span><span class="sxs-lookup"><span data-stu-id="8d3bc-183">Composition with SOAP</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="8d3bc-184"> supporta l'utilizzo sia di SOAP 1.1 che di SOAP 1.2 con WS-Reliable Messaging.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-184"> supports use of both SOAP 1.1 and SOAP 1.2 with WS-Reliable Messaging.</span></span>  
  
### <a name="composition-with-ws-security-and-ws-secureconversation"></a><span data-ttu-id="8d3bc-185">Composizione con WS-Security e WS-SecureConversation</span><span class="sxs-lookup"><span data-stu-id="8d3bc-185">Composition with WS-Security and WS-SecureConversation</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="8d3bc-186"> fornisce protezione per le sequenze di WS-Reliable Messaging utilizzando trasporto protetto (HTTPS), composizione con WS-Security e composizione con WS-SecureConversation.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-186"> provides protection for WS-Reliable Messaging sequences by using secure Transport (HTTPS), composition with WS-Security, and composition with WS-Secure Conversation.</span></span> <span data-ttu-id="8d3bc-187">Di seguito è riportato un elenco di vincoli che si applicano a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="8d3bc-187">The following is a list of constraints that apply to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]:</span></span>  
  
-   <span data-ttu-id="8d3bc-188">R2301: per proteggere l'integrità di una sequenza di WS-Reliable Messaging oltre all'integrità e riservatezza dei singoli messaggi, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] richiede che sia necessario utilizzare WS-Secure Conversation.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-188">R2301:To protect the integrity of a WS-Reliable Messaging sequence in addition to the integrity and confidentiality of individual messages, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] requires that WS-Secure Conversation must be used.</span></span>  
  
-   <span data-ttu-id="8d3bc-189">R2302:AWS-Secure Conversation deve essere stabilita prima di stabilire sequenze di WS-Reliable Messaging.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-189">R2302:AWS-Secure Conversation session must be established prior to establishing WS-Reliable Messaging sequence(s).</span></span>  
  
-   <span data-ttu-id="8d3bc-190">R2303: se la durata della sequenza di WS-Reliable Messaging supera la durata della sessione WS-SecureConversation, è necessario rinnovare il `SecurityContextToken` stabilito tramite WS-SecureConversation utilizzando l'associazione WS-Secure Conversation Renewal corrispondente.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-190">R2303: If the WS-Reliable Messaging sequence lifetime exceeds the WS-Secure Conversation session’s lifetime, the `SecurityContextToken` established by using WS-Secure Conversation must be renewed by using the corresponding WS-Secure Conversation Renewal binding.</span></span>  
  
-   <span data-ttu-id="8d3bc-191">B2304:ws-sequenza di messaggistica affidabile o una coppia di sequenze opposte sono sempre associate a una singola sessione WS-SecureConversation.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-191">B2304:WS-Reliable Messaging sequence or a pair of correlated converse sequences are always bound to a single WS-SecureConversation session.</span></span>  
  
     <span data-ttu-id="8d3bc-192">L'origine [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] genera l'elemento `wsse:SecurityTokenReference` nella sezione di estendibilità degli elementi del messaggio `CreateSequence`.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-192">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] source generates the `wsse:SecurityTokenReference` element in the element extensibility section of the `CreateSequence` message.</span></span>  
  
-   <span data-ttu-id="8d3bc-193">Composizione con WS-Secure Conversation R2305:when un `CreateSequence` messaggio deve contenere il `wsse:SecurityTokenReference` elemento.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-193">R2305:When composed with WS-Secure Conversation, a `CreateSequence` message must contain the `wsse:SecurityTokenReference` element.</span></span>  
  
## <a name="ws-reliable-messaging-ws-policy-assertion"></a><span data-ttu-id="8d3bc-194">Asserzione di WS-Policy relativa a WS-Reliable Messaging</span><span class="sxs-lookup"><span data-stu-id="8d3bc-194">WS-Reliable Messaging WS-Policy Assertion</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="8d3bc-195"> utilizza l'asserzione di WS-Policy `wsrm:RMAssertion` relativa a WS-Reliable Messaging per descrivere le funzionalità degli endpoint.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-195"> uses WS-Reliable Messaging WS-Policy Assertion `wsrm:RMAssertion` to describe endpoints capabilities.</span></span> <span data-ttu-id="8d3bc-196">Di seguito è riportato un elenco di vincoli che si applicano a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="8d3bc-196">The following is a list of constraints that apply to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]:</span></span>  
  
-   <span data-ttu-id="8d3bc-197">B3001: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] collega l'asserzione di WS-Policy `wsrm:RMAssertion` agli elementi `wsdl:binding`.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-197">B3001: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] attaches `wsrm:RMAssertion` WS-Policy Assertion to `wsdl:binding` elements.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="8d3bc-198"> supporta i collegamenti agli elementi `wsdl:binding` e `wsdl:port`.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-198"> supports both attachments to `wsdl:binding` and `wsdl:port` elements.</span></span>  
  
-   <span data-ttu-id="8d3bc-199">B3002: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] supporta le proprietà facoltative seguenti dell'asserzione di WS-Reliable Messaging e fornisce controllo su di essi nel [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] `ReliableMessagingBindingElement`:</span><span class="sxs-lookup"><span data-stu-id="8d3bc-199">B3002: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] supports the following optional properties of WS-Reliable Messaging assertion and provides control over them on the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]`ReliableMessagingBindingElement`:</span></span>  
  
    -   `wsrm:InactivityTimeout`  
  
    -   `wsrm:AcknowledgementInterval`  
  
     <span data-ttu-id="8d3bc-200">Di seguito è riportato un esempio.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-200">The following is an example.</span></span>  
  
    ```xml  
    <wsrm:RMAssertion>  
      <wsrm:InactivityTimeout Milliseconds="600000" />  
      <wsrm:AcknowledgementInterval Milliseconds="200" />  
    </wsrm:RMAssertion>  
    ```  
  
## <a name="flow-control-ws-reliable-messaging-extension"></a><span data-ttu-id="8d3bc-201">Estensione di WS-Reliable Messaging per il controllo del flusso</span><span class="sxs-lookup"><span data-stu-id="8d3bc-201">Flow Control WS-Reliable Messaging Extension</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="8d3bc-202"> utilizza l'estendibilità di WS-Reliable Messaging per offrire un controllo facoltativo aggiuntivo più rigido sul flusso di messaggi della sequenza.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-202"> uses WS-Reliable Messaging extensibility to provide optional additional tighter control over sequence message flow.</span></span>  
  
 <span data-ttu-id="8d3bc-203">Controllo di flusso viene abilitato impostando il `ReliableSessionBindingElement`del `FlowControlEnabled``bool` proprietà `true`.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-203">Flow control is enabled by setting the `ReliableSessionBindingElement`’s `FlowControlEnabled``bool` property to `true`.</span></span> <span data-ttu-id="8d3bc-204">Di seguito è riportato un elenco di vincoli che si applicano a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="8d3bc-204">The following is a list of constraints that apply to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]:</span></span>  
  
-   <span data-ttu-id="8d3bc-205">B4001: quando viene attivato il controllo del flusso di Reliable Messaging, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] genera un elemento `netrm:BufferRemaining` nell'estendibilità dell'elemento dell'intestazione `SequenceAcknowledgement`.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-205">B4001: When Reliable Messaging Flow Control is enabled, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generates a `netrm:BufferRemaining` element in the element extensibility of the `SequenceAcknowledgement` header.</span></span>  
  
-   <span data-ttu-id="8d3bc-206">B4002: quando il controllo di flusso di Reliable Messaging è attivato, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] non richiede la presenza di un elemento `netrm:BufferRemaining` nell'intestazione `SequenceAcknowledgement`, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-206">B4002: When Reliable Messaging Flow Control is enabled, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] does not require a `netrm:BufferRemaining` element to be present in `SequenceAcknowledgement` header, as shown in the following example.</span></span>  
  
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
  
-   <span data-ttu-id="8d3bc-207">B4003: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] utilizza `netrm:BufferRemaining` per indicare quanti nuovi messaggi la destinazione di Reliable Messaging è in grado di memorizzare nel buffer.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-207">B4003: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] uses `netrm:BufferRemaining` to indicate how many new messages the Reliable Messaging Destination can buffer.</span></span>  
  
-   <span data-ttu-id="8d3bc-208">B4004: il [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] il servizio di messaggistica affidabile limita il numero di messaggi trasmessi quando l'applicazione di destinazione Reliable Messaging non può ricevere messaggi rapidamente.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-208">B4004:The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Reliable Messaging Service throttles the number of messages transmitted when the Reliable Messaging destination application cannot receive messages quickly.</span></span> <span data-ttu-id="8d3bc-209">La destinazione Reliable Messaging memorizza nel buffer messaggi e il valore dell'elemento scende a 0.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-209">The Reliable Messaging destination buffers messages and the element’s value drops to 0.</span></span>  
  
-   <span data-ttu-id="8d3bc-210">B4005: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] genera valori integer `netrm:BufferRemaining` tra 0 e 4096 incluso e legge valori integer tra 0 e il valore `xs:int` di `maxInclusive`, 214748364 incluso.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-210">B4005: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generates `netrm:BufferRemaining` integer values between 0 and 4096 inclusive, and reads integer values between 0 and `xs:int`’s `maxInclusive` value 214748364 inclusive.</span></span>  
  
## <a name="message-exchange-patterns"></a><span data-ttu-id="8d3bc-211">Modelli di scambio dei messaggi</span><span class="sxs-lookup"><span data-stu-id="8d3bc-211">Message Exchange Patterns</span></span>  
 <span data-ttu-id="8d3bc-212">Contenuto della sezione viene illustrato il comportamento di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] quando WS-Reliable Messaging viene utilizzato per modelli di scambio di messaggi diversi.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-212">This section describes [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]'s behavior when WS-Reliable Messaging is used for different Message Exchange Patterns.</span></span> <span data-ttu-id="8d3bc-213">Per ogni modello di scambio di messaggi, vengono presi in considerazione i due scenari di distribuzione seguenti:</span><span class="sxs-lookup"><span data-stu-id="8d3bc-213">For each Message Exchange Pattern the following two deployments scenarios are considered:</span></span>  
  
-   <span data-ttu-id="8d3bc-214">Iniziatore non indirizzabile: l'iniziatore si trova dietro a un firewall; il risponditore può recapitare messaggi all'iniziatore solo su risposte HTTP.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-214">Non-Addressable Initiator: Initiator is behind firewall; Responder can deliver messages to Initiator only on HTTP responses.</span></span>  
  
-   <span data-ttu-id="8d3bc-215">Iniziatore indirizzabile: le richieste HTTP possono essere inviate sia all'iniziatore che al risponditore. In altre parole, è possibile stabilire due connessioni HTTP opposte.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-215">Addressable Initiator: Initiator and Responder both can be sent HTTP requests; in other words, two converse HTTP connections can be established.</span></span>  
  
### <a name="one-way-non-addressable-initiator"></a><span data-ttu-id="8d3bc-216">Iniziatore unidirezionale, non indirizzabile</span><span class="sxs-lookup"><span data-stu-id="8d3bc-216">One-way, Non-addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="8d3bc-217">Binding</span><span class="sxs-lookup"><span data-stu-id="8d3bc-217">Binding</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="8d3bc-218"> fornisce un modello unidirezionale di scambio di messaggi che utilizza una sola sequenza in un solo canale HTTP.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-218"> provides a one-way message exchange pattern using one sequence over one HTTP channel.</span></span> <span data-ttu-id="8d3bc-219">In [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] vengono utilizzate le richieste HTTP per trasmettere tutti i messaggi da RMS a RMD e la risposta HTTP per trasmettere tutti i messaggi da RMD a RMS.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-219">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] uses the HTTP requests to transmit all messages from the RMS to the RMD and the HTTP response to transmit all messages from the RMD to the RMS.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="8d3bc-220">Scambio CreateSequence</span><span class="sxs-lookup"><span data-stu-id="8d3bc-220">CreateSequence Exchange</span></span>  
 <span data-ttu-id="8d3bc-221">L'iniziatore [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] genera un messaggio `CreateSequence` senza offerta.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-221">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator generates a `CreateSequence` message with no offer.</span></span> <span data-ttu-id="8d3bc-222">Il risponditore [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] assicura che `CreateSequence` non abbia alcuna offerta prima di creare una sequenza.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-222">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder ensures the `CreateSequence` has no offer before creating a sequence.</span></span> <span data-ttu-id="8d3bc-223">Il risponditore [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] risponde alla richiesta `CreateSequence` con un messaggio `CreateSequenceResponse`.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-223">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder replies to the `CreateSequence` request with a `CreateSequenceResponse` message.</span></span>  
  
#### <a name="sequenceacknowledgement"></a><span data-ttu-id="8d3bc-224">SequenceAcknowledgement</span><span class="sxs-lookup"><span data-stu-id="8d3bc-224">SequenceAcknowledgement</span></span>  
 <span data-ttu-id="8d3bc-225">L'iniziatore [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] elabora gli acknowledgement sulla risposta di tutti i messaggi tranne il messaggio `CreateSequence` e i messaggi di errore.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-225">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator processes acknowledgements on the reply of all messages except the `CreateSequence` message and fault messages.</span></span> <span data-ttu-id="8d3bc-226">Il risponditore [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] genera sempre un acknowledgement autonomo in risposta alla sequenza e ai messaggi `AckRequested`.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-226">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder always generates a stand-alone acknowledgement in the response to both sequence and `AckRequested` messages.</span></span>  
  
#### <a name="terminatesequence-message"></a><span data-ttu-id="8d3bc-227">Messaggio TerminateSequence</span><span class="sxs-lookup"><span data-stu-id="8d3bc-227">TerminateSequence message</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="8d3bc-228"> considera `TerminateSequence` come un'operazione unidirezionale, in cui cioè la risposta HTTP ha un corpo vuoto e il codice di stato HTTP 202.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-228"> treats `TerminateSequence` as a one-way operation, meaning the HTTP response has an empty body and HTTP 202 status code.</span></span>  
  
### <a name="one-way-addressable-initiator"></a><span data-ttu-id="8d3bc-229">Iniziatore unidirezionale, indirizzabile</span><span class="sxs-lookup"><span data-stu-id="8d3bc-229">One Way, Addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="8d3bc-230">Binding</span><span class="sxs-lookup"><span data-stu-id="8d3bc-230">Binding</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="8d3bc-231"> fornisce un modello unidirezionale di scambio di messaggi che utilizza una sola sequenza su un canale HTTP in ingresso e in uscita.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-231"> provides a one-way message exchange pattern using one sequence over an inbound and an outbound Http channel.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="8d3bc-232"> utilizza le richieste HTTP per trasmettere tutti i messaggi.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-232"> uses the HTTP requests to transmit all messages.</span></span> <span data-ttu-id="8d3bc-233">Tutte le risposte HTTP hanno un corpo vuoto e un codice di stato HTTP 202.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-233">All HTTP responses have an empty body and HTTP 202 status code.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="8d3bc-234">Scambio CreateSequence</span><span class="sxs-lookup"><span data-stu-id="8d3bc-234">CreateSequence Exchange</span></span>  
 <span data-ttu-id="8d3bc-235">L'iniziatore [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] genera un messaggio `CreateSequence` senza offerta.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-235">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator generates a `CreateSequence` message with no offer.</span></span> <span data-ttu-id="8d3bc-236">Il risponditore [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] assicura che `CreateSequence` non abbia alcuna offerta prima di creare una sequenza.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-236">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder ensures that the `CreateSequence` has no offer before creating a sequence.</span></span> <span data-ttu-id="8d3bc-237">Il risponditore [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] trasmette il messaggio `CreateSequenceResponse` su una richiesta HTTP indirizzata con il riferimento endpoint `ReplyTo`.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-237">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder transmits the `CreateSequenceResponse` message on an HTTP request addressed with the `ReplyTo` endpoint reference.</span></span>  
  
### <a name="duplex-addressable-initiator"></a><span data-ttu-id="8d3bc-238">Iniziatore duplex, indirizzabile</span><span class="sxs-lookup"><span data-stu-id="8d3bc-238">Duplex, Addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="8d3bc-239">Binding</span><span class="sxs-lookup"><span data-stu-id="8d3bc-239">Binding</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="8d3bc-240"> fornisce un modello di scambio di messaggi bidirezionale completamente asincrono che utilizza due sequenze su un canale HTTP in ingresso e su uno in uscita.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-240"> provides a fully asynchronous two-way message exchange pattern using two sequences over an inbound and an outbound HTTP channel.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="8d3bc-241"> utilizza le richieste HTTP per trasmettere tutti i messaggi.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-241"> uses the HTTP requests to transmit all messages.</span></span> <span data-ttu-id="8d3bc-242">Tutte le risposte HTTP hanno un corpo vuoto e un codice di stato HTTP 202.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-242">All HTTP responses have an empty body and HTTP 202 status code.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="8d3bc-243">Scambio CreateSequence</span><span class="sxs-lookup"><span data-stu-id="8d3bc-243">CreateSequence Exchange</span></span>  
 <span data-ttu-id="8d3bc-244">L'iniziatore [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] genera un messaggio `CreateSequence` con un'offerta.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-244">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator generates a `CreateSequence` message with an offer.</span></span> <span data-ttu-id="8d3bc-245">Il risponditore [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] assicura che `CreateSequence` abbia un'offerta prima di creare una sequenza.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-245">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder ensures that the `CreateSequence` has an offer before creating a sequence.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="8d3bc-246"> invia `CreateSequenceResponse` sulla richiesta HTTP indirizzata al riferimento dell'endpoint `CreateSequence` di `ReplyTo`.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-246"> sends the `CreateSequenceResponse` on the HTTP request addressed to the `CreateSequence`’s `ReplyTo` endpoint reference.</span></span>  
  
#### <a name="sequence-lifetime"></a><span data-ttu-id="8d3bc-247">Durata della sequenza</span><span class="sxs-lookup"><span data-stu-id="8d3bc-247">Sequence Lifetime</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="8d3bc-248"> tratta le due sequenze come una sessione completamente duplex.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-248"> treats the two sequences as one fully duplex session.</span></span>  
  
 <span data-ttu-id="8d3bc-249">Dopo la generazione di un errore che origina errori in una sequenza, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] si aspetta che l'endpoint crei errori in entrambe le sequenze.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-249">Upon generating a fault that faults one sequence, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] expects the remote endpoint to fault both sequences.</span></span> <span data-ttu-id="8d3bc-250">Dopo la lettura di un errore che origina errori in una sequenza, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] crea errori in entrambe le sequenze.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-250">Upon reading a fault that faults one sequence, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] faults both sequences.</span></span>  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="8d3bc-251"> può chiudere la sequenza in uscita e continuare a elaborare i messaggi sulla sua sequenza in ingresso.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-251"> can close its outbound sequence and continue to process messages on its inbound sequence.</span></span> <span data-ttu-id="8d3bc-252">Per contro, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] può elaborare la chiusura della sequenza in ingresso e continuare a inviare i messaggi sulla sua sequenza in uscita.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-252">Conversely, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] can process the close of the inbound sequence and continue to send messages on its outbound sequence.</span></span>  
  
### <a name="request-reply-non-addressable-initiator"></a><span data-ttu-id="8d3bc-253">Iniziatore request/reply non indirizzabile</span><span class="sxs-lookup"><span data-stu-id="8d3bc-253">Request-Reply, Non-Addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="8d3bc-254">Binding</span><span class="sxs-lookup"><span data-stu-id="8d3bc-254">Binding</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="8d3bc-255"> fornisce un modello di scambio di messaggi request/reply e unidirezionale che utilizza due sequenze su un canale HTTP.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-255"> provides a one-way and request-reply message exchange pattern using two sequences over one HTTP channel.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="8d3bc-256"> utilizza le richieste HTTP per trasmettere i messaggi della sequenza di richiesta e utilizza le risposte HTTP per trasmettere i messaggi della sequenza di risposte.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-256"> uses the HTTP requests to transmit the request sequence’s messages and uses the HTTP responses to transmit the reply sequence’s messages.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="8d3bc-257">Scambio CreateSequence</span><span class="sxs-lookup"><span data-stu-id="8d3bc-257">CreateSequence Exchange</span></span>  
 <span data-ttu-id="8d3bc-258">L'iniziatore [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] genera un messaggio `CreateSequence` con un'offerta.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-258">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator generates a `CreateSequence` message with an offer.</span></span> <span data-ttu-id="8d3bc-259">Il risponditore [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] assicura che `CreateSequence` abbia un'offerta prima di creare una sequenza.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-259">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder ensures that the `CreateSequence` has an offer before creating a sequence.</span></span> <span data-ttu-id="8d3bc-260">Il risponditore [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] risponde alla richiesta `CreateSequence` con un messaggio `CreateSequenceResponse`.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-260">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder replies to the `CreateSequence` request with a `CreateSequenceResponse` message.</span></span>  
  
#### <a name="one-way-message"></a><span data-ttu-id="8d3bc-261">Messaggio unidirezionale</span><span class="sxs-lookup"><span data-stu-id="8d3bc-261">One-way Message</span></span>  
 <span data-ttu-id="8d3bc-262">Per completare correttamente un protocollo di scambio di messaggi unidirezionale, l'iniziatore [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] trasmette un messaggio della sequenza di richiesta sulla richiesta HTTP e riceve un messaggio `SequenceAcknowledgement` autonomo sulla risposta HTTP.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-262">To complete a one-way message exchange protocol successfully, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator transmits a request sequence message on the HTTP request and receives a standalone `SequenceAcknowledgement` message on the HTTP response.</span></span> <span data-ttu-id="8d3bc-263">`SequenceAcknowledgement` deve riconoscere il messaggio trasmesso.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-263">The `SequenceAcknowledgement` must acknowledge the message transmitted.</span></span>  
  
 <span data-ttu-id="8d3bc-264">Il risponditore [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] può rispondere alla richiesta con un acknowledgement, un errore o una risposta con un corpo vuoto e un codice di stato HTTP 202.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-264">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder can reply to the request with an acknowledgement, a fault, or a response with an empty body and HTTP 202 status code.</span></span>  
  
#### <a name="two-way-messages"></a><span data-ttu-id="8d3bc-265">Messaggi bidirezionali</span><span class="sxs-lookup"><span data-stu-id="8d3bc-265">Two Way Messages</span></span>  
 <span data-ttu-id="8d3bc-266">Per completare correttamente un protocollo di scambio di messaggi bidirezionale, l'iniziatore [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] trasmette un messaggio della sequenza di richiesta sulla richiesta HTTP e riceve un messaggio della sequenza di risposta sulla risposta HTTP.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-266">To complete a two way message exchange protocol successfully, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator transmits a request sequence message on the HTTP request and receives a reply sequence message on the HTTP response.</span></span> <span data-ttu-id="8d3bc-267">La risposta deve contenere un `SequenceAcknowledgement` che riconosce che il messaggio della sequenza di richiesta è stato trasmesso.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-267">The response must carry a `SequenceAcknowledgement` acknowledging the request sequence message transmitted.</span></span>  
  
 <span data-ttu-id="8d3bc-268">Il risponditore [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] può rispondere alla richiesta con una risposta dell'applicazione, un errore o una risposta con un corpo vuoto e un codice di stato HTTP 202.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-268">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder can reply to the request with an application reply, a fault or a response with an empty body and HTTP 202 status code.</span></span>  
  
 <span data-ttu-id="8d3bc-269">A causa della presenza di messaggi unidirezionali e del tempo delle risposte dell'applicazione, il numero di sequenza del messaggio della sequenza di richiesta e il numero di sequenza del messaggio di risposta non hanno alcuna correlazione.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-269">Because of the presence of one-way messages and the timing of application replies, the request sequence message’s sequence number and the response message’s sequence number have no correlation.</span></span>  
  
#### <a name="retrying-replies"></a><span data-ttu-id="8d3bc-270">Nuovi tentativi di risposte</span><span class="sxs-lookup"><span data-stu-id="8d3bc-270">Retrying Replies</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="8d3bc-271"> si basa sulla correlazione request/reply HTTP per la correlazione del protocollo di scambio di messaggi bidirezionali.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-271"> relies on HTTP request-reply correlation for two-way message exchange protocol correlation.</span></span> <span data-ttu-id="8d3bc-272">Di conseguenza, l'iniziatore [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] non smette di tentare un messaggio della sequenza di richiesta quando tale messaggio viene riconosciuto, ma piuttosto quando la risposta HTTP contiene un acknowledgement, un messaggio dell'utente o un errore.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-272">Because of this, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator does not stop retrying a request sequence message when the request sequence message is acknowledged but rather when the HTTP response carries an acknowledgement, user message, or fault.</span></span> <span data-ttu-id="8d3bc-273">Il risponditore [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ritenta le risposte sulla parte della richiesta HTTP della richiesta a cui è correlata la risposta.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-273">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder retries replies on the HTTP request leg of the request to which the reply is correlated.</span></span>  
  
#### <a name="lastmessage-exchange"></a><span data-ttu-id="8d3bc-274">Scambio LastMessage</span><span class="sxs-lookup"><span data-stu-id="8d3bc-274">LastMessage Exchange</span></span>  
 <span data-ttu-id="8d3bc-275">L'iniziatore [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] genera e trasmette un ultimo messaggio con corpo vuoto sulla parte della richiesta HTTP.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-275">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator generates and transmits an empty bodied last message on the HTTP request leg.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="8d3bc-276"> richiede una risposta, ma ignora il messaggio di risposta effettivo.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-276"> requires a response but ignores the actual response message.</span></span> <span data-ttu-id="8d3bc-277">Il risponditore [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] risponde all'ultimo messaggio con corpo vuoto della sequenza di richiesta con un ultimo messaggio con corpo vuoto della sequenza di risposta.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-277">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder replies to the request sequence’s empty-bodied last message with the reply sequence’s empty-bodied last message.</span></span>  
  
 <span data-ttu-id="8d3bc-278">Se il risponditore [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] riceve un ultimo messaggio in cui l'URI di azione non è http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] risponde con un ultimo messaggio.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-278">If the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder receives a last message in which the action URI is not http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] replies with a last message.</span></span> <span data-ttu-id="8d3bc-279">Nel caso di un protocollo di scambio di messaggi bidirezionale, l'ultimo messaggio contiene il messaggio dell'applicazione; nel caso, invece, di un protocollo di scambio di messaggi unidirezionale, l'ultimo messaggio è vuoto.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-279">In the case of a two-way message exchange protocol, the last message carries the application message; in the case of a one-way message exchange protocol, the last message is empty.</span></span>  
  
 <span data-ttu-id="8d3bc-280">Il risponditore [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] non richiede un acknowledgement per l'ultimo messaggio con corpo vuoto della sequenza di risposta.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-280">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder does not require an acknowledgement for the reply sequence’s empty-bodied last message.</span></span>  
  
#### <a name="terminatesequence-exchange"></a><span data-ttu-id="8d3bc-281">Scambio TerminateSequence</span><span class="sxs-lookup"><span data-stu-id="8d3bc-281">TerminateSequence Exchange</span></span>  
 <span data-ttu-id="8d3bc-282">Quando tutte le richieste hanno ricevuto una risposta valida, l'iniziatore [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] genera e trasmette il messaggio `TerminateSequence` della sequenza di richieste sulla parte della richiesta HTTP.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-282">When all requests have received a valid reply, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator generates and transmits the request sequence’s `TerminateSequence` message on the HTTP request leg.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="8d3bc-283"> richiede una risposta, ma ignora il messaggio di risposta effettivo.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-283"> requires a response but ignores the actual response message.</span></span> <span data-ttu-id="8d3bc-284">Il risponditore [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] risponde al messaggio `TerminateSequence` della sequenza di richiesta con un messaggio `TerminateSequence` della sequenza di risposta.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-284">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder replies to the request sequence’s `TerminateSequence` message with the reply sequence’s `TerminateSequence` message.</span></span>  
  
 <span data-ttu-id="8d3bc-285">In una sequenza di arresto normale, entrambi i messaggi `TerminateSequence` contengono un intervallo completo `SequenceAcknowledgement`.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-285">In a normal shutdown sequence, both `TerminateSequence` messages carry a full range `SequenceAcknowledgement`.</span></span>  
  
### <a name="requestreply-addressable-initiator"></a><span data-ttu-id="8d3bc-286">Iniziatore request/reply, indirizzabile</span><span class="sxs-lookup"><span data-stu-id="8d3bc-286">Request/Reply, Addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="8d3bc-287">Binding</span><span class="sxs-lookup"><span data-stu-id="8d3bc-287">Binding</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="8d3bc-288"> fornisce un modello di scambio di messaggi request/reply che utilizza due sequenze su un canale HTTP in ingresso e su uno in uscita.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-288"> provides a request-reply message exchange pattern using two sequences over an inbound and an outbound HTTP channel.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="8d3bc-289"> utilizza le richieste HTTP per trasmettere tutti i messaggi.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-289"> uses the HTTP requests to transmit all messages.</span></span> <span data-ttu-id="8d3bc-290">Tutte le risposte HTTP hanno un corpo vuoto e un codice di stato HTTP 202.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-290">All HTTP responses have an empty body and HTTP 202 status code.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="8d3bc-291">Scambio CreateSequence</span><span class="sxs-lookup"><span data-stu-id="8d3bc-291">CreateSequence Exchange</span></span>  
 <span data-ttu-id="8d3bc-292">L'iniziatore [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] genera un messaggio `CreateSequence` con un'offerta.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-292">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator generates a `CreateSequence` message with an offer.</span></span> <span data-ttu-id="8d3bc-293">Il risponditore [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] assicura che `CreateSequence` abbia un'offerta prima di creare una sequenza.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-293">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder ensures that the `CreateSequence` has an offer before creating a sequence.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="8d3bc-294"> invia `CreateSequenceResponse` sulla richiesta HTTP indirizzata al riferimento dell'endpoint `CreateSequence` di `ReplyTo`.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-294"> sends the `CreateSequenceResponse` on the HTTP request addressed to the `CreateSequence`’s `ReplyTo` endpoint reference.</span></span>  
  
#### <a name="requestreply-correlation"></a><span data-ttu-id="8d3bc-295">Correlazione request/reply</span><span class="sxs-lookup"><span data-stu-id="8d3bc-295">Request/Reply Correlation</span></span>  
 <span data-ttu-id="8d3bc-296">L'iniziatore [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] assicura che tutti i messaggi di richiesta dell'applicazione presentino un `MessageId` e un riferimento all'endpoint `ReplyTo`.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-296">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator ensures all application request messages bear a `MessageId` and a `ReplyTo` endpoint reference.</span></span> <span data-ttu-id="8d3bc-297">L'iniziatore [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] applica il riferimento endpoint `CreateSequence` del messaggio `ReplyTo` a ogni messaggio di richiesta dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-297">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator applies the `CreateSequence` message’s `ReplyTo` endpoint reference on each application request message.</span></span> <span data-ttu-id="8d3bc-298">Il risponditore [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] richiede che i messaggi di richiesta in ingresso presentino un `MessageId` e `ReplyTo`.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-298">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder requires that incoming request messages bear a `MessageId` and a `ReplyTo`.</span></span> <span data-ttu-id="8d3bc-299">Il risponditore [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] assicura che gli URI dei riferimenti endpoint di `CreateSequence` e di tutti i messaggi di richiesta dell'applicazione siano identici.</span><span class="sxs-lookup"><span data-stu-id="8d3bc-299">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder ensures that the endpoint reference’s URI of both the `CreateSequence` and all application request messages are identical.</span></span>
