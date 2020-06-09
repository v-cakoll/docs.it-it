---
title: Pooling
ms.date: 03/30/2017
ms.assetid: 688dfb30-b79a-4cad-a687-8302f8a9ad6a
ms.openlocfilehash: 82b81637deb0715d19109794348d2a2bcda7f0d9
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84594621"
---
# <a name="pooling"></a>Pooling
In questo esempio viene illustrato come estendere Windows Communication Foundation (WCF) per supportare il pool di oggetti. L'esempio illustra come creare un attributo sintatticamente e semanticamente simile alla funzionalità dell'attributo `ObjectPoolingAttribute` di Enterprise Services. Il pool degli oggetti può fornire una spinta notevole alle prestazioni di un'applicazione. Tuttavia, può avere l'effetto contrario se non utilizzato correttamente. Il pool degli oggetti consente di ridurre il sovraccarico dovuto alla creazione continua di oggetti frequentemente utilizzati che richiedono un'inizializzazione estesa. Tuttavia, se una chiamata a un metodo su un oggetto del pool richiede una quantità considerevole di tempo, il pool degli oggetti mette in coda richieste aggiuntive appena viene raggiunta la dimensione del pool massima. Pertanto può non riuscire a soddisfare richieste di creazione di oggetti generando un'eccezione di timeout.  
  
> [!NOTE]
> La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.  
  
 Il primo passaggio nella creazione di un'estensione WCF consiste nel decidere il punto di estensibilità da usare.  
  
 In WCF il termine *Dispatcher* fa riferimento a un componente runtime responsabile della conversione dei messaggi in arrivo in chiamate al metodo sul servizio dell'utente e della conversione di valori restituiti da tale metodo in un messaggio in uscita. Un servizio WCF crea un dispatcher per ogni endpoint. Un client WCF deve usare un dispatcher se il contratto associato a tale client è un contratto duplex.  
  
 I dispatcher del canale e dell'endpoint offrono estensibilità sul canale e sul contratto esponendo le varie proprietà che controllano il comportamento del dispatcher. La proprietà <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.DispatchRuntime%2A> consente inoltre di ispezionare, modificare e personalizzare la modalità di autenticazione dei certificati. Questo esempio si concentra sulla proprietà <xref:System.ServiceModel.Dispatcher.DispatchRuntime.InstanceProvider%2A> che punta all'oggetto che fornisce le istanze della classe del servizio.  
  
## <a name="the-iinstanceprovider"></a>Provider di istanze  
 In WCF, il dispatcher crea istanze della classe del servizio usando un oggetto <xref:System.ServiceModel.Dispatcher.DispatchRuntime.InstanceProvider%2A> che implementa l' <xref:System.ServiceModel.Dispatcher.IInstanceProvider> interfaccia. Questa interfaccia ha tre metodi:  
  
- <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%28System.ServiceModel.InstanceContext%2CSystem.ServiceModel.Channels.Message%29>: quando un messaggio arriva il dispatcher chiama il metodo <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%28System.ServiceModel.InstanceContext%2CSystem.ServiceModel.Channels.Message%29> per creare un'istanza della classe del servizio al fine di elaborare il messaggio. La frequenza delle chiamate a questo metodo è determinata dalla proprietà <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A>. Ad esempio, se la proprietà <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> è impostata su <xref:System.ServiceModel.InstanceContextMode.PerCall> viene creata una nuova istanza della classe del servizio per elaborare ogni messaggio che arriva, pertanto il metodo <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%28System.ServiceModel.InstanceContext%2CSystem.ServiceModel.Channels.Message%29> viene chiamato ogni qualvolta arriva un messaggio.  
  
- <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%28System.ServiceModel.InstanceContext%29>: questo metodo è identico a quello precedente, salvo che viene richiamato quando non c'è nessun argomento di messaggio.  
  
- <xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%28System.ServiceModel.InstanceContext%2CSystem.Object%29>: Quando la durata di un'istanza del servizio è scaduta, il dispatcher chiama il metodo <xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%28System.ServiceModel.InstanceContext%2CSystem.Object%29>. Solo per il metodo <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%28System.ServiceModel.InstanceContext%2CSystem.ServiceModel.Channels.Message%29>, la frequenza delle chiamate a questo metodo è determinata dalla proprietà <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A>.  
  
