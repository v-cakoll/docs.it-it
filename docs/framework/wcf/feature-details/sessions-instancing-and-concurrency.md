---
title: Sessioni, istanze e concorrenza
ms.date: 03/30/2017
ms.assetid: 50797a3b-7678-44ed-8138-49ac1602f35b
ms.openlocfilehash: 070e9ed25e2c0cce1309fb27e3f6a02bb01f3d2c
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84600322"
---
# <a name="sessions-instancing-and-concurrency"></a>Sessioni, istanze e concorrenza
Una *sessione* è una correlazione di tutti i messaggi inviati tra due endpoint. La*creazione di istanze* fa riferimento al controllo della durata di oggetti servizio definiti dall'utente e di oggetti <xref:System.ServiceModel.InstanceContext> correlati. La*concorrenza* è il termine dato al controllo del numero di thread in esecuzione contemporaneamente in un <xref:System.ServiceModel.InstanceContext> .  
  
 In questo argomento vengono descritte tali impostazioni, come utilizzarle e le varie interazioni tra di esse.  
  
## <a name="sessions"></a>Sessioni  
 Quando la proprietà <xref:System.ServiceModel.ServiceContractAttribute.SessionMode%2A?displayProperty=nameWithType> viene impostata da un contratto di servizio su <xref:System.ServiceModel.SessionMode.Required?displayProperty=nameWithType>, tutte le chiamate, ovvero gli scambi di messaggi sottostanti che supportano le chiamate, devono essere parte della stessa conversazione. Se un contratto consente sessioni ma non ne richiede, i client possono connettersi e possono stabilire o meno una sessione. Se, al termine della sessione, un messaggio viene inviato sullo stesso canale basato sulla sessione, viene generata un'eccezione.  
  
 Le sessioni WCF presentano le funzionalità concettuali principali seguenti:  
  
- Vengono avviate e terminate esplicitamente dall'applicazione chiamante.  
  
- I messaggi recapitati durante una sessione vengono elaborati nell'ordine in cui vengono ricevuti.  
  
- Le sessioni consentono di correlare un gruppo di messaggi in una conversazione. Il significato di tale correlazione è un'astrazione. Un canale basato sulla sessione, ad esempio, è in grado di correlare messaggi basati su una connessione di rete condivisa mentre un altro canale basato sulla sessione è in grado di correlare messaggi basati su un tag condiviso nel corpo del messaggio. Le funzionalità che possono derivare dalla sessione dipendono dalla natura della correlazione.  
  
- Nessun archivio dati generale associato a una sessione WCF.  
  
 Se si ha familiarità con la <xref:System.Web.SessionState.HttpSessionState?displayProperty=nameWithType> classe nelle applicazioni ASP.NET e con la funzionalità fornita, è possibile notare le differenze seguenti tra questo tipo di sessione e le sessioni WCF:  
  
- Le sessioni ASP.NET sono sempre avviate dal server.  
  
- Le sessioni ASP.NET sono implicitamente non ordinate.  
  
- Le sessioni ASP.NET forniscono un meccanismo di archiviazione dati generale per tutte le richieste.  
  
 Le applicazioni client e le applicazioni di servizio interagiscono con le sessioni in modi diversi. Le applicazioni client avviano sessioni e quindi ricevono ed elaborano i messaggi inviati all'interno della sessione. Le applicazioni di servizio possono utilizzare le sessioni come punto di estensibilità per aggiungere comportamenti. Ciò si ottiene utilizzando direttamente <xref:System.ServiceModel.InstanceContext> o implementando un provider di contesto dell'istanza personalizzato.  
  
## <a name="instancing"></a>creazione di istanze  
 Il comportamento delle istanze (impostato tramite la proprietà <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A?displayProperty=nameWithType> ) consente di controllare come viene creato <xref:System.ServiceModel.InstanceContext> in risposta ai messaggi in ingresso. Per impostazione predefinita, ogni <xref:System.ServiceModel.InstanceContext> viene associato a uno oggetto servizio definito dall'utente. In questo modo l'impostazione (nel caso predefinito) della proprietà <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> consente di controllare anche le istanze di oggetti servizio definiti dall'utente. L'enumerazione <xref:System.ServiceModel.InstanceContextMode> definisce le modalità di istanza.  
  
 Sono disponibili le modalità di istanza seguenti:  
  
