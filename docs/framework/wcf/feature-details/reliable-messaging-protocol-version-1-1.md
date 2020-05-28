---
title: Protocollo Reliable Messaging versione 1,1
ms.date: 03/30/2017
ms.assetid: 0da47b82-f8eb-42da-8bfe-e56ce7ba6f59
ms.openlocfilehash: ad0a77842c10965749eab4e76bb123938e07e9d5
ms.sourcegitcommit: ee5b798427f81237a3c23d1fd81fff7fdc21e8d3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/28/2020
ms.locfileid: "84144721"
---
# <a name="reliable-messaging-protocol-version-11"></a>Protocollo Reliable Messaging versione 1,1

In questo argomento vengono illustrati i dettagli di implementazione di Windows Communication Foundation (WCF) per il protocollo WS-ReliableMessaging febbraio 2007 (versione 1,1) necessario per l'interoperatività utilizzando il trasporto HTTP. WCF segue la specifica WS-ReliableMessaging con i vincoli e i chiarimenti illustrati in questo argomento. Si noti che il protocollo WS-ReliableMessaging versione 1,1 viene implementato a partire da .NET Framework 3,5.

Il protocollo WS-ReliableMessaging di febbraio 2007 viene implementato in WCF da <xref:System.ServiceModel.Channels.ReliableSessionBindingElement> .

Per comodità, nell'argomento vengono utilizzati i ruoli seguenti:

- Iniziatore: il client che inizia la creazione della sequenza di WS-Reliable Message.

- Risponditore: il servizio che riceve le richieste dell'iniziatore.

 In questo documento vengono utilizzati i prefissi e gli spazi dei nomi riportati nella tabella seguente.

|Prefisso|Spazio dei nomi|
|-|-|
|wsrm|`http://docs.oasis-open.org/ws-rx/wsrm/200702`|
|netrm|`http://schemas.microsoft.com/ws/2006/05/rm`|
|s|`http://www.w3.org/2003/05/soap-envelope`|
|wsa|`http://schemas.xmlsoap.org/ws/2005/08/addressing`|
|wsse|`http://docs.oasis-open.org/wss/2004/01/oasis-200401-wssecurity-secext-1.0.xsd`|
|wsrmp|`http://docs.oasis-open.org/ws-rx/wsrmp/200702`|
|netrmp|`http://schemas.microsoft.com/ws-rx/wsrmp/200702`|
|wsp|(WS-Policy 1.2 o WS-Policy 1.5)|

## <a name="messaging"></a>Messaggistica

### <a name="sequence-creation"></a>Creazione sequenza

WCF implementa `CreateSequence` `CreateSequenceResponse` i messaggi e per stabilire una sequenza di messaggistica affidabile. Si applicano i vincoli seguenti:

- B1101: l'iniziatore WCF usa lo stesso riferimento all'endpoint del `CreateSequence` messaggio `ReplyTo` , `AcksTo` e `Offer/Endpoint` .

- R1102: i riferimenti degli endpoint `AcksTo`, `ReplyTo` e `Offer/Endpoint` nel messaggio `CreateSequence` devono avere valori di indirizzo con rappresentazioni di stringa identiche in modo che corrispondano all'ottetto.

  - Il risponditore WCF verifica che la parte URI dei `AcksTo` `ReplyTo` `Endpoint` riferimenti endpoint e sia identica prima di creare una sequenza.

- R1103: i riferimenti degli endpoint `AcksTo`, `ReplyTo` e `Offer/Endpoint` nel messaggio `CreateSequence` devono avere lo stesso set di parametri per riferimento.

  - WCF non impone, ma presuppone che i parametri di riferimento di `AcksTo` `ReplyTo` e i `Offer/Endpoint` riferimenti all'endpoint `CreateSequence` siano identici e utilizzino parametri di riferimento dal `ReplyTo` riferimento all'endpoint per i messaggi di riconoscimento e di sequenza opposta.

- B1104: l'iniziatore WCF non genera l' `Expires` elemento facoltativo o `Offer/Expires` nel `CreateSequence` messaggio.

