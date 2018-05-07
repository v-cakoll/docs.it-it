---
title: Protocollo Reliable Messaging versione 1,1
ms.date: 03/30/2017
ms.assetid: 0da47b82-f8eb-42da-8bfe-e56ce7ba6f59
ms.openlocfilehash: 8ff02bc6953ec1e5030dd0b592a352b7e23ab0d6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="reliable-messaging-protocol-version-11"></a>Protocollo Reliable Messaging versione 1,1
In questo argomento vengono illustrati i dettagli di implementazione di Windows Communication Foundation (WCF) per WS-ReliableMessaging protocollo febbraio 2007 (versione 1.1) necessario per l'interoperatività con il trasporto HTTP. WCF segue la specifica WS-ReliableMessaging con i vincoli e i chiarimenti illustrati in questo argomento. Si noti che il protocollo di versione 1.1 di WS-ReliableMessaging viene implementato a partire dal [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)].  
  
 Il protocollo WS-ReliableMessaging febbraio 2007 protocollo è implementato in WCF per il <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>.  
  
 Per comodità, nell'argomento vengono utilizzati i ruoli seguenti:  
  
-   Iniziatore: il client che inizia la creazione della sequenza di WS-Reliable Message.  
  
-   Risponditore: il servizio che riceve le richieste dell'iniziatore.  
  
 In questo documento vengono utilizzati i prefissi e gli spazi dei nomi riportati nella tabella seguente.  
  
|Prefisso|Spazio dei nomi|  
|-|-|  
|wsrm|http://docs.oasis-open.org/ws-rx/wsrm/200702|  
|netrm|http://schemas.microsoft.com/ws/2006/05/rm|  
|s|http://www.w3.org/2003/05/soap-envelope|  
|wsa|http://schemas.xmlsoap.org/ws/2005/08/addressing|  
|wsse|http://docs.oasis-open.org/wss/2004/01/oasis-200401-wssecurity-secext-1.0.xsd|  
|wsrmp|http://docs.oasis-open.org/ws-rx/wsrmp/200702|  
|netrmp|http://schemas.microsoft.com/ws-rx/wsrmp/200702|  
|wsp|(WS-Policy 1.2 o WS-Policy 1.5)|  
  
## <a name="messaging"></a>Messaggistica  
  
### <a name="sequence-creation"></a>Creazione sequenza  
 Implementa WCF `CreateSequence` e `CreateSequenceResponse` di sequenza dei messaggi per stabilire una messaggistica affidabile. Si applicano i vincoli seguenti:  
  
-   B1101: L'iniziatore WCF utilizza lo stesso riferimento dell'endpoint come le `CreateSequence` del messaggio `ReplyTo`, `AcksTo` e `Offer/Endpoint`.  
  
-   R1102: i riferimenti degli endpoint `AcksTo`, `ReplyTo` e `Offer/Endpoint` nel messaggio `CreateSequence` devono avere valori di indirizzo con rappresentazioni di stringa identiche in modo che corrispondano all'ottetto.  
  
    -   Il risponditore WCF verifica che le parti URI del `AcksTo`, `ReplyTo` e `Endpoint` i riferimenti all'endpoint sono identiche prima di creare una sequenza.  
  
-   R1103: i riferimenti degli endpoint `AcksTo`, `ReplyTo` e `Offer/Endpoint` nel messaggio `CreateSequence` devono avere lo stesso set di parametri di riferimento.  
  
    -   WCF non impone, ma presuppone che fanno riferimento a parametri del `AcksTo`, `ReplyTo` e `Offer/Endpoint` fa riferimento a endpoint in `CreateSequence` siano identici e utilizza i parametri di riferimento dal `ReplyTo` riferimento dell'endpoint per acknowledgement e messaggi in sequenza opposta.  
  
-   B1104: L'iniziatore WCF non genera facoltativo `Expires` oppure `Offer/Expires` elemento il `CreateSequence` messaggio.  
  
-   B1105: Quando si accede al `CreateSequence` messaggio, il risponditore WCF utilizza il `Expires` valore nel `CreateSequence` come elemento il `Expires` valore il `CreateSequenceResponse` elemento. In caso contrario, il risponditore WCF legge e ignora il `Expires` e `Offer/Expires` valori.  
  
