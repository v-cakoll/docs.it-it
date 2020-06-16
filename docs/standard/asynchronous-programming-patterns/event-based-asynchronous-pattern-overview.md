---
title: Cenni preliminari sul modello asincrono basato su eventi
description: Esaminare i modelli asincroni basati su eventi (EAPs) in .NET, che rendono disponibili i vantaggi delle applicazioni multithreading, ma nascondono alcune complessità di progettazione.
ms.date: 03/30/2017
ms.technology: dotnet-standard
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
- AsyncOperation class
- AsyncCompletedEventArgs class
ms.assetid: 792aa8da-918b-458e-b154-9836b97735f3
ms.openlocfilehash: 18fbdb29e5a1fb02601dea00964538144c07122c
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/15/2020
ms.locfileid: "84768859"
---
# <a name="event-based-asynchronous-pattern-overview"></a>Cenni preliminari sul modello asincrono basato su eventi
Le applicazioni che eseguono più attività contemporaneamente, pur rimanendo disponibili all'utente, richiedono spesso una progettazione che preveda l'uso di più thread. Lo spazio dei nomi <xref:System.Threading> offre tutti gli strumenti necessari per creare applicazioni multithreading a elevate prestazioni, per l'uso dei quali è necessaria tuttavia una notevole esperienza nel campo dell'ingegneria del software multithreading. Per applicazioni multithreading relativamente semplici, il componente <xref:System.ComponentModel.BackgroundWorker> rappresenta una soluzione adeguata. Per applicazioni asincrone più complesse, si consiglia di implementare una classe che segua il modello asincrono basato su eventi.  
  
 Tale modello consente di usufruire dei vantaggi offerti dalle applicazioni multithreading nascondendo al contempo gran parte degli aspetti complessi inerenti la progettazione multithreading. L'uso di una classe che supporta questo modello consente di:  
  
- Eseguire in background attività che richiedono una quantità eccessiva di tempo, come download e operazioni di database, senza interrompere l'applicazione.  
  
- Eseguire più operazioni contemporaneamente, ricevendo notifiche relative al completamento di ognuna.  
  
- Attendere la disponibilità delle risorse senza interrompere o bloccare l'esecuzione dell'applicazione.  
  
- Comunicare con operazioni asincrone in sospeso mediante un modello noto di eventi e delegati. Per altre informazioni sull'uso di gestori eventi e delegati, vedere [Eventi](../events/index.md).  
  
 Una classe che supporta il modello asincrono basato su eventi avrà uno o più metodi denominati _NomeMetodo_**Async**. Tali metodi possono eseguire il mirroring delle versioni sincrone che eseguono la stessa operazione sul thread corrente. La classe può anche avere un evento _NomeMetodo_**Completed** e un metodo _NomeMetodo_**AsyncCancel** (o semplicemente **CancelAsync**).  
  
 <xref:System.Windows.Forms.PictureBox> è un componente tipico che supporta il modello asincrono basato su eventi. Per scaricare un'immagine in modo sincrono è possibile chiamare il relativo metodo <xref:System.Windows.Forms.PictureBox.Load%2A>, ma qualora le dimensioni dell'immagine fossero eccessive o la connessione di rete troppo lenta, l'esecuzione dell'applicazione verrà interrotta fino al completamento dell'operazione di download e alla restituzione della chiamata a <xref:System.Windows.Forms.PictureBox.Load%2A>.  
  
 Per lasciare che l'applicazione continui a essere eseguita durante il caricamento dell'immagine, è possibile chiamare il metodo <xref:System.Windows.Forms.PictureBox.LoadAsync%2A> e gestire l'evento <xref:System.Windows.Forms.PictureBox.LoadCompleted> analogamente a qualsiasi altro evento. Quando si chiama il metodo <xref:System.Windows.Forms.PictureBox.LoadAsync%2A> l'esecuzione dell'applicazione procede mentre l'operazione di download continua su un altro thread, in background. Al termine dell'operazione di caricamento dell'immagine verrà chiamato il gestore eventi che potrà esaminare il parametro <xref:System.ComponentModel.AsyncCompletedEventArgs> per determinare se il download è stato eseguito.  
  
 Il modello asincrono basato su eventi richiede la possibilità di annullare un'operazione asincrona, requisito supportato dal controllo <xref:System.Windows.Forms.PictureBox> per mezzo del relativo metodo <xref:System.Windows.Forms.PictureBox.CancelAsync%2A>. La chiamata del metodo <xref:System.Windows.Forms.PictureBox.CancelAsync%2A> determina l'invio di una richiesta di interruzione del download in sospeso. Quando l'attività viene annullata, viene generato l'evento <xref:System.Windows.Forms.PictureBox.LoadCompleted>.  
  
