---
title: Moduli (F#)
description: 'Informazioni su come un modulo F # è un raggruppamento di codice F #, ad esempio i valori, tipi e valori di funzioni, in un programma F #.'
ms.date: 04/24/2017
ms.openlocfilehash: fb0aa1d508d1141933b4fbdf10633f67ed078dc7
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/13/2018
ms.locfileid: "45528526"
---
# <a name="modules"></a>Moduli

Nel contesto del linguaggio F #, un *modulo* è un raggruppamento di codice F #, ad esempio i valori, tipi e valori di funzioni, in un programma F #. Il codice di raggruppamento nei moduli consente di tenere insieme il codice correlato e consente di evitare conflitti di nome nel programma.

## <a name="syntax"></a>Sintassi

```fsharp
// Top-level module declaration.
module [accessibility-modifier] [qualified-namespace.]module-name
declarations
// Local module declaration.
module [accessibility-modifier] module-name =
    declarations
```

## <a name="remarks"></a>Note

Un modulo F # è un raggruppamento di costrutti di codice F #, ad esempio i tipi, i valori, valori di funzione e codice in `do` associazioni. Viene implementato come una classe common language runtime (CLR) che includa solo membri statici. Esistono due tipi di dichiarazioni di modulo, a seconda del fatto che l'intero file è incluso nel modulo: una dichiarazione di modulo di primo livello e una dichiarazione di modulo locale. Una dichiarazione di modulo di livello principale include l'intero file nel modulo. Una dichiarazione di modulo di primo livello può apparire solo come la prima dichiarazione in un file.

La sintassi per la dichiarazione di modulo di primo livello, l'opzione facoltativa *qualificato-spazio dei nomi* è la sequenza di nomi di spazio dei nomi annidato che contiene il modulo. Lo spazio dei nomi qualificato non deve essere dichiarato in precedenza.

Non è necessario impostare un rientro delle dichiarazioni in un modulo di primo livello. È necessario impostare un rientro a tutte le dichiarazioni nei moduli locale. In una dichiarazione di modulo locale, solo le dichiarazioni vengono rientrate sotto tale dichiarazione di modulo fanno parte del modulo.

Se un file di codice non inizia con una dichiarazione di modulo di primo livello o una dichiarazione dello spazio dei nomi, l'intero contenuto del file, inclusi tutti i moduli locali, diventa parte di un modulo di primo livello creato in modo implicito con lo stesso nome del file, senza l'estensione, con la prima lettera convertita in caratteri maiuscoli. Ad esempio, si consideri il seguente file.

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6601.fs)]

Questo file potrebbe essere compilato come se fosse scritto in questo modo:

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6602.fs)]

Se si dispone di più moduli in un file, è necessario usare una dichiarazione di modulo locale per ogni modulo. Se viene dichiarato uno spazio dei nomi che lo contiene, questi moduli sono parte dello spazio dei nomi che lo contiene. Se non viene dichiarato uno spazio dei nomi che lo contiene, i moduli diventano parte del modulo di primo livello creato in modo implicito. Esempio di codice seguente illustra un file di codice che contiene più moduli. Il compilatore crea in modo implicito un modulo di primo livello denominato `Multiplemodules`, e `MyModule1` e `MyModule2` sono annidate in ogni modulo di primo livello.

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6603.fs)]

Se si hanno più file in un progetto o in un'unica compilazione o se si sta creando una libreria, è necessario includere una dichiarazione di modulo nella parte superiore del file o una dichiarazione dello spazio dei nomi. Il compilatore F # determina solo un nome di modulo in modo implicito quando è presente un solo file in una riga di comando di compilazione o di progetto e si sta creando un'applicazione.

Il *modificatore di accessibilità* può essere uno dei seguenti: `public`, `private`, `internal`. Per altre informazioni, vedere [Controllo di accesso](access-control.md). L'impostazione predefinita è public.

## <a name="referencing-code-in-modules"></a>Riferimenti al codice nei moduli

