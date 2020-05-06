---
title: Moduli
description: 'Informazioni su come un modulo F # è un raggruppamento di codice F #, ad esempio valori, tipi e valori di funzione, in un programma F #.'
ms.date: 04/24/2017
ms.openlocfilehash: 5f99bbd8069478bf0c7db2800ae545f31926728a
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2020
ms.locfileid: "82794364"
---
# <a name="modules"></a>Moduli

Nel contesto del linguaggio F #, un *modulo* è un raggruppamento di codice f #, ad esempio valori, tipi e valori di funzione, in un programma f #. Il codice di raggruppamento nei moduli consente di tenere insieme il codice correlato e consente di evitare conflitti di nome nel programma.

## <a name="syntax"></a>Sintassi

```fsharp
// Top-level module declaration.
module [accessibility-modifier] [qualified-namespace.]module-name
declarations
// Local module declaration.
module [accessibility-modifier] module-name =
    declarations
```

## <a name="remarks"></a>Osservazioni

Un modulo F # è un raggruppamento di costrutti di codice F #, ad esempio tipi, valori, valori di funzione e codice `do` nelle associazioni. Viene implementato come una classe Common Language Runtime (CLR) che dispone solo di membri statici. Esistono due tipi di dichiarazioni di modulo, a seconda che l'intero file sia incluso nel modulo: una dichiarazione di modulo di primo livello e una dichiarazione di modulo locale. Una dichiarazione di modulo di primo livello include l'intero file nel modulo. Una dichiarazione di modulo di primo livello può essere visualizzata solo come prima dichiarazione in un file.

Nella sintassi per la dichiarazione di modulo di primo livello, lo *spazio dei nomi Qualified* facoltativo è la sequenza dei nomi di spazio dei nomi annidati che contiene il modulo. Non è necessario dichiarare in precedenza lo spazio dei nomi qualificato.

Non è necessario rientrare nelle dichiarazioni in un modulo di primo livello. È necessario rientrare in tutte le dichiarazioni nei moduli locali. In una dichiarazione di modulo locale, solo le dichiarazioni rientrate sotto tale dichiarazione del modulo fanno parte del modulo.

Se un file di codice non inizia con una dichiarazione di modulo di primo livello o con una dichiarazione dello spazio dei nomi, l'intero contenuto del file, inclusi i moduli locali, diventa parte di un modulo di primo livello creato in modo implicito con lo stesso nome del file, senza l'estensione, con la prima lettera convertita in maiuscolo. Si consideri, ad esempio, il file seguente.

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6601.fs)]

Questo file verrà compilato come se fosse stato scritto in questo modo:

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6602.fs)]

Se sono presenti più moduli in un file, è necessario usare una dichiarazione di modulo locale per ogni modulo. Se viene dichiarato uno spazio dei nomi che lo contiene, questi moduli fanno parte dello spazio dei nomi che lo contiene. Se uno spazio dei nomi che lo contiene non è dichiarato, i moduli diventano parte del modulo di primo livello creato in modo implicito. Nell'esempio di codice riportato di seguito viene illustrato un file di codice contenente più moduli. Il compilatore crea in modo implicito un modulo di primo `Multiplemodules`livello denominato `MyModule1` e `MyModule2` e sono annidati in tale modulo di primo livello.

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6603.fs)]

Se si dispone di più file in un progetto o in una singola compilazione o se si compila una libreria, è necessario includere una dichiarazione dello spazio dei nomi o una dichiarazione di modulo nella parte superiore del file. Il compilatore F # determina un nome di modulo in modo implicito solo quando è presente un solo file in un progetto o in una riga di comando di compilazione e si crea un'applicazione.

Il *modificatore di accessibilità* può essere uno dei seguenti `public`: `private`, `internal`,. Per altre informazioni, vedere [Controllo di accesso](access-control.md). Il valore predefinito è public.

## <a name="referencing-code-in-modules"></a>Riferimento al codice nei moduli

