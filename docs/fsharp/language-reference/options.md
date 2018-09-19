---
title: Opzioni (F#)
description: 'Informazioni su come utilizzare F # opzione tipi quando un valore effettivo potrebbero non essere presente per una variabile o un valore denominato.'
ms.date: 05/16/2016
ms.openlocfilehash: 0859cb42e72ef9e67551b884f5cf6130fb099a78
ms.sourcegitcommit: f513a91160b3fec289dd06646d0d6f81f8fcf910
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/18/2018
ms.locfileid: "46287936"
---
# <a name="options"></a>Opzioni

Il tipo di opzione in F # viene utilizzato quando un valore effettivo non potrebbero essere disponibili per una variabile o un valore denominato. Un'opzione ha un tipo sottostante e può contenere un valore di quel tipo, o potrebbe non contenere un valore.

## <a name="remarks"></a>Note

Il codice seguente illustra una funzione che genera un tipo di opzione.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1404.fs)]

Come può notare, se l'input `a` è maggiore di 0 `Some(a)` viene generato.  In caso contrario, `None` viene generato.

Il valore `None` viene utilizzato quando un'opzione non ha un valore effettivo. In caso contrario, l'espressione `Some( ... )` offre la possibilità di un valore. I valori `Some` e `None` sono utili nei criteri di ricerca, come la funzione seguente `exists`, che restituisce `true` se l'opzione non ha un valore e `false` se non esiste.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1401.fs)]

## <a name="using-options"></a>Utilizzo delle opzioni

Le opzioni sono comunemente usate durante una ricerca non restituisce un risultato corrispondente, come illustrato nel codice seguente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1403.fs)]

Nel codice precedente, un elenco viene effettuata in modo ricorsivo. La funzione `tryFindMatch` accetta una funzione di predicato `pred` che restituisce un valore booleano e un elenco per la ricerca. Se viene trovato un elemento che soddisfa il predicato, le entità finali di ricorsione e la funzione restituisce il valore come un'opzione nell'espressione `Some(head)`. La ricorsione termina quando esiste una corrispondenza per l'elenco vuoto. A questo punto il valore `head` non è stato trovato, e `None` viene restituito.

Molte F # funzioni della libreria in cui la ricerca di una raccolta per un valore che può esistere o meno non restituiscono il `option` tipo. Per convenzione, queste funzioni iniziano con la `try` prefisso, ad esempio [ `Seq.tryFindIndex` ](https://msdn.microsoft.com/library/c357b221-edf6-4f68-bf40-82a3156d945a).

Opzioni possono essere utile anche quando un valore potrebbe non esistere, ad esempio se è possibile che venga generata un'eccezione quando si tenta di costruire un valore. Questo aspetto è illustrato nell'esempio di codice seguente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1402.fs)]

Il `openFile` funzione nell'esempio precedente è di tipo `string -> File option` perché restituisce un `File` dell'oggetto se il file viene aperto correttamente e `None` se si verifica un'eccezione. A seconda della situazione, potrebbe non essere una scelta appropriata per intercettare un'eccezione anziché consentirne la propagazione.

## <a name="option-properties-and-methods"></a>I metodi e le proprietà delle opzioni

Il tipo di opzione supporta le proprietà e i metodi seguenti.

