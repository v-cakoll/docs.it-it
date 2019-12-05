---
title: Concetti fondamentali di Windows Communication Foundation
ms.date: 03/30/2017
helpviewer_keywords:
- WCF [WCF], concepts
- concepts [WCF]
- fundamentals [WCF]
- Windows Communication Foundation [WCF], concepts
ms.assetid: 3e7e0afd-7913-499d-bafb-eac7caacbc7a
ms.openlocfilehash: 360479a2ba17c4542d61a737856d23992296e276
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/04/2019
ms.locfileid: "74802308"
---
# <a name="fundamental-windows-communication-foundation-concepts"></a>Concetti fondamentali di Windows Communication Foundation

Nel presente documento viene fornita una panoramica generale dell'architettura Windows Communication Foundation (WCF) Il documento è concepito per spiegare i concetti principali e le modalità di interazione. Per un'esercitazione sulla creazione della versione più semplice di un servizio e di un client WCF, vedere [Introduzione esercitazione](getting-started-tutorial.md). Per informazioni sulla programmazione WCF, vedere [programmazione WCF di base](basic-wcf-programming.md).

## <a name="wcf-fundamentals"></a>Nozioni fondamentali su WCF

WCF è un runtime e un set di API per la creazione di sistemi che inviano messaggi tra servizi e client. La stessa infrastruttura e le stesse API vengono utilizzate per creare applicazioni che comunicano con le altre applicazioni nello stesso computer o su un sistema di un'altra società accessibile tramite Internet.

### <a name="messaging-and-endpoints"></a>Messaggistica ed endpoint

WCF si basa sul concetto di comunicazione basata su messaggi e qualsiasi elemento che può essere modellato come messaggio (ad esempio, una richiesta HTTP o un messaggio di Accodamento messaggi (noto anche come MSMQ)) può essere rappresentato in modo uniforme nel modello di programmazione. Questo consente un'API unificata su meccanismi di trasporto differenti.

Il modello distingue tra _i client_, ovvero le applicazioni che avviano la comunicazione e i _Servizi_, ovvero le applicazioni che attendono che i client possano comunicare con loro e rispondono a tale comunicazione. Una singola applicazione può comportarsi sia come client, sia come servizio. Per esempi, vedere [servizi duplex](./feature-details/duplex-services.md) e [rete peer-to-peer](./feature-details/peer-to-peer-networking.md).

I messaggi vengono inviati tra endpoint. Gli _endpoint_ sono punti in cui i messaggi vengono inviati o ricevuti (o entrambi) e definiscono tutte le informazioni necessarie per lo scambio di messaggi. Un servizio espone uno o più endpoint dell'applicazione (così come zero o più endpoint dell'infrastruttura) e il client genera un endpoint che è compatibile con uno degli endpoint del servizio.

Un _endpoint_ descrive in modo standard la modalità di invio dei messaggi, il modo in cui devono essere inviati e l'aspetto dei messaggi. Un servizio può esporre queste informazioni come metadati che i client possono elaborare per generare client WCF appropriati e _stack_di comunicazione.

### <a name="communication-protocols"></a>Protocolli di comunicazione

Un elemento obbligatorio dello stack di comunicazione è il _protocollo di trasporto_. I messaggi possono essere inviati tramite Intranet e Internet utilizzando trasporti comuni, ad esempio HTTP e TCP. Sono inclusi altri trasporti che supportano la comunicazione con applicazioni di Accodamento messaggi e nodi su una rete peer. È possibile aggiungere più meccanismi di trasporto utilizzando i punti di estensione incorporati di WCF.

Un altro elemento obbligatorio nello stack di comunicazione è la codifica che specifica come ogni messaggio viene formattato. WCF fornisce le codifiche seguenti:

- Codifica testo, una codifica interoperativa.

- Codifica Message Transmission Optimization Mechanism (MTOM), una modalità interoperativa per l'invio efficiente di dati binari non strutturati a e da un servizio.

- Codifica binaria per trasferimenti efficienti.

È possibile aggiungere più meccanismi di codifica, ad esempio una codifica di compressione, usando i punti di estensione incorporati di WCF.

### <a name="message-patterns"></a>Modelli dei messaggi

WCF supporta diversi modelli di messaggistica, tra cui la comunicazione richiesta-risposta, unidirezionale e duplex. Trasporti differenti supportano modelli di messaggistica differenti e in questo modo influenzano i tipi di interazioni supportati. Le API e il runtime WCF consentono inoltre di inviare messaggi in modo sicuro e affidabile.

## <a name="wcf-terms"></a>Termini WCF

Altri concetti e termini usati nella documentazione di WCF sono i seguenti:

