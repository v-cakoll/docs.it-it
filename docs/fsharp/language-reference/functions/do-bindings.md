---
title: Associazioni do (F#)
description: "Informazioni su come un binding ' do' F # viene utilizzato per eseguire codice senza definire una funzione o un valore."
ms.date: 05/16/2016
ms.openlocfilehash: 6fd084090a204beab0da1c2deb5b5ae2a86281c8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33562336"
---
# <a name="do-bindings"></a>Associazioni do

Oggetto `do` associazione viene utilizzata per eseguire codice senza definire una funzione o un valore. Inoltre, eseguire i binding possono essere utilizzate nelle classi, vedere [ `do` associazioni nelle classi](../members/do-bindings-in-classes.md).


## <a name="syntax"></a>Sintassi

```fsharp
[ attributes ]
[ do ]expression
```

## <a name="remarks"></a>Note
Utilizzare un `do` associazione quando si desidera eseguire il codice in modo indipendente da una definizione di funzione o valore. L'espressione in un `do` deve restituire l'associazione `unit`. Codice in un livello superiore `do` associazione viene eseguita quando viene inizializzato il modulo. La parola chiave `do` è facoltativo.

Gli attributi possono essere applicati a un livello superiore `do` associazione. Ad esempio, se il programma utilizza l'interoperabilità COM, è possibile applicare il `STAThread` attributo al programma. È possibile farlo con un attributo in un `do` binding, come illustrato nel codice seguente.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet201.fs)]
    
## <a name="see-also"></a>Vedere anche
[Riferimenti per il linguaggio F#](../index.md)

[Funzioni](index.md)

