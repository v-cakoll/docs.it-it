---
title: Scrivere codice C# sicuro ed efficiente
description: I recenti miglioramenti apportati al linguaggio C# consentono di scrivere codice sicuro verificabile, con prestazioni superiori a quelle in precedenza associate al codice non gestito.
ms.date: 10/23/2018
ms.technology: csharp-advanced-concepts
ms.custom: mvc
ms.openlocfilehash: bb53264f61192c042da469ba687da6c472e8c6d4
ms.sourcegitcommit: 2514f4e3655081dcfe1b22470c0c28500f952c42
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/18/2020
ms.locfileid: "79506983"
---
# <a name="write-safe-and-efficient-c-code"></a>Scrivere codice C# sicuro ed efficiente

Le nuove funzionalità di C# consentono di scrivere codice sicuro verificabile con prestazioni migliori. Se si applicano queste tecniche attentamente, un numero inferiore di scenari richiede codice non gestito. Queste funzionalità semplificano l'uso dei riferimenti ai tipi valore come argomenti di metodo e valori restituiti di metodi. Se eseguite in modo sicuro, queste tecniche riducono al minimo la copia dei tipi valore. Usando i tipi valore, è possibile ridurre al minimo il numero di allocazioni e di passaggi di Garbage Collection.

Gran parte del codice di esempio in questo articolo usa le funzionalità aggiunte in C# 7.2. Per usare tali funzionalità, è necessario configurare il progetto per l'uso di C# 7.2 o versione successiva. Per ulteriori informazioni sull'impostazione della versione della lingua, vedere [configurare la versione della lingua](language-reference/configure-language-version.md).

Questo articolo è incentrato sulle tecniche per la gestione efficiente delle risorse. Un vantaggio dell'uso dei tipi valore è che spesso evitano le allocazioni di heap. Lo svantaggio è invece che vengono copiati in base al valore. Risulta quindi più difficile ottimizzare gli algoritmi che operano su grandi quantità di dati. Le nuove funzionalità del linguaggio C# 7.2 forniscono meccanismi che abilitano il codice sicuro efficiente tramite i riferimenti ai tipi valore. Usare queste funzionalità con criterio, per ridurre al minimo sia le allocazioni che le operazioni di copia. Questo articolo esamina le nuove funzionalità.

Questo articolo è incentrato sulle tecniche per la gestione delle risorse seguenti:

- Dichiarare [`readonly struct`](language-reference/keywords/readonly.md#readonly-struct-example) un per esprimere che un tipo non è **modificabile** e [`in`](language-reference/keywords/in-parameter-modifier.md) consente al compilatore di salvare le copie quando si utilizzano parametri.
- Se un tipo non può essere immutabile, dichiarare `struct` i membri `readonly` per indicare che il membro non modifica lo stato.
- Utilizzare [`ref readonly`](language-reference/keywords/ref.md#reference-return-values) un valore restituito quando `struct` il <xref:System.IntPtr.Size?displayProperty=nameWithType> valore restituito è maggiore di e la durata di archiviazione è maggiore del metodo che restituisce il valore.
- Quando le dimensioni di `readonly struct` sono maggiori di <xref:System.IntPtr.Size?displayProperty=nameWithType>, è consigliabile passarle come parametro `in` per motivi di prestazioni.
- Non passare `struct` mai `in` un come parametro `readonly` a meno che `readonly` non venga dichiarato con il modificatore o il metodo non chiami solo i membri dello struct. La violazione di queste indicazioni può influire negativamente sulle prestazioni e potrebbe portare a un comportamento oscuro.
- Utilizzare [`ref struct`](language-reference/keywords/ref.md#ref-struct-types)un oggetto `readonly ref struct` , <xref:System.Span%601> <xref:System.ReadOnlySpan%601> o ad esempio o per lavorare con la memoria come sequenza di byte.

Queste tecniche obbligano a trovare un compromesso tra due obiettivi opposti in termini di **riferimenti** e **valori**. Le variabili che sono [tipi riferimento](programming-guide/types/index.md#reference-types) contengono un riferimento alla posizione in memoria. Le variabili che sono [tipi valore](programming-guide/types/index.md#value-types) contengono direttamente il rispettivo valore. Queste caratteristiche evidenziano le principali differenze da tenere in considerazione per la gestione delle risorse della memoria. I **tipi valore** vengono in genere copiati se passati a un metodo o restituiti da un metodo. Questo comportamento include la copia del valore di `this` quando si chiamano i membri di un tipo valore. Il costo della copia è correlato alla dimensione del tipo. I **tipi riferimento** vengono allocati nell'heap gestito. Ogni nuovo oggetto richiede una nuova allocazione e successivamente deve essere recuperato. Entrambe queste operazioni richiedono tempo. Il riferimento viene copiato quando un tipo riferimento viene passato come argomento a un metodo o restituito da un metodo.

Questo articolo usa il concetto di esempio seguente relativo alla struttura di punti 3D per illustrare queste raccomandazioni:

```csharp
public struct Point3D
{
    public double X;
    public double Y;
    public double Z;
}
```

Le implementazioni di questo concetto variano a seconda degli esempi.

## <a name="declare-readonly-structs-for-immutable-value-types"></a>Dichiarare struct readonly per tipi valore non modificabili

Dichiarando uno `struct` tramite il modificatore `readonly`, si informa il compilatore che la finalità è la creazione di un tipo non modificabile. Il compilatore applica tale decisione di progettazione con le regole seguenti:

- Tutti i membri dei campi devono essere `readonly`
- Tutte le proprietà devono essere di sola lettura, incluse le proprietà implementate automaticamente.

Queste due regole sono sufficienti a garantire che nessun membro di un `readonly struct` modifichi lo stato di tale struct. Lo `struct` non è modificabile. La struttura `Point3D` può essere definita come struct non modificabile, come illustrato nell'esempio seguente:

```csharp
readonly public struct ReadonlyPoint3D
{
    public ReadonlyPoint3D(double x, double y, double z)
    {
        this.X = x;
        this.Y = y;
        this.Z = z;
    }

    public double X { get; }
    public double Y { get; }
    public double Z { get; }
}
```

Seguire questa raccomandazione quando la finalità della progettazione è la creazione di un tipo valore non modificabile. Qualsiasi miglioramento delle prestazioni comporta un ulteriore vantaggio. Il `readonly struct` esprime chiaramente la finalità della progettazione.

## <a name="declare-readonly-members-when-a-struct-cant-be-immutable"></a>Dichiarare membri readonly quando uno struct non può essere immutabileDeclare readonly members when a struct can't be immutable

Quando un tipo struct è modificabile, in Cè 8.0 e versioni successive, `readonly`è necessario dichiarare i membri che non causano la mutazione. Si consideri un'applicazione diversa che richiede una struttura di punti 3D, ma deve supportare la mutabilità. La versione seguente della struttura dei `readonly` punti 3D aggiunge il modificatore solo ai membri che non modificano la struttura. Seguire questo esempio quando la progettazione deve supportare le modifiche apportate allo struct da parte di alcuni membri, ma si desidera comunque i vantaggi derivanti dall'applicazione di readonly su alcuni membri:

```csharp
public struct Point3D
{
    public Point3D(double x, double y, double z)
    {
        _x = x;
        _y = y;
        _z = z;
    }

    private double _x;
    public double X
    {
        readonly get => _x;
        set => _x = value;
    }

    private double _y;
    public double Y
    {
        readonly get => _y;
        set => _y = value;
    }

    private double _z;
    public double Z
    {
        readonly get => _z;
        set => _z = value;
    }

    public readonly double Distance => Math.Sqrt(X * X + Y * Y + Z * Z);

    public readonly override string ToString() => $"{X}, {Y}, {Z}";
}
```

Nell'esempio precedente vengono illustrate molte delle `readonly` posizioni in cui è possibile applicare il modificatore: metodi, proprietà e funzioni di accesso alle proprietà. Se si utilizzano proprietà implementate `readonly` automaticamente, `get` il compilatore aggiunge il modificatore alla funzione di accesso per le proprietà di lettura/scrittura. Il compilatore `readonly` aggiunge il modificatore alle dichiarazioni di `get` proprietà implementate automaticamente per le proprietà con solo una funzione di accesso.

L'aggiunta del `readonly` modificatore ai membri che non modificano lo stato offre due vantaggi correlati. In primo luogo, il compilatore applica l'intento. Tale membro non può mutare lo stato dello struct, né può accedere `readonly`a un membro che non è anch'esso contrassegnato come . In secondo luogo, il compilatore `in` non creerà `readonly` copie difensive dei parametri quando si accede a un membro. Il compilatore può rendere questa ottimizzazione `struct` in modo `readonly` sicuro perché garantisce che l'oggetto non viene modificato da un membro.

## <a name="use-ref-readonly-return-statements-for-large-structures-when-possible"></a>Usare le istruzioni `ref readonly return` per le strutture di grandi dimensioni, se possibile

È possibile restituire i valori per riferimento quando il valore restituito non è locale per il metodo di restituzione. Con la restituzione per riferimento viene copiato solo il riferimento, non la struttura. Nell'esempio seguente la proprietà `Origin` non può usare un valore restituito `ref` perché il valore da restituire è una variabile locale:

```csharp
public Point3D Origin => new Point3D(0,0,0);
```

La definizione della proprietà seguente può tuttavia essere restituita per riferimento perché il valore restituito è un membro statico:

```csharp
public struct Point3D
{
    private static Point3D origin = new Point3D(0,0,0);

    // Dangerous! returning a mutable reference to internal storage
    public ref Point3D Origin => ref origin;

    // other members removed for space
}
```

Per fare in modo che i chiamanti non modifichino l'origine, restituire il valore per `ref readonly`:

```csharp
public struct Point3D
{
    private static Point3D origin = new Point3D(0,0,0);

    public static ref readonly Point3D Origin => ref origin;

    // other members removed for space
}
```

La restituzione di `ref readonly` consente un risparmio a livello di copie di strutture di dimensioni maggiori e di mantenere l'immutabilità dei membri dati interni.

Nel sito della chiamata i chiamanti scelgono di usare la proprietà `Origin` come `ref readonly` o come valore:

[!code-csharp[AssignRefReadonly](../../samples/snippets/csharp/safe-efficient-code/ref-readonly-struct/Program.cs#AssignRefReadonly "Assigning a ref readonly")]

La prima assegnazione del codice precedente crea una copia della costante `Origin` e assegna tale copia. La seconda assegna un riferimento. Si noti che il modificatore `readonly` deve fare parte della dichiarazione della variabile. Il riferimento a cui viene fatto riferimento non può essere modificato. I tentativi di eseguire questa operazione generano un errore in fase di compilazione.

Il modificatore `readonly` è necessario nella dichiarazione di `originReference`.

Il compilatore fa in modo che il chiamante non possa modificare il riferimento. I tentativi di assegnazione diretta del valore generano un errore in fase di compilazione. Il compilatore non può tuttavia sapere se un metodo del membro modifica lo stato dello struct.
Per assicurarsi che l'oggetto non venga modificato, il compilatore crea una copia e chiama i riferimenti al membro usando tale copia. Tutte le modifiche vengono apportate a tale copia difensiva.

## <a name="apply-the-in-modifier-to-readonly-struct-parameters-larger-than-systemintptrsize"></a>Applicare il modificatore `in` ai parametri `readonly struct` maggiori di `System.IntPtr.Size`

La parola chiave `in` è completare alle parole chiave `ref` e `out` esistenti per passare gli argomenti per riferimento. La parola chiave `in` specifica il passaggio dell'argomento per riferimento, ma il metodo chiamato non modifica il valore.

Questa aggiunta fornisce un vocabolario completo per esprimere le finalità di progettazione.
I tipi valore vengono copiati quando vengono passati a un metodo chiamato se nella firma del metodo non si specifica alcuno dei modificatori seguenti. Ognuno di questi modificatori specifica che una variabile viene passata per riferimento, evitando la copia. Ogni modificatore esprime una finalità diversa:

- `out`: questo metodo imposta il valore dell'argomento usato come parametro.
- `ref`: questo metodo può impostare il valore dell'argomento usato come parametro.
- `in`: questo metodo non modifica il valore dell'argomento utilizzato come parametro.

Aggiungere il modificatore `in` per passare un argomento per riferimento e dichiarare che la finalità di passare argomenti per riferimento, per evitare operazioni di copia non necessarie, non quella di modificare l'oggetto usato come argomento.

Questa procedura spesso migliora le prestazioni per i tipi valore readonly di dimensioni superiori a <xref:System.IntPtr.Size?displayProperty=nameWithType>. Per i tipi semplici (tipi `sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char`, `float`, `double`, `decimal` e `bool` ed `enum`), i potenziali miglioramenti alle prestazioni sono minimi. Le prestazioni potrebbero infatti peggiorare usando il passaggio per riferimento per i tipi con dimensioni inferiori a <xref:System.IntPtr.Size?displayProperty=nameWithType>.

Il codice seguente illustra un esempio di metodo che calcola la distanza tra due punti nello spazio 3D.

[!code-csharp[InArgument](../../samples/snippets/csharp/safe-efficient-code/ref-readonly-struct/Program.cs#InArgument "Specifying an in argument")]

Gli argomenti sono due strutture, contenenti ognuna tre valori double. Un valore double è pari a 8 byte, quindi ogni argomento è pari a 24 byte. Specificando il modificatore `in`, si passa un riferimento a 4 byte o 8 byte a tali argomenti, a seconda dell'architettura del computer. La differenza a livello di dimensioni è piccola, ma aumenta quando l'applicazione chiama questo metodo in un ciclo ridotto usando più valori diversi.

Il modificatore `in` integra `out` e `ref` anche in altri modi. Non è possibile creare overload di un metodo che si distinguono solo per la presenza di `in`, `out` o `ref`. Queste nuove regole estendono lo stesso comportamento da sempre definito per i parametri `out` e `ref`. Come i modificatori `out` e `ref`, i tipi valore non sono boxed perché viene applicato il modificatore `in`.

Il modificatore `in` può essere applicato a tutti i membri che accettano parametri: metodi, delegati, espressioni lambda, funzioni locali, indicizzatori, operatori.

Un'altra caratteristica dei parametri `in` è che è possibile usare valori letterali o costanti per l'argomento in un parametro `in`. Inoltre, diversamente da un parametro `ref` o `out`, non è necessario applicare il modificatore `in` nel sito di chiamata. Il codice seguente illustra due esempi di chiamata al metodo `CalculateDistance`. Il primo usa due variabili locali passate per riferimento. Il secondo include una variabile temporanea creata durante la chiamata al metodo.

[!code-csharp[UseInArgument](../../samples/snippets/csharp/safe-efficient-code/ref-readonly-struct/Program.cs#UseInArgument "Specifying an In argument")]

Il compilatore applica la natura di sola lettura di un argomento `in` in diversi modi.  Prima di tutto il metodo chiamato non può essere direttamente assegnato a un parametro `in`. Non può essere direttamente assegnato ai campi di un parametro `in` se quel valore è un tipo `struct`. Non è neppure possibile passare un parametro `in` a metodi che usano il modificatore `ref` o `out`.
Queste regole sono valide per qualsiasi campo di un parametro `in`, a condizione che il campo sia di tipo `struct` e che anche il parametro sia di tipo `struct`. Queste regole, in effetti, vengono applicate per più livelli di accesso ai membri, a condizione che a tutti i livelli di accesso ai membri i tipi siano `structs`.
Il compilatore impone che i tipi `struct` passati come argomenti `in` e i relativi membri `struct` siano variabili di sola lettura, se usati come argomenti per altri metodi.

L'uso di parametri `in` consente di evitare i costi potenziali sulle prestazioni per l'esecuzione di copie, ma non modifica la semantica delle chiamate a metodi. Non è quindi necessario specificare il modificatore `in` presso il sito di chiamata. Omettendo il modificatore `in` presso il sito di chiamata si informa il compilatore che può effettuare una copia dell'argomento per i motivi seguenti:

- Esiste una conversione implicita, ma non una conversione di identità dal tipo di argomento al tipo di parametro.
- L'argomento è un'espressione, ma non ha una variabile di archiviazione nota.
- È presente un overload diverso per la presenza o l'assenza di `in`. In tal caso, l'overload in base al valore è una corrispondenza migliore.

Queste regole sono utili quando si aggiorna codice esistente per usare argomenti di riferimento di sola lettura. All'interno del metodo chiamato è possibile chiamare qualsiasi metodo di istanza che usa parametri in base al valore. In tali istanze viene creata una copia del parametro `in`. Poiché il compilatore può creare una variabile temporanea per qualsiasi parametro `in`, è anche possibile specificare i valori predefiniti per qualsiasi parametro `in`. Il codice seguente specifica l'origine (punto 0,0) come valore predefinito per il secondo punto:

[!code-csharp[InArgumentDefault](../../samples/snippets/csharp/safe-efficient-code/ref-readonly-struct/Program.cs#InArgumentDefault "Specifying defaults for an in parameter")]

Per imporre al compilatore di passare argomenti di sola lettura per riferimento, specificare il modificatore `in` per gli argomenti presso il sito di chiamata, come illustrato nel codice seguente:

[!code-csharp[UseInArgument](../../samples/snippets/csharp/safe-efficient-code/ref-readonly-struct/Program.cs#ExplicitInArgument "Specifying an In argument")]

Questo comportamento semplifica nel tempo l'adozione di parametri `in` in codebase di grandi dimensioni in cui è possibile ottenere miglioramenti delle prestazioni. È prima necessario aggiungere il modificatore `in` alle firme dei metodi. È quindi possibile aggiungere il modificatore `in` presso i siti di chiamata e creare tipi `readonly struct` per consentire al compilatore di evitare di creare copie difensive di parametri `in` in altre posizioni.

La designazione del parametro `in` può anche essere usata con tipi riferimento o valori numerici. Gli eventuali vantaggi in entrambi i casi sono tuttavia minimi.

## <a name="avoid-mutable-structs-as-an-in-argument"></a>Evitare struct modificabili `in` come argomentoAvoid mutable structs as an argument

Le tecniche descritte in precedenza illustrano come evitare le copie restituendo i riferimenti e passando i valori per riferimento. Queste tecniche garantiscono prestazioni ottimali quando i tipi di argomenti vengono dichiarati come tipi `readonly struct`. In caso contrario, il compilatore deve creare **copie difensive** in molte situazioni per applicare la natura di sola lettura degli argomenti. Considerare l'esempio seguente che calcola la distanza di un punto 3D dall'origine:

[!code-csharp[InArgument](../../samples/snippets/csharp/safe-efficient-code/ref-readonly-struct/Program.cs#InArgument "Specifying an in argument")]

La struttura `Point3D`*non* è uno struct readonly. Sono presenti sei diverse chiamate di accesso a proprietà nel corpo di questo metodo. A un primo esame, si potrebbe pensare che questi accessi siano sicuri. Una funzione di accesso `get` infatti non dovrebbe modificare lo stato dell'oggetto, ma nessuna regola del linguaggio lo impone. È solo una convenzione comune. Qualsiasi tipo può implementare una funzione di accesso `get` che modifica lo stato interno. Senza una certa garanzia del linguaggio, il compilatore deve creare `readonly` una copia temporanea dell'argomento prima di chiamare qualsiasi membro non contrassegnato con il modificatore. La risorsa di archiviazione temporanea viene creata nello stack, i valori dell'argomento vengono copiati nella risorsa di archiviazione temporanea e il valore viene copiato nello stack per ogni accesso ai membri come argomento `this`. In molte situazioni, queste copie danneggiano le prestazioni in modo sufficiente che il pass-by-value è `readonly struct` più veloce del riferimento pass-by-readonly quando il tipo di argomento non è un e il metodo chiama membri non contrassegnati `readonly`con . Se si contrassegnano tutti i metodi `readonly`che non modificano lo stato struct come , il compilatore può determinare in modo sicuro che lo stato struct non viene modificato e non è necessaria una copia difensiva.

Al contrario, se il calcolo della `ReadonlyPoint3D`distanza utilizza lo struct non modificabile, non sono necessari oggetti temporanei:

[!code-csharp[readonlyInArgument](../../samples/snippets/csharp/safe-efficient-code/ref-readonly-struct/Program.cs#ReadOnlyInArgument "Specifying a readonly in argument")]

Il compilatore genera codice più efficiente `readonly struct`quando `this` si chiamano i membri di un `in` oggetto : il riferimento, anziché una copia del ricevitore, è sempre un parametro passato per riferimento al metodo membro. Questa ottimizzazione consente un risparmio a livello di copie quando si usa `readonly struct` come argomento `in`.

Non è necessario passare un tipo di `in` valore nullable come argomento. Il <xref:System.Nullable%601> tipo non è dichiarato come struct di sola lettura. Ciò significa che il compilatore deve generare le copie difensive di tutti gli argomenti del valore di tipo nullable passato a un metodo tramite il modificatore `in` nella dichiarazione del parametro.

È possibile visualizzare un programma di esempio che illustra le differenze di prestazioni utilizzando [BenchmarkDotNet](https://www.nuget.org/packages/BenchmarkDotNet/) nel repository degli esempi su GitHub.You can see an example program that demonstrates the performance differences using BenchmarkDotNet in our [samples repository](https://github.com/dotnet/samples/tree/master/csharp/safe-efficient-code/benchmark) on GitHub. Viene confrontato il passaggio di uno struct modificabile per valore e per riferimento con il passaggio di uno struct non modificabile per valore e per riferimento. L'uso dello struct non modificabile e del passaggio per riferimento è più veloce.

## <a name="use-ref-struct-types-to-work-with-blocks-or-memory-on-a-single-stack-frame"></a>Usare i tipi `ref struct` per lavorare con i blocchi o la memoria in un singolo stack frame

Una funzionalità del linguaggio correlata è la possibilità di dichiarare un tipo valore che deve essere vincolato a un singolo stack frame. Questa restrizione consente al compilatore di eseguire diverse ottimizzazioni. La principale motivazione di questa funzionalità sono stati <xref:System.Span%601> e le strutture correlate. Da questi miglioramenti si otterranno prestazioni più avanzate grazie alle API .NET nuove e aggiornate che usano il tipo <xref:System.Span%601>.

È possibile avere requisiti simili [`stackalloc`](language-reference/operators/stackalloc.md) quando si usa la memoria creata con o quando si usa memoria dalle API di interoperabilità. È possibile definire i tipi `ref struct` in base a tali esigenze.

## <a name="readonly-ref-struct-type"></a>Tipo di`readonly ref struct`

Dichiarando uno struct come `readonly ref` si combinano i vantaggi e le restrizioni delle dichiarazioni `ref struct` e `readonly struct`. La memoria usata dallo span di sola lettura è limitata a un singolo stack frame e non può essere modificata.

## <a name="conclusions"></a>Conclusioni

L'uso di tipi valore ridice al minimo il numero di operazioni di allocazione:

- Lo spazio di archiviazione per i tipi valore viene allocato nello stack per le variabili locali e gli argomenti dei metodi.
- Lo spazio di archiviazione per i tipi valore membri di altri oggetti viene allocato come parte dell'oggetto, non come allocazione separata.
- Lo spazio di archiviazione per i valori restituiti dei tipi valore viene allocato nello stack.

Confrontare questi tipi con i tipi riferimento nelle stesse situazioni:

- Lo spazio di archiviazione per i tipi riferimento viene allocato nell'heap per le variabili locali e gli argomenti dei metodi. Il riferimento è archiviato nello stack.
- Lo spazio di archiviazione per i tipi riferimento membri di altri oggetti viene allocato separatamente nell'heap. L'oggetto contenitore archivia il riferimento.
- Lo spazio di archiviazione per i valori restituiti dei tipi riferimento viene allocato nell'heap. Il riferimento a tale spazio di archiviazione è archiviato nello stack.

La riduzione al minimo delle allocazioni richiede alcuni compromessi. Si copia più memoria quando le dimensioni dello `struct` sono superiori a quelle di un riferimento. Un riferimento è in genere a 64 bit o a 32 bit e dipende dalla CPU del computer di destinazione.

Questi compromessi in genere hanno un impatto minimo sulle prestazioni. Tuttavia, per gli struct di grandi dimensioni o le raccolte di dimensioni maggiori, l'impatto sulle prestazioni aumenta. L'impatto può essere forte nei cicli ridotti e nei percorsi critici per i programmi.

Questi miglioramenti del linguaggio C# sono progettati per gli algoritmi con prestazioni critiche in cui la riduzione al minimo delle allocazioni della memoria è un fattore determinante per raggiungere le prestazioni necessarie. È possibile che non si usino spesso queste funzionalità nella scrittura del codice. Tuttavia, questi miglioramenti sono stati adottati in .NET. Il sempre maggior numero di API che useranno queste funzionalità renderà evidente il miglioramento delle prestazioni delle applicazioni.

## <a name="see-also"></a>Vedere anche

- [ref (parola chiave)](language-reference/keywords/ref.md)
- [Valori restituiti e variabili locali ref](programming-guide/classes-and-structs/ref-returns.md)