**Messaggio**  
 Unità autonoma di dati che può essere costituita da varie parti, incluso corpo e intestazioni.

**Service**  
 Costrutto che espone uno o più endpoint che a loro volta espongono una o più operazioni del servizio.

**Endpoint**  
 Costrutto a cui vengono inviati o da cui vengono ricevuti (o entrambe le operazioni) i messaggi. È costituito da un percorso (un indirizzo) che definisce dove è possibile inviare i messaggi, una specifica del meccanismo di comunicazione (un'associazione) che descrive la modalità di invio dei messaggi e una definizione per un set di messaggi che possono essere inviati o ricevuti (o entrambi) a tale posizione (un contratto di servizio) che descrive il messaggio che può essere inviato.

Un servizio WCF viene esposto come una raccolta di endpoint.

**Endpoint applicazione**  
 Endpoint esposto dall'applicazione che corrisponde a un contratto di servizio implementato dall'applicazione.

**Endpoint infrastruttura**  
 Endpoint esposto dall'infrastruttura per agevolare la funzionalità necessaria o fornita dal servizio che non è correlata a un contratto di servizio. Un servizio, ad esempio, potrebbe avere un endpoint dell'infrastruttura che fornisce informazioni sui metadati.

**Address**  
 Specifica il percorso in cui vengono ricevuti i messaggi. Viene specificato come Uniform Resource Identifier (URI). La parte relativa allo schema URI denomina il meccanismo di trasporto da usare per raggiungere l'indirizzo, ad esempio HTTP e TCP. La parte gerarchica dell'URI contiene un percorso univoco il cui formato dipende dal meccanismo di trasporto.

L'indirizzo endpoint consente di creare indirizzi endpoint univoci per ogni endpoint in un servizio o, a determinate condizioni, di condividere un indirizzo tra gli endpoint. Nell'esempio seguente viene illustrato un indirizzo che utilizza il protocollo HTTPS con una porta non predefinita:

```http
HTTPS://cohowinery:8005/ServiceModelSamples/CalculatorService
```

**Binding**  
 Definisce le modalità di comunicazione tra un endpoint e gli elementi rimanenti. È costituita da un set di componenti denominati elementi di associazione "impilati" uno sopra l'altro per creare l'infrastruttura di comunicazione. Un'associazione definisce almeno il trasporto (ad esempio HTTP o TCP) e la codifica (ad esempio testo o binaria) utilizzati. Un'associazione può contenere elementi di associazione che specificano dettagli come i meccanismi di sicurezza usati per proteggere i messaggi o il modello del messaggio usato da un endpoint. Per ulteriori informazioni, vedere [configurazione dei servizi](configuring-services.md).

**Binding-elemento**  
 Rappresenta una particolare parte dell'associazione, ad esempio un trasporto, una codifica, un'implementazione di un protocollo a livello di infrastruttura (ad esempio WS-ReliableMessaging) o qualsiasi altro componente dello stack di comunicazione.

**Comportamenti**  
 Componente che controlla vari aspetti in fase di esecuzione di un servizio, di un endpoint, di una particolare operazione o di un client. I comportamenti sono raggruppati in base allo scopo. I comportamenti comuni influiscono globalmente su tutti gli endpoint, i comportamenti del servizio influiscono solo sugli aspetti relativi al servizio, i comportamenti dell'endpoint influiscono solo sulle proprietà relative all'endpoint e i comportamenti a livello di operazione influiscono su particolari operazioni. Un comportamento del servizio, ad esempio, l'azione di limitazione che specifica come un servizio reagisce quando un eccesso di messaggi minaccia di sovraccaricarne le funzionalità di gestione. Un comportamento dell'endpoint, invece, controlla solo gli aspetti pertinenti agli endpoint, ad esempio come e dove trovare una credenziale di sicurezza.

**Associazioni fornite dal sistema**  
 WCF include numerose associazioni fornite dal sistema. Si tratta di raccolte di elementi di associazione ottimizzati per scenari specifici. Ad esempio, il <xref:System.ServiceModel.WSHttpBinding> è progettato per l'interoperabilità con servizi che implementano varie specifiche WS-\*. Le associazioni predefinite consentono di risparmiare tempo presentando solo quelle opzioni che possono essere applicate correttamente allo scenario specifico. Se un'associazione predefinita non soddisfa i requisiti, è possibile crearne una personalizzata.

**Configurazione e codifica**  
 Il controllo di un'applicazione può essere eseguito tramite codifica, tramite configurazione o tramite una combinazione di entrambe. La configurazione presenta il vantaggio di consentire a qualcun altro oltre allo sviluppatore, ad esempio a un amministratore di rete, di impostare parametri del client e del servizio dopo che il codice è stato scritto e senza doverlo ricompilare. La configurazione non solo consente di impostare valori come gli indirizzi endpoint ma fornisce anche un maggior controllo consentendo di aggiungere endpoint, associazioni e comportamenti. La codifica consente allo sviluppatore di mantenere uno stretto controllo su tutti i componenti del servizio o del client ed eventuali impostazioni eseguite tramite la configurazione possono essere controllate e se necessario sottoposte a override dal codice.

**Operazione del servizio**  
 Procedura definita nel codice di un servizio che implementa la funzionalità per un'operazione. Questa operazione viene esposta ai client come metodi in un client WCF. Il metodo può restituire un valore e può accettare zero, uno o più argomenti e può non restituire alcuna risposta. Un'operazione, ad esempio, che funziona come un semplice "Hello" può essere utilizzata come notifica della presenza di un client e per iniziare una serie di operazioni.

**Contratto di servizio**  
 Collega più operazioni correlate in una sola unità funzionale. Il contratto può definire impostazioni a livello di servizio, ad esempio lo spazio dei nomi del servizio, un contratto callback corrispondente e altre impostazioni simili. Nella maggior parte dei casi, il contratto viene definito creando un'interfaccia nel linguaggio di programmazione selezionato e applicando l'attributo <xref:System.ServiceModel.ServiceContractAttribute> all'interfaccia. Il codice del servizio effettivo viene determinato implementando l'interfaccia.

**Contratto dell'operazione**  
 Un contratto dell'operazione definisce i parametri e il tipo restituito di un'operazione. Quando si crea un'interfaccia che definisce il contratto di servizio, si indica un contratto dell'operazione applicando l'attributo <xref:System.ServiceModel.OperationContractAttribute> a ogni definizione del metodo che fa parte del contratto. Le operazioni possono essere modellate in modo da accettare un solo messaggio e restituire un solo messaggio o in modo da accettare un set di tipi e restituire un tipo. Nel secondo caso, il sistema determinerà il formato per i messaggi che devono essere scambiati per quell'operazione.

**Contratto di messaggio**  
 Descrive il formato di un messaggio. Dichiara, ad esempio, se gli elementi del messaggio devono andare nelle intestazioni invece che nel corpo, quale livello di sicurezza deve essere applicato e a quali elementi del messaggio e così via.

**Contratto di errore**  
 Può essere associato a un'operazione del servizio per individuare errori che possono essere restituiti al chiamante. Un'operazione può avere zero o più errori associati. Si tratta di errori SOAP modellati come eccezioni nel modello di programmazione.

**Contratto dati**  
 Descrizioni nei metadati dei tipi di dati utilizzati da un servizio. In questo modo è consentito ad altri elementi di interoperare con il servizio. I tipi di dati possono essere utilizzati in qualsiasi parte di un messaggio, come parametri o tipi restituiti. Se il servizio usa solo tipi semplici, non è necessario usare esplicitamente i contratti dati.

**Hosting**  
 Un servizio deve essere ospitato in un processo. Un _host_ è un'applicazione che controlla la durata del servizio. I servizi possono essere indipendenti o gestiti da un processo di hosting esistente.

**Servizio self-hosted**  
 Servizio in esecuzione all'interno di un'applicazione di processo creata dallo sviluppatore. Lo sviluppatore ne controlla la durata, imposta le proprietà del servizio, apre il servizio (impostandolo in modalità di ascolto) e chiude il servizio.

**Processo di hosting**  
 Applicazione progettata per ospitare servizi, inclusi Internet Information Services (IIS), Windows Activation Services (WAS) e servizi per Windows. In questi scenari di hosting, l'host controlla la durata del servizio. Ad esempio, tramite IIS è possibile configurare una directory virtuale che contiene l'assembly del servizio e il file di configurazione. Quando un messaggio viene ricevuto, IIS avvia il servizio e ne controlla la durata.

**Creazione di istanze**  
 Un servizio è dotato di un modello di istanze. Sono presenti tre modelli di istanze, ovvero singolo, nel quale un solo oggetto CLR provvede a tutti i client, per chiamata, nel quale viene creato un nuovo oggetto CLR per gestire ogni chiamata del client, e per sessione, nel quale viene creato un set di oggetti CLR, uno per ogni sessione separata. La scelta di un modello di istanze dipende dai requisiti dell'applicazione e dal modello di utilizzo previsto del servizio.

**Applicazione client**  
 Programma che scambia messaggi con uno o più endpoint. L'applicazione client inizia creando un'istanza di un client WCF e chiamando metodi del client WCF. È importante notare che una singola applicazione può essere sia un client che un servizio.

**Canale**  
 Implementazione concreta di un elemento di associazione. L'associazione rappresenta la configurazione e il canale è l'implementazione associata a tale configurazione. Per ogni elemento di associazione è pertanto presente un canale associato. I canali si dispongono uno sopra l'altro per creare l'implementazione concreta dell'associazione, ovvero lo stack dei canali.

**Client WCF**  
 Costrutto dell'applicazione client che espone le operazioni del servizio come metodi (nel linguaggio di programmazione .NET Framework di propria scelta, ad esempio Visual Basic o C#oggetto visivo). Qualsiasi applicazione può ospitare un client WCF, inclusa un'applicazione che ospita un servizio. È pertanto possibile creare un servizio che include client WCF di altri servizi.

Un client WCF può essere generato automaticamente utilizzando lo [strumento ServiceModel Metadata Utility Tool (Svcutil. exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) e puntando a un servizio in esecuzione che pubblica metadati.

**Metadati**  
 In un servizio, i metadati descrivono le caratteristiche del servizio che un'entità esterna deve comprendere per comunicare con il servizio. I metadati possono essere utilizzati dallo [strumento ServiceModel Metadata Utility Tool (Svcutil. exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) per generare un client WCF e una configurazione associata che può essere utilizzata da un'applicazione client per interagire con il servizio.

I metadati esposti dal servizio includono documenti di XML Schema che definiscono il contratto di dati del servizio e documenti WSDL che descrivono i metodi del servizio.

Se abilitati, i metadati del servizio vengono generati automaticamente da WCF tramite il controllo del servizio e dei relativi endpoint. Per pubblicare metadati da un servizio, è necessario abilitare esplicitamente il comportamento dei metadati.

**Security**  
 In WCF include riservatezza (crittografia dei messaggi per impedire l'intercettazione), integrità (mezzi per il rilevamento di manomissioni del messaggio), autenticazione (mezzi per la convalida di server e client) e autorizzazione (controllo di accesso a risorse). Queste funzioni vengono fornite sfruttando i meccanismi di sicurezza esistenti, ad esempio TLS su HTTP (noto anche come HTTPS), oppure implementando una o più delle diverse specifiche di sicurezza WS-\*.

**Modalità di sicurezza del trasporto**  
 Specifica che la riservatezza, l'integrità e l'autenticazione vengono fornite da meccanismi a livello del trasporto, ad esempio HTTPS. In caso di uso di un trasporto come HTTPS, questa modalità presenta il vantaggio di essere efficiente in termini di prestazioni e di essere ben compresa grazie alla sua prevalenza su Internet. Lo svantaggio consiste nel fatto che questo tipo di sicurezza viene applicato separatamente su ogni hop nel percorso di comunicazione, rendendo quest'ultima vulnerabile a un attacco di tipo "man in the middle".

**Modalità di sicurezza del messaggio**  
 Specifica che la sicurezza viene fornita implementando una o più specifiche di sicurezza, ad esempio la specifica denominata [Web Services Security: sicurezza dei messaggi SOAP](http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-soap-message-security-1.0.pdf). Ogni messaggio contiene i meccanismi necessari a fornire sicurezza durante il transito e a consentire ai destinatari di rilevare manomissioni e decrittografare i messaggi. A tale scopo, la sicurezza viene incapsulata all'interno di ogni messaggio, fornendo sicurezza end-to-end tra più hop. Poiché le informazioni sulla sicurezza diventano parte del messaggio, è anche possibile includere più tipi di credenziali con il messaggio (queste sono denominate _attestazioni_). Questo approccio presenta inoltre il vantaggio di consentire al messaggio di viaggiare in modo protetto su qualsiasi trasporto, anche se tra l'origine e la destinazione ne esistono diversi. Lo svantaggio di questo approccio consiste nella complessità dei meccanismi di crittografia adottati, con conseguenti implicazioni sulle prestazioni.

**Trasporto con modalità di sicurezza delle credenziali del messaggio**  
 Specifica l'utilizzo del livello trasporto per fornire riservatezza, autenticazione e integrità dei messaggi, mentre ogni messaggio può contenere più credenziali (attestazioni) richieste dai destinatari del messaggio.

**WS-\***  
 Abbreviazione per il set in continua crescita di specifiche Web Service (WS), ad esempio WS-Security, WS-ReliableMessaging e così via, che sono implementate in WCF.

## <a name="see-also"></a>Vedere anche

- [Informazioni su Windows Communication Foundation](whats-wcf.md)
- [Architettura di Windows Communication Foundation](architecture.md)
