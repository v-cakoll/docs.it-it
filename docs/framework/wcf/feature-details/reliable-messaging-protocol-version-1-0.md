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
# <a name="reliable-messaging-protocol-version-10"></a>Protocollo Reliable Messaging versione 1.0

In questo argomento vengono illustrati i dettagli di implementazione di Windows Communication Foundation (WCF) per il protocollo WS-Reliable Messaging February 2005 (versione 1,0) necessario per l'interoperabilità tramite il trasporto HTTP. WCF segue la specifica WS-Reliable Messaging con i vincoli e i chiarimenti illustrati in questo argomento. Si noti che il protocollo WS-ReliableMessaging versione 1,0 viene implementato a partire da WinFX.

Il protocollo WS-Reliable Messaging 2005 viene implementato in WCF da <xref:System.ServiceModel.Channels.ReliableSessionBindingElement> .

Per comodità, nell'argomento vengono utilizzati i ruoli seguenti:

- Iniziatore: il client che avvia la creazione della sequenza di WS-Reliable Message.

- Risponditore: il servizio che riceve le richieste dell'iniziatore.

In questo documento vengono utilizzati i prefissi e gli spazi dei nomi riportati nella tabella seguente.

|Prefisso|Spazio dei nomi|
|------------|---------------|
|wsrm|`http://schemas.xmlsoap.org/ws/2005/02/rm`|
|netrm|`http://schemas.microsoft.com/ws/2006/05/rm`|
|s|`http://www.w3.org/2003/05/soap-envelope`|
|wsa|`http://schemas.xmlsoap.org/ws/2005/08/addressing|
|wsse|`http://docs.oasis-open.org/wss/2004/01/oasis-200401-wssecurity-secext-1.0.xsd`|

## <a name="messaging"></a>Messaggistica

### <a name="sequence-establishment-messages"></a>Messaggi di definizione sequenza

WCF implementa `CreateSequence` `CreateSequenceResponse` i messaggi e per stabilire una sequenza di messaggi affidabile. Si applicano i vincoli seguenti:

- B1101: l'iniziatore WCF non genera l'elemento Expires facoltativo nel `CreateSequence` messaggio o, nei casi in cui il `CreateSequence` messaggio contiene un `Offer` elemento, l'elemento facoltativo `Expires` nell' `Offer` elemento.

- B1102: quando si accede al `CreateSequence` messaggio, WCF `Responder` Invia e riceve entrambi `Expires` gli elementi, se esistenti, ma non ne utilizza i valori.

Con il protocollo WS-ReliableMessaging viene introdotto il meccanismo `Offer` che consente di stabilire le due sequenze correlate opposte che formano una sessione.

- R1103: se `CreateSequence` contiene un elemento `Offer`, il risponditore Reliable Messaging deve accettare la sequenza e rispondere con `CreateSequenceResponse` contenente un elemento `wsrm:Accept`, formando due sequenze correlate opposte, oppure rifiutare la richiesta `CreateSequence`.

- R1104: i messaggi `SequenceAcknowledgement` e dell'applicazione in transito sulla sequenza opposta devono essere inviati al riferimento endpoint `ReplyTo` di `CreateSequence`.

- R1105: i riferimenti endpoint `AcksTo` e `ReplyTo` in `CreateSequence` devono presentare valori indirizzo che corrispondano all'ottetto.

  Il risponditore WCF verifica che la parte URI di `AcksTo` e `ReplyTo` EPRs sia identica prima di creare una sequenza.

- R1106: i riferimenti endpoint `AcksTo`e `ReplyTo` in `CreateSequence` devono avere lo stesso set di parametri per riferimento.

  WCF non impone, ma presuppone che i [parametri di riferimento] di `AcksTo` e `ReplyTo` on `CreateSequence` siano identici e utilizzino [parametri di riferimento] dal `ReplyTo` riferimento all'endpoint per i messaggi di riconoscimento e di sequenza opposta.

- R1107: quando vengono stabilite due sequenze opposte tramite il meccanismo `Offer`, i messaggi dell'applicazione e `SequenceAcknowledgement` in transito sulle sequenze opposte devono essere inviati al riferimento all'endpoint `ReplyTo` di `CreateSequence`.

