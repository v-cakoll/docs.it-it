---
title: Estensioni di tipo (F#)
description: 'Informazioni su come estensioni di tipo F # consentono che aggiungere nuovi membri a un tipo di oggetto definita in precedenza.'
keywords: visual f#, f#, programmazione funzionale
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: c9d7ce27-f5ad-4766-b9e9-34187da5bc24
ms.openlocfilehash: f78f8689e95fc1547f1a2b17c615592c00051f7c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="type-extensions"></a>Estensioni di tipo

Le estensioni di tipo consentono di aggiungere nuovi membri a un tipo di oggetto definita in precedenza.

## <a name="syntax"></a>Sintassi

```fsharp
// Intrinsic extension.
type typename with
    member self-identifier.member-name =
        body
    ...
[ end ]

// Optional extension.
type typename with
    member self-identifier.member-name =
        body
    ...
[ end ]
```

## <a name="remarks"></a>Note
Esistono due tipi di estensioni di tipo che presentano comportamenti e sintassi leggermente diversa. Un *estensione intrinseca* è un'estensione che viene visualizzata nello stesso spazio dei nomi o modulo, nello stesso file di origine e nello stesso assembly (DLL o file eseguibile) del tipo esteso. Un *estensione facoltativa* è un'estensione che viene visualizzata all'esterno dello spazio dei nomi, modulo o assembly del tipo esteso originale. Le estensioni intrinseche appaiono sul tipo quando il tipo viene esaminato tramite reflection, ma non le estensioni facoltative. Le estensioni facoltative devono trovarsi nei moduli e sono solo nell'ambito quando il modulo che contiene l'estensione è aperto.

Nella sintassi precedente, *typename* rappresenta il tipo da estendere. È possibile estendere qualsiasi tipo che è possibile accedere, ma il nome del tipo deve essere un nome di tipo effettivo, non è un'abbreviazione di tipo. È possibile definire più membri in un'estensione del tipo. Il *autoidentificatore* rappresenta l'istanza dell'oggetto, come membri ordinari in cui viene richiamato.

Il `end` parola chiave è facoltativa nella sintassi leggera.

Membri definiti nelle estensioni di tipo possono essere utilizzati come gli altri membri in un tipo di classe. Analogamente agli altri membri, possono essere statici o membri di istanza. Questi metodi sono noti anche come *metodi di estensione*; proprietà sono note come *le proprietà di estensione*e così via. Membri di estensione facoltative vengono compilati per i membri statici per il quale l'istanza dell'oggetto viene passata in modo implicito come primo parametro. Tuttavia, funzionano come se fossero membri di istanza o i membri statici in base alla modalità di dichiarazione. I membri impliciti delle estensioni sono inclusi come membri del tipo e possono essere utilizzati senza alcuna restrizione.

Metodi di estensione non possono essere metodi virtuali o astratti. È possibile eseguire l'overload di altri metodi con lo stesso nome, ma il compilatore assegna la priorità per i metodi di estensione nel caso di una chiamata ambigua.

In presenza di più estensioni di tipo intrinseco per un tipo, tutti i membri devono essere univoci. Per le estensioni di tipo facoltativi, i membri di diverse estensioni di tipo nello stesso tipo possono avere gli stessi nomi. Solo se il codice client apre due ambiti diversi che definiscono gli stessi nomi di membro, si verificano errori di ambiguità.

Nell'esempio seguente, un tipo in un modulo ha un'estensione di tipo intrinseco. Al codice client di fuori del modulo, l'estensione del tipo viene visualizzato come un membro regolare del tipo per tutti gli aspetti.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet3701.fs)]

È possibile utilizzare le estensioni di tipo intrinseco di separare la definizione di un tipo in sezioni. Può essere utile nella gestione delle definizioni di tipi di grandi dimensioni, ad esempio, per separare generato dal compilatore di codice e codice creato o per raggruppare il codice creato da persone diverse o associata a una funzionalità diversa.

Nell'esempio seguente, un'estensione di tipo facoltativi estende il `System.Int32` tipo con un metodo di estensione `FromString` che chiama il membro statico `Parse`. Il `testFromString` metodo dimostra che il nuovo membro viene chiamato come qualsiasi membro di istanza.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet3702.fs)]

Verrà visualizzato il nuovo membro di istanza come qualsiasi altro metodo del `Int32` tipo IntelliSense, ma solo quando il modulo che contiene l'estensione è aperto o in caso contrario nell'ambito.

## <a name="generic-extension-methods"></a>Metodi di estensione generico
Prima di F # 3.1, il compilatore F # non supporta l'uso di c#-metodi di estensione con una variabile di tipo generico, tipo di matrice, il tipo di tupla o un tipo di funzione F # come "this" parametro di stile. 3.1 F # supporta l'utilizzo di questi membri di estensione.

Nel codice F # 3.1, ad esempio, è possibile utilizzare i metodi di estensione con firme che sono simili alla sintassi seguente in c#:

```csharp
static member Method<T>(this T input, T other)
```

Questo approccio è particolarmente utile quando il parametro di tipo generico è vincolato. Inoltre, è possibile dichiarare i membri di estensione simile al seguente nel codice F # e definire un set aggiuntivi e semanticamente complesse di metodi di estensione. In F #, in genere è necessario definire i membri di estensione come illustrato nell'esempio seguente:

```fsharp
open System.Collections.Generic

type IEnumerable<'T> with
    /// Repeat each element of the sequence n times
    member xs.RepeatElements(n: int) =
        seq { for x in xs do for i in 1 .. n do yield x }
```

Tuttavia, per un tipo generico, la variabile di tipo potrebbe non essere vincolata. Sarà quindi possibile dichiarare c#-membro di estensione di stile in F # per aggirare questa limitazione. Quando si combina questo tipo di dichiarazione con la funzionalità di inline di F #, è possibile presentare algoritmi generici come membri di estensione.

Si consideri la seguente dichiarazione:

```fsharp
[<Extension>]
type ExtraCSharpStyleExtensionMethodsInFSharp () =
    [<Extension>]
    static member inline Sum(xs: IEnumerable<'T>) = Seq.sum xs
```

Tramite questa dichiarazione, è possibile scrivere codice simile al seguente esempio.

```fsharp
let listOfIntegers = [ 1 .. 100 ]
let listOfBigIntegers = [ 1I to 100I ]
let sum1 = listOfIntegers.Sum()
let sum2 = listOfBigIntegers.Sum()
```

In questo codice, lo stesso codice generico di aritmetico applicato agli elenchi di due tipi senza l'overload, definendo un membro unica estensione.


## <a name="see-also"></a>Vedere anche
[Riferimenti per il linguaggio F#](index.md)

[Membri](members/index.md)