Quando si fa riferimento a funzioni, tipi e valori di un altro modulo, è necessario usare un nome completo o aprire il modulo. Se si usa un nome completo, è necessario specificare gli spazi dei nomi, il modulo e l'identificatore per l'elemento del programma desiderato. Si separa ogni parte del percorso completo con un punto (.), come indicato di seguito.

`Namespace1.Namespace2.ModuleName.Identifier`

Per semplificare il codice, è possibile aprire il modulo o uno o più spazi dei nomi. Per ulteriori informazioni sull'apertura di spazi dei nomi e moduli, vedere [importare dichiarazioni: `open` parola chiave](import-declarations-the-open-keyword.md).

L'esempio di codice seguente mostra un modulo di primo livello che contiene tutto il codice fino alla fine del file.

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6604.fs)]

Per usare questo codice da un altro file nello stesso progetto, è possibile usare nomi completi o aprire il modulo prima di usare le funzioni, come illustrato negli esempi seguenti.

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6605.fs)]

## <a name="nested-modules"></a>Moduli annidati

I moduli possono essere annidati. Per indicare che si tratta di moduli interni e non nuovi moduli, è necessario rientrare nei moduli interni per quanto riguarda le dichiarazioni del modulo esterno. Confrontare, ad esempio, i due esempi seguenti. Il `Z` modulo è un modulo interno nel codice riportato di seguito.

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6607.fs)]

Tuttavia, `Z` il modulo è un elemento `Y` di pari livello nel codice riportato di seguito.

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6608.fs)]
Il `Z` modulo è anche un modulo di pari livello nel codice seguente, perché non è rientrato per quanto riguarda le altre dichiarazioni `Y`nel modulo.

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6609.fs)]
Infine, se il modulo esterno non ha dichiarazioni e viene seguito immediatamente da un'altra dichiarazione di modulo, si presuppone che la nuova dichiarazione del modulo sia un modulo interno, ma il compilatore avvisa l'utente se la definizione del secondo modulo non è rientrata rispetto alla prima.

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6610.fs)]
Per eliminare l'avviso, rientrare nel modulo interno.

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6611.fs)]
Se si vuole che tutto il codice in un file si trovi in un unico modulo esterno e si desideri che i moduli interni non richiedano il segno di uguale e le dichiarazioni, incluse le dichiarazioni dei moduli interni, che andranno nel modulo esterno non devono essere rientrate. È necessario rientrare le dichiarazioni all'interno delle dichiarazioni dei moduli interni. Il codice seguente illustra questo caso.

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6612.fs)]

## <a name="recursive-modules"></a>Moduli ricorsivi

F # 4,1 introduce la nozione di moduli che consentono a tutto il codice contenuto di essere ricorsivo a vicenda.  Questa operazione viene eseguita `module rec`tramite.  L'uso `module rec` di può alleviare alcune problematiche nella mancata possibilità di scrivere codice reciprocamente referenziale tra tipi e moduli.  Di seguito è riportato un esempio:

```fsharp
module rec RecursiveModule =
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

Si noti che l' `DontSqueezeTheBananaException` eccezione e la `Banana` classe fanno riferimento l'una all'altra.  Inoltre, il modulo `BananaHelpers` e la classe `Banana` fanno riferimento l'uno all'altro.  Non sarebbe possibile esprimere in F # se la `rec` parola chiave è stata rimossa dal `RecursiveModule` modulo.

Questa funzionalità è inoltre possibile negli [spazi dei nomi](namespaces.md) con F # 4,1.

## <a name="see-also"></a>Vedere anche

- [Riferimenti per il linguaggio F #](index.md)
- [Spazi dei nomi](namespaces.md)
- [F # RFC FS-1009-Consenti i tipi e i moduli referenziali reciprocamente su ambiti più ampi nei file](https://github.com/fsharp/fslang-design/blob/master/FSharp-4.1/FS-1009-mutually-referential-types-and-modules-single-scope.md)
