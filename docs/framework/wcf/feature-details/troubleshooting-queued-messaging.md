---
title: Risoluzione dei problemi relativi ai messaggi in coda
ms.date: 03/30/2017
ms.assetid: a5f2836f-018d-42f5-a571-1e97e64ea5b0
ms.openlocfilehash: ed114cc9a37fff549e8bfc874765252fd18893a9
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75345582"
---
# <a name="troubleshooting-queued-messaging"></a>Risoluzione dei problemi relativi ai messaggi in coda

In questa sezione sono contenute le domande frequenti e la guida alla risoluzione dei problemi per l'utilizzo di code in Windows Communication Foundation (WCF).

## <a name="common-questions"></a>Domande frequenti

**D:** Ho utilizzato WCF beta 1 ed è stato installato l'hotfix MSMQ. È necessario rimuovere l'hotfix?

**R:** Sì. Questo hotfix non è più supportato. WCF ora funziona con MSMQ senza un requisito di hotfix.

**D:** Per MSMQ sono disponibili due associazioni: <xref:System.ServiceModel.NetMsmqBinding> e <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>. Quando è opportuno utilizzare l'una o l'altra?

**R:** Utilizzare il <xref:System.ServiceModel.NetMsmqBinding> quando si desidera utilizzare MSMQ come trasporto per la comunicazione in coda tra due applicazioni WCF. Utilizzare la <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> quando si desidera utilizzare le applicazioni MSMQ esistenti per comunicare con le nuove applicazioni WCF.

**D:** È necessario aggiornare MSMQ per usare le associazioni <xref:System.ServiceModel.NetMsmqBinding> e `MsmqIntegration`?

**R:** No. Entrambe le associazioni funzionano con MSMQ 3,0 in [!INCLUDE[wxp](../../../../includes/wxp-md.md)] e Windows Server 2003. Alcune funzionalità dei binding diventano disponibili quando si esegue l'aggiornamento a MSMQ 4,0 in Windows Vista.

**D:** Quali funzionalità delle associazioni <xref:System.ServiceModel.NetMsmqBinding> e <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> sono disponibili in MSMQ 4,0 ma non in MSMQ 3,0?

**R:** Le funzionalità seguenti sono disponibili in MSMQ 4,0 ma non in MSMQ 3,0:

- Le code di messaggi non recapitabili personalizzate sono supportate solo in MSMQ 4.0.

- MSMQ 3.0 e 4.0 gestiscono i messaggi non elaborabili in modo diverso.

- La lettura transazionale remota è supportata solo in MSMQ 4.0.

Per ulteriori informazioni, vedere [differenze nelle funzionalità di Accodamento in Windows Vista, Windows Server 2003 e Windows XP](../../../../docs/framework/wcf/feature-details/diff-in-queue-in-vista-server-2003-windows-xp.md).

**D:** È possibile usare MSMQ 3,0 su un lato di una comunicazione in coda e su MSMQ 4,0 dall'altro lato?

**R:** Sì.

**D:** Desidero integrare le applicazioni MSMQ esistenti con i nuovi client o server WCF. è necessario aggiornare entrambi i lati dell'infrastruttura MSMQ?

**R:** No. Non è necessario eseguire l'aggiornamento a MSMQ 4.0 in entrambi i lati.

## <a name="troubleshooting"></a>Risoluzione dei problemi

Contenuto della sezione sono contenute risposte per la risoluzione della maggior parte dei problemi frequenti. Alcuni problemi costituiti da limitazioni note sono descritti anche nelle note sulla versione.

**D:** Si sta tentando di usare una coda privata e viene generata l'eccezione seguente: `System.InvalidOperationException`: l'URL non è valido. L'URL per la coda non può contenere il carattere '$'. Utilizzare la sintassi in net.msmq://machine/private/queueName per indirizzare una coda privata.

**R:** Controllare la coda Uniform Resource Identifier (URI) nella configurazione e nel codice. Non utilizzare il carattere "$" nell'URI. Per indirizzare, ad esempio, una coda privata denominata OrdersQueue, specificare l'URI come segue: net.msmq://localhost/private/ordersQueue.

