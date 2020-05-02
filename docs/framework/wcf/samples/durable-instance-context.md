---
title: Contesto dell'istanza durevole
ms.date: 03/30/2017
ms.assetid: 97bc2994-5a2c-47c7-927a-c4cd273153df
ms.openlocfilehash: d70617fef7ebe0a94e22e858ee403d5d4f1840e3
ms.sourcegitcommit: 7370aa8203b6036cea1520021b5511d0fd994574
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/02/2020
ms.locfileid: "82728401"
---
# <a name="durable-instance-context"></a>Contesto dell'istanza durevole

In questo esempio viene illustrato come personalizzare il runtime di Windows Communication Foundation (WCF) per abilitare contesti dell'istanza durevoli. SQL Server 2005 viene utilizzato come archivio di backup (in questo caso SQL Server 2005 Express). Tuttavia, viene fornito anche un modo di accedere ai meccanismi di archiviazione personalizzati.

> [!NOTE]
> La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.

Questo esempio prevede l'estensione del livello del canale e del livello del modello di servizio di WCF. È pertanto necessario comprendere i concetti sottostanti prima di entrare nei dettagli dell'implementazione.

I contesti dell'istanza durevoli si trovano spesso in situazioni del mondo reale. Un'applicazione del carrello acquisti, ad esempio, ha la possibilità di sospendere la spesa a metà e di continuare in un altro giorno. Quando si visita il carrello degli acquisti il giorno successivo, il contesto originale viene ripristinato. È importante notare che l'applicazione di carrello degli acquisti (sul server) non mantiene l'istanza del carrello degli acquisti mentre si è disconnessi. Invece, lo stato viene salvato in un archivio durevole e viene utilizzato per generare una nuova istanza del contesto ripristinato. Pertanto l'istanza del servizio che può essere utile allo stesso contesto non corrisponde all'istanza precedente (ovvero, non ha lo stesso indirizzo di memoria).

Il contesto dell'istanza durevole è reso possibile da un piccolo protocollo che consente al client e al servizio di scambiare un ID del contesto. Questo ID del contesto viene creato sul client e trasmesso al servizio. Quando viene creata l'istanza del servizio, il runtime del servizio tenta di caricare lo stato salvato che corrisponde a questo ID del contesto da un'archiviazione permanente (per impostazione predefinita corrisponde a un database SQL Server 2005). Se non è disponibile alcuno stato, la nuova istanza avrà lo stato predefinito. L'implementazione del servizio utilizza un attributo personalizzato per contrassegnare le operazioni che modificano il runtime del servizio, in modo che la fase di esecuzione possa salvare l'istanza del servizio dopo averle richiamate.

Dalla descrizione precedente è possibile individuare i due passaggi necessari per raggiungere l'obiettivo:

1. Modificare il messaggio che va in transito per portare l'ID del contesto.

2. Modificare il comportamento locale del servizio per implementare la logica dell'istanza personalizzata.

Poiché la prima nell'elenco influiscono sui messaggi in transito, è necessario implementarla come canale personalizzato e associarla al livello del canale. Il secondo passaggio influisce solo sul comportamento locale del servizio e pertanto può essere implementato estendendo vari punti di estensibilità del servizio. Nelle prossime sezioni verranno illustrate tutte queste estensioni.

## <a name="durable-instancecontext-channel"></a>Canale InstanceContext durevole

La prima cosa da notare è l'estensione del livello del canale. Il primo passaggio per creare un canale personalizzato consiste nel decidere la struttura della comunicazione del canale. Quando viene introdotto un nuovo protocollo wire, il canale dovrebbe funzionare con quasi tutti gli altri canali nello stack dei canali. È pertanto necessario che supporti tutti i modelli di scambio dei messaggi. Tuttavia, la funzionalità principale del canale rimane la stessa, indipendentemente dalla struttura della comunicazione. Più specificamente, deve scrivere l'ID del contesto ai messaggi dal client e leggere questo ID del contesto dai messaggi dal servizio, per poi passarlo ai livelli superiori. Per questa ragione, viene creata una classe `DurableInstanceContextChannelBase` che rappresenta la classe di base astratta per tutte le implementazioni dei canali del contesto dell'istanza durevole. Questa classe contiene le funzioni comuni di gestione del computer di stato e due membri protetti per applicare e leggere le informazioni di contesto a e da i messaggi.

