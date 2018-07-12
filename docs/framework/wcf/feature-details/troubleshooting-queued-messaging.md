---
title: Risoluzione dei problemi relativi ai messaggi in coda
ms.date: 03/30/2017
ms.assetid: a5f2836f-018d-42f5-a571-1e97e64ea5b0
ms.openlocfilehash: 45a3bf82662fcc01b732428d1ca351e4ae8ddca0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33509123"
---
# <a name="troubleshooting-queued-messaging"></a>Risoluzione dei problemi relativi ai messaggi in coda
In questa sezione contiene domande frequenti e risoluzione dei problemi per l'uso delle code in Windows Communication Foundation (WCF).  
  
## <a name="common-questions"></a>Domande frequenti  
 **Q:** utilizzato WCF Beta 1 ed è stato installato l'hotfix MSMQ. È necessario rimuovere l'hotfix?  
  
 **R:** Sì. Questo hotfix non è più supportato. WCF ora funziona con MSMQ senza la necessità di hotfix.  
  
 **Q:** sono disponibili due associazioni per MSMQ: <xref:System.ServiceModel.NetMsmqBinding> e <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>. Quando è opportuno utilizzare l'una o l'altra?  
  
 **R:** usare il <xref:System.ServiceModel.NetMsmqBinding> quando si desidera utilizzare MSMQ come trasporto per la comunicazione in coda tra due applicazioni WCF. Utilizzare il <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> quando si desidera utilizzare le applicazioni MSMQ esistenti per comunicare con le nuove applicazioni WCF.  
  
 **Q:** è necessario aggiornare MSMQ per utilizzare il <xref:System.ServiceModel.NetMsmqBinding> e `MsmqIntegration` associazioni?  
  
 **R:** No. Entrambe le associazioni funzionano con MSMQ 3.0 in [!INCLUDE[wxp](../../../../includes/wxp-md.md)] e [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]. Alcune funzionalità delle associazioni divengono disponibili quando si esegue l'aggiornamento a MSMQ 4.0 in [!INCLUDE[wv](../../../../includes/wv-md.md)].  
  
 **Q:** quali funzionalità del <xref:System.ServiceModel.NetMsmqBinding> e <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> le associazioni sono disponibili in MSMQ 4.0, ma non in MSMQ 3.0?  
  
 **R:** le funzionalità seguenti sono disponibili in MSMQ 4.0, ma non in MSMQ 3.0:  
  
-   Le code di messaggi non recapitabili personalizzate sono supportate solo in MSMQ 4.0.  
  
-   MSMQ 3.0 e 4.0 gestiscono i messaggi non elaborabili in modo diverso.  
  
-   La lettura transazionale remota è supportata solo in MSMQ 4.0.  
  
 Per altre informazioni, vedere [differenze nelle funzionalità di Accodamento messaggi in Windows Vista, Windows Server 2003 e Windows XP](../../../../docs/framework/wcf/feature-details/diff-in-queue-in-vista-server-2003-windows-xp.md).  
  
 **Q:** è possibile utilizzare MSMQ 3.0 su un lato di una comunicazione in coda e MSMQ 4.0 su altro lato?  
  
 **R:** Sì.  
  
 **Q:** per integrare applicazioni MSMQ esistenti con i nuovi client WCF o server. è necessario aggiornare entrambi i lati dell'infrastruttura MSMQ?  
  
 **R:** No. Non è necessario eseguire l'aggiornamento a MSMQ 4.0 in entrambi i lati.  
  
## <a name="troubleshooting"></a>Risoluzione dei problemi  
 Contenuto della sezione sono contenute risposte per la risoluzione della maggior parte dei problemi frequenti. Alcuni problemi costituiti da limitazioni note sono descritti anche nelle note sulla versione.  
  
 **Q:** si sta tentando di utilizzare una coda privata e viene generata l'eccezione seguente: `System.InvalidOperationException`: URL non valido. L'URL per la coda non può contenere il carattere '$'. Utilizzare la sintassi in net.msmq://machine/private/queueName per indirizzare una coda privata.  
  
 **R:** controllare la coda Uniform Resource Identifier (URI) nella configurazione e nel codice. Non utilizzare il carattere "$" nell'URI. Per indirizzare, ad esempio, una coda privata denominata OrdersQueue, specificare l'URI come segue: net.msmq://localhost/private/ordersQueue.  
  
 **Q:** chiamata `ServiceHost.Open()` per l'applicazione in coda genera la seguente eccezione: `System.ArgumentException`: un indirizzo di base non può contenere una stringa di query URI. Perché?  
  
 **R:** controllare l'URI nel file di configurazione e nel codice della coda. Mentre le code MSMQ supportano l'utilizzo del carattere '?', gli URI interpretano questo carattere come l'inizio di una query di stringa. Per evitare questo problema, utilizzare nomi di coda che non contengono caratteri '?'.  
  
 **Q:** l'invio è riuscito ma il ricevitore viene richiamata alcuna operazione di servizio. Perché?  
  
 **R:** per determinare la risposta, consultare l'elenco di controllo seguenti:  
  
