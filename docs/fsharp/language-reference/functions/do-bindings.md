---
title: Associazioni do (F#)
description: "Informazioni su come un binding ' do' F # viene utilizzato per eseguire codice senza definire una funzione o un valore."
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 4c63da0c5e2f4130d59f9efa6bc54a55e5fe9fd8
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2018
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

