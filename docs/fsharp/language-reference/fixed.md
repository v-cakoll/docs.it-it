---
title: 'La parola chiave Fixed (F #)'
description: "Informazioni su come è possibile 'pin' locale nello stack per impedire la raccolta con F # 'fixed' (parola chiave)."
ms.date: 04/24/2017
ms.openlocfilehash: 1bf1b2ad67d2dd7f854e569cfca7c06e8aec7f4c
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2018
ms.locfileid: "44271728"
---
# <a name="the-fixed-keyword"></a>La parola chiave Fixed

F # 4.1 introduce il `fixed` parola chiave, che consente di "aggiungere" una variabile locale nello stack per evitare che vengano raccolti o spostate durante la garbage collection.  Viene usato per gli scenari di programmazione di basso livello.

## <a name="syntax"></a>Sintassi

```fsharp
use ptr = fixed expression
```

## <a name="remarks"></a>Note

Estende la sintassi delle espressioni per consentire l'estrazione di un puntatore e associarlo a un nome di cui viene impedito di essere raccolti o spostati durante l'operazione di garbage collection.  

Un puntatore da un'espressione è stato risolto tramite il `fixed` parola chiave è associata a un identificatore tramite il `use` (parola chiave).  La semantica di questo oggetto è simile alla gestione delle risorse tramite il `use` (parola chiave).  Mentre si trova nell'ambito e una volta esula dall'ambito, non è non è più fisso, il puntatore è stato risolto.  `fixed` non è possibile usare all'esterno del contesto di un `use` associazione.  È necessario associare il puntatore a un nome con `use`.

Uso di `fixed` deve verificarsi all'interno di un'espressione in una funzione o un metodo.  Non può essere utilizzato in un ambito a livello di script o a livello di modulo.

Simile a tutte le code di puntatore, questa è una funzionalità non sicura e genererà un avviso quando viene utilizzato.

## <a name="example"></a>Esempio

```fsharp
open Microsoft.FSharp.NativeInterop

type Point = { mutable X: int; mutable Y: int}

let squareWithPointer (p: nativeptr<int>) =
    // Dereference the pointer at the 0th address.
    let mutable value = NativePtr.get p 0

    // Perform some work
    value <- value * value

    // Set the value in the pointer at the 0th address.
    NativePtr.set p 0 value

let pnt = { X = 1; Y = 2 }
printfn "pnt before - X: %d Y: %d" pnt.X pnt.Y // prints 1 and 2

// Note that the use of 'fixed' is inside a function.
// You cannot fix a pointer at a script-level or module-level scope.
let doPointerWork() =
    use ptr = fixed &pnt.Y

    // Square the Y value
    squareWithPointer ptr
    printfn "pnt after - X: %d Y: %d" pnt.X pnt.Y // prints 1 and 4

doPointerWork()
```

## <a name="see-also"></a>Vedere anche

- [NativePtr (modulo)](https://msdn.microsoft.com/visualfsharpdocs/conceptual/nativeinterop.nativeptr-module-%5Bfsharp%5D)
