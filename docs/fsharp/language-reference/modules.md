---
title: Moduli (F#)
description: 'Informazioni su come un modulo F # è un raggruppamento di codice F #, ad esempio i valori e tipi di valori di funzione, in un programma F #.'
ms.date: 04/24/2017
ms.openlocfilehash: 9a1416321e392f7a06551b4a7e3429e3a2d023bd
ms.sourcegitcommit: b7763f3435635850a76d4cbcf09bdce6c019208a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2018
ms.locfileid: "34483521"
---
# <a name="modules"></a>Moduli

Nel contesto del linguaggio F #, un *modulo* è un raggruppamento di codice F #, ad esempio i valori e tipi di valori di funzione, in un programma F #. Il codice di raggruppamento nei moduli consente di tenere insieme il codice correlato e consente di evitare conflitti di nome nel programma.

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
Un modulo F # è un raggruppamento di costrutti di codice F #, ad esempio tipi, i valori, valori di funzione e codice `do` associazioni. È implementato come una classe di common language runtime (CLR) che include solo i membri statici. Esistono due tipi di dichiarazioni di modulo, a seconda se l'intero file è incluso nel modulo: una dichiarazione di modulo di primo livello e una dichiarazione di modulo locale. Una dichiarazione di modulo di primo livello include l'intero file nel modulo. Una dichiarazione di modulo di primo livello può apparire solo come prima dichiarazione in un file.

Nella sintassi per la dichiarazione di modulo di primo livello, facoltativo *nomi qualificati* è la sequenza di nomi annidati che contiene il modulo. Lo spazio dei nomi completo non deve essere dichiarato in precedenza.

Non si dispone per il rientro delle dichiarazioni in un modulo di primo livello. È necessario impostare un rientro tutte le dichiarazioni nei moduli locali. In una dichiarazione di modulo locale, solo le dichiarazioni sono rientrate sotto tale dichiarazione di modulo fanno parte del modulo.

Se un file di codice non inizia con una dichiarazione di modulo di primo livello o una dichiarazione dello spazio dei nomi, l'intero contenuto del file, compresi eventuali moduli locali, diventa parte di un modulo di primo livello creata in modo implicito con lo stesso nome del file, senza l'estensione, con la prima lettera convertita in caratteri maiuscoli. Ad esempio, si consideri il seguente file.

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6601.fs)]

Questo file verrà compilato come se fosse scritto in questo modo:

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6602.fs)]

Se si dispone di più moduli in un file, è necessario utilizzare una dichiarazione di modulo locale per ogni modulo. Se viene dichiarato uno spazio dei nomi che lo contiene, questi moduli fanno parte dello spazio dei nomi che lo contiene. Se non è dichiarato uno spazio dei nomi che lo contiene, i moduli diventano parte del modulo di primo livello creata in modo implicito. Esempio di codice seguente viene illustrato un file di codice che contiene più moduli. Il compilatore crea in modo implicito un modulo di primo livello denominato `Multiplemodules`, e `MyModule1` e `MyModule2` sono annidate in tale modulo di primo livello.

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6603.fs)]

Se si dispone di più file in un progetto o in un'unica compilazione o se si compila una libreria, è necessario includere una dichiarazione dello spazio dei nomi o modulo nella parte superiore del file. Il compilatore F # determina solo un nome di modulo in modo implicito quando è presente un solo file in una riga di comando di compilazione o di progetto e si sta creando un'applicazione.

Il *modificatore di accessibilità* può essere uno dei seguenti: `public`, `private`, `internal`. Per altre informazioni, vedere [Controllo di accesso](access-control.md). L'impostazione predefinita è public.


## <a name="referencing-code-in-modules"></a>Riferimenti al codice nei moduli
Quando si fa riferimento a funzioni, tipi e valori da un altro modulo, è necessario utilizzare un nome completo o aprire il modulo. Se si utilizza un nome completo, è necessario specificare gli spazi dei nomi, il modulo e l'identificatore per l'elemento del programma desiderato. Separare ogni parte del percorso completo con un punto (.), come indicato di seguito.

`Namespace1.Namespace2.ModuleName.Identifier`

È possibile aprire il modulo o uno o più degli spazi dei nomi per semplificare il codice. Per ulteriori informazioni sull'apertura di spazi dei nomi e i moduli, vedere [dichiarazioni di importazione: il `open` parola chiave](import-declarations-the-open-keyword.md).

Esempio di codice seguente viene illustrato un modulo di primo livello che contiene tutto il codice fino alla fine del file.

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6604.fs)]

Per utilizzare questo codice da un altro file nello stesso progetto, è possibile utilizzare nomi completi o si apre il modulo prima di utilizzare le funzioni, come illustrato negli esempi seguenti.

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6605.fs)]

## <a name="nested-modules"></a>Moduli annidati
I moduli possono essere annidati. Moduli interni devono essere rientrati fino alle dichiarazioni di modulo esterno per indicare che sono moduli interni, non nuovi moduli. Ad esempio, confrontare i due esempi seguenti. Modulo `Z` è un modulo interno nel codice seguente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6607.fs)]

Ma modulo `Z` è di pari livello al modulo `Y` nel codice seguente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6608.fs)]
Modulo `Z` è inoltre un modulo di elemento di pari livello nel codice seguente, in quanto il rientro non concerne le altre dichiarazioni nel modulo `Y`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6609.fs)]
Infine, se il modulo esterno non include dichiarazioni ed è seguito immediatamente da un'altra dichiarazione di modulo, si presuppone che la nuova dichiarazione di modulo è un modulo interno, ma il compilatore visualizzerà un avviso se la seconda definizione di modulo non viene rientrata farther più di primo.

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6610.fs)]
Per eliminare l'avviso, impostare un rientro il modulo interno.

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6611.fs)]
Se si desidera che tutto il codice in un file in un singolo modulo esterno e si desidera moduli interni, il modulo esterno non richiede il segno di uguale e le dichiarazioni, incluse tutte le dichiarazioni di modulo interno, che entreranno nel modulo esterno non è necessario impostare un rientro. Le dichiarazioni all'interno delle dichiarazioni di moduli interni deve essere rientrato. Il codice seguente è illustrata questa situazione.

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6612.fs)]

## <a name="recursive-modules"></a>Moduli ricorsiva

F # 4.1 introduce la nozione di moduli che consentono di tutto il codice indipendente reciprocamente sono ricorsivi.  Questa operazione viene eseguita tramite `module rec`.  Utilizzo di `module rec` possibile tentare di risolvere alcune difficoltà in non è in grado di scrivere codice reciprocamente referenziale tra i tipi e i moduli.  Di seguito è riportato un esempio di questo oggetto:

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

Si noti che l'eccezione `DontSqueezeTheBananaException` e la classe `Banana` fanno riferimento a altro.  Inoltre, il modulo `BananaHelpers` e la classe `Banana` anche fare riferimento a altro.  Ciò non sarebbe possibile esprimere in F #, se è stato rimosso il `rec` (parola chiave) dal `RecursiveModule` modulo.

Questa funzionalità è anche possibile in [gli spazi dei nomi](namespaces.md) con F # 4.1.

## <a name="see-also"></a>Vedere anche

[Riferimenti per il linguaggio F#](index.md)  
[Spazi dei nomi](namespaces.md)  
[1009-F # RFC Fi - Consenti moduli e tipi reciprocamente referenziali su maggiori ambiti all'interno dei file](https://github.com/fsharp/fslang-design/blob/master/FSharp-4.1/FS-1009-mutually-referential-types-and-modules-single-scope.md)  
