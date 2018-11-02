---
title: Espressioni di oggetto (F#)
description: "Informazioni su come usare le espressioni di oggetto F # quando si desidera evitare il codice aggiuntivo e l'overhead necessario per creare un nuovo tipo denominato."
ms.date: 05/16/2016
ms.openlocfilehash: 1a971044d680d3bf5a6fff38affdaf001d5403b4
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/02/2018
ms.locfileid: "43865462"
---
# <a name="object-expressions"></a>Espressioni di oggetto

Un' *dell'oggetto espressione* è un'espressione che crea una nuova istanza di un tipo di oggetto creato dinamicamente, anonimo che si basa su un tipo di base esistente, interfaccia o set di interfacce.

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

Nella sintassi precedente, il *typename* rappresenta un tipo di classe esistente o un tipo di interfaccia. *tipo-params* vengono descritti i parametri di tipo generico facoltativo. Il *argomenti* vengono utilizzati solo per i tipi di classe, che richiedono i parametri del costruttore. Il *le definizioni dei membri* sono override dei metodi della classe base o le implementazioni dei metodi astratti da un'interfaccia o una classe di base.

L'esempio seguente illustra i diversi tipi di espressioni di oggetto.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4301.fs)]

## <a name="using-object-expressions"></a>Utilizzo delle espressioni di oggetto

Si usano le espressioni di oggetto quando si desidera evitare il codice aggiuntivo e l'overhead necessario per creare un nuovo tipo denominato. Se si usano espressioni di oggetto per ridurre al minimo il numero di tipi creati in un programma, è possibile ridurre il numero di righe di codice e impedire la diffusione non necessaria dei tipi. Anziché creare molti tipi per gestire situazioni specifiche, è possibile usare un'espressione di oggetto che consente di personalizzare un tipo esistente o fornisce un'implementazione di un'interfaccia appropriata per il caso specifico in corso.

## <a name="see-also"></a>Vedere anche

- [Riferimenti per il linguaggio F#](index.md)
