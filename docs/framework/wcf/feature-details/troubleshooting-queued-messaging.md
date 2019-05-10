---
title: Risoluzione dei problemi relativi ai messaggi in coda
ms.date: 03/30/2017
ms.assetid: a5f2836f-018d-42f5-a571-1e97e64ea5b0
ms.openlocfilehash: 760ef4801c0881829dbc57b4022dcea4ed8c64bb
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64645223"
---
# <a name="troubleshooting-queued-messaging"></a>Risoluzione dei problemi relativi ai messaggi in coda
In questa sezione contiene domande frequenti e risoluzione dei problemi per l'uso delle code in Windows Communication Foundation (WCF).  
  
## <a name="common-questions"></a>Domande frequenti  
 **Q:** Ho utilizzato WCF Beta 1 e installato l'hotfix MSMQ. È necessario rimuovere l'hotfix?  
  
 **R:** Sì. Questo hotfix non è più supportato. WCF ora funziona con MSMQ senza la necessità di hotfix.  
  
 **Q:** Sono disponibili due associazioni per MSMQ: <xref:System.ServiceModel.NetMsmqBinding> e <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>. Quando è opportuno utilizzare l'una o l'altra?  
  
 **R:** Usare il <xref:System.ServiceModel.NetMsmqBinding> quando si desidera utilizzare MSMQ come trasporto per la comunicazione in coda tra due applicazioni WCF. Usare il <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> quando si desidera utilizzare le applicazioni MSMQ esistenti per comunicare con le nuove applicazioni WCF.  
  
 **Q:** È necessario aggiornare MSMQ per utilizzare il <xref:System.ServiceModel.NetMsmqBinding> e `MsmqIntegration` associazioni?  
  
 **R:** No. Entrambe le associazioni funzionano con MSMQ 3.0 in [!INCLUDE[wxp](../../../../includes/wxp-md.md)] e [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]. Alcune funzionalità delle associazioni divengono disponibili quando si esegue l'aggiornamento a MSMQ 4.0 in [!INCLUDE[wv](../../../../includes/wv-md.md)].  
  
 **Q:** Quali funzionalità dei <xref:System.ServiceModel.NetMsmqBinding> e <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> associazioni sono disponibili in MSMQ 4.0, ma non in MSMQ 3.0?  
  
 **R:** Le funzionalità seguenti sono disponibili in MSMQ 4.0, ma non in MSMQ 3.0:  
  
- Le code di messaggi non recapitabili personalizzate sono supportate solo in MSMQ 4.0.  
  
- MSMQ 3.0 e 4.0 gestiscono i messaggi non elaborabili in modo diverso.  
  
- La lettura transazionale remota è supportata solo in MSMQ 4.0.  
  
 Per altre informazioni, vedere [differenze nelle funzionalità di Accodamento in Windows Vista, Windows Server 2003 e Windows XP](../../../../docs/framework/wcf/feature-details/diff-in-queue-in-vista-server-2003-windows-xp.md).  
  
 **Q:** È possibile utilizzare MSMQ 3.0 su un lato di una comunicazione in coda e MSMQ 4.0 su altro lato?  
  
 **R:** Sì.  
  
 **Q:** Si desidera integrare applicazioni MSMQ esistenti con i nuovi client WCF o server. è necessario aggiornare entrambi i lati dell'infrastruttura MSMQ?  
  
 **R:** No. Non è necessario eseguire l'aggiornamento a MSMQ 4.0 in entrambi i lati.  
  
## <a name="troubleshooting"></a>Risoluzione dei problemi  
 Contenuto della sezione sono contenute risposte per la risoluzione della maggior parte dei problemi frequenti. Alcuni problemi costituiti da limitazioni note sono descritti anche nelle note sulla versione.  
  
 **Q:** Sto cercando di usare una coda privata e viene generata l'eccezione seguente: `System.InvalidOperationException`: L'URL non è valido. L'URL per la coda non può contenere il carattere '$'. Utilizzare la sintassi in net.msmq://machine/private/queueName per indirizzare una coda privata.  
  
 **R:** Controllare la coda Uniform Resource Identifier (URI) nella configurazione e nel codice. Non utilizzare il carattere "$" nell'URI. Per indirizzare, ad esempio, una coda privata denominata OrdersQueue, specificare l'URI come segue: net.msmq://localhost/private/ordersQueue.  
  
 **Q:** La chiamata `ServiceHost.Open()` sull'applicazione in coda genera l'eccezione seguente: `System.ArgumentException`: Un indirizzo di base non può contenere una stringa di query URI. Perché?  
  
 **R:** Controllare l'URI nel file di configurazione e nel codice della coda. Mentre le code MSMQ supportano l'utilizzo del carattere '?', gli URI interpretano questo carattere come l'inizio di una query di stringa. Per evitare questo problema, utilizzare nomi di coda che non contengono caratteri '?'.  
  
 **Q:** L'invio è riuscito ma il ricevitore viene richiamata alcuna operazione di servizio. Perché?  
  
 **R:** Per determinare la risposta, consultare l'elenco di controllo seguente:  
  
