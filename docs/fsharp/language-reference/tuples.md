---
title: Tuple
description: 'Informazioni sulla tupla F #, un raggruppamento di valori senza nome ma ordinati, possibilmente di tipi diversi.'
ms.date: 05/16/2016
ms.openlocfilehash: 5d26fd5d7ec5b4939a895a6d2a6a0d7fc6c6c733
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2020
ms.locfileid: "86173289"
---
# <a name="tuples"></a>Tuple

Una *tupla* è un raggruppamento di valori senza nome ma ordinati, possibilmente di tipi diversi.  Le tuple possono essere tipi o struct di riferimento.

## <a name="syntax"></a>Sintassi

```fsharp
(element, ... , element)
struct(element, ... ,element )
```

## <a name="remarks"></a>Osservazioni

Ogni *elemento* della sintassi precedente può essere qualsiasi espressione F # valida.

## <a name="examples"></a>Esempi

Esempi di Tuple includono coppie, triple e così via, dello stesso tipo o di tipi diversi. Nel codice riportato di seguito sono illustrati alcuni esempi.

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L6-L21)]

## <a name="obtaining-individual-values"></a>Recupero di singoli valori

È possibile utilizzare criteri di ricerca per accedere e assegnare nomi per gli elementi di tupla, come illustrato nel codice seguente.

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L27-L29)]

È anche possibile decostruire una tupla tramite criteri di ricerca all'esterno di un' `match` espressione tramite `let` Binding:

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L34-L37)]

In alternativa, è possibile modellare le corrispondenze sulle tuple come input per le funzioni:

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L43-L47)]

Se è necessario un solo elemento della tupla, è possibile usare il carattere jolly (il carattere di sottolineatura) per evitare di creare un nuovo nome per un valore che non è necessario.

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L53-L54)]

Anche la copia di elementi da una tupla di riferimento in una tupla di struct è semplice:

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L62-L66)]

Le funzioni `fst` e `snd` (solo tuple di riferimento) restituiscono rispettivamente il primo e il secondo elemento di una tupla.

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L72-L73)]

Non esiste alcuna funzione incorporata che restituisce il terzo elemento di un triplo, ma è possibile scriverne facilmente uno come segue.

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L78-L78)]

In genere, è preferibile usare i criteri di ricerca per accedere ai singoli elementi della tupla.

## <a name="using-tuples"></a>Utilizzo di Tuple

Le tuple rappresentano un modo pratico per restituire più valori da una funzione, come illustrato nell'esempio seguente. In questo esempio viene eseguita la divisione di interi e viene restituito il risultato arrotondato dell'operazione come primo membro di una coppia di tuple e il resto come un secondo membro della coppia.

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L83-L86)]

Le tuple possono essere utilizzate anche come argomenti della funzione quando si desidera evitare il currying implicito degli argomenti della funzione che è implicito nella sintassi della funzione usuale.

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L88-L88)]

La sintassi consueta per la definizione della funzione `let sum a b = a + b` consente di definire una funzione che rappresenta l'applicazione parziale del primo argomento della funzione, come illustrato nel codice seguente.

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L90-L94)]

Se si usa una tupla come parametro, il currying viene disabilitato. Per ulteriori informazioni, vedere la sezione relativa all'applicazione parziale degli argomenti in [Functions](./functions/index.md).

## <a name="names-of-tuple-types"></a>Nomi dei tipi di tupla

Quando si scrive il nome di un tipo che è una tupla, si usa il `*` simbolo per separare gli elementi. Per una tupla costituita da un oggetto `int` , un oggetto `float` e un oggetto `string` , ad esempio `(10, 10.0, "ten")` , il tipo viene scritto come indicato di seguito.

```fsharp
int * float * string
```

## <a name="interoperation-with-c-tuples"></a>Interoperabilità con Tuple C#

C# 7,0 ha introdotto le tuple nel linguaggio.  Le tuple in C# sono struct e sono equivalenti alle tuple struct in F #.  Se è necessario interagire con C#, è necessario usare le tuple struct.

Questa operazione è facile.  Si supponga, ad esempio, di dover passare una tupla a una classe C# e quindi utilizzare il risultato, che è anche una tupla:

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

Nel codice F # è quindi possibile passare una tupla struct come parametro e utilizzare il risultato come tupla struct.

```fsharp
open TupleInterop

let struct (newX, newY) = Example.AddOneToXAndY(struct (1, 2))
// newX is now 2, and newY is now 3
```

### <a name="converting-between-reference-tuples-and-struct-tuples"></a>Conversione tra tuple di riferimento e Tuple di struct

Poiché le tuple di riferimento e le tuple struct hanno una rappresentazione sottostante completamente diversa, non sono convertibili in modo implicito.  Ovvero, il codice come il seguente non verrà compilato:

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/interop.fsx#L5-L12)]

È necessario definire la corrispondenza in una tupla e costruire l'altra con le parti costituenti.  Ad esempio:

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/interop.fsx#L18-L22)]

## <a name="compiled-form-of-reference-tuples"></a>Forma compilata di tuple di riferimento

In questa sezione viene illustrata la forma delle tuple quando vengono compilate.  Le informazioni non sono necessarie per la lettura, a meno che la destinazione non sia .NET Framework 3,5 o inferiore.

Le tuple vengono compilate in oggetti di uno dei diversi tipi generici, tutti denominati `System.Tuple` , che sono sottoutilizzati per il grado o il numero di parametri di tipo. I tipi di tupla vengono visualizzati in questo formato quando vengono visualizzati da un altro linguaggio, ad esempio C# o Visual Basic, oppure quando si utilizza uno strumento che non è in grado di riconoscere i costrutti F #. I `Tuple` tipi sono stati introdotti in .NET Framework 4. Se la destinazione è una versione precedente del .NET Framework, il compilatore usa le versioni di [System. Tuple](https://msdn.microsoft.com/library/5ac7953d-acdc-4a58-bfb7-c1f6406c0fa3) dalla versione 2,0 della libreria di base F #. I tipi in questa libreria vengono usati solo per le applicazioni destinate alle versioni 2,0, 3,0 e 3,5 del .NET Framework. L'invio dei tipi viene usato per garantire la compatibilità binaria tra i componenti .NET Framework 2,0 e .NET Framework 4 F #.

### <a name="compiled-form-of-struct-tuples"></a>Forma compilata di Tuple struct

Le tuple struct (ad esempio, `struct (x, y)` ) sono fondamentalmente diverse dalle tuple di riferimento.  Sono compilati nel <xref:System.ValueTuple> tipo, in overload per grado o nel numero di parametri di tipo.  Sono equivalenti a [Tuple C# 7,0](../../csharp/language-reference/builtin-types/value-tuples.md) e [Visual Basic Tuple 2017](../../visual-basic/programming-guide/language-features/data-types/tuples.md)e interoperano in modo bidirezionale.

## <a name="see-also"></a>Vedere anche

- [Riferimenti per il linguaggio F #](index.md)
- [Tipi F#](fsharp-types.md)
