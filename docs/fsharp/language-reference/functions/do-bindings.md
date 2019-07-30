---
title: Associazioni do
description: Informazioni sul modo F# in cui viene usata un'associazione ' do ' per eseguire il codice senza definire una funzione o un valore.
ms.date: 05/16/2016
ms.openlocfilehash: f98f523296bfaceeda35d4861eafbfeaa5a60c32
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630535"
---
# <a name="do-bindings"></a>Associazioni do

Un' `do` associazione viene utilizzata per eseguire il codice senza definire una funzione o un valore. Inoltre, le associazioni do possono essere utilizzate nelle classi, vedere [ `do` binding nelle classi](../members/do-bindings-in-classes.md).

## <a name="syntax"></a>Sintassi

```fsharp
[ attributes ]
[ do ]expression
```

## <a name="remarks"></a>Note

Utilizzare un' `do` associazione quando si desidera eseguire il codice indipendentemente dalla definizione di una funzione o di un valore. L'espressione in un' `do` associazione deve restituire `unit`. Il codice in un'associazione di `do` primo livello viene eseguito quando il modulo viene inizializzato. La parola `do` chiave è facoltativa.

Gli attributi possono essere applicati a un'associazione di `do` primo livello. Se, ad esempio, il programma usa l'interoperabilità COM, potrebbe essere `STAThread` necessario applicare l'attributo al programma. A tale scopo, è possibile utilizzare un attributo in `do` un'associazione, come illustrato nel codice seguente.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet201.fs)]

## <a name="see-also"></a>Vedere anche

- [Riferimenti per il linguaggio F#](../index.md)
- [Funzioni](index.md)