- B1105: quando si accede al `CreateSequence` messaggio, il risponditore WCF usa il `Expires` valore nell' `CreateSequence` elemento come `Expires` valore nell' `CreateSequenceResponse` elemento. In caso contrario, il risponditore WCF legge e ignora `Expires` i `Offer/Expires` valori e.

- B1106: quando si accede al `CreateSequenceResponse` messaggio, l'iniziatore WCF legge il `Expires` valore facoltativo ma non lo usa.

- B1107: l'iniziatore WCF e il risponditore generano sempre l' `IncompleteSequenceBehavior` elemento facoltativo negli `CreateSequence/Offer` `CreateSequenceResponse` elementi e.

- B1108: WCF usa solo i `DiscardFollowingFirstGap` `NoDiscard` valori e nell' `IncompleteSequenceBehavior` elemento.

  - WS-ReliableMessaging utilizza il meccanismo `Offer` per stabilire le due sequenze correlate opposte che formano una sessione.

- B1109: se `CreateSequence` contiene un `Offer` elemento, il RISPONDItore WCF a unidirezionale respinge la sequenza offerta rispondendo a `CreateSequenceResponse` senza un `Accept` elemento.

- B1110: se un risponditore Reliable Messaging rifiuta la sequenza offerta, l'iniziatore WCF genera errori nella sequenza appena stabilita.

- B1111: se `CreateSequence` non contiene un `Offer` elemento, il RISPONDItore WCF bidirezionale respinge la sequenza offerta rispondendo con un `CreateSequenceRefused` errore.

- R1112: quando vengono stabilite due sequenze opposte utilizzando il meccanismo `Offer`, la proprietà `[address]` del riferimento dell'endpoint `CreateSequenceResponse/Accept/AcksTo` deve corrispondere all'URI di destinazione del messaggio `CreateSequence`, byte per byte.

- R1113: quando vengono stabilite due sequenze opposte utilizzando il meccanismo `Offer`, tutti i messaggi su entrambe le sequenze dall'iniziatore al risponditore devono essere inviati allo stesso riferimento dell'endpoint.

WCF utilizza WS-ReliableMessaging per stabilire sessioni affidabili tra l'iniziatore e il risponditore. L'implementazione WCF WS-ReliableMessaging fornisce una sessione affidabile per modelli di messaggistica unidirezionali, Request/Reply e full duplex. Il meccanismo `Offer` di WS-Reliable Messaging in `CreateSequence` e `CreateSequenceResponse` consente di stabilire due sequenze opposte correlate e fornisce un protocollo della sessione idoneo per tutti gli endpoint del messaggio. Poiché WCF fornisce una garanzia di sicurezza per tale sessione, inclusa la protezione end-to-end per l'integrità della sessione, è consigliabile assicurarsi che i messaggi destinati alla stessa parte arrivino alla stessa destinazione. Ciò consente anche il "piggy-backing" degli acknowledgement della sequenza sui messaggi dell'applicazione. Pertanto, i vincoli R1102, R1112 e R1113 si applicano a WCF.

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

WCF utilizza i `CloseSequence` `CloseSequenceResponse` messaggi e per l'arresto di un'origine di messaggistica affidabile avviata. La destinazione di messaggistica affidabile WCF non avvia l'arresto e l'origine della messaggistica affidabile WCF non supporta l'arresto avviato da una destinazione di messaggistica affidabile. Si applicano i vincoli seguenti:

- B1201: l'origine della messaggistica affidabile WCF invia sempre un `CloseSequence` messaggio per arrestare la sequenza.

- B1202: l'origine di Reliable Messaging attende l'acknowledgment dell'intera serie di messaggi della sequenza prima di inviare il messaggio `CloseSequence`.

- B1203: l'origine di Reliable Messaging include sempre l'elemento facoltativo `LastMsgNumber`. Non lo include se la sequenza non contiene messaggi.

- R1204: la destinazione di Reliable Messaging non deve iniziare l'arresto inviando un messaggio `CloseSequence`.