```csharp
class DurableInstanceContextChannelBase
{
  //…
  protected void ApplyContext(Message message)
  {
    //…
  }
  protected string ReadContextId(Message message)
  {
    //…
  }
}
```

Questi due metodi si avvalgono delle implementazioni `IContextManager` per scrivere e leggere l'ID del contesto a o da il messaggio. (`IContextManager` è un'interfaccia personalizzata utilizzata per definire il contratto per tutti i gestori del contesto). Il canale può includere l'ID del contesto in un'intestazione SOAP personalizzata o in un'intestazione HTTP del cookie. Ogni implementazione dei gestori di contesto eredita dalla classe `ContextManagerBase` che contiene le funzionalità comuni per tutti i gestori del contesto. Il metodo `GetContextId` in questa classe viene utilizzato per originare l'ID del contesto dal client. Quando un ID del contesto viene originato per la prima volta, questo metodo lo salva in un file di testo il cui nome è costituito dall'indirizzo endpoint remoto (i caratteri del nome file non validi degli URI tipici sono sostituiti con il carattere @).

In un secondo momento, quando l'ID del contesto è necessario allo stesso endpoint remoto, il metodo verifica se esiste un file appropriato. Se esiste, il metodo legge l'ID del contesto e termina. In caso contrario, restituisce un ID del contesto appena generato e lo salva in un file. Con la configurazione predefinita, questi file vengono inseriti in una directory denominata ContextStore, che risiede nella directory temporanea dell'utente corrente. Questo percorso è tuttavia configurabile tramite l'elemento di associazione.

Il meccanismo utilizzato per trasportare l'ID del contesto è configurabile. Può essere scritto nell'intestazione HTTP del cookie o in un'intestazione SOAP personalizzata. Se si utilizza l'intestazione SOAP personalizzata, è possibile utilizzare questo protocollo con i protocolli non HTTP (ad esempio, TCP o Named pipe). Le due classi `MessageHeaderContextManager` e `HttpCookieContextManager` implementano queste due opzioni.

Entrambi scrivono l'ID del contesto nel messaggio in modo appropriato. Ad esempio, la classe `MessageHeaderContextManager` lo scrive in un'intestazione SOAP del metodo `WriteContext`.

```csharp
public override void WriteContext(Message message)
{
  string contextId = this.GetContextId();

  MessageHeader contextHeader =
    MessageHeader.CreateHeader(DurableInstanceContextUtility.HeaderName,
      DurableInstanceContextUtility.HeaderNamespace,
      contextId,
      true);

  message.Headers.Add(contextHeader);
}
```

I metodi `ApplyContext` e `ReadContextId` della classe  `DurableInstanceContextChannelBase` richiamano rispettivamente `IContextManager.ReadContext` e `IContextManager.WriteContext`. Questi gestori del contesto non vengono creati direttamente dalla classe `DurableInstanceContextChannelBase`. Viene utilizzata la classe `ContextManagerFactory` per eseguire quel processo.

```csharp
IContextManager contextManager =
                ContextManagerFactory.CreateContextManager(contextType,
                this.contextStoreLocation,
                this.endpointAddress);
```

Il metodo `ApplyContext` viene richiamato dai canali di invio. Inserisce l'ID del contesto nei messaggi in uscita. Il metodo `ReadContextId` viene richiamato dai canali di ricezione. Questo metodo assicura che l'ID del contesto sia disponibile nei messaggi in arrivo e lo aggiunge alla raccolta `Properties` della classe `Message`. Genera inoltre un'eccezione `CommunicationException` in caso di errore nella lettura dell'ID del contesto, facendo in modo che il canale venga interrotto.