**D:** Chiamando `ServiceHost.Open()` nell'applicazione in coda viene generata l'eccezione seguente: `System.ArgumentException`: un indirizzo di base non può contenere una stringa di query URI. Perché?

**R:** Controllare l'URI della coda nel file di configurazione e nel codice. Mentre le code MSMQ supportano l'utilizzo del carattere '?', gli URI interpretano questo carattere come l'inizio di una query di stringa. Per evitare questo problema, utilizzare nomi di coda che non contengono caratteri '?'.

**D:** L'invio è riuscito, ma non viene richiamata alcuna operazione del servizio sul ricevitore. Perché?

**R:** Per determinare la risposta, utilizzare l'elenco di controllo seguente:

- Controllare che i requisiti della coda transazionale siano compatibili con le garanzie specificate. Tenere presenti i principi seguenti:

  - È possibile inviare messaggi durevoli (datagrammi e sessioni) con garanzie "exactly once" (<xref:System.ServiceModel.MsmqBindingBase.ExactlyOnce%2A> = `true`) solo a una coda transazionale.

  - È possibile inviare sessioni solo con assicurazioni "una sola volta".

  - È necessaria una transazione per ricevere messaggi da una coda transazionale in una sessione.

  - È possibile inviare o ricevere messaggi volatili o durevoli (solo datagrammi) senza garanzie (<xref:System.ServiceModel.MsmqBindingBase.ExactlyOnce%2A> = `false`) solo a una coda non transazionale.

- Controllare la coda dei messaggi non recapitabili. Se sono presenti messaggi, determinare perché non sono stati recapitati.

- Verificare la connettività o eventuali problemi di indirizzamento delle code in uscita.

**D:** Ho specificato una coda di messaggi non recapitabili personalizzata, ma quando avvio l'applicazione mittente, ottengo un'eccezione che indica che la coda dei messaggi non recapitabili non è stata trovata o che l'applicazione mittente non dispone dell'autorizzazione per la coda dei messaggi non recapitabili. Perché si verifica questa situazione?

**R:** L'URI della coda dei messaggi non recapitabili personalizzata deve includere un "localhost" o il nome del computer nel primo segmento, ad esempio NET. MSMQ://localhost/private/myAppdead-letter Queue.

**D:** È sempre necessario definire una coda di messaggi non recapitabili personalizzata oppure esiste una coda di messaggi non recapitabili predefinita?

**R:** Se le garanzie sono "exactly once" (<xref:System.ServiceModel.MsmqBindingBase.ExactlyOnce%2A> = `true`) e se non si specifica una coda di messaggi non recapitabili personalizzata, il valore predefinito è una coda di messaggi non recapitabili transazionale a livello di sistema.

Se le garanzie sono None (<xref:System.ServiceModel.MsmqBindingBase.ExactlyOnce%2A> = `false`), il valore predefinito è nessuna funzionalità della coda dei messaggi non recapitabili.

**D:** Il servizio genera un'eccezione su SvcHost. Open con un messaggio "i requisiti di EndpointListener non possono essere soddisfatti da ListenerFactory". Perché?

Oggetto. Controllare il contratto di servizio. È possibile che si sia dimenticato di inserire "IsOneWay =`true`" in tutte le operazioni del servizio. Le code supportano solo operazioni del servizio unidirezionali.

**D:** Sono presenti messaggi nella coda, ma non viene richiamata alcuna operazione del servizio. Da che cosa è causato il problema?

**R:** Determinare se si è verificato un errore nell'host del servizio. È possibile eseguire questo controllo analizzando la traccia o implementando `IErrorHandler`. L'host del servizio, per impostazione predefinita, entra in stato di errore se viene rilevato un messaggio non elaborabile.

**D:** Sono presenti messaggi nella coda, ma il servizio in coda ospitato dal Web non viene attivato. Perché?

**R:** Il motivo più comune è le autorizzazioni.

1. Assicurarsi che il processo `NetMsmqActivator` sia in esecuzione e che all'identità del processo `NetMsmqActivator` sia concessa l'autorizzazione alla lettura e alla scrittura sulla coda.