- B1205: dopo la ricezione di un `CloseSequence` messaggio, l'origine della messaggistica affidabile WCF considera la sequenza incompleta e invia un errore.

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
```

Messaggio di esempio `CloseSequenceResponse` :

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

### <a name="sequence-termination"></a>Terminazione della sequenza

WCF utilizza principalmente l' `TerminateSequence/TerminateSequenceResponse` handshake dopo il completamento dell' `CloseSequence/CloseSequenceResponse` handshake. La destinazione di messaggistica affidabile WCF non avvia la terminazione e l'origine di Reliable Messaging non supporta la terminazione avviata da una destinazione di messaggistica affidabile. Si applicano i vincoli seguenti:

- B1301: l'iniziatore WCF invia il `TerminateSequence` messaggio solo dopo il completamento dell' `CloseSequence/CloseSequenceResponse` handshake.

- R1302: WCF verifica che l' `LastMsgNumber` elemento sia coerente in tutti `CloseSequence` `TerminateSequence` i messaggi e per una determinata sequenza. Ciò significa che `LastMsgNumber` o non è presente in tutti i messaggi `CloseSequence` e `TerminateSequence`, o è presente e identico in tutti i messaggi `CloseSequence` e `TerminateSequence`.

- B1303: al ricevimento di un messaggio `TerminateSequence` dopo l'handshake `CloseSequence/CloseSequenceResponse`, la destinazione di Reliable Messaging risponde con un messaggio `TerminateSequenceResponse`. Poiché l'origine di Reliable Messaging dispone dell'acknowledgement finale prima dell'invio del messaggio `TerminateSequence`, la destinazione di Reliable Messaging è a conoscenza della fine della sequenza e richiede immediatamente le risorse.

- B1304: quando si riceve un `TerminateSequence` messaggio prima dell' `CloseSequence/CloseSequenceResponse` handshake, la destinazione di messaggistica affidabile WCF risponde con un `TerminateSequenceResponse` messaggio. Se la destinazione di Reliable Messaging stabilisce che non vi sono incoerenze nella sequenza, attende per il periodo di tempo specificato dalla destinazione dell'applicazione prima di richiedere le risorse, per offrire al client la possibilità di ricevere l'acknowledgement finale. In caso contrario, la destinazione di Reliable Messaging richiede immediatamente le risorse e indica alla destinazione dell'applicazione che la sequenza termina in modo dubbio generando l'evento `Faulted`.

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
```

Messaggio di esempio `TerminateSequenceResponse` :

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

### <a name="sequences"></a>Sequenze

Di seguito è riportato un elenco di vincoli che si applicano alle sequenze:

- B1401: WCF genera e accede ai numeri di sequenza non più elevati del `xs:long` valore inclusivo massimo, 9223372036854775807.

Esempio di intestazione `Sequence`.

```xml
<wsrm:Sequence s:mustUnderstand="1">
  <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>
  <wsrm:MessageNumber>1</wsrm:MessageNumber>
</wsrm:Sequence>
```

### <a name="request-acknowledgement"></a>Acknowledgement della richiesta

WCF utilizza l' `AckRequested` intestazione come meccanismo Keep-Alive.

Esempio di intestazione `AckRequested`.

```xml
<wsrm:AckRequested>
  <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>
</wsrm:AckRequested>
```

### <a name="sequenceacknowledgement"></a>SequenceAcknowledgement

WCF utilizza un meccanismo "Piggy-Back" per i riconoscimenti di sequenza forniti in WS-Reliable Messaging. Si applicano i vincoli seguenti:

- R1601: quando vengono stabilite due sequenze opposte utilizzando il `Offer` meccanismo, l' `SequenceAcknowledgement` intestazione può essere inclusa in qualsiasi messaggio dell'applicazione trasmesso al destinatario previsto. L'endpoint remoto deve essere in grado di accedere a un'intestazione `SequenceAcknowledgement` sottoposta a piggyback.

- B1602: WCF non genera `SequenceAcknowledgement` intestazioni che contengono `Nack` elementi. WCF verifica che ogni `Nack` elemento contenga un numero di sequenza, ma altrimenti ignora l' `Nack` elemento e il valore.

 Esempio di intestazione `SequenceAcknowledgement`.