-   Controllare che i requisiti della coda transazionale siano compatibili con le garanzie specificate. Tenere presenti i principi seguenti:  
  
    -   È possibile inviare messaggi durevoli (datagrammi e sessioni) con "una sola volta" garanzie (<xref:System.ServiceModel.MsmqBindingBase.ExactlyOnce%2A> = `true`) solo a una coda transazionale.  
  
    -   È possibile inviare sessioni solo con assicurazioni "una sola volta".  
  
    -   È necessaria una transazione per ricevere messaggi da una coda transazionale in una sessione.  
  
    -   È possibile inviare o ricevere messaggi volatili o durevoli (solo datagrammi) senza alcuna garanzia (<xref:System.ServiceModel.MsmqBindingBase.ExactlyOnce%2A> = `false`) solo in una coda non transazionale.  
  
-   Controllare la coda dei messaggi non recapitabili. Se sono presenti messaggi, determinare perché non sono stati recapitati.  
  
-   Verificare la connettività o eventuali problemi di indirizzamento delle code in uscita.  
  
 **Q:** è stata specificata una coda recapitabili personalizzata, ma quando avvia l'applicazione mittente, viene generata un'eccezione che non si trovata entrambi la coda o all'applicazione mittente non dispone delle autorizzazioni per la coda di messaggi non recapitabili. Perché si verifica questa situazione?  
  
 **R:** l'URI della coda recapitabili personalizzata deve includere "localhost" o il nome del computer nel primo segmento, ad esempio, MSMQ: //localhost/private/coda msgnonrecapitabiliapp.  
  
 **Q:** è sempre necessario definire una coda recapitabili personalizzata, o se si è un valore predefinito recapitabili?  
  
 **R:** se le garanzie sono "una sola volta" (<xref:System.ServiceModel.MsmqBindingBase.ExactlyOnce%2A> = `true`), e se non si specifica una coda recapitabili personalizzata, il valore predefinito è una coda recapitabili transazionale a livello di sistema.  
  
 Se vi sono garanzie (<xref:System.ServiceModel.MsmqBindingBase.ExactlyOnce%2A> = `false`), il valore predefinito è una funzionalità non recapitabili.  
  
 **Q:** il servizio genera un'eccezione in Svchost. Open con un messaggio "i requisiti di EndpointListener non possono essere soddisfatti da ListenerFactory". Perché?  
  
 Un  Controllare il contratto di servizio. È possibile avere dimenticato di inserire "IsOneWay =`true`" in tutte le operazioni di servizio. Le code supportano solo operazioni del servizio unidirezionali.  
  
 **Q:** contiene messaggi nella coda, ma viene richiamata alcuna operazione di servizio. Da che cosa è causato il problema?  
  
 **R:** determinare se l'host del servizio contiene errori. È possibile eseguire questo controllo analizzando la traccia o implementando `IErrorHandler`. L'host del servizio, per impostazione predefinita, entra in stato di errore se viene rilevato un messaggio non elaborabile.  
  
 **Q:** sono presenti messaggi nella coda, ma il servizio in coda ospitata sul Web non è attiva. Perché?  
  
 **R:** il motivo più comune è costituito dalle autorizzazioni.  
  
1.  Assicurarsi che il processo `NetMsmqActivator` sia in esecuzione e che all'identità del processo `NetMsmqActivator` sia concessa l'autorizzazione alla lettura e alla scrittura sulla coda.  
  