```csharp
message.Properties.Add(DurableInstanceContextUtility.ContextIdProperty, contextId);
```

Prima di procedere, è importante comprendere l'utilizzo della raccolta `Properties` nella classe `Message`. In genere, questa raccolta `Properties` viene utilizzata quando si passano dati dai livelli inferiore a quelli superiori dal livello del canale. In questo modo i dati desiderati possono essere forniti ai livelli superiori in modo coerente, indipendentemente dai dettagli del protocollo. In altre parole, il livello del canale può inviare e ricevere l'ID del contesto come intestazione SOAP o intestazione HTTP del cookie. Ma non è necessario che i livelli superiori conoscano questi dettagli, perché il livello del canale rende disponibili queste informazioni nella raccolta `Properties`.

Una volta sistemata la classe `DurableInstanceContextChannelBase` tutte e dieci le interfacce necessarie (IOutputChannel, IInputChannel, IOutputSessionChannel, IInputSessionChannel, IRequestChannel, IReplyChannel, IRequestSessionChannel, IReplySessionChannel, IDuplexChannel, IDuplexSessionChannel) devono essere implementate. Sono simili a tutti i modelli di scambio dei messaggi disponibili (datagramma, simplex, duplex e varianti con sessione). Ognuna di queste implementazioni eredita la classe di base descritta in precedenza `ApplyContext` e `ReadContextId` chiama e in modo appropriato. Ad esempio, `DurableInstanceContextOutputChannel`, il quale implementa l'interfaccia IOutputChannel, chiama il metodo `ApplyContext` da ogni metodo che invia i messaggi.

```csharp
public void Send(Message message, TimeSpan timeout)
{
    // Apply the context information before sending the message.
    this.ApplyContext(message);
    //…
}
```

D'altra parte, `DurableInstanceContextInputChannel` che implementa l' `IInputChannel` interfaccia, chiama il `ReadContextId` metodo in ogni metodo che riceve i messaggi.

```csharp
public Message Receive(TimeSpan timeout)
{
    //…
      ReadContextId(message);
      return message;
}
```

Tranne che in questi casi, queste implementazioni del canale delegano le chiamate al metodo al canale sottostante nello stack di canali. Tuttavia, le varianti con sessione hanno una logica di base per assicurarsi che l'ID del contesto venga inviato e letto solo per il primo messaggio che crea la sessione.

```csharp
if (isFirstMessage)
{
//…
    this.ApplyContext(message);
    isFirstMessage = false;
}
```

Queste implementazioni del `DurableInstanceContextBindingElement` canale vengono quindi aggiunte al runtime del canale WCF dalla classe e `DurableInstanceContextBindingElementSection` dalla classe in modo appropriato. Per ulteriori informazioni sugli elementi di associazione e le sezioni degli elementi di associazione, vedere la documentazione di esempio sul canale [HttpCookieSession](../../../../docs/framework/wcf/samples/httpcookiesession.md) .

## <a name="service-model-layer-extensions"></a>Estensioni del livello del modello di servizio

Ora che l'ID del contesto è stato trasferito utilizzando il livello del canale, il comportamento del servizio può essere implementato per personalizzare la creazione di istanze. In questo esempio, viene utilizzata una gestione archivi per caricare e salvare lo stato a o da l'archivio permanente. Come spiegato in precedenza, questo esempio fornisce una gestione archivi che utilizza SQL Server 2005 come archivio di backup. È tuttavia possibile aggiungere meccanismi di archiviazione personalizzati a questa estensione. Per fare ciò, viene dichiarata un'interfaccia pubblica che deve essere implementata da tutte le gestioni archivi.

```csharp
public interface IStorageManager
{
    object GetInstance(string contextId, Type type);
    void SaveInstance(string contextId, object state);
}
```

La classe `SqlServerStorageManager` contiene l'implementazione `IStorageManager` predefinita. Nel `SaveInstance` metodo, l'oggetto specificato viene serializzato utilizzando XmlSerializer e viene salvato nel database SQL Server.