- R1108: quando vengono stabilite due sequenze opposte mediante il meccanismo Offer, la proprietà `[address]` dell'elemento figlio del riferimento endpoint `wsrm:AcksTo` dell'elemento `wsrm:Accept` di `CreateSequenceResponse` deve corrispondere per numero di byte all'URI di destinazione di `CreateSequence`.

- R1109: quando vengono stabilite due sequenze opposte tramite il meccanismo `Offer`, i messaggi inviati dall'iniziatore e gli acknowledgement a tali messaggi da parte del risponditore devono essere inviati allo stesso riferimento all'endpoint.

  WCF utilizza WS-Reliable Messaging per stabilire sessioni affidabili tra l'iniziatore e il risponditore. L'implementazione WS-Reliable Messaging di WCF fornisce una sessione affidabile per modelli di messaggistica unidirezionali, Request/Reply e full duplex. Il meccanismo WS-Reliable Messaging `Offer` in `CreateSequence` / `CreateSequenceResponse` consente di stabilire due sequenze opposte correlate e fornisce un protocollo di sessione adatto a tutti gli endpoint del messaggio. Poiché WCF fornisce una garanzia di sicurezza per tale sessione, inclusa la protezione end-to-end per l'integrità della sessione, è consigliabile assicurarsi che i messaggi destinati alla stessa parte arrivino alla stessa destinazione. Ciò consente anche il "piggy-backing" degli acknowledgement della sequenza sui messaggi dell'applicazione. Pertanto, i vincoli R1104, R1105 e R1108 si applicano a WCF.

Esempio di un messaggio `CreateSequence`.

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

 Esempio di un messaggio `CreateSequenceResponse`.

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

### <a name="sequence"></a>Sequenza

Di seguito è riportato un elenco di vincoli che si applicano alle sequenze:

- B1201: WCF genera e accede ai numeri di sequenza non più elevati del `xs:long` valore inclusivo massimo, 9223372036854775807.

- B1202: WCF genera sempre un ultimo messaggio con corpo vuoto con l'URI dell'azione `http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage` .

- B1203: WCF riceve e recapita un messaggio con un'intestazione di sequenza che contiene un `LastMessage` elemento purché l'URI dell'azione non sia `http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage` .

Esempio di intestazione di sequenza.

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

### <a name="ackrequested-header"></a>Intestazione AckRequested

WCF utilizza `AckRequested` l'intestazione come meccanismo Keep-Alive. WCF non genera l'elemento facoltativo `MessageNumber` . Quando riceve un messaggio con un' `AckRequested` intestazione che contiene l' `MessageNumber` elemento, WCF ignora il `MessageNumber` valore dell'elemento, come illustrato nell'esempio seguente.

```xml
<wsrm:AckRequested>
  <wsrm:Identifier>
    urn:uuid:addabbbf-60cb-44d3-8c5b-9e0841629a36
  </wsrm:Identifier>
</wsrm:AckRequested>
```

### <a name="sequenceacknowledgement-header"></a>Intestazione SequenceAcknowledgement

WCF utilizza un meccanismo di Piggy-Back per i riconoscimenti di sequenza forniti in WS-Reliable Messaging.

- R1401: quando vengono stabilite due sequenze opposte utilizzando il meccanismo `Offer`, l'intestazione `SequenceAcknowledgement` può essere inclusa in qualsiasi messaggio dell'applicazione trasmesso al destinatario desiderato.

- B1402: quando WCF deve generare un riconoscimento prima di ricevere messaggi di sequenza, ad esempio per soddisfare un `AckRequested` messaggio, WCF genera un' `SequenceAcknowledgement` intestazione che contiene l'intervallo 0-0, come illustrato nell'esempio seguente.

  ```xml
  <wsrm:SequenceAcknowledgement>
    <wsrm:Identifier>
      urn:uuid:addabbbf-60cb-44d3-8c5b-9e0841629a36
    </wsrm:Identifier>
    <wsrm:AcknowledgementRange Upper="0" Lower="0"/>
  </wsrm:SequenceAcknowledgement>
  ```

- B1403: WCF non genera `SequenceAcknowledgement` intestazioni contenenti un `Nack` elemento ma supporta `Nack` gli elementi.

### <a name="ws-reliablemessaging-faults"></a>Errori WS-ReliableMessaging

Di seguito è riportato un elenco di vincoli che si applicano all'implementazione WCF degli errori WS-Reliable Messaging:

- B1501: WCF non genera `MessageNumberRollover` errori.