```xml
<wsrm:SequenceAcknowledgement>
  <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>
  <wsrm:AcknowledgementRange Lower="1" Upper="1"></wsrm:AcknowledgementRange>
</wsrm:SequenceAcknowledgement>
```

### <a name="ws-reliablemessaging-faults"></a>Errori WS-ReliableMessaging

Di seguito è riportato un elenco di vincoli che si applicano all'implementazione WCF degli errori di WS-ReliableMessaging. Si applicano i vincoli seguenti:

- B1701: WCF non genera `MessageNumberRollover` errori.

- B1702: tramite SOAP 1,2, quando l'endpoint del servizio raggiunge il limite di connessione e non è in grado di elaborare nuove connessioni, WCF genera un `CreateSequenceRefused` codice sottocodice di errore annidato, `netrm:ConnectionLimitReached` , come illustrato nell'esempio seguente.

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

Poiché WS-ReliableMessaging utilizza WS-Addressing, l'implementazione di WCF WS-ReliableMessaging può generare e trasmettere errori di WS-Addressing. In questa sezione vengono illustrati gli errori WS-Addressing che WCF genera e trasmette in modo esplicito a livello di WS-ReliableMessaging:

- B1801: WCF genera e trasmette l' `Message Addressing Header Required` errore quando si verifica una delle condizioni seguenti:

  - In un messaggio `CreateSequence`, `CloseSequence` o `TerminateSequence` manca un'intestazione `MessageId`.

  - In un messaggio `CreateSequence`, `CloseSequence` o `TerminateSequence` manca un'intestazione `ReplyTo`.

  - In un messaggio `CreateSequenceResponse`, `CloseSequenceResponse` o `TerminateSequenceResponse` manca un'intestazione `RelatesTo`.

- B1802: WCF genera e trasmette l' `Endpoint Unavailable` errore per indicare che non è presente alcun endpoint in ascolto in grado di elaborare la sequenza in base all'esame delle intestazioni di indirizzamento nel `CreateSequence` messaggio.

## <a name="protocol-composition"></a>Composizione del protocollo

### <a name="composition-with-ws-addressing"></a>Composizione con WS-Addressing

WCF supporta due versioni di WS-Addressing: WS-Addressing 2004/08 [WS-ADDR] e W3C WS-Addressing 1,0 raccomandazioni [WS-ADDR-CORE] e [WS-ADDR-SOAP].

Anche se la specifica WS-ReliableMessaging menziona solo WS-Addressing 2004/08, non limita la versione WS-Addressing da utilizzare. Di seguito è riportato un elenco di vincoli che si applicano a WCF:

- R2101: sia WS-Addressing 2004/08 che WS-Addressing 1.0 possono essere utilizzati con WS-Reliable Messaging.

- R2102: è necessario utilizzare una sola versione di WS-Addressing in una data sequenza di WS-Reliable Messaging o in una coppia di sequenze opposte correlate tramite il meccanismo `Offer`.

### <a name="composition-with-soap"></a>Composizione con SOAP

WCF supporta l'utilizzo di SOAP 1,1 e SOAP 1,2 con WS-Reliable Messaging.

### <a name="composition-with-ws-security-and-ws-secureconversation"></a>Composizione con WS-Security e WS-SecureConversation

WCF fornisce la protezione per le sequenze WS-ReliableMessaging tramite trasporto protetto (HTTPS), composizione con WS-Security e composizione con WS-Secure Conversation. Il protocollo WS-Reliable Messaging 1.1, WS-Security 1.1 e il protocollo WS-SecureConversation 1.3 devono essere utilizzati insieme. Di seguito è riportato un elenco di vincoli che si applicano a WCF:

- R2301: per proteggere l'integrità di una sequenza di WS-ReliableMessaging oltre all'integrità e alla riservatezza dei singoli messaggi, WCF richiede l'utilizzo di WS-Secure Conversation.

- R2302: prima di stabilire la(e) sequenza(e) di WS-Reliable Messaging, è necessario stabilire una sessione WS-SecureConversation.