```csharp
XmlSerializer serializer = new XmlSerializer(state.GetType());
string data;

using (StringWriter writer = new StringWriter(CultureInfo.InvariantCulture))
{
    serializer.Serialize(writer, state);
    data = writer.ToString();
}

using (SqlConnection connection = new SqlConnection(GetConnectionString()))
{
    connection.Open();

    string update = @"UPDATE Instances SET Instance = @instance WHERE ContextId = @contextId";

    using (SqlCommand command = new SqlCommand(update, connection))
    {
        command.Parameters.Add("@instance", SqlDbType.VarChar, 2147483647).Value = data;
        command.Parameters.Add("@contextId", SqlDbType.VarChar, 256).Value = contextId;

        int rows = command.ExecuteNonQuery();

        if (rows == 0)
        {
            string insert = @"INSERT INTO Instances(ContextId, Instance) VALUES(@contextId, @instance)";
            command.CommandText = insert;
            command.ExecuteNonQuery();
        }
    }
}
```

Nel `GetInstance` metodo, i dati serializzati vengono letti per un determinato ID di contesto e l'oggetto costruito da esso viene restituito al chiamante.

```csharp
object data;
using (SqlConnection connection = new SqlConnection(GetConnectionString()))
{
    connection.Open();

    string select = "SELECT Instance FROM Instances WHERE ContextId = @contextId";
    using (SqlCommand command = new SqlCommand(select, connection))
    {
        command.Parameters.Add("@contextId", SqlDbType.VarChar, 256).Value = contextId;
        data = command.ExecuteScalar();
    }
}

if (data != null)
{
    XmlSerializer serializer = new XmlSerializer(type);
    using (StringReader reader = new StringReader((string)data))
    {
        object instance = serializer.Deserialize(reader);
        return instance;
    }
}
```

Non è necessario che gli utenti di queste gestioni archivi creino direttamente un'istanza. Possono utilizzare la classe `StorageManagerFactory` che astrae dai dettagli della creazione della gestione archivi. Questa classe ha uno membro statico, `GetStorageManager`, che crea un'istanza di un tipo di gestione archivi specificato. Se il parametro di tipo è `null`, questo metodo crea un'istanza della classe `SqlServerStorageManager` predefinita e la restituisce. Convalida inoltre il tipo specificato per assicurarsi che implementi l'interfaccia `IStorageManager`.

```csharp
public static IStorageManager GetStorageManager(Type storageManagerType)
{
IStorageManager storageManager = null;

if (storageManagerType == null)
{
    return new SqlServerStorageManager();
}
else
{
    object obj = Activator.CreateInstance(storageManagerType);

    // Throw if the specified storage manager type does not
    // implement IStorageManager.
    if (obj is IStorageManager)
    {
        storageManager = (IStorageManager)obj;
    }
    else
    {
        throw new InvalidOperationException(
                  ResourceHelper.GetString("ExInvalidStorageManager"));
    }

    return storageManager;
}
}
```

L'infrastruttura necessaria per leggere e scrivere istanze dall'archiviazione permanente è implementata. È ora necessario eseguire i passaggi necessari per modificare il comportamento del servizio.

Come primo passaggio di questo processo è necessario salvare l'ID del contesto che è stato trasferito sul InstanceContext attuale utilizzando il livello del canale. InstanceContext è un componente di runtime che funge da collegamento tra il Dispatcher WCF e l'istanza del servizio. Può essere utilizzato per fornire stati e comportamenti aggiuntivi all'istanza del servizio. È essenziale, perché nella comunicazione con sessione l'ID del contesto viene inviato solo con il primo messaggio.

WCF consente di estendere il componente runtime di InstanceContext aggiungendo un nuovo stato e un nuovo comportamento usando il modello di oggetto estensibile. Il modello a oggetti estendibile viene usato in WCF per estendere le classi di runtime esistenti con nuove funzionalità o per aggiungere nuove funzionalità di stato a un oggetto. Nel modello di oggetto estensibile sono disponibili tre interfacce,\<IExtensibleObject t>,\<IExtension t> e IExtensionCollection\<t>:

