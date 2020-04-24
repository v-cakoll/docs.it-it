---
title: Linee guida per l'utilizzo di Memory<T> e Span<T>
ms.date: 10/01/2018
helpviewer_keywords:
- Memory&lt;T&gt; and Span&lt;T&gt; best practices
- using Memory&lt;T&gt; and Span&lt;T&gt;
ms.openlocfilehash: 1f0d513e8bfd1668ee548315597385c555d374ef
ms.sourcegitcommit: 8b02d42f93adda304246a47f49f6449fc74a3af4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/24/2020
ms.locfileid: "82135776"
---
# <a name="memoryt-and-spant-usage-guidelines"></a>Linee guida per l'utilizzo di Memory\<T> e Span\<T>

.NET Core include vari tipi che rappresentano una regione contigua arbitraria della memoria. In .NET Core 2.0 sono stati introdotti <xref:System.Span%601> e <xref:System.ReadOnlySpan%601>, ovvero buffer di memoria leggeri che possono essere supportati da memoria gestita o non gestita. Dato che questi tipi possono solo essere archiviati nello stack, non sono adatti per vari scenari, incluse le chiamate di metodi asincrone. .NET Core 2.1 introduce alcuni tipi aggiuntivi, tra cui <xref:System.Memory%601>, <xref:System.ReadOnlyMemory%601>, <xref:System.Buffers.IMemoryOwner%601> e <xref:System.Buffers.MemoryPool%601>. Come <xref:System.Span%601>, <xref:System.Memory%601> e i tipi correlati possono essere supportati da memoria gestita e non gestita. Diversamente da <xref:System.Span%601>, <xref:System.Memory%601> supporta l'archiviazione nell'heap gestito.

Sia <xref:System.Span%601> che <xref:System.Memory%601> sono buffer di dati strutturati che possono essere usati nelle pipeline. Questo significa che sono progettati in modo che alcuni o tutti i dati possano essere passati in modo efficiente ai componenti nella pipeline, che possono elaborarli e facoltativamente modificare il buffer. Dato che <xref:System.Memory%601> e i tipi correlati sono accessibili da più componenti o da più thread, è importante che gli sviluppatori seguano alcune linee guida sull'utilizzo standard in modo da produrre codice solido.

## <a name="owners-consumers-and-lifetime-management"></a>Proprietari, consumer e gestione della durata

Poiché i buffer possono essere passati tra le API e dato che i buffer sono in alcuni casi accessibili da più thread, è importante prendere in considerazione la gestione della durata. Esistono tre concetti principali:

- **Proprietà**. Il proprietario di un'istanza del buffer è responsabile della gestione della durata, inclusa l'eliminazione definitiva del buffer quando non è più in uso. Tutti i buffer hanno un solo proprietario. Il proprietario è in genere il componente che ha creato il buffer o che ha ricevuto il buffer da una factory. La proprietà può anche essere trasferita. Il **componente A** può cedere il controllo del buffer al **componente-B** e a quel punto il **componente A** non può più usare il buffer e il **componente B ** diventa responsabile dell'eliminazione definitiva del buffer quando non è più in uso.

- A **consumo**. Il consumer di un'istanza del buffer è autorizzato a usare l'istanza del buffer leggendo da tale istanza e forse anche scrivendo in tale istanza. I buffer possono avere un solo consumer alla volta, a meno che non venga fornito un meccanismo di sincronizzazione esterno. Si noti che il consumer di un buffer attivo non è necessariamente il proprietario del buffer.

- **Lease**. Il lease è il periodo di tempo per cui un particolare componente è autorizzato a essere il consumer del buffer.

L'esempio di pseudocodice seguente illustra questi tre concetti. Include un metodo `Main` che crea un'istanza di un buffer <xref:System.Memory%601> di tipo <xref:System.Char>, chiama il metodo `WriteInt32ToBuffer` per scrivere la rappresentazione stringa di un intero nel buffer e quindi chiama il metodo `DisplayBufferToConsole` per visualizzare il valore del buffer.

```csharp
using System;

class Program
{
    // Write 'value' as a human-readable string to the output buffer.
    void WriteInt32ToBuffer(int value, Buffer buffer);

    // Display the contents of the buffer to the console.
    void DisplayBufferToConsole(Buffer buffer);

    // Application code
    static void Main()
    {
        var buffer = CreateBuffer();
        try
        {
            int value = Int32.Parse(Console.ReadLine());
            WriteInt32ToBuffer(value, buffer);
            DisplayBufferToConsole(buffer);
        }
        finally
        {
            buffer.Destroy();
        }
    }
}
```