- B1502: l'endpoint WCF può generare `CreateSequenceRefused` errori come descritto nella specifica.

- B1503: quando l'endpoint del servizio raggiunge il limite di connessione e non è in grado di elaborare nuove connessioni, WCF genera un `CreateSequenceRefused` codice di errore aggiuntivo, `netrm:ConnectionLimitReached` , come illustrato nell'esempio seguente.

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

### <a name="ws-addressing-faults"></a>Errori WS-Addressing

Poiché WS-Reliable Messaging utilizza WS-Addressing, l'implementazione di WCF WS-Reliable Messaging può generare errori di WS-Addressing. In questa sezione vengono illustrati gli errori WS-Addressing generati in modo esplicito da WCF al livello WS-Reliable Messaging:

- B1601: WCF genera l'intestazione di indirizzamento dei messaggi di errore necessaria quando si verifica una delle condizioni seguenti:

  - In un messaggio mancano un'intestazione `Sequence` e un'intestazione `Action`.

  - In un messaggio `CreateSequence` manca un'intestazione `MessageId`.

  - In un messaggio `CreateSequence` manca un'intestazione `ReplyTo`.

- B1602: WCF genera l'azione di errore non supportata in risposta a un messaggio in cui manca un' `Sequence` intestazione e ha un' `Action` intestazione non riconosciuta nella specifica WS-Reliable Messaging.

- B1603: WCF genera l'endpoint di errore non disponibile per indicare che l'endpoint non elabora la sequenza in base all'esame delle `CreateSequence` intestazioni di indirizzamento del messaggio.

## <a name="protocol-composition"></a>Composizione del protocollo

### <a name="composition-with-ws-addressing"></a>Composizione con WS-Addressing

WCF supporta due versioni di WS-Addressing: WS-Addressing 2004/08 [WS-ADDR] e W3C WS-Addressing 1,0 raccomandazioni [WS-ADDR-CORE] e [WS-ADDR-SOAP].

Anche se la specifica WS-Reliable Messaging menziona solo WS-Addressing 2004/08, non limita la versione WS-Addressing da utilizzare. Di seguito è riportato un elenco di vincoli che si applicano a WCF:

- R2101:sia WS-Addressing 2004/08 che WS-Addressing 1.0 possono essere utilizzati con WS-Reliable Messaging.

- R2102: è necessario utilizzare una sola versione di WS-Addressing in una determinata sequenza di WS-Reliable Messaging o in una coppia di sequenze opposte correlate tramite il `wsrm:Offer` meccanismo.

### <a name="composition-with-soap"></a>Composizione con SOAP

WCF supporta l'utilizzo di SOAP 1,1 e SOAP 1,2 con WS-Reliable Messaging.

### <a name="composition-with-ws-security-and-ws-secureconversation"></a>Composizione con WS-Security e WS-SecureConversation

WCF fornisce la protezione per le sequenze WS-Reliable Messaging usando il trasporto sicuro (HTTPS), la composizione con WS-Security e la composizione con WS-Secure Conversation. Di seguito è riportato un elenco di vincoli che si applicano a WCF:

- R2301: per proteggere l'integrità di una sequenza di WS-Reliable Messaging oltre all'integrità e alla riservatezza dei singoli messaggi, WCF richiede che sia necessario usare WS-Secure Conversation.

- R2302:prima di stabilire la/e sequenza/e di WS-Reliable Messaging, è necessario stabilire una sessione WS-SecureConversation.

- R2303: se la durata della sequenza di WS-Reliable Messaging supera la durata della sessione WS-SecureConversation, è necessario rinnovare il `SecurityContextToken` stabilito tramite WS-SecureConversation utilizzando l'associazione WS-Secure Conversation Renewal corrispondente.

- B2304: la sequenza di WS-Reliable Messaging o una coppia di sequenze opposte correlate sono sempre associate a una singola sessione WS-SecureConversation.

  L'origine WCF genera l' `wsse:SecurityTokenReference` elemento nella sezione di estendibilità degli elementi del `CreateSequence` messaggio.

- R2305: se composto con WS-Secure Conversation, un `CreateSequence` messaggio deve contenere l' `wsse:SecurityTokenReference` elemento.

## <a name="ws-reliable-messaging-ws-policy-assertion"></a>Asserzione di WS-Policy relativa a WS-Reliable Messaging