2. Se `NetMsmqActivator` sta controllando le code in un computer remoto, assicurarsi che `NetMsmqActivator` non sia in esecuzione con un token di accesso con restrizioni. Per eseguire `NetMsmqActivator` con un token di accesso senza restrizioni:

    ```console
    sc sidtype NetMsmqActivator unrestricted
    ```

Per i problemi relativi all'host Web non correlati alla sicurezza, vedere [il sito Web che ospita un'applicazione in coda](../../../../docs/framework/wcf/feature-details/web-hosting-a-queued-application.md).

**D:** Qual è il modo più semplice per accedere alle sessioni?

**R:** Impostare AutoComplete =`true` sull'operazione che corrisponde all'ultimo messaggio della sessione e impostare AutoComplete =`false` per tutte le operazioni del servizio rimanenti.

**D:** Dove è possibile trovare le risposte alle domande più comuni su MSMQ?

**R:** Per ulteriori informazioni su MSMQ, vedere [Microsoft Message Queuing](https://go.microsoft.com/fwlink/?LinkId=87810).

**D:** Perché il servizio genera un'`ProtocolException` durante la lettura da una coda che contiene sia i messaggi della sessione in coda che i messaggi del datagramma in coda?

**R:** Esiste una differenza fondamentale nel modo in cui i messaggi della sessione in coda e i messaggi del datagramma in coda vengono composti. Per questo motivo, un servizio che prevede di leggere un messaggio della sessione in coda non può ricevere un messaggio del datagramma in coda e un servizio che prevede di leggere un messaggio del datagramma in coda non può ricevere un messaggio della sessione. Eseguendo il tentativo di leggere entrambi tipi di messaggi dalla stessa coda viene generata l'eccezione seguente:

```console
System.ServiceModel.MsmqPoisonMessageException: The transport channel detected a poison message. This occurred because the message exceeded the maximum number of delivery attempts or because the channel detected a fundamental problem with the message. The inner exception may contain additional information.
---> System.ServiceModel.ProtocolException: An incoming MSMQ message contained invalid or unexpected .NET Message Framing information in its body. The message cannot be received. Ensure that the sender is using a compatible service contract with a matching SessionMode.
```

La coda dei messaggi non recapitabili di sistema, così come quella personalizzata, è particolarmente interessata dal problema se un'applicazione invia sia messaggi della sessione sia messaggi del datagramma in coda dallo stesso computer. Se non è possibile inviare correttamente un messaggio, questo viene spostato nella coda dei messaggi non recapitabili. In queste circostanze è possibile che nella coda dei messaggi non recapitabili siano presenti sia messaggi della sessione sia messaggi del datagramma. Non vi è modo di separare i due tipi di messaggi in fase di esecuzione quando viene letta una coda, pertanto le applicazioni non devono inviare messaggi della sessione e messaggi del datagramma in coda dallo stesso computer.

### <a name="msmq-integration-specific-troubleshooting"></a>Risoluzione dei problemi specifici dell'integrazione con MSMQ

**D:** Quando si invia un messaggio o quando si apre l'host del servizio, viene visualizzato un errore che indica che lo schema è errato. Perché?

**R:** Quando si utilizza l'associazione di integrazione MSMQ, è necessario utilizzare lo schema MSMQ. FormatName. Ad esempio, msmq.formatname:DIRECT=OS:.\private$\OrdersQueue. Ma quando si specifica la coda dei messaggi non recapitabili personalizzata è necessario utilizzare lo schema net.msmq.

**D:** Quando si utilizza un nome di formato pubblico o privato e si apre l'host del servizio in Windows Vista, viene visualizzato un errore. Perché?

**R:** Il canale di integrazione WCF in Windows Vista verifica se è possibile aprire una coda secondaria per la coda dell'applicazione principale per la gestione dei messaggi non elaborabili. Il nome della coda secondaria deriva da un URI msmq.formatname passato al listener. Il nome della coda secondaria in MSMQ può essere solo un nome in formato diretto. Per questo motivo viene generato l'errore. Modificare l'URI della coda in modo che il nome sia in un formato diretto.

**D:** Quando si riceve un messaggio da un'applicazione MSMQ, il messaggio si trova nella coda e non viene letto dall'applicazione WCF di destinazione. Perché?

**R:** Verificare se il messaggio contiene un corpo. Se è privo di corpo viene ignorato dal canale di integrazione con MSMQ. Implementare `IErrorHandler` per ricevere notifica delle eccezioni e controllare le tracce.

### <a name="security-related-troubleshooting"></a>Risoluzione dei problemi correlati alla protezione

**D:** Quando si esegue l'esempio che usa un'associazione predefinita in modalità gruppo di lavoro, i messaggi sembrano essere inviati ma non vengono mai ricevuti dal ricevitore.

**R:** Per impostazione predefinita, i messaggi vengono firmati utilizzando un certificato interno MSMQ che richiede il servizio directory Active Directory. In modalità gruppo di lavoro, poiché Active Directory non è disponibile, viene generato un errore nella firma del messaggio. Pertanto, il messaggio viene inserito nella coda dei messaggi non recapitabili e la relativa errore, ad esempio "firma errata", è indicata.

La soluzione alternativa consiste nel disattivare la sicurezza. Questa operazione viene eseguita impostando <xref:System.ServiceModel.NetMsmqSecurity.Mode%2A> = <xref:System.ServiceModel.NetMsmqSecurityMode.None> per farlo funzionare in modalità gruppo di lavoro.

Un'altra soluzione alternativa è ottenere <xref:System.ServiceModel.MsmqTransportSecurity> dalla proprietà <xref:System.ServiceModel.NetMsmqSecurity.Transport%2A> e impostarlo su <xref:System.ServiceModel.MsmqAuthenticationMode.Certificate>, quindi impostare il certificato client.

Un'ulteriore soluzione alternativa consiste nell'installare MSMQ unitamente all'integrazione con Active Directory.

**D:** Quando si invia un messaggio con binding predefinito (sicurezza del trasporto attivata) in Active Directory a una coda, viene ricevuto un messaggio "certificato interno non trovato". Com'è possibile risolvere il problema?

**R:** Ciò significa che è necessario rinnovare il certificato in Active Directory per il mittente. A tale scopo, aprire **Pannello di controllo**, **strumenti di amministrazione**, **Gestione computer**, fare clic con il pulsante destro del mouse su **MSMQ**, quindi scegliere **Proprietà**. Selezionare la scheda **certificato utente** e fare clic sul pulsante **rinnova** .

**D:** Quando si invia un messaggio utilizzando <xref:System.ServiceModel.MsmqAuthenticationMode.Certificate> e si specifica il certificato da utilizzare, viene ricevuto un messaggio "certificato non valido". Com'è possibile risolvere il problema?

**R:** Non è possibile usare un archivio certificati del computer locale con la modalità certificato. È necessario copiare il certificato dall'archivio dei certificati del computer all'archivio dell'utente corrente utilizzando lo snap-in Certificati. Per ottenere lo snap-in Certificati:

1. Fare clic sul pulsante **Start**, scegliere **esegui**, digitare `mmc`, quindi fare clic su **OK**.

2. In **Microsoft Management Console**aprire il menu **file** e selezionare **Aggiungi/Rimuovi snap-in**.

3. Nella finestra di dialogo **Aggiungi/Rimuovi snap-in** , fare clic sul pulsante **Aggiungi** .

4. Nella finestra **di dialogo Aggiungi snap-in autonomo** selezionare certificati e fare clic su **Aggiungi**.

5. Nella finestra di dialogo snap-in **certificati** selezionare **account utente personale** e fare clic su **fine**.

6. Successivamente, aggiungere un secondo snap-in certificati usando i passaggi precedenti, ma questa volta selezionare **account computer** e fare clic su **Avanti**.

7. Selezionare **Computer locale** e fare clic su **Fine**. È ora possibile trascinare i certificati dall'archivio del computer all'archivio dell'utente corrente.

**D:** Quando il servizio legge da una coda in un altro computer in modalità gruppo di lavoro, viene generata un'eccezione "accesso negato".

**R:** In modalità gruppo di lavoro, affinché un'applicazione remota ottenga l'accesso alla coda, l'applicazione deve disporre dell'autorizzazione per accedere alla coda. Aggiungere "login anonimo" all'elenco di controllo di accesso (ACL) della coda e concedergli l'autorizzazione di lettura.

**D:** Quando un client del servizio di rete (o un client che non dispone di un account di dominio) Invia un messaggio in coda, l'invio ha esito negativo con un certificato non valido. Com'è possibile risolvere il problema?

**R:** Controllare la configurazione dell'associazione. Per l'associazione predefinita è attivata la protezione del trasporto MSMQ per la firma del messaggio. Disattivarla.

### <a name="remote-transacted-receives"></a>Ricezioni transazionali remote

**D:** Quando si dispone di una coda sul computer A e un servizio WCF che legge i messaggi da una coda nel computer B (scenario di ricezione transazionale remoto), i messaggi non vengono letti dalla coda. Le informazioni di traccia indicano che la ricezione non è riuscita con il messaggio "Impossibile importare la transazione". Come si può risolvere questo problema?

**R:** Esistono tre possibili motivi:

- In modalità di dominio per la ricezione transazionale remota è necessario l'accesso alla rete di Microsoft Distributed Transaction Coordinator (MSDTC). È possibile abilitare questa operazione utilizzando **Aggiungi/Rimuovi componenti**.

  ![Screenshot che Mostra come abilitare l'accesso DTC alla rete.](./media/troubleshooting-queued-messaging/enable-distributed-transaction-coordinator-access.jpg)

- Verificare la modalità di autenticazione per la comunicazione con il gestore transazioni. Se si è in modalità gruppo di lavoro, è necessario selezionare "Nessuna autenticazione obbligatoria". Se si è in modalità dominio, è necessario selezionare "autenticazione reciproca obbligatoria".

  ![Abilitazione delle transazioni XA](../../../../docs/framework/wcf/feature-details/media/4f3695e0-fb0b-4c5b-afac-75f8860d2bb0.jpg "4f3695e0-fb0b-4c5b-afac-75f8860d2bb0")

- Verificare che MSDTC sia nell'elenco delle eccezioni nelle impostazioni del firewall per la **connessione Internet** .

- Assicurarsi di utilizzare Windows Vista. MSMQ in Windows Vista supporta la lettura transazionale remota. MSMQ con le versioni precedenti di Windows non supporta la lettura transazionale remota.

**D:** Quando il servizio che legge dalla coda è un servizio di rete, ad esempio in un host Web, perché viene generata un'eccezione di accesso negato durante la lettura dalla coda?

**R:** L'accesso in lettura al servizio di rete deve essere aggiunto all'ACL della coda per garantire che un servizio di rete possa leggere dalla coda.

**D:** È possibile utilizzare il servizio di attivazione MSMQ per attivare applicazioni basate su messaggi in una coda in un computer remoto?

**R:** Sì. A questo scopo, è necessario configurare il servizio di attivazione MSMQ in modo che venga eseguito come servizio di rete e aggiungere l'accesso al servizio di rete alla coda nel computer remoto.

## <a name="using-custom-msmq-bindings-with-receivecontext-enabled"></a>Utilizzo di associazioni MSMQ personalizzate con ReceiveContext abilitato

Quando si utilizza un'associazione MSMQ personalizzata con <xref:System.ServiceModel.Channels.ReceiveContext> abilitato, per elaborare un messaggio in arrivo verrà utilizzato un thread del pool poiché il componente MSMQ nativo non supporta il completamento I/O per ricezioni di <xref:System.ServiceModel.Channels.ReceiveContext> asincrone. Questa situazione si verifica perché l'elaborazione di tale messaggio utilizza transazioni interne per <xref:System.ServiceModel.Channels.ReceiveContext> e MSMQ non supporta l'elaborazione asincrona. Per risolvere questo problema, è possibile aggiungere un oggetto <xref:System.ServiceModel.Description.SynchronousReceiveBehavior> all'endpoint per forzare l'elaborazione asincrona o impostare <xref:System.ServiceModel.Description.DispatcherSynchronizationBehavior.MaxPendingReceives%2A> su 1.
