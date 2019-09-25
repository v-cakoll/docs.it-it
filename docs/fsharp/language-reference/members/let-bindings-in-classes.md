---
title: Associazioni let nelle classi
description: Informazioni su come definire campi privati e funzioni private per F# le classi usando associazioni ' Let ' nella definizione della classe.
ms.date: 05/16/2016
ms.openlocfilehash: 1366ab8f1f4f606fe5947a8fc4df10de49346b3e
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/24/2019
ms.locfileid: "71216526"
---
# <a name="let-bindings-in-classes"></a>Associazioni let nelle classi

È possibile definire campi privati e funzioni private per F# le classi `let` utilizzando binding nella definizione della classe.

## <a name="syntax"></a>Sintassi

```fsharp
// Field.
[static] let [ mutable ] binding1 [ and ... binding-n ]

// Function.
[static] let [ rec ] binding1 [ and ... binding-n ]
```

## <a name="remarks"></a>Note

La sintassi precedente viene visualizzata dopo l'intestazione della classe e le dichiarazioni di ereditarietà, ma prima delle definizioni dei membri. La sintassi è simile a quella `let` delle associazioni esterne alle classi, ma i nomi definiti in una classe hanno un ambito limitato alla classe. Un' `let` associazione crea una funzione o un campo privato; per esporre pubblicamente i dati o le funzioni, dichiarare una proprietà o un metodo del membro.

Un' `let` associazione non statica viene chiamata Associazione di istanza `let` . Le `let` associazioni di istanza vengono eseguite quando vengono creati oggetti. Le `let` associazioni statiche fanno parte dell'inizializzatore statico per la classe, che è garantita l'esecuzione prima che il tipo venga usato per la prima volta.

Il codice all'interno `let` delle associazioni di istanza può usare i parametri del costruttore primario.

Attributi e modificatori di accessibilità non sono `let` consentiti nelle associazioni nelle classi.

Negli esempi di codice seguenti vengono illustrati diversi `let` tipi di associazioni nelle classi.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3001.fs)]

L'output è indicato di seguito.

```console
10 52 1 204
```

## <a name="alternative-ways-to-create-fields"></a>Metodi alternativi per la creazione di campi

È anche possibile usare la `val` parola chiave per creare un campo privato. Quando si usa `val` la parola chiave, al campo non viene assegnato un valore quando viene creato l'oggetto, ma viene invece inizializzato con un valore predefinito. Per ulteriori informazioni, vedere [campi espliciti: Parola chiave](explicit-fields-the-val-keyword.md)Val.

È anche possibile definire campi privati in una classe usando una definizione del membro e aggiungendo la parola `private` chiave alla definizione. Questa operazione può essere utile se si prevede di modificare l'accessibilità di un membro senza riscrivere il codice. Per altre informazioni, vedere [Controllo di accesso](../access-control.md).

## <a name="see-also"></a>Vedere anche

- [Membri](index.md)
- [Associazioni `do` nelle classi](do-bindings-in-classes.md)
- [`let`Associazioni](../functions/let-bindings.md)
