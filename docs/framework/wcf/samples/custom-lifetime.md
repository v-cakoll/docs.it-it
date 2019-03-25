---
title: Durata personalizzata
ms.date: 08/20/2018
ms.assetid: 52806c07-b91c-48fe-b992-88a41924f51f
ms.openlocfilehash: be6013d568e3625c5eac7e0c145db7df1c6917e3
ms.sourcegitcommit: 3630c2515809e6f4b7dbb697a3354efec105a5cd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2019
ms.locfileid: "58410381"
---
# <a name="custom-lifetime"></a>Durata personalizzata

In questo esempio viene illustrato come scrivere un'estensione di Windows Communication Foundation (WCF) per fornire servizi di durata personalizzati per le istanze di servizio condivise di WCF.

> [!NOTE]
> La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo articolo.

## <a name="shared-instancing"></a>Istanze condivise

WCF offre diverse modalità di istanza per le istanze del servizio. La modalità istanze condivise illustrata in questo articolo fornisce un modo per condividere un'istanza del servizio tra più canali. I client possono contattare un metodo factory nel servizio e creare un nuovo canale per avviare la comunicazione. Il frammento di codice seguente illustra come un'applicazione client crea un nuovo canale a un'istanza di servizio esistente:

```csharp
// Create a header for the shared instance id
MessageHeader shareableInstanceContextHeader = MessageHeader.CreateHeader(
        CustomHeader.HeaderName,
        CustomHeader.HeaderNamespace,
        Guid.NewGuid().ToString());

// Create the channel factory
ChannelFactory<IEchoService> channelFactory =
    new ChannelFactory<IEchoService>("echoservice");

// Create the first channel
IEchoService proxy = channelFactory.CreateChannel();

// Call an operation to create shared service instance
using (new OperationContextScope((IClientChannel)proxy))
{
    OperationContext.Current.OutgoingMessageHeaders.Add(shareableInstanceContextHeader);
    Console.WriteLine("Service returned: " + proxy.Echo("Apple"));
}

((IChannel)proxy).Close();

// Create the second channel
IEchoService proxy2 = channelFactory.CreateChannel();

// Call an operation using the same header that will reuse the shared service instance
using (new OperationContextScope((IClientChannel)proxy2))
{
    OperationContext.Current.OutgoingMessageHeaders.Add(shareableInstanceContextHeader);
    Console.WriteLine("Service returned: " + proxy2.Echo("Apple"));
}
```

A differenza di altre modalità di istanza, la modalità istanze condivise dispone di un modo univoco di rilascio di istanze del servizio. Per impostazione predefinita, quando tutti i canali sono chiusi per un' <xref:System.ServiceModel.InstanceContext>, il runtime del servizio WCF controlla se il servizio <xref:System.ServiceModel.InstanceContextMode> è configurato per <xref:System.ServiceModel.InstanceContextMode.PerCall> o <xref:System.ServiceModel.InstanceContextMode.PerSession>e, se così rilasciata l'istanza e le risorse di attestazioni. Se una classe personalizzata <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> è in uso, WCF richiama il <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> metodo per l'implementazione del provider prima di rilasciare l'istanza. Se <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> restituisce `true` l'istanza viene rilasciata, in caso contrario, il <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> implementazione è responsabile della notifica di `Dispatcher` dello stato di inattività tramite un metodo di callback. Questa operazione viene eseguita chiamando il <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.NotifyIdle%2A> metodo del provider.

Questo esempio viene illustrato come è possibile ritardare il rilascio di <xref:System.ServiceModel.InstanceContext> con un timeout di inattività pari a 20 secondi.

## <a name="extending-the-instancecontext"></a>Estensione di InstanceContext

In WCF <xref:System.ServiceModel.InstanceContext> è il collegamento tra l'istanza del servizio e il `Dispatcher`. WCF consente di estendere tale componente runtime tramite l'aggiunta di nuovo stato o comportamento mediante il modello di oggetti estensibili. Questo modello viene utilizzato in WCF per estendere le classi runtime esistenti con nuove funzionalità oppure per aggiungere nuove funzionalità di stato a un oggetto. Nel modello di oggetti estensibili sono disponibili tre interfacce: <xref:System.ServiceModel.IExtensibleObject%601>, <xref:System.ServiceModel.IExtension%601> e <xref:System.ServiceModel.IExtensionCollection%601>.

Il <xref:System.ServiceModel.IExtensibleObject%601> interfaccia viene implementata dagli oggetti che consentono alle estensioni che consentono di personalizzare le relative funzionalità.