-   B1106: Quando si accede ai `CreateSequenceResponse` messaggio, l'iniziatore WCF legge facoltativo `Expires` valore ma non verranno utilizzate.  
  
-   B1107: L'iniziatore WCF e il risponditore genera sempre l'opzione facoltativa `IncompleteSequenceBehavior` elemento il `CreateSequence/Offer` e `CreateSequenceResponse` elementi.  
  
-   B1108: WCF Usa solo il `DiscardFollowingFirstGap` e `NoDiscard` i valori di `IncompleteSequenceBehavior` elemento.  
  
    -   WS-ReliableMessaging utilizza il meccanismo `Offer` per stabilire le due sequenze correlate opposte che formano una sessione.  
  
-   B1109: Se `CreateSequence` contiene un `Offer` elemento, il risponditore WCF unidirezionale respinge la sequenza offerta rispondendo con un `CreateSequenceResponse` senza un `Accept` elemento.  
  
-   B1110: Se un risponditore Reliable Messaging respinge la sequenza offerta, l'iniziatore WCF si verifica un errore nella sequenza appena stabilita.  
  
-   B1111: Se `CreateSequence` non contiene un `Offer` elemento, il risponditore bidirezionale di WCF respinge la sequenza offerta rispondendo con un `CreateSequenceRefused` fault.  
  
-   R1112: quando vengono stabilite due sequenze opposte utilizzando il meccanismo `Offer`, la proprietà `[address]` del riferimento dell'endpoint `CreateSequenceResponse/Accept/AcksTo` deve corrispondere all'URI di destinazione del messaggio `CreateSequence`, byte per byte.  
  
-   R1113: quando vengono stabilite due sequenze opposte utilizzando il meccanismo `Offer`, tutti i messaggi su entrambe le sequenze dall'iniziatore al risponditore devono essere inviati allo stesso riferimento dell'endpoint.  
  
 WCF utilizza WS-ReliableMessaging per stabilire sessioni affidabili tra l'iniziatore e il risponditore. L'implementazione WCF WS-ReliableMessaging offre una sessione affidabile per unidirezionali, request/reply e full duplex modelli di messaggistica. Il meccanismo `Offer` di WS-Reliable Messaging in `CreateSequence` e `CreateSequenceResponse` consente di stabilire due sequenze opposte correlate e fornisce un protocollo della sessione idoneo per tutti gli endpoint del messaggio. Poiché WCF fornisce una garanzia di sicurezza per tale sessione, inclusa la protezione end-to-end per l'integrità della sessione, è consigliabile assicurarsi che i messaggi destinati alla stessa parte arrivino alla stessa destinazione. Ciò consente anche il "piggy-backing" degli acknowledgement della sequenza sui messaggi dell'applicazione. Pertanto, si applicano i vincoli R1102 R1112 e R1113 a WCF.  
  
 Esempio di un messaggio `CreateSequence`.  
  
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
  
 Esempio di un messaggio `CreateSequenceResponse`.  
  
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
  
### <a name="closing-a-sequence"></a>Chiusura di una sequenza  
 WCF Usa il `CloseSequence` e `CloseSequenceResponse` messaggi per un arresto iniziato dall'origine di Reliable Messaging. La destinazione di Reliable Messaging di WCF non inizia l'arresto e l'origine di Reliable Messaging di WCF non supporta un arresto iniziata dalla destinazione di Reliable Messaging. Si applicano i vincoli seguenti:  
  
-   B1201: L'origine di Reliable Messaging di WCF invia sempre un `CloseSequence` messaggio per arrestare la sequenza.  
  
-   B1202: l'origine di Reliable Messaging attende l'acknowledgment dell'intera serie di messaggi della sequenza prima di inviare il messaggio `CloseSequence`.  
  
-   B1203: l'origine di Reliable Messaging include sempre l'elemento facoltativo `LastMsgNumber`. Non lo include se la sequenza non contiene messaggi.  
  
-   R1204: la destinazione di Reliable Messaging non deve iniziare l'arresto inviando un messaggio `CloseSequence`.  
  
-   B1205: al ricevimento un `CloseSequence` messaggio, l'origine di Reliable Messaging di WCF considera la sequenza incompleta e invia un errore.  
  
 Esempio di un messaggio `CloseSequence`.  
  
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
  
