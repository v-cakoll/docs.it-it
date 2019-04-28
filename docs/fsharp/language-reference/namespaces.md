---
title: Spazi dei nomi
description: Informazioni su come un F# dello spazio dei nomi consente di organizzare il codice in aree di funzionalità correlate grazie alla possibilità di associare un nome a un raggruppamento di elementi di programma.
ms.date: 12/08/2018
ms.openlocfilehash: 526d7a07e4804751811c15fa91b0c74c1954d591
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61666391"
---
# <a name="namespaces"></a>Spazi dei nomi

Uno spazio dei nomi consente di organizzare il codice in aree di funzionalità correlate grazie alla possibilità di associare un nome a un raggruppamento di F# elementi del programma. Spazi dei nomi sono gli elementi in genere livello principale in F# file.

## <a name="syntax"></a>Sintassi

```fsharp
namespace [rec] [parent-namespaces.]identifier
```

## <a name="remarks"></a>Note

Se si desidera inserire il codice in uno spazio dei nomi, la prima dichiarazione nel file deve dichiarare lo spazio dei nomi. Il contenuto dell'intero file quindi diventano parte dello spazio dei nomi, purché nessun altra dichiarazione di spazi dei nomi esiste più nel file. Se è questo il caso, tutto il codice fino alla dichiarazione dello spazio dei nomi successivo viene considerato all'interno dello spazio dei nomi prima.

Gli spazi dei nomi non può contenere direttamente i valori e le funzioni. Al contrario, i valori e le funzioni devono essere inclusi nei moduli e i moduli sono inclusi negli spazi dei nomi. Gli spazi dei nomi può contenere tipi di moduli.

Commenti in formato documentazione XML possono essere dichiarati di sopra di uno spazio dei nomi, ma esso verrà ignorato. Le direttive del compilatore possono essere dichiarate anche di sopra di uno spazio dei nomi.

Gli spazi dei nomi possono essere dichiarate in modo esplicito con la parola chiave dello spazio dei nomi o in modo implicito quando si dichiara un modulo. Per dichiarare uno spazio dei nomi in modo esplicito, usare la parola chiave dello spazio dei nomi seguita dal nome dello spazio dei nomi. L'esempio seguente illustra un file di codice che dichiara uno spazio dei nomi `Widgets` con un tipo e un modulo incluso nello spazio dei nomi.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6406.fs)]

Se l'intero contenuto del file è in uno dei moduli, è anche possibile dichiarare gli spazi dei nomi in modo implicito usando la `module` (parola chiave) e fornendo il nuovo nome dello spazio dei nomi nel nome completo del modulo. L'esempio seguente illustra un file di codice che dichiara uno spazio dei nomi `Widgets` e un modulo `WidgetsModule`, che contiene una funzione.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6401.fs)]

Il codice seguente è equivalente al codice precedente, ma il modulo è una dichiarazione di modulo locale. In tal caso, lo spazio dei nomi deve essere visualizzato nella riga a sé stante.

[!code-fsharp[Main](../../../samples/snippets/fsharp/namespaces/snippet6402.fs)]

Se nello stesso file in uno o più spazi dei nomi è necessaria più di un modulo, è necessario usare le dichiarazioni di modulo locale. Quando si usano le dichiarazioni di modulo locale, è possibile usare lo spazio dei nomi qualificato nelle dichiarazioni di modulo. Il codice seguente illustra un file con una dichiarazione dello spazio dei nomi e due dichiarazioni di modulo locale. In questo caso, i moduli sono contenuti direttamente nello spazio dei nomi; non è disponibile alcun modulo creato in modo implicito con lo stesso nome del file. Qualsiasi altro codice nel file, ad esempio un `do` binding, è nello spazio dei nomi, ma non in moduli interni, pertanto è necessario qualificare i membri di modulo `widgetFunction` usando il nome del modulo.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6403.fs)]

L'output di questo esempio è come indicato di seguito.

```fsharp
Module1 10 20
Module2 5 6
```