> [!CAUTION]
> Il download potrebbe terminare non appena viene effettuata la richiesta di <xref:System.Windows.Forms.PictureBox.CancelAsync%2A>. In tal caso, la proprietà <xref:System.ComponentModel.AsyncCompletedEventArgs.Cancelled%2A> potrebbe non riflettere la richiesta di annullamento. Si tratta di una *race condition*, ovvero di un problema riscontrato comunemente nella programmazione multithreading. Per altre informazioni sui problemi inerenti la programmazione multithreading, vedere [Procedure consigliate per il threading gestito](../threading/managed-threading-best-practices.md).  
  
## <a name="characteristics-of-the-event-based-asynchronous-pattern"></a>Caratteristiche del modello asincrono basato su eventi  
 Sono disponibili diversi tipi di modello asincrono basato su eventi, a seconda della complessità delle operazioni supportate da una determinata classe. Le classi più semplici possono presentare un solo metodo _NomeMetodo_**Async** e un evento _NomeMetodo_**Completed** corrispondente. Le classi più complesse possono invece avere diversi metodi _NomeMetodo_**Async**, ognuno dei quali con un evento _NomeMetodo_**Completed** associato, nonché versioni sincrone di tali metodi. Per ogni metodo asincrono le classi possono supportare funzionalità di annullamento e creazione di rapporti sullo stato di avanzamento, nonché risultati incrementali.  
  
 Un metodo asincrono può anche supportare più chiamate in sospeso, ovvero più richiami concorrenti, consentendo al codice di chiamarlo un numero indeterminato di volte prima del completamento di altre operazioni in sospeso. Una gestione efficace di questa situazione può richiedere che l'applicazione tenga traccia del completamento di ogni operazione.  
  
### <a name="examples-of-the-event-based-asynchronous-pattern"></a>Esempi del modello asincrono basato su eventi  
 I componenti <xref:System.Media.SoundPlayer> e <xref:System.Windows.Forms.PictureBox> rappresentano implementazioni semplici del modello asincrono basato su eventi. I componenti <xref:System.Net.WebClient> e <xref:System.ComponentModel.BackgroundWorker> rappresentano implementazioni più complesse del modello in questione.  
  
 Di seguito viene riportata una dichiarazione di classe di esempio conforme al modello:  
  
```vb  
Public Class AsyncExample  
    ' Synchronous methods.  
    Public Function Method1(ByVal param As String) As Integer
    Public Sub Method2(ByVal param As Double)
  
    ' Asynchronous methods.  
    Overloads Public Sub Method1Async(ByVal param As String)
    Overloads Public Sub Method1Async(ByVal param As String, ByVal userState As Object)
    Public Event Method1Completed As Method1CompletedEventHandler  
  
    Overloads Public Sub Method2Async(ByVal param As Double)
    Overloads Public Sub Method2Async(ByVal param As Double, ByVal userState As Object)
    Public Event Method2Completed As Method2CompletedEventHandler  
  
    Public Sub CancelAsync(ByVal userState As Object)
  
    Public ReadOnly Property IsBusy () As Boolean  
  
    ' Class implementation not shown.  
End Class  
```  
  
```csharp  
public class AsyncExample  
{  
    // Synchronous methods.  
    public int Method1(string param);  
    public void Method2(double param);  
  
    // Asynchronous methods.  
    public void Method1Async(string param);  
    public void Method1Async(string param, object userState);  
    public event Method1CompletedEventHandler Method1Completed;  
  
    public void Method2Async(double param);  
    public void Method2Async(double param, object userState);  
    public event Method2CompletedEventHandler Method2Completed;  
  
    public void CancelAsync(object userState);  
  
    public bool IsBusy { get; }  
  
    // Class implementation not shown.  
}  
```  
  
 La classe `AsyncExample` fittizia presenta due metodi che supportano entrambi i richiami sincroni e asincroni. Gli overload sincroni si comportano come qualsiasi chiamata di metodo ed eseguono le operazioni sul thread chiamante. Se l'operazione eseguita richiede tempo, potrebbe verificarsi un ritardo notevole nella restituzione della chiamata. Gli overload asincroni avviano l'operazione su un altro thread e vengono restituiti immediatamente consentendo al thread chiamante di continuare mentre l'operazione viene eseguita in background.  
  
### <a name="asynchronous-method-overloads"></a>Overload di metodi asincroni  
 Esistono potenzialmente due overload per le operazioni asincrone: a richiamo singolo e a più richiami. È possibile distinguere i due tipi di overload dalle firme dei relativi metodi. Il tipo a più richiami presenta un parametro supplementare denominato `userState` e consente al codice di chiamare più volte `Method1Async(string param, object userState)` senza attendere il completamento di eventuali operazioni asincrone in sospeso. Se, invece, si prova a chiamare `Method1Async(string param)` prima del completamento di un richiamo precedente, il metodo genera una <xref:System.InvalidOperationException>.  
  
 Il parametro `userState` degli overload a più richiami consente di distinguere le diverse operazioni asincrone. Specificare un valore univoco, ad esempio un GUID o un codice hash, per ogni chiamata al metodo `Method1Async(string param, object userState)`. Al termine di ogni operazione, il gestore eventi potrà determinare l'istanza dell'operazione che ha generato l'evento di completamento.  
  
