---
title: Associazioni do nelle classi
description: Informazioni su come usare un F# associazione in una definizione di classe che esegue azioni quando l'oggetto viene costruito oppure quando viene utilizzato innanzitutto il tipo ' do'.
ms.date: 05/16/2016
ms.openlocfilehash: 0ddf2b5ca458d0950c2e07bf2c37c205877e2173
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61904592"
---
# <a name="do-bindings-in-classes"></a>Associazioni do nelle classi

Oggetto `do` associazione in una definizione di classe esegue azioni quando viene costruito l'oggetto oppure, per un valore statico `do` binding, quando viene utilizzato il tipo prima di tutto.

## <a name="syntax"></a>Sintassi

```fsharp
[static] do expression
```

## <a name="remarks"></a>Note

Oggetto `do` associazione viene visualizzata insieme a o dopo `let` associazioni, ma prima le definizioni dei membri in una definizione di classe. Anche se il `do` è facoltativo per la parola chiave `do` associazioni a livello di modulo, non è facoltativo per `do` associazioni in una definizione di classe.

Per la costruzione di tutti gli oggetti di qualsiasi tipo specifico, non statici `do` associazioni e non statici `let` associazioni vengono eseguite nell'ordine in cui appaiono nella definizione della classe. Più `do` associazioni possono verificarsi in un solo tipo. Non statiche `let` associazioni e non statiche `do` associazioni diventano il corpo del costruttore primario. Il codice non statiche `do` può fare riferimento a parametri del costruttore primaria e qualsiasi valori o funzioni definite in sezione delle associazioni di `let` sezione delle associazioni.

Non statici `do` associazioni possono accedere ai membri della classe, purché la classe ha un identificatore automatico che è definito da un `as` parola chiave della classe sull'intestazione e fino a quando tutte le occorrenze di tali membri sono qualificate con l'identificatore utente per la classe.

Perché `let` associazioni inizializzano i campi privati di una classe, che è spesso necessario garantire che i membri si comportino come previsto, `do` associazioni vengono in genere inserite dopo `let` associazioni in modo che il codice nel `do` can associazione esecuzione con un oggetto completamente inizializzato. Se il codice tenta di usare un membro prima del completamento dell'inizializzazione, viene generata un'eccezione InvalidOperationException.

Statico `do` associazioni possono fare riferimento a membri statici o campi di inclusione classe ma non i membri o i campi di istanza. Statico `do` associazioni diventano parte dell'inizializzatore statico per la classe che viene sempre eseguito prima che la classe viene usata prima di tutto.

Gli attributi vengono ignorati per `do` associazioni di tipi. Se un attributo è obbligatorio per il codice eseguito in un `do` associazione, deve essere applicata al costruttore primario.

Nel codice seguente, una classe ha un valore statico `do` associazione e non statici `do` associazione. L'oggetto ha un costruttore che ha due parametri, `a` e `b`, e vengono definiti due campi privati nel `let` associazioni per la classe. Vengono definite anche due proprietà. Tutti questi rientrano nell'ambito non statiche `do` sezione associazioni, come illustrato dalla riga che vengono stampati tutti i valori.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3101.fs)]

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
- [`do` associazioni](../functions/do-Bindings.md)