Il metodo `Main` crea il buffer (in questo caso un'istanza di <xref:System.Span%601>) e pertanto ne è il proprietario. `Main` è quindi responsabile dell'eliminazione definitiva del buffer quando non è più in uso. Questa operazione viene eseguita chiamando il metodo <xref:System.Span%601.Clear?displayProperty=nameWithType> del buffer. (Il metodo <xref:System.Span%601.Clear> in questo caso cancella effettivamente la memoria del buffer. La struttura <xref:System.Span%601> non ha in effetti un metodo per l'eliminazione definitiva del buffer.)

Il buffer ha due consumer, `WriteInt32ToBuffer` e `DisplayBufferToConsole`. Esiste un solo consumer alla volta (prima `WriteInt32ToBuffer` e poi `DisplayBufferToConsole`), e nessuno dei consumer è proprietario del buffer. Si noti anche che il concetto di "consumer" in questo contesto non implica una visualizzazione di sola lettura del buffer. I consumer possono modificare il contenuto del buffer, come nel caso di `WriteInt32ToBuffer`, se ricevono una vista in lettura/scrittura del buffer.

Il metodo `WriteInt32ToBuffer` ha un lease per il buffer (può utilizzarlo) dall'inizio della chiamata al metodo fino al momento in cui il metodo restituisce il controllo. Analogamente, `DisplayBufferToConsole` ha un lease per il buffer mentre è in esecuzione e il lease viene rilasciato quando viene rimosso il metodo. (Non è disponibile alcuna API per la gestione del lease. Un "lease" è una questione concettuale.)

## <a name="memoryt-and-the-ownerconsumer-model"></a>Memory\<T> e il modello proprietario/consumer

Come indicato nella sezione [Proprietari, consumer e gestione della durata](#owners-consumers-and-lifetime-management), un buffer ha sempre un proprietario. .NET Core supporta due modelli di proprietà:

- Un modello che supporta la proprietà singola. Un buffer ha un solo proprietario per tutta la sua durata.

- Un modello che supporta il trasferimento della proprietà. La proprietà di un buffer può essere trasferita dal relativo proprietario (autore) originale a un altro componente, che quindi diventa responsabile della gestione della durata del buffer. Tale proprietario può a sua volta trasferire la proprietà a un altro componente e così via.

Per gestire in modo esplicito la proprietà di un buffer si usa l'interfaccia <xref:System.Buffers.IMemoryOwner%601?displayProperty=nameWithType>. <xref:System.Buffers.IMemoryOwner%601> supporta entrambi i modelli di proprietà. Il componente con un riferimento a <xref:System.Buffers.IMemoryOwner%601> è proprietario del buffer. L'esempio seguente usa un'istanza di <xref:System.Buffers.IMemoryOwner%601?> per riflettere la proprietà di un buffer <xref:System.Memory%601>.

[!code-csharp[ownership](~/samples/snippets/standard/buffers/memory-t/owner/owner.cs)]

È anche possibile scrivere questo esempio con [`using`](../../csharp/language-reference/keywords/using-statement.md):

[!code-csharp[ownership-using](~/samples/snippets/standard/buffers/memory-t/owner-using/owner-using.cs)]

In questo codice:

- Il metodo `Main` mantiene il riferimento all'istanza di <xref:System.Buffers.IMemoryOwner%601>, quindi il metodo `Main` è il proprietario del buffer.

- I metodi `WriteInt32ToBuffer` e `DisplayBufferToConsole` accettano <xref:System.Memory%601> come API pubblica. Sono pertanto consumer del buffer e lo utilizzano uno alla volta.

Anche se il metodo `WriteInt32ToBuffer` è progettato per scrivere un valore nel buffer, il metodo `DisplayBufferToConsole` non lo è. Di conseguenza, potrebbe avere accettato un argomento di tipo <xref:System.ReadOnlyMemory%601>. Per altre informazioni su <xref:System.ReadOnlyMemory%601>, vedere [regola #2: usare ReadOnlySpan\<t> o ReadOnlyMemory\<t> se il buffer deve essere](#rule-2)di sola lettura.

### <a name="ownerless-memoryt-instances"></a>Istanza di Memory\<T> "senza proprietario"

È possibile creare un'istanza di <xref:System.Memory%601> senza usare <xref:System.Buffers.IMemoryOwner%601>. In questo caso, la proprietà del buffer è implicita anziché esplicita ed è supportato solo il modello con proprietario singolo. A questo scopo:

- Chiamare direttamente uno dei costruttori <xref:System.Memory%601> passando un `T[]`, come nell'esempio seguente.

- Chiamare il metodo di estensione [String.AsMemory](xref:System.MemoryExtensions.AsMemory(System.String)) per produrre un'istanza di `ReadOnlyMemory<char>`.

[!code-csharp[ownerless-memory](~/samples/snippets/standard/buffers/memory-t/ownerless/ownerless.cs)]

Il metodo che crea inizialmente l'istanza di <xref:System.Memory%601> è il proprietario implicito del buffer. Non è possibile trasferire la proprietà a qualsiasi altro componente perché non esiste alcuna istanza di <xref:System.Buffers.IMemoryOwner%601> per facilitare il trasferimento. (In alternativa, è anche possibile immaginare che il Garbage Collector del runtime sia il proprietario del buffer e che i metodi utilizzino semplicemente il buffer.)

## <a name="usage-guidelines"></a>Linee guida per l'utilizzo

Dato che un blocco di memoria ha un proprietario, ma è destinato a essere passato a più componenti, alcuni dei quali potrebbero operare simultaneamente su un blocco di memoria specifico, è importante definire delle linee guida per l'uso sia di <xref:System.Memory%601> che di <xref:System.Span%601>.  Le linee guida sono necessarie per i motivi seguenti:

- Un componente può mantenere un riferimento a un blocco di memoria dopo il rilascio da parte del proprietario.

- È possibile che un componente operi su un buffer in contemporanea con un altro componente, con un processo che danneggia i dati nel buffer.

- Anche se il funzionamento basato sull'allocazione dello stack di <xref:System.Span%601> consente di ottimizzare le prestazioni e rende <xref:System.Span%601> il tipo preferito per operare su un blocco di memoria, <xref:System.Span%601> diventa soggetto ad alcune restrizioni significative. È importante sapere quando usare <xref:System.Span%601> e quando usare <xref:System.Memory%601>.

Di seguito sono riportati alcuni consigli per usare correttamente <xref:System.Memory%601> e i tipi correlati. Si noti che le linee guida valide per <xref:System.Memory%601> e <xref:System.Span%601> si applicano anche a <xref:System.ReadOnlyMemory%601> e <xref:System.ReadOnlySpan%601>, se non diversamente indicato in modo esplicito.

**#1 di regole: per un'API sincrona,\<utilizzare Span t> anziché\<Memory t> come parametro, se possibile.**

<xref:System.Span%601> è più versatile di <xref:System.Memory%601> e può rappresentare una più ampia gamma di buffer di memoria contigui. <xref:System.Span%601> offre anche prestazioni migliori di <xref:System.Memory%601>. Infine, è possibile usare la proprietà <xref:System.Memory%601.Span?displayProperty=nameWithType> per convertire un'istanza di <xref:System.Memory%601> in <xref:System.Span%601>, anche se la conversione da Span\<T> a Memory\<T> non è possibile. Nel caso i chiamanti abbiano un'istanza di <xref:System.Memory%601>, pertanto, potranno chiamare comunque i metodi con i parametri <xref:System.Span%601>.

L'uso di un parametro di tipo <xref:System.Span%601> anziché di tipo <xref:System.Memory%601> consente anche di scrivere un'implementazione corretta del metodo consumer. Si otterranno automaticamente controlli in fase di compilazione per assicurarsi che non si stia tentando di accedere al buffer dopo la scadenza del lease del metodo (più avanti sono disponibili altre informazioni su questo argomento).

Sarà a volte necessario usare un parametro <xref:System.Memory%601> invece di un parametro<xref:System.Span%601>, anche in caso di sincronia completa. È possibile che un'API da cui si dipende accetti solo argomenti <xref:System.Memory%601>. Non è un problema, ma tenere presenti i compromessi che implica l'uso sincrono di <xref:System.Memory%601>.

<a name="rule-2" />

**#2 della regola: usare\<ReadOnlySpan t> o\<ReadOnlyMemory t> se il buffer deve essere di sola lettura.**

Negli esempi precedenti il metodo `DisplayBufferToConsole` legge solo dal buffer e non modifica il contenuto del buffer. La firma del metodo deve essere modificata come segue.

```csharp
void DisplayBufferToConsole(ReadOnlyMemory<char> buffer);
```

In effetti, se si combinano questa regola e la regola 1, è possibile migliorare ancora e riscrivere la firma del metodo come segue:

```csharp
void DisplayBufferToConsole(ReadOnlySpan<char> buffer);
```

Il metodo `DisplayBufferToConsole` ora funziona praticamente con qualsiasi tipo di buffer immaginabile: `T[]`, archiviazione allocata con [stackalloc](../../csharp/language-reference/operators/stackalloc.md) e così via. È anche possibile passare direttamente una <xref:System.String>.

**#3 della regola: se il metodo accetta\<la memoria t> `void`e restituisce, non è necessario usare\<l'istanza Memory t> dopo che il metodo restituisce un risultato.**

Questo aspetto è correlato al concetto di "lease" menzionato in precedenza. Il lease di un metodo che restituisce void per l'istanza di <xref:System.Memory%601> inizia con l'accesso al metodo e termina quando il metodo viene chiuso. Si consideri l'esempio seguente, che chiama `Log` in un ciclo in base all'input dalla console.

[!code-csharp[void-returning](~/samples/snippets/standard/buffers/memory-t/void-returning/void-returning.cs#1)]

Se `Log` è un metodo completamente sincrono, questo codice si comporterà come previsto poiché non esiste un solo consumer attivo dell'istanza di memoria in qualsiasi momento.
Si immagini, invece, che `Log` abbia questa implementazione.

```csharp
// !!! INCORRECT IMPLEMENTATION !!!
static void Log(ReadOnlyMemory<char> message)
{
    // Run in background so that we don't block the main thread while performing IO.
    Task.Run(() =>
    {
        StreamWriter sw = File.AppendText(@".\input-numbers.dat");
        sw.WriteLine(message);
    });
}
```

In questa implementazione `Log` viola il lease perché tenta ancora di usare l'istanza di <xref:System.Memory%601> in background dopo l'uscita dal metodo originale. Il metodo `Main` potrebbe modificare il buffer mentre `Log` tenta una lettura, con potenziale danneggiamento dei dati.

Esistono diversi modi per risolvere questo problema:

- Il metodo `Log` può restituire un <xref:System.Threading.Tasks.Task> invece di `void`, come l'implementazione seguente del metodo `Log`.

   [!code-csharp[task-returning](~/samples/snippets/standard/buffers/memory-t/task-returning2/task-returning2.cs#1)]

- `Log` può invece essere implementato come segue:

   [!code-csharp[defensive-copy](~/samples/snippets/standard/buffers/memory-t/task-returning/task-returning.cs#1)]

**#4 della regola: se il metodo accetta una\<memoria t> e restituisce un'attività, non è necessario usare l'\<istanza Memory t> dopo che l'attività passa allo stato terminale.**

Si tratta semplicemente della variante asincrona della regola 3. Il metodo `Log` dall'esempio precedente può essere scritto come segue per la conformità a questa regola:

[!code-csharp[task-returning-async](~/samples/snippets/standard/buffers/memory-t/void-returning-async/void-returning-async.cs#1)]

In questo caso, "stato terminale" significa che l'attività passa a uno stato completato, di errore o annullato. In altre parole, "stato terminale" significa "tutto ciò che potrebbe causare la generazione di await o la continuazione dell'esecuzione".

Queste linee guida si applicano ai metodi che restituiscono <xref:System.Threading.Tasks.Task>, <xref:System.Threading.Tasks.Task%601>, <xref:System.Threading.Tasks.ValueTask%601> o qualsiasi tipo simile.

**#5 della regola: se il costruttore accetta\<la memoria t> come parametro, si presuppone che i metodi di istanza nell'oggetto costruito siano utenti dell'\<istanza di memoria t>.**

Prendere in considerazione gli esempi seguenti:

```csharp
class OddValueExtractor
{
    public OddValueExtractor(ReadOnlyMemory<int> input);
    public bool TryReadNextOddValue(out int value);
}

void PrintAllOddValues(ReadOnlyMemory<int> input)
{
    var extractor = new OddValueExtractor(input);
    while (extractor.TryReadNextOddValue(out int value))
    {
      Console.WriteLine(value);
    }
}
```

In questo caso, il costruttore `OddValueExtractor` accetta un `ReadOnlyMemory<int>` come parametro costruttore, pertanto il costruttore stesso è un consumer dell'istanza di `ReadOnlyMemory<int>` e tutti i metodi di istanza per il valore restituito sono anche consumer dell'istanza di `ReadOnlyMemory<int>` originale. Questo significa che `TryReadNextOddValue` utilizza l'istanza di `ReadOnlyMemory<int>`, anche se non viene passata direttamente al metodo `TryReadNextOddValue`.

**#6 della regola: se nel tipo è presente\<una proprietà della memoria impostabile t>-tipizzata (o un metodo di istanza equivalente), si presuppone che i metodi di istanza su tale\<oggetto siano consumer della memoria t> istanza.**

Si tratta semplicemente di una variante della regola 5. Questa regola esiste perché si presuppone che i setter delle proprietà o i metodi equivalenti acquisiscano gli input e li salvino in modo permanente, in modo che i metodi di istanza per lo stesso oggetto possano utilizzare lo stato acquisito.

L'esempio seguente attiva questa regola:

```csharp
class Person
{
    // Settable property.
    public Memory<char> FirstName { get; set; }

    // alternatively, equivalent "setter" method
    public SetFirstName(Memory<char> value);

    // alternatively, a public settable field
    public Memory<char> FirstName;
}
```

**#7 di regole: se si dispone di\<un riferimento a IMemoryOwner T>, è necessario a un certo punto eliminarlo o trasferirne la proprietà (ma non entrambi).**

Dato che un'istanza di <xref:System.Memory%601> potrebbe essere supportata da memoria gestita o non gestita, il proprietario deve chiamare <xref:System.Buffers.MemoryPool%601.Dispose%2A?displayProperty=nameWithType> al termine delle operazioni eseguite sull'istanza di <xref:System.Memory%601>. In alternativa, il proprietario potrebbe trasferire la proprietà dell'istanza di <xref:System.Buffers.IMemoryOwner%601> a un altro componente e a quel punto il componente di destinazione diventa responsabile di chiamare <xref:System.Buffers.MemoryPool%601.Dispose%2A?displayProperty=nameWithType> al momento appropriato (più avanti sono disponibili altre informazioni su questo argomento).

Se non viene chiamato il metodo <xref:System.Buffers.MemoryPool%601.Dispose%2A>, potrebbero verificarsi perdite della memoria non gestita o altre forme di riduzione del livello delle prestazioni.

Questa regola si applica anche al codice che chiama i metodi factory, ad esempio <xref:System.Buffers.MemoryPool%601.Rent%2A?displayProperty=nameWithType>. Il chiamante diventa il proprietario dell'oggetto restituito <xref:System.Buffers.IMemoryOwner%601> ed è responsabile dell'eliminazione dell'istanza al termine.

**#8 di regole: se si dispone di\<un parametro IMemoryOwner T> nella superficie dell'API, si accetta la proprietà di tale istanza.**

L'accettazione di un'istanza di questo tipo segnala che il componente intende acquisire la proprietà di questa istanza. Il componente diventa responsabile della corretta eliminazione in base alla regola 7.

Qualsiasi componente che trasferisce la proprietà dell'istanza di <xref:System.Buffers.IMemoryOwner%601> a un altro componente non deve più usare tale istanza dopo il completamento della chiamata al metodo.

> [!IMPORTANT]
> Se il costruttore accetta <xref:System.Buffers.IMemoryOwner%601> come parametro, il tipo deve implementare <xref:System.IDisposable> e il metodo <xref:System.IDisposable.Dispose%2A> deve chiamare <xref:System.Buffers.MemoryPool%601.Dispose%2A?displayProperty=nameWithType>.

**#9 di regole: se si esegue il wrapping di un metodo p/Invoke sincrono, l'\<API deve accettare Span T> come parametro.**

In base alla regola 1, <xref:System.Span%601> è in genere il tipo corretto da usare per le API sincrone. È possibile aggiungere <xref:System.Span%601> istanze tramite la [`fixed`](../../csharp/language-reference/keywords/fixed-statement.md) parola chiave, come nell'esempio seguente.

```csharp
using System.Runtime.InteropServices;

[DllImport(...)]
private static extern unsafe int ExportedMethod(byte* pbData, int cbData);

public unsafe int ManagedWrapper(Span<byte> data)
{
    fixed (byte* pbData = &MemoryMarshal.GetReference(data))
    {
        int retVal = ExportedMethod(pbData, data.Length);

        /* error checking retVal goes here */

        return retVal;
    }
}
```

Nell'esempio precedente, `pbData` può essere Null se, ad esempio, l'intervallo di input è vuoto. Se il metodo esportato richiede assolutamente che `pbData` non sia Null, anche se `cbData` è 0, il metodo può essere implementato come segue:

```csharp
public unsafe int ManagedWrapper(Span<byte> data)
{
    fixed (byte* pbData = &MemoryMarshal.GetReference(data))
    {
        byte dummy = 0;
        int retVal = ExportedMethod((pbData != null) ? pbData : &dummy, data.Length);

        /* error checking retVal goes here */

        return retVal;
    }
}
```

**#10 di regole: se si esegue il wrapping di un metodo p/invoke asincrono, l'API\<deve accettare la memoria T> come parametro.**

Poiché non è possibile utilizzare [`fixed`](../../csharp/language-reference/keywords/fixed-statement.md) la parola chiave tra le operazioni asincrone, <xref:System.Memory%601.Pin%2A?displayProperty=nameWithType> è possibile utilizzare <xref:System.Memory%601> il metodo per aggiungere istanze, indipendentemente dal tipo di memoria contigua rappresentata dall'istanza. Nell'esempio seguente viene illustrato come usare questa API per eseguire una chiamata P/Invoke asincrona.

```csharp
using System.Runtime.InteropServices;

[UnmanagedFunctionPointer(...)]
private delegate void OnCompletedCallback(IntPtr state, int result);

[DllImport(...)]
private static extern unsafe int ExportedAsyncMethod(byte* pbData, int cbData, IntPtr pState, IntPtr lpfnOnCompletedCallback);

private static readonly IntPtr _callbackPtr = GetCompletionCallbackPointer();

public unsafe Task<int> ManagedWrapperAsync(Memory<byte> data)
{
    // setup
    var tcs = new TaskCompletionSource<int>();
    var state = new MyCompletedCallbackState
    {
        Tcs = tcs
    };
    var pState = (IntPtr)GCHandle.Alloc(state);

    var memoryHandle = data.Pin();
    state.MemoryHandle = memoryHandle;

    // make the call
    int result;
    try
    {
        result = ExportedAsyncMethod((byte*)memoryHandle.Pointer, data.Length, pState, _callbackPtr);
    }
    catch
    {
        ((GCHandle)pState).Free(); // cleanup since callback won't be invoked
        memoryHandle.Dispose();
        throw;
    }

    if (result != PENDING)
    {
        // Operation completed synchronously; invoke callback manually
        // for result processing and cleanup.
        MyCompletedCallbackImplementation(pState, result);
    }

    return tcs.Task;
}

private static void MyCompletedCallbackImplementation(IntPtr state, int result)
{
    GCHandle handle = (GCHandle)state;
    var actualState = (MyCompletedCallbackState)(handle.Target);
    handle.Free();
    actualState.MemoryHandle.Dispose();

    /* error checking result goes here */

    if (error)
    {
        actualState.Tcs.SetException(...);
    }
    else
    {
        actualState.Tcs.SetResult(result);
    }
}

private static IntPtr GetCompletionCallbackPointer()
{
    OnCompletedCallback callback = MyCompletedCallbackImplementation;
    GCHandle.Alloc(callback); // keep alive for lifetime of application
    return Marshal.GetFunctionPointerForDelegate(callback);
}

private class MyCompletedCallbackState
{
    public TaskCompletionSource<int> Tcs;
    public MemoryHandle MemoryHandle;
}
```

## <a name="see-also"></a>Vedere anche

- <xref:System.Memory%601?displayProperty=nameWithType>
- <xref:System.Buffers.IMemoryOwner%601?displayProperty=nameWithType>
- <xref:System.Span%601?displayProperty=nameWithType>
