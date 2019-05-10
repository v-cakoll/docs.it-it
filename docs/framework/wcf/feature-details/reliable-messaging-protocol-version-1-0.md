---
title: Protocollo Reliable Messaging versione 1.0
ms.date: 03/30/2017
ms.assetid: a5509a5c-de24-4bc2-9a48-19138055dcce
ms.openlocfilehash: 857bbbf9ffa1311c38cfc007e0cdc6bde06d6284
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64617571"
---
# <a name="reliable-messaging-protocol-version-10"></a>Protocollo Reliable Messaging versione 1.0
In questo argomento vengono descritti i dettagli di implementazione Windows Communication Foundation (WCF) per WS-Reliable Messaging protocol di febbraio 2005 (versione 1.0) necessario per l'interoperatività con il trasporto HTTP. WCF è conforme alla specifica WS-Reliable Messaging con i vincoli e i chiarimenti illustrati in questo argomento. Si noti che il protocollo WS-Reliable Messaging versione 1.0 viene implementato a partire da [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)].  
  
 Il WS-Reliable Messaging febbraio 2005 protocollo viene implementato in WCF per il <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>.  
  
 Per comodità, nell'argomento vengono utilizzati i ruoli seguenti:  
  
- Iniziatore: il client che avvia la creazione della sequenza di WS-Reliable Message.  
  
- Risponditore: il servizio che riceve le richieste dell'iniziatore.  
  
 In questo documento vengono utilizzati i prefissi e gli spazi dei nomi riportati nella tabella seguente.  
  
|Prefisso|Spazio dei nomi|  
|------------|---------------|  
|wsrm|http://schemas.xmlsoap.org/ws/2005/02/rm|  
|netrm|http://schemas.microsoft.com/ws/2006/05/rm|  
|s|http://www.w3.org/2003/05/soap-envelope|  
|wsa|http://schemas.xmlsoap.org/ws/2005/08/addressing|  
|wsse|http://docs.oasis-open.org/wss/2004/01/oasis-200401-wssecurity-secext-1.0.xsd|  
  
## <a name="messaging"></a>Messaggistica  
  
### <a name="sequence-establishment-messages"></a>Messaggi di definizione sequenza  
 WCF implementa `CreateSequence` e `CreateSequenceResponse` messaggi per stabilire una sequenza di messaggi affidabili. Si applicano i vincoli seguenti:  
  
- B1101: L'iniziatore di WCF non genera l'elemento Expires facoltativo nel `CreateSequence` messaggio o, nei casi quando il `CreateSequence` messaggio contiene un `Offer` elemento, l'opzione facoltativa `Expires` elemento nel `Offer` elemento.  
  
- B1102: Quando si accede al `CreateSequence` dei messaggi, WCF`Responder` Invia e riceve entrambi `Expires` elementi se esiste, ma non usa i relativi valori.  
  
 Con il protocollo WS-ReliableMessaging viene introdotto il meccanismo `Offer` che consente di stabilire le due sequenze correlate opposte che formano una sessione.  
  
- R1103: Se `CreateSequence` contiene un `Offer` elemento, il risponditore Reliable Messaging necessario accettare la sequenza e rispondere con `CreateSequenceResponse` che contiene un `wsrm:Accept` elemento, formando due correlato sequenze opposte o rifiutare il `CreateSequence`richiesta.  
  
- R1104: i messaggi `SequenceAcknowledgement` e dell'applicazione in transito sulla sequenza opposta devono essere inviati al riferimento endpoint `ReplyTo` di `CreateSequence`.  
  
- R1105: i riferimenti endpoint `AcksTo` e `ReplyTo` in `CreateSequence` devono presentare valori indirizzo che corrispondano all'ottetto.  
  
     Il risponditore WCF verifica che la parte URI del `AcksTo` e `ReplyTo` EPR sono identici prima di creare una sequenza.  
  
- R1106: i riferimenti endpoint `AcksTo`e `ReplyTo` in `CreateSequence` devono avere lo stesso set di parametri per riferimento.  
  
     WCF non impone, ma presuppone che i parametri di riferimento] di `AcksTo` e `ReplyTo` sul `CreateSequence` siano identici e utilizza i parametri di riferimento] da `ReplyTo` riferimento dell'endpoint per acknowledgement e messaggi in sequenza opposta.  
  