## <a name="the-object-pool"></a>Pool di oggetti  
 Un'implementazione personalizzata della classe <xref:System.ServiceModel.Dispatcher.IInstanceProvider> fornisce la semantica del pool di oggetti necessaria per un servizio. Pertanto, questo esempio ha un tipo `ObjectPoolingInstanceProvider` che fornisce un'implementazione personalizzata della classe <xref:System.ServiceModel.Dispatcher.IInstanceProvider> per il pool. Quando `Dispatcher` chiama il metodo <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%28System.ServiceModel.InstanceContext%2CSystem.ServiceModel.Channels.Message%29>, anziché creare una nuova istanza, l'implementazione personalizzata cerca un oggetto esistente in un pool in memoria che viene restituito se disponibile. In caso contrario, viene creato un nuovo oggetto. Nell'esempio di codice seguente viene illustrata l'implementazione di `GetInstance`.  
  
```csharp  
object IInstanceProvider.GetInstance(InstanceContext instanceContext, Message message)  
{  
    object obj = null;  
  
    lock (poolLock)  
    {  
        if (pool.Count > 0)  
        {  
            obj = pool.Pop();  
        }  
        else  
        {  
            obj = CreateNewPoolObject();  
        }  
        activeObjectsCount++;  
    }  
  
    WritePoolMessage(ResourceHelper.GetString("MsgNewObject"));  
  
    idleTimer.Stop();  
  
    return obj;
}  
```  
  
 L'implementazione personalizzata di `ReleaseInstance` aggiunge l'istanza rilasciata nuovamente al pool e decrementa il valore di `ActiveObjectsCount`. Il `Dispatcher` può chiamare questi metodi da thread diversi e pertanto sincronizzare l'accesso ai membri del livello della classe, nella classe `ObjectPoolingInstanceProvider` obbligatoria.  
  
```csharp  
void IInstanceProvider.ReleaseInstance(InstanceContext instanceContext, object instance)  
{  
    lock (poolLock)  
    {  
        pool.Push(instance);  
        activeObjectsCount--;  
  
        WritePoolMessage(  
        ResourceHelper.GetString("MsgObjectPooled"));  
  
        // When the service goes completely idle (no requests
        // are being processed), the idle timer is started  
        if (activeObjectsCount == 0)  
            idleTimer.Start();
    }  
}  
```  
  
 Il `ReleaseInstance` metodo fornisce una funzionalità di pulizia dell'inizializzazione. Normalmente il pool gestisce un numero minimo di oggetti per la durata del pool. Ci possono essere, tuttavia, periodi di utilizzo eccessivo che richiedono la creazione di oggetti aggiuntivi nel pool per raggiungere il limite massimo specificato nella configurazione. Successivamente, quando il pool diviene meno attivo, quegli oggetti in surplus possono divenire un sovraccarico aggiuntivo. Pertanto, quando il conteggio `activeObjectsCount` si azzera, viene avviato un timer, precedentemente inattivo, che inizia ed esegue un ciclo di pulizia.  
  
## <a name="adding-the-behavior"></a>Aggiunta del comportamento.  
 Le estensioni del livello del dispatcher vengono collegate utilizzando i comportamenti seguenti:  
  
- Comportamenti del servizio. Essi consentono la personalizzazione del runtime dell'intero servizio.  
  
- Comportamenti dell'endpoint. Essi consentono la personalizzazione degli endpoint del servizio, in particolare un canale e un dispatcher dell'endpoint.  
  
- Comportamenti del contratto. Essi consentono la personalizzazione di entrambe le classi <xref:System.ServiceModel.Dispatcher.ClientRuntime> e <xref:System.ServiceModel.Dispatcher.DispatchRuntime> rispettivamente sul client e sui servizi.  
  
 Allo scopo di un'estensione del pool di oggetti deve essere creato un comportamento del servizio. I comportamenti del servizio vengono creati implementando l'interfaccia <xref:System.ServiceModel.Description.IServiceBehavior>. Ci sono molti modi per rendere consapevole il modello dei servizi dei comportamenti personalizzati:  
  
- Utilizzo di un attributo personalizzato.  
  
- Aggiunto imperativamente alla raccolta di comportamenti della descrizione del servizio.  
  