- R2303: se la durata della sequenza di WS-Reliable Messaging supera la durata della sessione WS-SecureConversation, è necessario rinnovare il `SecurityContextToken` stabilito tramite WS-SecureConversation utilizzando l'associazione WS-Secure Conversation Renewal corrispondente.

- B2304: la sequenza WS-ReliableMessaging o una coppia di sequenze opposte sono sempre associate a una singola sessione WS-SecureConversation.

- R2305: se composto con WS-Secure Conversation, il risponditore WCF richiede che il `CreateSequence` messaggio contenga l' `wsse:SecurityTokenReference` elemento e l' `wsrm:UsesSequenceSTR` intestazione.

 Esempio di intestazione `UsesSequenceSTR`.

```xml
<wsrm:UsesSequenceSTR></wsrm:UsesSequenceSTR>
```

### <a name="composition-with-ssltls-sessions"></a>Composizione con sessioni SSL/TLS

WCF non supporta la composizione con sessioni SSL/TLS:

- B2401: WCF non genera l' `wsrm:UsesSequenceSSL` intestazione.

- R2402: un iniziatore di messaggistica affidabile non deve inviare un `CreateSequence` messaggio con un' `wsrm:UsesSequenceSSL` intestazione a un risponditore WCF.

### <a name="composition-with-ws-policy"></a>Composizione con WS-Policy

WCF supporta due versioni di WS-Policy: WS-Policy 1,2 e WS-Policy 1,5.

## <a name="ws-reliablemessaging-ws-policy-assertion"></a>Asserzione di WS-Policy relativa a WS-ReliableMessaging

WCF usa l'asserzione WS-Policy di WS-ReliableMessaging `wsrm:RMAssertion` per descrivere le funzionalità degli endpoint. Di seguito è riportato un elenco di vincoli che si applicano a WCF:

- B3001: WCF connette l' `wsrmn:RMAssertion` asserzione WS-Policy agli `wsdl:binding` elementi. WCF supporta entrambi gli allegati `wsdl:binding` agli `wsdl:port` elementi e.

- B3002: WCF non genera mai il `wsp:Optional` tag.

- B3003: quando si accede all' `wsrmp:RMAssertion` asserzione WS-Policy, WCF ignora il `wsp:Optional` tag e considera i criteri WS-RM come obbligatori.

- R3004: poiché WCF non compone con sessioni SSL/TLS, WCF non accetta criteri che specificano `wsrmp:SequenceTransportSecurity` .

- B3005: WCF genera sempre l' `wsrmp:DeliveryAssurance` elemento.

- B3006: WCF specifica sempre la `wsrmp:ExactlyOnce` garanzia di recapito.

- B3007: WCF genera e legge le seguenti proprietà dell'asserzione WS-ReliableMessaging e ne fornisce il controllo su WCF `ReliableSessionBindingElement` :

  - `netrmp:InactivityTimeout`

  - `netrmp:AcknowledgementInterval`

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

WCF utilizza l'estendibilità di WS-ReliableMessaging per fornire un controllo facoltativo aggiuntivo più rigido sul flusso di messaggi della sequenza.

Il controllo di flusso viene abilitato impostando la <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.FlowControlEnabled?displayProperty=nameWithType> proprietà su `true` . Di seguito è riportato un elenco di vincoli che si applicano a WCF:

- B4001: quando è abilitato il controllo di flusso di Reliable Messaging, WCF genera un `netrm:BufferRemaining` elemento nell'estendibilità dell'elemento dell' `SequenceAcknowledgement` intestazione, come illustrato nell'esempio seguente.

  ```xml
  <wsrm:SequenceAcknowledgement>
    <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>
    <wsrm:AcknowledgementRange Upper="1" Lower="1"/>
    <netrm:BufferRemaining>8</netrm:BufferRemaining>
  </wsrm:SequenceAcknowledgement>
  ```

- B4002: anche quando è abilitato il controllo del flusso di messaggistica affidabile, WCF non richiede un `netrm:BufferRemaining` elemento nell' `SequenceAcknowledgement` intestazione.

- B4003: la destinazione di messaggistica affidabile WCF USA `netrm:BufferRemaining` per indicare il numero di nuovi messaggi che possono essere memorizzati nel buffer.