- R1107: Quando vengono stabilite due sequenze opposte utilizzando il `Offer` meccanismo, `SequenceAcknowledgement` e i messaggi dell'applicazione sulle sequenze opposte devono essere inviati al `ReplyTo` riferimento all'endpoint del `CreateSequence`.  
  
- R1108: Quando vengono stabilite due sequenze opposte utilizzando il meccanismo Offer, la `[address]` proprietà del `wsrm:AcksTo` elemento figlio di riferimento dell'Endpoint del `wsrm:Accept` elemento del `CreateSequenceResponse` deve corrispondere numero di byte all'URI di destinazione del `CreateSequence`.  
  
- R1109: Quando vengono stabilite due sequenze opposte utilizzando il `Offer` meccanismo, i messaggi inviati dall'iniziatore e riconoscimenti per i messaggi dal risponditore devono essere inviati allo stesso riferimento dell'Endpoint.  
  
     WCF utilizza WS-Reliable Messaging per stabilire sessioni affidabili tra l'iniziatore e risponditore. Implementazione di WS-Reliable Messaging di WCF offre una sessione affidabile per unidirezionali, request / reply e full duplex modelli di messaggistica. WS-Reliable Messaging `Offer` meccanismo `CreateSequence` / `CreateSequenceResponse` ti permette di stabilire due sequenze opposte correlate e fornisce un protocollo della sessione è adatto per tutti gli endpoint del messaggio. Poiché WCF fornisce una garanzia di sicurezza per tale sessione, inclusa la protezione end-to-end per l'integrità della sessione, è consigliabile assicurarsi che i messaggi destinati alla stessa entità sono in arrivo alla stessa destinazione. Ciò consente anche il "piggy-backing" degli acknowledgement della sequenza sui messaggi dell'applicazione. Di conseguenza, i vincoli R1104, R1105 e R1108 si applicano a WCF.  
  
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
  
### <a name="sequence"></a>Sequence  
 Di seguito è riportato un elenco di vincoli che si applicano alle sequenze:  
  
- Genera l'errore B1201:WCF e gli accessi alla sequenza di numeri non superiori al `xs:long`del valore massimo, 9223372036854775807.  
  
- B1202:WCF genera sempre un messaggio ultimo con corpo vuoto con l'URI dell'azione di `http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage`.  
  
- B1203: WCF riceve e recapita un messaggio con un'intestazione di sequenza che contiene un `LastMessage` elemento fino a quando non è l'URI dell'azione `http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage`.  
  
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
 WCF Usa `AckRequested` intestazione come meccanismo keep-alive. WCF non genera facoltativo `MessageNumber` elemento. Quando viene ricevuto un messaggio con un `AckRequested` intestazione che contiene il `MessageNumber` elemento, WCF ignora il `MessageNumber` valore dell'elemento, come illustrato nell'esempio seguente.  
  
```xml  
<wsrm:AckRequested>  
  <wsrm:Identifier>  
    urn:uuid:addabbbf-60cb-44d3-8c5b-9e0841629a36  
  </wsrm:Identifier>  
</wsrm:AckRequested>  
```  
  
### <a name="sequenceacknowledgement-header"></a>Intestazione SequenceAcknowledgement  
 WCF Usa meccanismo piggy-back per gli acknowledgement di sequenza forniti in WS-Reliable Messaging.  
  
- R1401: Quando vengono stabilite due sequenze opposte utilizzando il `Offer` meccanismo, il `SequenceAcknowledgement` intestazione può essere incluso nei messaggi dell'applicazione trasmesso al destinatario desiderato.  
  