- Estensione dei file di configurazione  
  
 Questo esempio utilizza un attributo personalizzato. Quando la classe <xref:System.ServiceModel.ServiceHost> viene costruita esamina gli attributi utilizzati nella definizione del tipo del servizio e aggiunge i comportamenti disponibili alla raccolta di comportamenti della descrizione del servizio.  
  
 L'interfaccia <xref:System.ServiceModel.Description.IServiceBehavior> contiene tre metodi: <xref:System.ServiceModel.Description.IServiceBehavior.Validate%2A>, <xref:System.ServiceModel.Description.IServiceBehavior.AddBindingParameters%2A> e <xref:System.ServiceModel.Description.IServiceBehavior.ApplyDispatchBehavior%2A>. Il metodo <xref:System.ServiceModel.Description.IServiceBehavior.Validate%2A> viene utilizzato per assicurare che il comportamento possa essere applicato al servizio. In questo esempio, l'implementazione assicura che il servizio non sia configurato con <xref:System.ServiceModel.InstanceContextMode.Single>. Il metodo <xref:System.ServiceModel.Description.IServiceBehavior.AddBindingParameters%2A> viene utilizzato per configurare le associazioni del servizio. Non è obbligatorio in questo scenario. Il metodo <xref:System.ServiceModel.Description.IServiceBehavior.ApplyDispatchBehavior%2A> viene utilizzato per configurare i dispatcher del servizio. Questo metodo viene chiamato da WCF quando <xref:System.ServiceModel.ServiceHost> è in corso l'inizializzazione di. I parametri seguenti vengono passati in questo metodo:  
  
- `Description`: questo argomento fornisce la descrizione del servizio per l'intero servizio. Può essere utilizzato per controllare dati della descrizione sugli endpoint del servizio, contratti, associazioni e altri dati.  
  
- `ServiceHostBase`: questo argomento fornisce la classe <xref:System.ServiceModel.ServiceHostBase> attualmente in fase di inizializzazione.  
  
 Nell'implementazione personalizzata della classe <xref:System.ServiceModel.Description.IServiceBehavior> viene creata una nuova istanza di `ObjectPoolingInstanceProvider` e viene assegnata alla proprietà <xref:System.ServiceModel.Dispatcher.DispatchRuntime.InstanceProvider%2A> in ogni <xref:System.ServiceModel.Dispatcher.DispatchRuntime> in ServiceHostBase.  
  
```csharp  
void IServiceBehavior.ApplyDispatchBehavior(ServiceDescription description, ServiceHostBase serviceHostBase)  
{  
    // Create an instance of the ObjectPoolInstanceProvider.  
    ObjectPoolingInstanceProvider instanceProvider = new  
           ObjectPoolingInstanceProvider(description.ServiceType,
                                                    minPoolSize);  
  
    // Forward the call if we created a ServiceThrottlingBehavior.  
    if (this.throttlingBehavior != null)  
    {  
        ((IServiceBehavior)this.throttlingBehavior).ApplyDispatchBehavior(description, serviceHostBase);  
    }  
  
    // In case there was already a ServiceThrottlingBehavior
    // (this.throttlingBehavior==null), it should have initialized
    // a single ServiceThrottle on all ChannelDispatchers.
    // As we loop through the ChannelDispatchers, we verify that
    // and modify the ServiceThrottle to guard MaxPoolSize.  
    ServiceThrottle throttle = null;  
  
    foreach (ChannelDispatcherBase cdb in
            serviceHostBase.ChannelDispatchers)  
    {  
        ChannelDispatcher cd = cdb as ChannelDispatcher;  
        if (cd != null)  
        {  
            // Make sure there is exactly one throttle used by all
            // endpoints. If there were others, we could not enforce
            // MaxPoolSize.  
            if ((this.throttlingBehavior == null) &&
                        (this.maxPoolSize != Int32.MaxValue))  
            {  
                throttle ??= cd.ServiceThrottle;
                if (cd.ServiceThrottle == null)  
                {  
                    throw new
InvalidOperationException(ResourceHelper.GetString("ExNullThrottle"));  
                }  
                if (throttle != cd.ServiceThrottle)  
                {  
                    throw new InvalidOperationException(ResourceHelper.GetString("ExDifferentThrottle"));  
                }  
             }  
  
             foreach (EndpointDispatcher ed in cd.Endpoints)  
             {  
                 // Assign it to DispatchBehavior in each endpoint.  
                 ed.DispatchRuntime.InstanceProvider =
                                      instanceProvider;  
             }  
         }  
     }  
  
     // Set the MaxConcurrentInstances to limit the number of items
     // that will ever be requested from the pool.  
     if ((throttle != null) && (throttle.MaxConcurrentInstances >
                                      this.maxPoolSize))  
     {  
         throttle.MaxConcurrentInstances = this.maxPoolSize;  
     }  
}  
```  
  
 Oltre a un'implementazione della classe <xref:System.ServiceModel.Description.IServiceBehavior>, la classe <xref:System.EnterpriseServices.ObjectPoolingAttribute> ha molti membri per personalizzare il pool di oggetti utilizzando gli argomenti dell'attributo. Questi membri includono <xref:System.EnterpriseServices.ObjectPoolingAttribute.MaxPoolSize%2A>, <xref:System.EnterpriseServices.ObjectPoolingAttribute.MinPoolSize%2A> e <xref:System.EnterpriseServices.ObjectPoolingAttribute.CreationTimeout%2A>, per corrispondere al set di funzionalità del pool di oggetti fornito da Enterprise Services .NET.  
  
 Il comportamento del pool di oggetti può ora essere aggiunto a un servizio WCF annotando l'implementazione del servizio con l'attributo personalizzato appena creato `ObjectPooling` .  
  
