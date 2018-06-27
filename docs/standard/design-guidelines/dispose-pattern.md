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
# <a name="dispose-pattern"></a><span data-ttu-id="dfcea-102">Modello Dispose</span><span class="sxs-lookup"><span data-stu-id="dfcea-102">Dispose Pattern</span></span>
<span data-ttu-id="dfcea-103">Tutti i programmi acquisiscono una o più risorse di sistema, ad esempio memoria, handle del sistema o le connessioni al database, nel corso della loro esecuzione.</span><span class="sxs-lookup"><span data-stu-id="dfcea-103">All programs acquire one or more system resources, such as memory, system handles, or database connections, during the course of their execution.</span></span> <span data-ttu-id="dfcea-104">Gli sviluppatori devono prestare molta attenzione quando si utilizza tali risorse di sistema, poiché deve essere liberate dopo che sono stati acquisiti e utilizzati.</span><span class="sxs-lookup"><span data-stu-id="dfcea-104">Developers have to be careful when using such system resources, because they must be released after they have been acquired and used.</span></span>  
  
 <span data-ttu-id="dfcea-105">CLR fornisce supporto per la gestione automatica della memoria.</span><span class="sxs-lookup"><span data-stu-id="dfcea-105">The CLR provides support for automatic memory management.</span></span> <span data-ttu-id="dfcea-106">Memoria gestita (memoria allocata tramite l'operatore c# `new`) non devono essere rilasciate in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="dfcea-106">Managed memory (memory allocated using the C# operator `new`) does not need to be explicitly released.</span></span> <span data-ttu-id="dfcea-107">Viene rilasciata automaticamente dal garbage collector (GC).</span><span class="sxs-lookup"><span data-stu-id="dfcea-107">It is released automatically by the garbage collector (GC).</span></span> <span data-ttu-id="dfcea-108">Ciò consente agli sviluppatori dell'attività tediosa e difficile di rilascio di memoria che ha causato uno dei motivi principali per la produttività precedenti offerto da .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="dfcea-108">This frees developers from the tedious and difficult task of releasing memory and has been one of the main reasons for the unprecedented productivity afforded by the .NET Framework.</span></span>  
  
 <span data-ttu-id="dfcea-109">Sfortunatamente, della memoria gestita è solo uno dei molti tipi di risorse di sistema.</span><span class="sxs-lookup"><span data-stu-id="dfcea-109">Unfortunately, managed memory is just one of many types of system resources.</span></span> <span data-ttu-id="dfcea-110">Risorse diverse dalla memoria gestita ancora devono essere rilasciate in modo esplicito e sono dette risorse non gestite.</span><span class="sxs-lookup"><span data-stu-id="dfcea-110">Resources other than managed memory still need to be released explicitly and are referred to as unmanaged resources.</span></span> <span data-ttu-id="dfcea-111">Il catalogo globale in modo specifico non è stato progettato per gestire tali risorse non gestite, il che significa che la responsabilità per la gestione delle risorse non gestite si trovi nelle mani degli sviluppatori di.</span><span class="sxs-lookup"><span data-stu-id="dfcea-111">The GC was specifically not designed to manage such unmanaged resources, which means that the responsibility for managing unmanaged resources lies in the hands of the developers.</span></span>  
  
 <span data-ttu-id="dfcea-112">CLR fornisce alcune informazioni utili per il rilascio di risorse non gestite.</span><span class="sxs-lookup"><span data-stu-id="dfcea-112">The CLR provides some help in releasing unmanaged resources.</span></span> <span data-ttu-id="dfcea-113"><xref:System.Object?displayProperty=nameWithType> dichiara un metodo virtuale <xref:System.Object.Finalize%2A> (detto anche il finalizzatore) che viene chiamato per il Garbage Collector prima che la memoria venga recuperata tramite il Garbage Collector e possa eseguire l'override per rilasciare le risorse non gestite.</span><span class="sxs-lookup"><span data-stu-id="dfcea-113"><xref:System.Object?displayProperty=nameWithType> declares a virtual method <xref:System.Object.Finalize%2A> (also called the finalizer) that is called by the GC before the object’s memory is reclaimed by the GC and can be overridden to release unmanaged resources.</span></span> <span data-ttu-id="dfcea-114">Tipi che eseguono l'override del finalizzatore vengono definiti come tipi di finalizzazione.</span><span class="sxs-lookup"><span data-stu-id="dfcea-114">Types that override the finalizer are referred to as finalizable types.</span></span>  
  
 <span data-ttu-id="dfcea-115">Sebbene i finalizzatori sono efficaci in alcuni scenari di pulizia, presentano due svantaggi significativi:</span><span class="sxs-lookup"><span data-stu-id="dfcea-115">Although finalizers are effective in some cleanup scenarios, they have two significant drawbacks:</span></span>  
  
-   <span data-ttu-id="dfcea-116">Il finalizzatore viene chiamato quando il Garbage Collector rileva che un oggetto è idoneo per la raccolta.</span><span class="sxs-lookup"><span data-stu-id="dfcea-116">The finalizer is called when the GC detects that an object is eligible for collection.</span></span> <span data-ttu-id="dfcea-117">Ciò si verifica in alcune non determinato periodo di tempo dopo che la risorsa non è più necessaria.</span><span class="sxs-lookup"><span data-stu-id="dfcea-117">This happens at some undetermined period of time after the resource is not needed anymore.</span></span> <span data-ttu-id="dfcea-118">Il ritardo tra quando lo sviluppatore può o rilasciare la risorsa e l'ora quando la risorsa viene effettivamente rilasciata dal finalizzatore può essere inaccettabile in programmi che acquisiscono molte risorse insufficienti (risorse che possono essere facilmente esaurite) o in casi in cui le risorse sono costose da mantenere in uso (ad esempio, i buffer di grandi quantità di memoria non gestito).</span><span class="sxs-lookup"><span data-stu-id="dfcea-118">The delay between when the developer could or would like to release the resource and the time when the resource is actually released by the finalizer might be unacceptable in programs that acquire many scarce resources (resources that can be easily exhausted) or in cases in which resources are costly to keep in use (e.g., large unmanaged memory buffers).</span></span>  
  
-   <span data-ttu-id="dfcea-119">Quando CLR è necessario chiamare un finalizzatore, è necessario posticipare la raccolta di memoria dell'oggetto fino alla successiva arrotondare di garbage collection (finalizzatori eseguiti tra le raccolte).</span><span class="sxs-lookup"><span data-stu-id="dfcea-119">When the CLR needs to call a finalizer, it must postpone collection of the object’s memory until the next round of garbage collection (the finalizers run between collections).</span></span> <span data-ttu-id="dfcea-120">Ciò significa che la memoria dell'oggetto (e tutti gli oggetti che cui fa riferimento) non verranno rilasciati per un periodo di tempo.</span><span class="sxs-lookup"><span data-stu-id="dfcea-120">This means that the object’s memory (and all objects it refers to) will not be released for a longer period of time.</span></span>  
  
 <span data-ttu-id="dfcea-121">Pertanto, basarsi esclusivamente su finalizzatori potrebbero non essere appropriate in molti scenari quando è importante recuperare le risorse non gestite al più presto, quando si lavora con risorse limitate, o in elevata ad alte prestazioni scenari in cui l'overhead aggiunto di Garbage Collection di finalizzazione non è accettabile.</span><span class="sxs-lookup"><span data-stu-id="dfcea-121">Therefore, relying exclusively on finalizers might not be appropriate in many scenarios when it is important to reclaim unmanaged resources as quickly as possible, when dealing with scarce resources, or in highly performant scenarios in which the added GC overhead of finalization is unacceptable.</span></span>  
  
 <span data-ttu-id="dfcea-122">Il Framework fornisce il <xref:System.IDisposable?displayProperty=nameWithType> interfaccia che deve essere implementata per lo sviluppatore di rilasciare le risorse non gestite, non appena non sono necessari in modo manuale.</span><span class="sxs-lookup"><span data-stu-id="dfcea-122">The Framework provides the <xref:System.IDisposable?displayProperty=nameWithType> interface that should be implemented to provide the developer a manual way to release unmanaged resources as soon as they are not needed.</span></span> <span data-ttu-id="dfcea-123">Fornisce inoltre il <xref:System.GC.SuppressFinalize%2A?displayProperty=nameWithType> metodo grado di stabilire il catalogo globale che un oggetto è stato eliminato manualmente e non necessita di essere finalizzati più, nel qual caso la memoria dell'oggetto può essere recuperata in precedenza.</span><span class="sxs-lookup"><span data-stu-id="dfcea-123">It also provides the <xref:System.GC.SuppressFinalize%2A?displayProperty=nameWithType> method that can tell the GC that an object was manually disposed of and does not need to be finalized anymore, in which case the object’s memory can be reclaimed earlier.</span></span> <span data-ttu-id="dfcea-124">I tipi che implementano il `IDisposable` interfaccia sono definiti tipi disposable.</span><span class="sxs-lookup"><span data-stu-id="dfcea-124">Types that implement the `IDisposable` interface are referred to as disposable types.</span></span>  
  
 <span data-ttu-id="dfcea-125">È destinato il modello Dispose per standardizzare le informazioni sull'utilizzo e l'implementazione di finalizzatori e `IDisposable` interfaccia.</span><span class="sxs-lookup"><span data-stu-id="dfcea-125">The Dispose Pattern is intended to standardize the usage and implementation of finalizers and the `IDisposable` interface.</span></span>  
  
 <span data-ttu-id="dfcea-126">La principale motivazione per il modello consiste nel ridurre la complessità dell'implementazione del <xref:System.Object.Finalize%2A> e il <xref:System.IDisposable.Dispose%2A> metodi.</span><span class="sxs-lookup"><span data-stu-id="dfcea-126">The main motivation for the pattern is to reduce the complexity of the implementation of the <xref:System.Object.Finalize%2A> and the <xref:System.IDisposable.Dispose%2A> methods.</span></span> <span data-ttu-id="dfcea-127">La complessità deriva dal fatto che i metodi condividono alcuni, ma non tutti i percorsi del codice (le differenze sono illustrate più avanti in questo capitolo).</span><span class="sxs-lookup"><span data-stu-id="dfcea-127">The complexity stems from the fact that the methods share some but not all code paths (the differences are described later in the chapter).</span></span> <span data-ttu-id="dfcea-128">Inoltre, esistono motivi storici per alcuni elementi del modello correlato all'evoluzione del supporto delle lingue per la gestione delle risorse deterministica.</span><span class="sxs-lookup"><span data-stu-id="dfcea-128">In addition, there are historical reasons for some elements of the pattern related to the evolution of language support for deterministic resource management.</span></span>  
  
 <span data-ttu-id="dfcea-129">**✓ SI** implementare il modello Dispose base su tipi contenente le istanze di tipi disposable.</span><span class="sxs-lookup"><span data-stu-id="dfcea-129">**✓ DO** implement the Basic Dispose Pattern on types containing instances of disposable types.</span></span> <span data-ttu-id="dfcea-130">Vedere la [base modello Dispose](#basic_pattern) sezione per informazioni dettagliate sul modello di base.</span><span class="sxs-lookup"><span data-stu-id="dfcea-130">See the [Basic Dispose Pattern](#basic_pattern) section for details on the basic pattern.</span></span>  
  
 <span data-ttu-id="dfcea-131">Se un tipo è responsabile per la durata di altri oggetti eliminabili, gli sviluppatori devono un modo per l'eliminazione, troppo.</span><span class="sxs-lookup"><span data-stu-id="dfcea-131">If a type is responsible for the lifetime of other disposable objects, developers need a way to dispose of them, too.</span></span> <span data-ttu-id="dfcea-132">Usa il contenitore `Dispose` metodo è un modo pratico per rendere possibile questa.</span><span class="sxs-lookup"><span data-stu-id="dfcea-132">Using the container’s `Dispose` method is a convenient way to make this possible.</span></span>  
  
 <span data-ttu-id="dfcea-133">**✓ SI** implementare il modello Dispose base e di fornire un finalizzatore tipi che contiene le risorse che devono essere liberate in modo esplicito e che non dispongono di finalizzatori.</span><span class="sxs-lookup"><span data-stu-id="dfcea-133">**✓ DO** implement the Basic Dispose Pattern and provide a finalizer on types holding resources that need to be freed explicitly and that do not have finalizers.</span></span>  
  
 <span data-ttu-id="dfcea-134">Ad esempio, lo schema deve essere implementato sui tipi di archiviare i buffer di memoria non gestita.</span><span class="sxs-lookup"><span data-stu-id="dfcea-134">For example, the pattern should be implemented on types storing unmanaged memory buffers.</span></span> <span data-ttu-id="dfcea-135">Il [finalizzabili tipi](#finalizable_types) sezione vengono illustrate le linee guida relative all'implementazione i finalizzatori.</span><span class="sxs-lookup"><span data-stu-id="dfcea-135">The [Finalizable Types](#finalizable_types) section discusses guidelines related to implementing finalizers.</span></span>  
  
 <span data-ttu-id="dfcea-136">**✓ Provare a** implementa il modello Dispose base nelle classi che stessi non contenere le risorse non gestite o gli oggetti eliminabili ma che sono probabilmente hanno sottotipi che eseguono.</span><span class="sxs-lookup"><span data-stu-id="dfcea-136">**✓ CONSIDER** implementing the Basic Dispose Pattern on classes that themselves don’t hold unmanaged resources or disposable objects but are likely to have subtypes that do.</span></span>  
  
 <span data-ttu-id="dfcea-137">È un ottimo esempio di ciò il <xref:System.IO.Stream?displayProperty=nameWithType> classe.</span><span class="sxs-lookup"><span data-stu-id="dfcea-137">A great example of this is the <xref:System.IO.Stream?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="dfcea-138">Sebbene sia una classe base astratta che non contiene tutte le risorse, la maggior parte delle sue sottoclassi non e per questo motivo, implementato questo modello.</span><span class="sxs-lookup"><span data-stu-id="dfcea-138">Although it is an abstract base class that doesn’t hold any resources, most of its subclasses do and because of this, it implements this pattern.</span></span>  
  
<a name="basic_pattern"></a>   
## <a name="basic-dispose-pattern"></a><span data-ttu-id="dfcea-139">Modello Dispose base</span><span class="sxs-lookup"><span data-stu-id="dfcea-139">Basic Dispose Pattern</span></span>  
 <span data-ttu-id="dfcea-140">L'implementazione di base del modello prevede l'implementazione il `System.IDisposable` interfaccia e si dichiara la `Dispose(bool)` metodo che implementa la logica di pulizia risorse tutti essere condivise tra il `Dispose` metodo e il finalizzatore facoltativo.</span><span class="sxs-lookup"><span data-stu-id="dfcea-140">The basic implementation of the pattern involves implementing the `System.IDisposable` interface and declaring the `Dispose(bool)` method that implements all resource cleanup logic to be shared between the `Dispose` method and the optional finalizer.</span></span>  
  
 <span data-ttu-id="dfcea-141">Nell'esempio seguente viene illustrata un'implementazione semplice del modello di base:</span><span class="sxs-lookup"><span data-stu-id="dfcea-141">The following example shows a simple implementation of the basic pattern:</span></span>  
  
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
  
 <span data-ttu-id="dfcea-142">Il parametro booleano `disposing` indica se il metodo è stato richiamato dal `IDisposable.Dispose` implementazione o dal finalizzatore.</span><span class="sxs-lookup"><span data-stu-id="dfcea-142">The Boolean parameter `disposing` indicates whether the method was invoked from the `IDisposable.Dispose` implementation or from the finalizer.</span></span> <span data-ttu-id="dfcea-143">Il `Dispose(bool)` implementazione deve controllare il parametro prima dell'accesso ad altri oggetti di riferimento (ad esempio, il campo delle risorse nell'esempio precedente).</span><span class="sxs-lookup"><span data-stu-id="dfcea-143">The `Dispose(bool)` implementation should check the parameter before accessing other reference objects (e.g., the resource field in the preceding sample).</span></span> <span data-ttu-id="dfcea-144">Tali oggetti devono essere effettuati solo quando il metodo viene chiamato dal `IDisposable.Dispose` implementazione (quando il `disposing` parametro è uguale a true).</span><span class="sxs-lookup"><span data-stu-id="dfcea-144">Such objects should only be accessed when the method is called from the `IDisposable.Dispose` implementation (when the `disposing` parameter is equal to true).</span></span> <span data-ttu-id="dfcea-145">Se il metodo viene richiamato dal finalizzatore (`disposing` è false), non accedere altri oggetti.</span><span class="sxs-lookup"><span data-stu-id="dfcea-145">If the method is invoked from the finalizer (`disposing` is false), other objects should not be accessed.</span></span> <span data-ttu-id="dfcea-146">Il motivo è che gli oggetti vengono finalizzati in un ordine imprevedibile e pertanto o una delle relative dipendenze, potrebbe essere già stata completata.</span><span class="sxs-lookup"><span data-stu-id="dfcea-146">The reason is that objects are finalized in an unpredictable order and so they, or any of their dependencies, might already have been finalized.</span></span>  
  
 <span data-ttu-id="dfcea-147">Inoltre, questa sezione si applica alle classi con una base che non implementano il modello Dispose.</span><span class="sxs-lookup"><span data-stu-id="dfcea-147">Also, this section applies to classes with a base that does not already implement the Dispose Pattern.</span></span> <span data-ttu-id="dfcea-148">Se sta ereditando da una classe che implementa già il modello, è sufficiente eseguire l'override di `Dispose(bool)` metodo per fornire la logica di pulizia di risorse aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="dfcea-148">If you are inheriting from a class that already implements the pattern, simply override the `Dispose(bool)` method to provide additional resource cleanup logic.</span></span>  
  
 <span data-ttu-id="dfcea-149">**✓ SI** dichiarare un `protected virtual void Dispose(bool disposing)` metodo per centralizzare la logica di tutti i relativi al rilascio di risorse non gestite.</span><span class="sxs-lookup"><span data-stu-id="dfcea-149">**✓ DO** declare a `protected virtual void Dispose(bool disposing)` method to centralize all logic related to releasing unmanaged resources.</span></span>  
  
 <span data-ttu-id="dfcea-150">Pulizia di tutte le risorse deve essere eseguito in questo metodo.</span><span class="sxs-lookup"><span data-stu-id="dfcea-150">All resource cleanup should occur in this method.</span></span> <span data-ttu-id="dfcea-151">Il metodo viene chiamato da entrambi il finalizzatore e il `IDisposable.Dispose` metodo.</span><span class="sxs-lookup"><span data-stu-id="dfcea-151">The method is called from both the finalizer and the `IDisposable.Dispose` method.</span></span> <span data-ttu-id="dfcea-152">Il parametro sarà false se viene richiamata dall'interno un finalizzatore.</span><span class="sxs-lookup"><span data-stu-id="dfcea-152">The parameter will be false if being invoked from inside a finalizer.</span></span> <span data-ttu-id="dfcea-153">È consigliabile utilizzarlo per verificare che qualsiasi codice in esecuzione durante la finalizzazione non accede ad altri oggetti finalizzabili.</span><span class="sxs-lookup"><span data-stu-id="dfcea-153">It should be used to ensure any code running during finalization is not accessing other finalizable objects.</span></span> <span data-ttu-id="dfcea-154">Dettagli dell'implementazione di finalizzatori sono descritti nella sezione successiva.</span><span class="sxs-lookup"><span data-stu-id="dfcea-154">Details of implementing finalizers are described in the next section.</span></span>  
  
```csharp
protected virtual void Dispose(bool disposing) {  
    if (disposing) {  
        if (resource!= null) resource.Dispose();  
    }  
}  
```  
  
 <span data-ttu-id="dfcea-155">**✓ SI** implementare il `IDisposable` interfaccia semplicemente chiamando `Dispose(true)` seguito da `GC.SuppressFinalize(this)`.</span><span class="sxs-lookup"><span data-stu-id="dfcea-155">**✓ DO** implement the `IDisposable` interface by simply calling `Dispose(true)` followed by `GC.SuppressFinalize(this)`.</span></span>  
  
 <span data-ttu-id="dfcea-156">La chiamata a `SuppressFinalize` dovrebbero verificarsi solo se `Dispose(true)` viene eseguita correttamente.</span><span class="sxs-lookup"><span data-stu-id="dfcea-156">The call to `SuppressFinalize` should only occur if `Dispose(true)` executes successfully.</span></span>  
  
```csharp
public void Dispose(){  
    Dispose(true);  
    GC.SuppressFinalize(this);  
}  
```  
  
 <span data-ttu-id="dfcea-157">**X non** rendere senza parametri `Dispose` metodo virtuale.</span><span class="sxs-lookup"><span data-stu-id="dfcea-157">**X DO NOT** make the parameterless `Dispose` method virtual.</span></span>  
  
 <span data-ttu-id="dfcea-158">Il `Dispose(bool)` metodo è quella che deve essere sottoposto a override dalle sottoclassi.</span><span class="sxs-lookup"><span data-stu-id="dfcea-158">The `Dispose(bool)` method is the one that should be overridden by subclasses.</span></span>  
  
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
  
 <span data-ttu-id="dfcea-159">**X non** dichiarare tutti gli overload del `Dispose` metodo diverso da `Dispose()` e `Dispose(bool)`.</span><span class="sxs-lookup"><span data-stu-id="dfcea-159">**X DO NOT** declare any overloads of the `Dispose` method other than `Dispose()` and `Dispose(bool)`.</span></span>  
  
 <span data-ttu-id="dfcea-160">`Dispose` deve essere considerata una parola riservata per codificare questo modello e per impedire confusione tra i responsabili dell'implementazione, utenti e i compilatori.</span><span class="sxs-lookup"><span data-stu-id="dfcea-160">`Dispose` should be considered a reserved word to help codify this pattern and prevent confusion among implementers, users, and compilers.</span></span> <span data-ttu-id="dfcea-161">Alcune lingue potrebbero scegliere di implementare automaticamente questo modello su determinati tipi.</span><span class="sxs-lookup"><span data-stu-id="dfcea-161">Some languages might choose to automatically implement this pattern on certain types.</span></span>  
  
 <span data-ttu-id="dfcea-162">**✓ SI** consentire il `Dispose(bool)` metodo da chiamare più volte.</span><span class="sxs-lookup"><span data-stu-id="dfcea-162">**✓ DO** allow the `Dispose(bool)` method to be called more than once.</span></span> <span data-ttu-id="dfcea-163">Il metodo è possibile scegliere di non eseguire alcuna operazione dopo la prima chiamata.</span><span class="sxs-lookup"><span data-stu-id="dfcea-163">The method might choose to do nothing after the first call.</span></span>  
  
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
  
 <span data-ttu-id="dfcea-164">**X evitare** generare un'eccezione dall'interno `Dispose(bool)` tranne che in alcune situazioni critiche in cui il processo di contenitore è stato danneggiato (perdite, lo stato condiviso non coerente, ecc.).</span><span class="sxs-lookup"><span data-stu-id="dfcea-164">**X AVOID** throwing an exception from within `Dispose(bool)` except under critical situations where the containing process has been corrupted (leaks, inconsistent shared state, etc.).</span></span>  
  
 <span data-ttu-id="dfcea-165">Gli utenti si aspettano che una chiamata a `Dispose` non genererà un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="dfcea-165">Users expect that a call to `Dispose` will not raise an exception.</span></span>  
  
 <span data-ttu-id="dfcea-166">Se `Dispose` potrebbe generare un'eccezione, non verrà eseguita la logica di pulizia ulteriore blocco finally.</span><span class="sxs-lookup"><span data-stu-id="dfcea-166">If `Dispose` could raise an exception, further finally-block cleanup logic will not execute.</span></span> <span data-ttu-id="dfcea-167">Per risolvere questo problema, l'utente dovrà eseguire il wrapping di ogni chiamata a `Dispose` (all'interno di blocco finally!) in un blocco try, determinando i gestori di pulizia molto complessi.</span><span class="sxs-lookup"><span data-stu-id="dfcea-167">To work around this, the user would need to wrap every call to `Dispose` (within the finally block!) in a try block, which leads to very complex cleanup handlers.</span></span> <span data-ttu-id="dfcea-168">Se l'esecuzione di un `Dispose(bool disposing)` (metodo), mai generano un'eccezione se disposing è false.</span><span class="sxs-lookup"><span data-stu-id="dfcea-168">If executing a `Dispose(bool disposing)` method, never throw an exception if disposing is false.</span></span> <span data-ttu-id="dfcea-169">In questo modo interromperà il processo se l'esecuzione all'interno di un contesto finalizzatore.</span><span class="sxs-lookup"><span data-stu-id="dfcea-169">Doing so will terminate the process if executing inside a finalizer context.</span></span>  
  
 <span data-ttu-id="dfcea-170">**✓ SI** generano un <xref:System.ObjectDisposedException> da qualsiasi membro non può essere usati dopo che l'oggetto è stato eliminato di.</span><span class="sxs-lookup"><span data-stu-id="dfcea-170">**✓ DO** throw an <xref:System.ObjectDisposedException> from any member that cannot be used after the object has been disposed of.</span></span>  
  
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
  
 <span data-ttu-id="dfcea-171">**✓ Provare a** fornendo meccanismo `Close()`, oltre al `Dispose()`, se chiudere è terminologia nell'area.</span><span class="sxs-lookup"><span data-stu-id="dfcea-171">**✓ CONSIDER** providing method `Close()`, in addition to the `Dispose()`, if close is standard terminology in the area.</span></span>  
  
 <span data-ttu-id="dfcea-172">In tal caso, è importante eseguire il `Close` identica all'implementazione `Dispose` e provare a implementare la `IDisposable.Dispose` metodo in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="dfcea-172">When doing so, it is important that you make the `Close` implementation identical to `Dispose` and consider implementing the `IDisposable.Dispose` method explicitly.</span></span>  
  
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
## <a name="finalizable-types"></a><span data-ttu-id="dfcea-173">Tipi di finalizzazione</span><span class="sxs-lookup"><span data-stu-id="dfcea-173">Finalizable Types</span></span>  
 <span data-ttu-id="dfcea-174">Tipi finalizzabili sono tipi che estendono il modello Dispose base eseguendo l'override del finalizzatore e fornendo il percorso di codice la finalizzazione nel `Dispose(bool)` metodo.</span><span class="sxs-lookup"><span data-stu-id="dfcea-174">Finalizable types are types that extend the Basic Dispose Pattern by overriding the finalizer and providing finalization code path in the `Dispose(bool)` method.</span></span>  
  
 <span data-ttu-id="dfcea-175">I finalizzatori sono notoriamente difficili da implementare correttamente, soprattutto perché non è possibile apportare alcuni presupposti (in genere validi) sullo stato del sistema durante l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="dfcea-175">Finalizers are notoriously difficult to implement correctly, primarily because you cannot make certain (normally valid) assumptions about the state of the system during their execution.</span></span> <span data-ttu-id="dfcea-176">Le linee guida seguenti devono essere prese in un'attenta considerazione.</span><span class="sxs-lookup"><span data-stu-id="dfcea-176">The following guidelines should be taken into careful consideration.</span></span>  
  
 <span data-ttu-id="dfcea-177">Si noti che alcune linee guida si applicano non solo al `Finalize` (metodo), ma a qualsiasi codice chiamato da un finalizzatore.</span><span class="sxs-lookup"><span data-stu-id="dfcea-177">Note that some of the guidelines apply not just to the `Finalize` method, but to any code called from a finalizer.</span></span> <span data-ttu-id="dfcea-178">Nel caso il metodo Dispose modello di base definiti in precedenza, questo significa logica che viene eseguita all'interno di `Dispose(bool disposing)` quando il `disposing` parametro è false.</span><span class="sxs-lookup"><span data-stu-id="dfcea-178">In the case of the Basic Dispose Pattern previously defined, this means logic that executes inside `Dispose(bool disposing)` when the `disposing` parameter is false.</span></span>  
  
 <span data-ttu-id="dfcea-179">Se la classe di base già è finalizzabile e implementa il modello Dispose base, è consigliabile non eseguire l'override `Finalize` nuovamente.</span><span class="sxs-lookup"><span data-stu-id="dfcea-179">If the base class already is finalizable and implements the Basic Dispose Pattern, you should not override `Finalize` again.</span></span> <span data-ttu-id="dfcea-180">Deve invece eseguire l'override di `Dispose(bool)` metodo per fornire la logica di pulizia di risorse aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="dfcea-180">You should instead just override the `Dispose(bool)` method to provide additional resource cleanup logic.</span></span>  
  
 <span data-ttu-id="dfcea-181">Il codice seguente viene illustrato un esempio di un tipo finalizzabile:</span><span class="sxs-lookup"><span data-stu-id="dfcea-181">The following code shows an example of a finalizable type:</span></span>  
  
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
  
 <span data-ttu-id="dfcea-182">**X evitare** effettua tipi finalizzabile.</span><span class="sxs-lookup"><span data-stu-id="dfcea-182">**X AVOID** making types finalizable.</span></span>  
  
 <span data-ttu-id="dfcea-183">Considerare con attenzione tutti i casi in cui si ritiene che è necessario un finalizzatore.</span><span class="sxs-lookup"><span data-stu-id="dfcea-183">Carefully consider any case in which you think a finalizer is needed.</span></span> <span data-ttu-id="dfcea-184">È presente un reale costi associati alle istanze con i finalizzatori, dal punto vista complessità sia delle prestazioni sia del codice.</span><span class="sxs-lookup"><span data-stu-id="dfcea-184">There is a real cost associated with instances with finalizers, from both a performance and code complexity standpoint.</span></span> <span data-ttu-id="dfcea-185">Preferire l'utilizzo di wrapper di risorse, ad esempio <xref:System.Runtime.InteropServices.SafeHandle> per incapsulare le risorse non gestite, laddove possibile, nel qual caso un finalizzatore diventa non necessario perché il wrapper è responsabile della pulizia di risorse.</span><span class="sxs-lookup"><span data-stu-id="dfcea-185">Prefer using resource wrappers such as <xref:System.Runtime.InteropServices.SafeHandle> to encapsulate unmanaged resources where possible, in which case a finalizer becomes unnecessary because the wrapper is responsible for its own resource cleanup.</span></span>  
  
 <span data-ttu-id="dfcea-186">**X non** finalizzabili in modo che i tipi di valore.</span><span class="sxs-lookup"><span data-stu-id="dfcea-186">**X DO NOT** make value types finalizable.</span></span>  
  
 <span data-ttu-id="dfcea-187">Solo i tipi di riferimento ottengano finalizzati effettivamente da CLR, e pertanto verrà ignorata qualsiasi tentativo di inserire un finalizzatore in un tipo di valore.</span><span class="sxs-lookup"><span data-stu-id="dfcea-187">Only reference types actually get finalized by the CLR, and thus any attempt to place a finalizer on a value type will be ignored.</span></span> <span data-ttu-id="dfcea-188">I compilatori c# e C++ applicano questa regola.</span><span class="sxs-lookup"><span data-stu-id="dfcea-188">The C# and C++ compilers enforce this rule.</span></span>  
  
 <span data-ttu-id="dfcea-189">**✓ SI** rendere finalizzabili se il tipo è responsabile del rilascio di una risorsa non gestita che non dispone di un proprio finalizzatore di un tipo.</span><span class="sxs-lookup"><span data-stu-id="dfcea-189">**✓ DO** make a type finalizable if the type is responsible for releasing an unmanaged resource that does not have its own finalizer.</span></span>  
  
 <span data-ttu-id="dfcea-190">Quando si implementa il finalizzatore, è sufficiente chiamare `Dispose(false)` e inserire logica di pulizia in tutte le risorse all'interno di `Dispose(bool disposing)` metodo.</span><span class="sxs-lookup"><span data-stu-id="dfcea-190">When implementing the finalizer, simply call `Dispose(false)` and place all resource cleanup logic inside the `Dispose(bool disposing)` method.</span></span>  
  
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
  
 <span data-ttu-id="dfcea-191">**✓ SI** implementare il modello Dispose base su ogni tipo di finalizzazione.</span><span class="sxs-lookup"><span data-stu-id="dfcea-191">**✓ DO** implement the Basic Dispose Pattern on every finalizable type.</span></span>  
  
 <span data-ttu-id="dfcea-192">In questo modo gli utenti del tipo di un modo per eseguire in modo esplicito la pulitura deterministica delle stesse risorse di cui è responsabile il finalizzatore.</span><span class="sxs-lookup"><span data-stu-id="dfcea-192">This gives users of the type a means to explicitly perform deterministic cleanup of those same resources for which the finalizer is responsible.</span></span>  
  
 <span data-ttu-id="dfcea-193">**X non** accedere agli oggetti finalizzabili nel percorso di codice finalizzatore perché vi è rischio significativo che essi verrà sia già stati completati.</span><span class="sxs-lookup"><span data-stu-id="dfcea-193">**X DO NOT** access any finalizable objects in the finalizer code path, because there is significant risk that they will have already been finalized.</span></span>  
  
 <span data-ttu-id="dfcea-194">Ad esempio, un oggetto finalizzabile A che presenta un riferimento a un altro oggetto finalizzabile B non è possibile usare in modo affidabile B nel finalizzatore, o viceversa.</span><span class="sxs-lookup"><span data-stu-id="dfcea-194">For example, a finalizable object A that has a reference to another finalizable object B cannot reliably use B in A’s finalizer, or vice versa.</span></span> <span data-ttu-id="dfcea-195">I finalizzatori vengono chiamati in ordine casuale (se non si una garanzia di ordinamento vulnerabile per la finalizzazione critico).</span><span class="sxs-lookup"><span data-stu-id="dfcea-195">Finalizers are called in a random order (short of a weak ordering guarantee for critical finalization).</span></span>  
  
 <span data-ttu-id="dfcea-196">Inoltre, tenere presente che gli oggetti archiviati in variabili statiche verranno raccolto in determinati momenti durante uno scaricamento del dominio applicazione o durante l'uscita dal processo.</span><span class="sxs-lookup"><span data-stu-id="dfcea-196">Also, be aware that objects stored in static variables will get collected at certain points during an application domain unload or while exiting the process.</span></span> <span data-ttu-id="dfcea-197">L'accesso a una variabile statica che fa riferimento a un oggetto finalizzabile (o chiamare un metodo statico che potrebbe utilizzare i valori archiviati in variabili statiche) potrebbe non essere sicura se <xref:System.Environment.HasShutdownStarted%2A?displayProperty=nameWithType> restituisce true.</span><span class="sxs-lookup"><span data-stu-id="dfcea-197">Accessing a static variable that refers to a finalizable object (or calling a static method that might use values stored in static variables) might not be safe if <xref:System.Environment.HasShutdownStarted%2A?displayProperty=nameWithType> returns true.</span></span>  
  
 <span data-ttu-id="dfcea-198">**✓ SI** apportare le `Finalize` metodo protetto.</span><span class="sxs-lookup"><span data-stu-id="dfcea-198">**✓ DO** make your `Finalize` method protected.</span></span>  
  
 <span data-ttu-id="dfcea-199">Gli sviluppatori c#, C++ e Visual Basic.NET non devono preoccuparsi di questa operazione, perché i compilatori della Guida per applicare questa linea guida.</span><span class="sxs-lookup"><span data-stu-id="dfcea-199">C#, C++, and VB.NET developers do not need to worry about this, because the compilers help to enforce this guideline.</span></span>  
  
 <span data-ttu-id="dfcea-200">**X non** eccezioni let escape dalla logica del finalizzatore, ad eccezione di errori critici del sistema.</span><span class="sxs-lookup"><span data-stu-id="dfcea-200">**X DO NOT** let exceptions escape from the finalizer logic, except for system-critical failures.</span></span>  
  
 <span data-ttu-id="dfcea-201">Se viene generata un'eccezione da un finalizzatore, CLR si arresterà l'intero processo (a partire da .NET Framework versione 2.0), altri finalizzatori impediscono l'esecuzione e le risorse da rilasciati in modo controllato.</span><span class="sxs-lookup"><span data-stu-id="dfcea-201">If an exception is thrown from a finalizer, the CLR will shut down the entire process (as of .NET Framework version 2.0), preventing other finalizers from executing and resources from being released in a controlled manner.</span></span>  
  
 <span data-ttu-id="dfcea-202">**✓ si consiglia** creazione e utilizzo di un oggetto finalizzabile critico (un tipo con una gerarchia che contiene <xref:System.Runtime.ConstrainedExecution.CriticalFinalizerObject>) per le situazioni in cui un finalizzatore assolutamente necessario eseguire anche in caso di applicazione forzato lo scaricamento di dominio e thread si interrompe.</span><span class="sxs-lookup"><span data-stu-id="dfcea-202">**✓ CONSIDER** creating and using a critical finalizable object (a type with a type hierarchy that contains <xref:System.Runtime.ConstrainedExecution.CriticalFinalizerObject>) for situations in which a finalizer absolutely must execute even in the face of forced application domain unloads and thread aborts.</span></span>  
  
 <span data-ttu-id="dfcea-203">*Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*</span><span class="sxs-lookup"><span data-stu-id="dfcea-203">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="dfcea-204">*State ristampate dall'autorizzazione di Pearson Education, Inc. dal [Framework linee guida di progettazione: convenzioni, idiomi e modelli per le librerie .NET riutilizzabile, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="dfcea-204">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfcea-205">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dfcea-205">See Also</span></span>  
 <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType>  
 <xref:System.Object.Finalize%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="dfcea-206">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="dfcea-206">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="dfcea-207">Modelli di progettazione comuni</span><span class="sxs-lookup"><span data-stu-id="dfcea-207">Common Design Patterns</span></span>](../../../docs/standard/design-guidelines/common-design-patterns.md)  
 [<span data-ttu-id="dfcea-208">Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="dfcea-208">Garbage Collection</span></span>](../../../docs/standard/garbage-collection/index.md)
