---
title: Spazi dei nomi
description: 'Informazioni su come uno spazio dei nomi F # consente di organizzare il codice in aree di funzionalità correlate consentendo di alleghiare un nome a un raggruppamento di elementi di programma.'
ms.date: 12/08/2018
ms.openlocfilehash: bf71843349434a1ea91c58dbc0477373dbb0c449
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2020
ms.locfileid: "82796132"
---
# <a name="namespaces"></a>Spazi dei nomi

Uno spazio dei nomi consente di organizzare il codice in aree della funzionalità correlata consentendo di alleghiare un nome a un raggruppamento di elementi di programma F #. Gli spazi dei nomi sono in genere elementi di primo livello nei file F #.

## <a name="syntax"></a>Sintassi

```fsharp
namespace [rec] [parent-namespaces.]identifier
```

## <a name="remarks"></a>Osservazioni

Se si desidera inserire il codice in uno spazio dei nomi, la prima dichiarazione nel file deve dichiarare lo spazio dei nomi. Il contenuto dell'intero file diventa quindi parte dello spazio dei nomi, purché nel file non esistano altre dichiarazioni di spazi dei nomi. In tal caso, tutto il codice fino alla successiva dichiarazione dello spazio dei nomi viene considerato all'interno del primo spazio dei nomi.

Gli spazi dei nomi non possono contenere direttamente valori e funzioni. Al contrario, i valori e le funzioni devono essere inclusi nei moduli e i moduli sono inclusi negli spazi dei nomi. Gli spazi dei nomi possono contenere tipi, moduli.

I commenti in formato documentazione XML possono essere dichiarati sopra uno spazio dei nomi, ma sono ignorati. Le direttive del compilatore possono anche essere dichiarate sopra uno spazio dei nomi.

Gli spazi dei nomi possono essere dichiarati in modo esplicito con la parola chiave namespace o in modo implicito quando si dichiara un modulo. Per dichiarare uno spazio dei nomi in modo esplicito, usare la parola chiave namespace seguita dal nome dello spazio dei nomi. Nell'esempio seguente viene illustrato un file di codice che dichiara uno `Widgets` spazio dei nomi con un tipo e un modulo inclusi nello spazio dei nomi.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6406.fs)]

Se l'intero contenuto del file si trova in un modulo, è anche possibile dichiarare gli spazi dei nomi in modo implicito usando la `module` parola chiave e specificando il nuovo nome dello spazio dei nomi nel nome completo del modulo. Nell'esempio seguente viene illustrato un file di codice che dichiara uno `Widgets` spazio dei nomi `WidgetsModule`e un modulo che contiene una funzione.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6401.fs)]

Il codice seguente è equivalente a quello precedente, ma il modulo è una dichiarazione di modulo locale. In tal caso, lo spazio dei nomi deve essere visualizzato su una riga a parte.

[!code-fsharp[Main](~/samples/snippets/fsharp/namespaces/snippet6402.fs)]

Se è necessario più di un modulo nello stesso file in uno o più spazi dei nomi, è necessario usare le dichiarazioni di modulo locali. Quando si usano le dichiarazioni di modulo locali, non è possibile usare lo spazio dei nomi Qualified nelle dichiarazioni del modulo. Il codice seguente illustra un file con una dichiarazione dello spazio dei nomi e due dichiarazioni di modulo locali. In questo caso, i moduli sono contenuti direttamente nello spazio dei nomi; non esiste alcun modulo creato in modo implicito con lo stesso nome del file. Qualsiasi altro codice nel file, ad esempio un' `do` associazione, si trova nello spazio dei nomi ma non nei moduli interni, quindi è necessario qualificare il membro `widgetFunction` del modulo usando il nome del modulo.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6403.fs)]

L'output di questo esempio è il seguente.

```fsharp
Module1 10 20
Module2 5 6
```

Per ulteriori informazioni, vedere [moduli](modules.md).

## <a name="nested-namespaces"></a>Spazi dei nomi annidati

Quando si crea uno spazio dei nomi annidato, è necessario qualificarlo completamente. In caso contrario, viene creato un nuovo spazio dei nomi di primo livello. Il rientro viene ignorato nelle dichiarazioni dello spazio dei nomi.

Nell'esempio seguente viene illustrato come dichiarare uno spazio dei nomi annidato.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6404.fs)]

## <a name="namespaces-in-files-and-assemblies"></a>Spazi dei nomi in file e assembly

Gli spazi dei nomi possono estendersi su più file in un singolo progetto o compilazione. Il termine *frammento spazio dei nomi* descrive la parte di uno spazio dei nomi incluso in un file. Gli spazi dei nomi possono anche estendersi su più assembly. Ad esempio, lo `System` spazio dei nomi include l'intero .NET Framework, che si estende su molti assembly e contiene molti spazi dei nomi annidati.

## <a name="global-namespace"></a>Spazio dei nomi globale

Usare lo spazio dei `global` nomi predefinito per inserire i nomi nello spazio dei nomi di primo livello .NET.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6407.fs)]

È anche possibile usare Global per fare riferimento allo spazio dei nomi .NET di primo livello, ad esempio per risolvere i conflitti di nomi con altri spazi dei nomi.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6408.fs)]

## <a name="recursive-namespaces"></a>Spazi dei nomi ricorsivi

Gli spazi dei nomi possono anche essere dichiarati come ricorsivi per consentire a tutto il codice contenuto di essere ricorsivo a vicenda.  Questa operazione viene eseguita `namespace rec`tramite. L'uso `namespace rec` di può alleviare alcune problematiche nella mancata possibilità di scrivere codice reciprocamente referenziale tra tipi e moduli. Di seguito è riportato un esempio:

```fsharp
namespace rec MutualReferences

type Orientation = Up | Down
type PeelState = Peeled | Unpeeled

// This exception depends on the type below.
exception DontSqueezeTheBananaException of Banana

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

Si noti che l' `DontSqueezeTheBananaException` eccezione e la `Banana` classe fanno riferimento l'una all'altra.  Inoltre, il modulo `BananaHelpers` e la classe `Banana` fanno riferimento l'uno all'altro. Non sarebbe possibile esprimere in F # se la `rec` parola chiave è stata rimossa dallo `MutualReferences` spazio dei nomi.

Questa funzionalità è disponibile anche per i [moduli](modules.md)di livello superiore.

## <a name="see-also"></a>Vedere anche

- [Riferimenti per il linguaggio F #](index.md)
- [Moduli](modules.md)
- [F # RFC FS-1009-Consenti i tipi e i moduli referenziali reciprocamente su ambiti più ampi nei file](https://github.com/fsharp/fslang-design/blob/master/FSharp-4.1/FS-1009-mutually-referential-types-and-modules-single-scope.md)
