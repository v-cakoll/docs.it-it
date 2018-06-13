---
title: Espressioni di oggetto (F#)
description: "Informazioni su come utilizzare le espressioni di oggetto di F # quando si desidera evitare il codice aggiuntivo e l'overhead necessario per creare un nuovo tipo denominato."
ms.date: 05/16/2016
ms.openlocfilehash: fed78e2be52838eedf55759b195696f1210a8a20
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33564391"
---
# <a name="object-expressions"></a><span data-ttu-id="357f7-103">Espressioni di oggetto</span><span class="sxs-lookup"><span data-stu-id="357f7-103">Object Expressions</span></span>

<span data-ttu-id="357f7-104">Un *oggetto espressione* è un'espressione che crea una nuova istanza di un tipo di oggetto anonimo creato dinamicamente che si basa su un tipo di base esistente, interfaccia o set di interfacce.</span><span class="sxs-lookup"><span data-stu-id="357f7-104">An *object expression* is an expression that creates a new instance of a dynamically created, anonymous object type that is based on an existing base type, interface, or set of interfaces.</span></span>


## <a name="syntax"></a><span data-ttu-id="357f7-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="357f7-105">Syntax</span></span>

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

## <a name="remarks"></a><span data-ttu-id="357f7-106">Note</span><span class="sxs-lookup"><span data-stu-id="357f7-106">Remarks</span></span>
<span data-ttu-id="357f7-107">Nella sintassi precedente, il *typename* rappresenta un tipo di classe esistente o un tipo di interfaccia.</span><span class="sxs-lookup"><span data-stu-id="357f7-107">In the previous syntax, the *typename* represents an existing class type or interface type.</span></span> <span data-ttu-id="357f7-108">*parametri di tipo* vengono descritti i parametri di tipo generico facoltativi.</span><span class="sxs-lookup"><span data-stu-id="357f7-108">*type-params* describes the optional generic type parameters.</span></span> <span data-ttu-id="357f7-109">Il *argomenti* vengono utilizzati solo per i tipi di classe, che richiedono che i parametri del costruttore.</span><span class="sxs-lookup"><span data-stu-id="357f7-109">The *arguments* are used only for class types, which require constructor parameters.</span></span> <span data-ttu-id="357f7-110">Il *definizioni di membro* sono override dei metodi della classe base o implementazioni di metodi astratti di un'interfaccia o una classe di base.</span><span class="sxs-lookup"><span data-stu-id="357f7-110">The *member-definitions* are overrides of base class methods, or implementations of abstract methods from either a base class or an interface.</span></span>

<span data-ttu-id="357f7-111">L'esempio seguente illustra i diversi tipi di espressioni di oggetto.</span><span class="sxs-lookup"><span data-stu-id="357f7-111">The following example illustrates several different types of object expressions.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4301.fs)]

## <a name="using-object-expressions"></a><span data-ttu-id="357f7-112">Utilizzo di espressioni di oggetto</span><span class="sxs-lookup"><span data-stu-id="357f7-112">Using Object Expressions</span></span>
<span data-ttu-id="357f7-113">Usare le espressioni di oggetto quando si desidera evitare il codice aggiuntivo e l'overhead necessario per creare un nuovo tipo denominato.</span><span class="sxs-lookup"><span data-stu-id="357f7-113">You use object expressions when you want to avoid the extra code and overhead that is required to create a new, named type.</span></span> <span data-ttu-id="357f7-114">Se si utilizzano espressioni di oggetto per ridurre al minimo il numero di tipi creati in un programma, è possibile ridurre il numero di righe di codice e impedire la proliferazione dei tipi non necessaria.</span><span class="sxs-lookup"><span data-stu-id="357f7-114">If you use object expressions to minimize the number of types created in a program, you can reduce the number of lines of code and prevent the unnecessary proliferation of types.</span></span> <span data-ttu-id="357f7-115">Invece di creare molti tipi per gestire situazioni specifiche, è possibile utilizzare un'espressione di oggetto che consente di personalizzare un tipo esistente o fornisce un'implementazione di un'interfaccia per il case specifico.</span><span class="sxs-lookup"><span data-stu-id="357f7-115">Instead of creating many types just to handle specific situations, you can use an object expression that customizes an existing type or provides an appropriate implementation of an interface for the specific case at hand.</span></span>


## <a name="see-also"></a><span data-ttu-id="357f7-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="357f7-116">See Also</span></span>
[<span data-ttu-id="357f7-117">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="357f7-117">F# Language Reference</span></span>](index.md)