WCF usa l'asserzione WS-Policy WS-Reliable Messaging `wsrm:RMAssertion` per descrivere le funzionalità degli endpoint. Di seguito è riportato un elenco di vincoli che si applicano a WCF:

- B3001: WCF connette l' `wsrm:RMAssertion` asserzione WS-Policy agli `wsdl:binding` elementi. WCF supporta entrambi gli allegati `wsdl:binding` agli `wsdl:port` elementi e.

- B3002: WCF supporta le proprietà facoltative seguenti dell'asserzione WS-Reliable Messaging e ne fornisce il controllo su WCF `ReliableMessagingBindingElement` :

  - `wsrm:InactivityTimeout`

  - `wsrm:AcknowledgementInterval`

  Di seguito è riportato un esempio.

  ```xml
  <wsrm:RMAssertion>
    <wsrm:InactivityTimeout Milliseconds="600000" />
    <wsrm:AcknowledgementInterval Milliseconds="200" />
  </wsrm:RMAssertion>
  ```

## <a name="flow-control-ws-reliable-messaging-extension"></a>Estensione di WS-Reliable Messaging per il controllo del flusso

WCF utilizza l'estensibilità WS-Reliable Messaging per offrire un controllo facoltativo aggiuntivo più rigido sul flusso di messaggi della sequenza.

Il controllo di flusso viene abilitato impostando la <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.FlowControlEnabled?displayProperty=nameWithType> proprietà su `true` . Di seguito è riportato un elenco di vincoli che si applicano a WCF:

- B4001: quando è abilitato il controllo di flusso di Reliable Messaging, WCF genera un `netrm:BufferRemaining` elemento nell'estendibilità dell'elemento dell' `SequenceAcknowledgement` intestazione.

- B4002: quando è abilitato il controllo di flusso di Reliable Messaging, WCF non richiede `netrm:BufferRemaining` che un elemento sia presente nell' `SequenceAcknowledgement` intestazione, come illustrato nell'esempio seguente.

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

- B4003: WCF USA `netrm:BufferRemaining` per indicare il numero di nuovi messaggi che la destinazione della messaggistica affidabile può memorizzare nel buffer.

- B4004: il servizio WCF Reliable Messaging limita il numero di messaggi trasmessi quando l'applicazione di destinazione di Reliable Messaging non può ricevere rapidamente messaggi. La destinazione Reliable Messaging memorizza nel buffer messaggi e il valore dell'elemento scende a 0.

- B4005: WCF genera `netrm:BufferRemaining` valori integer compresi tra 0 e 4096 inclusivi e legge i valori integer compresi tra 0 e `xs:int` il `maxInclusive` valore 214748364 inclusi.

## <a name="message-exchange-patterns"></a>Modelli di scambio dei messaggi

In questa sezione viene descritto il comportamento di WCF quando WS-Reliable Messaging viene utilizzato per modelli di scambio di messaggi diversi. Per ogni modello di scambio di messaggi, vengono presi in considerazione i due scenari di distribuzione seguenti:

- Iniziatore non indirizzabile: l'iniziatore si trova dietro a un firewall; il risponditore può recapitare messaggi all'iniziatore solo su risposte HTTP.

- Iniziatore indirizzabile: le richieste HTTP possono essere inviate sia all'iniziatore che al risponditore. In altre parole, è possibile stabilire due connessioni HTTP opposte.

### <a name="one-way-non-addressable-initiator"></a>Iniziatore unidirezionale, non indirizzabile

#### <a name="binding"></a>Associazione

WCF fornisce un modello di scambio di messaggi unidirezionale utilizzando una sequenza su un canale HTTP. WCF usa le richieste HTTP per trasmettere tutti i messaggi da RMS a RMD e la risposta HTTP per trasmettere tutti i messaggi da RMD a RMS.

#### <a name="createsequence-exchange"></a>Scambio CreateSequence

L'iniziatore WCF genera un `CreateSequence` messaggio senza alcuna offerta. Il risponditore WCF garantisce che `CreateSequence` non abbia un'offerta prima di creare una sequenza. Il risponditore WCF risponde alla `CreateSequence` richiesta con un `CreateSequenceResponse` messaggio.

#### <a name="sequenceacknowledgement"></a>SequenceAcknowledgement

L'iniziatore WCF elabora i riconoscimenti della risposta di tutti i messaggi ad eccezione dei `CreateSequence` messaggi di errore e di messaggio. Il risponditore WCF genera sempre un riconoscimento autonomo nella risposta alla sequenza e ai `AckRequested` messaggi.

