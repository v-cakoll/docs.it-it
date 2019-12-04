---
title: Durata personalizzata
ms.date: 08/20/2018
ms.assetid: 52806c07-b91c-48fe-b992-88a41924f51f
ms.openlocfilehash: 8625877d9b4d05d5cf06af2c9f8ef10f701e98db
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/03/2019
ms.locfileid: "74715473"
---
# <a name="custom-lifetime"></a>Durata personalizzata

In questo esempio viene illustrato come scrivere un'estensione Windows Communication Foundation (WCF) per fornire servizi di durata personalizzati per le istanze del servizio WCF condivise.

> [!NOTE]
> La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo articolo.

## <a name="shared-instancing"></a>Istanze condivise

WCF offre diverse modalità di istanza per le istanze del servizio. La modalità di istanza condivisa descritta in questo articolo consente di condividere un'istanza del servizio tra più canali. I client possono contattare un metodo factory nel servizio e creare un nuovo canale per avviare la comunicazione. Il frammento di codice seguente mostra in che modo un'applicazione client crea un nuovo canale per un'istanza del servizio esistente:

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

A differenza di altre modalità di istanza, la modalità istanze condivise dispone di un modo univoco di rilascio di istanze del servizio. Per impostazione predefinita, quando tutti i canali vengono chiusi per un <xref:System.ServiceModel.InstanceContext>, il runtime del servizio WCF verifica se il <xref:System.ServiceModel.InstanceContextMode> del servizio è configurato per <xref:System.ServiceModel.InstanceContextMode.PerCall> o <xref:System.ServiceModel.InstanceContextMode.PerSession>e, in caso affermativo, rilascia l'istanza e dichiara le risorse. Se viene utilizzato un <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> personalizzato, WCF richiama il metodo <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> dell'implementazione del provider prima di rilasciare l'istanza. Se <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> restituisce `true` l'istanza viene rilasciata, in caso contrario l'implementazione di <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> è responsabile della notifica del `Dispatcher` dello stato inattivo tramite un metodo di callback. Questa operazione viene eseguita chiamando il metodo <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.NotifyIdle%2A> del provider.

Questo esempio illustra come è possibile ritardare il rilascio del <xref:System.ServiceModel.InstanceContext> con un timeout di inattività di 20 secondi.

## <a name="extending-the-instancecontext"></a>Estensione di InstanceContext

In WCF <xref:System.ServiceModel.InstanceContext> è il collegamento tra l'istanza del servizio e la `Dispatcher`. WCF consente di estendere questo componente di runtime aggiungendo un nuovo stato o comportamento mediante il modello di oggetti estensibili. Il modello a oggetti estendibile viene usato in WCF per estendere le classi di runtime esistenti con nuove funzionalità o per aggiungere nuove funzionalità di stato a un oggetto. Nel modello di oggetti estensibili sono disponibili tre interfacce: <xref:System.ServiceModel.IExtensibleObject%601>, <xref:System.ServiceModel.IExtension%601> e <xref:System.ServiceModel.IExtensionCollection%601>.

L'interfaccia <xref:System.ServiceModel.IExtensibleObject%601> viene implementata dagli oggetti per consentire le estensioni che ne personalizzano la funzionalità.

L'interfaccia <xref:System.ServiceModel.IExtension%601> viene implementata da oggetti che possono essere estensioni di classi di tipo `T`.

Infine, l'interfaccia <xref:System.ServiceModel.IExtensionCollection%601> è una raccolta di implementazioni di <xref:System.ServiceModel.IExtension%601> che consente di recuperare un'implementazione di <xref:System.ServiceModel.IExtension%601> in base al relativo tipo.

Pertanto, per estendere il <xref:System.ServiceModel.InstanceContext>, è necessario implementare l'interfaccia <xref:System.ServiceModel.IExtension%601>. In questo progetto di esempio, la classe `CustomLeaseExtension` contiene questa implementazione.

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

Inoltre, è necessario aggiungere l'implementazione necessaria all'estensione per fornire il supporto di durata estesa. Pertanto, l'interfaccia `ICustomLease` viene dichiarata con i metodi desiderati ed è implementata nella classe `CustomLeaseExtension`.

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

Quando WCF richiama il metodo <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> nell'implementazione <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider>, questa chiamata viene indirizzata al metodo <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> della `CustomLeaseExtension`. Quindi, il `CustomLeaseExtension` controlla lo stato privato per verificare se il <xref:System.ServiceModel.InstanceContext> è inattivo. Se è inattivo, restituisce `true`. In caso contrario, viene avviato un timer per un tempo specificato della durata estesa.

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

