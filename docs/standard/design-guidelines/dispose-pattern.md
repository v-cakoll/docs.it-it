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
ms.openlocfilehash: ff52e17cfe4a4236e4d165c0961ca3a23fed9a72
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2018
ms.locfileid: "43864644"
---
# <a name="dispose-pattern"></a>Modello Dispose
Tutti i programmi acquisiscono uno o più risorse di sistema, ad esempio memoria, gli handle del sistema o connessioni di database, nel corso della loro esecuzione. Gli sviluppatori devono prestare attenzione quando si usano tali risorse di sistema, perché deve essere liberate dopo l'acquisizione e utilizzati.  
  
 CLR fornisce supporto per la gestione automatica della memoria. Gestione della memoria (memoria allocata tramite l'operatore c# `new`) non dovrà essere rilasciato in modo esplicito. Viene rilasciato automaticamente dal garbage collector (GC). Ciò consente agli sviluppatori di attività difficile e noioso di rilascio di memoria ed è stato uno dei motivi principali per la produttività senza precedenti offerte da .NET Framework.  
  
 Sfortunatamente, della memoria gestita è solo uno di molti tipi di risorse di sistema. Risorse diverse dalla memoria gestita ancora devono essere rilasciati in modo esplicito e vengono definite le risorse non gestite. Il Garbage Collector in modo specifico non è stato progettato per gestire tali risorse non gestite, il che significa che la responsabilità di gestire le risorse non gestite si trova nelle mani degli sviluppatori.  
  
 CLR fornisce alcune informazioni utili per rilasciare risorse non gestite. <xref:System.Object?displayProperty=nameWithType> dichiara un metodo virtuale <xref:System.Object.Finalize%2A> (detto anche il finalizzatore) che viene chiamato dal GC prima che la memoria dell'oggetto venga recuperata tramite il Garbage Collector e possa eseguire l'override per rilasciare risorse non gestite. Tipi che eseguono l'override del finalizzatore vengono definiti come tipi di finalizzazione.  
  
 Sebbene i finalizzatori siano valide in alcuni scenari di pulizia, presentano due svantaggi significativi:  
  
-   Il finalizzatore viene richiamato quando il Garbage Collector rileva che un oggetto è idoneo per la raccolta. Ciò accade in un certo periodo di tempo dopo la risorsa non è più necessario indeterminato. Il ritardo tra quando lo sviluppatore potrebbe o si vuole rilasciare la risorsa e il tempo quando la risorsa è in realtà rilasciata dal finalizzatore può essere inaccettabile in programmi che acquisire molte risorse insufficienti (risorse che possono esaurirsi con facilità) o in casi in cui le risorse sono costose da mantenere in uso (ad esempio, i buffer di grandi quantità di memoria non gestita).  
  
-   Quando CLR deve chiamare un finalizzatore, è necessario posticipare la raccolta della memoria dell'oggetto fino alla successiva arrotondare di garbage collection (i finalizzatori eseguiti tra le raccolte). Ciò significa che la memoria dell'oggetto (e tutti gli oggetti che si intende) non verranno rilasciati per un periodo di tempo più lungo.  
  
 Pertanto, basarsi esclusivamente su finalizzatori potrebbe non essere appropriato in molti scenari quando è importante recuperare le risorse non gestite al più presto, quando si lavora con risorse insufficienti o in altamente efficienti scenari in cui l'overhead di GC aggiunto della finalizzazione non è accettabile.  
  
 Il Framework fornisce il <xref:System.IDisposable?displayProperty=nameWithType> interfaccia che deve essere implementato per fornire allo sviluppatore di rilasciare risorse non gestite, non appena non sono necessari in modo manuale. Fornisce inoltre il <xref:System.GC.SuppressFinalize%2A?displayProperty=nameWithType> metodo che è possibile determinare il Garbage Collector che un oggetto è stato eliminato manualmente e non deve essere finalizzato più, nel qual caso la memoria dell'oggetto può essere recuperata in precedenza. I tipi che implementano il `IDisposable` interfaccia sono detti tipi disposable.  
  
 È destinato il modello Dispose per standardizzare l'utilizzo e l'implementazione di finalizzatori e `IDisposable` interfaccia.  
  
 La motivazione principale per il modello è quello di ridurre la complessità dell'implementazione del <xref:System.Object.Finalize%2A> e il <xref:System.IDisposable.Dispose%2A> metodi. La complessità deriva dal fatto che i metodi condividono alcuni ma non tutti i percorsi del codice (le differenze sono descritte più avanti in questo capitolo). Inoltre, esistono motivi storici per alcuni elementi del modello correlate all'evoluzione del supporto del linguaggio per la gestione delle risorse deterministica.  
  
 **✓ DO** implementare il modello Dispose base su tipi contenente le istanze di tipi disposable. Vedere le [base modello Dispose](#basic_pattern) sezione per informazioni dettagliate sul modello di base.  
  
 Se un tipo è responsabile per la durata degli altri oggetti disposable, gli sviluppatori devono un modo per l'eliminazione, troppo. Uso del contenitore `Dispose` metodo è un modo pratico per rendere possibile questa.  
  
 **✓ DO** implementare il modello Dispose base e di fornire un finalizzatore tipi che contiene le risorse che devono essere liberate in modo esplicito e che non dispongono di finalizzatori.  
  
 Ad esempio, il modello deve essere implementato in tipi di archiviazione di buffer di memoria non gestita. Il [finalizzabili tipi](#finalizable_types) sezione illustra le linee guida correlate a implementare i finalizzatori.  
  
 **✓ CONSIDER** implementa il modello Dispose base nelle classi che stessi non contenere le risorse non gestite o gli oggetti eliminabili ma che sono probabilmente hanno sottotipi che eseguono.  
  
 È un ottimo esempio di <xref:System.IO.Stream?displayProperty=nameWithType> classe. Sebbene sia una classe base astratta che non contiene tutte le risorse, eseguire la maggior parte delle sue sottoclassi e per questo motivo, implementa questo modello.  
  
<a name="basic_pattern"></a>   
## <a name="basic-dispose-pattern"></a>Modello Dispose base  
 L'implementazione di base del modello prevede l'implementazione di `System.IDisposable` interfaccia e la dichiarazione il `Dispose(bool)` metodo che implementa la logica di pulizia di tutte le risorse devono essere condivisi tra il `Dispose` metodo e il finalizzatore facoltativo.  
  
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
  
 Il parametro booleano `disposing` indica se il metodo è stato richiamato dal `IDisposable.Dispose` implementazione o dal finalizzatore. Il `Dispose(bool)` implementazione deve controllare il parametro prima dell'accesso ad altri oggetti di riferimento (ad esempio, il campo delle risorse nell'esempio precedente). Tali oggetti devono essere effettuati solo quando il metodo viene chiamato dal `IDisposable.Dispose` implementazione (quando il `disposing` parametro è uguale a true). Se il metodo viene richiamato dal finalizzatore (`disposing` è false), non accedere altri oggetti. Il motivo è che gli oggetti vengono finalizzati in un ordine imprevedibile e pertanto sono o una qualsiasi delle relative dipendenze, potrebbe essere già stato completato.  
  
 Inoltre, questa sezione si applica alle classi con una base che non implementano il modello Dispose. Se sta ereditando da una classe che implementa già il modello, è sufficiente eseguire l'override di `Dispose(bool)` metodo per fornire la logica di pulizia di risorse aggiuntivi.  
  
 **✓ DO** dichiarare un `protected virtual void Dispose(bool disposing)` metodo per centralizzare la logica di tutti i relativi al rilascio di risorse non gestite.  
  
 La pulizia di tutte le risorse deve verificarsi all'interno del metodo. Il metodo viene chiamato dal finalizzatore entrambi e `IDisposable.Dispose` (metodo). Il parametro sarà false se viene richiamata dall'interno un finalizzatore. Da utilizzare per verificare che qualsiasi codice in esecuzione durante la finalizzazione non acceda ad altri oggetti finalizzabili. Dettagli di implementazione i finalizzatori sono descritti nella sezione successiva.  
  
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
  
 Il `Dispose(bool)` metodo è quello che deve essere sottoposto a override dalle sottoclassi.  
  
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
  
 `Dispose` deve essere considerata una parola riservata per codificare questo modello ed evitare confusione tra i responsabili dell'implementazione, gli utenti e i compilatori. Alcuni linguaggi potrebbero scegliere di implementare automaticamente questo modello su determinati tipi.  
  
 **✓ DO** consentire il `Dispose(bool)` metodo da chiamare più volte. Il metodo è possibile scegliere di non fare nulla dopo la prima chiamata.  
  
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
  
 Se `Dispose` potrebbe generare un'eccezione, non verrà eseguita la logica di pulizia ulteriore blocco finally. Per risolvere questo problema, l'utente deve eseguire il wrapping di ogni chiamata a `Dispose` (entro il blocco finally!) in un blocco try, con conseguente ai gestori di pulizia molto complesse. Se l'esecuzione di un `Dispose(bool disposing)` (metodo), mai generano un'eccezione se l'eliminazione è false. Questa operazione interromperà il processo se in esecuzione in un contesto di finalizzatore.  
  
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
  
 In tal caso, è importante eseguire il `Close` identico all'implementazione `Dispose` e provare a implementare la `IDisposable.Dispose` metodo in modo esplicito.  
  
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
## <a name="finalizable-types"></a>Tipi finalizzabili  
 Tipi di finalizzabili sono tipi che estendono il modello Dispose base eseguendo l'override del finalizzatore e fornito percorso di codice di finalizzazione nel `Dispose(bool)` (metodo).  
  
 I finalizzatori sono notoriamente difficili da implementare in modo corretto, principalmente perché non è possibile apportare alcuni presupposti sullo stato del sistema (in genere validi) durante la loro esecuzione. Le linee guida seguenti tenere in considerazione un'attenta valutazione.  
  
 Si noti che alcune linee guida si applicano non solo al `Finalize` metodo, tuttavia, per qualsiasi codice chiamato da un finalizzatore. Nel caso il metodo Dispose modello di base definiti in precedenza, ciò significa che per la logica che viene eseguita all'interno `Dispose(bool disposing)` quando il `disposing` parametro ha valore false.  
  
 Se la classe di base già è finalizzabile e implementa il modello Dispose base, è consigliabile non eseguire l'override `Finalize` nuovamente. Deve invece eseguire l'override di `Dispose(bool)` metodo per fornire la logica di pulizia di risorse aggiuntivi.  
  
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
  
 Valutare con attenzione tutti i casi in cui si ritiene che è necessario un finalizzatore. È presente un reale costi associati alle istanze con i finalizzatori, da prestazioni sia codice punto di vista della complessità. Preferire l'utilizzo di wrapper di risorse, ad esempio <xref:System.Runtime.InteropServices.SafeHandle> per incapsulare le risorse non gestite, laddove possibile, nel qual caso un finalizzatore non è più necessario perché il wrapper è responsabile per la propria pulizia delle risorse.  
  
 **X DO NOT** finalizzabili in modo che i tipi di valore.  
  
 Solo i tipi di riferimento ottengano effettivamente completati da CLR, e che pertanto verrà ignorato qualsiasi tentativo di inserire un finalizzatore in un tipo di valore. I compilatori C++ e c# applicano questa regola.  
  
 **✓ DO** rendere finalizzabili se il tipo è responsabile del rilascio di una risorsa non gestita che non dispone di un proprio finalizzatore di un tipo.  
  
 Quando si implementa il finalizzatore, è sufficiente chiamare `Dispose(false)` e inserire la logica di pulizia di tutte le risorse all'interno di `Dispose(bool disposing)` (metodo).  
  
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
  
 In questo modo gli utenti del tipo di un mezzo per eseguire in modo esplicito la pulitura deterministica delle stesse risorse di cui è responsabile il finalizzatore.  
  
 **X DO NOT** accedere agli oggetti finalizzabili nel percorso di codice finalizzatore perché vi è rischio significativo che essi verrà sia già stati completati.  
  
 Ad esempio, un oggetto finalizzabile inutilizzato A che presenta un riferimento a un altro oggetto finalizzabile B non è possibile usare in modo affidabile B in del finalizzatore, o viceversa. I finalizzatori vengono chiamati in ordine casuale (una garanzia di ordinamento debole per la finalizzazione critica).  
  
 Inoltre, tenere presente che gli oggetti archiviati in variabili statiche verranno raccolto in determinati momenti durante uno scaricamento del dominio dell'applicazione o durante l'uscita dal processo. L'accesso a una variabile statica che fa riferimento a un oggetto finalizzabile inutilizzato (o chiamare un metodo statico che potrebbe utilizzare i valori archiviati nelle variabili statiche) potrebbe non essere sicura se <xref:System.Environment.HasShutdownStarted%2A?displayProperty=nameWithType> restituisce true.  
  
 **✓ DO** apportare le `Finalize` metodo protetto.  
  
 Gli sviluppatori c#, C++ e Visual Basic.NET non sono necessario preoccuparsi di questa operazione, perché i compilatori semplifica l'imposizione di questa linea guida.  
  
 **X DO NOT** eccezioni let escape dalla logica del finalizzatore, ad eccezione di errori critici del sistema.  
  
 Se viene generata un'eccezione da un finalizzatore, CLR si arresta l'intero processo (a partire da .NET Framework versione 2.0), altri finalizzatori impediscono l'esecuzione e le risorse da rilasciati in modo controllato.  
  
 **✓ CONSIDER** creazione e utilizzo di un oggetto finalizzabile critico (un tipo con una gerarchia che contiene <xref:System.Runtime.ConstrainedExecution.CriticalFinalizerObject>) per le situazioni in cui un finalizzatore assolutamente necessario eseguire anche in caso di applicazione forzato lo scaricamento di dominio e thread si interrompe.  
  
 *Parti protette da copyright © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*  
  
 *Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType>  
- <xref:System.Object.Finalize%2A?displayProperty=nameWithType>  
- [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)  
- [Modelli di progettazione comuni](../../../docs/standard/design-guidelines/common-design-patterns.md)  
- [Garbage Collection](../../../docs/standard/garbage-collection/index.md)
