---
title: Protocolli di messaggistica
ms.date: 03/30/2017
ms.assetid: 5b20bca7-87b3-4c8f-811b-f215b5987104
ms.openlocfilehash: d35cd496db32e1a2886f7ca06e7a3d0964f9c9b5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184590"
---
# <a name="messaging-protocols"></a>Protocolli di messaggistica

Lo stack di canali di Windows Communication Foundation (WCF) utilizza i canali di codifica e trasporto per trasformare la rappresentazione interna del messaggio nel relativo formato di trasmissione e inviarlo utilizzando un trasporto specifico. Il trasporto più comunemente utilizzato per garantire l'interoperabilità dei servizi Web è il protocollo HTTP, mentre le codifiche utilizzate dai servizi Web sono in genere SOAP 1.1 basato su XML, SOAP 1.2 e il protocollo MTOM (Message Transmission Optimization Mechanism, meccanismo di ottimizzazione della trasmissione dei messaggi).

In questo argomento vengono illustrati i <xref:System.ServiceModel.Channels.HttpTransportBindingElement>dettagli di implementazione di WCF per i protocolli seguenti utilizzati da .

Specifiche/documento:

- [HTTP 1.1](https://www.ietf.org/rfc/rfc2616.txt)
- [Associazione HTTP SOAP 1.1](https://www.w3.org/TR/2000/NOTE-SOAP-20000508), Sezione 7
- [Binding HTTP SOAP 1.2](https://www.w3.org/TR/soap12-part2) Sezione 7

In questo argomento vengono illustrati i <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement> <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement> dettagli di implementazione di WCF per i protocolli seguenti che e impiegano.

Specifica/Documento:

- [Xml](https://www.w3.org/TR/REC-xml)
- [SOAP 1,1](https://www.w3.org/TR/2000/NOTE-SOAP-20000508/)
- [SOAP 1.2 Core](https://www.w3.org/TR/soap12-part1/)
- [WS-Addressing 2004/08](https://www.w3.org/Submission/2004/SUBM-ws-addressing-20040810/)
- [W3C Web Services Addressing 1.0 - Core](https://www.w3.org/TR/2006/REC-ws-addr-core-20060509)
- [W3C Web Services Addressing 1.0 - SOAP Binding](https://www.w3.org/TR/2006/REC-ws-addr-soap-20060509)
- [Indirizzamento dei servizi Web W3C 1.0 - Associazione WSDL](https://www.w3.org/TR/2006/CR-ws-addr-wsdl-20060529/)
- [W3C Web Services Addressing 1.0 - Metadata](https://www.w3.org/TR/ws-addr-metadata/)
- [Associazione WSDL SOAP1.1](https://www.w3.org/TR/wsdl/)
- [WSDL SOAP1.2 Binding](https://www.w3.org/Submission/wsdl11soap12/)

In questo argomento vengono illustrati i <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement> dettagli di implementazione di WCF per i protocolli seguenti che utilizzano.

Specifiche/documento:

- [XOP](https://www.w3.org/TR/xop10/)
- [Associazione MTOM SOAP 1.2](https://www.w3.org/TR/soap12-mtom/)
- [Associazione MTOM SOAP 1.1](https://www.w3.org/Submission/soap11mtom10/)
- [Asserzione di WS-Policy relativa a MTOM](https://www.w3.org/Submission/2006/SUBM-WS-MTOMPolicy-20061101/)

In questo argomento vengono utilizzati gli spazi dei nomi XML e i prefissi associati seguenti:The following XML namespaces and associated prefixes are used throughout this topic:

| Prefisso | URI (Uniform Resource Identifier) dello spazio dei nomi |
|------------|---------------------------------------------------|
| s11 | `http://schemas.xmlsoap.org/soap/envelope` |
| s12 |`http://www.w3.org/2003/05/soap-envelope` |
| wsa |`http://www.w3.org/2004/08/addressing` |
| wsam |`http://www.w3.org/2007/05/addressing/metadata` |
| wsap |`http://schemas.xmlsoap.org/ws/2004/09/policy/addressing` |
| wsa10 |`http://www.w3.org/2005/08/addressing` |
| wsaw10 |`http://www.w3.org/2006/05/addressing/wsdl` |
| xop |`http://www.w3.org/2004/08/xop/include` |
| xmime |`http://www.w3.org/2004/06/xmlmime`<br /><br /> `http://www.w3.org/2005/05/xmlmime` |
| Dp |`http://schemas.microsoft.com/net/2006/06/duplex` |

## <a name="soap-11-and-soap-12"></a>SOAP 1.1 e SOAP 1.2

### <a name="envelope-and-processing-model"></a>Modello di elaborazione della envelope
WCF implementa l'elaborazione della busta SOAP 1.1 dopo Basic Profile 1.1 (BP11) e Basic Profile 1.0 (SSBP10). L'elaborazione della SOAP 1.2 envelope viene implementata attenendosi alla specifica SOAP12-Part1.

In questa sezione vengono illustrate alcune scelte di implementazione eseguite da WCF per quanto riguarda BP11 e SOAP12-Part1.

#### <a name="mandatory-header-processing"></a>Elaborazione obbligatoria delle intestazioni
WCF segue le regole `mustUnderstand` per l'elaborazione delle intestazioni contrassegnate come descritte nelle specifiche SOAP 1.1 e SOAP 1.2, con le variazioni seguenti.

Un messaggio che entra nello stack di canali WCF viene elaborato da singoli canali configurati da elementi di associazione associati, ad esempio Codifica sms, Sicurezza, Messaggistica affidabile e Transazioni. Ogni canale riconosce le intestazioni dallo spazio dei nomi associato e le contrassegna come riconosciute. Dopo l'inserimento di un messaggio nel dispatcher, il formattatore dell'operazione legge le intestazioni previste dal contratto di messaggio/operazione corrispondente e le contrassegna come riconosciute. Quindi, il dispatcher verifica se esistono intestazioni non riconosciute ma la cui intestazione `mustUnderstand` richiede il riconoscimento e, in tal caso, genera un'eccezione. I messaggi che contengono intestazioni `mustUnderstand` indirizzate al destinatario non vengono elaborati dal codice dell'applicazione di destinazione.

Questo tipo di elaborazione a livelli consente la separazione fra i livelli di infrastruttura e livelli di applicazione del nodo SOAP:

- B1111: le intestazioni che non sono comprese vengono rilevate dopo l'elaborazione del messaggio dallo stack di canali dell'infrastruttura WCF, ma prima che venga elaborato dall'applicazione

     Il valore dell'intestazione `mustUnderstand` differisce tra SOAP 1.1 e SOAP 1.2. Basic Profile 1.1 richiede che il valore di `mustUnderstand` sia 0 o 1 per i messaggi SOAP 1.1. La specifica di SOAP 1.2, oltre ai valori 0 e 1, prevede inoltre i valori `false` e `true`. Tuttavia, tale specifica consiglia di applicare una rappresentazione canonica dei valori `xs:boolean`, ovvero `false` e `true`.

- B1112: WCF `mustUnderstand` genera valori 0 e 1 per entrambe le versioni SOAP 1.1 e SOAP 1.2 della busta SOAP. WCF accetta l'intero `xs:boolean` spazio `mustUnderstand` del valore di `false`per `true`l'intestazione (0, 1, , )

#### <a name="soap-faults"></a>Errori SOAP
Di seguito è riportato un elenco di implementazioni di errore SOAP specifiche di WCF.

- B2121: WCF restituisce i seguenti codici `s11:mustUnderstand` `s11:Client`di `s11:Server`errore SOAP 1.1: , e .

- B2122: WCF restituisce i seguenti codici `s12:MustUnderstand` `s12:Sender`di `s12:Receiver`errore SOAP 1.2: , e .

### <a name="http-binding"></a>Associazione HTTP

#### <a name="soap-11-http-binding"></a>Associazione SOAP 1,1 HTTP
WCF implementa l'associazione HTTP SOAP1.1 seguendo la sezione 3.4 della specifica Basic Profile 1.1 con i chiarimenti seguenti:

- B2211: il servizio WCF non implementa il reindirizzamento delle richieste HTTP POST.

- B2212: I client WCF supportano i cookie HTTP in conformità con 3.4.8.B2212: WCF clients support HTTP Cookies in accordance with 3.4.8.

#### <a name="soap-12-http-binding"></a>Associazione SOAP 1,2 HTTP
WCF implementa l'associazione HTTP SOAP 1.2 come descritto nella specifica SOAP 1.2-part 2 (SOAP12Part2) con i chiarimenti seguenti.

SOAP 1.2 introduce un nuovo parametro Action facoltativo per il tipo di supporto `application/soap+xml`. Questo parametro è utile per ottimizzare l'invio dei messaggi in quanto elimina l'esigenza di analizzare il corpo del messaggio SOAP quando non si utilizza la specifica WS-Addressing.

- R2221: il parametro Action `application/soap+xml`, quando presente in una richiesta SOAP 1.2, deve corrispondere all'attributo `soapAction` dell'elemento `wsoap12:operation` contenuto nell'associazione WSDL corrispondente.

- R2222: il parametro Action `application/soap+xml`, quando presente in un messaggio SOAP 1.2, deve corrispondere all'elemento `wsa:Action` quando si utilizza la specifica WS-Addressing 2004/08 o la specifica WS-Addressing 1.0.

Quando la specifica WS-Addressing è disabilitata e in una richiesta in ingresso non è incluso alcun parametro Action, il parametro `Action` del messaggio viene considerato come non specificato.

## <a name="ws-addressing"></a>WS-Addressing
WCF implementa 3 versioni di WS-Addressing:

- WS-Addressing 2004/08

- Specifica di base di W3C Web Services Addressing 1.0 (ADDR10-CORE) e associazione SOAP (ADDR10-SOAP)

- WS-Addressing 1.0 - Metadata

### <a name="endpoint-references"></a>Riferimenti a endpoint
Tutte le versioni di WS-Addressing implementate da WCF utilizzano i riferimenti endpoint per descrivere gli endpoint.

#### <a name="endpoint-references-and-ws-addressing-versions"></a>Utilizzo dei riferimenti a endpoint con le versioni di WS-Addressing
WCF implementa una serie di protocolli di infrastruttura che `EndpointReference` utilizzano WS-Addressing e in particolare l'elemento e `W3C.WsAddressing.EndpointReferenceType` la classe (ad esempio, WS-ReliableMessaging, WS-SecureConversation e WS-Trust). WCF supporta l'utilizzo di entrambe le versioni di WS-Addressing con altri protocolli di infrastruttura. Gli endpoint WCF supportano una versione di WS-Addressing per endpoint.

Per R3111, lo `EndpointReference` spazio dei nomi per l'elemento o il tipo utilizzato nei messaggi scambiati con un endpoint WCF deve corrispondere alla versione di WS-Addressing implementata da questo endpoint.

Ad esempio, se un endpoint WCF implementa `AcksTo` WS-ReliableMessaging, l'intestazione restituita da tale endpoint all'interno `CreateSequenceResponse` utilizza la versione WS-Addressing che l'elemento `EncodingBinding` specifica per questo endpoint.

#### <a name="endpoint-references-and-metadata"></a>Utilizzo dei riferimenti a endpoint con i metadati
Diversi scenari richiedono la comunicazione di metadati o di riferimenti a metadati relativi a un dato endpoint.

B3121: WCF utilizza i meccanismi descritti nella specifica WS-MetadataExchange (MEX) Sezione 6 per includere i metadati per i riferimenti agli endpoint per valore o per riferimento.

Si consideri uno scenario in cui un servizio WCF richiede l'autenticazione utilizzando `http://sts.fabrikam123.com`un token SAML (Security Assertions Markup Language) emesso dall'autorità emittente di token in . L'endpoint WCF descrive questo `sp:IssuedToken` requisito di `sp:Issuer` autenticazione utilizzando l'asserzione con un'asserzione annidata che punta all'autorità emittente di token. Le applicazioni client che accedono all'asserzione `sp:Issuer` devono conoscere la modalità di comunicazione con l'endpoint dell'emittente di token. In particolare, il client deve conoscere i metadati relativi all'emittente di token. Utilizzando le estensioni dei metadati di riferimento dell'endpoint definite in MEX, WCF fornisce un riferimento ai metadati dell'autorità emittente di token.

```xml
<sp:IssuedToken>
  <sp:Issuer>
    <wsa10:Address>
      http://sts.fabrikam123.com
    </wsa10:Address>
    <wsa10:Metadata>
      <mex:Metadata>
        <mex:MetadataSection>
          <mex:MetadataReference>
            <wsa10:Address>
              http://sts.fabrikam123.com/mex
            </wsa10:Address>
          </mex:MetadataReference>
        </mex:MetadataSection>
      </mex:Metadata>
    </wsa10:Metadata>
  </sp:Issuer>
</sp:IssuedToken>
```

### <a name="message-addressing-headers"></a>Intestazioni di indirizzamento dei messaggi

#### <a name="message-headers"></a>Intestazioni del messaggio
Per entrambe le versioni di WS-Addressing, WCF utilizza `wsa:To` `wsa:ReplyTo`le `wsa:Action` `wsa:MessageID`intestazioni dei messaggi seguenti come prescritto dalle specifiche , , , e `wsa:RelatesTo`.

B3211: per tutte le versioni di WS-Addressing, WCF rispetta, ma non `wsa:FaultTo` produce, intestazioni dei messaggi WS-Addressing e `wsa:From`.

Le applicazioni che interagiscono con le applicazioni WCF possono aggiungere queste intestazioni di messaggio e WCF le elaborerà di conseguenza.

#### <a name="reference-parameters-and-properties"></a>Parametri e proprietà dei riferimenti

WCF implementa l'elaborazione dei parametri di riferimento dell'endpoint e delle proprietà di riferimento in base alle rispettive specifiche.

B3221: se configurato per l'utilizzo di WS-Addressing 2004/08, gli endpoint WCF non distinguono tra l'elaborazione delle proprietà di riferimento e i parametri di riferimento.

### <a name="message-exchange-patterns"></a>Modelli di scambio dei messaggi
La sequenza dei messaggi coinvolti nella chiamata dell'operazione del servizio Web viene definita modello di *scambio*dei messaggi . WCF supporta modelli di scambio di messaggi unidirezionali, richiesta-risposta e duplex. Questa sezione descrive i requisiti della specifica WS-Addressing che definiscono il modo in cui il modello di scambio dei messaggi usato influisce sull'elaborazione dei messaggi.

Contenuto della sezione, il richiedente invia il primo messaggio e il risponditore riceve il primo messaggio.

#### <a name="one-way-message"></a>Modello unidirezionale
Quando un endpoint WCF è configurato `Action` per supportare i messaggi con un dato di seguire un modello unidirezionale, l'endpoint WCF segue i comportamenti e i requisiti seguenti. Se non diversamente specificato, i comportamenti e le regole si applicano a entrambe le versioni di WS-Addressing supportate in WCF:

- R3311: il richiedente deve includere gli elementi `wsa:To` e `wsa:Action` nonché le intestazioni di tutti i parametri specificati nel riferimento a endpoint. Quando si utilizza la specifica WS-Addressing 2004/08 e il riferimento a endpoint specifica le proprietà di riferimento [reference properties], occorre aggiungere al messaggio anche le intestazioni corrispondenti.

- B3312: il richiedente può includere le intestazioni `MessageID` e `ReplyTo` e `FaultTo`. Dopo essere stati ignorati dall'infrastruttura del destinatario, questi elementi vengono passati all'applicazione.

- R3313: quando si utilizza il protocollo HTTP e non viene inviato alcun messaggio sul canale di risposta HTTP, il risponditore deve inviare una risposta HTTP contenente un corpo vuoto e un codice di stato HTTP 202.

     Quando si utilizza il trasporto HTTP e il contratto dell'operazione dichiara un messaggio unidirezionale, la risposta HTTP può comunque essere utilizzata per l'invio di messaggi di infrastruttura. Ad esempio, la funzionalità di messaggistica affidabile può inviare un messaggio `SequenceAcknowledgement` in una risposta HTTP.

- B3314: il risponditore WCF non invia un messaggio di errore in risposta a un messaggio unidirezionale.

#### <a name="request-reply"></a>Request/Reply
Quando un endpoint WCF è configurato `Action` per un messaggio con un dato di follow-the follow del modello di richiesta-risposta, l'endpoint WCF segue i comportamenti e i requisiti riportati di seguito. Se non diversamente specificato diversamente, i comportamenti e le regole si applicano a entrambe le versioni di WS-Addressing supportate in WCF:

- R3321: il richiedente deve `wsa:To`includere `wsa:Action` `wsa:MessageID`nella richiesta , , e le intestazioni per tutti i parametri di riferimento o le proprietà di riferimento (o entrambi) specificati dal riferimento all'endpoint.

- R3322: quando si utilizza la specifica WS-Addressing 2004/08, nella richiesta deve essere incluso anche l'elemento `ReplyTo`.

- R3323: quando WS-Addressing 1.0 `ReplyTo` viene utilizzato e non è presente nella richiesta, viene `http://www.w3.org/2005/08/addressing/anonymous` utilizzato un riferimento all'endpoint predefinito con la proprietà [address] uguale a.

- R3324: il richiedente `wsa:To` `wsa:Action`deve `wsa:RelatesTo` includere le intestazioni , e nel messaggio di risposta, nonché le `ReplyTo` intestazioni per tutti i parametri di riferimento o le proprietà di riferimento (o entrambi) specificati dal riferimento all'endpoint nella richiesta.

### <a name="web-services-addressing-faults"></a>Errori di indirizzamento dei servizi Web
R3411: WCF produce i seguenti errori definiti da WS-Addressing 2004/08.

| Codice | Causa |
|----------|-----------|
| `wsa:DestinationUnreachable` | Il messaggio in ingresso presenta un riferimento `ReplyTo` diverso dall'indirizzo per risposte definito per questo canale. Non esiste alcun endpoint in attesa presso l'indirizzo specificato nell'intestazione di destinazione. |
| `wsa:ActionNotSupported` | I canali dell'infrastruttura o il dispatcher associato all'endpoint non riconoscono l'azione specificata nell'intestazione `Action`. |

R3412: WCF produce i seguenti errori definiti da WS-Addressing 1.0.

| Codice | Causa |
|----------|-----------|
| `wsa10:InvalidAddressingHeader` | `wsa:To`Duplicare `wsa:ReplyTo` `wsa:From` , `wsa:MessageID`, o . Duplicare `wsa:RelatesTo` con `RelationshipType`lo stesso file . |
| `wsa10:MessageAddressingHeaderRequired` | L'intestazione obbligatoria di indirizzamento è mancante. |
| `wsa10:DestinationUnreachable` | Il messaggio in ingresso presenta un riferimento `ReplyTo` diverso dall'indirizzo per risposte definito per questo canale. Non esiste alcun endpoint in attesa presso l'indirizzo specificato nell'intestazione di destinazione. |
| `wsa10:ActionNotSupported` | I canali dell'infrastruttura o il dispatcher associato all'endpoint non riconoscono l'azione specificata nell'intestazione `Action`. |
| `wsa10:EndpointUnavailable` | Il canale RM restituisce questo errore per indicare che l'endpoint non elaborerà la sequenza basata sull'esame delle intestazioni di indirizzamento del messaggio `CreateSequence`. |

Il codice delle tabelle precedenti viene mappato al codice `FaultCode` in SOAP 1.1 e al codice `SubCode` (in cui il codice corrisponde al mittente) in SOAP 1.2.

### <a name="wsdl-11-binding-and-ws-policy-assertions"></a>Utilizzo di associazioni WSDL 1.1 con le asserzioni di WS-Policy

#### <a name="indicating-use-of-ws-addressing"></a>Definizione dell'uso di WS-Addressing
WCF utilizza asserzioni di criteri per indicare il supporto dell'endpoint per una particolare versione di WS-Addressing.WCF uses policy assertions to indicate endpoint support for a particular WS-Addressing version.

L'asserzione di criteri seguente contiene il soggetto dei criteri di endpoint [WS-PA] e indica che i messaggi scambiati con l'endpoint devono utilizzare la specifica WS-Addressing 2004/08.

```xml
<wsap:UsingAddressing />
```

Questa asserzione di criteri si aggiunge alla specifica WS-Addressing 2004/08.

Tramite l'asserzione di criteri seguente viene indicato che nei messaggi inviati/ricevuti deve essere utilizzato WS-Addressing 1.0.

```xml
<wsam:Addressing/>
```

Nell'asserzione di criteri seguente è incluso un soggetto dei criteri di endpoint [WS-PA] e viene indicato che nei messaggi scambiati con l'endpoint deve essere utilizzata la specifica WS-Addressing 2004/08.

```xml
<wsaw10:UsingAddressing />
```

L'elemento `wsaw10:UsingAddressing` è preso in prestito da [WS-Addressing-WSDL] e viene utilizzato nel contesto di WS-Policy in conformità alla sezione 3.1.2 di tale specifica.

L'utilizzo dell'intestazione di indirizzamento non modifica la semantica delle associazioni WSDL 1.1 HTTP, SOAP 1.1 HTTP e SOAP 1.2 HTTP. Ad esempio, se si prevede una risposta a una richiesta inviata a un endpoint in cui vengono utilizzati WS-Addressing e l'associazione WSDL SOAP 1.x HTTP, la risposta deve essere inviata tramite la risposta HTTP.

Per le risposte inviate tramite la risposta http, l'asserzione WS-AM è:

```xml
<wsam:AnonymousResponses/>
```

L'asserzione di criteri completa potrebbe essere simile alla seguente:

```xml
<wsam:Addressing>
    <wsp:Policy>
        <wsam:AnonymousResponses />
    </wsp:Policy>
</wsam:Addressing>
```

Tuttavia, sono presenti modelli di scambio dei messaggi che traggono profitto dalla presenza di due connessioni HTTP opposte indipendenti stabilite tra il richiedente e il risponditore, ad esempio i messaggi unidirezionali non richiesti inviati dal risponditore.

WCF offre una funzionalità tramite la quale due canali di trasporto sottostanti possono formare un canale Duplex composito, in cui un canale viene utilizzato per i messaggi di input e l'altro per i messaggi di output. Nel caso del trasporto HTTP, il modello duplex composito offre due connessioni HTTP opposte. Il richiedente utilizza una connessione per inviare i messaggi al risponditore, mentre quest'ultimo utilizza l'altra connessione per inviare i messaggi di risposta al richiedente.

Per le risposte inviate tramite richieste http distinte, l'asserzione ws-am è:

```xml
<wsam:NonAnonymousResponses/>
```

L'asserzione di criteri completa potrebbe essere simile alla seguente:

```xml
<wsam:Addressing>
    <wsp:Policy>
        <wsam:NonAnonymousResponses />
    </wsp:Policy>
</wsam:Addressing>
```

Per l'utilizzo dell'asserzione seguente che presenta il soggetto dei criteri di endpoint [WS-PA] negli endpoint in cui vengono utilizzate le associazioni SOAP 1.x HTTP WSDL 1.1 sono richieste due connessioni HTTP opposte e distinte da utilizzare rispettivamente per i messaggi dal richiedente al risponditore e dal risponditore al richiedente.

```xml
<cdp:CompositeDuplex/>
```

L'istruzione precedente comporta i requisiti seguenti per l'intestazione `wsa:ReplyTo` dei messaggi di richiesta:

- R3514: i messaggi di richiesta `ReplyTo` inviati a `[address]` un endpoint `http://www.w3.org/2005/08/addressing/anonymous` devono avere un'intestazione con la proprietà diversa da se `wsap10:UsingAddressing` l'endpoint utilizza un'associazione HTTP SOAP 1.x WSDL 1.1 e dispone di un'alternativa di criteri con `wsap:UsingAddressing` un'asserzione o associata. `cdp:CompositeDuplex`

- R3515: i messaggi di richiesta `ReplyTo` inviati a `[address]` un `http://www.w3.org/2005/08/addressing/anonymous`endpoint devono avere `ReplyTo` un'intestazione con la proprietà uguale o non avere un'intestazione, se l'endpoint utilizza un'associazione HTTP WSDL 1.1 SOAP 1.x e dispone di un'alternativa di criteri con `wsap10:UsingAddressing` asserzione e asserzione associata. `cdp:CompositeDuplex`

- R3516: i messaggi di richiesta `ReplyTo` inviati a `[address]` un `http://www.w3.org/2005/08/addressing/anonymous` endpoint devono avere un'intestazione con una proprietà uguale a `wsap:UsingAddressing` se `cdp:CompositeDuplex` l'endpoint utilizza un'associazione HTTP SOAP 1.x WSDL 1.1 e dispone di un'alternativa dei criteri con asserzione e asserzione associata.

La specifica WS-Addressing WSDL tenta di descrivere associazioni del protocollo simili introducendo un elemento `<wsaw:Anonymous/>` con tre valori testuali (obbligatorio, facoltativo e proibito) per indicare requisiti nell'intestazione `wsa:ReplyTo` (sezione 3.2). Sfortunatamente, tale definizione dell'elemento non è utilizzabile in modo specifico nel contesto di WS-Policy, perché richiede estensioni specifiche di dominio per supportare l'intersezione di alternative che utilizzano tale elemento come asserzione. A differenza del comportamento di endpoint in transito, che rende il valore dell'intestazione `ReplyTo` specifico del trasporto HTTP, il suddetto elemento indica questo valore senza associarlo a un determinato protocollo.

#### <a name="action-definition"></a>Definizione dell'attributo Action
La specifica WS-Addressing 2004/08 definisce un attributo `wsa:Action` per gli elementi `wsdl:portType/wsdl:operation/[wsdl:input | wsdl:output | wsdl:fault]`. L'associazione WS-Addressing 1.0 WSDL (WS-ADDR10-WSDL) definisce un attributo simile, ovvero `wsaw10:Action`.

L'unica differenza consiste nella semantica del modello Action predefinito, descritta rispettivamente nella sezione 3.3.2 della specifica WS-ADDR e nella sezione 4.4.4 della specifica WS-ADDR10-WSDL.

È ragionevole avere due endpoint che condividono lo stesso `portType` (o contratto, nella terminologia WCF) ma utilizzando versioni diverse di WS-Addressing. Tuttavia, se l'attributo Action è definito dall'attributo `portType` e deve essere condiviso da tutti gli endpoint che implementano l'attributo `portType`, risulta impossibile supportare entrambi i modelli Action predefiniti.

Per risolvere questa controversia, WCF supporta una `Action` singola versione dell'attributo.

B3521: WCF `wsaw10:Action` utilizza `wsdl:portType/wsdl:operation/[wsdl:input | wsdl:output | wsdl:fault]` l'attributo sugli elementi come definito in `Action` WS-ADDR10-WSDL per determinare l'URI per i messaggi corrispondenti indipendentemente dalla versione DI WS-Addressing utilizzata dall'endpoint.

#### <a name="use-endpoint-reference-inside-wsdl-port"></a>Utilizzare il riferimento a endpoint nell'elemento wsdl:port
La sezione 4.1 di WS-ADDR10-WSDL estende l'elemento `wsdl:port` per includere l'elemento figlio `<wsa10:EndpointReference…/>` allo scopo di descrivere l'endpoint in termini di WS-Addressing. WCF espande questa utilità in WS-Addressing 2004/08, consentendo `<wsa:EndpointReference…/>` `wsdl:port`la visualizzazione come elemento figlio di .

- R3531: se a un endpoint è associata un'alternativa criteri avente un'asserzione di criteri `<wsaw10:UsingAddressing/>``wsdl:port`.

- R3532: se `wsdl:port` un oggetto `<wsa10:EndpointReference …/>`contiene `wsa10:EndpointReference/wsa10:Address` un elemento figlio , `@address` il valore dell'elemento figlio deve corrispondere al valore dell'attributo dell'elemento di pari livello. `wsdl:port` / `wsdl:location`

- R3533: se a un endpoint è associata un'alternativa criteri avente un'asserzione di criteri `<wsap:UsingAddressing/>``wsdl:port`.

- R3534: se `wsdl:port` un oggetto `<wsa:EndpointReference …/>`contiene `wsa:EndpointReference/wsa:Address` un elemento figlio , `@address` il valore dell'elemento figlio deve corrispondere al valore dell'attributo dell'elemento di pari livello. `wsdl:port` / `wsdl:location`

### <a name="composition-with-ws-security"></a>Integrazione con WS-Security
Secondo le sezioni di WS-ADDR e WS-ADDR10 relative alle considerazioni sulla sicurezza, è consigliabile firmare tutte le intestazioni dei messaggi di indirizzamento insieme al corpo del messaggio, in modo da associarli fra loro.

Quando si utilizza WS-Security per garantire l'integrità dei messaggi, le intestazioni dei messaggi di WS-Addressing nonché le intestazioni ottenute dai parametri o dalle proprietà del riferimento (o da entrambi) devono essere firmate insieme al corpo del messaggio.

### <a name="examples"></a>Esempi

#### <a name="one-way-message"></a>Modello unidirezionale
In questo scenario, il mittente invia un messaggio unidirezionale al destinatario. Vengono utilizzate le specifiche SOAP 1.2, HTTP 1.1 e W3C WS-Addressing 1.0.

Struttura dei messaggi di richiesta: le intestazioni dei messaggi includono gli elementi `wsa10:To` e `wsa10:Action`. Il corpo dei messaggi include un elemento `<app:Ping>` specifico dello spazio dei nomi dell'applicazione.

Intestazioni HTTP: la destinazione in POST `wsa10:To` corrisponde all'URI nell'elemento.

L'intestazione Content-Type dispone del valore di `application/soap+xml` come richiesto da SOAP 1.2. I parametri `charset` e `action` sono inclusi. Il parametro `action` dell'intestazione Content-Type corrisponde al valore dell'intestazione dei messaggi `wsa10:Action`.

```
POST http://fabrikam123.com/Service HTTP/1.1
Content-Type: application/soap+xml; charset=utf-8;  
              action="http://fabrikam123.com/Service/OneWay"
Host: 131.107.72.15
Content-Length: 1501
Expect: 100-continue
Proxy-Connection: Keep-Alive
<s12:Envelope>
  <s12:Header>
    <wsa10:To s12:mustUnderstand="1">
        http://fabrikam123.com/Service
    </wsa10:To>
    <wsa10:Action s12:mustUnderstand="1">
        http://fabrikam123.com/Service/OneWay
    </wsa10:Action>
  </s12:Header>
  <s12:Body>
    <Ping xmlns="http://fabrikam123.com/Service/">
      <Text>Hello World</Text>
    </Ping>
  </s12:Body>
</s12:Envelope>
```

Il destinatario fornisce con una risposta HTTP vuota e lo stato 202. Un esempio della risposta HTTP:

```
HTTP/1.1 202 Accepted
Date: Fri, 15 Jul 2005 08:56:07 GMT
Server: Microsoft-IIS/6.0
MicrosoftOfficeWebServer: 5.0_Pub
X-Powered-By: ASP.NET
X-AspNet-Version: 2.0.50215
Cache-Control: private
Content-Length: 0
```

## <a name="soap-message-transmission-optimization-mechanism"></a>SOAP MTOM
In questa sezione vengono descritti i dettagli di implementazione WCF per il servizio MTOM SOAP HTTP. La tecnologia MTOM è un meccanismo di codifica dei messaggi SOAP della stessa classe della codifica testo/XML tradizionale o della codifica binaria WCF. Il meccanismo MTOM prevede le funzionalità seguenti:

- Meccanismo di codifica e assemblaggio di pacchetti XML descritto da [XOP] che ottimizza le voci di informazioni XML contenenti dati binari con codifica in base 64 suddividendoli in parti binarie distinte.

- Incapsulamento MIME del pacchetto XOP che serializza l'InfoSet XML e ogni parte binaria del pacchetto XOP in una parte MIME distinta.

- Codifica MIME XOP applicata alla SOAP 1.x envelope.

- Associazione di trasporto HTTP.

È possibile usare MTOM con trasporti non HTTP con WCF. quanto descritto in questo argomento si basa sul protocollo HTTP.

Il formato MTOM sfrutta un numeroso set di specifiche relative al meccanismo MTOM stesso, a XOP e a MIME. La modularità di questo set di specifiche rende piuttosto difficile ricavare in modo esatto i requisiti relativi alla semantica di formato ed elaborazione. Questa sezione descrive i requisiti di formato ed elaborazione dell'associazione MTOM HTTP.

### <a name="mtom-message-encoding"></a>Codifica dei messaggi MTOM

#### <a name="generating-mtom-messages"></a>Generazione di messaggi MTOM
La sezione 3.1 di [XOP] descrive il processo di codifica di elementi XML aventi voci di informazioni sugli elementi contenenti valori in base 64 in un pacchetto XOP definito in modo astratto.

La sequenza di passaggi seguente descrive il processo di codifica specifico del meccanismo MTOM:

1. Assicurarsi che la busta SOAP da codificare non `[local name]` `Include`contenga alcun elemento di informazioni sull'elemento con un `[namespace name]` e `http://www.w3.org/2004/08/xop/include` un oggetto di .

2. Creare un pacchetto MIME vuoto.

3. Identificare all'interno dell'InfoSet XML originale le voci di informazioni sugli elementi da ottimizzare. Per gli elementi da ottimizzare, i `[children]` caratteri che costituiscono l'elemento di `xs:base64Binary` informazioni dell'elemento devono essere in formato canonico (vedere XSD-2, 3.2.16 base64Binary) e non devono contenere spazi vuoti che precedono, inline o seguono il contenuto diverso dallo spazio vuoto.

4. Creare una XOP SOAP envelope uguale alla SOAP envelope originale, sostituendo tuttavia al figlio di ogni voce di informazioni sugli elementi identificato nel passaggio precedente una voce di informazioni sugli elementi `xop:Include` costruito come segue:

    1. Trasformare i caratteri sostituiti in dati binari elaborandoli come dati codificati in base 64.

    2. Generare un valore univoco di intestazione Content-ID che soddisfi i requisiti R3133 e R3134.

    3. Generare un'intestazione MIME Content-Transfer-Encoding con il valore in binario.

    4. Se la voce di informazioni sugli elementi da ottimizzare (ovvero il padre [parent] della voce di informazioni sugli elementi `xop:Include` appena aggiunto) contiene una voce di informazioni sugli attributi `xmime:contentType`, generare un'intestazione Content-Type MIME con il valore dell'attributo `xmime:contentType`.

    5. Generare una nuova parte MIME binaria avente un contenuto formato dagli elementi seguenti: dati binari decodificati a partire dai caratteri sostituiti elaborati come dati in base 64, intestazione Content-ID come da passaggio 4b, intestazione Content- Transfer-Encoding come da passaggio 4c e intestazione Content-Type come da passaggio 4d, se presente.

    6. Aggiungere un attributo `href` all'elemento `xop:Include` con il valore cid: uri derivato dal valore dell'intestazione Content-ID generato nel passaggio 4b. Rimuovere i caratteri\<di inclusione " " e ">", eseguire `cid:`l'escape URL nella stringa rimanente e aggiungere il prefisso . La suddetta conversione, da eseguire in base ai documenti RFC1738 e RFC2396, deve riguardare almeno il set di caratteri seguente, ma può essere applicata anche ad altri caratteri.

        ```
        Hexadecimal 00-1F , 7F, 20, "<" | ">" | "#" | "%" | <">
        "{" | "}" | "|" | "\" | "^" | "[" | "]" | "`" | "~" | "^"
        ```

5. Creare una parte MIME radice contenente la XOP SOAP envelope ottenuta nel passaggio 4.

6. Scrivere le intestazioni HTTP, compresa l'intestazione Content-Type HTTP.

7. Scrivere il pacchetto MIME.

#### <a name="processing-mtom-messages"></a>Elaborazione di messaggi MTOM
L'elaborazione di un messaggio MTOM è l'esatto contrario del processo descritto nella sezione precedente "Generazione di messaggi MTOM":

1. Verificare che la parte MIME radice contenga l'elemento Content-Type `application/xop+xml`.

2. Costruire una SOAP envelope analizzando la parte MIME radice del pacchetto come documento XML. La codifica dei caratteri viene determinata in base al parametro `charset` del Content-Type della parte MIME radice.

3. Per ogni voce di informazioni sugli elementi della SOAP envelope costruita, che come unico membro della proprietà dei relativi figli [children] presenta una voce di informazioni sugli elementi `xop:Include`, eseguire quanto segue:

    1. Rimuovere il prefisso `cid:` ed eseguire la conversione URI inversa di tutte le sequenze escape (RFC 2396) contenute nel valore dell'attributo `@href` dell'elemento `xop:Include`. Racchiudere la stringa\<di risultato in " ", ">".

    2. Individuare la parte MIME contenente il valore dell'intestazione Content-ID corrispondente alla stringa ottenuta nel passaggio 3a.

    3. Sostituire la voce di informazioni sugli elementi `xop:Include` contenuto nella proprietà `children` di ogni elemento contenente le voci di informazioni sugli elementi che rappresentano la codifica canonica in base 64 (vedere XSD-2, 3.2.16 base64Binary) del corpo dell'entità della parte MIME identificato nel passaggio 3b. In pratica, sostituire la voce di informazioni sugli elementi `xop:Include` con i dati ricostruiti a partire dalla parte di pacchetto.

#### <a name="http-content-type-header"></a>Intestazione Content-Type HTTP
Di seguito è riportato un elenco di chiarimenti WCF per il formato dell'intestazione Content-Type HTTP di un messaggio con codifica MTOM SOAP 1.x derivato dai requisiti indicati nella specifica MTOM stessa e derivano da MTOM e RFC 2387.

- R4131: un'intestazione Content-Type HTTP deve contenere il valore multipart/related (che non fa distinzione fra maiuscole e minuscole) e i relativi parametri. Anche i nomi dei parametri non fanno distinzione tra maiuscole e minuscole. Inoltre, l'ordine dei parametri è irrilevante.

- La notazione BNF completa dell'intestazione Content-Type dei messaggi MIME è riportata nella sezione 5.1 del documento RFC 2045.

- R4132: un'intestazione Content-Type HTTP deve contenere un parametro di tipo avente il valore `application/xop+xml` compreso fra virgolette doppie.

Mentre il requisito di utilizzare le virgolette doppie non è esplicito in RFC 2387, il\@testo osserva che tutti i parametri multipart/tipo di supporto correlati molto probabilmente contengono caratteri riservati come " " o " " /" e pertanto devono essere racchiusi tra virgolette doppie.

- R4133: un'intestazione Content-Type HTTP deve presentare un parametro start con il valore dell'intestazione Content-ID della parte MIME contenente l'elemento SOAP 1.x Envelope, racchiuso fra virgolette doppie. Se tale parametro viene omesso, la SOAP 1.x envelope deve essere inclusa nella prima parte MIME.

- R4134: un'intestazione Content-Type HTTP di un messaggio con codifica SOAP 1.1 MTOM deve includere il parametro start-info con il valore text/xml racchiuso fra virgolette doppie.

- R4135: un'intestazione Content-Type HTTP di un messaggio con codifica SOAP 1.2 MTOM deve includere il parametro start-info con il valore `application/soap+xml` racchiuso fra virgolette doppie.

- R4136: un'intestazione Content-Type HTTP di un messaggio con codifica SOAP 1.x MTOM deve contenere un parametro boundary il cui valore (racchiuso fra virgolette doppie) corrisponda al formato BNF del limite MIME definito nella sezione 5.1.1 del documento RFC 2046.

    ```
    boundary := 0*69<bchars> bcharsnospace
    bchars := bcharsnospace / " "
    bcharsnospace :=    DIGIT / ALPHA / "'" / "(" / ")" / "+"
                        / "_" / "," / "-" / "." / "/" / ":" / "=" / "?"
    ```

     Esempi:

     CORRETTO

    ```
    Content-Type: multipart/related; type="application/xop+xml";start=" <part0@tempuri.org>";boundary="uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=1";start-info="text/xml"
    ```

     CORRETTO

    ```
    Content-Type: Multipart/Related; type="application/xop+xml";start-info="text/xml";boundary="uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=1"
    ```

     NON CORRETTO

    ```
    Content-Type: Multipart/Related; type=application/xop+xml;start=" <part0@tempuri.org>";start-info="text/xml";boundary="uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=1"
    ```

#### <a name="infoset-mime-part"></a>Parte MIME InfoSet
La SOAP 1.x envelope è incapsulata come parte radice del pacchetto XOP MIME e spesso viene detta "parte `infoset`".

- R4141: la SOAP 1.x envelope deve essere incapsulata come parte radice del pacchetto XOP MIME, detto "parte `infoset`", a cui si fa riferimento nell'intestazione Content-Type HTTP.

- R4142: la parte `Infoset` SOAP deve contenere le intestazioni MIME seguenti: `Content-ID`, `Content-Transfer-Encoding` e `Content-Type`.

Il formato dell'intestazione Content-ID è definito nel documento RFC 2045 come

```
"Content-ID" ":" msg-id
```

in cui l'elemento `msg-id` è definito nel documento RFC 2822 (che sostituisce il documento RFC 822, a cui si fa riferimento nel documento RFC 2045) come:

```
msg-id    =       [CFWS] "<" id-left "@" id-right ">" [CFWS]
```

ed è effettivamente un indirizzo\<e-mail racchiuso tra " " e ">". Il prefisso e il suffisso `[CFWS]` sono stati aggiunti nel documento RFC 2822 per contenere commenti e non devono essere utilizzati per mantenere l'interoperabilità.

R4143: il valore dell'intestazione Content-ID della parte MIME InfoSet deve attenersi alle regole di definizione dell'elemento `msg-id` indicate nel documento RFC 2822, omettendo le parti `[CFWS]` di prefisso e suffisso.

Un certo numero di implementazioni MIME relaxed\<requisiti per il valore racchiuso tra `absoluteURI` " "\<e ">" per essere un indirizzo di posta elettronica e utilizzato racchiuso tra " " , ">" oltre all'indirizzo di posta elettronica. Questa versione di WCF utilizza i valori dell'intestazione MIME Content-ID nel modulo:

```
Content-ID: <http://tempuri.org/0>
```

R4144: i processori MTOM devono accettare valori di intestazione Content-ID corrispondenti all'elemento `msg-id` con requisiti ridotti riportato di seguito.

```
msg-id-relaxed =     [CFWS] "<" (absoluteURI | mail-address) ">" [CFWS]
mail-address   =     id-left "@" id-right
```

Il protocollo MIME (RFC 2045) fornisce l'intestazione Content-Transfer-Encoding per comunicare la codifica del contenuto della parte MIME. L'impostazione predefinita dell'intestazione Content-Transfer-Encoding è una codifica a 7 bit, che tuttavia per la maggior parte dei messaggi SOAP risulta inadatta. Pertanto, tale intestazione è necessaria per garantire una maggiore interoperabilità:

- R4145: la parte SOAP InfoSet deve contenere l'intestazione Content-Transfer-Encoding.

- R4146: se la codifica dei caratteri della SOAP envelope è UTF-8, il valore dell'intestazione Content-Transfer-Encoding deve corrispondere a una codifica a 8 bit.

- R4147: se la codifica dei caratteri della SOAP envelope è UTF-16, il valore dell'intestazione Content-Transfer-Encoding deve corrispondere a una codifica binaria.

- Secondo quanto indicato nella sezione 5 di [XOP]:

- R4148: la parte del set di infoset SOAP1.1 deve contenere l'intestazione Content-Type con il tipo di supporto application/xop-xml e i parametri type, "text/xml" e charset

    ```
    Content-Type: application/xop+xml;
                  charset=utf-8;type="text/xml"
    ```

- R4149: la parte dell'Infoset SOAP 1.2 deve `application/xop+xml` contenere l'intestazione Content-Type con il tipo di supporto e i parametri type , "`application/soap+xml`e `charset`.

    ```
    Content-Type: application/xop+xml;
                  charset=utf-8;type="application/soap+xml"
    ```

     Benché XOP consenta di definire il parametro `charset` di `application/xop+xml` come facoltativo, tale parametro è necessario per l'interoperabilità, analogamente al requisito di BP 1.1 relativo al parametro `charset` del tipo di supporto `text/xml`.

- R41410: i parametri `type` e `charset` devono essere presenti nell'intestazione Content-Type della parte SOAP 1.x InfoSet.

#### <a name="wcf-endpoint-support-for-mtom"></a>Supporto degli endpoint WCF per MTOM
Lo scopo del meccanismo MTOM è codificare un messaggio SOAP allo scopo di ottimizzare i dati codificati in base 64. Segue un elenco di vincoli:

- R4151: qualsiasi voce di informazioni sugli elementi contenente dati con codifica in base 64 può essere ottimizzata.

- B4152: WCF ottimizza gli elementi di informazioni sugli elementi che contengono dati con codifica base64 e superano i 1024 byte di lunghezza.

Un endpoint WCF configurato per l'utilizzo di MTOM invierà sempre messaggi con codifica MTOM. Anche se nessuna parte soddisfa i criteri previsti, il messaggio viene comunque considerato come messaggio con codifica MTOM, serializzato come pacchetto MIME e avente una sola parte MIME contenente la SOAP envelope.

### <a name="ws-policy-assertion-for-mtom"></a>Asserzione di WS-Policy relativa a MTOM
WCF utilizza la seguente asserzione di criteri per indicare l'utilizzo Di MTOM per endpoint:WCF uses the following policy assertion to indicate MTOM usage by endpoint:

```xml
<wsoma:OptimizedMimeSerialization ... />
```

- R4211: l'asserzione di criteri precedente contiene un soggetto dei criteri di endpoint e impone che tutti i messaggi inviati all'endpoint e provenienti da quest'ultimo vengano ottimizzati tramite il meccanismo MTOM.

- B4212: se configurato per l'utilizzo dell'ottimizzazione MTOM, un endpoint WCF `wsdl:binding`aggiunge un'asserzione di criteri MTOM ai criteri associati al file corrispondente.

### <a name="composition-with-ws-security"></a>Integrazione con WS-Security
MTOM è un meccanismo `text/xml` di codifica simile a XML binario WCF. Il meccanismo MTOM può integrarsi perfettamente con il protocollo WS-Security e gli altri protocolli WS - *: un messaggio protetto mediante il protocollo WS-Security può infatti essere ottimizzato tramite MTOM.

### <a name="examples"></a>Esempi

#### <a name="wcf-soap-11-message-encoded-using-mtom"></a>Esempio di messaggio WCF SOAP 1.1 codificato tramite MTOM

```
POST http://131.107.72.15/Mtom/svc/service.svc/Soap11MtomUTF8 HTTP/1.1
SOAPAction: "http://xmlsoap.org/echoBinaryAsString"
Content-Type: multipart/related;type="application/xop+xml";
              start="<http://tempuri.org/0>";start-info="text/xml";
       boundary="uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=1"
Host: 131.107.72.15
Content-Length: 1501
--uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=1
Content-ID: <http://tempuri.org/0>
Content-Transfer-Encoding: 8bit
Content-Type: application/xop+xml;charset=utf-8;type="text/xml"
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Body>
    <EchoBinaryAsString xmlns="http://xmlsoap.org/Ping">
      <array>
        <xop:Include
         href="cid:http%3A%2F%2Ftempuri.org%2F1%2F632618206521093670"
         xmlns:xop="http://www.w3.org/2004/08/xop/include"/>
      </array>
    </EchoBinaryAsString>
  </s:Body>
</s:Envelope>
--uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=1
Content-ID: <http://tempuri.org/1/632618206521093670>
Content-Transfer-Encoding: binary
Content-Type: application/octet-stream
…Binary Content..
--uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=1
```

#### <a name="wcf-secure-soap-12-message-encoded-using-mtom"></a>Esempio di messaggio WCF Secure SOAP 1.2 codificato tramite MTOM
Questo esempio illustra la codifica tramite MTOM e SOAP 1.2 di un messaggio protetto mediante WS-Security. Le parti binarie identificate per la codifica sono il contenuto del token `BinarySecurityToken`, il valore `CipherValue` dell'elemento `EncryptedData` che corrisponde alla firma crittografata e il corpo crittografato. Si noti che l'oggetto `CipherValue` non è stato identificato per l'ottimizzazione `EncryptedKey` da WCF, perché la sua lunghezza è inferiore a 1024 byte.

```
POST http://131.107.72.15/Mtom/service.svc/Soap12MtomSecureSignEncrypt HTTP/1.1
Content-Type: multipart/related; type="application/xop+xml";
              start="<http://tempuri.org/0>";
            boundary="uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=3";
              start-info="application/soap+xml";
              action="http://xmlsoap.org/echoBinaryAsString"
Host: 131.107.72.15
Content-Length: 1941
--uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=3
Content-ID: <http://tempuri.org/0>
Content-Transfer-Encoding: 8bit
Content-Type: application/xop+xml;charset=utf-8;type="application/soap+xml"
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/" xmlns:u="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd">
  <s:Header>
    <o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd">
      <u:Timestamp u:Id="uuid-4d4ee765-5717-4d53-9ac9-99bddc07df6c-5">
        <u:Created>2005-09-09T06:57:32.488Z</u:Created>
        <u:Expires>2005-09-09T07:02:32.488Z</u:Expires>
      </u:Timestamp>
      <o:BinarySecurityToken u:Id="uuid-4d4ee765-5717-4d53-9ac9-99bddc07df6c-2" ValueType="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-x509-token-profile-1.0#X509v3" EncodingType="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-soap-message-security-1.0#Base64Binary">
        <xop:Include href="cid:http%3A%2F%2Ftempuri.org%2F1%2F632618206525089430" xmlns:xop="http://www.w3.org/2004/08/xop/include"/>
      </o:BinarySecurityToken>
      <e:EncryptedKey Id="_1" xmlns:e="http://www.w3.org/2001/04/xmlenc#">
        <e:EncryptionMethod Algorithm="http://www.w3.org/2001/04/xmlenc#rsa-oaep-mgf1p"/>
        <KeyInfo xmlns="http://www.w3.org/2000/09/xmldsig#">
          <o:SecurityTokenReference>
            <o:KeyIdentifier ValueType="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-x509-token-profile-1.0#X509SubjectKeyIdentifier">Xeg55vRyK3ZhAEhEf+YT0z986L0=</o:KeyIdentifier>
          </o:SecurityTokenReference>
        </KeyInfo>
        <e:CipherData>          <e:CipherValue>oQfpxwT8/SAGyZQzKE2b4yO6dXuQj7pwJ+5CGL3Rf7C06bQ5ttMoQ9GLJcQYkXTzin+WwHEgs5bj5ml9HKTW9QAU5JJ6lksdymmQvWP5ZtGPBVchO4sofEGoCKmBiZL/DYS/cnbzgnc/3a6NYnc10y2fWGaGLiqa00zijAw7o0Y=</e:CipherValue>
        </e:CipherData>
      </e:EncryptedKey>
      <c:DerivedKeyToken u:Id="_2" xmlns:c="http://schemas.xmlsoap.org/ws/2005/02/sc">
        <o:SecurityTokenReference>
          <o:Reference URI="#_1"/>
        </o:SecurityTokenReference>
        <c:Nonce>OrEPRX7fISIS4sXYWPMv3g==</c:Nonce>
      </c:DerivedKeyToken>
      <e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#">
        <e:DataReference URI="#_3"/>
        <e:DataReference URI="#_4"/>
      </e:ReferenceList>
      <e:EncryptedData Id="_4" Type="http://www.w3.org/2001/04/xmlenc#Element" xmlns:e="http://www.w3.org/2001/04/xmlenc#">
        <e:EncryptionMethod Algorithm="http://www.w3.org/2001/04/xmlenc#aes256-cbc"/>
        <KeyInfo xmlns="http://www.w3.org/2000/09/xmldsig#">
          <o:SecurityTokenReference>
            <o:Reference URI="#_2"/>
          </o:SecurityTokenReference>
        </KeyInfo>
        <e:CipherData>
          <e:CipherValue>
            <xop:Include href="cid:http%3A%2F%2Ftempuri.org%2F2%2F632618206525089430" xmlns:xop="http://www.w3.org/2004/08/xop/include"/>
          </e:CipherValue>
        </e:CipherData>
      </e:EncryptedData>
    </o:Security>
  </s:Header>
  <s:Body u:Id="_0">
    <e:EncryptedData Id="_3" Type="http://www.w3.org/2001/04/xmlenc#Content" xmlns:e="http://www.w3.org/2001/04/xmlenc#">
      <e:EncryptionMethod Algorithm="http://www.w3.org/2001/04/xmlenc#aes256-cbc"/>
      <KeyInfo xmlns="http://www.w3.org/2000/09/xmldsig#">
        <o:SecurityTokenReference xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd">
          <o:Reference URI="#_2"/>
        </o:SecurityTokenReference>
      </KeyInfo>
      <e:CipherData>
        <e:CipherValue>
          <xop:Include href="cid:http%3A%2F%2Ftempuri.org%2F3%2F632618206525089430" xmlns:xop="http://www.w3.org/2004/08/xop/include"/>
        </e:CipherValue>
      </e:CipherData>
    </e:EncryptedData>
  </s:Body>
</s:Envelope>
--uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=3
Content-ID: <http://tempuri.org/1/632618206525089430>
Content-Transfer-Encoding: binary
Content-Type: application/octet-stream
...Binary content of BinarySecurityToken - X509 Certificate...
--uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=3
Content-ID: <http://tempuri.org/2/632618206525089430>
Content-Transfer-Encoding: binary
Content-Type: application/octet-stream
...Binary serialization of the encrypted primary signature...
--uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=3
Content-ID: <http://tempuri.org/3/632618206525089430>
Content-Transfer-Encoding: binary
Content-Type: application/octet-stream
...Binary serialization of the encrypted Body...
--uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=3--
```
