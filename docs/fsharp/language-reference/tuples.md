---
title: Tuple (F#)
description: 'Informazioni su F # tupla, un raggruppamento di valori senza nome ma ordinati, tipi potenzialmente diversi.'
keywords: visual f#, f#, programmazione funzionale
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 35069073-9a82-410f-8dea-912e2a152e6d
ms.openlocfilehash: e0a5e5eb08e13bd5cbe9f88a47d4cf4bba19ea22
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="tuples"></a>Tuple

Oggetto *tupla* è un raggruppamento di valori senza nome ma ordinati, tipi potenzialmente diversi.  Tuple possono essere tipi di riferimento o struct.

## <a name="syntax"></a>Sintassi

```fsharp
(element, ... , element)
struct(element, ... ,element )
```
## <a name="remarks"></a>Note
Ogni *elemento* nella sintassi precedente può essere qualsiasi espressione valida di F #.

## <a name="examples"></a>Esempi
Sono esempi di tuple coppie, Triple e così via, di tipo stesso o diversi. Alcuni esempi sono illustrati nel codice seguente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L6-L21)]
    
## <a name="obtaining-individual-values"></a>Recupero di singoli valori
È possibile utilizzare criteri di ricerca per accedere e assegnare i nomi degli elementi di tupla, come illustrato nel codice seguente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L27-L29)]

È anche possibile annullare una tupla tramite criteri di ricerca di fuori di un `match` espressione tramite `let` associazione:

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L34-L37)]

O creare una serie di corrispondenza tuple come input per le funzioni:

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L43-L47)]

Se è necessario un solo elemento della tupla, è possibile utilizzare il carattere jolly (carattere di sottolineatura) per evitare di creare un nuovo nome per un valore che non è necessario.

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L53-L54)]

È inoltre semplice copia di elementi da una tupla di riferimento in una tupla di struct:

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L62-L66)]

Le funzioni `fst` e `snd` (fare riferimento solo tuple) restituiscono il primo e secondo elemento di una tupla, rispettivamente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L72-L73)]

Non vi è alcuna funzione predefinita che restituisce il terzo elemento di una tripla, ma è possibile scrivere facilmente uno come indicato di seguito.

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L78-L78)]

In genere, si consiglia di utilizzare criteri di ricerca per accedere agli elementi di tupla individuali.

## <a name="using-tuples"></a>Utilizzo di tuple
Le tuple offrono un modo pratico per restituire più valori da una funzione, come illustrato nell'esempio seguente. In questo esempio esegue la divisione di interi e restituisce il risultato arrotondato dell'operazione come primo membro di una coppia di tupla e il resto come secondo membro della coppia.

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L83-L86)]

Tuple anche essere utilizzate come argomenti della funzione quando si desidera evitare il currying implicito gli argomenti della funzione è implicita la normale sintassi della funzione.

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L88-L88)]

La sintassi comune per definire la funzione `let sum a b = a + b` consente di definire una funzione che è l'applicazione parziale del primo argomento della funzione, come illustrato nel codice seguente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L90-L94)]

L'utilizzo di una tupla come parametro Disattiva currying. Per ulteriori informazioni, vedere "Applicazione parziale di argomenti" in [funzioni](functions/index.md).

## <a name="names-of-tuple-types"></a>Nomi dei tipi di tupla
Quando si scrive il nome di un tipo che è una tupla, utilizzare il `*` simbolo per separare gli elementi. Per una tupla costituita da un `int`, un `float`e un `string`, ad esempio `(10, 10.0, "ten")`, il tipo verrebbe scritto come indicato di seguito.

```fsharp
int * float * string
```

## <a name="interoperation-with-c-tuples"></a>Interoperabilità con c# Tuple

C# 7.0 introdotti tuple per la lingua.  Le tuple in c# sono strutture e sono equivalenti alle tuple struct in F #.  Se è necessario interoperare con c#, è necessario utilizzare tuple struct.

Si tratta di un'operazione semplice.  Si supponga, ad esempio, che è necessario passare una tupla a una classe c# e quindi utilizzare il risultato, che è anche una tupla:

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

Nel codice F #, è quindi possibile passare una tupla di struttura come parametro e utilizzare il risultato come una tupla di struct.

```fsharp
open TupleInterop

let struct (newX, newY) = Example.AddOneToXAndY(struct (1, 2))
// newX is now 2, and newY is now 3
```

### <a name="converting-between-reference-tuples-and-struct-tuples"></a>La conversione tra le tuple di riferimento e Struct Tuple

Le tuple di riferimento e Struct Tuples dispone di una rappresentazione sottostante completamente diversa, pertanto non sono convertibili in modo implicito.  Ovvero, non verrà compilato il codice seguente:

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/interop.fsx#L5-L12)]

È necessario criteri di corrispondenza per una tupla e costruire l'altro con le parti costitutive.  Ad esempio:

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/interop.fsx#L18-L22)]

## <a name="compiled-form-of-reference-tuples"></a>Form compilato di tuple di riferimento
Questa sezione viene illustrato il formato di tuple quando essi è compilati.  Le informazioni riportate di seguito non sono necessaria per leggere, a meno che la destinazione di .NET Framework 3.5 o inferiore.

Le tuple vengono compilate in oggetti di uno dei vari tipi generici, tutti i `System.Tuple`, che sono sottoposti a overload in grado o sul numero di parametri di tipo. Tipi di tupla vengono visualizzati in questo modulo quando visualizzati da un altro linguaggio, ad esempio c# o Visual Basic, o quando si utilizza uno strumento che non è a conoscenza dei costrutti di F #. Il `Tuple` tipi sono stati introdotti in .NET Framework 4. Se la destinazione è una versione precedente di .NET Framework, il compilatore utilizza le versioni di [System. Tuple](https://msdn.microsoft.com/library/5ac7953d-acdc-4a58-bfb7-c1f6406c0fa3) dalla versione 2.0 della libreria di base F #. I tipi in questa libreria vengono utilizzati solo per le applicazioni destinate a 2.0, 3.0 e 3.5 versioni di .NET Framework. Inoltro dei tipi viene usato per garantire la compatibilità binaria tra i componenti di .NET Framework 2.0 e .NET Framework 4 F #.

### <a name="compiled-form-of-struct-tuples"></a>Form compilato di tuple Struct

Struct Tuple (ad esempio, `struct (x, y)`), sono completamente diversi da tuple di riferimento.  Vengono compilate nel <xref:System.ValueTuple> tipo, dal grado, o il numero di parametri di tipo di overload.  Sono equivalenti a [c# 7.0 Tuple](../../csharp/tuples.md) e [Visual Basic 2017 Tuple](../../visual-basic/programming-guide/language-features/data-types/tuples.md)e interagire in modalità bidirezionale.

## <a name="see-also"></a>Vedere anche
[Riferimenti per il linguaggio F#](index.md)

[Tipi F#](fsharp-types.md)