- L'interfaccia\<IExtensibleObject T> è implementata da oggetti che consentono le estensioni che ne personalizzano la funzionalità.

- L'interfaccia\<IExtension T> viene implementata da oggetti che sono estensioni di classi di tipo T.

- L'interfaccia\<IExtensionCollection T> è una raccolta di IExtensions che consente di recuperare IExtensions in base al tipo.

È pertanto necessario creare una classe InstanceContextExtension che implementi l'interfaccia IExtension e definisca lo stato necessario per salvare l'ID del contesto. Questa classe fornisce inoltre lo stato per memorizzare la gestione archivi utilizzata. Una volta salvato il nuovo stato, non sarà possibile modificarlo. Lo stato viene pertanto fornito e salvato nell'istanza che viene generata in quel momento e vi si potrà accedere soltanto utilizzando le proprietà di sola lettura.

```csharp
// Constructor
public DurableInstanceContextExtension(string contextId,
            IStorageManager storageManager)
{
    this.contextId = contextId;
    this.storageManager = storageManager;
}

// Read only properties
public string ContextId
{
    get { return this.contextId; }
}

public IStorageManager StorageManager
{
    get { return this.storageManager; }
}
```

La classe InstanceContextInitializer implementa l'interfaccia IInstanceContextInitializer e aggiunge l'estensione del contesto di istanza alla raccolta di estensioni dell'InstanceContext che viene generata.

```csharp
public void Initialize(InstanceContext instanceContext, Message message)
{
    string contextId =
  (string)message.Properties[DurableInstanceContextUtility.ContextIdProperty];

    DurableInstanceContextExtension extension =
                new DurableInstanceContextExtension(contextId,
                     storageManager);
    instanceContext.Extensions.Add(extension);
}
```

Come descritto precedentemente, l'ID del contesto viene letto dalla raccolta `Properties` della classe `Message` e passato al costruttore della classe dell'estensione. Questo dimostra che le informazioni possono essere scambiate tra i livelli in modo coerente.

Il successivo passaggio consiste nell'eseguire l'override del processo di creazione dell'istanza di servizio. WCF consente di implementare comportamenti di creazione di istanze personalizzati e di associarli al runtime utilizzando l'interfaccia IInstanceProvider. La nuova classe `InstanceProvider` viene implementata per eseguire quel processo. Il tipo di servizio previsto dal provider di istanze è accettato nel costruttore. In un secondo momento viene utilizzato per creare nuove istanze. Nell' `GetInstance` implementazione di viene creata un'istanza di un gestore di archiviazione che cerca un'istanza salvata in modo permanente. Se restituisce `null`, viene creata un'istanza di una nuova istanza del tipo di servizio e viene restituita al chiamante.

```csharp
public object GetInstance(InstanceContext instanceContext, Message message)
{
    object instance = null;

    DurableInstanceContextExtension extension =
    instanceContext.Extensions.Find<DurableInstanceContextExtension>();

    string contextId = extension.ContextId;
    IStorageManager storageManager = extension.StorageManager;

    instance = storageManager.GetInstance(contextId, serviceType);

    instance ??= Activator.CreateInstance(serviceType);
    return instance;
}
```

Il passaggio importante successivo consiste nell'installare le `InstanceContextExtension`classi `InstanceContextInitializer`, e `InstanceProvider` nel runtime del modello di servizio. È possibile utilizzare un attributo personalizzato per contrassegnare le classi di implementazione del servizio perché installino il comportamento. `DurableInstanceContextAttribute` contiene l'implementazione per questo attributo e implementa l'interfaccia `IServiceBehavior` per estendere l'intero runtime del servizio.

Questa classe è dotata di una proprietà che accetta il tipo della gestione archivi da utilizzare. In questo modo, l'implementazione consente agli utenti di specificare la propria `IStorageManager` implementazione come parametro di questo attributo.

