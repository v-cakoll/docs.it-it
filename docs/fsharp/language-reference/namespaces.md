---
title: Spazi dei nomi (F#)
description: 'Informazioni su come uno spazio dei nomi in F # consente di organizzare il codice in aree di funzionalità correlate, consentendo di collegare un nome a un raggruppamento di elementi del programma.'
ms.date: 04/24/2017
ms.openlocfilehash: 151079864f18fff79dac108889b68b3acf1566a1
ms.sourcegitcommit: 88f251b08bf0718ce119f3d7302f514b74895038
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/10/2018
ms.locfileid: "33957762"
---
# <a name="namespaces"></a>Spazi dei nomi

Uno spazio dei nomi consente di organizzare il codice in aree di funzionalità correlate perché consente di collegare un nome a un raggruppamento di elementi di programma.


## <a name="syntax"></a>Sintassi

```fsharp
namespace [parent-namespaces.]identifier
```

## <a name="remarks"></a>Note
Se si desidera inserire il codice in uno spazio dei nomi, la prima dichiarazione nel file deve dichiarare lo spazio dei nomi. Il contenuto dell'intero file diventa quindi parte dello spazio dei nomi.

Spazi dei nomi non può contenere direttamente le funzioni e valori. Invece, funzioni e i valori devono essere inclusi nei moduli e sono inclusi negli spazi dei nomi. Spazi dei nomi può contenere tipi di moduli.

Spazi dei nomi possono essere dichiarate in modo esplicito con la parola chiave dello spazio dei nomi o in modo implicito quando si dichiara un modulo. Per dichiarare uno spazio dei nomi in modo esplicito, utilizzare la parola chiave dello spazio dei nomi seguita dal nome dello spazio dei nomi. Nell'esempio seguente viene illustrato un file di codice che dichiara uno spazio dei nomi widget con un tipo e un modulo incluso nello spazio dei nomi.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6406.fs)]

Se l'intero contenuto del file in un modulo, è inoltre possibile dichiarare spazi dei nomi in modo implicito tramite il `module` (parola chiave) e fornendo il nuovo nome dello spazio dei nomi nel nome del modulo completo. Nell'esempio seguente viene illustrato un file di codice che dichiara uno spazio dei nomi `Widgets` e un modulo `WidgetsModule`, che contiene una funzione.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6401.fs)]

Il codice seguente equivale a quello precedente, ma il modulo è una dichiarazione di modulo locale. In tal caso, lo spazio dei nomi deve essere presente nella propria riga.

[!code-fsharp[Main](../../../samples/snippets/fsharp/namespaces/snippet6402.fs)]

Se nello stesso file in uno o più spazi, è necessaria più di un modulo, è necessario utilizzare le dichiarazioni di modulo locale. Quando si utilizzano dichiarazioni di modulo locali, è possibile utilizzare lo spazio dei nomi completo nelle dichiarazioni di modulo. Il codice seguente viene illustrato un file con una dichiarazione dello spazio dei nomi e due dichiarazioni di modulo locale. In questo caso, i moduli sono contenuti direttamente nello spazio dei nomi; non vi è alcun modulo creato in modo implicito con lo stesso nome del file. Qualsiasi altro codice nel file, ad esempio un `do` l'associazione, è nello spazio dei nomi ma non nei moduli interni, pertanto è necessario qualificare il membro modulo `widgetFunction` utilizzando il nome del modulo.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6403.fs)]

L'output di questo esempio è come indicato di seguito.

```fsharp
Module1 10 20
Module2 5 6
```

Per ulteriori informazioni, vedere [moduli](modules.md).

## <a name="nested-namespaces"></a>Spazi dei nomi annidati
Quando si crea uno spazio dei nomi annidato, è necessario specificarla. In caso contrario, si crea un nuovo spazio dei nomi di primo livello. Rientro viene ignorato nelle dichiarazioni dello spazio dei nomi.

Nell'esempio seguente viene illustrato come dichiarare uno spazio dei nomi annidato.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6404.fs)]

## <a name="namespaces-in-files-and-assemblies"></a>Spazi dei nomi di file e assembly
Spazi dei nomi può estendersi su più file in un singolo progetto o di una compilazione. Il termine *frammento dello spazio dei nomi* descrive la parte di uno spazio dei nomi che è incluso in un file. Spazi dei nomi può occupare più assembly. Ad esempio, il `System` spazio dei nomi include l'intero .NET Framework, si estende su molti assembly che contiene molti spazi dei nomi annidati.


## <a name="global-namespace"></a>Namespace globale
Lo spazio dei nomi predefiniti `global` per inserire i nomi dello spazio dei nomi principali di .NET.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6407.fs)]

È possibile inoltre utilizzare globale per fare riferimento il primo livello dello spazio dei nomi .NET, ad esempio, per risolvere i conflitti di nome con altri spazi dei nomi.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6408.fs)]

## <a name="recursive-namespaces"></a>Spazi dei nomi ricorsiva

F # 4.1 introduce la nozione di spazi dei nomi che consentono di tutto il codice indipendente reciprocamente sono ricorsivi.  Questa operazione viene eseguita tramite `namespace rec`.  Utilizzo di `namespace rec` possibile tentare di risolvere alcune difficoltà in non è in grado di scrivere codice reciprocamente referenziale tra i tipi e i moduli.  Di seguito è riportato un esempio di questo oggetto:

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

Si noti che l'eccezione `DontSqueezeTheBananaException` e la classe `Banana` fanno riferimento a altro.  Inoltre, il modulo `BananaHelpers` e la classe `Banana` anche fare riferimento a altro.  Ciò non sarebbe possibile esprimere in F #, se è stato rimosso il `rec` (parola chiave) dal `MutualReferences` dello spazio dei nomi.

Questa funzionalità è anche disponibile per primo livello [moduli](modules.md) in F # 4.1 o versione successiva.

## <a name="see-also"></a>Vedere anche
[Riferimenti per il linguaggio F#](index.md)

[Moduli](modules.md)

[1009-F # RFC Fi - Consenti moduli e tipi reciprocamente referenziali su maggiori ambiti all'interno dei file](https://github.com/fsharp/fslang-design/blob/master/FSharp-4.1/FS-1009-mutually-referential-types-and-modules-single-scope.md)
