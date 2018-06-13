---
title: Associazioni let nelle classi (F#)
description: "Informazioni su come definire i campi privati e funzioni private per le classi F # con binding 'let' nella definizione della classe."
ms.date: 05/16/2016
ms.openlocfilehash: 1c17fe0edec14c28c9bdde86d0a2acb7c886cdf7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33564547"
---
# <a name="let-bindings-in-classes"></a>Associazioni let nelle classi

È possibile definire campi privati e funzioni private per le classi F # utilizzando `let` associazioni nella definizione della classe.


## <a name="syntax"></a>Sintassi

```fsharp
// Field.
[static] let [ mutable ] binding1 [ and ... binding-n ]

// Function.
[static] let [ rec ] binding1 [ and ... binding-n ]
```

## <a name="remarks"></a>Note
La sintassi precedente viene visualizzato dopo le dichiarazioni di intestazione e l'ereditarietà di classe ma prima di qualsiasi definizione del membro. La sintassi è simile a quella di `let` associazioni di fuori di classi, ma i nomi definiti in una classe hanno un ambito è limitato alla classe. Oggetto `let` associazione crea una funzione; per esporre i dati o un campo privato o le funzioni pubblicamente, dichiarare una proprietà o un metodo di membro.

Oggetto `let` che l'associazione non è statico viene chiamato un'istanza `let` associazione. Istanza `let` associazioni eseguire quando vengono creati gli oggetti. Statico `let` associazioni fanno parte dell'inizializzatore statico per la classe, che viene sempre eseguito prima che il tipo viene utilizzato prima.

Il codice all'interno di istanza `let` associazioni possono utilizzare i parametri del costruttore primario.

Gli attributi e modificatori di accessibilità non consentiti in `let` associazioni nelle classi.

Gli esempi di codice seguenti illustrano diversi tipi di `let` associazioni nelle classi.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3001.fs)]

L'output è indicato di seguito.

```
10 52 1 204
```

## <a name="alternative-ways-to-create-fields"></a>Modalità alternative di creazione di campi
È inoltre possibile utilizzare il `val` (parola chiave) per creare un campo privato. Quando si utilizza il `val` (parola chiave), il campo non ha un valore quando l'oggetto viene creato, ma invece viene inizializzata con un valore predefinito. Per ulteriori informazioni, vedere [campi espliciti: val (parola chiave)](explicit-fields-the-val-keyword.md).

È inoltre possibile definire campi privati in una classe usando una definizione di membro e aggiungendo la parola chiave `private` alla definizione. Questo può essere utile se si prevede di modificare l'accessibilità di un membro senza riscrivere il codice. Per altre informazioni, vedere [Controllo di accesso](../access-control.md).

## <a name="see-also"></a>Vedere anche
[Membri](index.md)

[Associazioni `do` nelle classi](do-bindings-in-classes.md)

[`let` Associazioni](../functions/let-bindings.md)