Nell' `ApplyDispatchBehavior` implementazione di, l' `InstanceContextMode` oggetto dell'attributo `ServiceBehavior` corrente viene verificato. Se questa proprietà è impostata su Singleton, non è possibile abilitare la creazione di istanze durevoli e viene generata un'eccezione `InvalidOperationException` per notificare l'host.

```csharp
ServiceBehaviorAttribute serviceBehavior =
    serviceDescription.Behaviors.Find<ServiceBehaviorAttribute>();

if (serviceBehavior != null &&
     serviceBehavior.InstanceContextMode == InstanceContextMode.Single)
{
    throw new InvalidOperationException(
       ResourceHelper.GetString("ExSingletonInstancingNotSupported"));
}
```

Dopodiché le istanze della gestione archivi, dell'inizializzatore del contesto dell'istanza e del provider di istanze vengono  creati e installati nel `DispatchRuntime` creato per ogni endpoint.

```csharp
IStorageManager storageManager =
    StorageManagerFactory.GetStorageManager(storageManagerType);

InstanceContextInitializer contextInitializer =
    new InstanceContextInitializer(storageManager);

InstanceProvider instanceProvider =
    new InstanceProvider(description.ServiceType);

foreach (ChannelDispatcherBase cdb in serviceHostBase.ChannelDispatchers)
{
    ChannelDispatcher cd = cdb as ChannelDispatcher;

    if (cd != null)
    {
        foreach (EndpointDispatcher ed in cd.Endpoints)
        {
            ed.DispatchRuntime.InstanceContextInitializers.Add(contextInitializer);
            ed.DispatchRuntime.InstanceProvider = instanceProvider;
        }
    }
}
```

Per riassumere, questo esempio ha prodotto un canale che abilita il protocollo di rete personalizzato per lo scambio di ID del contesto personalizzati e sovrascrive il comportamento di istanza predefinito per caricare le istanze dall'archivio permanente.

Rimane da trovare un modo per salvare l'istanza del servizio nell'archivio permanente. Come illustrato precedentemente, esiste già la funzionalità necessaria per salvare lo stato in un'implementazione `IStorageManager`. A questo punto è necessario integrare questa operazione con il runtime WCF. È necessario un altro attributo applicabile ai metodi della classe di implementazione del servizio. Questo attributo va applicato ai metodi che modificano lo stato dell'istanza del servizio.

La classe `SaveStateAttribute` implementa questa funzionalità. Implementa `IOperationBehavior` inoltre la classe per modificare il runtime WCF per ogni operazione. Quando un metodo è contrassegnato con questo attributo, il runtime WCF richiama il `ApplyBehavior` metodo mentre viene costruito l' `DispatchOperation` oggetto appropriato. In questa implementazione del metodo è presente una sola riga di codice:

```csharp
dispatch.Invoker = new OperationInvoker(dispatch.Invoker);
```

Questa istruzione crea un'istanza di tipo `OperationInvoker` e la assegna alla proprietà `Invoker` dell'elemento `DispatchOperation` che viene generato. La classe `OperationInvoker` è un wrapper per l'invoker dell'operazione predefinita creato per `DispatchOperation`. La classe implementa l'interfaccia `IOperationInvoker`. Nell'implementazione `Invoke` del metodo, la chiamata al metodo effettiva viene delegata all'invoker dell'operazione interna. Tuttavia, prima di restituire i risultati la gestione archivi in `InstanceContext` viene utilizzata per salvare l'istanza del servizio.

```csharp
object result = innerOperationInvoker.Invoke(instance,
    inputs, out outputs);

// Save the instance using the storage manager saved in the
// current InstanceContext.
InstanceContextExtension extension =
    OperationContext.Current.InstanceContext.Extensions.Find<InstanceContextExtension>();

extension.StorageManager.SaveInstance(extension.ContextId, instance);
return result;
```

## <a name="using-the-extension"></a>Utilizzo dell'estensione

