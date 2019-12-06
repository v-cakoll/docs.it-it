---
title: Mapping fra gli endpoint di servizio e l'indirizzamento delle code
ms.date: 03/30/2017
ms.assetid: 7d2d59d7-f08b-44ed-bd31-913908b83d97
ms.openlocfilehash: 6bdd3b0966f85ff456e0e2ed0b6da773046201dc
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837987"
---
# <a name="service-endpoints-and-queue-addressing"></a>Mapping fra gli endpoint di servizio e l'indirizzamento delle code
Questo argomento descrive come i client indirizzano i servizi che leggono da code e il mapping fra gli endpoint di servizio e le code. Come promemoria, nella figura seguente viene illustrata la distribuzione dell'applicazione in coda Windows Communication Foundation (WCF) classica.  
  
 ![Diagramma dell'applicazione in coda](../../../../docs/framework/wcf/feature-details/media/distributed-queue-figure.jpg "Distributed-Queue-Figure")  
  
 Per inviare il messaggio al servizio, il client indirizza il messaggio alla coda di destinazione. Per leggere i messaggi da questa coda, il servizio imposta il proprio indirizzo di attesa sulla coda di destinazione. L'indirizzamento in WCF è Uniform Resource Identifier basato su (URI), mentre i nomi delle code di Accodamento messaggi (MSMQ) non sono basati su URI. È pertanto essenziale comprendere come indirizzare le code create in MSMQ tramite WCF.  
  
## <a name="msmq-addressing"></a>Indirizzamento di MSMQ  
 Nel sistema MSMQ le code vengono identificate tramite nomi di percorso e di formato. I percorsi specificano un nome host e un elemento `QueueName`. Fra il nome host e l'elemento `Private$` è inoltre previsto l'elemento facoltativo `QueueName`. Tale elemento indica una coda privata non pubblicata nel servizio di directory Active Directory.  
  
 Viene eseguito il mapping dei nomi di percorso a "FormatNames" per determinare altri aspetti dell'indirizzo, tra cui routing e il protocollo di trasferimento del gestore code. Questo servizio supporta due protocolli di trasferimento: il protocollo MSMQ nativo e il protocollo SOAP Reliable Messaging Protocol (SRMP).  
  
 Per ulteriori informazioni sui nomi di percorso e di formato MSMQ, vedere [informazioni su Accodamento messaggi](https://go.microsoft.com/fwlink/?LinkId=94837).  
  
## <a name="netmsmqbinding-and-service-addressing"></a>Associazione NetMsmqBinding e indirizzamento del servizio  
 Quando si indirizza un messaggio a un servizio, lo schema contenuto nell'URI viene scelto in base al trasporto utilizzato per le comunicazioni. Ogni trasporto in WCF ha uno schema univoco. Lo schema deve riflettere le caratteristiche del trasporto utilizzato per le comunicazioni, ad esempio net.tcp, net.pipe, HTTP e così via.  
  
 Il trasporto accodato MSMQ in WCF espone uno schema net. MSMQ. Tutti i messaggi indirizzati utilizzando lo schema net.msmq vengono inviati utilizzando l'associazione `NetMsmqBinding` sul canale del trasporto in coda del sistema MSMQ.  
  
 L'indirizzamento di una coda in WCF si basa sul modello seguente:  
  
 NET. MSMQ://\<*nome-host*>/[private/] \<*nome-coda*>  
  
 dove:  
  
- \<*nome host-* > è il nome del computer che ospita la coda di destinazione.  
  
- L'elemento facoltativo [private] viene utilizzato quando si indirizza una coda di destinazione privata. Per indirizzare una coda pubblica è necessario non specificare [private]. Si noti che, a differenza dei percorsi MSMQ, non esiste alcun "$" nel form URI WCF.  
  
- \<*queue-name*> è il nome della coda. Il nome della coda può riferirsi anche a una coda secondaria. Pertanto, \<nome- *coda*> = \<*nome della coda*> [; *nome-coda secondaria*].  
  
 Esempio 1: per indirizzare una coda privata PurchaseOrders ospitata nel computer abc presso adatum.com, l'URI da utilizzare è net.msmq://abc.adatum.com/private/PurchaseOrders.  
  
 Esempio 2: per indirizzare una coda pubblica AccountsPayable ospitata nel computer def presso adatum.com, l'URI da utilizzare è net.msmq://def.adatum.com/AccountsPayable.  
  
 L'indirizzo della coda viene utilizzato dal listener come URI di ascolto da cui leggere i messaggi. In altre parole, l'indirizzo della coda è equivalente alla porta di ascolto del socket TCP.  
  
 Un endpoint che legge da una coda deve specificare l'indirizzo della coda utilizzando lo stesso schema specificato in precedenza per l'apertura di ServiceHost. Per esempi, vedere [associazione net MSMQ](../../../../docs/framework/wcf/samples/net-msmq-binding.md).  
  
### <a name="multiple-contracts-in-a-queue"></a>Contratti multipli in una coda  
 I messaggi di una coda possono implementare più contratti. In questo caso, per leggere ed elaborare tutti i messaggi, è essenziale applicare uno degli approcci seguenti:  
  
- Specificare un endpoint per un servizio che implementa tutti i contratti. Si tratta dell'approccio consigliato.  
  
- Specificare più endpoint con contratti diversi, garantendo tuttavia che tutti gli endpoint utilizzino lo stesso oggetto `NetMsmqBinding`. La logica di distribuzione di ServiceModel utilizza una message pump che legge i messaggi dal canale di trasporto e quindi li distribuisce. Questa procedura, una volta completata, consente di ottenere il demultiplexing dei messaggi verso vari endpoint in base al contratto. Una message pump viene creata per una coppia URI di ascolto/associazione. L'indirizzo della coda viene utilizzato dal listener in coda come URI di ascolto. Se si configurano tutti gli endpoint in modo da utilizzare lo stesso oggetto di associazione è possibile garantire che il sistema utilizzi un'unica message pump per leggere il messaggio e quindi eseguirne il demultiplexing verso gli endpoint appropriati in base al contratto.  
  
### <a name="srmp-messaging"></a>Messaggistica SRMP  
 Come già indicato, è possibile utilizzare il protocollo SRMP per i trasferimenti fra code. Questo approccio in genere viene utilizzato quando un trasporto HTTP trasmette i messaggi fra la coda di trasmissione e la coda di destinazione.  
  
 Per utilizzare il protocollo di trasferimento SRMP è necessario indirizzare i messaggi tramite lo schema degli URI net.msmq, come già menzionato, nonché impostare la proprietà `QueueTransferProtocol` dell'associazione `NetMsmqBinding` su SRMP o su SRMP protetto.  
  
 La specifica della proprietà `QueueTransferProtocol` è una funzionalità di solo invio e rappresenta un'indicazione del tipo di protocollo di trasferimento fra code da utilizzare nel client.  
  
### <a name="using-active-directory"></a>Utilizzo di Active Directory  
 MSMQ supporta l'integrazione con Active Directory. Quando si installa MSMQ con l'opzione di integrazione con Active Directory, il computer deve appartenere a un dominio Windows. Active Directory viene utilizzata per pubblicare le code per l'individuazione; tali code sono denominate *code pubbliche*. Quando si indirizza una coda, il relativo indirizzo può essere risolto utilizzando Active Directory. Questo approccio è analogo all'utilizzo di Domain Name System (DNS) per risolvere l'indirizzo IP di un nome di rete. La proprietà `UseActiveDirectory` dell'associazione `NetMsmqBinding` è un valore booleano che indica se il canale in coda deve utilizzare Active Directory per risolvere l'URI della coda. Per impostazione predefinita, questa proprietà è impostata su `false`. Se la proprietà `UseActiveDirectory` è impostata su `true`, il canale in coda utilizza Active Directory per convertire l'URI net.msmq:// nel nome di formato.  
  
 La proprietà `UseActiveDirectory` è rilevante solo per i client che stanno inviando un messaggio, in quanto tale proprietà viene utilizzata per risolvere l'indirizzo della coda durante la fase di invio dei messaggi.  
  
### <a name="mapping-netmsmq-uri-to-message-queuing-format-names"></a>Mapping fra gli URI net.msmq e i nomi di formato di MSMQ  
 Il canale in coda gestisce il mapping fra i nomi degli URI net.msmq forniti al canale e i nomi di formato di MSMQ. La tabella seguente riepiloga le regole di mapping.  
  
|Indirizzo di coda basato sugli URI WCF|Impostazione della proprietà UseActiveDirectory|Impostazione della proprietà QueueTransferProtocol|Nomi di formato di MSMQ risultanti|  
|----------------------------------|-----------------------------------|--------------------------------------|---------------------------------|  
|Net.msmq://\<machine-name>/private/abc|False (valore predefinito)|Native (impost. predef.)|DIRECT=OS:nome-computer\private$\abc|  
|Net.msmq://\<machine-name>/private/abc|Falso|SRMP|DIRECT =http://machine/msmq/private $/ABC|  
|Net.msmq://\<machine-name>/private/abc|True|Nativo|PUBLIC=guid (GUID della coda)|  
  
### <a name="reading-messages-from-the-dead-letter-queue-or-the-poison-message-queue"></a>Lettura dei messaggi dalla coda dei messaggi non recapitabili o dalla coda dei messaggi non elaborabili  
 Per leggere i messaggi da una coda di messaggi non elaborabili che è una coda secondaria della coda di destinazione, aprire l'elemento `ServiceHost` con l'indirizzo della coda secondaria.  
  
 Esempio: un servizio che legge dalla coda di messaggi non elaborabili della coda privata PurchaseOrders nel computer locale presenta l'indirizzo net.msmq://localhost/private/PurchaseOrders;poison.  
  
 Per leggere messaggi da una coda transazionale di sistema di messaggi non recapitabili, l'URI deve presentarsi nel formato: net.msmq://localhost/system$;DeadXact.  
  
 Per leggere messaggi da una coda non transazionale di sistema di messaggi non recapitabili, l'URI deve presentarsi nel formato: net.msmq://localhost/system$;DeadLetter.  
  
 Quando si utilizza una coda di messaggi non recapitabili personalizzata, si noti che questa coda deve trovarsi nel computer locale. Ne consegue che l'URI della coda deve attenersi al formato:  
  
 NET. MSMQ://localhost/[private/] \<> *Custom-Dead-Letter-Queue-Name*.  
  
 Un servizio WCF verifica che tutti i messaggi ricevuti siano stati rivolti alla coda specifica su cui è in ascolto. Se un messaggio viene rilevato in una coda a cui non era destinato, tale messaggio non viene elaborato dal servizio. Si tratta di un problema che i servizi in attesa di una coda di messaggi non recapitabili devono affrontare, poiché questo tipo di coda contiene messaggi che in realtà erano destinati altrove. Per leggere i messaggi di una coda di messaggi non recapitabili o non elaborabili occorre utilizzare un comportamento `ServiceBehavior` con il parametro <xref:System.ServiceModel.AddressFilterMode.Any>. Per un esempio, vedere Code di messaggi non [recapitabili](../../../../docs/framework/wcf/samples/dead-letter-queues.md).  
  
## <a name="msmqintegrationbinding-and-service-addressing"></a>Associazione MsmqIntegrationBinding e indirizzamento del servizio  
 L'associazione `MsmqIntegrationBinding` viene utilizzata per comunicare con le applicazioni MSMQ tradizionali. Per semplificare l'interazione con un'applicazione MSMQ esistente, WCF supporta solo l'indirizzamento dei nomi di formato. Di conseguenza, i messaggi inviati tramite questa associazione devono attenersi allo schema degli URI seguente:  
  
 msmq.formatname:\<*MSMQ-format-name*>>  
  
 MSMQ-format-name ha il formato specificato da MSMQ in [About Accodamento messaggi](https://go.microsoft.com/fwlink/?LinkId=94837).  
  
 Si noti che quando si ricevono messaggi da una coda tramite l'associazione `MsmqIntegrationBinding` è possibile utilizzare soltanto i nomi di formato Direct e, se è stata scelta l'opzione di integrazione con Active Directory, i nomi di formato pubblici e privati. È tuttavia consigliabile utilizzare i nomi di formato Direct. In Windows Vista, ad esempio, l'utilizzo di qualsiasi altro nome di formato causa un errore, in quanto il sistema tenta di aprire una coda secondaria, che può essere aperta solo con nomi di formato diretti.  
  
 Quando si esegue l'indirizzamento tramite il protocollo SRMP usando l'associazione `MsmqIntegrationBinding` non occorre aggiungere /msmq/ nel nome di formato Direct per consentire ai servizi Internet Information Services (IIS) di eseguire la distribuzione. Ad esempio: quando si indirizza una coda ABC usando il protocollo SRMP, anziché DIRECT =http://adatum.com/msmq/private $/ABC, è consigliabile usare DIRECT =http://adatum.com/private $/ABC.  
  
 Si noti che non è possibile utilizzare l'indirizzamento net.msmq:// con l'associazione `MsmqIntegrationBinding`. Poiché `MsmqIntegrationBinding` supporta l'indirizzamento dei nomi di formato MSMQ in formato libero, è possibile utilizzare un servizio WCF che utilizza questa associazione per utilizzare le funzionalità della lista di distribuzione e multicast in MSMQ. Un'eccezione è la specifica dell'elemento `CustomDeadLetterQueue` quando si utilizza l'associazione `MsmqIntegrationBinding`. Analogamente al caso di specifica dell'elemento quando si utilizza l'associazione `NetMsmqBinding`, tale elemento deve presentare il formato net.msmq://.  
  
## <a name="see-also"></a>Vedere anche

- [Hosting Web di un'applicazione in coda](../../../../docs/framework/wcf/feature-details/web-hosting-a-queued-application.md)