Quando si fa riferimento a funzioni, tipi e valori da un altro modulo, è necessario usare un nome completo o aprire il modulo. Se si usa un nome completo, è necessario specificare gli spazi dei nomi, il modulo e l'identificatore per l'elemento del programma desiderato. È separare ogni parte del percorso completo con un punto (.), come indicato di seguito.

`Namespace1.Namespace2.ModuleName.Identifier`

È possibile aprire il modulo o uno o più degli spazi dei nomi per semplificare il codice. Per altre informazioni sull'apertura degli spazi dei nomi e i moduli, vedere [dichiarazioni di importazione: il `open` parola chiave](import-declarations-the-open-keyword.md).

Esempio di codice seguente mostra un modulo di primo livello che contiene tutto il codice fino alla fine del file.

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6604.fs)]

Per usare questo codice da un altro file nello stesso progetto, è possibile utilizzare nomi completi o si apre il modulo prima di usare le funzioni, come illustrato negli esempi seguenti.

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6605.fs)]

## <a name="nested-modules"></a>Moduli annidati

I moduli possono essere annidati. Moduli interni devono essere applicato un rientro per quanto riguarda le dichiarazioni di modulo esterno per indicare che sono moduli interni, non nuovi moduli. Ad esempio, confrontare i due esempi seguenti. Modulo `Z` è un modulo interno nel codice seguente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6607.fs)]

Ma modulo `Z` è di pari livello al modulo `Y` nel codice seguente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6608.fs)]
Modulo `Z` è anche un modulo di pari livello nel codice seguente, in quanto non viene applicato un rientro per quanto riguarda le altre dichiarazioni di modulo `Y`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6609.fs)]
Infine, se il modulo esterno non dispone di alcun dichiarazioni ed è seguito immediatamente da un'altra dichiarazione di modulo, la nuova dichiarazione di modulo viene considerato come un modulo interno, ma il compilatore avverte l'utente se la seconda definizione del modulo non verrà rientrata rispetto a farther il primo.

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6610.fs)]
Per eliminare l'avviso, impostare un rientro del modulo interno.

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6611.fs)]
Se si vuole che tutto il codice in un file in un singolo modulo esterno e si vuole moduli interni, il modulo esterno non richiede il segno di uguale e le dichiarazioni, incluse le dichiarazioni di modulo interno, che entreranno nel modulo esterno non sono necessario impostare un rientro. Le dichiarazioni all'interno delle dichiarazioni di modulo interno deve essere rientrata. Il codice seguente viene illustrato in questo caso.

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6612.fs)]

## <a name="recursive-modules"></a>Moduli ricorsiva

F # 4.1 introduce la nozione di moduli che consentono di tutto il codice indipendente si escludono a vicenda sono ricorsivi.  Questa operazione viene eseguita tramite `module rec`.  Uso di `module rec` possibile tentare di risolvere alcune aree problematiche in cui non riesca a scrivere il codice si escludono a vicenda referenziali tra i tipi e i moduli.  Di seguito è riportato un esempio:

```fsharp
module rec RecursiveModule =
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

Si noti che l'eccezione `DontSqueezeTheBananaException` e la classe `Banana` entrambe fanno riferimento reciproco.  Inoltre, il modulo `BananaHelpers` e la classe `Banana` riferimento anche a altro.  Ciò non sarebbe possibile esprimere in F # se sono stati rimossi i `rec` parola chiave dal `RecursiveModule` modulo.

Questa funzionalità è anche possibile nelle [spazi dei nomi](namespaces.md) con F # 4.1.

## <a name="see-also"></a>Vedere anche

- [Riferimenti per il linguaggio F#](index.md)  
- [Spazi dei nomi](namespaces.md)  
- [1009-F # RFC FS - Consenti moduli e tipi referenziali si escludono a vicenda su ambiti più ampi all'interno dei file](https://github.com/fsharp/fslang-design/blob/master/FSharp-4.1/FS-1009-mutually-referential-types-and-modules-single-scope.md)  
