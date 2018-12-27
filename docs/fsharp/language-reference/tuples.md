---
title: Tuple
description: Scopri la F# tupla, un raggruppamento di valori senza nome, ma ordinati, tipi potenzialmente diversi.
ms.date: 05/16/2016
ms.openlocfilehash: a1fc31d4dc97c0921545e53b91dcde0547002006
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/19/2018
ms.locfileid: "53611048"
---
# <a name="tuples"></a>Tuple

Oggetto *tupla* è un raggruppamento di valori senza nome, ma ordinati, tipi potenzialmente diversi.  Le tuple possono essere tipi riferimento o struct.

## <a name="syntax"></a>Sintassi

```fsharp
(element, ... , element)
struct(element, ... ,element )
```

## <a name="remarks"></a>Note

Ciascuna *elemento* nella sintassi precedente può essere qualsiasi F# espressione.

## <a name="examples"></a>Esempi

Coppie Triple e così via, dei tipi uguali o diversi esempi di tuple. Nel codice seguente sono illustrati alcuni esempi.

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L6-L21)]

## <a name="obtaining-individual-values"></a>Recupero di singoli valori

È possibile utilizzare criteri di ricerca per accedere e assegnare i nomi per gli elementi di tupla, come illustrato nel codice seguente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L27-L29)]

È anche possibile decostruire una tupla tramite criteri di ricerca di fuori di una `match` espressione tramite `let` associazione:

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L34-L37)]

Oppure potete creare una serie corrispondono in tuple come input per le funzioni:

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L43-L47)]

Se è necessario un solo elemento di tupla, il carattere jolly (il carattere di sottolineatura) è utilizzabile per evitare di creare un nuovo nome per un valore che non è necessario.

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L53-L54)]

Copia gli elementi da una tupla di riferimento in una tupla di uno struct è anche semplice:

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L62-L66)]

Le funzioni `fst` e `snd` (fanno riferimento le tuple solo) restituiscono il primo e secondo elemento di una tupla, rispettivamente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L72-L73)]

Non vi è alcuna funzione predefinita che restituisce il terzo elemento di una triple, ma è possibile scrivere facilmente uno come indicato di seguito.

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L78-L78)]

In generale, è preferibile usare criteri di ricerca per accedere agli elementi di tupla individuali.

## <a name="using-tuples"></a>Usare le tuple

Le tuple forniscono un modo pratico per restituire più valori da una funzione, come illustrato nell'esempio seguente. In questo esempio esegue la divisione di interi e restituisce il risultato arrotondato dell'operazione come membro di una coppia di tuple prima che il resto come secondo membro della coppia.

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L83-L86)]

Le tuple sono anche utilizzabile come argomenti della funzione quando si desidera evitare il currying implicita degli argomenti della funzione che è in cui è inclusa la sintassi della funzione normale.

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L88-L88)]

La sintassi comune per la definizione di funzione `let sum a b = a + b` consente di definire una funzione che rappresenta l'applicazione parziale del primo argomento della funzione, come illustrato nel codice seguente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L90-L94)]

Uso di una tupla come parametro disabilita currying. Per altre informazioni, vedere "Applicazione parziale di argomenti" nella [funzioni](functions/index.md).

## <a name="names-of-tuple-types"></a>Nomi dei tipi di tupla

Quando si scrive il nome di un tipo che è una tupla, è utilizzare il `*` simbolo per separare gli elementi. Per una tupla costituita da un `int`, un `float`e una `string`, ad esempio `(10, 10.0, "ten")`, il tipo viene scritto come indicato di seguito.

```fsharp
int * float * string
```

## <a name="interoperation-with-c-tuples"></a>Interoperabilità con tuple in c#

C# 7.0 ha introdotto le tuple del linguaggio.  Le tuple in C# sono gli struct e sono equivalenti alle tuple di struct F#.  Se è necessario per l'interoperabilità con c#, è necessario usare le tuple struct.

Si tratta di un'operazione semplice.  Si supponga, ad esempio passare una tupla a una classe c# e quindi utilizzare il risultato, che è anche una tupla:

```csharp
namespace CSharpTupleInterop
{
    public static class Example
    {
        public static (int, int) AddOneToXAndY((int x, int y) a) =>
            (a.x + 1, a.y + 1);
    }
}
```

Nel F# code, è quindi possibile passare una tupla di uno struct come parametro e utilizzare il risultato come una tupla di uno struct.

```fsharp
open TupleInterop

let struct (newX, newY) = Example.AddOneToXAndY(struct (1, 2))
// newX is now 2, and newY is now 3
```

### <a name="converting-between-reference-tuples-and-struct-tuples"></a>Conversione tra le tuple di riferimento e le tuple Struct

Poiché le tuple di riferimento e Struct Tuples hanno una rappresentazione sottostante completamente diversa, non sono convertibili in modo implicito.  Vale a dire, non verrà compilato il codice seguente:

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/interop.fsx#L5-L12)]

È necessario criteri di corrispondenza per una tupla e costruire l'altro con le parti costituenti.  Ad esempio:

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/interop.fsx#L18-L22)]

## <a name="compiled-form-of-reference-tuples"></a>Formato compilato di tuple di riferimento

Questa sezione illustra la forma di tuple quando essi è compilati.  Le informazioni qui non sono necessari per la lettura a meno che non si usa .NET Framework 3.5 o inferiore.

Le tuple vengono compilate in oggetti di uno dei vari tipi generici, tutte il nome `System.Tuple`, che sono sottoposti a overload in grado o sul numero di parametri di tipo. Tipi di tupla appaiono in questa forma quando vengono visualizzati da un altro linguaggio, ad esempio C# o Visual Basic, o quando si utilizza uno strumento che non è a conoscenza di F# costruisce. Il `Tuple` tipi sono stati introdotti in .NET Framework 4. Se la destinazione è una versione precedente di .NET Framework, il compilatore Usa le versioni di [System. Tuple](https://msdn.microsoft.com/library/5ac7953d-acdc-4a58-bfb7-c1f6406c0fa3) dalla versione 2.0 del F# libreria di base. I tipi in questa raccolta vengono utilizzati solo per le applicazioni che usano la versione 2.0, 3.0 e 3.5 versioni di .NET Framework. L'inoltro dei tipi viene usato per garantire la compatibilità binaria tra .NET Framework 2.0 e .NET Framework 4 F# componenti.

### <a name="compiled-form-of-struct-tuples"></a>Formato compilato di tuple di Struct

Le tuple struct (ad esempio, `struct (x, y)`), sono fondamentalmente diversi da tuple di riferimento.  Vengono compilate nel <xref:System.ValueTuple> tipo, sottoposti a overload da arietà o il numero di parametri di tipo.  Queste saranno equivalenti a [tuple in c# 7.0](../../csharp/tuples.md) e [tuple di Visual Basic 2017](../../visual-basic/programming-guide/language-features/data-types/tuples.md)e l'interoperabilità bidirezionale.

## <a name="see-also"></a>Vedere anche

- [Riferimenti per il linguaggio F#](index.md)
- [Tipi F#](fsharp-types.md)