---
title: Modifica dei livelli di condivisione della cache per le attività Send
ms.date: 03/30/2017
ms.assetid: 03926a64-753d-460e-ac06-2a4ff8e1bbf5
ms.openlocfilehash: 101aab98a7d34ad45ad29efbe252cff0814ca290
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185386"
---
# <a name="changing-the-cache-sharing-levels-for-send-activities"></a>Modifica dei livelli di condivisione della cache per le attività Send
L'estensione <xref:System.ServiceModel.Activities.SendMessageChannelCache> consente di personalizzare i livelli di condivisione della cache, le impostazioni della cache della channel factory e della cache del canale per i flussi di lavoro che inviano messaggi agli endpoint del servizio tramite le attività di messaggistica <xref:System.ServiceModel.Activities.Send>. Questi sono in genere flussi di lavoro del client ma potrebbero essere anche servizi del flusso di lavoro ospitati in un oggetto <xref:System.ServiceModel.WorkflowServiceHost>. La cache della channel factory contiene gli oggetti <xref:System.ServiceModel.ChannelFactory%601> memorizzati nella cache. La cache del canale contiene i canali memorizzati nella cache.  
  
> [!NOTE]
> I flussi di lavoro possono utilizzare le attività di messaggistica <xref:System.ServiceModel.Activities.Send> per inviare messaggi o parametri. L'esecuzione del flusso di lavoro aggiunge channel factory alla cache che creano canali di tipo <xref:System.ServiceModel.Channels.IRequestChannel> quando si utilizza un'attività <xref:System.ServiceModel.Activities.ReceiveReply> con un'attività <xref:System.ServiceModel.Activities.Send> e un oggetto <xref:System.ServiceModel.Channels.IOutputChannel> quando si utilizza solo un'attività <xref:System.ServiceModel.Activities.Send> (nessuna attività <xref:System.ServiceModel.Activities.ReceiveReply>).  
  
## <a name="the-cache-sharing-levels"></a>Livelli di condivisione della cache  
 Per impostazione predefinita, in un flusso di lavoro ospitato da un oggetto <xref:System.ServiceModel.WorkflowServiceHost>, la cache utilizzata dalle attività di messaggistica <xref:System.ServiceModel.Activities.Send> è condivisa da tutte le istanze del flusso di lavoro nell'oggetto <xref:System.ServiceModel.WorkflowServiceHost> (memorizzazione nella cache a livello di host). Per un flusso di lavoro del client che non è ospitato da un oggetto <xref:System.ServiceModel.WorkflowServiceHost>, la cache è disponibile solo all'istanza del flusso di lavoro (memorizzazione nella cache a livello di istanza). La cache è disponibile solo per le attività <xref:System.ServiceModel.Activities.Send> che non utilizzano gli endpoint definiti nella configurazione, a meno che non sia abilitata la memorizzazione nella cache non sicura.  
  
 Di seguito sono riportati i diversi livelli di condivisione della cache disponibili per le attività <xref:System.ServiceModel.Activities.Send> in un flusso di lavoro e il relativo utilizzo consigliato:  
  
- **Livello host:** a livello di condivisione host, la cache è disponibile solo per le istanze del flusso di lavoro ospitate nell'host del servizio flusso di lavoro. Una cache può essere condivisa anche tra host del servizio flusso di lavoro di una cache a livello di processo.  
  
- **Livello di**istanza : a livello di condivisione dell'istanza, la cache è disponibile per una determinata istanza del flusso di lavoro per tutta la sua durata, ma la cache non è disponibile per altre istanze del flusso di lavoro.  
  
- **Nessuna cache**: La cache è disattivata per impostazione predefinita se si dispone di un flusso di lavoro che utilizza endpoint definiti nella configurazione. In questo caso, è consigliabile mantenere disattivata la cache anche perché l'attivazione potrebbe risultare non sicura, ad esempio, se per ogni invio è necessaria un'identità diversa (credenziali diverse o utilizzo della rappresentazione).  
  
## <a name="changing-the-cache-sharing-level-for-a-client-workflow"></a>Modifica del livello di condivisione della cache per un flusso di lavoro client  
 Per impostare la condivisione della cache in un flusso di lavoro client, aggiungere un'istanza della classe <xref:System.ServiceModel.Activities.SendMessageChannelCache> come estensione al set desiderato di istanze del flusso di lavoro. In questo modo la cache viene condivisa in tutte le istanze del flusso di lavoro. Negli esempi di codice seguenti viene mostrato come eseguire questi passaggi.  
  
 Innanzitutto, dichiarare un'istanza di tipo <xref:System.ServiceModel.Activities.SendMessageChannelCache>.  
  
```csharp  
// Create an instance of SendMessageChannelCache with default cache settings.  
static SendMessageChannelCache sharedChannelCacheExtension =  
    new SendMessageChannelCache();  
```  
  
 Successivamente, aggiungere l'estensione della cache a ogni istanza del flusso di lavoro client.  
  