- Controllare che i requisiti della coda transazionale siano compatibili con le garanzie specificate. Tenere presenti i principi seguenti:  
  
    - È possibile inviare messaggi durevoli (datagrammi e sessioni) con "exactly-once" garanzie (<xref:System.ServiceModel.MsmqBindingBase.ExactlyOnce%2A> = `true`) solo a una coda transazionale.  
  
    - È possibile inviare sessioni solo con assicurazioni "una sola volta".  
  
    - È necessaria una transazione per ricevere messaggi da una coda transazionale in una sessione.  
  
    - È possibile inviare o ricevere messaggi volatili o durevoli (solo datagrammi) senza garanzie (<xref:System.ServiceModel.MsmqBindingBase.ExactlyOnce%2A> = `false`) solo a una coda non transazionale.  
  
- Controllare la coda dei messaggi non recapitabili. Se sono presenti messaggi, determinare perché non sono stati recapitati.  
  
- Verificare la connettività o eventuali problemi di indirizzamento delle code in uscita.  
  
 **Q:** È stata specificata una coda non recapitabili personalizzata, ma quando avvia l'applicazione mittente, viene generata un'eccezione che la coda di lettera non consegnata non viene trovata, o l'applicazione mittente non dispone di autorizzazioni per la coda di messaggi non recapitabili. Perché si verifica questa situazione?  
  
 **R:** L'URI della coda non recapitabilità personalizzato deve includere "localhost" o il nome del computer nel primo segmento, ad esempio, MSMQ: //localhost/private/coda msgnonrecapitabiliapp.  
  
 **Q:** È sempre necessario definire una coda non recapitabili personalizzata o è presente un coda predefinita?  
  
 **R:** Se le garanzie sono "exactly-once" (<xref:System.ServiceModel.MsmqBindingBase.ExactlyOnce%2A> = `true`), e se non si specifica una coda non recapitabili personalizzata, il valore predefinito è una coda recapitabili transazionale a livello di sistema.  
  
 Se vi sono garanzie (<xref:System.ServiceModel.MsmqBindingBase.ExactlyOnce%2A> = `false`), quindi il valore predefinito è disponibile alcuna funzionalità di coda dei messaggi non recapitabili.  
  
 **Q:** Il servizio genera un'eccezione in Svchost con un messaggio "i requisiti di EndpointListener non possono essere soddisfatti da ListenerFactory". Perché?  
  
 Un  Controllare il contratto di servizio. È possibile avere dimenticato di inserire "IsOneWay =`true`" in tutte le operazioni del servizio. Le code supportano solo operazioni del servizio unidirezionali.  
  
 **Q:** Sono presenti messaggi nella coda, ma viene richiamata alcuna operazione di servizio. Da che cosa è causato il problema?  
  
 **R:** Determinare se l'host del servizio contiene errori. È possibile eseguire questo controllo analizzando la traccia o implementando `IErrorHandler`. L'host del servizio, per impostazione predefinita, entra in stato di errore se viene rilevato un messaggio non elaborabile.  
  
 **Q:** Sono presenti messaggi nella coda ma non si attiva il mio servizio in coda ospitata sul Web. Perché?  
  
 **R:** Il motivo più comune è le autorizzazioni.  
  
1. Assicurarsi che il processo `NetMsmqActivator` sia in esecuzione e che all'identità del processo `NetMsmqActivator` sia concessa l'autorizzazione alla lettura e alla scrittura sulla coda.  
  
