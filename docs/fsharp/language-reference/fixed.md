---
title: 'La parola chiave Fixed (F #)'
description: "Informazioni su come è possibile 'pin' locale nello stack per impedire la raccolta con F # 'fixed' parola chiave."
author: cartermp
ms.author: phcart
ms.date: 04/24/2017
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 8c1d486ec754335dfbaeec439b1eb949494e4241
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2018
---
# <a name="the-fixed-keyword"></a><span data-ttu-id="67c83-103">La parola chiave Fixed</span><span class="sxs-lookup"><span data-stu-id="67c83-103">The Fixed Keyword</span></span>

<span data-ttu-id="67c83-104">F # 4.1 introduce il `fixed` (parola chiave), che consente di "bloccare" locale nello stack per evitare che venga raccolto o spostato durante l'operazione di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="67c83-104">F# 4.1 introduces the `fixed` keyword, which allows you to "pin" a local onto the stack to prevent it from being collected or moved during garbage-collection.</span></span>  <span data-ttu-id="67c83-105">Viene usato per gli scenari di programmazione di basso livello.</span><span class="sxs-lookup"><span data-stu-id="67c83-105">It is used for low-level programming scenarios.</span></span>

## <a name="syntax"></a><span data-ttu-id="67c83-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="67c83-106">Syntax</span></span>

```fsharp
use ptr = fixed expression
```

## <a name="remarks"></a><span data-ttu-id="67c83-107">Note</span><span class="sxs-lookup"><span data-stu-id="67c83-107">Remarks</span></span>

<span data-ttu-id="67c83-108">Estende la sintassi delle espressioni per consentire l'estrazione di un puntatore e l'associazione a un nome che ha impedito a essere raccolti o spostato durante l'operazione di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="67c83-108">This extends the syntax of expressions to allow extracting a pointer and binding it to a name which is prevented from being collected or moved during garbage-collection.</span></span>  

<span data-ttu-id="67c83-109">Un puntatore da un'espressione è stato risolto tramite il `fixed` parola chiave è associata a un identificatore tramite il `use` (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="67c83-109">A pointer from an expression is fixed via the `fixed` keyword is bound to an identifier via the `use` keyword.</span></span>  <span data-ttu-id="67c83-110">La semantica di ciò è simile alla gestione delle risorse tramite il `use` (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="67c83-110">The semantics of this are similar to resource management via the `use` keyword.</span></span>  <span data-ttu-id="67c83-111">È stato risolto il puntatore si trova nell'ambito, mentre una volta rientra nell'ambito, non è corretto.</span><span class="sxs-lookup"><span data-stu-id="67c83-111">The pointer is fixed while it is in scope, and once it is out of scope, it is no longer fixed.</span></span>  <span data-ttu-id="67c83-112">`fixed` non può essere utilizzata all'esterno del contesto di un `use` associazione.</span><span class="sxs-lookup"><span data-stu-id="67c83-112">`fixed` cannot be used outside the context of a `use` binding.</span></span>  <span data-ttu-id="67c83-113">È necessario associare il puntatore a un nome con `use`.</span><span class="sxs-lookup"><span data-stu-id="67c83-113">You must bind the pointer to a name with `use`.</span></span>

<span data-ttu-id="67c83-114">Utilizzo di `fixed` devono verificarsi all'interno di un'espressione in una funzione o un metodo.</span><span class="sxs-lookup"><span data-stu-id="67c83-114">Use of `fixed` must occur within an expression in a function or a method.</span></span>  <span data-ttu-id="67c83-115">Non può essere utilizzato in un ambito a livello di script o a livello di modulo.</span><span class="sxs-lookup"><span data-stu-id="67c83-115">It cannot be used at a script-level or module-level scope.</span></span>

<span data-ttu-id="67c83-116">Ad esempio tutto il codice di puntatore, questo è una funzionalità unsafe e genererà un avviso quando viene utilizzato.</span><span class="sxs-lookup"><span data-stu-id="67c83-116">Like all pointer code, this is an unsafe feature and will emit a warning when used.</span></span>

## <a name="example"></a><span data-ttu-id="67c83-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="67c83-117">Example</span></span>

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

## <a name="see-also"></a><span data-ttu-id="67c83-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="67c83-118">See Also</span></span>

[<span data-ttu-id="67c83-119">NativePtr (modulo)</span><span class="sxs-lookup"><span data-stu-id="67c83-119">NativePtr Module</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/nativeinterop.nativeptr-module-%5Bfsharp%5D)
