---
title: Associazioni do
description: Informazioni su come un F# 'do' binding viene usato per eseguire codice senza definire una funzione o un valore.
ms.date: 05/16/2016
ms.openlocfilehash: 0755e36912fc4e5a645e55eb4bee5c730a56cadf
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "65641921"
---
# <a name="do-bindings"></a>Associazioni do

Oggetto `do` binding viene usato per eseguire codice senza definire una funzione o un valore. Inoltre, eseguire i binding possono essere usati nelle classi, vedere [ `do` associazioni nelle classi](../members/do-bindings-in-classes.md).

## <a name="syntax"></a>Sintassi

```fsharp
[ attributes ]
[ do ]expression
```

## <a name="remarks"></a>Note

Usare un `do` binding quando si desidera eseguire il codice indipendentemente da una definizione di funzione o un valore. L'espressione in una `do` binding deve restituire `unit`. Codice in un livello superiore `do` associazione viene eseguita quando viene inizializzato il modulo. La parola chiave `do` è facoltativo.

Gli attributi possono essere applicati a un livello superiore `do` associazione. Ad esempio, se il programma Usa l'interoperabilità COM, è possibile applicare il `STAThread` attributo al programma. Questo scopo, è possibile utilizzare un attributo in un `do` associazione, come illustrato nel codice seguente.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet201.fs)]

## <a name="see-also"></a>Vedere anche

- [Riferimenti per il linguaggio F#](../index.md)
- [Funzioni](index.md)
