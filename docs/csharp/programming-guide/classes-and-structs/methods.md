---
title: Metodi - Guida per programmatori C#
ms.date: 07/20/2015
helpviewer_keywords:
- methods [C#]
- C# language, methods
ms.assetid: cc738f07-e8cd-4683-9585-9f40c0667c37
ms.openlocfilehash: 8c90f06bfadc528bd9575ead30e6b01263055fe8
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743914"
---
# <a name="methods-c-programming-guide"></a>Metodi (Guida per programmatori C#)

Un metodo è un blocco di codice che contiene una serie di istruzioni. Un programma fa in modo che le istruzioni vengano eseguite chiamando il metodo e specificando gli argomenti del metodo obbligatori. In C#, ogni istruzione eseguita viene attuata nel contesto di un metodo. Il `Main` metodo è il punto di ingresso per C# ogni applicazione e viene chiamato dal Common Language Runtime (CLR) all'avvio del programma.

> [!NOTE]
> Questo articolo illustra i metodi denominati. Per informazioni sulle funzioni anonime, vedere [Funzioni anonime](../statements-expressions-operators/anonymous-functions.md).

## <a name="method-signatures"></a>Firme del metodo

I metodi vengono dichiarati in una [classe](../../language-reference/keywords/class.md) o in una [struct](../../language-reference/keywords/struct.md) specificando il livello di accesso, ad esempio `public` o `private`, i modificatori facoltativi, ad esempio `abstract` o `sealed`, il valore restituito, il nome del metodo e i parametri del metodo. Queste parti costituiscono la firma del metodo.

> [!NOTE]
> Un tipo restituito di un metodo non fa parte della firma del metodo in caso di overload dei metodi. Fa tuttavia parte della firma del metodo quando si determina la compatibilità tra un delegato e il metodo a cui fa riferimento.

I parametri del metodo vengono racchiusi tra parentesi e separati da virgole. Le parentesi vuote indicano che il metodo non richiede parametri. Questa classe contiene quattro metodi:

[!code-csharp[csProgGuideObjects#40](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#40)]

## <a name="method-access"></a>Accesso ai metodi

Chiamare un metodo su un oggetto è come accedere a un campo. Dopo il nome dell'oggetto aggiungere un punto, il nome del metodo e le parentesi. Gli argomenti vengono elencati tra parentesi e separati da virgole. I metodi della classe `Motorcycle` possono quindi essere chiamati come nell'esempio seguente:

[!code-csharp[csProgGuideObjects#41](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#41)]

## <a name="method-parameters-vs-arguments"></a>Parametri di metodo e argomenti

La definizione del metodo specifica i nomi e i tipi di tutti i parametri obbligatori. Quando il codice chiamante chiama il metodo, fornisce valori concreti, detti argomenti, per ogni parametro. Gli argomenti devono essere compatibili con il tipo di parametro, ma il nome dell'argomento (se presente) usato nel codice chiamante non deve essere lo stesso del parametro denominato definito nel metodo. Ad esempio:

[!code-csharp[csProgGuideObjects#74](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#74)]

## <a name="passing-by-reference-vs-passing-by-value"></a>Passaggio per riferimento e passaggio per valore

Per impostazione predefinita, quando un'istanza di un [tipo di valore](../../language-reference/builtin-types/value-types.md) viene passata a un metodo, la relativa copia viene passata al posto dell'istanza stessa. Pertanto, le modifiche apportate all'argomento non hanno alcun effetto sull'istanza originale nel metodo chiamante. Per passare un'istanza di tipo valore per riferimento, usare la parola chiave `ref`. Per altre informazioni, vedere [Passaggio di parametri di tipi di valore](./passing-value-type-parameters.md).

Quando viene passato un oggetto di un tipo riferimento a un metodo, viene passato un riferimento all'oggetto, ovvero, il metodo riceve un argomento che indica la posizione dell'oggetto, ma non l'oggetto stesso. Se si modifica un membro dell'oggetto usando questo riferimento, la modifica si riflette nell'argomento nel metodo chiamante, anche se si passa l'oggetto per valore.

Per creare un tipo riferimento, usare la parola chiave `class`, come illustrato nell'esempio seguente:

[!code-csharp[csProgGuideObjects#42](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#42)]

Se ora si passa un oggetto basato su questo tipo a un metodo, viene passato un riferimento all'oggetto. Nell'esempio seguente viene passato un oggetto di tipo `SampleRefType` al metodo `ModifyObject`:

[!code-csharp[csProgGuideObjects#75](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#75)]

L'esempio è sostanzialmente uguale al precedente in quanto passa un argomento per valore a un metodo, ma, essendo usato un tipo riferimento, il risultato è diverso. La modifica apportata in `ModifyObject` al campo `value` del parametro, `obj`, cambia anche il campo `value` dell'argomento, `rt`, nel metodo `TestRefType` . Il metodo `TestRefType` visualizza 33 come output.

Per altre informazioni su come passare i tipi di riferimento per riferimento e per valore, vedere [Passaggio di parametri di tipi di riferimento ](./passing-reference-type-parameters.md) e [Tipi di riferimento](../../language-reference/keywords/reference-types.md).

## <a name="return-values"></a>Valori restituiti

I metodi possono restituire un valore al chiamante. Se il tipo restituito, il tipo elencato prima del nome del metodo, non è `void`, il metodo può restituire il valore usando la parola chiave `return` . Un'istruzione con la parola chiave `return` seguita da un valore corrispondente al tipo restituito restituirà tale valore al chiamante del metodo.

Il valore può essere restituito dal chiamante per valore o, a partire dalla versione C# 7.0, [per riferimento](ref-returns.md). I valori vengono restituiti al chiamante per riferimento se la parola chiave `ref` viene usata nella firma del metodo e se segue ogni parola chiave `return`. La firma del metodo e l'istruzione di restituzione seguenti, ad esempio, indicano che il metodo restituisce al chiamante i nomi di una variabile `estDistance` per riferimento.

```csharp
public ref double GetEstimatedDistance()
{
    return ref estDistance;
}
```

La parola chiave `return` interrompe anche l'esecuzione del metodo. Se il tipo restituito è `void`, un'istruzione `return` senza un valore è tuttavia utile per interrompere l'esecuzione del metodo. Senza la parola chiave `return` , l'esecuzione del metodo verrà interrotta quando verrà raggiunta la fine del blocco di codice. Per usare la parola chiave `return` per restituire un valore, sono obbligatori metodi con un tipo restituito non void. Ad esempio, questi due metodi usano la parola chiave `return` per restituire numeri interi:

[!code-csharp[csProgGuideObjects#44](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#44)]

Per usare un valore restituito da un metodo, il metodo chiamante può usare la chiamata al metodo stessa ovunque è sufficiente un valore dello stesso tipo. È inoltre possibile assegnare il valore restituito a una variabile. I due esempi seguenti di codice ottengono lo stesso risultato:

[!code-csharp[csProgGuideObjects#45](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#45)]

[!code-csharp[csProgGuideObjects#46](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#46)]

L'uso di una variabile locale, in questo caso `result`, per archiviare un valore è facoltativo. Potrebbe migliorare la leggibilità del codice o potrebbe essere necessario se si desidera archiviare il valore originale dell'argomento per l'intero ambito del metodo.

Per usare un valore restituito da un metodo per riferimento, è necessario dichiarare una variabile [locale ref](ref-returns.md#ref-locals) se si vuole modificarne il valore. Se, ad esempio, il metodo `Planet.GetEstimatedDistance` restituisce un valore <xref:System.Double> per riferimento, è possibile definirlo come variabile locale ref con un codice simile al seguente:

```csharp
ref int distance = plant
```

Non è necessario restituire una matrice multidimensionale da un metodo, `M`, che modifica il contenuto della matrice, se la funzione chiamante ha passato la matrice a `M`.  Si può restituire la matrice risultante da `M` per un flusso di valori corretto o funzionale, ma non è necessario perché C# passa tutti i tipi riferimento per valore e il valore di un riferimento a una matrice è il puntatore alla matrice. Nel metodo `M`, tutte le modifiche apportate al contenuto della matrice sono osservabili da qualsiasi codice che contiene un riferimento alla matrice, come illustrato nell'esempio seguente:

```csharp
static void Main(string[] args)
{
    int[,] matrix = new int[2, 2];
    FillMatrix(matrix);
    // matrix is now full of -1
}

public static void FillMatrix(int[,] matrix)
{
    for (int i = 0; i < matrix.GetLength(0); i++)
    {
        for (int j = 0; j < matrix.GetLength(1); j++)
        {
            matrix[i, j] = -1;
        }
    }
}
```

Per altre informazioni, vedere [return](../../language-reference/keywords/return.md).

## <a name="async-methods"></a>Metodi asincroni

Tramite la funzionalità async, è possibile richiamare i metodi asincroni senza usare callback espliciti o suddividere manualmente il codice in più metodi o espressioni lambda.

Se si contrassegna un metodo con il modificatore [async](../../language-reference/keywords/async.md), è possibile usare l'operatore [await](../../language-reference/operators/await.md) nel metodo. Quando il controllo raggiunge un'espressione await nel metodo asincrono, il controllo torna al chiamante e l'avanzamento nel metodo viene sospeso fino al completamento dell'attività attesa. Una volta completata l'attività, l'esecuzione del metodo può riprendere.

> [!NOTE]
> Un metodo async viene restituito al chiamante quando rileva il primo oggetto atteso che non è ancora completo o raggiunge la fine del metodo async, qualunque si verifichi prima.

Un metodo asincrono può avere un tipo restituito <xref:System.Threading.Tasks.Task%601>, <xref:System.Threading.Tasks.Task>o void. Il tipo restituito void viene usato principalmente per definire i gestori eventi, dove un tipo restituito void è necessario. Un metodo asincrono che restituisce void non può essere atteso e il chiamante di un metodo che restituisce void non può intercettare eccezioni generate dal metodo.

Nel seguente esempio, `DelayAsync` è un metodo asincrono con un tipo restituito <xref:System.Threading.Tasks.Task%601>. `DelayAsync` ha un'istruzione `return` che restituisce un numero intero. La dichiarazione del metodo di `DelayAsync` deve quindi avere un tipo restituito `Task<int>`. Poiché il tipo restituito è `Task<int>`, la valutazione dell'espressione `await` in `DoSomethingAsync` genera un numero intero come illustra l'istruzione seguente: `int result = await delayTask`.

Il metodo `startButton_Click` è un esempio di un metodo asincrono con un tipo restituito void. Poiché `DoSomethingAsync` è un metodo asincrono, l'attività per la chiamata a `DoSomethingAsync` deve essere attesa, come mostra l'istruzione seguente: `await DoSomethingAsync();`. Il metodo `startButton_Click` deve essere definito con il modificatore `async` perché il metodo ha un'espressione `await` .

[!code-csharp[csAsyncMethod#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csasyncmethod/cs/mainwindow.xaml.cs#2)]

Un metodo asincrono non può dichiarare parametri [ref](../../language-reference/keywords/ref.md) o [out](../../language-reference/keywords/out-parameter-modifier.md) , ma può chiamare metodi che hanno tali parametri.

Per altre informazioni sui metodi asincroni, vedere [Programmazione asincrona con Async e Await](../concepts/async/index.md), [Flusso di controllo in programmi asincroni](../concepts/async/control-flow-in-async-programs.md) e [Tipi restituiti asincroni](../concepts/async/async-return-types.md).

## <a name="expression-body-definitions"></a>Definizioni del corpo dell'espressione

È comune disporre di definizioni di metodo che semplicemente restituiscono subito il risultato di un'espressione o che includono una singola istruzione come corpo del metodo. Esiste una sintassi breve per definire tali metodi usando `=>`:

```csharp
public Point Move(int dx, int dy) => new Point(x + dx, y + dy);
public void Print() => Console.WriteLine(First + " " + Last);
// Works with operators, properties, and indexers too.
public static Complex operator +(Complex a, Complex b) => a.Add(b);
public string Name => First + " " + Last;
public Customer this[long id] => store.LookupCustomer(id);
```

Se il metodo restituisce `void` o è un metodo asincrono, il corpo del metodo deve essere un'espressione di istruzione (come per le espressioni lambda). Per le proprietà e gli indicizzatori, devono essere di sola lettura e non è necessario usare la parola chiave della funzione di accesso `get`.

## <a name="iterators"></a>Iterators

Un iteratore esegue un'iterazione personalizzata su una raccolta, ad esempio un elenco o una matrice. Un iteratore usa l'istruzione [yield return](../../language-reference/keywords/yield.md) per restituire un elemento alla volta. Quando viene raggiunta un'istruzione [yield return](../../language-reference/keywords/yield.md) , la posizione corrente nel codice viene memorizzata. L'esecuzione viene riavviata a partire da quella posizione la volta successiva che viene chiamato l'iteratore.

Per chiamare un iteratore dal codice client, usare un'istruzione [foreach](../../language-reference/keywords/foreach-in.md) .

Il tipo restituito di un iteratore può essere <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>o <xref:System.Collections.Generic.IEnumerator%601>.

Per altre informazioni, vedere [Iteratori](../concepts/iterators.md).

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../index.md)
- [Classi e struct](index.md)
- [Modificatori di accesso](access-modifiers.md)
- [Classi statiche e membri di classi statiche](static-classes-and-static-class-members.md)
- [Ereditarietà](inheritance.md)
- [Classi e membri delle classi astratte e sealed](abstract-and-sealed-classes-and-class-members.md)
- [params](../../language-reference/keywords/params.md)
- [return](../../language-reference/keywords/return.md)
- [out](../../language-reference/keywords/out.md)
- [ref](../../language-reference/keywords/ref.md)
- [Passaggio di parametri](passing-parameters.md)