```csharp
WorkflowApplication clientInstance1 = new WorkflowApplication(new clientWorkflow1());  
WorkflowApplication clientInstance2 = new WorkflowApplication(new clientWorkflow2());  
  
// Share the cache extension object
  
clientInstance1.Extensions.Add(sharedChannelCacheExtension);  
clientInstance2.Extensions.Add(sharedChannelCacheExtension);  
```  
  
## <a name="changing-the-cache-sharing-level-for-a-hosted-workflow-service"></a>Modifica del livello di condivisione della cache per un servizio di flusso di lavoro ospitato  
 Per impostare la condivisione della cache in un servizio di flusso di lavoro ospitato, aggiungere un'istanza della classe <xref:System.ServiceModel.Activities.SendMessageChannelCache> come estensione a tutti gli host del servizio di flusso di lavoro. In questo modo la cache viene condivisa in tutti gli host del servizio di flusso di lavoro. Negli esempi di codice seguenti viene mostrato come eseguire questi passaggi.  
  
 Innanzitutto, dichiarare un'istanza di tipo <xref:System.ServiceModel.Activities.SendMessageChannelCache> a livello di classe.  
  
```csharp  
// Create static instance of SendMessageChannelCache with default cache settings.  
static SendMessageChannelCache sharedChannelCacheExtension = new  
    SendMessageChannelCache();  
```  
  
 Successivamente, aggiungere l'estensione della cache statica a ogni host del servizio di flusso di lavoro.  
  
```csharp  
WorkflowServiceHost host1 = new WorkflowServiceHost(new serviceWorkflow1(), new Uri(baseAddress1));  
WorkflowServiceHost host2 = new WorkflowServiceHost(new serviceWorkflow2(), new Uri(baseAddress2));  
  
// Share the static cache to get an AppDomain level cache.  
host1.WorkflowExtensions.Add(sharedChannelCacheExtension);  
host2.WorkflowExtensions.Add(sharedChannelCacheExtension);  
```  
  
 Per impostare la divisione della cache in un servizio flusso di lavoro ospitato a livello di istanza, aggiungere un delegato `Func<SendMessageChannelCache>` come estensione all'host del servizio flusso di lavoro e assegnare questo delegato al codice che crea una nuova istanza della classe <xref:System.ServiceModel.Activities.SendMessageChannelCache>. Ciò comporta una cache diversa per ogni singola istanza del flusso di lavoro, anziché una sola cache condivisa da tutte le istanze del flusso di lavoro nell'host del servizio flusso di lavoro. Nell'esempio di codice seguente viene mostrato come eseguire questa operazione tramite un'espressione lambda per definire direttamente l'estensione <xref:System.ServiceModel.Activities.SendMessageChannelCache> a cui il delegato fa riferimento.  
  
```csharp
serviceHost.WorkflowExtensions.Add(() => new SendMessageChannelCache  
{  
    // Use FactorySettings property to add custom factory cache settings.  
    FactorySettings = new ChannelCacheSettings
    { MaxItemsInCache = 5, },  
    // Use ChannelSettings property to add custom channel cache settings.  
    ChannelSettings = new ChannelCacheSettings
    { MaxItemsInCache = 10 },  
});  
```  
  
## <a name="customizing-cache-settings"></a>Personalizzazione delle impostazioni della cache  
 È possibile personalizzare le impostazioni della cache della channel factory e del canale. Le impostazioni della cache sono definite nella classe <xref:System.ServiceModel.Activities.ChannelCacheSettings>. La <xref:System.ServiceModel.Activities.SendMessageChannelCache> classe definisce le impostazioni predefinite della cache per la cache della channel factory e la cache dei canali nel relativo costruttore senza parametri. Nella tabella seguente vengono elencati i valori predefiniti di queste impostazioni per ogni tipo di cache.  
  
|Impostazioni|LeaseTimeout (min)|IdleTimeout (min)|MaxItemsInCache|  
|-|-|-|-|  
|Valore predefinito della cache della factory|TimeSpan.MaxValue|2|16|  
|Valore predefinito della cache del canale|5|2|16|  
  
 Per personalizzare le impostazioni della cache della factory e del canale, creare un'istanza della classe <xref:System.ServiceModel.Activities.SendMessageChannelCache> utilizzando il costruttore con parametri <xref:System.ServiceModel.Activities.SendMessageChannelCache.%23ctor%2A> e passare una nuova istanza dell'oggetto <xref:System.ServiceModel.Activities.ChannelCacheSettings> con valori personalizzati a ognuno dei parametri `factorySettings` e `channelSettings`. Successivamente aggiungere la nuova istanza di questa classe come estensione a un host del servizio di flusso di lavoro o a un'istanza del flusso di lavoro. Nell'esempio di codice seguente viene mostrato come eseguire questi passaggi per un'istanza del flusso di lavoro.  
  
