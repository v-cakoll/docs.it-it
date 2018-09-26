---
title: Associazioni let nelle classi (F#)
description: "Informazioni su come definire i campi privati e funzioni private per le classi di F # tramite associazioni 'let' nella definizione della classe."
ms.date: 05/16/2016
ms.openlocfilehash: 237eb98a57571a21c9187abf31f05160374cf4fc
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/26/2018
ms.locfileid: "47210240"
---
# <a name="let-bindings-in-classes"></a>Associazioni let nelle classi

È possibile definire i campi privati e funzioni private per le classi di F # tramite `let` associazioni nella definizione della classe.

## <a name="syntax"></a>Sintassi

```fsharp
// Field.
[static] let [ mutable ] binding1 [ and ... binding-n ]

// Function.
[static] let [ rec ] binding1 [ and ... binding-n ]
```

## <a name="remarks"></a>Note

La sintassi precedente viene visualizzata dopo le dichiarazioni di intestazione e l'ereditarietà di classe ma prima di qualsiasi definizione del membro. La sintassi è simile a quella di `let` associazioni di fuori di classi, ma i nomi definiti in una classe hanno un ambito è limitato alla classe. Oggetto `let` binding crea un campo privato o una funzione; per esporre i dati o le funzioni pubblicamente, dichiarare una proprietà o un metodo del membro.

Oggetto `let` che l'associazione non è statico viene chiamato un'istanza `let` associazione. Istanza `let` associazioni eseguite quando vengono creati gli oggetti. Statico `let` associazioni fanno parte dell'inizializzatore statico per la classe che viene sempre eseguito prima che il tipo viene usato prima di tutto.

Il codice all'interno di istanza `let` associazioni è possono usare i parametri del costruttore primario.

Gli attributi e i modificatori di accessibilità non sono consentiti sui `let` associazioni nelle classi.

Gli esempi di codice seguenti illustrano diversi tipi di `let` associazioni nelle classi.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3001.fs)]

L'output è indicato di seguito.

```
10 52 1 204
```

## <a name="alternative-ways-to-create-fields"></a>Modalità alternative di creazione di campi

È anche possibile usare il `val` (parola chiave) per creare un campo privato. Quando si usa il `val` (parola chiave), il campo non ha un valore quando l'oggetto viene creato, ma invece viene inizializzata con un valore predefinito. Per altre informazioni, vedere [i campi espliciti: val (parola chiave)](explicit-fields-the-val-keyword.md).

È anche possibile definire i campi privati in una classe usando una definizione di membro e aggiungendo la parola chiave `private` alla definizione. Ciò può essere utile se si prevede di modificare l'accessibilità di un membro senza riscrivere il codice. Per altre informazioni, vedere [Controllo di accesso](../access-control.md).

## <a name="see-also"></a>Vedere anche

- [Membri](index.md)
- [Associazioni `do` nelle classi](do-bindings-in-classes.md)
- [`let` associazioni](../functions/let-bindings.md)
