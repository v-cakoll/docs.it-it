---
title: Accodamento in WCF
ms.date: 03/30/2017
ms.assetid: e98d76ba-1acf-42cd-b137-0f8214661112
ms.openlocfilehash: 6656ab0b2db88297e6ac9a28bb2ea18c0056d18c
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837324"
---
# <a name="queuing-in-wcf"></a>Accodamento in WCF
In questa sezione viene descritto come utilizzare la comunicazione in coda in Windows Communication Foundation (WCF).  
  
## <a name="queues-as-a-wcf-transport-binding"></a>Accodamento come associazione di trasporto WCF  
 In WCF i contratti specificano gli elementi che vengono scambiati. I contratti sono scambi di messaggi dipendenti dall'azienda o specifici dell'applicazione. Il meccanismo (o la modalità) usato per scambiare messaggi viene specificato nelle associazioni. Le associazioni in WCF incapsulano i dettagli dello scambio di messaggi. Espongono funzionalità di configurazione che consentono all'utente di controllare vari aspetti del trasporto o del protocollo rappresentato dall'associazione. L'accodamento in WCF viene considerato come qualsiasi altra associazione di trasporto, che rappresenta un grande vantaggio per molte applicazioni di Accodamento. Oggi, molte applicazioni di accodamento vengono scritte in modo diverso dalle applicazioni distribuite in stile chiamata di procedura remota (RPC), rendendone più difficile la gestione. Con WCF, lo stile di scrittura di un'applicazione distribuita è molto simile, rendendolo più semplice da seguire e gestire. Inoltre, eseguendo il factoring del meccanismo di scambio separatamente dalla regola business, è più semplice configurare il trasporto o apportarvi modifiche senza incidere sul codice specifico dell'applicazione. Nella figura seguente viene illustrata la struttura di un servizio e un client WCF usando MSMQ come trasporto.  
  
 ![Diagramma dell'applicazione in coda](../../../../docs/framework/wcf/feature-details/media/distributed-queue-figure.jpg "Distributed-Queue-Figure")  
  
 Come risulta evidente dalla figura precedente, il client e il servizio devono definire solo la semantica dell'applicazione, ovvero, il contratto e l'implementazione. Il servizio configura un'associazione in coda con le impostazioni preferite. Il client utilizza lo [strumento ServiceModel Metadata Utility Tool (Svcutil. exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) per generare un client WCF per il servizio e per generare un file di configurazione che descrive i binding da utilizzare per l'invio di messaggi al servizio. Pertanto, per inviare un messaggio in coda, il client crea un'istanza di un client WCF e richiama un'operazione su di essa. Questo fa sì che il messaggio venga inviato alla coda di trasmissione e trasferito alla coda di destinazione. Tutte le complessità della comunicazione in coda vengono nascoste all'applicazione che sta inviando e ricevendo messaggi.  
  
 Le avvertenze sull'associazione in coda in WCF includono:  
  
- Tutte le operazioni del servizio devono essere unidirezionali perché l'associazione in coda predefinita in WCF non supporta la comunicazione duplex con le code. Un esempio di comunicazione bidirezionale ([comunicazione bidirezionale](../../../../docs/framework/wcf/samples/two-way-communication.md)) illustra come usare i contratti a 2 1 per implementare la comunicazione duplex con le code.  
  
- Per generare un client WCF mediante lo scambio di metadati, è necessario un endpoint HTTP aggiuntivo nel servizio in modo che sia possibile eseguire una query direttamente per generare il client WCF e ottenere informazioni di binding per configurare in modo appropriato la comunicazione in coda.  
  
- In base all'associazione in coda, è necessaria una configurazione aggiuntiva all'esterno di WCF. Ad esempio, la classe <xref:System.ServiceModel.NetMsmqBinding> fornita con WCF richiede la configurazione dei binding e la configurazione minima di Accodamento messaggi (MSMQ).  
  
 Nelle sezioni seguenti vengono descritte le associazioni in coda specifiche fornite con WCF, basate su MSMQ.  
  
### <a name="msmq"></a>MSMQ  
 Il trasporto in coda in WCF utilizza MSMQ per la comunicazione in coda.  
  
 MSMQ viene fornito con Windows come componente facoltativo e viene eseguito come servizio NT. Acquisisce i messaggi per la trasmissione in una coda di trasmissione e per il recapito in una coda di destinazione. I gestori code MSMQ implementano un protocollo di trasferimento messaggi affidabile, in modo che i messaggi non vengano persi durante la trasmissione. Il protocollo può essere nativo o basato su SOAP, ad esempio SRMP (SOAP Reliable Message Protocol).  
  
 In MSMQ, le code possono essere transazionali o non transazionali. Una coda transazionale consente di acquisire e recapitare messaggi in una transazione, per poi archiviarli permanentemente nella coda. I messaggi inviati a una coda transazionale vengono trasferiti esattamente una volta in ordine. È possibile usare una coda non transazionale per inviare messaggi volatili e durevoli. Un messaggio inviato a una coda non transazionale non offre alcuna assicurazione di trasferimento affidabile e può quindi essere perso.  
  
 Le code MSMQ possono essere protette anche usando un'identità di Windows registrata con il servizio directory Active Directory. Quando si installa MSMQ, è possibile installare l'integrazione di Active Directory, che richiede che il computer faccia parte di una rete di dominio Windows.  
  
 Per ulteriori informazioni su MSMQ, vedere [installazione di Accodamento messaggi (MSMQ)](../../../../docs/framework/wcf/samples/installing-message-queuing-msmq.md).  
  
### <a name="netmsmqbinding"></a>NetMsmqBinding  
 Il [\<netmsmqbinding >](../../../../docs/framework/configure-apps/file-schema/wcf/netmsmqbinding.md) è il binding in coda che WCF fornisce per la comunicazione tra due endpoint WCF mediante MSMQ. L'associazione, pertanto, espone proprietà specifiche di MSMQ. Tuttavia, non tutte le funzionalità e le proprietà di MSMQ vengono esposte in `NetMsmqBinding`. La classe compatta `NetMsmqBinding` è progettata con un set ottimale di funzionalità che la maggior parte dei clienti dovrebbe trovare sufficiente.  
  
 La classe `NetMsmqBinding` manifesta i principali concetti di accodamento descritti fino ad ora nella forma di proprietà sulle associazioni. Queste proprietà, a loro volta, comunicano a MSMQ come trasferire e recapitare i messaggi. Nelle sezioni seguenti vengono descritte le categorie di proprietà. Per ulteriori informazioni, vedere gli argomenti concettuali che descrivono le proprietà specifiche più completamente.  
  
#### <a name="exactlyonce-and-durable-properties"></a>Proprietà ExactlyOnce e Durable  
 Le proprietà `ExactlyOnce` e `Durable` incidono sulla modalità di trasferimento dei messaggi tra le code:  
  
- `ExactlyOnce`: se è impostata su `true` (impostazione predefinita), il canale in coda assicura che il messaggio, se recapitato, non venga duplicato. Assicura inoltre che il messaggio non venga perso. Se il messaggio non può essere recapitato o se la durata del messaggio scade prima che il messaggio possa essere recapitato, il messaggio non riuscito, insieme al motivo dell'errore di recapito, viene registrato in una coda di messaggi non recapitabili. Se la proprietà è impostata su `false`, il canale in coda tenta di trasferire il messaggio. In questo caso, è possibile scegliere una coda di messaggi non recapitabili.  
  
- `Durable:` se è impostata su `true` (impostazione predefinita), il canale in coda assicura che MSMQ archivi il messaggio sul disco in modo permanente. Così, se il servizio MSMQ viene interrotto e riavviato, il messaggio sul disco viene trasferito alla coda di destinazione o recapitato al servizio. Se la proprietà è impostata su `false`, i messaggi vengono memorizzati in un archivio volatile e persi al momento dell'interruzione e del riavvio del servizio MSMQ.  
  
 Per il trasferimento affidabile `ExactlyOnce`, MSMQ richiede che la coda sia transazionale. Inoltre, MSMQ richiede una transazione da leggere da una coda transazionale. Se si usa `NetMsmqBinding` è quindi importante ricordare che è necessaria una transazione per inviare o ricevere messaggi quando la proprietà `ExactlyOnce` è impostata su `true`. Allo stesso modo, MSMQ richiede che la coda sia non transazionale per le situazioni che necessitano del massimo sforzo, come quando `ExactlyOnce` è `false` e per la messaggistica volatile. Quindi, quando si imposta `ExactlyOnce` su `false` o Durable su `false`, non è possibile inviare o ricevere messaggi usando una transazione.  
  
> [!NOTE]
> Assicurarsi che venga creata la coda corretta (transazionale o non transazionale) in base alle impostazioni nelle associazioni. Se `ExactlyOnce` è `true`, usare una coda transazionale; altrimenti, usare una coda non transazionale.  
  
#### <a name="dead-letter-queue-properties"></a>Proprietà della coda di messaggi non recapitabili  
 La coda di messaggi non recapitabili viene usata per archiviare i messaggi il cui recapito ha esito negativo. L'utente può scrivere una logica di compensazione che legga i messaggi dalla coda di messaggi non recapitabili.  
  
 Molti sistemi di accodamento prevedono una coda di messaggi non recapitabili a livello di sistema. MSMQ include una coda di messaggi non recapitabili non transazionale a livello di sistema per i messaggi il cui recapito nelle code non transazionali ha esito negativo e una coda di messaggi non recapitabili transazionale a livello di sistema per i messaggi il cui recapito nelle code transazionali ha esito negativo.  
  
 Se più client che inviano messaggi a code di destinazione diverse condividono il servizio MSMQ, tutti i messaggi inviati dai client finiranno nella stessa coda di messaggi non recapitabili. Ciò non è sempre preferibile. Per un migliore isolamento, WCF e MSMQ in Windows Vista forniscono una coda di messaggi non recapitabili personalizzata, ovvero una coda di messaggi non recapitabili specifica dell'applicazione, che l'utente può specificare per archiviare i messaggi che non vengono recapitati. Pertanto, client diversi non condividono la stessa coda di messaggi non recapitabili.  
  
 L'associazione dispone di due proprietà interessanti:  
  
- `DeadLetterQueue`: questa proprietà è un'enumerazione che indica se è necessaria una coda di messaggi non recapitabili. Nel caso sia necessaria, l'enumerazione contiene anche il tipo di coda di messaggi non recapitabili. I valori sono `None`, `System` e `Custom`. Per ulteriori informazioni sull'interpretazione di queste proprietà, vedere [utilizzo di code di messaggi non recapitabili per gestire gli errori di trasferimento dei messaggi](../../../../docs/framework/wcf/feature-details/using-dead-letter-queues-to-handle-message-transfer-failures.md)  
  
- `CustomDeadLetterQueue`: questa proprietà è l'indirizzo URI (Uniform Resource Identifier) della coda di messaggi non recapitabili specifica dell'applicazione. Questa operazione è obbligatoria se `DeadLetterQueue`.`Custom` viene scelto.  
  
#### <a name="poison-message-handling-properties"></a>Proprietà di gestione dei messaggi non elaborabili  
 Quando il servizio legge un messaggio dalla coda di destinazione in una transazione, è possibile che non riesca a elaborarlo per vari motivi. Il messaggio viene quindi reinserito nella coda per essere nuovamente letto. Per gestire messaggi la cui elaborazione ripetutamente esito negativo, è possibile configurare nell'associazione un set di proprietà di gestione dei messaggi non elaborabili. Sono disponibili quattro proprietà: `ReceiveRetryCount`, `MaxRetryCycles`, `RetryCycleDelay` e `ReceiveErrorHandling`. Per ulteriori informazioni su queste proprietà, vedere [gestione dei messaggi non elaborabili](../../../../docs/framework/wcf/feature-details/poison-message-handling.md).  
  
#### <a name="security-properties"></a>Proprietà di sicurezza  
 MSMQ espone il proprio modello di sicurezza, che prevede ad esempio l'applicazione di elenchi di controllo di accesso (ACL) su una coda o l'invio di messaggi autenticati. La classe `NetMsmqBinding` espone queste proprietà di sicurezza come parte delle proprie impostazioni di sicurezza del trasporto. Nell'associazione sono presenti due proprietà per la sicurezza del trasporto: `MsmqAuthenticationMode` e `MsmqProtectionLevel`. Le impostazioni in queste proprietà dipendono dalla modalità di configurazione di MSMQ. Per ulteriori informazioni, vedere [protezione dei messaggi mediante la sicurezza del trasporto](../../../../docs/framework/wcf/feature-details/securing-messages-using-transport-security.md).  
  
 Oltre alla sicurezza del trasporto, il messaggio SOAP effettivo stesso può essere protetto usando la sicurezza dei messaggi. Per ulteriori informazioni, vedere [protezione dei messaggi mediante la sicurezza dei](../../../../docs/framework/wcf/feature-details/securing-messages-using-message-security.md)messaggi.  
  
 Anche `MsmqTransportSecurity` espone due proprietà, `MsmqEncryptionAlgorithm` e `MsmqHashAlgorithm`. Si tratta di enumerazioni di algoritmi diversi da scegliere per la crittografia del trasferimento da coda a coda di messaggi e l'hash delle firme.  
  
#### <a name="other-properties"></a>Altre proprietà  
 Oltre alle proprietà precedenti, le altre proprietà specifiche di MSMQ esposte nell'associazione includono:  
  
- `UseSourceJournal`: proprietà che indica che l'inserimento nel journal di origine è attivato. L'inserimento nel journal di origine è una funzionalità MSMQ che consente di tenere traccia dei messaggi correttamente trasmessi dalla coda di trasmissione.  
  
- `UseMsmqTracing`: proprietà che indica che la traccia MSMQ è attivata. La traccia MSMQ consente di inviare messaggi di rapporto a una coda dei rapporti ogni volta che un messaggio lascia o arriva in un computer che ospita un gestore code MSMQ.  
  
- `QueueTransferProtocol`: enumerazione del protocollo da usare per i trasferimenti di messaggi da coda a coda. MSMQ implementa un protocollo di trasferimento da coda a coda nativo e un protocollo basato su SOAP denominato SRMP (SOAP Reliable Messaging Protocol). SRMP viene usato quando si usa il trasporto HTTP per i trasferimenti da coda a coda. Viene invece usato il protocollo SRMP protetto quando si usa HTTPS per i trasferimenti da coda a coda.  
  
- `UseActiveDirectory`: valore booleano che indica se è necessario usare Active Directory per la risoluzione degli indirizzi delle code. Per impostazione predefinita, questa funzionalità è disattivata. Per ulteriori informazioni, vedere [endpoint di servizio e indirizzamento delle code](../../../../docs/framework/wcf/feature-details/service-endpoints-and-queue-addressing.md).  
  
### <a name="msmqintegrationbinding"></a>MsmqIntegrationBinding  
 Il `MsmqIntegrationBinding` viene utilizzato quando si desidera che un endpoint WCF comunichi con un'applicazione MSMQ esistente scritta in API C C++,, com o System. Messaging.  
  
 Le proprietà dell'associazione sono le stesse di `NetMsmqBinding`. Esistono tuttavia le differenze seguenti:  
  
- Il contratto dell'operazione per `MsmqIntegrationBinding` si limita ad accettare un solo parametro di tipo <xref:System.ServiceModel.MsmqIntegration.MsmqMessage%601>, in cui il parametro di tipo è il tipo di corpo.  
  
- Molte delle proprietà dei messaggi native MSMQ vengono esposte in <xref:System.ServiceModel.MsmqIntegration.MsmqMessage%601> per l'uso.  
  
- Per agevolare la serializzazione e la deserializzazione del corpo del messaggio vengono forniti serializzatori XML e ActiveX.  
  
### <a name="sample-code"></a>Codice di esempio  
 Per istruzioni dettagliate su come scrivere servizi WCF che usano MSMQ, vedere gli argomenti seguenti:  
  
- [Procedura: Scambiare messaggi con endpoint WCF e con applicazioni di accodamento messaggi](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-with-wcf-endpoints-and-message-queuing-applications.md)  
  
- [Procedura: Scambiare messaggi in coda con endpoint WCF](../../../../docs/framework/wcf/feature-details/how-to-exchange-queued-messages-with-wcf-endpoints.md)  
  
 Per un esempio di codice completo in cui viene illustrato l'uso di MSMQ in WCF, vedere gli argomenti seguenti:  
  
- [Associazioni MSMQ transazionali](../../../../docs/framework/wcf/samples/transacted-msmq-binding.md)  
  
- [Comunicazione volatile in coda](../../../../docs/framework/wcf/samples/volatile-queued-communication.md)  
  
- [Code di messaggi non recapitabili](../../../../docs/framework/wcf/samples/dead-letter-queues.md)  
  
- [Sessioni e code](../../../../docs/framework/wcf/samples/sessions-and-queues.md)  
  
- [Comunicazione bidirezionale](../../../../docs/framework/wcf/samples/two-way-communication.md) 
  
- [SRMP](../../../../docs/framework/wcf/samples/srmp.md)  
  
- [Sicurezza dei messaggi nell'accodamento messaggi](../../../../docs/framework/wcf/samples/message-security-over-message-queuing.md)  
  
## <a name="see-also"></a>Vedere anche

- [Endpoint di servizio e indirizzamento delle code](../../../../docs/framework/wcf/feature-details/service-endpoints-and-queue-addressing.md)
- [Hosting Web di un'applicazione in coda](../../../../docs/framework/wcf/feature-details/web-hosting-a-queued-application.md)