- B4004: quando è abilitato il controllo di flusso di Reliable Messaging, l'origine della messaggistica affidabile WCF usa il valore di `netrm:BufferRemaining` per limitare la trasmissione dei messaggi.

- B4005: WCF genera `netrm:BufferRemaining` valori integer compresi tra 0 e 4096 inclusivi e legge i valori integer compresi tra 0 e `xs:int` il `maxInclusive` valore 214748364 inclusi.

## <a name="message-exchange-patterns"></a>Modelli di scambio dei messaggi

In questa sezione viene descritto il comportamento di WCF quando WS-ReliableMessaging viene utilizzato per modelli di scambio di messaggi diversi. Per ogni modello di scambio di messaggi, vengono presi in considerazione i due scenari di distribuzione seguenti:

- Iniziatore non indirizzabile: l'iniziatore si trova dietro a un firewall; il risponditore può recapitare messaggi all'iniziatore solo su risposte HTTP.

- Iniziatore indirizzabile: le richieste HTTP possono essere inviate sia all'iniziatore che al risponditore. In altre parole, è possibile stabilire due connessioni HTTP opposte.

### <a name="one-way-non-addressable-initiator"></a>Iniziatore unidirezionale, non indirizzabile

#### <a name="binding"></a>Associazione

WCF fornisce un modello di scambio di messaggi unidirezionale utilizzando una sequenza su un canale HTTP. WCF utilizza le richieste HTTP per trasmettere tutti i messaggi dall'iniziatore alle risposte del risponditore e HTTP per trasmettere tutti i messaggi dal risponditore all'iniziatore.

#### <a name="createsequence-exchange"></a>Scambio CreateSequence

L'iniziatore WCF trasmette un `CreateSequence` messaggio senza alcun `Offer` elemento su una richiesta HTTP e attende il `CreateSequenceResponse` messaggio sulla risposta http. Il risponditore WCF crea una sequenza e trasmette il `CreateSequenceResponse` messaggio senza alcun `Accept` elemento sulla risposta http.

#### <a name="sequenceacknowledgement"></a>SequenceAcknowledgement

L'iniziatore WCF elabora i riconoscimenti della risposta di tutti i messaggi ad eccezione dei `CreateSequence` messaggi di errore e di messaggio. Il risponditore WCF trasmette sempre un riconoscimento autonomo sulla risposta HTTP a tutti i messaggi e alla sequenza `AckRequested` .

#### <a name="closesequence-exchange"></a>Scambio CloseSequence

L'iniziatore WCF trasmette un `CloseSequence` messaggio su una richiesta HTTP e attende il `CreateSequenceResponse` messaggio sulla risposta http. Il risponditore WCF trasmette il `CloseSequenceResponse` messaggio sulla risposta http.

#### <a name="terminatesequence-exchange"></a>Scambio TerminateSequence

L'iniziatore WCF trasmette un `TerminateSequence` messaggio su una richiesta HTTP e attende il `TerminateSequenceResponse` messaggio sulla risposta http. Il risponditore WCF trasmette il `TerminateSequenceResponse` messaggio sulla risposta http.

### <a name="one-way-addressable-initiator"></a>Iniziatore unidirezionale, indirizzabile

#### <a name="binding"></a>Associazione

WCF fornisce un modello di scambio di messaggi unidirezionale utilizzando una sequenza su un canale HTTP in ingresso e uno in uscita. WCF utilizza le richieste HTTP per trasmettere tutti i messaggi. Tutte le risposte HTTP hanno un corpo vuoto e un codice di stato HTTP 202.

#### <a name="createsequence-exchange"></a>Scambio CreateSequence

L'iniziatore WCF trasmette un `CreateSequence` messaggio senza alcun `Offer` elemento su una richiesta HTTP. Il risponditore WCF crea una sequenza e trasmette il `CreateSequenceResponse` messaggio senza alcun `Accept` elemento su una richiesta HTTP.

### <a name="duplex-addressable-initiator"></a>Iniziatore duplex, indirizzabile