2.  Se `NetMsmqActivator` sta controllando le code in un computer remoto, assicurarsi che `NetMsmqActivator` non sia in esecuzione con un token di accesso con restrizioni. Per eseguire `NetMsmqActivator` con un token di accesso senza restrizioni:  
  
    ```  
    sc sidtype NetMsmqActivator unrestricted  
    ```  
  
 Per problemi dell'host Web correlati non correlato alla sicurezza, vedere: [Web ospita un'applicazione in coda](../../../../docs/framework/wcf/feature-details/web-hosting-a-queued-application.md).  
  
 **Q:** che cos'è il modo più semplice per le sessioni di accesso?  
  
 **R:** impostare AutoComplete =`true` sull'operazione che corrisponde all'ultimo messaggio della sessione e impostare AutoComplete =`false` in tutte le altre operazioni di servizio.  
  
 **Q:** dove posso trovare risposte alle domande frequenti su MSMQ?  
  
 **R:** per ulteriori informazioni su MSMQ, vedere [Microsoft Message Queuing](http://go.microsoft.com/fwlink/?LinkId=87810).  
  
 **Q:** perché il servizio genera un `ProtocolException` quando la lettura da una coda contenente sia messaggi della sessione e messaggi del datagramma in coda?  
  
 **R:** sussiste una differenza fondamentale nei messaggi di sessione in modo coda e sono composti da messaggi del datagramma in coda. Per questo motivo, un servizio che prevede di leggere un messaggio della sessione in coda non può ricevere un messaggio del datagramma in coda e un servizio che prevede di leggere un messaggio del datagramma in coda non può ricevere un messaggio della sessione. Eseguendo il tentativo di leggere entrambi tipi di messaggi dalla stessa coda viene generata l'eccezione seguente:  
  
```  
System.ServiceModel.MsmqPoisonMessageException: The transport channel detected a poison message. This occurred because the message exceeded the maximum number of delivery attempts or because the channel detected a fundamental problem with the message. The inner exception may contain additional information.   
---> System.ServiceModel.ProtocolException: An incoming MSMQ message contained invalid or unexpected .NET Message Framing information in its body. The message cannot be received. Ensure that the sender is using a compatible service contract with a matching SessionMode.  
```  
  
 La coda dei messaggi non recapitabili di sistema, così come quella personalizzata, è particolarmente interessata dal problema se un'applicazione invia sia messaggi della sessione sia messaggi del datagramma in coda dallo stesso computer. Se non è possibile inviare correttamente un messaggio, questo viene spostato nella coda dei messaggi non recapitabili. In queste circostanze è possibile che nella coda dei messaggi non recapitabili siano presenti sia messaggi della sessione sia messaggi del datagramma. Non vi è modo di separare i due tipi di messaggi in fase di esecuzione quando viene letta una coda, pertanto le applicazioni non devono inviare messaggi della sessione e messaggi del datagramma in coda dallo stesso computer.  
  
### <a name="msmq-integration-specific-troubleshooting"></a>Risoluzione dei problemi specifici dell'integrazione con MSMQ  
 **Q:** quando si invia un messaggio o quando viene aperto l'host del servizio, viene generato un errore che indica lo schema è errato. Perché?  
  
 **R:** quando si utilizza l'associazione di integrazione MSMQ, è necessario utilizzare lo schema MSMQ. FormatName. Ad esempio, msmq.formatname:DIRECT=OS:.\private$\OrdersQueue. Ma quando si specifica la coda dei messaggi non recapitabili personalizzata è necessario utilizzare lo schema net.msmq.  
  
 **Q:** quando si utilizza un nome di formato pubblico o privato e aprire l'host del servizio nel [!INCLUDE[wv](../../../../includes/wv-md.md)], viene generato un errore. Perché?  
  
 **R:** canale di integrazione di WCF in [!INCLUDE[wv](../../../../includes/wv-md.md)] verifiche per controllare se una coda secondaria può essere aperto per la coda dell'applicazione principale per la gestione messaggi non elaborabili. Il nome della coda secondaria deriva da un URI msmq.formatname passato al listener. Il nome della coda secondaria in MSMQ può essere solo un nome in formato diretto. Per questo motivo viene generato l'errore. Modificare l'URI della coda in modo che il nome sia in un formato diretto.  
  
 **Q:** quando si riceve un messaggio da un'applicazione MSMQ, il messaggio rimane nella coda e non viene letto dall'applicazione di ricezione WCF. Perché?  
  
 **R:** per verificare se il messaggio ha un corpo. Se è privo di corpo viene ignorato dal canale di integrazione con MSMQ. Implementare `IErrorHandler` per ricevere notifica delle eccezioni e controllare le tracce.  
  
### <a name="security-related-troubleshooting"></a>Risoluzione dei problemi correlati alla protezione  
 **Q:** quando si esegue l'esempio che utilizza un'associazione predefinita in modalità gruppo di lavoro, i messaggi sembrano essere inviati, ma non vengono mai ricevuti dal destinatario.  
  
 **R:** per impostazione predefinita, i messaggi vengono firmati utilizzando un certificato interno a MSMQ che richiede che il servizio directory Active Directory. In modalità gruppo di lavoro, poiché Active Directory non è disponibile, viene generato un errore nella firma del messaggio. Pertanto, il messaggio arriva nella coda di messaggi non recapitabili e viene indicato causa dell'errore, ad esempio "Firma errata".  
  
 La soluzione alternativa consiste nel disattivare la sicurezza. Questa operazione viene eseguita impostando <xref:System.ServiceModel.NetMsmqSecurity.Mode%2A>  =  <xref:System.ServiceModel.NetMsmqSecurityMode.None> per consentire il funzionamento in modalità gruppo di lavoro.  
  
 Un'altra soluzione alternativa è ottenere <xref:System.ServiceModel.MsmqTransportSecurity> dalla proprietà <xref:System.ServiceModel.NetMsmqSecurity.Transport%2A> e impostarlo su <xref:System.ServiceModel.MsmqAuthenticationMode.Certificate>, quindi impostare il certificato client.  
  
 Un'ulteriore soluzione alternativa consiste nell'installare MSMQ unitamente all'integrazione con Active Directory.  
  
 **Q:** quando si invia un messaggio con un'associazione predefinita (trasporto attivata) in Active Directory per una coda, viene visualizzato un messaggio "certificato interno non trovato". Com'è possibile risolvere il problema?  
  
 **R:** ciò significa che il certificato in Active Directory per il mittente deve essere rinnovato. A tale scopo, aprire **Pannello di controllo**, **strumenti di amministrazione**, **Gestione Computer**, fare doppio clic su **MSMQ**e selezionare **Proprietà**. Selezionare il **certificato utente** scheda e scegliere il **rinnova** pulsante.  
  
 **Q:** quando si invia un messaggio utilizzando <xref:System.ServiceModel.MsmqAuthenticationMode.Certificate> e specificare il certificato da utilizzare, viene visualizzato un messaggio "Certificato non valido". Com'è possibile risolvere il problema?  
  
 **R:** non è possibile utilizzare un archivio certificati del computer locale con la modalità certificati. È necessario copiare il certificato dall'archivio dei certificati del computer all'archivio dell'utente corrente utilizzando lo snap-in Certificati. Per ottenere lo snap-in Certificati:  
  
1.  Fare clic su **avviare**selezionare **eseguire**, tipo `mmc`, fare clic su **OK**.  
  
2.  Nel **Microsoft Management Console**, aprire il **File** dal menu **Aggiungi/Rimuovi Snap-in**.  
  
3.  Nel **Aggiungi/Rimuovi Snap-in** la finestra di dialogo, fare clic su di **Aggiungi** pulsante.  
  
4.  Nel **Aggiungi Snap-in Standalone** la finestra di dialogo, selezionare i certificati e fare clic su **Aggiungi**.  
  
5.  Nel **certificati** snap-in finestra di dialogo Seleziona **account dell'utente,** e fare clic su **fine**.  
  
6.  Successivamente, aggiungere un secondo snap-in certificati utilizzando i passaggi precedenti, ma questa volta selezionare **account Computer** e fare clic su **Avanti**.  
  
7.  Selezionare **Computer locale** e fare clic su **fine**. È ora possibile trascinare e rilasciare i certificati dall'archivio del computer all'archivio dell'utente corrente.  
  
 **Q:** quando il servizio legge da una coda in un altro computer in modalità gruppo di lavoro, viene generata un'eccezione "accesso negato".  
  
 **R:** In modalità gruppo di lavoro, per un'applicazione remota accedere alla coda, l'applicazione deve avere l'autorizzazione per accedere alla coda. Aggiungere "Accesso anonimo" all'elenco di controllo della coda accesso (ACL) e assegnare l'autorizzazione alla lettura.  
  
 **Q:** quando un client del servizio di rete (o qualsiasi client che non dispone di un account di dominio) invia un messaggio in coda, la trasmissione ha esito negativo con un certificato non valido. Com'è possibile risolvere il problema?  
  
 **R:** controllare la configurazione dell'associazione. Per l'associazione predefinita è attivata la protezione del trasporto MSMQ per la firma del messaggio. Disattivarla.  
  
### <a name="remote-transacted-receives"></a>Ricezioni transazionali remote  
 **Q:** quando si dispone di una coda sul computer A, e un servizio WCF che legge i messaggi da una coda sul computer B (scenario di ricezione transazionale remota), i messaggi non vengono letti dalla coda. Le informazioni di analisi indica la ricezione non riuscito con il messaggio "delle transazioni non possono essere importati." Che cosa può fare per risolvere il problema?  
  
 **R:** esistono tre possibili cause:  
  
-   In modalità di dominio per la ricezione transazionale remota è necessario l'accesso alla rete di Microsoft Distributed Transaction Coordinator (MSDTC). A tale scopo, utilizzare **Aggiungi/Rimuovi componenti**.  
  
     ![Abilitazione dell'accesso di rete DTC](../../../../docs/framework/wcf/feature-details/media/applicationserveraddcomps.jpg "ApplicationServerAddComps")  
  
-   Verificare la modalità di autenticazione per la comunicazione con il gestore transazioni. Se si è in modalità gruppo di lavoro, è non necessario selezionare "Nessuna autenticazione". Se si è in modalità di dominio, è necessario selezionare "Necessaria autenticazione reciproca".  
  
     ![Abilitazione delle transazioni XA](../../../../docs/framework/wcf/feature-details/media/4f3695e0-fb0b-4c5b-afac-75f8860d2bb0.jpg "4f3695e0-fb0b-4c5b-afac-75f8860d2bb0")  
  
-   Verificare che MSDTC sia nell'elenco delle eccezioni nel **Firewall connessione Internet** impostazioni.  
  
-   Assicurarsi di utilizzare [!INCLUDE[wv](../../../../includes/wv-md.md)]. MSMQ con [!INCLUDE[wv](../../../../includes/wv-md.md)] supporta la lettura transazionale remota. MSMQ con le versioni precedenti di Windows non supporta la lettura transazionale remota.  
  
 **Q:** quando il servizio che legge dalla coda è un servizio di rete, ad esempio, un sito Web host, motivo per cui ottenere un'eccezione di accesso negato viene generato durante la lettura dalla coda?  
  
 **R:** accesso in lettura servizio di rete deve essere aggiunti alla coda ACL in modo da garantire che un servizio di rete può leggere dalla coda.  
  
 **Q:** è possibile usare il servizio di attivazione MSMQ per attivare applicazioni basate su messaggi in una coda in un computer remoto?  
  
 **R:** Sì. A questo scopo, è necessario configurare il servizio di attivazione MSMQ in modo che venga eseguito come servizio di rete e aggiungere l'accesso al servizio di rete alla coda nel computer remoto.  
  
## <a name="using-custom-msmq-bindings-with-receivecontext-enabled"></a>Utilizzo di associazioni MSMQ personalizzate con ReceiveContext abilitato  
 Quando si utilizza un'associazione MSMQ personalizzata con <xref:System.ServiceModel.Channels.ReceiveContext> abilitato, per elaborare un messaggio in arrivo verrà utilizzato un thread del pool poiché il componente MSMQ nativo non supporta il completamento I/O per ricezioni di <xref:System.ServiceModel.Channels.ReceiveContext> asincrone. Questa situazione si verifica perché l'elaborazione di tale messaggio utilizza transazioni interne per <xref:System.ServiceModel.Channels.ReceiveContext> e MSMQ non supporta l'elaborazione asincrona. Per risolvere questo problema, è possibile aggiungere un oggetto <xref:System.ServiceModel.Description.SynchronousReceiveBehavior> all'endpoint per forzare l'elaborazione asincrona o impostare <xref:System.ServiceModel.Description.DispatcherSynchronizationBehavior.MaxPendingReceives%2A> su 1.
