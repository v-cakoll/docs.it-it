---
title: Inizializzazione differita
description: Esplora l'inizializzazione lazy in .NET, un miglioramento delle prestazioni che indica che la creazione di un oggetto viene posticipata finché l'oggetto non viene usato per la prima volta.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- lazy initialization in .NET, introduction
ms.assetid: 56b4ae5c-4745-44ff-ad78-ffe4fcde6b9b
ms.openlocfilehash: 355fa326fc19e9a50a74e21ace0a6353f5c740c5
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/17/2020
ms.locfileid: "84904234"
---
# <a name="lazy-initialization"></a>Inizializzazione differita
L'*inizializzazione differita* di un oggetto significa che la creazione dell'oggetto viene posticipata finché l'oggetto non viene usato per la prima volta. Per questo argomento, i termini *inizializzazione Lazy* e *creazione di istanze Lazy* sono sinonimi. L'inizializzazione differita viene utilizzata principalmente per migliorare le prestazioni, evitare inutili calcoli e ridurre i requisiti di memoria del programma. Ecco gli scenari più comuni:  
  
- La creazione di un oggetto è dispendiosa e il programma potrebbe non usarlo. Si supponga, ad esempio, di avere un oggetto `Customer` in memoria che include una proprietà `Orders` contenente una matrice di grandi dimensioni di oggetti `Order`, per la cui inizializzazione è necessaria una connessione di database. Se l'utente non chiede mai di visualizzare gli ordini o di usare i dati in un calcolo, non vi è motivo di usare la memoria di sistema o cicli di calcolo per creare l'oggetto. Usando `Lazy<Orders>` per dichiarare l'oggetto `Orders` per l'inizializzazione differita, è possibile evitare di sprecare risorse di sistema quando l'oggetto non viene usato.  
  
- La creazione di un oggetto è dispendiosa e si vuole posticiparla fino al completamento di altre operazioni dispendiose. Si supponga, ad esempio, che il programma carichi diverse istanze dell'oggetto all'avvio, ma che solo alcune siano necessarie immediatamente. È possibile migliorare le prestazioni di avvio del programma posticipando l'inizializzazione degli oggetti non necessari finché non vengono creati quelli necessari.  
  
 Benché sia possibile scrivere codice personalizzato per eseguire l'inizializzazione differita, è consigliabile usare <xref:System.Lazy%601>. <xref:System.Lazy%601> e i tipi correlati supportano anche la thread safety e forniscono criteri uniformi di propagazione delle eccezioni.  
  
 La tabella seguente elenca i tipi forniti da .NET Framework versione 4 per consentire l'inizializzazione differita in diversi scenari.  
  
|Type|Descrizione|  
|----------|-----------------|  
|<xref:System.Lazy%601>|Classe wrapper che fornisce la semantica di inizializzazione differita per qualsiasi libreria di classi o tipo definito dall'utente.|  
|<xref:System.Threading.ThreadLocal%601>|È simile a <xref:System.Lazy%601>, con la differenza che fornisce la semantica di inizializzazione differita in base a dati locali del thread. Ogni thread ha accesso al proprio valore univoco.|  
|<xref:System.Threading.LazyInitializer>|Fornisce metodi `static` (`Shared` in Visual Basic) avanzati per l'inizializzazione differita di oggetti senza l'overhead di una classe.|  
  