### <a name="sequence-termination"></a>Terminazione della sequenza  
 WCF Usa principalmente il `TerminateSequence/TerminateSequenceResponse` handshake dopo aver completato il `CloseSequence/CloseSequenceResponse` handshake. La destinazione di Reliable Messaging di WCF non avviare la terminazione e l'origine di Reliable Messaging non supporta una terminazione iniziata dalla destinazione di Reliable Messaging. Si applicano i vincoli seguenti:  
  
-   B1301: L'iniziatore WCF invia solo la `TerminateSequence` messaggio dopo il completamento dei `CloseSequence/CloseSequenceResponse` handshake.  
  
-   R1302: WCF consente di verificare che il `LastMsgNumber` elemento sia coerenza in tutti `CloseSequence` e `TerminateSequence` i messaggi per una sequenza specificata. Ciò significa che `LastMsgNumber` o non è presente in tutti i messaggi `CloseSequence` e `TerminateSequence`, o è presente e identico in tutti i messaggi `CloseSequence` e `TerminateSequence`.  
  
-   B1303: al ricevimento di un messaggio `TerminateSequence` dopo l'handshake `CloseSequence/CloseSequenceResponse`, la destinazione di Reliable Messaging risponde con un messaggio `TerminateSequenceResponse`. Poiché l'origine di Reliable Messaging dispone dell'acknowledgement finale prima dell'invio del messaggio `TerminateSequence`, la destinazione di Reliable Messaging è a conoscenza della fine della sequenza e richiede immediatamente le risorse.  
  
-   B1304: Durante la ricezione di un `TerminateSequence` messaggio nelle versioni precedenti per il `CloseSequence/CloseSequenceResponse` handshake, la destinazione di Reliable Messaging di WCF risponde con un `TerminateSequenceResponse` messaggio. Se la destinazione di Reliable Messaging stabilisce che non vi sono incoerenze nella sequenza, attende per il periodo di tempo specificato dalla destinazione dell'applicazione prima di richiedere le risorse, per offrire al client la possibilità di ricevere l'acknowledgement finale. In caso contrario, la destinazione di Reliable Messaging richiede immediatamente le risorse e indica alla destinazione dell'applicazione che la sequenza termina in modo dubbio generando l'evento `Faulted`.  
  
 Esempio di un messaggio `TerminateSequence`.  
  
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
  
### <a name="sequences"></a>Sequenze  
 Di seguito è riportato un elenco di vincoli che si applicano alle sequenze:  
  
-   Genera l'errore B1401:WCF e accessi sequenza numeri non superiori a `xs:long`del valore inclusivo massimo, 9223372036854775807.  
  
 Esempio di intestazione `Sequence`.  
  
```xml  
<wsrm:Sequence s:mustUnderstand="1">  
  <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
  <wsrm:MessageNumber>1</wsrm:MessageNumber>  
</wsrm:Sequence>  
```  
  
### <a name="request-acknowledgement"></a>Acknowledgement della richiesta  
 WCF Usa il `AckRequested` intestazione come meccanismo keep-alive.  
  
 Esempio di intestazione `AckRequested`.  
  
```xml  
<wsrm:AckRequested>  
  <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
</wsrm:AckRequested>  
```  
  
### <a name="sequenceacknowledgement"></a>SequenceAcknowledgement  
 WCF utilizza un meccanismo "piggy-back" per gli acknowledgement di sequenza forniti in WS-Reliable Messaging. Si applicano i vincoli seguenti:  
  
-   R1601: Quando due sequenze vengono stabilite opposte utilizzando il `Offer` meccanismo, il `SequenceAcknowledgement` intestazione può essere incluso nei messaggi dell'applicazione trasmesso al destinatario prescelto. L'endpoint remoto deve essere in grado di accedere a un'intestazione `SequenceAcknowledgement` sottoposta a piggyback.  
  
-   B1602: WCF non genera `SequenceAcknowledgement` intestazioni contenenti `Nack` elementi. WCF verifica che ogni `Nack` elemento contiene un numero di sequenza, ma altrimenti ignora il `Nack` elemento e valore.  
  
 Esempio di intestazione `SequenceAcknowledgement`.  
  
```xml  
<wsrm:SequenceAcknowledgement>  
  <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
  <wsrm:AcknowledgementRange Lower="1" Upper="1"></wsrm:AcknowledgementRange>  
</wsrm:SequenceAcknowledgement>  
```  
  