#### <a name="terminatesequence-message"></a>Messaggio TerminateSequence

WCF `TerminateSequence` viene considerato come un'operazione unidirezionale, ovvero la risposta http ha un corpo vuoto e un codice di stato HTTP 202.

### <a name="one-way-addressable-initiator"></a>Iniziatore unidirezionale, indirizzabile

#### <a name="binding"></a>Associazione

WCF fornisce un modello di scambio di messaggi unidirezionale utilizzando una sequenza su un canale HTTP in ingresso e in uscita. WCF utilizza le richieste HTTP per trasmettere tutti i messaggi. Tutte le risposte HTTP hanno un corpo vuoto e un codice di stato HTTP 202.

#### <a name="createsequence-exchange"></a>Scambio CreateSequence

L'iniziatore WCF genera un `CreateSequence` messaggio senza alcuna offerta. Il risponditore WCF garantisce che `CreateSequence` non abbia un'offerta prima di creare una sequenza. Il risponditore WCF trasmette il `CreateSequenceResponse` messaggio su una richiesta http risolta con il `ReplyTo` riferimento all'endpoint.

### <a name="duplex-addressable-initiator"></a>Iniziatore duplex, indirizzabile

#### <a name="binding"></a>Associazione

WCF fornisce un modello di scambio di messaggi bidirezionale completamente asincrono utilizzando due sequenze su un canale HTTP in ingresso e in uscita. WCF utilizza le richieste HTTP per trasmettere tutti i messaggi. Tutte le risposte HTTP hanno un corpo vuoto e un codice di stato HTTP 202.

#### <a name="createsequence-exchange"></a>Scambio CreateSequence

L'iniziatore WCF genera un `CreateSequence` messaggio con un'offerta. Il risponditore WCF garantisce che `CreateSequence` abbia un'offerta prima di creare una sequenza. WCF invia la `CreateSequenceResponse` sulla richiesta HTTP indirizzata al `CreateSequence` riferimento all' `ReplyTo` endpoint di.

#### <a name="sequence-lifetime"></a>Durata della sequenza

WCF tratta le due sequenze come una sessione completamente duplex.

Quando si genera un errore che genera errori in una sequenza, WCF prevede che l'endpoint remoto errori entrambe le sequenze. Durante la lettura di un errore che genera errori in una sequenza, WCF genera errori in entrambe le sequenze.

WCF può chiudere la sequenza in uscita e continuare a elaborare i messaggi sulla relativa sequenza in ingresso. Viceversa, WCF può elaborare la chiusura della sequenza in ingresso e continuare a inviare messaggi sulla relativa sequenza in uscita.

### <a name="request-reply-non-addressable-initiator"></a>Iniziatore request/reply non indirizzabile

#### <a name="binding"></a>Associazione

WCF fornisce un modello di scambio di messaggi unidirezionale e Request/Reply utilizzando due sequenze su un canale HTTP. WCF utilizza le richieste HTTP per trasmettere i messaggi della sequenza di richiesta e utilizza le risposte HTTP per trasmettere i messaggi della sequenza di risposta.

#### <a name="createsequence-exchange"></a>Scambio CreateSequence

L'iniziatore WCF genera un `CreateSequence` messaggio con un'offerta. Il risponditore WCF garantisce che `CreateSequence` abbia un'offerta prima di creare una sequenza. Il risponditore WCF risponde alla `CreateSequence` richiesta con un `CreateSequenceResponse` messaggio.

#### <a name="one-way-message"></a>Messaggio unidirezionale

Per completare correttamente un protocollo di scambio di messaggi unidirezionale, l'iniziatore WCF trasmette un messaggio della sequenza di richiesta sulla richiesta HTTP e riceve un messaggio autonomo `SequenceAcknowledgement` sulla risposta http. `SequenceAcknowledgement` deve riconoscere il messaggio trasmesso.

Il risponditore WCF può rispondere alla richiesta con un riconoscimento, un errore o una risposta con un corpo vuoto e un codice di stato HTTP 202.

#### <a name="two-way-messages"></a>Messaggi bidirezionali

Per completare correttamente un protocollo di scambio di messaggi bidirezionale, l'iniziatore WCF trasmette un messaggio della sequenza di richiesta sulla richiesta HTTP e riceve un messaggio della sequenza di risposta nella risposta HTTP. La risposta deve contenere un `SequenceAcknowledgement` che riconosce che il messaggio della sequenza di richiesta è stato trasmesso.