- B1402: Quando WCF deve generare un acknowledgement prima di ricevere qualsiasi messaggio di sequenza (ad esempio, per soddisfare un' `AckRequested` messaggio), WCF genera un `SequenceAcknowledgement` intestazione che contiene l'intervallo 0-0, come illustrato nell'esempio seguente.  
  
    ```xml  
    <wsrm:SequenceAcknowledgement>  
      <wsrm:Identifier>  
        urn:uuid:addabbbf-60cb-44d3-8c5b-9e0841629a36  
      </wsrm:Identifier>  
      <wsrm:AcknowledgementRange Upper="0" Lower="0"/>  
    </wsrm:SequenceAcknowledgement>  
    ```  
  
- B1403: WCF non genera `SequenceAcknowledgement` intestazioni contenenti un' `Nack` elemento, ma supporta `Nack` elementi.  
  
### <a name="ws-reliablemessaging-faults"></a>Errori WS-ReliableMessaging  
 Di seguito è riportato un elenco di vincoli che si applicano all'implementazione WCF di errori WS-Reliable Messaging:  
  
- B1501: WCF non genera `MessageNumberRollover` errori.  
  
- Endpoint B1502:WCF può generare `CreateSequenceRefused` genera un errore come descritto nella specifica.  
  
- B1503:when l'endpoint del servizio raggiunge il limite di connessione e non è in grado di elaborare nuove connessioni, WCF genera un'ulteriore `CreateSequenceRefused` codice secondario, di errore `netrm:ConnectionLimitReached`, come illustrato nell'esempio seguente.  
  
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
 Poiché WS-Reliable Messaging utilizza WS-Addressing, l'implementazione WCF WS-Reliable Messaging potrebbe generare errori WS-Addressing. In questa sezione vengono trattati gli errori WS-Addressing che WCF genera in modo esplicito a livello di WS-Reliable Messaging:  
  
- B1601:WCF genera l'errore Message Addressing Header Required quando viene soddisfatta una delle operazioni seguenti:  
  
    - In un messaggio mancano un'intestazione `Sequence` e un'intestazione `Action`.  
  
    - In un messaggio `CreateSequence` manca un'intestazione `MessageId`.  
  
    - In un messaggio `CreateSequence` manca un'intestazione `ReplyTo`.  
  
- B1602:WCF genera l'errore non sono supportate azioni in risposta a un messaggio che non è presente una `Sequence` intestazione e ha un `Action` intestazione che non riconosciuta nella specifica WS-Reliable Messaging.  
  
- B1603:WCF genera l'errore dell'Endpoint non disponibile per indicare che l'endpoint non elabora la sequenza in base all'esame del `CreateSequence` messaggio, intestazioni di indirizzamento.  
  
## <a name="protocol-composition"></a>Composizione del protocollo  
  
### <a name="composition-with-ws-addressing"></a>Composizione con WS-Addressing  
 WCF supporta due versioni di WS-Addressing: WS-Addressing 2004/08 [WS-ADDR] e W3C WS-Addressing 1.0 raccomandazioni [WS-ADDR-CORE] e [WS-ADDR-SOAP].  
  
 Anche se la specifica WS-Reliable Messaging menziona solo WS-Addressing 2004/08, non limita la versione WS-Addressing da utilizzare. Di seguito è riportato un elenco di vincoli che si applicano a WCF:  
  
- R2101: sia WS-Addressing 2004/08 che WS-Addressing 1.0 possono essere utilizzati con WS-Reliable Messaging.  
  
- R2102:A singola versione di WS-Addressing deve essere usato in una data sequenza di WS-Reliable Messaging o una coppia di sequenze opposte correlate tramite il `wsrm:Offer` meccanismo.  
  
### <a name="composition-with-soap"></a>Composizione con SOAP  
 WCF supporta l'utilizzo di SOAP 1.1 e SOAP 1.2 con WS-Reliable Messaging.  
  
### <a name="composition-with-ws-security-and-ws-secureconversation"></a>Composizione con WS-Security e WS-SecureConversation  
 WCF fornisce protezione per le sequenze di WS-Reliable Messaging utilizzando sicuro trasporto (HTTPS), composizione con WS-Security e composizione con WS-SecureConversation. Di seguito è riportato un elenco di vincoli che si applicano a WCF:  
  
- R2301: per proteggere l'integrità di una sequenza di WS-Reliable Messaging oltre all'integrità e riservatezza dei singoli messaggi, WCF, è necessario che deve essere utilizzato WS-SecureConversation.  
  
- R2302:AWS-Secure Conversation deve essere stabilita prima di stabilire sequence(s) WS-Reliable Messaging.  
  
- R2303: Se la durata della sequenza di WS-Reliable Messaging supera il WS-Secure Conversation durata della sessione, il `SecurityContextToken` stabilito tramite WS-Secure Conversation deve essere rinnovato tramite l'associazione WS-Secure Conversation Renewal corrispondente.  
  
- B2304:ws-sequenza di messaggistica affidabile o una coppia di sequenze opposte è sempre associata a una singola sessione WS-SecureConversation.  
  
     L'origine WCF genera il `wsse:SecurityTokenReference` elemento nella sezione dell'elemento di estensibilità del `CreateSequence` messaggio.  
  
- R2305:when composizione con WS-SecureConversation, un `CreateSequence` messaggio deve contenere il `wsse:SecurityTokenReference` elemento.  
  
## <a name="ws-reliable-messaging-ws-policy-assertion"></a>Asserzione di WS-Policy relativa a WS-Reliable Messaging  
 WCF utilizza l'asserzione di WS-Policy WS-Reliable Messaging `wsrm:RMAssertion` per descrivere le funzionalità degli endpoint. Di seguito è riportato un elenco di vincoli che si applicano a WCF:  
  
- B3001: WCF Allega `wsrm:RMAssertion` asserzione WS-Policy relativa a `wsdl:binding` elementi. WCF supporta i collegamenti agli `wsdl:binding` e `wsdl:port` elementi.  
  
- B3002: WCF supporta le proprietà facoltative seguenti dell'asserzione di WS-Reliable Messaging e fornisce controllo su di essi in WCF`ReliableMessagingBindingElement`:  
  
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
 WCF utilizza l'estendibilità di WS-Reliable Messaging per fornire un controllo facoltativo aggiuntivo sul flusso di messaggi sequenza.  
  
 Controllo di flusso viene abilitato impostando il <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.FlowControlEnabled?displayProperty=nameWithType> proprietà `true`. Di seguito è riportato un elenco di vincoli che si applicano a WCF:  
  
- B4001: Quando è abilitata la messaggistica affidabile flusso di controllo, WCF genera un `netrm:BufferRemaining` nell'estendibilità dell'elemento dell'elemento di `SequenceAcknowledgement` intestazione.  
  
- B4002: Quando è abilitata la messaggistica affidabile flusso di controllo, WCF non richiede un `netrm:BufferRemaining` elemento sia presente in `SequenceAcknowledgement` intestazione, come illustrato nell'esempio seguente.  
  
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
  
- B4003: WCF Usa `netrm:BufferRemaining` per indicare quanti nuovi messaggi la destinazione di Reliable Messaging può memorizzare nel buffer.  
  
- B4004: il servizio WCF Reliable Messaging limita il numero di messaggi trasmessi quando l'applicazione di destinazione Reliable Messaging non può ricevere messaggi rapidamente. La destinazione Reliable Messaging memorizza nel buffer messaggi e il valore dell'elemento scende a 0.  
  
- B4005: WCF genera `netrm:BufferRemaining` integer i valori compresi tra 0 e 4096 incluso e legge valori integer compresi tra 0 e `xs:int`del `maxInclusive` valore 214748364 incluso.  
  
## <a name="message-exchange-patterns"></a>Modelli di scambio dei messaggi  
 In questa sezione viene descritto il comportamento di WCF quando WS-Reliable Messaging viene usato per modelli di scambio di messaggi diversi. Per ogni modello di scambio di messaggi, vengono presi in considerazione i due scenari di distribuzione seguenti:  
  
- Iniziatore non indirizzabile: L'iniziatore è protetto da firewall; Risponditore può recapitare messaggi all'iniziatore solo su risposte HTTP.  
  
- Iniziatore indirizzabile: Iniziatore e risponditore sia possibile inviare richieste HTTP. in altre parole, è possano stabilire due connessioni HTTP opposte.  
  
### <a name="one-way-non-addressable-initiator"></a>Iniziatore unidirezionale, non indirizzabile  
  
#### <a name="binding"></a>Binding  
 WCF fornisce un modello di scambio di messaggi unidirezionale utilizzando una sequenza su un canale HTTP. WCF utilizza le richieste HTTP per trasmettere tutti i messaggi da RMS a RMD e la risposta HTTP per trasmettere tutti i messaggi da RMD a RMS.  
  
#### <a name="createsequence-exchange"></a>Scambio CreateSequence  
 L'iniziatore WCF genera un `CreateSequence` messaggio senza offerta. Il risponditore WCF garantisce la `CreateSequence` non abbia alcuna offerta prima di creare una sequenza. Il risponditore WCF risponde al `CreateSequence` della richiesta con un `CreateSequenceResponse` messaggio.  
  
#### <a name="sequenceacknowledgement"></a>SequenceAcknowledgement  
 L'iniziatore WCF elabora gli acknowledgement sulla risposta di tutti i messaggi tranne il `CreateSequence` messaggi e messaggi di errore. Il risponditore WCF genera sempre un acknowledgement autonomo in risposta alla sequenza e `AckRequested` messaggi.  
  
#### <a name="terminatesequence-message"></a>Messaggio TerminateSequence  
 WCF considera `TerminateSequence` come un'operazione unidirezionale, vale a dire la risposta HTTP ha un corpo vuoto e un codice di stato HTTP 202.  
  
### <a name="one-way-addressable-initiator"></a>Iniziatore unidirezionale, indirizzabile  
  
#### <a name="binding"></a>Binding  
 WCF fornisce un modello di scambio di messaggi unidirezionale utilizzando una sola sequenza su ingresso e un canale Http in uscita. WCF utilizza le richieste HTTP per trasmettere tutti i messaggi. Tutte le risposte HTTP hanno un corpo vuoto e un codice di stato HTTP 202.  
  
#### <a name="createsequence-exchange"></a>Scambio CreateSequence  
 L'iniziatore WCF genera un `CreateSequence` messaggio senza offerta. Il risponditore WCF garantisce che il `CreateSequence` non abbia alcuna offerta prima di creare una sequenza. Il risponditore WCF trasmette il `CreateSequenceResponse` messaggi su una richiesta HTTP indirizzata con la `ReplyTo` riferimento dell'endpoint.  
  
### <a name="duplex-addressable-initiator"></a>Iniziatore duplex, indirizzabile  
  
#### <a name="binding"></a>Binding  
 WCF fornisce un modello di scambio di messaggi bidirezionale completamente asincrono utilizzando due sequenze su un canale HTTP in uscita e ingresso. WCF utilizza le richieste HTTP per trasmettere tutti i messaggi. Tutte le risposte HTTP hanno un corpo vuoto e un codice di stato HTTP 202.  
  
#### <a name="createsequence-exchange"></a>Scambio CreateSequence  
 L'iniziatore WCF genera un `CreateSequence` messaggio con un'offerta. Il risponditore WCF garantisce che il `CreateSequence` abbia un'offerta prima di creare una sequenza. WCF invia il `CreateSequenceResponse` sulla richiesta HTTP indirizzata al `CreateSequence`del `ReplyTo` riferimento dell'endpoint.  
  
#### <a name="sequence-lifetime"></a>Durata della sequenza  
 WCF considera due sequenze come una sessione completamente duplex.  
  
 Dopo la generazione di un errore che origina errori in un'unica sequenza, WCF si aspetta che l'endpoint crei errori in entrambe le sequenze. Dopo la lettura di un errore che origina errori in un'unica sequenza, WCF genera un errore per entrambe le sequenze.  
  
 WCF è possibile chiudere la sequenza in uscita e continuare a elaborare i messaggi sulla sua sequenza in ingresso. Al contrario, WCF può elaborare la chiusura della sequenza in ingresso e continuare a inviare messaggi sulla sua sequenza in uscita.  
  
### <a name="request-reply-non-addressable-initiator"></a>Iniziatore request/reply non indirizzabile  
  
#### <a name="binding"></a>Binding  
 WCF fornisce unidirezionale e modello di scambio di messaggi request / reply utilizzando due sequenze su un canale HTTP. WCF utilizza le richieste HTTP per trasmettere i messaggi della sequenza di richiesta e Usa le risposte HTTP per trasmettere i messaggi della sequenza di risposta.  
  
#### <a name="createsequence-exchange"></a>Scambio CreateSequence  
 L'iniziatore WCF genera un `CreateSequence` messaggio con un'offerta. Il risponditore WCF garantisce che il `CreateSequence` abbia un'offerta prima di creare una sequenza. Il risponditore WCF risponde al `CreateSequence` della richiesta con un `CreateSequenceResponse` messaggio.  
  
#### <a name="one-way-message"></a>Messaggio unidirezionale  
 Per completare correttamente un protocollo di scambio di messaggi unidirezionale, l'iniziatore WCF trasmette un messaggio della sequenza di richiesta sulla richiesta HTTP e riceve un autonomo `SequenceAcknowledgement` messaggio sulla risposta HTTP. `SequenceAcknowledgement` deve riconoscere il messaggio trasmesso.  
  
 Il risponditore WCF può rispondere alla richiesta con un acknowledgement, un errore o una risposta con un corpo vuoto e un codice di stato HTTP 202.  
  
#### <a name="two-way-messages"></a>Messaggi bidirezionali  
 Per completare correttamente un protocollo di scambio di messaggi bidirezionale, l'iniziatore WCF trasmette un messaggio della sequenza di richiesta sulla richiesta HTTP e riceve un messaggio della sequenza di risposta sulla risposta HTTP. La risposta deve contenere un `SequenceAcknowledgement` che riconosce che il messaggio della sequenza di richiesta è stato trasmesso.  
  
 Il risponditore WCF può rispondere alla richiesta con una risposta dell'applicazione, un errore o una risposta con un corpo vuoto e un codice di stato HTTP 202.  
  
 A causa della presenza di messaggi unidirezionali e del tempo delle risposte dell'applicazione, il numero di sequenza del messaggio della sequenza di richiesta e il numero di sequenza del messaggio di risposta non hanno alcuna correlazione.  
  
#### <a name="retrying-replies"></a>Nuovi tentativi di risposte  
 WCF si fonda sulla correlazione request / reply HTTP per la correlazione del protocollo di scambio messaggi bidirezionale. Per questo motivo, l'iniziatore di WCF non smette di tentare un messaggio della sequenza di richiesta quando tale messaggio viene riconosciuto, ma piuttosto quando la risposta HTTP contiene un acknowledgement, un messaggio utente o un errore. Il risponditore WCF Ritenta le risposte sulla parte della richiesta HTTP della richiesta a cui è correlata la risposta.  
  
#### <a name="lastmessage-exchange"></a>Scambio LastMessage  
 L'iniziatore WCF genera e trasmette un messaggio ultimo con corpo vuoto sulla parte della richiesta HTTP. WCF non richiede una risposta ma ignora il messaggio di risposta effettivo. Le risposte del risponditore WCF della sequenza di richiesta con corpo vuoto ultimo messaggio con corpo vuoto ultimo messaggio della sequenza di risposta.  
  
 Se il risponditore WCF riceve un ultimo messaggio in cui l'URI dell'azione non è `http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage`, WCF risponde con un ultimo messaggio. Nel caso di un protocollo di scambio di messaggi bidirezionale, l'ultimo messaggio contiene il messaggio dell'applicazione; nel caso, invece, di un protocollo di scambio di messaggi unidirezionale, l'ultimo messaggio è vuoto.  
  
 Il risponditore WCF non richiede un acknowledgment per messaggio ultimo con corpo vuoto della sequenza di risposta.  
  
#### <a name="terminatesequence-exchange"></a>Scambio TerminateSequence  
 Quando tutte le richieste hanno ricevuto una risposta valida, l'iniziatore WCF genera e trasmette la sequenza di richiesta `TerminateSequence` messaggio sulla parte della richiesta HTTP. WCF non richiede una risposta ma ignora il messaggio di risposta effettivo. Il risponditore WCF risponde della sequenza di richiesta `TerminateSequence` messaggio con la sequenza di risposta `TerminateSequence` messaggio.  
  
 In una sequenza di arresto normale, entrambi i messaggi `TerminateSequence` contengono un intervallo completo `SequenceAcknowledgement`.  
  
### <a name="requestreply-addressable-initiator"></a>Iniziatore request/reply, indirizzabile  
  
#### <a name="binding"></a>Binding  
 WCF fornisce un modello di scambio di messaggi request / reply utilizzando due sequenze su un in ingresso e un canale HTTP in uscita. WCF utilizza le richieste HTTP per trasmettere tutti i messaggi. Tutte le risposte HTTP hanno un corpo vuoto e un codice di stato HTTP 202.  
  
#### <a name="createsequence-exchange"></a>Scambio CreateSequence  
 L'iniziatore WCF genera un `CreateSequence` messaggio con un'offerta. Il risponditore WCF garantisce che il `CreateSequence` abbia un'offerta prima di creare una sequenza. WCF invia il `CreateSequenceResponse` sulla richiesta HTTP indirizzata al `CreateSequence`del `ReplyTo` riferimento dell'endpoint.  
  
#### <a name="requestreply-correlation"></a>Correlazione request/reply  
 L'iniziatore di WCF assicura tutte le applicazioni richiesta messaggi presentino un `MessageId` e un `ReplyTo` riferimento dell'endpoint. L'iniziatore di WCF si applica il `CreateSequence` del messaggio `ReplyTo` riferimento dell'endpoint in ogni messaggio di richiesta dell'applicazione. Il risponditore WCF richiede messaggi di tale richiesta in ingresso presentino un `MessageId` e un `ReplyTo`. Il risponditore WCF garantisce che URI del riferimento dell'endpoint di entrambi i `CreateSequence` e tutti i messaggi di richiesta dell'applicazione sono identici.
