---
title: Modello Dispose
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- Dispose method
- class library design guidelines [.NET Framework], Dispose method
- class library design guidelines [.NET Framework], Finalize method
- customizing Dispose method name
- Finalize method
ms.assetid: 31a6c13b-d6a2-492b-9a9f-e5238c983bcb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f7bb9420d6439cff36c5cfa997152773503fbd9a
ms.sourcegitcommit: ed7b4b9b77d35e94a35a2634e8c874f46603fb2b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/26/2018
ms.locfileid: "36948550"
---
# <a name="dispose-pattern"></a>Modello Dispose
Tutti i programmi acquisiscono una o più risorse di sistema, ad esempio memoria, handle del sistema o le connessioni al database, nel corso della loro esecuzione. Gli sviluppatori devono prestare molta attenzione quando si utilizza tali risorse di sistema, poiché deve essere liberate dopo che sono stati acquisiti e utilizzati.  
  
 CLR fornisce supporto per la gestione automatica della memoria. Memoria gestita (memoria allocata tramite l'operatore c# `new`) non devono essere rilasciate in modo esplicito. Viene rilasciata automaticamente dal garbage collector (GC). Ciò consente agli sviluppatori dell'attività tediosa e difficile di rilascio di memoria che ha causato uno dei motivi principali per la produttività precedenti offerto da .NET Framework.  
  
 Sfortunatamente, della memoria gestita è solo uno dei molti tipi di risorse di sistema. Risorse diverse dalla memoria gestita ancora devono essere rilasciate in modo esplicito e sono dette risorse non gestite. Il catalogo globale in modo specifico non è stato progettato per gestire tali risorse non gestite, il che significa che la responsabilità per la gestione delle risorse non gestite si trovi nelle mani degli sviluppatori di.  
  
 CLR fornisce alcune informazioni utili per il rilascio di risorse non gestite. <xref:System.Object?displayProperty=nameWithType> dichiara un metodo virtuale <xref:System.Object.Finalize%2A> (detto anche il finalizzatore) che viene chiamato per il Garbage Collector prima che la memoria venga recuperata tramite il Garbage Collector e possa eseguire l'override per rilasciare le risorse non gestite. Tipi che eseguono l'override del finalizzatore vengono definiti come tipi di finalizzazione.  
  
 Sebbene i finalizzatori sono efficaci in alcuni scenari di pulizia, presentano due svantaggi significativi:  
  
-   Il finalizzatore viene chiamato quando il Garbage Collector rileva che un oggetto è idoneo per la raccolta. Ciò si verifica in alcune non determinato periodo di tempo dopo che la risorsa non è più necessaria. Il ritardo tra quando lo sviluppatore può o rilasciare la risorsa e l'ora quando la risorsa viene effettivamente rilasciata dal finalizzatore può essere inaccettabile in programmi che acquisiscono molte risorse insufficienti (risorse che possono essere facilmente esaurite) o in casi in cui le risorse sono costose da mantenere in uso (ad esempio, i buffer di grandi quantità di memoria non gestito).  
  
-   Quando CLR è necessario chiamare un finalizzatore, è necessario posticipare la raccolta di memoria dell'oggetto fino alla successiva arrotondare di garbage collection (finalizzatori eseguiti tra le raccolte). Ciò significa che la memoria dell'oggetto (e tutti gli oggetti che cui fa riferimento) non verranno rilasciati per un periodo di tempo.  
  
 Pertanto, basarsi esclusivamente su finalizzatori potrebbero non essere appropriate in molti scenari quando è importante recuperare le risorse non gestite al più presto, quando si lavora con risorse limitate, o in elevata ad alte prestazioni scenari in cui l'overhead aggiunto di Garbage Collection di finalizzazione non è accettabile.  
  
 Il Framework fornisce il <xref:System.IDisposable?displayProperty=nameWithType> interfaccia che deve essere implementata per lo sviluppatore di rilasciare le risorse non gestite, non appena non sono necessari in modo manuale. Fornisce inoltre il <xref:System.GC.SuppressFinalize%2A?displayProperty=nameWithType> metodo grado di stabilire il catalogo globale che un oggetto è stato eliminato manualmente e non necessita di essere finalizzati più, nel qual caso la memoria dell'oggetto può essere recuperata in precedenza. I tipi che implementano il `IDisposable` interfaccia sono definiti tipi disposable.  
  
 È destinato il modello Dispose per standardizzare le informazioni sull'utilizzo e l'implementazione di finalizzatori e `IDisposable` interfaccia.  
  
 La principale motivazione per il modello consiste nel ridurre la complessità dell'implementazione del <xref:System.Object.Finalize%2A> e il <xref:System.IDisposable.Dispose%2A> metodi. La complessità deriva dal fatto che i metodi condividono alcuni, ma non tutti i percorsi del codice (le differenze sono illustrate più avanti in questo capitolo). Inoltre, esistono motivi storici per alcuni elementi del modello correlato all'evoluzione del supporto delle lingue per la gestione delle risorse deterministica.  
  
 **✓ DO** implementare il modello Dispose base su tipi contenente le istanze di tipi disposable. Vedere la [base modello Dispose](#basic_pattern) sezione per informazioni dettagliate sul modello di base.  
  
 Se un tipo è responsabile per la durata di altri oggetti eliminabili, gli sviluppatori devono un modo per l'eliminazione, troppo. Usa il contenitore `Dispose` metodo è un modo pratico per rendere possibile questa.  
  
 **✓ DO** implementare il modello Dispose base e di fornire un finalizzatore tipi che contiene le risorse che devono essere liberate in modo esplicito e che non dispongono di finalizzatori.  
  
 Ad esempio, lo schema deve essere implementato sui tipi di archiviare i buffer di memoria non gestita. Il [finalizzabili tipi](#finalizable_types) sezione vengono illustrate le linee guida relative all'implementazione i finalizzatori.  
  
 **✓ CONSIDER** implementa il modello Dispose base nelle classi che stessi non contenere le risorse non gestite o gli oggetti eliminabili ma che sono probabilmente hanno sottotipi che eseguono.  
  
 È un ottimo esempio di ciò il <xref:System.IO.Stream?displayProperty=nameWithType> classe. Sebbene sia una classe base astratta che non contiene tutte le risorse, la maggior parte delle sue sottoclassi non e per questo motivo, implementato questo modello.  
  
<a name="basic_pattern"></a>   
## <a name="basic-dispose-pattern"></a>Modello Dispose base  
 L'implementazione di base del modello prevede l'implementazione il `System.IDisposable` interfaccia e si dichiara la `Dispose(bool)` metodo che implementa la logica di pulizia risorse tutti essere condivise tra il `Dispose` metodo e il finalizzatore facoltativo.  
  
 Nell'esempio seguente viene illustrata un'implementazione semplice del modello di base:  
  
```csharp
public class DisposableResourceHolder : IDisposable {  
  
    private SafeHandle resource; // handle to a resource  
  
    public DisposableResourceHolder() {  
        this.resource = ... // allocates the resource  
    }  
  
    public void Dispose() {  
        Dispose(true);  
        GC.SuppressFinalize(this);  
    }  
  
    protected virtual void Dispose(bool disposing) {  
        if (disposing) {  
            if (resource!= null) resource.Dispose();  
        }  
    }  
}  
```  
  
 Il parametro booleano `disposing` indica se il metodo è stato richiamato dal `IDisposable.Dispose` implementazione o dal finalizzatore. Il `Dispose(bool)` implementazione deve controllare il parametro prima dell'accesso ad altri oggetti di riferimento (ad esempio, il campo delle risorse nell'esempio precedente). Tali oggetti devono essere effettuati solo quando il metodo viene chiamato dal `IDisposable.Dispose` implementazione (quando il `disposing` parametro è uguale a true). Se il metodo viene richiamato dal finalizzatore (`disposing` è false), non accedere altri oggetti. Il motivo è che gli oggetti vengono finalizzati in un ordine imprevedibile e pertanto o una delle relative dipendenze, potrebbe essere già stata completata.  
  
 Inoltre, questa sezione si applica alle classi con una base che non implementano il modello Dispose. Se sta ereditando da una classe che implementa già il modello, è sufficiente eseguire l'override di `Dispose(bool)` metodo per fornire la logica di pulizia di risorse aggiuntive.  
  
 **✓ DO** dichiarare un `protected virtual void Dispose(bool disposing)` metodo per centralizzare la logica di tutti i relativi al rilascio di risorse non gestite.  
  
 Pulizia di tutte le risorse deve essere eseguito in questo metodo. Il metodo viene chiamato da entrambi il finalizzatore e il `IDisposable.Dispose` metodo. Il parametro sarà false se viene richiamata dall'interno un finalizzatore. È consigliabile utilizzarlo per verificare che qualsiasi codice in esecuzione durante la finalizzazione non accede ad altri oggetti finalizzabili. Dettagli dell'implementazione di finalizzatori sono descritti nella sezione successiva.  
  
```csharp
protected virtual void Dispose(bool disposing) {  
    if (disposing) {  
        if (resource!= null) resource.Dispose();  
    }  
}  
```  
  
 **✓ DO** implementare il `IDisposable` interfaccia semplicemente chiamando `Dispose(true)` seguito da `GC.SuppressFinalize(this)`.  
  
 La chiamata a `SuppressFinalize` dovrebbero verificarsi solo se `Dispose(true)` viene eseguita correttamente.  
  
```csharp
public void Dispose(){  
    Dispose(true);  
    GC.SuppressFinalize(this);  
}  
```  
  
 **X DO NOT** rendere senza parametri `Dispose` metodo virtuale.  
  
 Il `Dispose(bool)` metodo è quella che deve essere sottoposto a override dalle sottoclassi.  
  
```csharp
// bad design  
public class DisposableResourceHolder : IDisposable {  
    public virtual void Dispose() { ... }  
    protected virtual void Dispose(bool disposing) { ... }  
}  
  
// good design  
public class DisposableResourceHolder : IDisposable {  
    public void Dispose() { ... }  
    protected virtual void Dispose(bool disposing) { ... }  
}  
```  
  
 **X DO NOT** dichiarare tutti gli overload del `Dispose` metodo diverso da `Dispose()` e `Dispose(bool)`.  
  
 `Dispose` deve essere considerata una parola riservata per codificare questo modello e per impedire confusione tra i responsabili dell'implementazione, utenti e i compilatori. Alcune lingue potrebbero scegliere di implementare automaticamente questo modello su determinati tipi.  
  
 **✓ DO** consentire il `Dispose(bool)` metodo da chiamare più volte. Il metodo è possibile scegliere di non eseguire alcuna operazione dopo la prima chiamata.  
  
```csharp
public class DisposableResourceHolder : IDisposable {  
  
    bool disposed = false;  
  
    protected virtual void Dispose(bool disposing) {  
        if (disposed) return;  
        // cleanup  
        ...  
        disposed = true;  
    }  
}  
```  
  
 **X AVOID** generare un'eccezione dall'interno `Dispose(bool)` tranne che in alcune situazioni critiche in cui il processo di contenitore è stato danneggiato (perdite, lo stato condiviso non coerente, ecc.).  
  
 Gli utenti si aspettano che una chiamata a `Dispose` non genererà un'eccezione.  
  
 Se `Dispose` potrebbe generare un'eccezione, non verrà eseguita la logica di pulizia ulteriore blocco finally. Per risolvere questo problema, l'utente dovrà eseguire il wrapping di ogni chiamata a `Dispose` (all'interno di blocco finally!) in un blocco try, determinando i gestori di pulizia molto complessi. Se l'esecuzione di un `Dispose(bool disposing)` (metodo), mai generano un'eccezione se disposing è false. In questo modo interromperà il processo se l'esecuzione all'interno di un contesto finalizzatore.  
  
 **✓ DO** generano un <xref:System.ObjectDisposedException> da qualsiasi membro non può essere usati dopo che l'oggetto è stato eliminato di.  
  
```csharp
public class DisposableResourceHolder : IDisposable {  
    bool disposed = false;  
    SafeHandle resource; // handle to a resource  
  
    public void DoSomething() {  
        if (disposed) throw new ObjectDisposedException(...);  
        // now call some native methods using the resource   
        ...  
    }  
    protected virtual void Dispose(bool disposing) {  
        if (disposed) return;  
        // cleanup  
        ...  
        disposed = true;  
    }  
}  
```  
  
 **✓ CONSIDER** fornendo meccanismo `Close()`, oltre al `Dispose()`, se chiudere è terminologia nell'area.  
  
 In tal caso, è importante eseguire il `Close` identica all'implementazione `Dispose` e provare a implementare la `IDisposable.Dispose` metodo in modo esplicito.  
  
```csharp
public class Stream : IDisposable {  
    IDisposable.Dispose() {  
        Close();  
    }  
    public void Close() {  
        Dispose(true);  
        GC.SuppressFinalize(this);  
    }  
}  
```  
  
<a name="finalizable_types"></a>   
## <a name="finalizable-types"></a>Tipi di finalizzazione  
 Tipi finalizzabili sono tipi che estendono il modello Dispose base eseguendo l'override del finalizzatore e fornendo il percorso di codice la finalizzazione nel `Dispose(bool)` metodo.  
  
 I finalizzatori sono notoriamente difficili da implementare correttamente, soprattutto perché non è possibile apportare alcuni presupposti (in genere validi) sullo stato del sistema durante l'esecuzione. Le linee guida seguenti devono essere prese in un'attenta considerazione.  
  
 Si noti che alcune linee guida si applicano non solo al `Finalize` (metodo), ma a qualsiasi codice chiamato da un finalizzatore. Nel caso il metodo Dispose modello di base definiti in precedenza, questo significa logica che viene eseguita all'interno di `Dispose(bool disposing)` quando il `disposing` parametro è false.  
  
 Se la classe di base già è finalizzabile e implementa il modello Dispose base, è consigliabile non eseguire l'override `Finalize` nuovamente. Deve invece eseguire l'override di `Dispose(bool)` metodo per fornire la logica di pulizia di risorse aggiuntive.  
  
 Il codice seguente viene illustrato un esempio di un tipo finalizzabile:  
  
```csharp
public class ComplexResourceHolder : IDisposable {  
  
    private IntPtr buffer; // unmanaged memory buffer  
    private SafeHandle resource; // disposable handle to a resource  
  
    public ComplexResourceHolder() {  
        this.buffer = ... // allocates memory  
        this.resource = ... // allocates the resource  
    }  
  
    protected virtual void Dispose(bool disposing) {  
            ReleaseBuffer(buffer); // release unmanaged memory  
        if (disposing) { // release other disposable objects  
            if (resource!= null) resource.Dispose();  
        }  
    }  
  
    ~ComplexResourceHolder() {
        Dispose(false);  
    }  
  
    public void Dispose() {
        Dispose(true);  
        GC.SuppressFinalize(this);  
    }  
}  
```  
  
 **X AVOID** effettua tipi finalizzabile.  
  
 Considerare con attenzione tutti i casi in cui si ritiene che è necessario un finalizzatore. È presente un reale costi associati alle istanze con i finalizzatori, dal punto vista complessità sia delle prestazioni sia del codice. Preferire l'utilizzo di wrapper di risorse, ad esempio <xref:System.Runtime.InteropServices.SafeHandle> per incapsulare le risorse non gestite, laddove possibile, nel qual caso un finalizzatore diventa non necessario perché il wrapper è responsabile della pulizia di risorse.  
  
 **X DO NOT** finalizzabili in modo che i tipi di valore.  
  
 Solo i tipi di riferimento ottengano finalizzati effettivamente da CLR, e pertanto verrà ignorata qualsiasi tentativo di inserire un finalizzatore in un tipo di valore. I compilatori c# e C++ applicano questa regola.  
  
 **✓ DO** rendere finalizzabili se il tipo è responsabile del rilascio di una risorsa non gestita che non dispone di un proprio finalizzatore di un tipo.  
  
 Quando si implementa il finalizzatore, è sufficiente chiamare `Dispose(false)` e inserire logica di pulizia in tutte le risorse all'interno di `Dispose(bool disposing)` metodo.  
  
```csharp
public class ComplexResourceHolder : IDisposable {  
  
    ~ComplexResourceHolder() {
        Dispose(false);  
    }  
  
    protected virtual void Dispose(bool disposing) {
        ...  
    }  
}  
```  
  
 **✓ DO** implementare il modello Dispose base su ogni tipo di finalizzazione.  
  
 In questo modo gli utenti del tipo di un modo per eseguire in modo esplicito la pulitura deterministica delle stesse risorse di cui è responsabile il finalizzatore.  
  
 **X DO NOT** accedere agli oggetti finalizzabili nel percorso di codice finalizzatore perché vi è rischio significativo che essi verrà sia già stati completati.  
  
 Ad esempio, un oggetto finalizzabile A che presenta un riferimento a un altro oggetto finalizzabile B non è possibile usare in modo affidabile B nel finalizzatore, o viceversa. I finalizzatori vengono chiamati in ordine casuale (se non si una garanzia di ordinamento vulnerabile per la finalizzazione critico).  
  
 Inoltre, tenere presente che gli oggetti archiviati in variabili statiche verranno raccolto in determinati momenti durante uno scaricamento del dominio applicazione o durante l'uscita dal processo. L'accesso a una variabile statica che fa riferimento a un oggetto finalizzabile (o chiamare un metodo statico che potrebbe utilizzare i valori archiviati in variabili statiche) potrebbe non essere sicura se <xref:System.Environment.HasShutdownStarted%2A?displayProperty=nameWithType> restituisce true.  
  
 **✓ DO** apportare le `Finalize` metodo protetto.  
  
 Gli sviluppatori c#, C++ e Visual Basic.NET non devono preoccuparsi di questa operazione, perché i compilatori della Guida per applicare questa linea guida.  
  
 **X DO NOT** eccezioni let escape dalla logica del finalizzatore, ad eccezione di errori critici del sistema.  
  
 Se viene generata un'eccezione da un finalizzatore, CLR si arresterà l'intero processo (a partire da .NET Framework versione 2.0), altri finalizzatori impediscono l'esecuzione e le risorse da rilasciati in modo controllato.  
  
 **✓ CONSIDER** creazione e utilizzo di un oggetto finalizzabile critico (un tipo con una gerarchia che contiene <xref:System.Runtime.ConstrainedExecution.CriticalFinalizerObject>) per le situazioni in cui un finalizzatore assolutamente necessario eseguire anche in caso di applicazione forzato lo scaricamento di dominio e thread si interrompe.  
  
 *Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*  
  
 *State ristampate dall'autorizzazione di Pearson Education, Inc. dal [Framework linee guida di progettazione: convenzioni, idiomi e modelli per le librerie .NET riutilizzabile, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType>  
 <xref:System.Object.Finalize%2A?displayProperty=nameWithType>  
 [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)  
 [Modelli di progettazione comuni](../../../docs/standard/design-guidelines/common-design-patterns.md)  
 [Garbage Collection](../../../docs/standard/garbage-collection/index.md)