### <a name="ws-reliablemessaging-faults"></a>Errori WS-ReliableMessaging  
 Di seguito è un elenco di vincoli che si applicano all'implementazione WCF di errori WS-ReliableMessaging. Si applicano i vincoli seguenti:  
  
-   B1701: WCF non genera `MessageNumberRollover` errori.  
  
-   B1702: Su SOAP 1.2 quando l'endpoint del servizio raggiunge il limite di connessione e non è in grado di elaborare nuove connessioni, WCF genera nidificate `CreateSequenceRefused` codice secondario, di errore `netrm:ConnectionLimitReached`, come illustrato nell'esempio seguente.  
  
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
  
### <a name="ws-addressing-faults"></a>Errori WS-Addressing  
 Poiché il protocollo WS-ReliableMessaging utilizza WS-Addressing, l'implementazione WCF WS-Reliable Messaging potrebbe generare e trasmettere errori WS-Addressing. In questa sezione vengono trattati gli errori WS-Addressing che WCF in modo esplicito genera e trasmette a livello del protocollo WS-ReliableMessaging:  
  
-   B1801:WCF genera e trasmette il `Message Addressing Header Required` di errore quando viene soddisfatta una delle operazioni seguenti:  
  
    -   In un messaggio `CreateSequence`, `CloseSequence` o `TerminateSequence` manca un'intestazione `MessageId`.  
  
    -   In un messaggio `CreateSequence`, `CloseSequence` o `TerminateSequence` manca un'intestazione `ReplyTo`.  
  
    -   In un messaggio `CreateSequenceResponse`, `CloseSequenceResponse` o `TerminateSequenceResponse` manca un'intestazione `RelatesTo`.  
  
-   B1802:WCF genera e trasmette il `Endpoint Unavailable` errore per indicare nessun endpoint in ascolto in grado di elaborare la sequenza in base all'esame delle intestazioni di indirizzamento nel `CreateSequence` messaggio.  
  
## <a name="protocol-composition"></a>Composizione del protocollo  
  
### <a name="composition-with-ws-addressing"></a>Composizione con WS-Addressing  
 WCF supporta due versioni di WS-Addressing: WS-Addressing 2004/08 [WS-ADDR] e W3C WS-Addressing 1.0 Recommendation [WS-ADDR-CORE] e [WS-ADDR-SOAP].  
  
 Anche se la specifica WS-ReliableMessaging menziona solo WS-Addressing 2004/08, non limita la versione WS-Addressing da utilizzare. Di seguito è un elenco di vincoli che si applicano a WCF:  
  
-   R2101: sia WS-Addressing 2004/08 che WS-Addressing 1.0 possono essere utilizzati con WS-Reliable Messaging.  
  
-   R2102: è necessario utilizzare una sola versione di WS-Addressing in una data sequenza di WS-Reliable Messaging o in una coppia di sequenze opposte correlate tramite il meccanismo `Offer`.  
  
### <a name="composition-with-soap"></a>Composizione con SOAP  
 WCF supporta l'utilizzo di SOAP 1.1 e SOAP 1.2 con WS-Reliable Messaging.  
  
### <a name="composition-with-ws-security-and-ws-secureconversation"></a>Composizione con WS-Security e WS-SecureConversation  
 WCF fornisce la protezione per le sequenze di WS-ReliableMessaging utilizzando sicuri trasporto (HTTPS), composizione con WS-Security e composizione con WS-SecureConversation. Il protocollo WS-Reliable Messaging 1.1, WS-Security 1.1 e il protocollo WS-SecureConversation 1.3 devono essere utilizzati insieme. Di seguito è un elenco di vincoli che si applicano a WCF:  
  
-   R2301: Per proteggere l'integrità di una sequenza di WS-Reliable Messaging oltre all'integrità e riservatezza dei singoli messaggi, WCF, è necessario che è necessario utilizzare WS-Secure Conversation.  
  
-   R2302:AWS-Secure Conversation deve essere stabilita prima di stabilire le sequenze di WS-ReliableMessaging.  
  
-   R2303: se la durata della sequenza di WS-Reliable Messaging supera la durata della sessione WS-SecureConversation, è necessario rinnovare il `SecurityContextToken` stabilito tramite WS-SecureConversation utilizzando l'associazione WS-Secure Conversation Renewal corrispondente.  
  