Il risponditore WCF può rispondere alla richiesta con una risposta dell'applicazione, un errore o una risposta con un corpo vuoto e un codice di stato HTTP 202.

A causa della presenza di messaggi unidirezionali e del tempo delle risposte dell'applicazione, il numero di sequenza del messaggio della sequenza di richiesta e il numero di sequenza del messaggio di risposta non hanno alcuna correlazione.

#### <a name="retrying-replies"></a>Nuovi tentativi di risposte

WCF si basa sulla correlazione request/reply HTTP per la correlazione tra protocolli di scambio di messaggi bidirezionali. Per questo motivo, l'iniziatore WCF non interrompe il nuovo tentativo di un messaggio della sequenza di richiesta quando il messaggio della sequenza di richiesta viene riconosciuto, ma piuttosto quando la risposta HTTP contiene un riconoscimento, un messaggio utente o un errore. Il risponditore WCF ritenta le risposte sulla parte della richiesta HTTP della richiesta a cui è correlata la risposta.

#### <a name="lastmessage-exchange"></a>Scambio LastMessage

L'iniziatore WCF genera e trasmette un ultimo messaggio con corpo vuoto sulla parte della richiesta HTTP. WCF richiede una risposta ma ignora il messaggio di risposta effettivo. Il risponditore WCF risponde all'ultimo messaggio con corpo vuoto della sequenza di richiesta con l'ultimo messaggio con corpo vuoto della sequenza di risposta.

Se il risponditore WCF riceve un ultimo messaggio in cui l'URI dell'azione non è `http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage` , WCF risponde con un ultimo messaggio. Nel caso di un protocollo di scambio di messaggi bidirezionale, l'ultimo messaggio contiene il messaggio dell'applicazione; nel caso, invece, di un protocollo di scambio di messaggi unidirezionale, l'ultimo messaggio è vuoto.

Il risponditore WCF non richiede un riconoscimento per l'ultimo messaggio con corpo vuoto della sequenza di risposta.

#### <a name="terminatesequence-exchange"></a>Scambio TerminateSequence

Quando tutte le richieste hanno ricevuto una risposta valida, l'iniziatore WCF genera e trasmette il messaggio della sequenza di richiesta `TerminateSequence` sulla parte della richiesta HTTP. WCF richiede una risposta ma ignora il messaggio di risposta effettivo. Il risponditore WCF risponde al messaggio della sequenza di richiesta `TerminateSequence` con il messaggio della sequenza di risposta `TerminateSequence` .

In una sequenza di arresto normale, entrambi i messaggi `TerminateSequence` contengono un intervallo completo `SequenceAcknowledgement`.

### <a name="requestreply-addressable-initiator"></a>Iniziatore request/reply, indirizzabile

#### <a name="binding"></a>Associazione

WCF fornisce un modello di scambio di messaggi request/reply utilizzando due sequenze su un canale HTTP in ingresso e in uscita. WCF utilizza le richieste HTTP per trasmettere tutti i messaggi. Tutte le risposte HTTP hanno un corpo vuoto e un codice di stato HTTP 202.

#### <a name="createsequence-exchange"></a>Scambio CreateSequence

L'iniziatore WCF genera un `CreateSequence` messaggio con un'offerta. Il risponditore WCF garantisce che `CreateSequence` abbia un'offerta prima di creare una sequenza. WCF invia la `CreateSequenceResponse` sulla richiesta HTTP indirizzata al `CreateSequence` riferimento all' `ReplyTo` endpoint di.

#### <a name="requestreply-correlation"></a>Correlazione request/reply

L'iniziatore WCF garantisce che tutti i messaggi di richiesta dell'applicazione contengano un `MessageId` e un `ReplyTo` riferimento all'endpoint. L'iniziatore WCF applica il `CreateSequence` riferimento all'endpoint del messaggio `ReplyTo` in ogni messaggio di richiesta dell'applicazione. Per il risponditore WCF è necessario che i messaggi di richiesta in ingresso contengano `MessageId` e `ReplyTo` . Il risponditore WCF garantisce che l'URI del riferimento dell'endpoint di `CreateSequence` e di tutti i messaggi di richiesta dell'applicazione siano identici.
