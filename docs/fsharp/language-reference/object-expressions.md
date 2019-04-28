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
# <a name="object-expressions"></a><span data-ttu-id="aa112-103">Espressioni di oggetto</span><span class="sxs-lookup"><span data-stu-id="aa112-103">Object Expressions</span></span>

<span data-ttu-id="aa112-104">Un' *dell'oggetto espressione* è un'espressione che crea una nuova istanza di un tipo di oggetto creato dinamicamente, anonimo che si basa su un tipo di base esistente, interfaccia o set di interfacce.</span><span class="sxs-lookup"><span data-stu-id="aa112-104">An *object expression* is an expression that creates a new instance of a dynamically created, anonymous object type that is based on an existing base type, interface, or set of interfaces.</span></span>

## <a name="syntax"></a><span data-ttu-id="aa112-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="aa112-105">Syntax</span></span>

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

## <a name="remarks"></a><span data-ttu-id="aa112-106">Note</span><span class="sxs-lookup"><span data-stu-id="aa112-106">Remarks</span></span>

<span data-ttu-id="aa112-107">Nella sintassi precedente, il *typename* rappresenta un tipo di classe esistente o un tipo di interfaccia.</span><span class="sxs-lookup"><span data-stu-id="aa112-107">In the previous syntax, the *typename* represents an existing class type or interface type.</span></span> <span data-ttu-id="aa112-108">*tipo-params* vengono descritti i parametri di tipo generico facoltativo.</span><span class="sxs-lookup"><span data-stu-id="aa112-108">*type-params* describes the optional generic type parameters.</span></span> <span data-ttu-id="aa112-109">Il *argomenti* vengono utilizzati solo per i tipi di classe, che richiedono i parametri del costruttore.</span><span class="sxs-lookup"><span data-stu-id="aa112-109">The *arguments* are used only for class types, which require constructor parameters.</span></span> <span data-ttu-id="aa112-110">Il *le definizioni dei membri* sono override dei metodi della classe base o le implementazioni dei metodi astratti da un'interfaccia o una classe di base.</span><span class="sxs-lookup"><span data-stu-id="aa112-110">The *member-definitions* are overrides of base class methods, or implementations of abstract methods from either a base class or an interface.</span></span>

<span data-ttu-id="aa112-111">L'esempio seguente illustra i diversi tipi di espressioni di oggetto.</span><span class="sxs-lookup"><span data-stu-id="aa112-111">The following example illustrates several different types of object expressions.</span></span>

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

## <a name="using-object-expressions"></a><span data-ttu-id="aa112-112">Utilizzo delle espressioni di oggetto</span><span class="sxs-lookup"><span data-stu-id="aa112-112">Using Object Expressions</span></span>

<span data-ttu-id="aa112-113">Si usano le espressioni di oggetto quando si desidera evitare il codice aggiuntivo e l'overhead necessario per creare un nuovo tipo denominato.</span><span class="sxs-lookup"><span data-stu-id="aa112-113">You use object expressions when you want to avoid the extra code and overhead that is required to create a new, named type.</span></span> <span data-ttu-id="aa112-114">Se si usano espressioni di oggetto per ridurre al minimo il numero di tipi creati in un programma, è possibile ridurre il numero di righe di codice e impedire la diffusione non necessaria dei tipi.</span><span class="sxs-lookup"><span data-stu-id="aa112-114">If you use object expressions to minimize the number of types created in a program, you can reduce the number of lines of code and prevent the unnecessary proliferation of types.</span></span> <span data-ttu-id="aa112-115">Anziché creare molti tipi per gestire situazioni specifiche, è possibile usare un'espressione di oggetto che consente di personalizzare un tipo esistente o fornisce un'implementazione di un'interfaccia appropriata per il caso specifico in corso.</span><span class="sxs-lookup"><span data-stu-id="aa112-115">Instead of creating many types just to handle specific situations, you can use an object expression that customizes an existing type or provides an appropriate implementation of an interface for the specific case at hand.</span></span>

## <a name="see-also"></a><span data-ttu-id="aa112-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aa112-116">See also</span></span>

- [<span data-ttu-id="aa112-117">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="aa112-117">F# Language Reference</span></span>](index.md)