```csharp  
[ObjectPooling(MaxPoolSize=1024, MinPoolSize=10, CreationTimeout=30000)]
public class PoolService : IPoolService  
{  
  // …  
}  
```  
  
## <a name="running-the-sample"></a>Esecuzione dell'esempio  
 L'esempio illustra i vantaggi a livello di prestazioni che possono essere raggiunti utilizzando i pool di oggetti in alcuni scenari.  
  
 L'applicazione di servizio implementa due servizi: `WorkService` e `ObjectPooledWorkService`. Entrambi i servizi condividono la stessa implementazione. Richiedono entrambi una lunga inizializzazione e quindi espongono un metodo `DoWork()` che è relativamente conveniente. La sola differenza è che `ObjectPooledWorkService` ha un pool di oggetti configurato:  
  
```csharp  
[ObjectPooling(MinPoolSize = 0, MaxPoolSize = 5)]  
public class ObjectPooledWorkService : IDoWork  
{  
    public ObjectPooledWorkService()  
    {  
        Thread.Sleep(5000);  
        ColorConsole.WriteLine(ConsoleColor.Blue, "ObjectPooledWorkService instance created.");  
    }  
  
    public void DoWork()  
    {  
        ColorConsole.WriteLine(ConsoleColor.Blue, "ObjectPooledWorkService.GetData() completed.");  
    }
}  
```  
  
 Quando si esegue il client, effettua la chiamata a `WorkService` 5 volte. Quindi effettua la chiamata a `ObjectPooledWorkService` 5 volte. Viene infine visualizzata la differenza:  
  
```console
Press <ENTER> to start the client.  
  
Calling WorkService:  
1 - DoWork() Done  
2 - DoWork() Done  
3 - DoWork() Done  
4 - DoWork() Done  
5 - DoWork() Done  
Calling WorkService took: 26722 ms.  
Calling ObjectPooledWorkService:  
1 - DoWork() Done  
2 - DoWork() Done  
3 - DoWork() Done  
4 - DoWork() Done  
5 - DoWork() Done  
Calling ObjectPooledWorkService took: 5323 ms.  
Press <ENTER> to exit.  
```  
  
> [!NOTE]
> La prima volta che il client viene eseguito, entrambi i servizi sembrano avere la stessa durata. Se si esegue nuovamente l'esempio, è possibile vedere che `ObjectPooledWorkService` restituisce molto più rapidamente perché un'istanza di quell'oggetto già esiste nel pool.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
  
1. Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Per compilare la soluzione, seguire le istruzioni riportate in [compilazione degli esempi di Windows Communication Foundation](building-the-samples.md).  
  
3. Per eseguire l'esempio in una configurazione con un solo computer o tra computer diversi, seguire le istruzioni in [esecuzione degli esempi di Windows Communication Foundation](running-the-samples.md).  
  
> [!NOTE]
> Se si usa Svcutil.exe per rigenerare la configurazione di questo esempio, assicurarsi di modificare il nome dell'endpoint nella configurazione client in modo che corrisponda al codice client.  
  
> [!IMPORTANT]
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) ed [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Instancing\Pooling`  