-   B2304:ws-sequenza ReliableMessaging o una coppia di sequenze opposte sono sempre associate a una singola sessione WS-SecureConversation.  
  
-   R2305: Caso di composizione con WS-SecureConversation, il risponditore WCF richiede che il `CreateSequence` messaggio contiene il `wsse:SecurityTokenReference` elemento e il `wsrm:UsesSequenceSTR` intestazione.  
  
 Esempio di intestazione `UsesSequenceSTR`.  
  
```xml  
<wsrm:UsesSequenceSTR></wsrm:UsesSequenceSTR>  
```  
  
### <a name="composition-with-ssltls-sessions"></a>Composizione con sessioni SSL/TLS  
 WCF non supporta la composizione con sessioni SSL/TLS:  
  
-   B2401: WCF non genera la `wsrm:UsesSequenceSSL` intestazione.  
  
-   R2402: Un iniziatore Reliable Messaging non deve essere inviato un `CreateSequence` dei messaggi con un `wsrm:UsesSequenceSSL` intestazione a un risponditore WCF.  
  
### <a name="composition-with-ws-policy"></a>Composizione con WS-Policy  
 WCF supporta due versioni di WS-Policy: WS-Policy 1.2 e WS-Policy 1.5.  
  
## <a name="ws-reliablemessaging-ws-policy-assertion"></a>Asserzione di WS-Policy relativa a WS-ReliableMessaging  
 WCF utilizza l'asserzione di WS-Policy WS-ReliableMessaging `wsrm:RMAssertion` per descrivere le funzionalità degli endpoint. Di seguito è un elenco di vincoli che si applicano a WCF:  
  
-   B3001: WCF Allega `wsrmn:RMAssertion` asserzione WS-Policy relativa a `wsdl:binding` elementi. WCF supporta i collegamenti agli `wsdl:binding` e `wsdl:port` elementi.  
  
-   B3002: WCF non lo genera mai il `wsp:Optional` tag.  
  
-   B3003: Quando si accede ai `wsrmp:RMAssertion` asserzione di WS-Policy, WCF ignora il `wsp:Optional` tag e considera obbligatorio il criterio WS-RM.  
  
-   R3004: Poiché WCF non esegue la composizione con sessioni SSL/TLS, WCF non accetta il criterio che specifica `wsrmp:SequenceTransportSecurity`.  
  
-   B3005: WCF genera sempre il `wsrmp:DeliveryAssurance` elemento.  
  
-   B3006: WCF specifica sempre la `wsrmp:ExactlyOnce` garanzia di recapito.  
  
-   B3007: WCF genera e legge le proprietà seguenti dell'asserzione WS-ReliableMessaging e fornisce controllo su di essi in WCF`ReliableSessionBindingElement`:  
  
    -   `netrmp:InactivityTimeout`  
  
    -   `netrmp:AcknowledgementInterval`  
  
     Esempio di `RMAssertion`.  
  
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
  
## <a name="flow-control-ws-reliablemessaging-extension"></a>Estensione di WS-ReliableMessaging per il controllo del flusso  
 WCF utilizza l'estendibilità di WS-ReliableMessaging per fornire un controllo facoltativo aggiuntivo sul flusso di messaggi di sequenza.  
  
 Controllo di flusso viene abilitato impostando il `ReliableSessionBindingElement`del `FlowControlEnabled``boolean` proprietà `true`. Di seguito è un elenco di vincoli che si applicano a WCF:  
  
-   B4001: Quando è abilitata la messaggistica affidabile flusso di controllo, WCF genera una `netrm:BufferRemaining` elemento nell'estendibilità dell'elemento di `SequenceAcknowledgement` intestazione, come illustrato nell'esempio seguente.  
  
    ```xml  
    <wsrm:SequenceAcknowledgement>  
      <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
      <wsrm:AcknowledgementRange Upper="1" Lower="1"/>             
      <netrm:BufferRemaining>8</netrm:BufferRemaining>  
    </wsrm:SequenceAcknowledgement>  
    ```  
  
-   B4002: Anche quando la messaggistica affidabile flusso di controllo è abilitato, WCF non richiede un `netrm:BufferRemaining` elemento di `SequenceAcknowledgement` intestazione.  
  
