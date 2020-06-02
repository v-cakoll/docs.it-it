---
title: Suggerimenti per l'implementazione del modello asincrono basato su eventi
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- Event-based Asynchronous Pattern
- ProgressChangedEventArgs class
- BackgroundWorker component
- events [.NET Framework], asynchronous
- AsyncOperationManager class
- threading [.NET Framework], asynchronous features
- AsyncOperation class
- AsyncCompletedEventArgs class
ms.assetid: 4acd2094-4f46-4eff-9190-92d0d9ff47db
ms.openlocfilehash: 66979415f2951acc78dc4eb7b2aafe3c84e85397
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84289941"
---
# <a name="best-practices-for-implementing-the-event-based-asynchronous-pattern"></a>Suggerimenti per l'implementazione del modello asincrono basato su eventi
Il modello asincrono basato su eventi offre un sistema efficace per l'esposizione del comportamento asincrono nelle classi attraverso una semantica nota di eventi e delegati. Per implementare tale modello, è necessario soddisfare alcuni requisiti comportamentali specifici. Nelle sezioni riportate di seguito vengono illustrati i requisiti e le indicazioni da tenere presenti per l'implementazione di una classe che segue il modello asincrono basato su eventi.  
  
 Per informazioni generali, vedere [Implementazione del modello asincrono basato su eventi](implementing-the-event-based-asynchronous-pattern.md).  
  
## <a name="required-behavioral-guarantees"></a>Garanzie comportamentali richieste  
 Se si implementa il modello asincrono basato su eventi, è necessario fornire garanzie sul comportamento della classe e sull'affidabilità di tale comportamento per i client.  
  
### <a name="completion"></a>Completion  
 Richiamare sempre il gestore eventi <em>NomeMetodo</em>**Completed** in caso di completamento, errore o annullamento. È infatti consigliabile che le applicazioni non si trovino mai in una situazione permanente di inattività nella quale il completamento non si verifica mai. Fa eccezione a questa regola il caso in cui l'operazione asincrona stessa sia progettata per non essere mai completata.  
  
### <a name="completed-event-and-eventargs"></a>Eventi Completed e classi EventArgs  
 Per ogni metodo**Async** <em>MethodName</em>separato, applicare i requisiti di progettazione seguenti:  
  
- Definire un evento <em>MethodName</em>**Completed** sulla stessa classe del metodo.  
  
- Definire una <xref:System.EventArgs> classe e un delegato associato per l'evento <em>NomeMetodo</em>**Completed** che deriva dalla <xref:System.ComponentModel.AsyncCompletedEventArgs> classe. Il nome predefinito della classe deve avere il formato <em>MethodName</em>**CompletedEventArgs**.  
  
- Verificare che la classe <xref:System.EventArgs> sia specifica dei valori restituiti del metodo <em>NomeMetodo</em>. Quando si usa la classe <xref:System.EventArgs>, è consigliabile non richiedere mai agli sviluppatori di eseguire il cast del risultato.  
  
     Nell'esempio di codice seguente vengono illustrate rispettivamente un'implementazione valida e non valida del requisito di progettazione in questione.  
  
```csharp  
// Good design  
private void Form1_MethodNameCompleted(object sender, xxxCompletedEventArgs e)
{
    DemoType result = e.Result;  
}  
  
// Bad design  
private void Form1_MethodNameCompleted(object sender, MethodNameCompletedEventArgs e)
{
    DemoType result = (DemoType)(e.Result);  
}  
```  
  
- Non definire una classe <xref:System.EventArgs> per restituire metodi che restituiscono `void`. Usare invece un'istanza della classe <xref:System.ComponentModel.AsyncCompletedEventArgs>.  
  
- Assicurarsi di generare sempre l'evento <em>MethodName</em>**Completed** . Questo evento deve essere generato in caso di corretto completamento, errore o annullamento. È infatti consigliabile che le applicazioni non si trovino mai in una situazione permanente di inattività nella quale il completamento non si verifica mai.  
  
- Assicurarsi di intercettare le eccezioni che si verificano nell'operazione asincrona e assegnare l'eccezione intercettata alla proprietà <xref:System.ComponentModel.AsyncCompletedEventArgs.Error%2A>.  
  
- Se si è verificato un errore durante il completamento dell'attività, è possibile che i risultati non siano accessibili. Quando la proprietà <xref:System.ComponentModel.AsyncCompletedEventArgs.Error%2A> non è `null`, assicurarsi che l'accesso a qualsiasi proprietà nella struttura <xref:System.EventArgs> generi un'eccezione. Usare il metodo <xref:System.ComponentModel.AsyncCompletedEventArgs.RaiseExceptionIfNecessary%2A> per eseguire questa verifica.  
  