```csharp  
ChannelCacheSettings factorySettings = new ChannelCacheSettings{  
                        MaxItemsInCache = 5,
                        IdleTimeout = TimeSpan.FromMinutes(5),
                        LeaseTimeout = TimeSpan.FromMinutes(20)};  
  
ChannelCacheSettings channelSettings = new ChannelCacheSettings{  
                        MaxItemsInCache = 5,
                        IdleTimeout = TimeSpan.FromMinutes(2),  
                        LeaseTimeout = TimeSpan.FromMinutes(10) };  
  
SendMessageChannelCache customChannelCacheExtension =
    new SendMessageChannelCache(factorySettings, channelSettings);  
  
clientInstance.Extensions.Add(customChannelCacheExtension);  
```  
  
 Per abilitare la memorizzazione nella cache quando il servizio di flusso di lavoro dispone di endpoint definiti nella configurazione, creare un'istanza della classe <xref:System.ServiceModel.Activities.SendMessageChannelCache> utilizzando il costruttore con parametri <xref:System.ServiceModel.Activities.SendMessageChannelCache.%23ctor%2A> con il parametro `allowUnsafeCaching` impostato su `true`. Successivamente aggiungere la nuova istanza di questa classe come estensione a un host del servizio di flusso di lavoro o a un'istanza del flusso di lavoro. Nell'esempio di codice seguente viene mostrato come abilitare la memorizzazione nella cache per un'istanza del flusso di lavoro.  
  
```csharp  
SendMessageChannelCache customChannelCacheExtension =
    new SendMessageChannelCache{ AllowUnsafeCaching = true };  
  
clientInstance.Extensions.Add(customChannelCacheExtension);  
```  
  
 Per disabilitare completamente la cache per le channel factory e i canali, disabilitare la cache della channel factory. In questo modo viene disattivata anche la cache del canale poiché i canali appartengono alle channel factory corrispondenti. Per disabilitare la cache della channel factory, passare il parametro `factorySettings` al costruttore <xref:System.ServiceModel.Activities.SendMessageChannelCache.%23ctor%2A> inizializzato su un'istanza <xref:System.ServiceModel.Activities.ChannelCacheSettings> con un valore <xref:System.ServiceModel.Activities.ChannelCacheSettings.MaxItemsInCache%2A> pari a 0. Nell'esempio di codice seguente viene illustrata questa operazione.  
  
```csharp  
// Disable the factory cache. This results in the channel cache to be turned off as well.  
ChannelCacheSettings factorySettings = new ChannelCacheSettings  
    { MaxItemsInCache = 0 };  
  
ChannelCacheSettings channelSettings = new ChannelCacheSettings();  
  
SendMessageChannelCache customChannelCacheExtension =
    new SendMessageChannelCache(factorySettings, channelSettings);
  
clientInstance.Extensions.Add(customChannelCacheExtension);  
```  
  
 È possibile scegliere di utilizzare solo la cache della channel factory e disabilitare la cache del canale passando il parametro `channelSettings` al costruttore <xref:System.ServiceModel.Activities.SendMessageChannelCache.%23ctor%2A> inizializzato su un'istanza <xref:System.ServiceModel.Activities.ChannelCacheSettings> con un valore <xref:System.ServiceModel.Activities.ChannelCacheSettings.MaxItemsInCache%2A> pari a 0. Nell'esempio di codice seguente viene illustrata questa operazione.  
  
```csharp  
ChannelCacheSettings factorySettings = new ChannelCacheSettings();  
// Disable only the channel cache.  
ChannelCacheSettings channelSettings = new ChannelCacheSettings  
    { MaxItemsInCache = 0};  
  
SendMessageChannelCache customChannelCacheExtension =
    new SendMessageChannelCache(factorySettings, channelSettings);
  
clientInstance.Extensions.Add(customChannelCacheExtension);  
```  
  
 In un servizio flusso di lavoro ospitato è possibile specificare le impostazioni della cache della factory e della cache del canale nel file di configurazione dell'applicazione. A tale scopo, aggiungere un comportamento del servizio contenente le impostazioni della cache della factory e del canale e aggiungere tale comportamento al servizio. Nell'esempio seguente viene illustrato il contenuto `MyChannelCacheBehavior` di un file di configurazione che contiene il comportamento del servizio con le impostazioni personalizzate della cache di factory e della cache dei canali. Questo comportamento del servizio viene `behaviorConfiguration` aggiunto al servizio tramite l'attributo .  
  
```xml  
<configuration>
  <system.serviceModel>  
    <!-- List of other config sections here -->
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="MyChannelCacheBehavior">  
          <sendMessageChannelCache allowUnsafeCaching ="false" >  
            <!-- Control only the host level settings -->
            <factorySettings maxItemsInCache = "8" idleTimeout = "00:05:00" leaseTimeout="10:00:00" />  
            <channelSettings maxItemsInCache = "32" idleTimeout = "00:05:00" leaseTimeout="00:06:00" />  
          </sendMessageChannelCache>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    <services>  
      <service name="MyService" behaviorConfiguration="MyChannelCacheBehavior" />  
    </services>  
  </system.serviceModel>  
</configuration>  
```
