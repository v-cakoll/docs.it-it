---
title: Opzioni
description: Informazioni su come usare F# i tipi di opzioni quando un valore effettivo potrebbe non esistere per un valore o una variabile denominata.
ms.date: 05/16/2016
ms.openlocfilehash: 9326cf04f53adac7422c09a49a59c4eecd49486d
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "68627357"
---
# <a name="options"></a>Opzioni

Il tipo di opzione F# in viene usato quando un valore effettivo potrebbe non esistere per un valore o una variabile denominata. Un'opzione ha un tipo sottostante e può contenere un valore di quel tipo o potrebbe non avere un valore.

## <a name="remarks"></a>Note

Nel codice seguente viene illustrata una funzione che genera un tipo di opzione.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1404.fs)]

Come si può notare, se l'input `a` è maggiore di 0, `Some(a)` viene generato.  In caso `None` contrario, viene generato.

Il valore `None` viene utilizzato quando un'opzione non dispone di un valore effettivo. In caso contrario, `Some( ... )` l'espressione assegna un valore all'opzione. I valori `Some` e `None` sono utili nella corrispondenza dei modelli, come nella funzione `exists`seguente, che restituisce `true` se l'opzione ha un valore e `false` in caso contrario.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1401.fs)]

## <a name="using-options"></a>Opzioni using

Le opzioni vengono in genere usate quando una ricerca non restituisce un risultato corrispondente, come illustrato nel codice seguente.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1403.fs)]

Nel codice precedente viene eseguita la ricerca in modo ricorsivo di un elenco. La funzione `tryFindMatch` accetta una funzione `pred` di predicato che restituisce un valore booleano e un elenco in cui eseguire la ricerca. Se viene trovato un elemento che soddisfa il predicato, la ricorsione termina e la funzione restituisce il valore come opzione nell' `Some(head)`espressione. La ricorsione termina quando viene confrontato l'elenco vuoto. A questo punto il valore `head` non è stato trovato e `None` viene restituito.

Molte F# funzioni di libreria che cercano un valore che può essere o meno presente in una raccolta restituiscono il `option` tipo. Per convenzione, queste funzioni iniziano con il `try` prefisso, ad [`Seq.tryFindIndex`](https://msdn.microsoft.com/library/c357b221-edf6-4f68-bf40-82a3156d945a)esempio.

Le opzioni possono inoltre essere utili quando un valore potrebbe non esistere, ad esempio se è possibile che venga generata un'eccezione quando si tenta di costruire un valore. Questo aspetto è illustrato nell'esempio di codice seguente.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1402.fs)]

La `openFile` funzione nell'esempio precedente è di tipo `string -> File option` perché restituisce un `File` oggetto se il file viene aperto correttamente e `None` se si verifica un'eccezione. A seconda della situazione, potrebbe non essere una scelta di progettazione appropriata per intercettare un'eccezione anziché consentire la propagazione.

Inoltre, è comunque possibile passare `null` o un valore null per il `Some` caso di un'opzione. Questa operazione viene in genere evitata e in genere si trova F# nella programmazione di routine, ma è possibile a causa della natura dei tipi di riferimento in .NET.

## <a name="option-properties-and-methods"></a>Metodi e proprietà delle opzioni

Il tipo di opzione supporta le proprietà e i metodi seguenti.