- Modellare un timeout come errore. Quando si verifica un timeout, generare l'evento <em>MethodName</em>**Completed** e assegnare un oggetto <xref:System.TimeoutException> alla <xref:System.ComponentModel.AsyncCompletedEventArgs.Error%2A> Proprietà.  
  
- Se la classe supporta più chiamate simultanee, assicurarsi che l'evento <em>MethodName</em>**Completed** contenga l' `userSuppliedState` oggetto appropriato.  
  
- Verificare che l'evento <em>MethodName</em>**Completed** venga generato nel thread appropriato e nel momento appropriato del ciclo di vita dell'applicazione. Per altre informazioni, vedere la sezione Thread e contesti.  
  
### <a name="simultaneously-executing-operations"></a>Esecuzione simultanea di operazioni  
  
- Se la classe supporta più chiamate simultanee, consentire allo sviluppatore di tenere traccia di ogni chiamata separatamente definendo l'overload <em>MethodName</em>**asincrono** di NomeMetodo che accetta un parametro di stato con valori di oggetto, o un ID attività, denominato `userSuppliedState` . Questo parametro deve essere sempre l'ultimo parametro della firma del metodo**Async** <em>MethodName</em>.  
  
- Se la classe definisce l'overload**asincrono** di <em>NomeMetodo</em>che accetta un parametro di stato con valori di oggetto, o un ID attività, tenere traccia del ciclo di vita dell'operazione con tale ID e assicurarsi di riportarlo nel gestore di completamento. Per l'esecuzione di tali operazioni sono disponibili classi di supporto specifiche. Per altre informazioni sulla gestione della concorrenza, vedere [Procedura: implementare un componente che supporta il modello asincrono basato su eventi](component-that-supports-the-event-based-asynchronous-pattern.md).  
  
- Se la classe definisce il metodo**Async** <em>MethodName</em>senza il parametro di stato e non supporta più chiamate simultanee, assicurarsi che qualsiasi tentativo di richiamare <em>MethodName</em>**Async** prima del completamento della chiamata**asincrona** di <em>NomeMetodo precedente generi</em>un oggetto <xref:System.InvalidOperationException> .  
  
- In generale, non generare un'eccezione se il metodo**Async** <em>MethodName</em>senza il `userSuppliedState` parametro viene richiamato più volte in modo che siano presenti più operazioni in attesa. È possibile generare un'eccezione quando la classe non può gestire questa situazione, ma si presuppone che gli sviluppatori possano gestire i diversi callback indistinguibili in corso.  
  
### <a name="accessing-results"></a>Accesso ai risultati  
  
- Se durante l'esecuzione dell'operazione asincrona si è verificato un errore, è possibile che i risultati non siano accessibili. Verificare che l'accesso a qualsiasi proprietà in <xref:System.ComponentModel.AsyncCompletedEventArgs> quando <xref:System.ComponentModel.AsyncCompletedEventArgs.Error%2A> non è `null` generi l'eccezione a cui fa riferimento <xref:System.ComponentModel.AsyncCompletedEventArgs.Error%2A>. La classe <xref:System.ComponentModel.AsyncCompletedEventArgs> fornisce il metodo <xref:System.ComponentModel.AsyncCompletedEventArgs.RaiseExceptionIfNecessary%2A> a questo scopo.  
  
- Assicurarsi che i tentativi di accesso al risultato generino un'eccezione di tipo <xref:System.InvalidOperationException> che segnala l'avvenuto annullamento dell'operazione. Usare il metodo <xref:System.ComponentModel.AsyncCompletedEventArgs.RaiseExceptionIfNecessary%2A?displayProperty=nameWithType> per eseguire questa verifica.  
  
### <a name="progress-reporting"></a>Report di stato  
  
- Garantire il supporto della generazione di report sullo stato di avanzamento, se possibile, per consentire agli sviluppatori di offrire prestazioni ottimali dell'applicazione durante l'utilizzo della classe.  
  
- Se si implementa un evento **ProgressChanged** o <em>MethodName</em>**ProgressChanged** , assicurarsi che non siano stati generati eventi di questo tipo per una determinata operazione asincrona dopo la generazione dell'evento <em>MethodName</em>**Completed** dell'operazione.  
  