-   B4003: Destinazione di WCF Reliable Messaging utilizza `netrm:BufferRemaining` per indicare quanti messaggi nuovi è possibile memorizzare nel buffer.  
  
-   B4004:when Reliable Messaging flusso di controllo è abilitato, l'origine di messaggistica affidabile WCF utilizza il valore di `netrm:BufferRemaining` per la trasmissione dei messaggi di limitazione.  
  
-   B4005: Genera l'errore WCF `netrm:BufferRemaining` intero i valori compresi tra 0 e 4096 incluso e legge valori integer compresi tra 0 e `xs:int`del `maxInclusive` valore 214748364 incluso.  
  
## <a name="message-exchange-patterns"></a>Modelli di scambio dei messaggi  
 Questa sezione descrive il comportamento di WCF quando WS-ReliableMessaging è utilizzato per modelli di scambio di messaggi diversi. Per ogni modello di scambio di messaggi, vengono presi in considerazione i due scenari di distribuzione seguenti:  
  
-   Iniziatore non indirizzabile: l'iniziatore si trova dietro a un firewall; il risponditore può recapitare messaggi all'iniziatore solo su risposte HTTP.  
  
-   Iniziatore indirizzabile: le richieste HTTP possono essere inviate sia all'iniziatore che al risponditore. In altre parole, è possibile stabilire due connessioni HTTP opposte.  
  
### <a name="one-way-non-addressable-initiator"></a>Iniziatore unidirezionale, non indirizzabile  
  
#### <a name="binding"></a>Binding  
 WCF fornisce un modello di scambio di messaggi unidirezionale utilizza una sola sequenza in un solo canale HTTP. WCF utilizza le richieste HTTP per trasmettere tutti i messaggi dall'iniziatore il risponditore e le risposte HTTP per trasmettere tutti i messaggi dal risponditore all'iniziatore.  
  
#### <a name="createsequence-exchange"></a>Scambio CreateSequence  
 L'iniziatore WCF trasmette un `CreateSequence` messaggio senza alcun `Offer` elemento su una richiesta HTTP e non prevede il `CreateSequenceResponse` messaggio sulla risposta HTTP. Il risponditore WCF crea una sequenza e trasmette il `CreateSequenceResponse` messaggio senza alcun `Accept` elemento sulla risposta HTTP.  
  
#### <a name="sequenceacknowledgement"></a>SequenceAcknowledgement  
 L'iniziatore WCF elabora gli acknowledgement sulla risposta di tutti i messaggi tranne il `CreateSequence` messaggi e messaggi di errore. Il risponditore WCF trasmette sempre un acknowledgement autonomo sulla risposta HTTP a tutte le sequenze e `AckRequested` i messaggi.  
  
#### <a name="closesequence-exchange"></a>Scambio CloseSequence  
 L'iniziatore WCF trasmette un `CloseSequence` messaggio su una richiesta HTTP e non prevede il `CreateSequenceResponse` messaggio sulla risposta HTTP. Il risponditore WCF trasmette il `CloseSequenceResponse` messaggio sulla risposta HTTP.  
  
#### <a name="terminatesequence-exchange"></a>Scambio TerminateSequence  
 L'iniziatore WCF trasmette un `TerminateSequence` messaggio su una richiesta HTTP e non prevede il `TerminateSequenceResponse` messaggio sulla risposta HTTP. Il risponditore WCF trasmette il `TerminateSequenceResponse` messaggio sulla risposta HTTP.  
  
### <a name="one-way-addressable-initiator"></a>Iniziatore unidirezionale, indirizzabile  
  
#### <a name="binding"></a>Binding  
 WCF fornisce un modello di scambio di messaggi unidirezionale utilizza una sola sequenza su uno in ingresso e un solo canale HTTP in uscita. WCF utilizza le richieste HTTP per trasmettere tutti i messaggi. Tutte le risposte HTTP hanno un corpo vuoto e un codice di stato HTTP 202.  
  
#### <a name="createsequence-exchange"></a>Scambio CreateSequence  
 L'iniziatore WCF trasmette un `CreateSequence` messaggio senza alcun `Offer` elemento su una richiesta HTTP. Il risponditore WCF crea una sequenza e trasmette il `CreateSequenceResponse` messaggio senza alcun `Accept` elemento su una richiesta HTTP.  
  
