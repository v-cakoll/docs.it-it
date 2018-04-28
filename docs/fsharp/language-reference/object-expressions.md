---
title: Espressioni di oggetto (F#)
description: "Informazioni su come utilizzare le espressioni di oggetto di F # quando si desidera evitare il codice aggiuntivo e l'overhead necessario per creare un nuovo tipo denominato."
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: f5a728823e7abe18aeb604b3991087fd0252698e
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2018
---
# <a name="object-expressions"></a>Espressioni di oggetto

Un *oggetto espressione* è un'espressione che crea una nuova istanza di un tipo di oggetto anonimo creato dinamicamente che si basa su un tipo di base esistente, interfaccia o set di interfacce.


## <a name="syntax"></a>Sintassi

```fsharp
// When typename is a class:
{ new typename [type-params]arguments with
    member-definitions
    [ additional-interface-definitions ]
}
// When typename is not a class:
{ new typename [generic-type-args] with
    member-definitions
    [ additional-interface-definitions ]
}
```

## <a name="remarks"></a>Note
Nella sintassi precedente, il *typename* rappresenta un tipo di classe esistente o un tipo di interfaccia. *parametri di tipo* vengono descritti i parametri di tipo generico facoltativi. Il *argomenti* vengono utilizzati solo per i tipi di classe, che richiedono che i parametri del costruttore. Il *definizioni di membro* sono override dei metodi della classe base o implementazioni di metodi astratti di un'interfaccia o una classe di base.

L'esempio seguente illustra i diversi tipi di espressioni di oggetto.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4301.fs)]

## <a name="using-object-expressions"></a>Utilizzo di espressioni di oggetto
Usare le espressioni di oggetto quando si desidera evitare il codice aggiuntivo e l'overhead necessario per creare un nuovo tipo denominato. Se si utilizzano espressioni di oggetto per ridurre al minimo il numero di tipi creati in un programma, è possibile ridurre il numero di righe di codice e impedire la proliferazione dei tipi non necessaria. Invece di creare molti tipi per gestire situazioni specifiche, è possibile utilizzare un'espressione di oggetto che consente di personalizzare un tipo esistente o fornisce un'implementazione di un'interfaccia per il case specifico.


## <a name="see-also"></a>Vedere anche
[Riferimenti per il linguaggio F#](index.md)