- In caso di popolamento della classe <xref:System.ComponentModel.ProgressChangedEventArgs> standard, accertarsi che la proprietà <xref:System.ComponentModel.ProgressChangedEventArgs.ProgressPercentage%2A> possa essere sempre interpretata come percentuale. Non è necessario che il valore di percentuale sia preciso, purché si tratti di un valore di percentuale. Se l'unità di misura dei report sullo stato di avanzamento deve essere diversa da una percentuale, derivare una classe dalla classe <xref:System.ComponentModel.ProgressChangedEventArgs> e lasciare impostato su 0 il valore di <xref:System.ComponentModel.ProgressChangedEventArgs.ProgressPercentage%2A>. Evitare di usare unità di misura dei report diverse dalla percentuale.  
  
- Verificare che l'evento `ProgressChanged` venga generato sul thread appropriato nel momento adeguato del ciclo di vita dell'applicazione. Per altre informazioni, vedere la sezione Thread e contesti.  
  
### <a name="isbusy-implementation"></a>Implementazione della proprietà IsBusy  
  
- Non esporre una proprietà `IsBusy` se la classe supporta più chiamate simultanee. I proxy dei servizi Web XML, ad esempio, non espongono una proprietà `IsBusy` in quanto supportano più chiamate simultanee dei metodi asincroni.  
  
- La `IsBusy` proprietà deve restituire `true` dopo che il metodo**Async** <em>MethodName</em>è stato chiamato e prima che venga generato l'evento <em>MethodName</em>**Completed** . In caso contrario, deve restituire `false`. I componenti <xref:System.ComponentModel.BackgroundWorker> e <xref:System.Net.WebClient> sono esempi di classi che espongono una proprietà `IsBusy`.  
  
### <a name="cancellation"></a>Annullamento  
  
- Garantire il supporto dell'annullamento, se possibile, per consentire agli sviluppatori di offrire prestazioni ottimali dell'applicazione durante l'utilizzo della classe.  
  
- In caso di annullamento, impostare il flag <xref:System.ComponentModel.AsyncCompletedEventArgs.Cancelled%2A> nell'oggetto <xref:System.ComponentModel.AsyncCompletedEventArgs>.  
  
- Assicurarsi che i tentativi di accesso al risultato generino un'eccezione di tipo <xref:System.InvalidOperationException> che segnala l'avvenuto annullamento dell'operazione. Usare il metodo <xref:System.ComponentModel.AsyncCompletedEventArgs.RaiseExceptionIfNecessary%2A?displayProperty=nameWithType> per eseguire questa verifica.  
  
- Verificare che le chiamate a un metodo di annullamento vengano eseguite correttamente senza mai generare un'eccezione. Generalmente, a un client viene notificato se un'operazione è realmente annullabile in qualsiasi momento mentre non viene notificato se un annullamento già avviato ha avuto esito positivo. All'applicazione viene invece sempre notificato l'avvenuto annullamento, poiché lo stato di completamento dipende anche dall'applicazione.  
  
- Genera l'evento <em>MethodName</em>**Completed** quando viene annullata l'operazione.  
  
### <a name="errors-and-exceptions"></a>Errori ed eccezioni  
  
- Intercettare le eccezioni che si verificano nell'operazione asincrona e impostare il valore della proprietà <xref:System.ComponentModel.AsyncCompletedEventArgs.Error%2A?displayProperty=nameWithType> su tali eccezioni.  
  
### <a name="threading-and-contexts"></a>Thread e contesti  
 Per un corretto funzionamento della classe, è fondamentale che i gestori eventi del client siano chiamati sul thread o sul contesto appropriato per il modello di applicazione specifico, incluse le applicazioni ASP.NET e Windows Forms. Per garantire il comportamento corretto della classe asincrona con qualsiasi modello di applicazione sono disponibili due classi di supporto, <xref:System.ComponentModel.AsyncOperation> e <xref:System.ComponentModel.AsyncOperationManager>.  
  
 <xref:System.ComponentModel.AsyncOperationManager> fornisce un metodo, <xref:System.ComponentModel.AsyncOperationManager.CreateOperation%2A>, che restituisce un oggetto <xref:System.ComponentModel.AsyncOperation>. Il metodo**Async** <em>Method</em>chiama <xref:System.ComponentModel.AsyncOperationManager.CreateOperation%2A> e la classe usa l'oggetto restituito <xref:System.ComponentModel.AsyncOperation> per tenere traccia della durata dell'attività asincrona.  
  
 Per generare report destinati al client sullo stato di avanzamento, sui risultati incrementali e sul completamento, chiamare i metodi <xref:System.ComponentModel.AsyncOperation.Post%2A> e <xref:System.ComponentModel.AsyncOperation.OperationCompleted%2A> sull'oggetto <xref:System.ComponentModel.AsyncOperation>. <xref:System.ComponentModel.AsyncOperation> è responsabile del marshalling delle chiamate sui gestori eventi del client al thread o al contesto appropriato.  
  
