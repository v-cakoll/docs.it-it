---
title: Associazioni do nelle classi
description: Informazioni su come usare un F# binding ' do ' in una definizione di classe, che esegue azioni quando l'oggetto viene costruito o quando il tipo viene usato per la prima volta.
ms.date: 05/16/2016
ms.openlocfilehash: ced4f1bb17d9e23bf51cc79b5a275cc334cca013
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "68627583"
---
# <a name="do-bindings-in-classes"></a>Associazioni do nelle classi

Un' `do` associazione in una definizione di classe esegue azioni quando l'oggetto viene costruito o, per un' `do` associazione statica, quando il tipo viene usato per la prima volta.

## <a name="syntax"></a>Sintassi

```fsharp
[static] do expression
```

## <a name="remarks"></a>Note

Un' `do` associazione viene visualizzata insieme a o `let` dopo le associazioni ma prima delle definizioni dei membri in una definizione di classe. Sebbene la `do` parola chiave sia facoltativa per `do` le associazioni a livello di modulo, non è facoltativa per `do` le associazioni in una definizione di classe.

Per la costruzione di ogni oggetto di un determinato tipo, le associazioni non `do` statiche e le associazioni non statiche `let` vengono eseguite nell'ordine in cui sono visualizzate nella definizione della classe. In `do` un tipo possono essere presenti più associazioni. Le associazioni non statiche `let` e le associazioni non statiche `do` diventano il corpo del costruttore primario. Il codice nella sezione associazioni non statiche `do` può fare riferimento ai parametri del costruttore primario e a qualsiasi valore o funzione definito `let` nella sezione Bindings.

Le associazioni non `do` statiche possono accedere ai membri della classe purché la classe disponga di un identificatore di autonomia definito da una `as` parola chiave nell'intestazione della classe e purché tutti gli utilizzi di tali membri siano qualificati con l'identificatore automatico per la classe.

Poiché `let` le associazioni inizializzano i campi privati di una classe, che è spesso necessaria per garantire che i membri si comportino come previsto, `do` le `let` associazioni vengono in genere inserite dopo le `do` associazioni in modo tale che il codice nell'associazione possa eseguire con un oggetto completamente inizializzato. Se il codice tenta di utilizzare un membro prima che l'inizializzazione venga completata, viene generata un'eccezione InvalidOperationException.

Le `do` associazioni statiche possono fare riferimento a membri o campi statici della classe contenitore, ma non a membri o campi di istanza. Le `do` associazioni statiche diventano parte dell'inizializzatore statico per la classe, che è garantita l'esecuzione prima che la classe venga usata per la prima volta.

Gli attributi vengono ignorati per `do` le associazioni nei tipi. Se è necessario un attributo per il codice eseguito in un' `do` associazione, è necessario applicarlo al costruttore primario.

Nel codice seguente, una classe ha un'associazione statica `do` e un'associazione non statica. `do` L'oggetto ha un costruttore con due parametri, `a` e `b`e due `let` campi privati vengono definiti nelle associazioni per la classe. Sono definite anche due proprietà. Tutti questi elementi sono inclusi nell'ambito della sezione associazioni non `do` statiche, come illustrato dalla riga che stampa tutti questi valori.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3101.fs)]

L'output è indicato di seguito.

```console
Initializing MyType.
Initializing object 1 2 2 4 8 16
```

## <a name="see-also"></a>Vedere anche

- [Membri](index.md)
- [Classi](../classes.md)
- [Costruttori](constructors.md)
- [Associazioni `let` nelle classi](let-bindings-in-classes.md)
- [`do`Associazioni](../functions/do-Bindings.md)
