---
title: Implementazione del modello asincrono basato su eventi
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Event-based Asynchronous Pattern
- ProgressChangedEventArgs class
- BackgroundWorker component
- events [.NET Framework], asynchronous
- Asynchronous Pattern
- AsyncOperationManager class
- threading [.NET Framework], asynchronous features
- components [.NET Framework], asynchronous
- AsyncOperation class
- AsyncCompletedEventArgs class
ms.assetid: 43402d19-8d30-426d-8785-1a4478233bfa
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6b4df5e4df914d932c7413e9330e8663753456c8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="implementing-the-event-based-asynchronous-pattern"></a>Implementazione del modello asincrono basato su eventi
In caso di scrittura di una classe con alcune operazioni che possono causare ritardi notevoli, è consigliabile assegnare la funzionalità asincrona implementando [Cenni preliminari sul modello asincrono basato su eventi](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md).  
  
 Il modello asincrono basato su eventi offre un modo standardizzato per aggiungere funzionalità asincrone a una classe. Se implementata con le classi di supporto come <xref:System.ComponentModel.AsyncOperationManager>, la classe funziona con qualsiasi modello di applicazione, tra cui [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)], applicazioni Console e applicazioni Windows Form.  
  
 Per un esempio che implementa il modello asincrono basato su eventi, vedere [Procedura: Implementare un componente che supporta il modello asincrono basato su eventi](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md).  
  
 Per le operazioni asincrone semplice, può risultare utile il <xref:System.ComponentModel.BackgroundWorker> componente adatto. Per ulteriori informazioni su <xref:System.ComponentModel.BackgroundWorker>, vedere [procedura: eseguire un'operazione in Background](../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md).  
  
 L'elenco seguente descrive le funzionalità del modello asincrono basato su eventi affrontate in questo argomento.  
  
-   Opportunità per implementare il modello asincrono basato su eventi  
  
-   Denominazione di metodi asincroni  
  
-   Supporto facoltativo dell'annullamento  
  
-   Supporto facoltativo della proprietà IsBusy  
  
-   Supporto facoltativo per la generazione di report sullo stato di avanzamento  
  
-   Supporto facoltativo per la restituzione di risultati incrementali  
  
-   Gestione dei parametri Out e Ref nei metodi  
  
## <a name="opportunities-for-implementing-the-event-based-asynchronous-pattern"></a>Opportunità per implementare il modello asincrono basato su eventi  
 Valutare l'implementazione del modello asincrono basato su eventi quando:  
  
-   Client della classe non è necessario <xref:System.Threading.WaitHandle> e <xref:System.IAsyncResult> oggetti disponibili per le operazioni asincrone, vale a dire che il polling e <xref:System.Threading.WaitHandle.WaitAll%2A> o <xref:System.Threading.WaitHandle.WaitAny%2A> dovrà essere generato dal client.  
  
-   Si desidera che le operazioni asincrone vengano gestite dal client con il modello noto di evento/delegato.  
  
 Qualsiasi operazione è un candidato per un'implementazione asincrona, ma è opportuno considerare quelle con lunghe latenze previste. Sono particolarmente indicate le operazioni in cui i client chiamano un metodo e ricevono una notifica al completamento, senza richiedere ulteriori interventi. Rientrano in questa condizione anche le operazioni con esecuzione continua,che inviano notifiche periodiche ai client sullo stato di avanzamento, sui risultati incrementali o sulle modifiche di stato.  
  
 Per altre informazioni sui casi in cui supportare il modello asincrono basato su eventi, vedere [Quando implementare il modello asincrono basato su eventi](../../../docs/standard/asynchronous-programming-patterns/deciding-when-to-implement-the-event-based-asynchronous-pattern.md).  
  
## <a name="naming-asynchronous-methods"></a>Denominazione di metodi asincroni  
 Per ogni metodo *MethodName* sincrono per il quale si desidera specificare una controparte asincrona:  
  
 Definire un metodo *MethodName*`Async` che:  
  
-   Restituisce `void`.  
  
-   Accetta gli stessi parametri del metodo *MethodName*.  
  
-   Accetta più chiamate.  
  
 Definire facoltativamente un overload di *MethodName*`Async` identico a *MethodName*`Async`, ma con un parametro con valore di oggetto aggiuntivo denominato `userState`. Seguire questa procedura se si intende gestire più chiamate simultanee del metodo, nel qual caso il valore `userState` verrà recapitato nuovamente a tutti i gestori eventi per distinguere le chiamate del metodo. È anche possibile scegliere questa opzione come posizione in cui archiviare lo stato utente per un successivo recupero.  
  
 Per ogni firma di metodo *MethodName*`Async` distinta:  
  
1.  Definire l'evento seguente nella stessa classe del metodo:  
  
    ```vb  
    Public Event MethodNameCompleted As MethodNameCompletedEventHandler  
    ```  
  
    ```csharp  
    public event MethodNameCompletedEventHandler MethodNameCompleted;  
    ```  
  
2.  Definire il seguente delegato e <xref:System.ComponentModel.AsyncCompletedEventArgs>. che verranno probabilmente definiti all'esterno della classe, ma nello stesso spazio dei nomi.  
  
    ```vb  
    Public Delegate Sub MethodNameCompletedEventHandler( _  
        ByVal sender As Object, _  
        ByVal e As MethodNameCompletedEventArgs)  
  
    Public Class MethodNameCompletedEventArgs  
        Inherits System.ComponentModel.AsyncCompletedEventArgs  
    Public ReadOnly Property Result() As MyReturnType  
    End Property  
    ```  
  
    ```csharp  
    public delegate void MethodNameCompletedEventHandler(object sender,   
        MethodNameCompletedEventArgs e);  
  
    public class MethodNameCompletedEventArgs : System.ComponentModel.AsyncCompletedEventArgs  
    {  
        public MyReturnType Result { get; }  
    }  
    ```  
  
    -   Verificare che la classe *MethodName*`CompletedEventArgs` esponga i relativi membri come proprietà di sola lettura e non come campi, dal momento che questi ultimi non consentono il data binding.  
  
    -   Non definisce alcun <xref:System.ComponentModel.AsyncCompletedEventArgs>-classe derivata per i metodi che non producono risultati. È sufficiente usare un'istanza di <xref:System.ComponentModel.AsyncCompletedEventArgs> stesso.  
  
        > [!NOTE]
        >  È perfettamente accettabile, quando possibile e appropriato, riutilizzare il delegato e <xref:System.ComponentModel.AsyncCompletedEventArgs> tipi. In questo caso, la denominazione non sarà coerenza con il nome del metodo, poiché un determinato delegato e <xref:System.ComponentModel.AsyncCompletedEventArgs> non saranno collegati a un singolo metodo.  
  
## <a name="optionally-support-cancellation"></a>Supporto facoltativo dell'annullamento  
 Se la classe supporta l'annullamento delle operazioni asincrone, l'annullamento dovrebbe essere esposto al client come descritto di seguito. Si noti che è necessario raggiungere due decisioni prima di definire il supporto dell'annullamento:  
  
-   La classe, incluse eventuali aggiunte future previste, include una sola operazione asincrona che supporta l'annullamento?  
  
-   Le operazioni asincrone che supportano l'annullamento supportano più operazioni in sospeso? In altre parole, il metodo *MethodName*`Async` accetta un parametro `userState` e consente più chiamate prima di attendere il completamento di uno di essi?  
  
 Usare le risposte a queste due domande nella tabella seguente per determinare la firma per il metodo di annullamento scelto.  
  
### <a name="visual-basic"></a>Visual Basic  
  
||Più operazioni simultanee supportate|Una sola operazione alla volta|  
|------|------------------------------------------------|----------------------------------|  
|Una operazione asincrona nell'intera classe|`Sub MethodNameAsyncCancel(ByVal userState As Object)`|`Sub MethodNameAsyncCancel()`|  
|Più operazioni asincrone nella classe|`Sub CancelAsync(ByVal userState As Object)`|`Sub CancelAsync()`|  
  
### <a name="c"></a>C#  
  
||Più operazioni simultanee supportate|Una sola operazione alla volta|  
|------|------------------------------------------------|----------------------------------|  
|Una operazione asincrona nell'intera classe|`void MethodNameAsyncCancel(object userState);`|`void MethodNameAsyncCancel();`|  
|Più operazioni asincrone nella classe|`void CancelAsync(object userState);`|`void CancelAsync();`|  
  
 Se si definisce il metodo `CancelAsync(object userState)`, i client devono scegliere con cautela i valori di stato per permettere la distinzione tra tutti i metodi asincroni chiamati sull'oggetto e non solo tra tutte le chiamate di un singolo metodo asincrono.  
  
 La decisione di denominare la versione della singola operazione asincrona *MethodName*`AsyncCancel` dipende dalla capacità di individuare più facilmente il metodo in un ambiente di progettazione come IntelliSense di Visual Studio. Questo raggruppa i membri correlati e li distingue dagli altri membri che non hanno a che fare con funzionalità asincrone. Se si prevede che potrebbero essere aggiunte altre operazioni asincrone nelle versioni successive, è preferibile definire `CancelAsync`.  
  
 Non definire più metodi della tabella precedente nella stessa classe. Non avrebbe senso e creerebbe confusione nell'interfaccia della classe con un numero eccessivo di metodi.  
  
 Questi metodi vengono in genere restituiti immediatamente e l'esito dell'operazione di annullamento non è garantito. Nel gestore eventi per l'evento *MethodName*`Completed` l'oggetto *MethodName*`CompletedEventArgs` contiene un campo `Cancelled`, che può essere usato dai client per determinare se si è verificato l'annullamento.  
  
 Rispettare la semantica di annullamento descritta in [Suggerimenti per l'implementazione del modello asincrono basato su eventi](../../../docs/standard/asynchronous-programming-patterns/best-practices-for-implementing-the-event-based-asynchronous-pattern.md).  
  
## <a name="optionally-support-the-isbusy-property"></a>Supporto facoltativo della proprietà IsBusy  
 Se la classe non supporta più chiamate simultanee, è consigliabile esporre una proprietà `IsBusy`. In questo modo gli sviluppatori possono stabilire se un metodo *MethodName*`Async` è in esecuzione senza rilevare un'eccezione generata dal metodo *MethodName*`Async`.  
  
 Rispettare la semantica di `IsBusy` descritta in [Suggerimenti per l'implementazione del modello asincrono basato su eventi](../../../docs/standard/asynchronous-programming-patterns/best-practices-for-implementing-the-event-based-asynchronous-pattern.md).  
  
## <a name="optionally-provide-support-for-progress-reporting"></a>Supporto facoltativo per la generazione di report sullo stato di avanzamento  
 È spesso utile che un'operazione asincrona generi un report sullo stato di avanzamento durante il funzionamento. Il modello asincrono basato su eventi offre linee guida a tale scopo.  
  
-   Definire facoltativamente un evento che verrà generato dall'operazione asincrona e chiamato sul thread appropriato. Il <xref:System.ComponentModel.ProgressChangedEventArgs> oggetto supporta un indicatore di stato con valori interi che deve essere compreso tra 0 e 100.  
  
-   Denominare l'evento come indicato di seguito:  
  
    -   `ProgressChanged` se la classe dispone di più operazioni asincrone (o presumibilmente aumenterà per includere più operazioni asincrone nelle versioni future);  
  
    -   *MethodName* `ProgressChanged` se la classe include una sola operazione asincrona.  
  
     Questa scelta di denominazione è paragonabile a quella eseguita per il metodo di annullamento, come descritto nella sezione Supporto facoltativo dell'annullamento.  
  
 Questo evento deve utilizzare il <xref:System.ComponentModel.ProgressChangedEventHandler> firma del delegato e <xref:System.ComponentModel.ProgressChangedEventArgs> classe. In alternativa, se è possibile fornire un indicatore di stato più specifico di dominio (per istanza, byte letti e byte totali per un'operazione di download), è necessario definire una classe derivata di <xref:System.ComponentModel.ProgressChangedEventArgs>.  
  
 Si noti che per la classe è presente un solo evento `ProgressChanged` o *MethodName*`ProgressChanged`, indipendentemente dal numero di metodi asincroni supportati. Per i client è previsto l'uso dell'oggetto `userState` passato ai metodi *MethodName*`Async` per distinguere i diversi aggiornamenti dello stato di avanzamento in più operazioni simultanee.  
  
 In alcuni casi, più operazioni potrebbero supportare lo stato di avanzamento e restituire singolarmente un indicatore diverso. In questo caso, un singolo evento `ProgressChanged` non è appropriato ed è opportuno scegliere di supportare più eventi `ProgressChanged`. Usare quindi un modello di denominazione di *MethodName*`ProgressChanged` per ogni metodo *MethodName*`Async`.  
  
 Rispettare la semantica della generazione di report sullo stato di avanzamento descritta in [Suggerimenti per l'implementazione del modello asincrono basato su eventi](../../../docs/standard/asynchronous-programming-patterns/best-practices-for-implementing-the-event-based-asynchronous-pattern.md).  
  
## <a name="optionally-provide-support-for-returning-incremental-results"></a>Supporto facoltativo per la restituzione di risultati incrementali  
 A volte un'operazione asincrona può restituire risultati incrementali prima del completamento. Per supportare questo scenario sono disponibili numerose opzioni. Di seguito sono riportati alcuni esempi.  
  
### <a name="single-operation-class"></a>Classe con singola operazione  
 Se la classe supporta solo una singola operazione asincrona e tale operazione è in grado di restituire risultati incrementali:  
  
-   Estendere la <xref:System.ComponentModel.ProgressChangedEventArgs> digitare per il trasporto di dati dei risultati incrementali e definire un *NomeMetodo* `ProgressChanged` eventi con i dati estesi.  
  
-   Generare l'evento *MethodName*`ProgressChanged` in questione in presenza di un risultato incrementale da inserire nel report.  
  
 Questa soluzione si applica in modo specifico a una classe con singola operazione asincrona poiché non determina alcun problema se lo stesso evento si ripete per restituire gli stessi risultati incrementali in tutte le operazioni, come avviene con l'evento *MethodName*`ProgressChanged`.  
  
### <a name="multiple-operation-class-with-homogeneous-incremental-results"></a>Classe con più operazioni con risultati incrementali omogenei  
 In questo caso, la classe supporta più metodi asincroni, ognuno dei quali è in grado di restituire risultati incrementali che avranno tutti lo stesso tipo di dati.  
  
 Seguire il modello descritto in precedenza per le classi di singola operazione, come lo stesso <xref:System.EventArgs> struttura funzionerà per tutti i risultati incrementali. Definire un evento `ProgressChanged` anziché un evento *MethodName*`ProgressChanged`, dal momento che si applica a più metodi asincroni.  
  
### <a name="multiple-operation-class-with-heterogeneous-incremental-results"></a>Classe con più operazioni con risultati incrementali eterogenei  
 Se la classe supporta più metodi asincroni, ognuno dei quali restituisce un tipo diverso di dati, è consigliabile:  
  
-   Separare il report dei risultati incrementali dal report sullo stato di avanzamento.  
  
-   Definire un apposito *NomeMetodo* `ProgressChanged` evento con appropriato <xref:System.EventArgs> per ciascun metodo gestire i dati dei risultati incrementali del metodo asincrono.  
  
 Chiamare il gestore eventi sul thread appropriato, come descritto in [Suggerimenti per l'implementazione del modello asincrono basato su eventi](../../../docs/standard/asynchronous-programming-patterns/best-practices-for-implementing-the-event-based-asynchronous-pattern.md).  
  
## <a name="handling-out-and-ref-parameters-in-methods"></a>Gestione dei parametri Out e Ref nei metodi  
 Sebbene l'uso di `out` e `ref` sia, in generale, sconsigliato in .NET Framework, ecco le regole da seguire quando sono presenti:  
  
 Dato un metodo *MethodName* sincrono:  
  
-   i parametri `out` per *MethodName* non devono far parte di *MethodName*`Async`, bensì di *MethodName*`CompletedEventArgs`, con lo stesso nome del relativo parametro equivalente in *MethodName*, a meno che non esista un nome più appropriato.  
  
-   i parametri `ref` per *MethodName* devono far parte di *MethodName*`Async` e di *MethodName*`CompletedEventArgs` con lo stesso nome del relativo parametro equivalente in *MethodName*, a meno che non esista un nome più appropriato.  
  
 Ad esempio, dato:  
  
```vb  
Public Function MethodName(ByVal arg1 As String, ByRef arg2 As String, ByRef arg3 As String) As Integer  
```  
  
```csharp  
public int MethodName(string arg1, ref string arg2, out string arg3);  
```  
  
 Il metodo asincrono e il relativo <xref:System.ComponentModel.AsyncCompletedEventArgs> classe avrà un aspetto simile al seguente:  
  
```vb  
Public Sub MethodNameAsync(ByVal arg1 As String, ByVal arg2 As String)  
  
Public Class MethodNameCompletedEventArgs  
    Inherits System.ComponentModel.AsyncCompletedEventArgs  
    Public ReadOnly Property Result() As Integer   
    End Property  
    Public ReadOnly Property Arg2() As String   
    End Property  
    Public ReadOnly Property Arg3() As String   
    End Property  
End Class  
```  
  
```csharp  
public void MethodNameAsync(string arg1, string arg2);  
  
public class MethodNameCompletedEventArgs : System.ComponentModel.AsyncCompletedEventArgs  
{  
    public int Result { get; };  
    public string Arg2 { get; };  
    public string Arg3 { get; };  
}  
```  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ComponentModel.ProgressChangedEventArgs>  
 <xref:System.ComponentModel.AsyncCompletedEventArgs>  
 [Procedura: Implementare un componente che supporta il modello asincrono basato su eventi](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md)  
 [Procedura: Eseguire un'operazione in background](../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)  
 [Procedura: Implementare un form che esegue un'operazione in background](../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md)  
 [Quando implementare il modello asincrono basato su eventi](../../../docs/standard/asynchronous-programming-patterns/deciding-when-to-implement-the-event-based-asynchronous-pattern.md)  
 [Programmazione multithreading con il modello asincrono basato su eventi](../../../docs/standard/asynchronous-programming-patterns/multithreaded-programming-with-the-event-based-asynchronous-pattern.md)  
 [Suggerimenti per l'implementazione del modello asincrono basato su eventi](../../../docs/standard/asynchronous-programming-patterns/best-practices-for-implementing-the-event-based-asynchronous-pattern.md)
