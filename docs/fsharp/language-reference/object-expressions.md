---
title: Espressioni di oggetto
description: Informazioni su come usare F# espressioni di oggetto quando si desidera evitare il codice aggiuntivo e l'overhead necessario per creare un nuovo tipo denominato.
ms.date: 02/08/2019
ms.openlocfilehash: 63f2c1d7128721b7b8c744e4cf02d73c2a8b4a07
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61666292"
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

```fsharp
// This object expression specifies a System.Object but overrides the
// ToString method.
let obj1 = { new System.Object() with member x.ToString() = "F#" }
printfn "%A" obj1

// This object expression implements the IFormattable interface.
let delimiter(delim1: string, delim2: string, value: string) =
    { new System.IFormattable with
        member x.ToString(format: string, provider: System.IFormatProvider) =
            if format = "D" then
                delim1 + value + delim2
            else
                value }

let obj2 = delimiter("{","}", "Bananas!");

printfn "%A" (System.String.Format("{0:D}", obj2))

// Define two interfaces
type IFirst =
  abstract F : unit -> unit
  abstract G : unit -> unit

type ISecond =
  inherit IFirst
  abstract H : unit -> unit
  abstract J : unit -> unit

// This object expression implements both interfaces.
let implementer() =
    { new ISecond with
        member this.H() = ()
        member this.J() = ()
      interface IFirst with
        member this.F() = ()
        member this.G() = () }
```

## <a name="using-object-expressions"></a>Utilizzo delle espressioni di oggetto

Si usano le espressioni di oggetto quando si desidera evitare il codice aggiuntivo e l'overhead necessario per creare un nuovo tipo denominato. Se si usano espressioni di oggetto per ridurre al minimo il numero di tipi creati in un programma, è possibile ridurre il numero di righe di codice e impedire la diffusione non necessaria dei tipi. Anziché creare molti tipi per gestire situazioni specifiche, è possibile usare un'espressione di oggetto che consente di personalizzare un tipo esistente o fornisce un'implementazione di un'interfaccia appropriata per il caso specifico in corso.

## <a name="see-also"></a>Vedere anche

- [Riferimenti per il linguaggio F#](index.md)