#### <a name="binding"></a>Associazione

WCF fornisce un modello di scambio di messaggi bidirezionale completamente asincrono utilizzando due sequenze su un canale HTTP in ingresso e uno in uscita. Questo modello di scambio può essere combinato con il modello di scambio di messaggi dell'iniziatore `Request/Reply`, `Addressable` in modo limitato. WCF utilizza le richieste HTTP per trasmettere tutti i messaggi. Tutte le risposte HTTP hanno un corpo vuoto e un codice di stato HTTP 202.

#### <a name="createsequence-exchange"></a>Scambio CreateSequence

L'iniziatore WCF trasmette un `CreateSequence` messaggio con un `Offer` elemento su una richiesta HTTP. Il risponditore WCF garantisce che `CreateSequence` disponga di un `Offer` elemento, quindi crea una sequenza e trasmette il `CreateSequenceResponse` messaggio con un `Accept` elemento.

#### <a name="sequence-lifetime"></a>Durata della sequenza

WCF tratta le due sequenze come una sessione completamente duplex.

Quando si genera un errore che genera errori in una sequenza, WCF prevede che l'endpoint remoto errori entrambe le sequenze. Durante la lettura di un errore che genera errori in una sequenza, WCF genera errori in entrambe le sequenze.

WCF può chiudere la sequenza in uscita e continuare a elaborare i messaggi sulla relativa sequenza in ingresso. Viceversa, WCF può elaborare la chiusura della sequenza in ingresso e continuare a inviare messaggi sulla relativa sequenza in uscita.

### <a name="request-reply-and-one-way-non-addressable-initiator"></a>Iniziatore request/reply e unidirezionale, non indirizzabile

#### <a name="binding"></a>Associazione

WCF fornisce un modello di scambio di messaggi unidirezionale e Request/Reply utilizzando due sequenze su un canale HTTP. WCF utilizza le richieste HTTP per trasmettere tutti i messaggi dall'iniziatore alle risposte del risponditore e HTTP per trasmettere tutti i messaggi dal risponditore all'iniziatore.

#### <a name="createsequence-exchange"></a>Scambio CreateSequence

L'iniziatore WCF trasmette un `CreateSequence` messaggio con un `Offer` elemento su una richiesta HTTP e attende il `CreateSequenceResponse` messaggio sulla risposta http. Il risponditore WCF crea una sequenza e trasmette il `CreateSequenceResponse` messaggio con un `Accept` elemento sulla risposta http.

#### <a name="one-way-message"></a>Messaggio unidirezionale

Per completare correttamente uno scambio di messaggi unidirezionale, l'iniziatore WCF trasmette un messaggio della sequenza di richiesta sulla richiesta HTTP e riceve un `SequenceAcknowledgement` messaggio autonomo sulla risposta http. `SequenceAcknowledgement` deve riconoscere il messaggio trasmesso.

Il risponditore WCF può rispondere alla richiesta con un riconoscimento, un errore o una risposta con un corpo vuoto e un codice di stato HTTP 202.

#### <a name="two-way-messages"></a>Messaggi bidirezionali

Per completare correttamente un protocollo di scambio di messaggi bidirezionale, l'iniziatore WCF trasmette un messaggio della sequenza di richiesta sulla richiesta HTTP e riceve un messaggio della sequenza di risposta nella risposta HTTP. La risposta deve contenere un `SequenceAcknowledgement` che riconosce che il messaggio della sequenza di richiesta è stato trasmesso.

Il risponditore WCF può rispondere alla richiesta con una risposta dell'applicazione, un errore o una risposta con un corpo vuoto e un codice di stato HTTP 202.

A causa della presenza di messaggi unidirezionali e del tempo delle risposte dell'applicazione, il numero di sequenza del messaggio della sequenza di richiesta e il numero di sequenza del messaggio di risposta non hanno alcuna correlazione.

#### <a name="retrying-replies"></a>Nuovi tentativi di risposte

