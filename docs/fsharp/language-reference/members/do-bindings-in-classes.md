---
title: Associazioni do nelle classi (F#)
description: "Informazioni su come utilizzare un'associazione in una definizione di classe che esegue azioni quando l'oggetto viene costruito o quando il tipo viene utilizzato prima ' do' F #."
ms.date: 05/16/2016
ms.openlocfilehash: 779b33c44b1518135f4c7f270173ec8124fec101
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33565191"
---
# <a name="do-bindings-in-classes"></a>Associazioni do nelle classi

Oggetto `do` associazione in una definizione di classe esegue azioni quando l'oggetto viene costruito o, per un valore statico `do` binding, quando il tipo viene innanzitutto utilizzato.


## <a name="syntax"></a>Sintassi

```fsharp
[static] do expression
```

## <a name="remarks"></a>Note
Oggetto `do` associazione viene visualizzata insieme a o dopo `let` associazioni ma prima delle definizioni di membro in una definizione di classe. Sebbene il `do` parola chiave è facoltativa per `do` associazioni a livello di modulo, non è facoltativo per `do` binding in una definizione di classe.

Per la costruzione di ogni oggetto di qualsiasi tipo specifico, non statico `do` associazioni e non statici `let` associazioni vengono eseguite nell'ordine in cui appaiono nella definizione della classe. Più `do` associazioni possono verificarsi in un solo tipo. Non statiche `let` associazioni e non statiche `do` associazioni diventano il corpo del costruttore primario. Il codice non statiche `do` sezione delle associazioni può fare riferimento a parametri del costruttore primario e qualsiasi valori o funzioni che sono definite nel `let` sezione delle associazioni.

Non statico `do` associazioni possono accedere i membri della classe fino a quando la classe dispone di un autoidentificatore definito da un `as` parola chiave nella classe di intestazione e a condizione che tutte le occorrenze di tali membri sono qualificate con l'identificatore utente per la classe.

Poiché `let` associazioni inizializzano i campi privati di una classe, che è spesso necessario garantire che i membri si comportino come previsto, `do` binding vengono in genere inseriti dopo `let` associazioni in modo che il codice nel `do` associazione può eseguire con un oggetto completamente inizializzato. Se il codice tenta di usare un membro prima del completamento dell'inizializzazione, viene generata un'eccezione InvalidOperationException.

Statico `do` associazioni possono fare riferimento a membri statici o campi di inclusione classe ma non campi o membri di istanza. Statico `do` associazioni diventano parte dell'inizializzatore statico per la classe, che viene sempre eseguito prima che la classe viene utilizzata prima.

Gli attributi vengono ignorati per `do` nei tipi di associazioni. Se un attributo è obbligatorio per il codice eseguito in un `do` associazione deve essere applicata al costruttore primario.

Nel codice seguente, una classe dispone di un valore statico `do` associazione e non statici `do` associazione. L'oggetto ha un costruttore che ha due parametri, `a` e `b`, e due campi privati sono definiti nel `let` associazioni per la classe. Vengono definite anche due proprietà. Tutti questi rientrano nell'ambito non statiche `do` sezione associazioni, come illustrato dalla riga che vengono stampati tutti i valori.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3101.fs)]

L'output è indicato di seguito.

```console
Initializing MyType.
Initializing object 1 2 2 4 8 16
```

## <a name="see-also"></a>Vedere anche
[Membri](index.md)

[Classi](../classes.md)

[Costruttori](constructors.md)

[Associazioni `let` nelle classi](let-bindings-in-classes.md)

[`do` Associazioni](../functions/do-Bindings.md)