|Proprietà o metodo|Type|DESCRIZIONE|
|------------------|----|-----------|
|[None](https://msdn.microsoft.com/library/83ef260a-aa33-4e6f-aee6-b9bf0a461476)|`'T option`|Proprietà statica che consente di creare un valore di opzione con il `None` valore.|
|[IsNone](https://msdn.microsoft.com/library/f08532ca-1716-4f60-ae59-8ef6256df234)|`bool`|Restituisce `true` se l'opzione ha il `None` valore.|
|[IsSome](https://msdn.microsoft.com/library/c5088d51-c5d7-425f-a77f-12c379bb356f)|`bool`|Restituisce `true` se l'opzione ha un valore diverso `None`da.|
|[Alcuni](https://msdn.microsoft.com/library/12f048d2-e293-4596-accb-de036ecd63fc)|`'T option`|Membro statico che crea un'opzione con un valore diverso `None`da.|
|[Valore](https://msdn.microsoft.com/library/c79f68e8-11fd-45b1-a053-e8fc38b56df7)|`'T`|Restituisce il valore sottostante o genera un' `System.NullReferenceException` eccezione se il valore è. `None`|

## <a name="option-module"></a>Modulo Option

È disponibile un modulo, [Option](https://msdn.microsoft.com/library/e615e4d3-bbbb-49ba-addc-6061ea2e2f4c), che contiene funzioni utili che eseguono operazioni sulle opzioni. Alcune funzioni ripetono la funzionalità delle proprietà, ma sono utili nei contesti in cui è necessaria una funzione. [Option. di some](https://msdn.microsoft.com/library/41ad0857-5672-4326-84b5-c33dc43dcf79) e [Option. unnone](https://msdn.microsoft.com/library/73db6a53-15e7-40a6-94f9-a0049e5f4819) sono entrambe funzioni del modulo che verificano se un'opzione include un valore. [Option. Get](https://msdn.microsoft.com/library/803e9fcb-6edd-4910-808c-25f08cbc55ea) ottiene il valore, se presente. Se non è presente alcun valore, viene `System.ArgumentException`generata un'eccezione.

La funzione [Option. Bind](https://msdn.microsoft.com/library/c3406192-24ac-49b5-bc3b-8f805187f1c0) esegue una funzione sul valore, se è presente un valore. La funzione deve avere esattamente un argomento e il tipo di parametro deve essere il tipo di opzione. Il valore restituito della funzione è un altro tipo di opzione.

Il modulo Option include anche funzioni che corrispondono alle funzioni disponibili per elenchi, matrici, sequenze e altri tipi di raccolta. Queste funzioni includono [`Option.map`](https://msdn.microsoft.com/library/91a20385-7e73-40c2-9adc-635e86d6a622) [`Option.iter`](https://msdn.microsoft.com/library/83389eef-3dff-4074-b4cc-f69581c25191) [,,`Option.exists`](https://msdn.microsoft.com/library/a606d2d4-fddc-4eab-ab37-c6138fb7ad99) [,,`Option.foldBack`](https://msdn.microsoft.com/library/a882fbaf-c019-46f0-b4f5-b8c2b8b90ffb) [,`Option.count`](https://msdn.microsoft.com/library/2dac83a9-684e-4d0f-b50e-ff722a8bb876)e. [`Option.forall`](https://msdn.microsoft.com/library/ba884586-5eae-49c5-9e36-05481c1c3428) [`Option.fold`](https://msdn.microsoft.com/library/af896794-3d53-406c-9411-316cd5c33ad8) Queste funzioni consentono di usare le opzioni come una raccolta di zero o un elemento. Per ulteriori informazioni ed esempi, vedere la discussione sulle funzioni di raccolta negli [elenchi](lists.md).

## <a name="converting-to-other-types"></a>Conversione in altri tipi

Le opzioni possono essere convertite in elenchi o matrici. Quando un'opzione viene convertita in una di queste strutture di dati, la struttura dei dati risultante è costituita da zero o un elemento. Per convertire un'opzione in una matrice, usare [`Option.toArray`](https://msdn.microsoft.com/library/c8044873-ba17-4b52-8231-eb1a28318c64). Per convertire un'opzione in un elenco, usare [`Option.toList`](https://msdn.microsoft.com/library/5f1af295-9fa9-40ad-b4a1-3578d94d44e1).

## <a name="see-also"></a>Vedere anche

- [Riferimenti per il linguaggio F#](index.md)
- [Tipi F#](fsharp-types.md)