## <a name="basic-lazy-initialization"></a>Inizializzazione differita di base  
 Per definire un tipo a inizializzazione differita, ad esempio `MyType`, usare `Lazy<MyType>` (`Lazy(Of MyType)` in Visual Basic), come mostrato nell'esempio seguente. Se non viene passato alcun delegato nel costruttore <xref:System.Lazy%601>, il tipo con wrapping viene creato usando <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType> in occasione del primo accesso alla proprietà del valore. Se il tipo non dispone di un costruttore senza parametri, viene generata un'eccezione in fase di esecuzione.  
  
 Nell'esempio seguente si supponga che `Orders` sia una classe che contiene una matrice di oggetti `Order` recuperati da un database. Un oggetto `Customer` contiene un'istanza di `Orders`, ma a seconda delle azioni dell'utente, i dati dell'oggetto `Orders` potrebbero non essere necessari.  
  
 [!code-csharp[Lazy#1](../../../samples/snippets/csharp/VS_Snippets_Misc/lazy/cs/cs_lazycodefile.cs#1)]
 [!code-vb[Lazy#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/lazy/vb/lazy_vb.vb#1)]  
  
 È anche possibile passare un delegato nel costruttore <xref:System.Lazy%601>, che richiama un overload del costruttore specifico nel tipo con wrapping in fase di creazione, ed eseguire tutti gli altri passaggi di inizializzazione necessari, come mostrato nell'esempio seguente.  
  
 [!code-csharp[Lazy#2](../../../samples/snippets/csharp/VS_Snippets_Misc/lazy/cs/cs_lazycodefile.cs#2)]
 [!code-vb[Lazy#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/lazy/vb/lazy_vb.vb#2)]  
  
 Una volta creato l'oggetto Lazy, non viene creata alcuna istanza di `Orders` fino al momento del primo accesso alla proprietà <xref:System.Lazy%601.Value%2A> della variabile Lazy. Al primo accesso, il tipo con wrapping viene creato e restituito e quindi archiviato per tutti gli accessi futuri.  
  
 [!code-csharp[Lazy#3](../../../samples/snippets/csharp/VS_Snippets_Misc/lazy/cs/cs_lazycodefile.cs#3)]
 [!code-vb[Lazy#3](../../../samples/snippets/visualbasic/VS_Snippets_Misc/lazy/vb/lazy_vb.vb#3)]  
  
 Un oggetto <xref:System.Lazy%601> restituisce sempre lo stesso oggetto o valore con cui è stato inizializzato. Di conseguenza, la proprietà <xref:System.Lazy%601.Value%2A> è di sola lettura. Se in <xref:System.Lazy%601.Value%2A> è archiviato un tipo riferimento, non è possibile assegnarvi un nuovo oggetto. È tuttavia possibile modificare il valore delle proprietà e dei campi pubblici impostabili. Se <xref:System.Lazy%601.Value%2A> Archivia un tipo di valore, non è possibile modificarne il valore. È tuttavia possibile creare una nuova variabile richiamando di nuovo il costruttore della variabile con nuovi argomenti.  
  
 [!code-csharp[Lazy#4](../../../samples/snippets/csharp/VS_Snippets_Misc/lazy/cs/cs_lazycodefile.cs#4)]
 [!code-vb[Lazy#4](../../../samples/snippets/visualbasic/VS_Snippets_Misc/lazy/vb/lazy_vb.vb#4)]  
  
 La nuova istanza Lazy, come la precedente, non crea un'istanza di `Orders` fino al momento del primo accesso alla proprietà <xref:System.Lazy%601.Value%2A> correlata.  
  
### <a name="thread-safe-initialization"></a>Inizializzazione thread-safe  
 Per impostazione predefinita, gli oggetti <xref:System.Lazy%601> sono thread-safe. Di conseguenza, se il costruttore non specifica il tipo di thread safety, gli oggetti <xref:System.Lazy%601> creati sono thread-safe. Negli scenari di multithreading il primo thread che accede alla proprietà <xref:System.Lazy%601.Value%2A> di un oggetto <xref:System.Lazy%601> thread-safe lo inizializza per tutti gli accessi successivi in tutti i thread e tutti i thread condividono gli stessi dati. Di conseguenza, non importa quale thread inizializza l'oggetto e le race condition sono valide.  
  
> [!NOTE]
> È possibile estendere questa coerenza alle condizioni di errore usando la memorizzazione nella cache delle eccezioni. Per altre informazioni, vedere la sezione [Eccezioni negli oggetti Lazy](lazy-initialization.md#ExceptionsInLazyObjects) di seguito.  
  
 L'esempio seguente mostra che la stessa istanza `Lazy<int>` ha lo stesso valore per tre thread separati.  
  
 [!code-csharp[Lazy#8](../../../samples/snippets/csharp/VS_Snippets_Misc/lazy/cs/cs_lazycodefile.cs#8)]
 [!code-vb[Lazy#8](../../../samples/snippets/visualbasic/VS_Snippets_Misc/lazy/vb/lazy_vb.vb#8)]  
  
 Se sono necessari dati separati in ogni thread, usare il tipo <xref:System.Threading.ThreadLocal%601>, descritto più avanti in questo argomento.  
  
 Alcuni costruttori <xref:System.Lazy%601> includono un parametro booleano chiamato `isThreadSafe`, che viene usato per specificare se si intende accedere alla proprietà <xref:System.Lazy%601.Value%2A> da più thread. Se si intende accedere alla proprietà da un solo thread, passare `false` per ottenere un vantaggio moderato in termini di prestazioni. Se si intende accedere alla proprietà da più thread, passare `true` per indicare all'istanza <xref:System.Lazy%601> di gestire correttamente le race condition in cui un thread genera un'eccezione in fase di inizializzazione.  
  
 Alcuni costruttori <xref:System.Lazy%601> includono un parametro <xref:System.Threading.LazyThreadSafetyMode> chiamato `mode`. Questi costruttori forniscono una modalità di thread safety aggiuntiva. La tabella seguente mostra in che modo i parametri del costruttore che specificano la thread safety influiscono sulla thread safety di un oggetto <xref:System.Lazy%601>. Ogni costruttore include al massimo uno di questi parametri.  
  
|Thread safety dell'oggetto|`LazyThreadSafetyMode``mode`parametro di|Parametro `isThreadSafe` booleano|Nessun parametro di thread safety|  
|---------------------------------|---------------------------------------------|--------------------------------------|---------------------------------|  
|Completamente thread-safe. Un solo thread per volta tenta di inizializzare il valore.|<xref:System.Threading.LazyThreadSafetyMode.ExecutionAndPublication>|`true`|Sì.|  
|Non thread-safe.|<xref:System.Threading.LazyThreadSafetyMode.None>|`false`|Non applicabile.|  
|Completamente thread-safe. I thread competono per inizializzare il valore.|<xref:System.Threading.LazyThreadSafetyMode.PublicationOnly>|Non applicabile.|Non applicabile.|  
  
 Come mostrato nella tabella, l'immissione di <xref:System.Threading.LazyThreadSafetyMode.ExecutionAndPublication?displayProperty=nameWithType> per il parametro `mode` equivale all'immissione di `true` per il parametro `isThreadSafe`, mentre l'immissione di <xref:System.Threading.LazyThreadSafetyMode.None?displayProperty=nameWithType> equivale all'immissione di `false`.  
  
 Se si specifica <xref:System.Threading.LazyThreadSafetyMode.PublicationOnly?displayProperty=nameWithType>, si consente a più thread di tentare di inizializzare l'istanza <xref:System.Lazy%601>. Solo un thread può riuscire, mentre tutti gli altri thread ricevono il valore inizializzato da quello che ha avuto esito positivo. Se durante l'inizializzazione viene generata un'eccezione in un thread, questo thread non riceve il valore impostato dal thread che è riuscito a eseguire l'inizializzazione. Poiché le eccezioni non sono memorizzate nella cache, un tentativo successivo di accesso alla proprietà <xref:System.Lazy%601.Value%2A> può restituire un'inizializzazione riuscita. Questo comportamento è diverso dal modo in cui vengono gestite le eccezioni in altre modalità, descritto nella sezione seguente. Per altre informazioni, vedere l'enumerazione <xref:System.Threading.LazyThreadSafetyMode>.  
  
<a name="ExceptionsInLazyObjects"></a>
## <a name="exceptions-in-lazy-objects"></a>Eccezioni negli oggetti Lazy  
 Come già indicato, un oggetto <xref:System.Lazy%601> restituisce sempre lo stesso oggetto o valore con cui è stato inizializzato e di conseguenza la proprietà <xref:System.Lazy%601.Value%2A> è di sola lettura. Se si abilita la memorizzazione nella cache delle eccezioni, questa natura non modificabile si estende al comportamento delle eccezioni. Se per un oggetto con inizializzazione lazy è abilitata la memorizzazione nella cache delle eccezioni e viene generata un'eccezione dal relativo metodo di inizializzazione quando <xref:System.Lazy%601.Value%2A> si accede prima alla proprietà, viene generata la stessa eccezione a ogni tentativo successivo di accesso alla <xref:System.Lazy%601.Value%2A> Proprietà. In altre parole, il costruttore del tipo con wrapping non viene mai richiamato, anche in scenari di multithreading. Di conseguenza, l'oggetto <xref:System.Lazy%601> non può generare un'eccezione durante un accesso e restituire un valore all'accesso successivo.  
  
 La memorizzazione nella cache delle eccezioni viene abilitata quando si usa qualsiasi costruttore <xref:System.Lazy%601?displayProperty=nameWithType> che accetta un metodo di inizializzazione (parametro `valueFactory`). Ad esempio, viene abilitata quando si usa il costruttore `Lazy(T)(Func(T))`. Se il costruttore accetta anche un valore <xref:System.Threading.LazyThreadSafetyMode> (parametro `mode`), specificare <xref:System.Threading.LazyThreadSafetyMode.ExecutionAndPublication?displayProperty=nameWithType> o <xref:System.Threading.LazyThreadSafetyMode.None?displayProperty=nameWithType>. Se si specifica un metodo di inizializzazione, la memorizzazione nella cache delle eccezioni viene abilitata per queste due modalità. Il metodo di inizializzazione può essere molto semplice. Ad esempio, potrebbe chiamare il costruttore senza parametri per `T` : `new Lazy<Contents>(() => new Contents(), mode)` in C# o `New Lazy(Of Contents)(Function() New Contents())` in Visual Basic. Se si usa un costruttore <xref:System.Lazy%601?displayProperty=nameWithType> che non specifica un metodo di inizializzazione, le eccezioni generate dal costruttore senza parametri per `T` non vengono memorizzate nella cache. Per altre informazioni, vedere l'enumerazione <xref:System.Threading.LazyThreadSafetyMode>.  
  
> [!NOTE]
> Se si crea un oggetto <xref:System.Lazy%601> con il parametro del costruttore `isThreadSafe` impostato su `false` o il parametro del costruttore `mode` impostato su <xref:System.Threading.LazyThreadSafetyMode.None?displayProperty=nameWithType>, è necessario accedere all'oggetto <xref:System.Lazy%601> da un solo thread o fornire la sincronizzazione. Questo vale per tutti gli aspetti dell'oggetto, anche per la memorizzazione nella cache delle eccezioni.  
  
 Come indicato nella sezione precedente, gli oggetti <xref:System.Lazy%601> creati specificando <xref:System.Threading.LazyThreadSafetyMode.PublicationOnly?displayProperty=nameWithType> gestiscono le eccezioni in modo diverso. Con <xref:System.Threading.LazyThreadSafetyMode.PublicationOnly>, più thread possono competere per inizializzare l'istanza <xref:System.Lazy%601>. In questo caso, le eccezioni non vengono memorizzate nella cache e i tentativi di accesso alla proprietà <xref:System.Lazy%601.Value%2A> possono continuare finché l'inizializzazione non riesce.  
  
 La tabella seguente offre un riepilogo del modo in cui i costruttori <xref:System.Lazy%601> controllano la memorizzazione nella cache delle eccezioni.  
  
|Costruttore|Modalità di thread safety|Usa il metodo di inizializzazione|Le eccezioni vengono memorizzate nella cache|  
|-----------------|------------------------|--------------------------------|---------------------------|  
|Lazy(T)()|(<xref:System.Threading.LazyThreadSafetyMode.ExecutionAndPublication>)|No|No|  
|Lazy(T)(Func(T))|(<xref:System.Threading.LazyThreadSafetyMode.ExecutionAndPublication>)|Sì|Sì|  
|Lazy(T)(Boolean)|`True` (<xref:System.Threading.LazyThreadSafetyMode.ExecutionAndPublication>) o `false` (<xref:System.Threading.LazyThreadSafetyMode.None>)|No|No|  
|Lazy(T)(Func(T), Boolean)|`True` (<xref:System.Threading.LazyThreadSafetyMode.ExecutionAndPublication>) o `false` (<xref:System.Threading.LazyThreadSafetyMode.None>)|Sì|Sì|  
|Lazy(T)(LazyThreadSafetyMode)|Specificata dall'utente|No|No|  
|Lazy(T)(Func(T), LazyThreadSafetyMode)|Specificata dall'utente|Sì|No se l'utente specifica <xref:System.Threading.LazyThreadSafetyMode.PublicationOnly>; in caso contrario, sì.|  
  
## <a name="implementing-a-lazy-initialized-property"></a>Implementazione di una proprietà a inizializzazione differita  
 Per implementare una proprietà pubblica usando l'inizializzazione differita, definire il campo sottostante della proprietà come <xref:System.Lazy%601> e restituire la proprietà <xref:System.Lazy%601.Value%2A> dalla funzione di accesso `get` della proprietà.  
  
 [!code-csharp[Lazy#5](../../../samples/snippets/csharp/VS_Snippets_Misc/lazy/cs/cs_lazycodefile.cs#5)]
 [!code-vb[Lazy#5](../../../samples/snippets/visualbasic/VS_Snippets_Misc/lazy/vb/lazy_vb.vb#5)]  
  
 Poiché la proprietà <xref:System.Lazy%601.Value%2A> è di sola lettura, la proprietà che la espone non ha funzioni di accesso `set`. Se è necessaria una proprietà di lettura/scrittura con un oggetto <xref:System.Lazy%601> sottostante, la funzione di accesso `set` deve creare un nuovo oggetto <xref:System.Lazy%601> e assegnarlo all'archivio sottostante. La funzione di accesso `set` deve creare un'espressione lambda che restituisca il nuovo valore di proprietà passato alla funzione di accesso `set` e passare l'espressione lambda al costruttore per il nuovo oggetto <xref:System.Lazy%601>. L'accesso successivo della proprietà <xref:System.Lazy%601.Value%2A> provoca l'inizializzazione del nuovo oggetto <xref:System.Lazy%601> e da questo momento in poi la proprietà <xref:System.Lazy%601.Value%2A> correlata restituirà il nuovo valore assegnato alla proprietà. Il motivo di questo comportamento complesso è preservare le protezioni multithreading integrate in <xref:System.Lazy%601>. In caso contrario, le funzioni di accesso della proprietà dovrebbero memorizzare nella cache il primo valore restituito dalla proprietà <xref:System.Lazy%601.Value%2A> e modificare solo il valore memorizzato nella cache e sarebbe necessario scrivere codice thread-safe personalizzato a questo scopo. A causa delle inizializzazioni aggiuntive necessarie per una proprietà di lettura/scrittura con un oggetto <xref:System.Lazy%601> sottostante, le prestazioni potrebbero non essere accettabili. Inoltre, a seconda dello scenario specifico, potrebbe essere necessario un ulteriore coordinamento per evitare race condition tra setter e getter.  
  
## <a name="thread-local-lazy-initialization"></a>Inizializzazione differita con dati locali del thread  
 In alcuni scenari di multithreading potrebbe essere necessario fornire a ogni thread dati privati propri. Questi dati vengono chiamati *dati locali del thread*. In .NET Framework 3.5 e versioni precedenti è possibile applicare l'attributo `ThreadStatic` a una variabile statica per renderla una variabile di thread locale. Tuttavia, l'uso dell'attributo `ThreadStatic` può provocare errori difficili da rilevare. Ad esempio, anche istruzioni di inizializzazione di base possono far sì che la variabile venga inizializzata solo nel primo thread che vi accede, come mostrato nell'esempio seguente.  
  
 [!code-csharp[Lazy#6](../../../samples/snippets/csharp/VS_Snippets_Misc/lazy/cs/cs_lazycodefile.cs#6)]
 [!code-vb[Lazy#6](../../../samples/snippets/visualbasic/VS_Snippets_Misc/lazy/vb/lazy_vb.vb#6)]  
  
 In tutti gli altri thread la variabile verrà inizializzata usando il valore predefinito (zero). Come alternativa, in .NET Framework 4 è possibile usare il tipo <xref:System.Threading.ThreadLocal%601?displayProperty=nameWithType> per creare una variabile di thread locale basata su istanza che deve essere inizializzata in tutti i thread dal delegato <xref:System.Action%601> specificato personalmente. Nell'esempio seguente tutti i thread che accedono a `counter` visualizzeranno il valore iniziale come 1.  
  
 [!code-csharp[Lazy#7](../../../samples/snippets/csharp/VS_Snippets_Misc/lazy/cs/cs_lazycodefile.cs#7)]
 [!code-vb[Lazy#7](../../../samples/snippets/visualbasic/VS_Snippets_Misc/lazy/vb/lazy_vb.vb#7)]  
  
 <xref:System.Threading.ThreadLocal%601> esegue il wrapping del proprio oggetto quasi allo stesso modo di <xref:System.Lazy%601>, con queste importanti differenze:  
  
- Ogni thread inizializza la variabile di thread locale usando i propri dati privati, che non sono accessibili da altri thread.  
  
- La proprietà <xref:System.Threading.ThreadLocal%601.Value%2A?displayProperty=nameWithType> è di lettura/scrittura e può essere modificata tutte le volte che è necessario. Questo può influire sulla propagazione delle eccezioni. Ad esempio, un'operazione `get` può generare un'eccezione, ma la successiva può inizializzare correttamente il valore.  
  
- Se non si specifica alcun delegato di inizializzazione, <xref:System.Threading.ThreadLocal%601> inizializza il tipo con wrapping usando il valore predefinito del tipo. In questo senso, <xref:System.Threading.ThreadLocal%601> è coerente con l'attributo <xref:System.ThreadStaticAttribute>.  
  
 L'esempio seguente mostra che ogni thread che accede all'istanza `ThreadLocal<int>` ottiene una copia univoca dei dati.  
  
 [!code-csharp[Lazy#9](../../../samples/snippets/csharp/VS_Snippets_Misc/lazy/cs/cs_lazycodefile.cs#9)]
 [!code-vb[Lazy#9](../../../samples/snippets/visualbasic/VS_Snippets_Misc/lazy/vb/lazy_vb.vb#9)]  
  
## <a name="thread-local-variables-in-parallelfor-and-foreach"></a>Variabili di thread locali in Parallel.For e ForEach  
 Quando si usa il metodo <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> o <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> per eseguire l'iterazione delle origini dati in parallelo, è possibile usare gli overload che includono supporto integrato per dati locali del thread. In questi metodi la natura locale dei dati del thread viene ottenuta usando delegati locali per accedere ai dati, crearli e pulirli. Per altre informazioni, vedere [Procedura: Scrivere un ciclo Parallel.For con variabili di thread locali](../../standard/parallel-programming/how-to-write-a-parallel-for-loop-with-thread-local-variables.md) e [Procedura: Scrivere un ciclo Parallel.ForEach con variabili partition-local](../../standard/parallel-programming/how-to-write-a-parallel-foreach-loop-with-partition-local-variables.md).  
  
## <a name="using-lazy-initialization-for-low-overhead-scenarios"></a>Uso dell'inizializzazione differita per scenari con sovraccarico ridotto  
 Negli scenari in cui è necessario inizializzare in modo differito un numero elevato di oggetti, si potrebbe stabilire che il wrapping di ogni oggetto in un oggetto <xref:System.Lazy%601> richiede una quantità eccessiva di memoria o di risorse di calcolo. In un altro caso, potrebbe essere necessario soddisfare requisiti rigorosi relativamente all'esposizione dell'inizializzazione differita. In questi casi, è possibile usare i metodi `static` (`Shared` in Visual Basic) della classe <xref:System.Threading.LazyInitializer?displayProperty=nameWithType> per inizializzare in modo differito ogni oggetto senza eseguirne il wrapping in un'istanza di <xref:System.Lazy%601>.  
  
 Invece di eseguire il wrapping di un intero oggetto `Orders` in un oggetto <xref:System.Lazy%601>, nell'esempio seguente si supponga di aver inizializzato in modo differito singoli oggetti `Order` solo quando sono necessari.  
  
 [!code-csharp[Lazy#10](../../../samples/snippets/csharp/VS_Snippets_Misc/lazy/cs/cs_lazycodefile.cs#10)]
 [!code-vb[Lazy#10](../../../samples/snippets/visualbasic/VS_Snippets_Misc/lazy/vb/lazy_vb.vb#10)]  
  
 In questo esempio notare che la procedura di inizializzazione viene richiamata a ogni iterazione del ciclo. In scenari di multithreading, il primo thread che richiama la procedura di inizializzazione è quello i cui valori vengono visualizzati da tutti i thread. Anche i thread successivi richiamano la procedura di inizializzazione, ma i loro risultati non vengono usati. Se questo tipo di possibile race condition non è accettabile, usare l'overload di <xref:System.Threading.LazyInitializer.EnsureInitialized%2A?displayProperty=nameWithType>, che accetta un argomento booleano e un oggetto di sincronizzazione.  
  
## <a name="see-also"></a>Vedere anche

- [Nozioni fondamentali sul threading gestito](../../standard/threading/managed-threading-basics.md)
- [Thread e Threading](../../standard/threading/threads-and-threading.md)
- [Task Parallel Library (TPL)](../../standard/parallel-programming/task-parallel-library-tpl.md)
- [Procedura: eseguire l'inizializzazione lenta di oggetti](how-to-perform-lazy-initialization-of-objects.md)