L'interfaccia <xref:System.ServiceModel.IExtension%601> viene implementata da oggetti che possono essere estensioni di classi di tipo `T`.

E, infine, il <xref:System.ServiceModel.IExtensionCollection%601> interfaccia è una raccolta di <xref:System.ServiceModel.IExtension%601> implementazioni che consente di recuperare un'implementazione di <xref:System.ServiceModel.IExtension%601> in base al tipo.

Pertanto, per estendere il <xref:System.ServiceModel.InstanceContext>, è necessario implementare il <xref:System.ServiceModel.IExtension%601> interfaccia. In questo progetto di esempio, il `CustomLeaseExtension` classe include tale implementazione.

```csharp
class CustomLeaseExtension : IExtension<InstanceContext>
{
}
```

L'interfaccia <xref:System.ServiceModel.IExtension%601> dispone di due metodi: <xref:System.ServiceModel.IExtension%601.Attach%2A> e <xref:System.ServiceModel.IExtension%601.Detach%2A>. Come implicano i nomi, questi due metodi vengono chiamati quando il runtime connette e disconnette l'estensione a un'istanza della classe <xref:System.ServiceModel.InstanceContext>. In questo esempio, il metodo `Attach` viene utilizzato per tenere traccia dell'oggetto <xref:System.ServiceModel.InstanceContext> appartenente all'istanza corrente dell'estensione.

```csharp
InstanceContext owner;

public void Attach(InstanceContext owner)
{
    this.owner = owner;
}
```

Inoltre, è necessario aggiungere l'implementazione necessaria all'estensione per fornire il supporto di durata estesa. Pertanto, il `ICustomLease` interfaccia viene dichiarata con i metodi desiderati e viene implementato nel `CustomLeaseExtension` classe.

```csharp
interface ICustomLease
{
    bool IsIdle { get; }
    InstanceContextIdleCallback Callback { get; set; }
}

class CustomLeaseExtension : IExtension<InstanceContext>, ICustomLease
{
}
```

Quando WCF richiama il <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> metodo nella <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> implementazione, questa chiamata viene instradata al <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> metodo il `CustomLeaseExtension`. Successivamente, il `CustomLeaseExtension` controlla lo stato privato per vedere se il <xref:System.ServiceModel.InstanceContext> è inattivo. Se è inattivo, viene restituito `true`. In caso contrario, viene avviato un timer per un tempo specificato della durata estesa.

```csharp
public bool IsIdle
{
  get
  {
    lock (thisLock)
    {
      if (isIdle)
      {
        return true;
      }
      else
      {
        StartTimer();
        return false;
      }
    }
  }
}
```

Il timer `Elapsed` evento, la funzione di callback nel Dispatcher viene chiamata per avviare un altro ciclo di pulizia.

```csharp
void idleTimer_Elapsed(object sender, ElapsedEventArgs args)
{
    lock (thisLock)
    {
        StopTimer();
        isIdle = true;
        Utility.WriteMessageToConsole(
            ResourceHelper.GetString("MsgLeaseExpired"));
        callback(owner);
    }
}
```

Non è possibile rinnovare il timer in esecuzione quando arriva un nuovo messaggio per l'istanza viene spostato nello stato inattivo.

L'esempio implementa <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> per intercettare le chiamate al metodo <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> e indirizzarle a `CustomLeaseExtension`. L'implementazione <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> è inclusa nella classe `CustomLifetimeLease`. Il <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> metodo viene richiamato quando sta per rilasciare l'istanza del servizio WCF. Tuttavia, esiste solo un'istanza di una specifica implementazione `ISharedSessionInstance` nella raccolta <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> di ServiceBehavior. Ciò significa che non è possibile sapere se il <xref:System.ServiceModel.InstanceContext> viene chiusa in fase di WCF controlla la <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> (metodo). In questo esempio utilizza pertanto blocchi di thread per serializzare le richieste per il <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> (metodo).

> [!IMPORTANT]
> L'utilizzo di blocchi di thread non è un approccio consigliato perché la serializzazione può influenzare negativamente le prestazioni dell'applicazione.

Un campo membro privato viene usato nel `CustomLifetimeLease` classe per tenere traccia dello stato inattivo e viene restituito dal <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> (metodo). Ogni volta che il <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> metodo viene chiamato, il `isIdle` campo viene restituito e reimpostato su `false`.  È essenziale impostare questo valore su `false` per assicurarsi che il dispatcher chiami il metodo <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.NotifyIdle%2A>.