WCF si basa sulla correlazione request/reply HTTP per la correlazione tra protocolli di scambio di messaggi bidirezionali. Per questo motivo, l'iniziatore WCF non interrompe il nuovo tentativo di un messaggio della sequenza di richiesta quando il messaggio della sequenza di richiesta viene riconosciuto, ma piuttosto quando la risposta HTTP contiene un `SequenceAcknowledgement` , una risposta dell'applicazione o un errore. Il risponditore WCF ritenta le risposte sulla risposta HTTP della richiesta a cui è correlata la risposta.

#### <a name="closesequence-exchange"></a>Scambio CloseSequence

Dopo aver ricevuto tutti i messaggi della sequenza di risposta e i riconoscimenti per tutti i messaggi della sequenza di richiesta unidirezionale, l'iniziatore WCF trasmette un `CloseSequence` messaggio per la sequenza di richiesta su una richiesta HTTP e attende la `CloseSequenceResponse` sulla risposta http.

Se la sequenza di richiesta viene chiusa in modo implicito, viene chiusa anche la sequenza di risposta. Ciò significa che l'iniziatore WCF include il finale della sequenza di risposta `SequenceAcknowledgement` sul `CloseSequence` messaggio e che la sequenza di risposta non ha uno `CloseSequence` scambio.

Il risponditore WCF garantisce che tutte le risposte siano riconosciute e trasmette il `CloseSequenceResponse` messaggio sulla risposta http.

#### <a name="terminatesequence-exchange"></a>Scambio TerminateSequence

Dopo la ricezione del `CloseSequenceResponse` messaggio, l'iniziatore WCF trasmette un `TerminateSequence` messaggio per la sequenza di richiesta su una richiesta HTTP e attende la `TerminateSequenceResponse` sulla risposta http.

Analogamente allo scambio `CloseSequence`, la terminazione della sequenza di richiesta in modo implicito termina la sequenza di risposta. Ciò significa che l'iniziatore WCF include il finale della sequenza di risposta `SequenceAcknowledgement` sul `TerminateSequence` messaggio e che la sequenza di risposta non ha uno `TerminateSequence` scambio.

Il risponditore WCF trasmette il `TerminateSequenceResponse` messaggio sulla risposta http.

### <a name="requestreply-addressable-initiator"></a>Iniziatore request/reply, indirizzabile

#### <a name="binding"></a>Associazione

WCF fornisce un modello di scambio di messaggi request/reply utilizzando due sequenze su un canale HTTP in ingresso e su uno in uscita. Questo modello di scambio può essere combinato con il modello di scambio di messaggi dell'iniziatore `Duplex, Addressable` in modo limitato. WCF utilizza le richieste HTTP per trasmettere tutti i messaggi. Tutte le risposte HTTP hanno un corpo vuoto e un codice di stato HTTP 202.

#### <a name="createsequence-exchange"></a>Scambio CreateSequence

L'iniziatore WCF trasmette un `CreateSequence` messaggio con un `Offer` elemento su una richiesta HTTP. Il risponditore WCF garantisce che `CreateSequence` abbia un `Offer` elemento, quindi crea una sequenza e trasmette il `CreateSequenceResponse` messaggio con un `Accept` elemento.

#### <a name="requestreply-correlation"></a>Correlazione request/reply

Quanto riportato di seguito si applica a tutte le richieste e le risposte correlate:

- WCF garantisce che tutti i messaggi di richiesta dell'applicazione contengano un `ReplyTo` riferimento all'endpoint e un `MessageId` .

- WCF applica il riferimento all'endpoint locale come ogni messaggio di richiesta dell'applicazione `ReplyTo` . Il riferimento dell'endpoint locale è `CreateSequence` del messaggio `ReplyTo` per l'iniziatore e `CreateSequence` del messaggio `To` per il risponditore.

- WCF garantisce che i messaggi di richiesta in ingresso contengano `MessageId` e `ReplyTo` .

- WCF garantisce `ReplyTo` che l'URI del riferimento dell'endpoint di tutti i messaggi di richiesta dell'applicazione corrisponda al riferimento all'endpoint locale definito in precedenza.

- WCF garantisce che tutte le risposte contengano le `RelatesTo` intestazioni e corrette che `To` seguono le regole di `wsa` correlazione request/reply.