### <a name="duplex-addressable-initiator"></a>Iniziatore duplex, indirizzabile  
  
#### <a name="binding"></a>Binding  
 WCF fornisce un modello di scambio di messaggi bidirezionale completamente asincrono usando due sequenze su uno in ingresso e un solo canale HTTP in uscita. Questo modello di scambio può essere combinato con il modello di scambio di messaggi dell'iniziatore `Request/Reply`, `Addressable` in modo limitato. WCF utilizza le richieste HTTP per trasmettere tutti i messaggi. Tutte le risposte HTTP hanno un corpo vuoto e un codice di stato HTTP 202.  
  
#### <a name="createsequence-exchange"></a>Scambio CreateSequence  
 L'iniziatore WCF trasmette un `CreateSequence` dei messaggi con un `Offer` elemento su una richiesta HTTP. Il risponditore WCF assicura che il `CreateSequence` ha un `Offer` elemento, quindi crea una sequenza e trasmette il `CreateSequenceResponse` dei messaggi con un `Accept` elemento.  
  
#### <a name="sequence-lifetime"></a>Durata della sequenza  
 WCF tratta le due sequenze come una sessione completamente duplex.  
  
 Dopo la generazione di un errore che origina errori in un'unica sequenza, WCF prevede che l'endpoint remoto errori in entrambe le sequenze. Dopo la lettura di un errore che origina errori in un'unica sequenza, WCF si verifica un errore entrambe le sequenze.  
  
 WCF è possibile chiudere la relativa sequenza in uscita e continuare a elaborare i messaggi sulla sua sequenza in ingresso. Al contrario, WCF può elaborare la chiusura della sequenza in ingresso e continuare a inviare i messaggi sulla sua sequenza in uscita.  
  
### <a name="request-reply-and-one-way-non-addressable-initiator"></a>Iniziatore request/reply e unidirezionale, non indirizzabile  
  
#### <a name="binding"></a>Binding  
 WCF fornisce unidirezionale e modello di scambio di messaggi request/reply usando due sequenze su un canale HTTP. WCF utilizza le richieste HTTP per trasmettere tutti i messaggi dall'iniziatore il risponditore e le risposte HTTP per trasmettere tutti i messaggi dal risponditore all'iniziatore.  
  
#### <a name="createsequence-exchange"></a>Scambio CreateSequence  
 L'iniziatore WCF trasmette un `CreateSequence` dei messaggi con un `Offer` elemento su una richiesta HTTP e non prevede il `CreateSequenceResponse` messaggio sulla risposta HTTP. Il risponditore WCF crea una sequenza e trasmette il `CreateSequenceResponse` dei messaggi con un `Accept` elemento sulla risposta HTTP.  
  
#### <a name="one-way-message"></a>Messaggio unidirezionale  
 Per completare correttamente uno scambio di messaggi unidirezionale, l'iniziatore WCF trasmette un messaggio di sequenza di richiesta sulla richiesta HTTP e riceve un computer autonomo `SequenceAcknowledgement` messaggio sulla risposta HTTP. `SequenceAcknowledgement` deve riconoscere il messaggio trasmesso.  
  
 Il risponditore WCF può rispondere alla richiesta con un acknowledgement, un errore o una risposta con un corpo vuoto e un codice di stato HTTP 202.  
  
#### <a name="two-way-messages"></a>Messaggi bidirezionali  
 Per completare correttamente un protocollo di scambio di messaggi bidirezionale, l'iniziatore WCF trasmette un messaggio della sequenza di richiesta sulla richiesta HTTP e riceve un messaggio della sequenza di risposta sulla risposta HTTP. La risposta deve contenere un `SequenceAcknowledgement` che riconosce che il messaggio della sequenza di richiesta è stato trasmesso.  
  
 Il risponditore WCF può rispondere alla richiesta con una risposta dell'applicazione, un errore o una risposta con un corpo vuoto e un codice di stato HTTP 202.  
  
 A causa della presenza di messaggi unidirezionali e del tempo delle risposte dell'applicazione, il numero di sequenza del messaggio della sequenza di richiesta e il numero di sequenza del messaggio di risposta non hanno alcuna correlazione.  
  