> [!NOTE]
> È possibile aggirare queste regole se si vuole esplicitamente evitare l'uso dei criteri del modello di applicazione, pur usufruendo degli altri vantaggi derivanti dal modello asincrono basato su eventi. È ad esempio possibile creare una classe threading Free operante in Windows Form, purché agli sviluppatori siano chiare le restrizioni implicate. Le applicazioni console non sincronizzano l'esecuzione delle chiamate del metodo <xref:System.ComponentModel.AsyncOperation.Post%2A>. L'ordine di generazione degli eventi `ProgressChanged` potrebbe quindi non essere corretto. Se si vuole l'esecuzione serializzata delle chiamate al metodo <xref:System.ComponentModel.AsyncOperation.Post%2A>, implementare e installare una classe <xref:System.Threading.SynchronizationContext?displayProperty=nameWithType>.  
  
 Per altre informazioni sull'uso di <xref:System.ComponentModel.AsyncOperation> e <xref:System.ComponentModel.AsyncOperationManager> per abilitare le operazioni asincrone, vedere [Procedura: implementare un componente che supporta il modello asincrono basato su eventi](component-that-supports-the-event-based-asynchronous-pattern.md).  
  
## <a name="guidelines"></a>Linee guida  
  
- È preferibile che ogni chiamata a un metodo sia indipendente dalle altre. Si consiglia di evitare di associare chiamate a risorse condivise. Se le risorse devono essere condivise tra le chiamate, è necessario fornire un meccanismo di sincronizzazione adeguato nell'implementazione.  
  
- Non sono consigliati progetti in cui al client sia richiesta l'implementazione della funzionalità di sincronizzazione. Si supponga il caso di un metodo asincrono che riceve un oggetto statico globale come parametro. Più chiamate simultanee a tale metodo potrebbero determinare il danneggiamento dei dati o deadlock.  
  
- Se si implementa un metodo con l'overload a più chiamate (`userState` nella firma), la classe dovrà gestire un insieme di stati utente, o ID attività, e le relative operazioni in sospeso. Questa raccolta deve essere protetta con aree `lock`, in quanto le varie chiamate aggiungono e rimuovono gli oggetti `userState` presenti al suo interno.  
  
- Riutilizzare le classi `CompletedEventArgs`, quando possibile e appropriato. In tal caso, la denominazione non sarà coerente con il nome del metodo, poiché un determinato delegato e il tipo <xref:System.EventArgs> non saranno collegati a un unico metodo. Non è tuttavia accettabile imporre agli sviluppatori di eseguire il cast del valore recuperato da una proprietà sull'oggetto <xref:System.EventArgs>.  
  
- Se si sta creando una classe che deriva da <xref:System.ComponentModel.Component>, non implementare e installare la propria classe <xref:System.Threading.SynchronizationContext>. Sono i modelli di applicazione e non i componenti a controllare l'oggetto <xref:System.Threading.SynchronizationContext> usato.  
  
- L'uso di qualsiasi tipo di multithreading determina la potenziale esposizione a bug seri e complessi. Prima di implementare una soluzione che preveda l'uso del multithreading, vedere [Procedure consigliate per l'uso del threading gestito](../threading/managed-threading-best-practices.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ComponentModel.AsyncOperation>
- <xref:System.ComponentModel.AsyncOperationManager>
- <xref:System.ComponentModel.AsyncCompletedEventArgs>
- <xref:System.ComponentModel.ProgressChangedEventArgs>
- <xref:System.ComponentModel.BackgroundWorker>
- [Implementazione del modello asincrono basato su eventi](implementing-the-event-based-asynchronous-pattern.md)
- [Event-based Asynchronous Pattern (EAP)](event-based-asynchronous-pattern-eap.md) (Modello asincrono basato su eventi, EAP)
- [Quando implementare il modello asincrono basato su eventi](deciding-when-to-implement-the-event-based-asynchronous-pattern.md)
- [Suggerimenti per l'implementazione del modello asincrono basato su eventi](best-practices-for-implementing-the-event-based-asynchronous-pattern.md)
- [Procedura: usare componenti che supportano il modello asincrono basato su eventi](how-to-use-components-that-support-the-event-based-asynchronous-pattern.md)
- [Procedura: implementare un componente che supporta il modello asincrono basato su eventi](component-that-supports-the-event-based-asynchronous-pattern.md)