### <a name="tracking-pending-operations"></a>Verifica delle operazioni in sospeso  
 Se si usano gli overload a più richiami, il codice deve tenere traccia degli oggetti `userState` (o ID attività) relativi alle attività in sospeso. Per ogni chiamata al metodo `Method1Async(string param, object userState)`, di solito viene generato un nuovo oggetto `userState` univoco che viene aggiunto a una raccolta. Quando l'attività corrispondente a tale oggetto `userState` genera l'evento di completamento, l'implementazione del metodo di completamento esamina <xref:System.ComponentModel.AsyncCompletedEventArgs.UserState%2A?displayProperty=nameWithType> e la rimuove dalla raccolta. Se usato in questo modo, il parametro `userState` funge da ID attività.  
  
> [!NOTE]
> È necessario specificare un valore univoco per il parametro `userState` nelle chiamate a overload a più richiami. La specifica di ID attività non univoci determina la generazione di una <xref:System.ArgumentException> da parte della classe asincrona.  
  
### <a name="canceling-pending-operations"></a>Annullamento delle operazioni in sospeso  
 È importante che sia possibile annullare le operazioni asincrone in qualsiasi momento prima che vengano completate. Le classi che implementano il modello asincrono basato su eventi avranno un metodo `CancelAsync` (se è presente un solo metodo asincrono) o un metodo _NomeMetodo_**AsyncCancel** (se sono presenti più metodi asincroni).  
  
 I metodi che consentono più chiamate accettano un parametro `userState` che può essere usato per tenere traccia della durata di ogni attività. `CancelAsync` accetta un parametro `userState` che consente di annullare attività specifiche in sospeso.  
  
 I metodi che supportano una sola operazione in sospeso alla volta, come `Method1Async(string param)`, non sono annullabili.  
  
### <a name="receiving-progress-updates-and-incremental-results"></a>Ricezione di aggiornamenti sullo stato di avanzamento e di risultati incrementali  
 Per tenere traccia dello stato di avanzamento e dei risultati incrementali, una classe conforme al modello asincrono basato su eventi può facoltativamente fornire un evento, che in genere è denominato `ProgressChanged` o _NomeMetodo_**ProgressChanged**, il cui gestore eventi accetta un parametro <xref:System.ComponentModel.ProgressChangedEventArgs>.  
  
 Il gestore eventi relativo all'evento `ProgressChanged` può esaminare la proprietà <xref:System.ComponentModel.ProgressChangedEventArgs.ProgressPercentage%2A?displayProperty=nameWithType> per determinare la percentuale di completamento di un'attività asincrona. Questa proprietà ha il valore compreso tra 0 e 100 e può essere usata per aggiornare la proprietà <xref:System.Windows.Forms.ProgressBar.Value%2A> di un oggetto <xref:System.Windows.Forms.ProgressBar>. Se sono in sospeso più operazioni asincrone, è possibile usare la proprietà <xref:System.ComponentModel.ProgressChangedEventArgs.UserState%2A?displayProperty=nameWithType> per identificare l'operazione per la quale viene generato il rapporto sullo stato di avanzamento.  
  
 Alcune classi possono generare un rapporto sui risultati incrementali mano a mano che procede l'esecuzione delle operazioni asincrone. I risultati verranno memorizzati in una classe derivata da <xref:System.ComponentModel.ProgressChangedEventArgs> e verranno visualizzati come proprietà nella classe derivata. È possibile accedere ai risultati nel gestore eventi dell'evento `ProgressChanged` usando la stessa procedura valida per la proprietà <xref:System.ComponentModel.ProgressChangedEventArgs.ProgressPercentage%2A>. Se sono in sospeso più operazioni asincrone, è possibile usare la proprietà <xref:System.ComponentModel.ProgressChangedEventArgs.UserState%2A> per identificare l'operazione per la quale viene generato il rapporto sui risultati incrementali.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ComponentModel.ProgressChangedEventArgs>
- <xref:System.ComponentModel.BackgroundWorker>
- <xref:System.ComponentModel.AsyncCompletedEventArgs>
- [Procedura: usare componenti che supportano il modello asincrono basato su eventi](how-to-use-components-that-support-the-event-based-asynchronous-pattern.md)
- [Procedura: Eseguire un'operazione in background](../../framework/winforms/controls/how-to-run-an-operation-in-the-background.md)
- [Procedura: implementare un form che utilizza un'operazione in background](../../framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md)
- [Event-based Asynchronous Pattern (EAP)](event-based-asynchronous-pattern-eap.md) (Modello asincrono basato su eventi, EAP)
- [Suggerimenti per l'implementazione del modello asincrono basato su eventi](best-practices-for-implementing-the-event-based-asynchronous-pattern.md)
- [Quando implementare il modello asincrono basato su eventi](deciding-when-to-implement-the-event-based-asynchronous-pattern.md)
