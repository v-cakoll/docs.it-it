---
title: 'La parola chiave Fixed (F #)'
description: "Informazioni su come è possibile 'pin' locale nello stack per impedire la raccolta con F # 'fixed' parola chiave."
ms.date: 04/24/2017
ms.openlocfilehash: 913ee4d7b0f6b2437793d4788e53556d6be6c4db
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="the-fixed-keyword"></a>La parola chiave Fixed

F # 4.1 introduce il `fixed` (parola chiave), che consente di "bloccare" locale nello stack per evitare che venga raccolto o spostato durante l'operazione di garbage collection.  Viene usato per gli scenari di programmazione di basso livello.

## <a name="syntax"></a>Sintassi

```fsharp
use ptr = fixed expression
```

## <a name="remarks"></a>Note

Estende la sintassi delle espressioni per consentire l'estrazione di un puntatore e l'associazione a un nome che ha impedito a essere raccolti o spostato durante l'operazione di garbage collection.  

Un puntatore da un'espressione è stato risolto tramite il `fixed` parola chiave è associata a un identificatore tramite il `use` (parola chiave).  La semantica di ciò è simile alla gestione delle risorse tramite il `use` (parola chiave).  È stato risolto il puntatore si trova nell'ambito, mentre una volta rientra nell'ambito, non è corretto.  `fixed` non può essere utilizzata all'esterno del contesto di un `use` associazione.  È necessario associare il puntatore a un nome con `use`.

Utilizzo di `fixed` devono verificarsi all'interno di un'espressione in una funzione o un metodo.  Non può essere utilizzato in un ambito a livello di script o a livello di modulo.

Ad esempio tutto il codice di puntatore, questo è una funzionalità unsafe e genererà un avviso quando viene utilizzato.

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

[NativePtr (modulo)](https://msdn.microsoft.com/visualfsharpdocs/conceptual/nativeinterop.nativeptr-module-%5Bfsharp%5D)