Le estensioni del livello del canale e del livello del modello di servizio vengono eseguite e ora possono essere utilizzate nelle applicazioni WCF. I servizi devono aggiungere il canale nello stack dei canali utilizzando un'associazione personalizzata e quindi contrassegnare le classi di implementazione del servizio con gli attributi appropriati.

```csharp
[DurableInstanceContext]
[ServiceBehavior(InstanceContextMode=InstanceContextMode.PerSession)]
public class ShoppingCart : IShoppingCart
{
//…
     [SaveState]
     public int AddItem(string item)
     {
         //…
     }
//…
 }
```

È necessario che le applicazioni client aggiungano DurableInstanceContextChannel allo stack di canali utilizzando un'associazione personalizzata. Per configurare in modo dichiarativo il canale nel file di configurazione la sezione dell'elemento di associazione deve essere aggiunta alla raccolta delle estensioni degli elementi di associazione.

```xml
<system.serviceModel>
 <extensions>
   <bindingElementExtensions>
     <add name="durableInstanceContext"
type="Microsoft.ServiceModel.Samples.DurableInstanceContextBindingElementSection, DurableInstanceContextExtension, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null"/>
   </bindingElementExtensions>
 </extensions>
</system.serviceModel>
```

È ora possibile utilizzare l'elemento di associazione con un'associazione personalizzata, proprio come gli altri elementi di associazione standard:

```xml
<bindings>
 <customBinding>
   <binding name="TextOverHttp">
     <durableInstanceContext contextType="HttpCookie"/>
     <reliableSession />
     <textMessageEncoding />
     <httpTransport />
   </binding>
 </customBinding>
</bindings>
```

## <a name="conclusion"></a>Conclusioni

In questo esempio viene illustrato come creare un canale del protocollo personalizzato e come personalizzare il comportamento del servizio per abilitarlo.

L'estensione può essere ulteriormente migliorata consentendo agli utenti di specificare l'implementazione `IStorageManager` utilizzando una sezione di configurazione. In questo modo è possibile modificare l'archivio di backup senza ricompilare il codice del servizio.

È inoltre possibile tentare di implementare una classe (ad esempio, `StateBag`) che incapsuli lo stato dell'istanza. Quella classe è responsabile di salvare in modo permanente lo stato quando viene modificato. In questo modo è possibile evitare di utilizzare l'attributo `SaveState` ed eseguire più accuratamente il lavoro di archiviazione permanente (ad esempio, è possibile salvare in modo permanente lo stato solo quando viene davvero modificato piuttosto che salvarlo ogni volta che viene chiamato un metodo con l'attributo `SaveState`).

Quando si esegue l'esempio, viene visualizzato l'output seguente: Il client aggiunge due elementi al carrello degli acquisti e ottiene l'elenco di elementi nel carrello degli acquisti dal servizio. Premere INVIO in tutte le finestre della console per arrestare il servizio e il client.

```console
Enter the name of the product: apples
Enter the name of the product: bananas

Shopping cart currently contains the following items.
apples
bananas
Press ENTER to shut down client
```

> [!NOTE]
> La ricompilazione del servizio si sovrascrive il file di database. Per osservare lo stato salvato in modo permanente in più esecuzioni dell'esempio, assicurarsi di non ricompilare l'esempio tra esecuzioni.

#### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio

1. Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).

2. Per compilare la soluzione, seguire le istruzioni riportate in [compilazione degli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).

3. Per eseguire l'esempio in una configurazione con un solo computer o tra computer diversi, seguire le istruzioni in [esecuzione degli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).

> [!NOTE]
> È necessario che SQL Server 2005 o SQL Express 2005 siano in esecuzione per eseguire questo esempio. Se è in esecuzione SQL Server 2005, è necessario modificare la configurazione della stringa di connessione del servizio. Quando si esegue tra più computer, SQL Server è necessario solo sul server.

> [!IMPORTANT]
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ed esempi. Questo esempio si trova nella directory seguente.
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Instancing\Durable`