#### <a name="retrying-replies"></a>Nuovi tentativi di risposte  
 WCF si basa sulla correlazione request/reply HTTP per la correlazione di protocollo di scambio di messaggi bidirezionale. Per questo motivo, l'iniziatore WCF smette di tentare un messaggio della sequenza di richiesta quando tale messaggio viene riconosciuto, ma piuttosto quando la risposta HTTP contiene un `SequenceAcknowledgement`, risposta dell'applicazione o un errore. Il risponditore WCF Ritenta le risposte sulla risposta HTTP della richiesta a cui è correlata la risposta.  
  
#### <a name="closesequence-exchange"></a>Scambio CloseSequence  
 Dopo la ricezione di tutti i messaggi di sequenza di risposta e gli acknowledgement per tutti i messaggi di sequenza di richiesta unidirezionali, l'iniziatore WCF trasmette un `CloseSequence` del messaggio per la sequenza di richiesta su una richiesta HTTP e non prevede il `CloseSequenceResponse` sulla risposta HTTP.  
  
 Se la sequenza di richiesta viene chiusa in modo implicito, viene chiusa anche la sequenza di risposta. Ciò significa che l'iniziatore WCF include finale della sequenza di risposta `SequenceAcknowledgement` nella `CloseSequence` messaggio e la sequenza di risposta non ha un `CloseSequence` exchange.  
  
 Il risponditore WCF assicura tutte le risposte vengano riconosciute e trasmette il `CloseSequenceResponse` messaggio sulla risposta HTTP.  
  
#### <a name="terminatesequence-exchange"></a>Scambio TerminateSequence  
 Dopo avere ricevuto il `CloseSequenceResponse` messaggio, l'iniziatore WCF trasmette un `TerminateSequence` messaggio per la sequenza di richiesta su una richiesta HTTP e non prevede il `TerminateSequenceResponse` sulla risposta HTTP.  
  
 Analogamente allo scambio `CloseSequence`, la terminazione della sequenza di richiesta in modo implicito termina la sequenza di risposta. Ciò significa che l'iniziatore WCF include finale della sequenza di risposta `SequenceAcknowledgement` nella `TerminateSequence` messaggio e la sequenza di risposta non ha un `TerminateSequence` exchange.  
  
 Il risponditore WCF trasmette il `TerminateSequenceResponse` messaggio sulla risposta HTTP.  
  
### <a name="requestreply-addressable-initiator"></a>Iniziatore request/reply, indirizzabile  
  
#### <a name="binding"></a>Binding  
 WCF fornisce un modello di scambio di messaggi request/reply usando due sequenze su uno in ingresso e un solo canale HTTP in uscita. Questo modello di scambio può essere combinato con il modello di scambio di messaggi dell'iniziatore `Duplex, Addressable` in modo limitato. WCF utilizza le richieste HTTP per trasmettere tutti i messaggi. Tutte le risposte HTTP hanno un corpo vuoto e un codice di stato HTTP 202.  
  
#### <a name="createsequence-exchange"></a>Scambio CreateSequence  
 L'iniziatore WCF trasmette un `CreateSequence` dei messaggi con un `Offer` elemento su una richiesta HTTP. Il risponditore WCF assicura che il `CreateSequence` ha un `Offer` elemento quindi crea una sequenza e trasmette il `CreateSequenceResponse` dei messaggi con un `Accept` elemento.  
  
#### <a name="requestreply-correlation"></a>Correlazione request/reply  
 Quanto riportato di seguito si applica a tutte le richieste e le risposte correlate:  
  
-   WCF garantisce tendente al tutti i messaggi di richiesta dell'applicazione un `ReplyTo` riferimento dell'endpoint e un `MessageId`.  
  
-   WCF si applica il riferimento dell'endpoint locale come ogni messaggio di richiesta dell'applicazione `ReplyTo`. Il riferimento dell'endpoint locale è `CreateSequence` del messaggio `ReplyTo` per l'iniziatore e `CreateSequence` del messaggio `To` per il risponditore.  
  
-   WCF garantisce i messaggi di tale richiesta in ingresso presentino un `MessageId` e un `ReplyTo`.  
  
-   WCF garantisce la `ReplyTo` URI dei riferimenti endpoint di tutti i messaggi di richiesta dell'applicazione corrisponde al riferimento dell'endpoint locale come definito in precedenza.  
  
-   WCF garantisce che tutte le risposte contengano `RelatesTo` e `To` le intestazioni `wsa` tipo le regole di correlazione request/reply.