|Proprietà o metodo|Tipo|Descrizione|
|------------------|----|-----------|
|[None](https://msdn.microsoft.com/library/83ef260a-aa33-4e6f-aee6-b9bf0a461476)|`'T option`|Una proprietà statica che consente di creare un valore di opzione con il `None` valore.|
|[IsNone](https://msdn.microsoft.com/library/f08532ca-1716-4f60-ae59-8ef6256df234)|`bool`|Restituisce `true` se l'opzione ha il `None` valore.|
|[IsSome](https://msdn.microsoft.com/library/c5088d51-c5d7-425f-a77f-12c379bb356f)|`bool`|Restituisce `true` se l'opzione ha un valore che non è `None`.|
|[Alcuni](https://msdn.microsoft.com/library/12f048d2-e293-4596-accb-de036ecd63fc)|`'T option`|Un membro statico che crea un'opzione che ha un valore che non è `None`.|
|[Valore](https://msdn.microsoft.com/library/c79f68e8-11fd-45b1-a053-e8fc38b56df7)|`'T`|Restituisce il valore sottostante oppure genera una `System.NullReferenceException` se il valore è `None`.|

## <a name="option-module"></a>Modulo Option

È disponibile un modulo [opzione](https://msdn.microsoft.com/library/e615e4d3-bbbb-49ba-addc-6061ea2e2f4c), che contiene funzioni utili che eseguono operazioni nelle opzioni. Alcune funzioni di ripetono la funzionalità delle proprietà, ma sono utili nei contesti in cui è necessaria una funzione. [Option. isSome](https://msdn.microsoft.com/library/41ad0857-5672-4326-84b5-c33dc43dcf79) e [Option. IsNone](https://msdn.microsoft.com/library/73db6a53-15e7-40a6-94f9-a0049e5f4819) sono entrambe le funzioni del modulo che verificano se un'opzione non contiene un valore. [Option. Get](https://msdn.microsoft.com/library/803e9fcb-6edd-4910-808c-25f08cbc55ea) Ottiene il valore, se presente. Se è presente alcun valore, viene generata `System.ArgumentException`.

Il [Bind](https://msdn.microsoft.com/library/c3406192-24ac-49b5-bc3b-8f805187f1c0) funzione esegue una funzione sul valore, se è presente un valore. La funzione deve accettare esattamente un solo argomento e il tipo di parametro deve essere il tipo di opzione. Il valore restituito della funzione è un altro tipo di opzione.

Il modulo option include anche funzioni che corrispondono alle funzioni disponibili per gli elenchi, matrici, le sequenze e altri tipi di raccolta. Queste funzioni includono [ `Option.map` ](https://msdn.microsoft.com/library/91a20385-7e73-40c2-9adc-635e86d6a622), [ `Option.iter` ](https://msdn.microsoft.com/library/83389eef-3dff-4074-b4cc-f69581c25191), [ `Option.forall` ](https://msdn.microsoft.com/library/ba884586-5eae-49c5-9e36-05481c1c3428), [ `Option.exists` ](https://msdn.microsoft.com/library/a606d2d4-fddc-4eab-ab37-c6138fb7ad99), [ `Option.foldBack` ](https://msdn.microsoft.com/library/a882fbaf-c019-46f0-b4f5-b8c2b8b90ffb), [ `Option.fold` ](https://msdn.microsoft.com/library/af896794-3d53-406c-9411-316cd5c33ad8), e [ `Option.count` ](https://msdn.microsoft.com/library/2dac83a9-684e-4d0f-b50e-ff722a8bb876). Queste funzioni abilitare le opzioni da utilizzare, ad esempio una raccolta di zero o un elemento. Per altre informazioni ed esempi, vedere la discussione delle funzioni di raccolta nella [Elenca](lists.md).

## <a name="converting-to-other-types"></a>Conversione in altri tipi

Le opzioni possono essere convertite in elenchi o matrici. Quando un'opzione viene convertita in una di queste strutture di dati, la struttura di dati risultante è zero o un elemento. Per convertire un'opzione in una matrice, usare [ `Option.toArray` ](https://msdn.microsoft.com/library/c8044873-ba17-4b52-8231-eb1a28318c64). Per convertire un'opzione in un elenco, usare [ `Option.toList` ](https://msdn.microsoft.com/library/5f1af295-9fa9-40ad-b4a1-3578d94d44e1).

## <a name="see-also"></a>Vedere anche

- [Riferimenti per il linguaggio F#](index.md)
- [Tipi F#](fsharp-types.md)