```csharp
public bool IsIdle(InstanceContext instanceContext)
{
    get
    {
        lock (thisLock)
        {
            //...
            bool idleCopy = isIdle;
            isIdle = false;
            return idleCopy;
        }
    }
}
```

Se il <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A?displayProperty=nameWithType> restituzione del metodo `false`, il Dispatcher registra una funzione di richiamata mediante la <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.NotifyIdle%2A> (metodo). Tale metodo riceve un riferimento al <xref:System.ServiceModel.InstanceContext> rilasciato. Pertanto, il codice di esempio può eseguire una query il `ICustomLease` digitare l'estensione e controllare il `ICustomLease.IsIdle` proprietà nello stato esteso.

```csharp
public void NotifyIdle(InstanceContextIdleCallback callback,
            InstanceContext instanceContext)
{
    lock (thisLock)
    {
       ICustomLease customLease =
           instanceContext.Extensions.Find<ICustomLease>();
       customLease.Callback = callback;
       isIdle = customLease.IsIdle;
       if (isIdle)
       {
             callback(instanceContext);
       }
    }
}
```

Prima di `ICustomLease.IsIdle` proprietà è selezionata, la proprietà di Callback deve essere impostato come ciò è essenziale per `CustomLeaseExtension` notifichi al Dispatcher quando diventa inattivo. Se `ICustomLease.IsIdle` restituisce `true`, il membro privato `isIdle` viene semplicemente impostato in `CustomLifetimeLease` su `true` e chiama il metodo di callback. Poiché il codice contiene un blocco, altri thread non è possibile modificare il valore del membro privato. La volta successiva che chiama Dispatcher e il <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A?displayProperty=nameWithType>, viene restituito `true` e consente al Dispatcher di rilasciare l'istanza.

Una volta completato il lavoro di base per l'estensione personalizzata, quest'ultima deve essere associata al modello del servizio. Per associare il `CustomLeaseExtension` implementazione per il <xref:System.ServiceModel.InstanceContext>, WCF fornisce le <xref:System.ServiceModel.Dispatcher.IInstanceContextInitializer> interfaccia per eseguire l'avvio di <xref:System.ServiceModel.InstanceContext>. Nell'esempio, la classe `CustomLeaseInitializer` implementa tale interfaccia e aggiunge un'istanza di `CustomLeaseExtension` alla raccolta <xref:System.ServiceModel.InstanceContext.Extensions%2A> dalla sola inizializzazione del metodo. Questo metodo viene chiamato dal dispatcher durante l'inizializzazione di <xref:System.ServiceModel.InstanceContext>.

```csharp
public void InitializeInstanceContext(InstanceContext instanceContext,
    System.ServiceModel.Channels.Message message, IContextChannel channel)

    //...

    IExtension<InstanceContext> customLeaseExtension =
        new CustomLeaseExtension(timeout, headerId);
    instanceContext.Extensions.Add(customLeaseExtension);
}
```

 Infine il <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> implementazione è collegata al modello di servizio usando il <xref:System.ServiceModel.Description.IServiceBehavior> implementazione. Tale implementazione viene posizionata nella classe `CustomLeaseTimeAttribute` e deriva dalla classe di base <xref:System.Attribute> per esporre questo comportamento come attributo.

```csharp
public void ApplyDispatchBehavior(ServiceDescription description,
           ServiceHostBase serviceHostBase)
{
    CustomLifetimeLease customLease = new CustomLifetimeLease(timeout);

    foreach (ChannelDispatcherBase cdb in serviceHostBase.ChannelDispatchers)
    {
        ChannelDispatcher cd = cdb as ChannelDispatcher;

        if (cd != null)
        {
            foreach (EndpointDispatcher ed in cd.Endpoints)
            {
                ed.DispatchRuntime.InstanceContextProvider = customLease;
            }
        }
    }
}
```

Questo comportamento può essere aggiunto a una classe del servizio di esempio mediante annotazione con l'attributo `CustomLeaseTime`.

```csharp
[CustomLeaseTime(Timeout = 20000)]
public class EchoService : IEchoService
{
  //…
}
```

Quando si esegue l'esempio, le richieste e le risposte dell'operazione vengono visualizzate nelle finestre della console client e del servizio. Premere INVIO in tutte le finestre della console per arrestare il servizio e il client.

### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio

1. Assicurarsi di aver eseguito il [monouso procedura di installazione per gli esempi di Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).

2. Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](building-the-samples.md).

3. Per eseguire l'esempio in una configurazione singola o tra computer, seguire le istruzioni in [esegue gli esempi di Windows Communication Foundation](running-the-samples.md).

> [!IMPORTANT]
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Instancing\Lifetime`