Per altre informazioni, vedere [moduli](modules.md).

## <a name="nested-namespaces"></a>Spazi dei nomi annidati

Quando si crea uno spazio dei nomi annidato, è necessario specificarla. In caso contrario, si crea un nuovo spazio dei nomi di primo livello. Rientro viene ignorato nelle dichiarazioni dello spazio dei nomi.

Nell'esempio seguente viene illustrato come dichiarare uno spazio dei nomi annidato.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6404.fs)]

## <a name="namespaces-in-files-and-assemblies"></a>Spazi dei nomi nel file e assembly

Gli spazi dei nomi possono estendersi su più file in una compilazione o di singolo progetto. Il termine *frammento dello spazio dei nomi* descrive la parte di uno spazio dei nomi che è incluso in un unico file. Gli spazi dei nomi può anche estendersi su più assembly. Ad esempio, il `System` dello spazio dei nomi include l'intero .NET Framework, si estende su molti assembly che contiene molti spazi dei nomi annidati.

## <a name="global-namespace"></a>Global Namespace

Lo spazio dei nomi predefiniti `global` per inserire nomi nello spazio dei nomi di livello superiore di .NET.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6407.fs)]

È possibile inoltre utilizzare globali fanno riferimento a spazio dei nomi principale di .NET, ad esempio, per risolvere i conflitti di nome con altri spazi dei nomi.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6408.fs)]

## <a name="recursive-namespaces"></a>Spazi dei nomi ricorsiva

Gli spazi dei nomi possono anche essere dichiarate come ricorsiva per consentire tutto il codice indipendente si escludono a vicenda sono ricorsivi.  Questa operazione viene eseguita tramite `namespace rec`. Uso di `namespace rec` possibile tentare di risolvere alcune aree problematiche in cui non riesca a scrivere il codice si escludono a vicenda referenziali tra i tipi e i moduli. Di seguito è riportato un esempio:

```fsharp
namespace rec MutualReferences

type Orientation = Up | Down
type PeelState = Peeled | Unpeeled

// This exception depends on the type below.
exception DontSqueezeTheBananaException of Banana

type BananaPeel() = class end

type Banana(orientation : Orientation) =
    member val IsPeeled = false with get, set
    member val Orientation = orientation with get, set
    member val Sides: PeelState list = [ Unpeeled; Unpeeled; Unpeeled; Unpeeled] with get, set

    member self.Peel() = BananaHelpers.peel self // Note the dependency on the BananaHelpers module.
    member self.SqueezeJuiceOut() = raise (DontSqueezeTheBananaException self) // This member depends on the exception above.

module BananaHelpers =
    let peel (b: Banana) =
        let flip (banana: Banana) =
            match banana.Orientation with
            | Up -> 
                banana.Orientation <- Down
                banana
            | Down -> banana

        let peelSides (banana: Banana) =
            banana.Sides
            |> List.map (function
                         | Unpeeled -> Peeled
                         | Peeled -> Peeled)

        match b.Orientation with
        | Up ->   b |> flip |> peelSides
        | Down -> b |> peelSides
```

Si noti che l'eccezione `DontSqueezeTheBananaException` e la classe `Banana` entrambe fanno riferimento reciproco.  Inoltre, il modulo `BananaHelpers` e la classe `Banana` riferimento anche a altro. Ciò non sarebbe possibile esprimere F# se è stato rimosso il `rec` parola chiave dal `MutualReferences` dello spazio dei nomi.

Questa funzionalità è disponibile anche per primo livello [moduli](modules.md).

## <a name="see-also"></a>Vedere anche

- [Riferimenti per il linguaggio F#](index.md)
- [Moduli](modules.md)
- [F#RFC FS-1009 - Consenti moduli e tipi referenziali si escludono a vicenda su ambiti più ampi all'interno dei file](https://github.com/fsharp/fslang-design/blob/master/FSharp-4.1/FS-1009-mutually-referential-types-and-modules-single-scope.md)