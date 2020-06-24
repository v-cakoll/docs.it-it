---
title: Scelta di un trasporto
description: 'Informazioni sui criteri per la scelta tra i trasporti principali offerti da WCF: HTTP, TCP e named pipe.'
ms.date: 03/30/2017
helpviewer_keywords:
- choosing transports [WCF]
ms.assetid: b169462b-f7b6-4cf4-9fca-d306909ee8bf
ms.openlocfilehash: e1a92203de25aa399316eea91a758802768442a0
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85247494"
---
# <a name="choosing-a-transport"></a>Scelta di un trasporto
In questo argomento vengono illustrati i criteri per la scelta tra i tre trasporti principali inclusi in Windows Communication Foundation (WCF): HTTP, TCP e named pipe. WCF include inoltre un trasporto di Accodamento messaggi (noto anche come MSMQ), ma questo documento non copre l'accodamento dei messaggi.  
  
 Il modello di programmazione WCF separa le operazioni dell'endpoint (espresse in un contratto di servizio) dal meccanismo di trasporto che connette due endpoint. In questo modo è possibile decidere come esporre i servizi sulla rete.  
  
 In WCF è possibile specificare come trasferire i dati attraverso una rete tra endpoint usando un' *associazione*, costituita da una sequenza di *elementi di associazione*. Per trasporto si intende un elemento di associazione del trasporto che fa parte dell'associazione. Un'associazione include elementi di associazione del protocollo facoltativi, ad esempio la protezione, un elemento di associazione del codificatore dei messaggi obbligatorio e un elemento di associazione del trasporto obbligatorio. Un trasporto invia o riceve il messaggio in formato serializzato da o verso un'altra applicazione.  
  
 Se è necessario connettersi a un client o un server esistente, la scelta di utilizzare un particolare trasporto potrebbe essere obbligata. Tuttavia, i servizi WCF possono essere resi accessibili tramite più endpoint, ognuno con un trasporto diverso. Quando un singolo trasporto non include i destinatari desiderati per il servizio, è consigliabile esporre il servizio su più endpoint. Le applicazioni client possono quindi utilizzare l'endpoint più appropriato.  
  
 Dopo avere scelto un trasporto, è necessario selezionare un'associazione che lo utilizzi. È possibile scegliere un'associazione fornita dal sistema (vedere [associazioni fornite dal sistema](../system-provided-bindings.md)) oppure creare un'associazione personalizzata (vedere [binding personalizzati](../extending/custom-bindings.md)). È inoltre possibile creare un'associazione. Per ulteriori informazioni, vedere [creazione di associazioni definite dall'utente](../extending/creating-user-defined-bindings.md).  
  
## <a name="advantages-of-each-transport"></a>Vantaggi di ogni trasporto  
 Contenuto della sezione vengono illustrati i motivi principali per cui scegliere uno dei tre trasporti principali, incluso un grafico dettagliato per agevolare la scelta.  
  
### <a name="when-to-use-http-transport"></a>Quando utilizzare il trasporto HTTP  
 HTTP è un protocollo di richiesta/risposta tra client e server. L'ambito di applicazione più comune è costituito da client del browser Web che comunicano con un server Web. Il client invia una richiesta a un server che è in ascolto dei messaggi di richiesta del client. Quando il server riceve una richiesta, restituisce una risposta che contiene lo stato della richiesta. Se la richiesta ha esito positivo, vengono restituiti dati facoltativi, ad esempio una pagina Web, un messaggio di errore o altre informazioni. Per ulteriori informazioni sul protocollo HTTP, vedere [http-Hypertext Transfer Protocol](https://www.w3.org/Protocols/).  
  
 Il protocollo HTTP non è basato sulla connessione; quando la risposta è stata inviata, lo stato non viene gestito. Per gestire transazioni a più pagine, l'applicazione deve rendere persistente lo stato necessario.  
  
 In WCF, l'associazione di trasporto HTTP è ottimizzata per l'interoperabilità con sistemi legacy non WCF. Se tutte le parti che comunicano utilizzano WCF, le associazioni basate su TCP o sulle named pipe sono più veloci. Per altre informazioni, vedere <xref:System.ServiceModel.NetTcpBinding> e <xref:System.ServiceModel.NetNamedPipeBinding>.  
  
### <a name="when-to-use-the-tcp-transport"></a>Quando utilizzare il trasporto TCP  
 TCP è un servizio di recapito basato sulla connessione e orientato al flusso con rilevamento e correzione degli errori end-to-end. *Basato sulla connessione* significa che viene stabilita una sessione di comunicazione tra gli host prima di scambiare dati. Un host è qualsiasi dispositivo su una rete TCP/IP identificato da un indirizzo IP logico.  
  
 TCP garantisce affidabilità nel recapito dei dati e facilità d'uso. In particolare, TCP segnala al mittente il recapito del pacchetto, garantisce che i pacchetti vengano recapitati nello stesso ordine nel quale sono stati inviati, ritrasmette i pacchetti perduti e assicura che i pacchetti di dati non vengano duplicati. Si noti che questo recapito affidabile si applica tra due nodi TCP/IP e non è uguale a *WS-ReliableMessaging*, che si applica tra gli endpoint, indipendentemente dal numero di nodi intermedi che possono includere.  
  
 Il trasporto TCP WCF è ottimizzato per lo scenario in cui entrambe le estremità della comunicazione utilizzano WCF. Questo binding è il binding WCF più veloce per gli scenari che comportano la comunicazione tra computer diversi. Gli scambi di messaggi utilizzano <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement> per ottimizzare il trasferimento del messaggio. TCP supporta la comunicazione duplex e pertanto può essere utilizzato per implementare contratti duplex, anche se il client è basato su NAT (Network Address Translation).  
  
### <a name="when-to-use-the-named-pipe-transport"></a>Quando utilizzare il trasporto di named pipe  
 Una named pipe è un oggetto nel kernel del sistema operativo Windows, ad esempio una sezione della memoria condivisa che i processi possono utilizzare per la comunicazione. Le named pipe hanno un nome e possono essere utilizzate per la comunicazione unidirezionale o duplex tra processi in un singolo computer.  
  
 Quando è richiesta la comunicazione tra applicazioni WCF diverse in un singolo computer e si desidera impedire la comunicazione da un altro computer, utilizzare il trasporto named pipe. Un vincolo ulteriore consiste nella possibilità di limitare i processi in esecuzione dal desktop remoto di Windows alla stessa sessione di Connessione desktop remoto, a meno che dispongano di privilegi elevati.  
  
> [!WARNING]
> Quando si utilizza il trasporto della named pipe con una prenotazione URL debole con caratteri jolly su più siti ospitati in IIS, può verificarsi un errore nel servizio di attivazione 'NetPipeActivator' del protocollo 'net.pipe' durante il tentativo di restare in ascolto sul sito '2'. Il protocollo verrà disabilitato temporaneamente per il sito. Per ulteriori dettagli, vedere il messaggio di eccezione. URL: WeakWildcard: NET. pipe:/ \<machine name> /Status: ConflictingRegistration Exception: nome processo: SMSvcHost Process ID: 1076 \  
  
## <a name="decision-points-for-choosing-a-transport"></a>Fattori essenziali per la scelta di un trasporto  
 Nella tabella seguente vengono illustrati i fattori essenziali utilizzati per scegliere un trasporto. È necessario considerare qualsiasi attributo e trasporto aggiuntivo applicabile all'applicazione. Identificare gli attributi che sono importanti per l'applicazione, identificare i trasporti che possono essere agevolmente associati a ognuno degli attributi e quindi selezionare i trasporti che funzionano meglio con gli attributi utilizzati.  
  
|Attributo|Descrizione|Trasporti consigliati|  
|---------------|-----------------|------------------------|  
|Diagnostica|La diagnostica consente di rilevare automaticamente problemi di connettività del trasporto. Tutti i trasporti supportano la possibilità di restituire informazioni sull'errore che descrivano le condizioni di connettività. Tuttavia, WCF non include strumenti di diagnostica per l'analisi dei problemi di rete.|nessuno|  
|Hosting|Tutti gli endpoint WCF devono essere ospitati all'interno di un'applicazione. IIS 6,0 e versioni precedenti supportano solo le applicazioni che utilizzano il trasporto HTTP. In Windows Vista è stato aggiunto il supporto per l'hosting di tutti i trasporti WCF, tra cui TCP e named pipe. Per ulteriori informazioni, vedere [hosting in Internet Information Services](hosting-in-internet-information-services.md) e [hosting nel servizio di attivazione dei processi di Windows](hosting-in-windows-process-activation-service.md).|HTTP|  
|Ispezione|L'ispezione è la possibilità di estrarre ed elaborare informazioni dai messaggi durante la trasmissione. Il protocollo HTTP separa le informazioni di routing e di controllo dai dati, semplificando la creazione di strumenti in grado di ispezionare e analizzare i messaggi. I tipi di trasporto facilmente controllabili possono richiedere anche minore capacità di elaborazione nei dispositivi di rete. La possibilità di controllare i messaggi dipende dal livello di sicurezza utilizzato.|HTTP|  
|Latenza|La latenza è il periodo minimo di tempo richiesto per completare un scambio di messaggi. Tutte le operazioni di rete sono caratterizzate da una latenza maggiore o minore a seconda del trasporto scelto. L'uso della comunicazione duplex o unidirezionale con un trasporto il cui modello di scambio messaggi nativo è richiesta-risposta, ad esempio HTTP, può provocare una latenza aggiuntiva a causa della correlazione forzata dei messaggi. In questa situazione, è consigliabile usare un trasporto il cui modello di scambio messaggi nativo sia duplex, ad esempio TCP.|TCP, Named<br /><br /> Pipe|  
|Copertura|La portata di un trasporto indica la capacità di connessione del trasporto con altri sistemi. Il trasporto di named pipe ha una portata molto limitata, in quanto può connettersi solo a servizi che sono in esecuzione nello stesso computer. I trasporti TCP e HTTP hanno entrambi una portata eccellente e possono penetrare alcune configurazioni basate su NAT e firewall. Per ulteriori informazioni, vedere [utilizzo di NAT e firewall](working-with-nats-and-firewalls.md).|HTTP, TCP|  
|Sicurezza|La protezione è la possibilità di proteggere i messaggi durante il trasferimento garantendo riservatezza, integrità o autenticazione. La riservatezza garantisce che un messaggio non possa essere esaminato, l'integrità protegge un messaggio dalle modifiche e l'autenticazione fornisce garanzie sul mittente o il destinatario del messaggio.<br /><br /> WCF supporta la sicurezza del trasferimento a livello di messaggio e di trasporto. La protezione dei messaggi si integra con un trasporto se questo supporta una modalità di trasferimento con memorizzazione nel buffer. Il supporto della protezione del trasporto varia a seconda del trasporto scelto. I trasporti HTTP, TCP e named pipe sono a un livello di parità ragionevole nel supporto della protezione del trasporto.|Tutti|  
|Velocità effettiva|La velocità effettiva misura la quantità di dati che possono essere trasmessi ed elaborati in uno specifico periodo di tempo. Analogamente alla latenza, il trasporto scelto può influire sulla velocità effettiva per le operazioni del servizio. Per ottimizzare la velocità effettiva di un trasporto, è necessario ottimizzare sia il sovraccarico legato alla trasmissione del contenuto che il tempo trascorso in attesa del completamento dello scambio del messaggio. Sia il trasporti TCP che named pipe aggiungono un sovraccarico minimo al corpo del messaggio e supportano una forma duplex nativa che riduce l'attesa per le risposte del messaggio.|TCP, named pipe|  
|Strumenti|Gli strumenti rappresentano la possibilità che un protocollo supporti applicazioni di terze parti per lo sviluppo, la diagnosi, l'hosting e altre attività. Lo sviluppo di strumenti e software da utilizzare con il protocollo HTTP comporta un investimento notevole.|HTTP|  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.BasicHttpBinding>
- <xref:System.ServiceModel.WSHttpBinding>
- <xref:System.ServiceModel.WSDualHttpBinding>
- <xref:System.ServiceModel.WSFederationHttpBinding>
- <xref:System.ServiceModel.Channels.HttpTransportBindingElement>
- <xref:System.ServiceModel.NetTcpBinding>
- <xref:System.ServiceModel.Channels.TcpTransportBindingElement>
- <xref:System.ServiceModel.NetNamedPipeBinding>
- <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>
- [Associazioni](bindings.md)
- [Associazioni fornite dal sistema](../system-provided-bindings.md)
- [Creazione di associazioni definite dall'utente](../extending/creating-user-defined-bindings.md)
