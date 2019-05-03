---
title: La parola chiave fixed
description: Informazioni su come è possibile aggiungere una variabile locale nello stack per impedire la raccolta con il F# 'fixed' (parola chiave).
ms.date: 04/24/2017
ms.openlocfilehash: 7fdf66560f3e2ab7584b00c7e4584d7f6c161858
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61772658"
---
# <a name="the-fixed-keyword"></a>La parola chiave fixed

F#4.1 introduce il `fixed` parola chiave, che consente di "aggiungere" una variabile locale nello stack per evitare che vengano raccolti o spostate durante la garbage collection.  Viene usato per gli scenari di programmazione di basso livello.

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