2. Se `NetMsmqActivator` sta controllando le code in un computer remoto, assicurarsi che `NetMsmqActivator` non sia in esecuzione con un token di accesso con restrizioni. Per eseguire `NetMsmqActivator` con un token di accesso senza restrizioni:  
  
    ```  
    sc sidtype NetMsmqActivator unrestricted  
    ```  
  
 Per problemi non correlato alla sicurezza correlati Web host, vedere: [Web che ospita un'applicazione in coda](../../../../docs/framework/wcf/feature-details/web-hosting-a-queued-application.md).  
  
 **Q:** Che cos'è il modo più semplice per accedere alle sessioni?  
  
 **R:** Impostare AutoComplete =`true` sull'operazione che corrisponde all'ultimo messaggio della sessione e AutoComplete =`false` su tutte le altre operazioni di servizio.  
  
 **Q:** Dove trovare le risposte alle domande comuni su MSMQ?  
  
 **R:** Per altre informazioni su MSMQ, vedere [Accodamento messaggi Microsoft](https://go.microsoft.com/fwlink/?LinkId=87810).  
  
 **Q:** Il motivo per cui il servizio genera una `ProtocolException` quando la lettura da una coda contenente sia messaggi della sessione e messaggi del datagramma in coda?  
  
 **R:** È presente una differenza fondamentale nei messaggi di sessione in modo coda e sono composti da messaggi del datagramma in coda. Per questo motivo, un servizio che prevede di leggere un messaggio della sessione in coda non può ricevere un messaggio del datagramma in coda e un servizio che prevede di leggere un messaggio del datagramma in coda non può ricevere un messaggio della sessione. Eseguendo il tentativo di leggere entrambi tipi di messaggi dalla stessa coda viene generata l'eccezione seguente:  
  
```  
System.ServiceModel.MsmqPoisonMessageException: The transport channel detected a poison message. This occurred because the message exceeded the maximum number of delivery attempts or because the channel detected a fundamental problem with the message. The inner exception may contain additional information.   
---> System.ServiceModel.ProtocolException: An incoming MSMQ message contained invalid or unexpected .NET Message Framing information in its body. The message cannot be received. Ensure that the sender is using a compatible service contract with a matching SessionMode.  
```  
  
 La coda dei messaggi non recapitabili di sistema, così come quella personalizzata, è particolarmente interessata dal problema se un'applicazione invia sia messaggi della sessione sia messaggi del datagramma in coda dallo stesso computer. Se non è possibile inviare correttamente un messaggio, questo viene spostato nella coda dei messaggi non recapitabili. In queste circostanze è possibile che nella coda dei messaggi non recapitabili siano presenti sia messaggi della sessione sia messaggi del datagramma. Non vi è modo di separare i due tipi di messaggi in fase di esecuzione quando viene letta una coda, pertanto le applicazioni non devono inviare messaggi della sessione e messaggi del datagramma in coda dallo stesso computer.  
  
### <a name="msmq-integration-specific-troubleshooting"></a>Integrazione con MSMQ Risoluzione dei problemi specifici  
 **Q:** Quando si invia un messaggio o quando si apre l'host del servizio, viene visualizzato un errore che indica che lo schema è errato. Perché?  
  
 **R:** Quando si usa l'associazione di integrazione MSMQ, è necessario usare lo schema MSMQ. FormatName. Ad esempio, msmq.formatname:DIRECT=OS:.\private$\OrdersQueue. Ma quando si specifica la coda dei messaggi non recapitabili personalizzata è necessario utilizzare lo schema net.msmq.  
  
 **Q:** Quando Usa un nome di formato pubblici o privati e aprire l'host del servizio su [!INCLUDE[wv](../../../../includes/wv-md.md)], viene visualizzato un errore. Perché?  
  
 **R:** Il canale di integrazione WCF su [!INCLUDE[wv](../../../../includes/wv-md.md)] controlla se una coda secondaria può essere aperto per la coda dell'applicazione principale per la gestione dei messaggi non elaborabili. Il nome della coda secondaria deriva da un URI msmq.formatname passato al listener. Il nome della coda secondaria in MSMQ può essere solo un nome in formato diretto. Per questo motivo viene generato l'errore. Modificare l'URI della coda in modo che il nome sia in un formato diretto.  
  
 **Q:** Quando si riceve un messaggio da un'applicazione MSMQ, il messaggio rimane nella coda e non viene letto dall'applicazione di ricezione WCF. Perché?  
  
 **R:** Verificare se il messaggio contiene un corpo. Se è privo di corpo viene ignorato dal canale di integrazione con MSMQ. Implementare `IErrorHandler` per ricevere notifica delle eccezioni e controllare le tracce.  
  
### <a name="security-related-troubleshooting"></a>Risoluzione dei problemi correlati alla protezione  
 **Q:** Quando esegue l'esempio che usa un'associazione predefinita in modalità gruppo di lavoro, i messaggi sembrano essere inviati, ma non vengono mai ricevuti dal ricevitore.  
  
 **R:** Per impostazione predefinita, i messaggi vengono firmati usando un certificato interno MSMQ che richiede il servizio directory Active Directory. In modalità gruppo di lavoro, poiché Active Directory non è disponibile, viene generato un errore nella firma del messaggio. Pertanto, il messaggio arriva la coda di messaggi non recapitabili e viene indicata causa dell'errore, ad esempio "Firma errata".  
  
 La soluzione alternativa consiste nel disattivare la sicurezza. Questa operazione viene eseguita impostando <xref:System.ServiceModel.NetMsmqSecurity.Mode%2A>  =  <xref:System.ServiceModel.NetMsmqSecurityMode.None> per consentire il funzionamento in modalità gruppo di lavoro.  
  
 Un'altra soluzione alternativa è ottenere <xref:System.ServiceModel.MsmqTransportSecurity> dalla proprietà <xref:System.ServiceModel.NetMsmqSecurity.Transport%2A> e impostarlo su <xref:System.ServiceModel.MsmqAuthenticationMode.Certificate>, quindi impostare il certificato client.  
  
 Un'ulteriore soluzione alternativa consiste nell'installare MSMQ unitamente all'integrazione con Active Directory.  
  
 **Q:** Quando si invia un messaggio con l'associazione predefinita (trasporto sicurezza attivata) in Active Directory per una coda, viene visualizzato un messaggio "certificato interno non trovato". Com'è possibile risolvere il problema?  
  
 **R:** Ciò significa che il certificato in Active Directory per il mittente deve essere rinnovato. A tale scopo, aprire **Pannello di controllo**, **strumenti di amministrazione**, **Gestione Computer**, fare doppio clic su **MSMQ**e scegliere **Proprietà**. Selezionare il **certificato utente** scheda e fare clic sui **Renew** pulsante.  
  
 **Q:** Quando si invia un messaggio utilizzando <xref:System.ServiceModel.MsmqAuthenticationMode.Certificate> e specificare il certificato da usare, viene visualizzato un messaggio "Certificato non valido". Com'è possibile risolvere il problema?  
  
 **R:** È possibile utilizzare un archivio certificati computer locale con la modalità certificati. È necessario copiare il certificato dall'archivio dei certificati del computer all'archivio dell'utente corrente utilizzando lo snap-in Certificati. Per ottenere lo snap-in Certificati:  
  
1. Fare clic su **avviare**, selezionare **eseguito**, digitare `mmc`, fare clic su **OK**.  
  
2. Nel **Microsoft Management Console**, aprire il **File** dal menu **Aggiungi/Rimuovi Snap-in**.  
  
3. Nel **Aggiungi/Rimuovi Snap-in** finestra di dialogo, fare clic sul **Aggiungi** pulsante.  
  
4. Nel **Aggiungi Snap-in Standalone** finestra di dialogo selezionare certificati e fare clic su **Add**.  
  
5. Nel **certificati** snap-in finestra di dialogo **account dell'utente** e fare clic su **fine**.  
  
6. Successivamente, aggiungere un secondo snap-in certificati usando i passaggi precedenti, ma questa volta selezionare **account Computer** e fare clic su **successivo**.  
  
7. Selezionare **Computer locale** e fare clic su **fine**. È ora possibile trascinare i certificati dall'archivio del computer all'archivio dell'utente corrente.  
  
 **Q:** Quando il servizio legge da una coda in un altro computer in modalità gruppo di lavoro, viene generata un'eccezione "accesso negato".  
  
 **R:** In modalità gruppo di lavoro, per un'applicazione remota accedere alla coda, l'applicazione deve avere l'autorizzazione per accedere alla coda. Aggiungere "Accesso anonimo" all'elenco di controllo di accesso della coda (ACL) e assegnargli l'autorizzazione di lettura.  
  
 **Q:** Quando un client del servizio di rete (o qualsiasi client che non dispone di un account di dominio) invia un messaggio in coda, l'invio ha esito negativo con un certificato non valido. Com'è possibile risolvere il problema?  
  
 **R:** Controllare la configurazione dell'associazione. Per l'associazione predefinita è attivata la protezione del trasporto MSMQ per la firma del messaggio. Disattivarla.  
  
### <a name="remote-transacted-receives"></a>Ricezioni transazionali remote  
 **Q:** Quando si dispone di una coda un oggetto e un servizio WCF che legge i messaggi da una coda sul computer B (scenario di ricezione transazionale remota) del computer, i messaggi sono non letto dalla coda. Informazioni di traccia indicano la ricezione non è riuscita con il messaggio "delle transazioni non possono essere importati." Cosa può fare per risolvere questo problema?  
  
 **R:** Le ragioni possibili sono tre:  
  
- In modalità di dominio per la ricezione transazionale remota è necessario l'accesso alla rete di Microsoft Distributed Transaction Coordinator (MSDTC). È possibile abilitarla usando **Aggiungi/Rimuovi componenti**.  
  
     ![Screenshot che mostra l'abilitazione di rete DTC accesso.](./media/troubleshooting-queued-messaging/enable-distributed-transaction-coordinator-access.jpg)  
  
- Verificare la modalità di autenticazione per la comunicazione con il gestore transazioni. Se si è in modalità gruppo di lavoro, è non necessario selezionare "Nessuna autenticazione". Se si è in modalità di dominio, è necessario selezionare "Necessaria autenticazione reciproca".  
  
     ![Abilitazione delle transazioni XA](../../../../docs/framework/wcf/feature-details/media/4f3695e0-fb0b-4c5b-afac-75f8860d2bb0.jpg "4f3695e0-fb0b-4c5b-afac-75f8860d2bb0")  
  
- Assicurarsi che MSDTC sia nell'elenco delle eccezioni nel **Internet Connection Firewall** impostazioni.  
  
- Assicurarsi di utilizzare [!INCLUDE[wv](../../../../includes/wv-md.md)]. MSMQ con [!INCLUDE[wv](../../../../includes/wv-md.md)] supporta la lettura transazionale remota. MSMQ con le versioni precedenti di Windows non supporta la lettura transazionale remota.  
  
 **Q:** Quando il servizio che legge dalla coda è un servizio di rete, ad esempio, un sito Web host, il motivo per cui ottenere un'eccezione di accesso negato viene generato durante la lettura dalla coda?  
  
 **R:** Accesso in lettura del servizio di rete deve essere aggiunto alla coda di ACL per assicurarsi che un servizio di rete può leggere dalla coda.  
  
 **Q:** È possibile usare il servizio di attivazione MSMQ per attivare le applicazioni basate su messaggi in una coda in un computer remoto?  
  
 **R:** Sì. A questo scopo, è necessario configurare il servizio di attivazione MSMQ in modo che venga eseguito come servizio di rete e aggiungere l'accesso al servizio di rete alla coda nel computer remoto.  
  
## <a name="using-custom-msmq-bindings-with-receivecontext-enabled"></a>Utilizzo di associazioni MSMQ personalizzate con ReceiveContext abilitato  
 Quando si utilizza un'associazione MSMQ personalizzata con <xref:System.ServiceModel.Channels.ReceiveContext> abilitato, per elaborare un messaggio in arrivo verrà utilizzato un thread del pool poiché il componente MSMQ nativo non supporta il completamento I/O per ricezioni di <xref:System.ServiceModel.Channels.ReceiveContext> asincrone. Questa situazione si verifica perché l'elaborazione di tale messaggio utilizza transazioni interne per <xref:System.ServiceModel.Channels.ReceiveContext> e MSMQ non supporta l'elaborazione asincrona. Per risolvere questo problema, è possibile aggiungere un oggetto <xref:System.ServiceModel.Description.SynchronousReceiveBehavior> all'endpoint per forzare l'elaborazione asincrona o impostare <xref:System.ServiceModel.Description.DispatcherSynchronizationBehavior.MaxPendingReceives%2A> su 1.