- <xref:System.ServiceModel.InstanceContextMode.PerCall>: viene creato un nuovo <xref:System.ServiceModel.InstanceContext> (e di conseguenza l'oggetto servizio) per ogni richiesta client.  
  
- <xref:System.ServiceModel.InstanceContextMode.PerSession>: viene creato un nuovo <xref:System.ServiceModel.InstanceContext> (e di conseguenza l'oggetto servizio) per ogni sessione client nuova e viene mantenuto per la durata di quella sessione (è necessaria un'associazione che supporti sessioni).  
  
- <xref:System.ServiceModel.InstanceContextMode.Single>: un unico <xref:System.ServiceModel.InstanceContext> (e di conseguenza l'oggetto servizio) gestisce tutte le richieste client per la durata dell'applicazione.  
  
 Nell'esempio di codice seguente viene illustrato il valore <xref:System.ServiceModel.InstanceContextMode> predefinito, con <xref:System.ServiceModel.InstanceContextMode.PerSession> impostato esplicitamente su una classe del servizio.  
  
```csharp  
[ServiceBehavior(InstanceContextMode=InstanceContextMode.PerSession)]
public class CalculatorService : ICalculatorInstance
{
    ...  
}  
```  
  
 Mentre la proprietà <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A?displayProperty=nameWithType> consente di controllare la frequenza di rilascio di <xref:System.ServiceModel.InstanceContext> , le proprietà <xref:System.ServiceModel.OperationBehaviorAttribute.ReleaseInstanceMode%2A?displayProperty=nameWithType> e <xref:System.ServiceModel.ServiceBehaviorAttribute.ReleaseServiceInstanceOnTransactionComplete%2A?displayProperty=nameWithType> consentono di controllare quando l'oggetto servizio viene rilasciato.  
  
### <a name="well-known-singleton-services"></a>Servizi Singleton noti  
 Una variazione su oggetti servizio di una singola istanza può a volte essere utile. È infatti possibile creare un oggetto servizio e quindi creare l'host del servizio tramite quell'oggetto. A tale scopo, è necessario impostare la proprietà <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A?displayProperty=nameWithType> su <xref:System.ServiceModel.InstanceContextMode.Single> , in caso contrario verrà generata un'eccezione quando l'host del servizio viene aperto.  
  
 Utilizzare il costruttore <xref:System.ServiceModel.ServiceHost.%23ctor%28System.Object%2CSystem.Uri%5B%5D%29> per creare tale servizio. Fornisce un'alternativa all'implementazione di un'interfaccia <xref:System.ServiceModel.Dispatcher.IInstanceContextInitializer?displayProperty=nameWithType> personalizzata quando si desidera fornire un'istanza specifica dell'oggetto utilizzabile da un servizio singleton. È possibile utilizzare questo overload quando il tipo di implementazione del servizio è difficile da costruire, ad esempio se non implementa un costruttore pubblico senza parametri.  
  
 Si noti che quando un oggetto viene fornito a questo costruttore, alcune funzionalità relative al comportamento di creazione delle istanze di Windows Communication Foundation (WCF) funzionano in modo diverso. La chiamata, ad esempio, di <xref:System.ServiceModel.InstanceContext.ReleaseServiceInstance%2A?displayProperty=nameWithType> non ha effetto quando viene fornita l'istanza di un oggetto Singleton. Analogamente, qualsiasi altro meccanismo di rilascio delle istanze viene ignorato. L'host <xref:System.ServiceModel.ServiceHost> si comporta sempre come se la proprietà <xref:System.ServiceModel.OperationBehaviorAttribute.ReleaseInstanceMode%2A?displayProperty=nameWithType> fosse impostata su <xref:System.ServiceModel.ReleaseInstanceMode.None?displayProperty=nameWithType> per tutte le operazioni.  
  
### <a name="sharing-instancecontext-objects"></a>Condivisione di oggetti InstanceContext  
 È inoltre possibile controllare l'associazione tra canali o chiamate con sessione e oggetti <xref:System.ServiceModel.InstanceContext> eseguendo quell'associazione.  
  
## <a name="concurrency"></a>Concorrenza  
 La concorrenza è il controllo del numero di thread attivi in un <xref:System.ServiceModel.InstanceContext> contemporaneamente. Viene controllato tramite <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A?displayProperty=nameWithType> con l'enumerazione <xref:System.ServiceModel.ConcurrencyMode> .  
  
 Sono disponibili le tre modalità di concorrenza seguenti:  
  
- <xref:System.ServiceModel.ConcurrencyMode.Single>: ogni contesto dell'istanza può avere al massimo un thread alla volta per l'elaborazione dei messaggi nel contesto dell'istanza. Altri thread che devono utilizzare lo stesso contesto dell'istanza, devono restare bloccati fino alla chiusura del thread originale dal contesto dell'istanza.  
  
- <xref:System.ServiceModel.ConcurrencyMode.Multiple>: ogni istanza del servizio può avere contemporaneamente più thread per l'elaborazione messaggi. Per essere in grado di usare questa modalità di concorrenza, l'implementazione del servizio deve essere thread-safe.  
  
- <xref:System.ServiceModel.ConcurrencyMode.Reentrant>: ogni istanza del servizio elabora un messaggio alla volta ma accetta chiamate di operazioni rientranti. Il servizio accetta queste chiamate solo quando viene chiamato tramite un oggetto client WCF.  
  
> [!NOTE]
> Può essere difficile comprendere, scrivere correttamente e sviluppare codice che utilizza in modo sicuro più di un thread. Prima di utilizzare valori <xref:System.ServiceModel.ConcurrencyMode.Multiple> o <xref:System.ServiceModel.ConcurrencyMode.Reentrant> , verificare che il servizio sia progettato correttamente per queste modalità. Per altre informazioni, vedere <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A>.  
  
 L'uso della concorrenza è correlato alla modalità di istanza. Nelle <xref:System.ServiceModel.InstanceContextMode.PerCall> istanze la concorrenza non è pertinente perché ogni messaggio viene elaborato da un nuovo <xref:System.ServiceModel.InstanceContext> e, pertanto, non è mai presente più di un thread attivo in <xref:System.ServiceModel.InstanceContext> .  
  
 Nell'esempio di codice seguente viene illustrata l'impostazione della proprietà <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A> su <xref:System.ServiceModel.ConcurrencyMode.Multiple>.  
  
```csharp
[ServiceBehavior(ConcurrencyMode=ConcurrencyMode.Multiple, InstanceContextMode = InstanceContextMode.Single)]
public class CalculatorService : ICalculatorConcurrency
{
    ...  
}  
```  
  
## <a name="sessions-interact-with-instancecontext-settings"></a>Sessioni che interagiscono con impostazioni InstanceContext  
 L'interazione di sessioni e di <xref:System.ServiceModel.InstanceContext> , che dipendono dalla combinazione tra il valore dell'enumerazione <xref:System.ServiceModel.SessionMode> in un contratto e la proprietà <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A?displayProperty=nameWithType> nell'implementazione del servizio, consente di controllare l'associazione tra canali e oggetti servizio specifici.  
  
 Nella tabella seguente viene mostrato il risultato di un canale in ingresso in cui le sessioni sono supportate o non supportate. Tale risultato è in funzione della combinazione dei valori delle proprietà <xref:System.ServiceModel.ServiceContractAttribute.SessionMode%2A?displayProperty=nameWithType> e <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A?displayProperty=nameWithType> del servizio.  
  
|Valore InstanceContextMode|<xref:System.ServiceModel.SessionMode.Required>|<xref:System.ServiceModel.SessionMode.Allowed>|<xref:System.ServiceModel.SessionMode.NotAllowed>|  
|-------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------|  
|PerCall|-Comportamento con canale con sessione: una sessione e <xref:System.ServiceModel.InstanceContext> per ogni chiamata.<br />-Comportamento con canale senza sessione: viene generata un'eccezione.|-Comportamento con canale con sessione: una sessione e <xref:System.ServiceModel.InstanceContext> per ogni chiamata.<br />-Comportamento con canale senza sessione: un oggetto <xref:System.ServiceModel.InstanceContext> per ogni chiamata.|-Comportamento con il canale con sessione: viene generata un'eccezione.<br />-Comportamento con canale senza sessione: un oggetto <xref:System.ServiceModel.InstanceContext> per ogni chiamata.|  
|PerSession|-Comportamento con canale con sessione: una sessione e <xref:System.ServiceModel.InstanceContext> per ogni canale.<br />-Comportamento con canale senza sessione: viene generata un'eccezione.|-Comportamento con canale con sessione: una sessione e <xref:System.ServiceModel.InstanceContext> per ogni canale.<br />-Comportamento con canale senza sessione: un oggetto <xref:System.ServiceModel.InstanceContext> per ogni chiamata.|-Comportamento con il canale con sessione: viene generata un'eccezione.<br />-Comportamento con canale senza sessione: un oggetto <xref:System.ServiceModel.InstanceContext> per ogni chiamata.|  
|Single|-Comportamento con canale con sessione: una sessione e una <xref:System.ServiceModel.InstanceContext> per tutte le chiamate.<br />-Comportamento con canale senza sessione: viene generata un'eccezione.|-Comportamento con canale con sessione: una sessione e <xref:System.ServiceModel.InstanceContext> per il singleton creato o specificato dall'utente.<br />-Comportamento con canale senza sessione: un oggetto <xref:System.ServiceModel.InstanceContext> per il singleton creato o specificato dall'utente.|-Comportamento con il canale con sessione: viene generata un'eccezione.<br />-Comportamento con canale senza sessione: un <xref:System.ServiceModel.InstanceContext> per ogni singleton creato o per il singleton specificato dall'utente.|  
  
## <a name="see-also"></a>Vedere anche

- [Uso di sessioni](../using-sessions.md)
- [Procedura: creare un servizio che richiede sessioni](how-to-create-a-service-that-requires-sessions.md)
- [Procedura: Controllare le istanze del servizio](how-to-control-service-instancing.md)
- [Concorrenza](../samples/concurrency.md)
- [creazione di istanze](../samples/instancing.md)
- [Sessione](../samples/session.md)