Nell'evento `Elapsed` del timer, la funzione di callback nel Dispatcher viene chiamata per avviare un altro ciclo di pulizia.

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

Non è possibile rinnovare il timer in esecuzione quando arriva un nuovo messaggio per l'istanza spostata allo stato inattivo.

L'esempio implementa <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> per intercettare le chiamate al metodo <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> e indirizzarle a `CustomLeaseExtension`. L'implementazione <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> è inclusa nella classe `CustomLifetimeLease`. Il metodo <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> viene richiamato quando WCF sta per rilasciare l'istanza del servizio. Tuttavia, esiste solo un'istanza di una specifica implementazione `ISharedSessionInstance` nella raccolta <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> di ServiceBehavior. Ciò significa che non esiste alcun modo per sapere se il <xref:System.ServiceModel.InstanceContext> viene chiuso al momento in cui WCF controlla il metodo di <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A>. Pertanto, in questo esempio viene utilizzato il blocco dei thread per serializzare le richieste al metodo <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A>.

> [!IMPORTANT]
> L'utilizzo di blocchi di thread non è un approccio consigliato perché la serializzazione può influenzare negativamente le prestazioni dell'applicazione.

Un campo membro privato viene usato nella classe `CustomLifetimeLease` per tenere traccia dello stato di inattività e viene restituito dal metodo <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A>. Ogni volta che viene chiamato il metodo <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A>, viene restituito il campo `isIdle` e viene reimpostato il `false`.  È essenziale impostare questo valore su `false` per assicurarsi che il dispatcher chiami il metodo <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.NotifyIdle%2A>.

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

Se il metodo <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A?displayProperty=nameWithType> restituisce `false`, il dispatcher registra una funzione di callback utilizzando il metodo <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.NotifyIdle%2A>. Tale metodo riceve un riferimento al <xref:System.ServiceModel.InstanceContext> rilasciato. Pertanto, il codice di esempio può eseguire una query sull'estensione del tipo di `ICustomLease` e controllare la proprietà `ICustomLease.IsIdle` nello stato esteso.

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

Prima di controllare la proprietà `ICustomLease.IsIdle`, è necessario impostare la proprietà di callback perché è essenziale per `CustomLeaseExtension` inviare una notifica al dispatcher quando diventa inattiva. Se `ICustomLease.IsIdle` restituisce `true`, il membro privato `isIdle` viene semplicemente impostato in `CustomLifetimeLease` su `true` e chiama il metodo di callback. Poiché il codice include un blocco, gli altri thread non possono modificare il valore di questo membro privato. Il dispatcher successivo chiama il <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A?displayProperty=nameWithType>, restituisce `true` e consente al dispatcher di rilasciare l'istanza.

Una volta completato il lavoro di base per l'estensione personalizzata, quest'ultima deve essere associata al modello del servizio. Per associare l'implementazione di `CustomLeaseExtension` al <xref:System.ServiceModel.InstanceContext>, WCF fornisce l'interfaccia <xref:System.ServiceModel.Dispatcher.IInstanceContextInitializer> per eseguire il bootstrap dei <xref:System.ServiceModel.InstanceContext>. Nell'esempio, la classe `CustomLeaseInitializer` implementa tale interfaccia e aggiunge un'istanza di `CustomLeaseExtension` alla raccolta <xref:System.ServiceModel.InstanceContext.Extensions%2A> dalla sola inizializzazione del metodo. Questo metodo viene chiamato dal dispatcher durante l'inizializzazione di <xref:System.ServiceModel.InstanceContext>.

```csharp
public void InitializeInstanceContext(InstanceContext instanceContext,
    System.ServiceModel.Channels.Message message, IContextChannel channel)

    //...

    IExtension<InstanceContext> customLeaseExtension =
        new CustomLeaseExtension(timeout, headerId);
    instanceContext.Extensions.Add(customLeaseExtension);
}
```

 Infine, l'implementazione del <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> viene associata al modello del servizio usando l'implementazione di <xref:System.ServiceModel.Description.IServiceBehavior>. Tale implementazione viene posizionata nella classe `CustomLeaseTimeAttribute` e deriva dalla classe di base <xref:System.Attribute> per esporre questo comportamento come attributo.

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

1. Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).

2. Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](building-the-samples.md).

3. Per eseguire l'esempio in una configurazione con un solo computer o tra computer diversi, seguire le istruzioni in [esecuzione degli esempi di Windows Communication Foundation](running-the-samples.md).

> [!IMPORTANT]
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Instancing\Lifetime`
